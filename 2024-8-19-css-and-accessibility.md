# The Other C in CSS by Sara Soueidan
https://www.youtube.com/watch?v=ob_M_qXeDVE

https://www.sarasoueidan.com/

https://practical-accessibility.today/ (Sara's Course)

CSS and Accessibility - How CSS affects the semantic accessibility of HTML

Accessibility Tree -> contains information about objects, what they are, and what they contain; not visible to users. Only read aloud to users using accessibility software.

4 pieces of info in a tree object:
- Role (What kind of thing is this?)
- Name (How can we refer to this?)
- Description (How can we further describe this thing?)
- State (What is the item's current state?)

It may also contain element properties and relationships to other elements


## CSS Can affect the information exposed in the Accessibility Tree. Some properties may only affect the role of an element in certain browser/screen reader combinations only.

Example:

	/* In some versions of Safari, this declaration
	will remove list semantics */
 
	ul {
		list-style:none;
	}


The above code, on older versions of Safari MacOS, screen readers don't announce the list or the number of items in a list. This could degrade the user experience for disabled users, since they might start browsing through a list seemingly endlessly.

Newer versions of Safari will only remove list semantics unless the list is contained within a navigation landmark. The thought, I suppose, is that if a list is contained within a navigation, that it is important; otherwise not.

Behavior reported as a bug, before a Webkit Engineer (James Craig) pointed this out as a puposeful feature because of "over-use of lists by web developers". He indicates that you can re-initiate list semantics with a code like this:

	<ul role="list">
		<li><a href="/products/">Products</a></li>
		<li><a href="/products/">Products</a></li>
		<li><a href="/products/">Products</a></li>
	</ul>

	ul:where([role="list"]){
		list-style:none;
	}

Or, as the author suggests, you could avoid stripping list semantics entirely by setting list-style-type to an empty string:

	ul{
		list-style-type: "";
	}

Always make sure to fire up a screen reader and test after making a change


## CSS can also completely remove the presence of an element from the Accessibility Tree

There are several ways to hide things in HTML, CSS, and ARIA.

In CSS, there are 7 main ways. Out of this different ways, visibility:hidden and display:none make elements unavailable to the accessibility tree and inaccessible to all users.

The display property controls the type of box an element will generate. So, for example, display:none will mean that no boxes will be generated for the element and it's descendants.


display:contents at the bottom is supposed be similar to display none, where it stops the element itself from generating a box, but will keep the children of that element unaffected. Also, it doesn't hide it from the accessibility tree or rewrite any semantic roles for the element.

At least...that's the intended behavior. The reality is that display:contents has a long history of bugs across browsers that make it almost unusable over the past few years.

Also, in Firefox, display:contents on an element completely breaks the anchor links to that element.

It's been so problematic that one article described it as potentially harmful.

Today, the author's suggestion is to avoid using it (for now), unless you are using it on a very generic container such as a div. That way you are not sacrificing any semantics.

Until all browser implementations are fixed, avoid using it on meaningful or interactive elements.

## Visually Hidden Class

If you write lots of accessible CSS, you are definitely familiar with the visiually-hidden utility class:

	.visually-hidden:not(:focus):not(:active){
		width:1px;
		height:1px;
		overflow:hidden;
		clip: rect(0 0 0 0);
		clip-path: inset(50%);
		position: absolute;
		white-space: nowrap;
	}

It's also known as ".sr-only", but "visually-hidden" is a more appropriate name. This is a way to hide an element while keeping that element accessible, as there's no other native way within CSS or HTML to do so.

Now the :not(:focus) and :not(:active) part of the rule makes sure this rule is not applied to elements that are focused or active. This part is critical, but you see many rules like this in the wild without these specific part. It's fine to use it on text elements, but this part of the element emphasizes how you shouldn't use the visually-hidden class on interactive elements unless those elements become visible when they receive focus.

Interactive elements should ALWAYS become visible when the user interacts with them. Otherwise you create a WCAG violation and usability problem because blind users won't be able to "see" them.

IKEA uses something like this to hide "skip" links on their webpages. Each of these skip links allows users to skip past entire sections of the webpage, making it extremely convenient for keyboard users; when the skip link is focused on, it becomes visible.

> Don't use the visually-hidden utility class to permanently hide interactive elements.

This is a general rule, but there is one exception the author can think of. 

This exception is where you have something that replaces an interactive element. So, for example, if you have an SVG that is meant to replace the basic checkbox element with something more fancy (like something that gets "shaded in" as soon as the user clicks it), you definitely want to hide the native checkbox and animate the fancy checkbox as the checkbox is interacted with it.

More details on this at her blog at https://www.sarasoueidan.com/blog/inclusively-hiding-and-styling-checkboxes-and-radio-buttons/


Example Syntax:

	<label>
		<input type="checkbox" id="c-checkbox" />
		
		<svg width="32' height="32" viewBox="-4 -4 39 39" aria-hidden="true" focusable="false">
			...
		</svg>

		<span>The checkbox label text</span>
	</label>


For our checkbox, we want the checkbox to still be visible to screenreaders, but hide the SVG (since it's redundant).

To hide elements from screen-readers ONLY, we use the "aria-hidden" attribute, which removes the element from the accessibility tree. Use this on the SVG

Now, we want to hide the checkbox itself visually, but keep it available for screen readers. There are 2 ways; either position the checkbox off-canvas, or use a "visually-hidden" class WITHOUT the above addition of ":not(:focus):not(:active)"

But, neither of these techniques is inclusive to those navigating on mobile devices by touch.

> "Touch interface screen readers allow users to run their finger over the screen to find what is directly underneath. This provides the user with a quick sense of an entire interface" (Material Design Accessibility Guidelines)

If you hide an interactive element via "visually-hidden", it will be too small for a user to actually touch, and if you position it off the canvas, it won't be there for users to touch over.

To ensure the checkbox is found by touch, you need to keep it present on the screen by using position absolute to position it above the custom checkbox and set it's opacity to 0. Like so:

	input[type="checkbox"]{
		position:absolute;
		width:1em;
		height:1em;
		opacity:0;
	}

This keeps it accessible for mobile users as well. The SVG becomes "visually-hidden", but is visible for sighted users, while mobile users can find the checkbox by touch.

Use this same technique for any native interactive control that you need to hide and replace with an image.

So, if anyone tells you to just use the "visually-hidden" class to hide interactive elements, remember that that is an over-simplification and over-generalization. Decide whether to use it or not based on whether the interactive element will become visible when it receives focus.

## CSS Can also influence the accessible name of an element

A browser uses an alogrithm to determine the accessible name of an element:
1) Does the element have an *aria-labelledby* attribute? If so, and if the ID in this attribute is a valid reference to an element on the page, it uses the referenced element's computed text to provide the Accessible Name.

2) Otherwise (if *aria-labelledby* isn't present), it checks if the element has an *aria-label* attribute. If it does, it uses the value of the *aria-label* attribute as the Accessible Name.

3) Otherwise, and unless the element is marked as presentational using *role="presentation"* or *role="none"* (in which case, the element doesn't accept an Accessible Name anymore), the browser checks if it can get the name:
     - From an HTML attribute (such as "alt" or "title"; the latter should only be used on IFrames, simply because it's the best way to guarantee an announced Accessible Name across most screen readers )
     - From another element (such as "\<label\>" or "\<legend\>")
     - Or from the element's contents


Most HTML elements can get an Accessible Name in more than one way. If they gets a name in more than one way, it has various priorities, even differing based on elements, to figure out what name is used.

In Chrome DevTools, you can go to an element and look in the "Accessibility" tab on the right, where it will show the elements "Name" computed property and where it's being overwritten in some way.


> The order of priority defined in the Accessibile Name computation algorithm does not define the order of priority that *you* should follow when you provide an Accessible Name to your elements.
> 
> "In fact, when you provide an Accessible Name to your elements, your order of priority should almost be the opposite of the steps in the previous algorithm"

### Order of Priority for naming HTML elements that can be named:

1) Use HTML Content (such as text in an \<a href=""\> or text in a \<button\>)
2) Otherwise, use an HTML attribute or element (such as an "alt" attribute or the \<label\> element)
3) Otherwise, use aria-labelledby referencing an element that's already present on the page.
4) Otherwise, when none of the previous methods is feasible, use aria-label

> "Prioritize native HTML. Unless providing a name for an IFrame, avoid the title attribute completely. And ARIA should be your last resort."
> 
> If you can provide an Accessible Name using an element's contents (like with a link or a button), do that.


## &:before and &:after pseudo-elements 

According to the specification, when the Accessible Name for an element is derived from the element's contents, the browser must include the contents of the &:before and &:after pseudo-elements in the Accessible Name.

So any content that you add to an element via &:before and &:after pseudo-elements could and probably will be announced by screen readers, depending on that content.

Depending on the content you add, you may end up degrading the spoken experienced for screen reader users.

For example, if you use this kind of CSS to add an "info" icon to the front of a link:

	<a href=".." class="info">About CSS Generated Content</a>

	.info::before{
		content: "ⓘ";
	}

The screen reader reads this content as "Latin Small Letter I About CSS Generated Content", including the icon in the Accessible Name, causing the degraded spoken experience.

"Latin Small Letter I" is perfectly meaningless to users. Ideally, the icon should be announced as WHAT IT REPRESENTS, not what it actually is.

There should be alternative text for these icons inserted via CSS. This make sure that the icon conveys the same meaning to non-sighted users that it is conveying to sighted users. Obviously if the icon is an icon that everyone knows the meaning of!

The good news is that some new syntax allows us to add alternative text to the "content" element like so:

	.info::before{
		content: "ⓘ" / "Info";
	}

OR

	.info::before{
		content: url('path/to/i-icon.svg') / "Info";
	}


Sadly,the widespread browser support for this is not quite there yet. Firefox doesn't actually support this at all and the presence of the alt text within the "content" rule invalidates the entire rule.

The good news is that the Firefox support IS COMING down the line. However, the author still doesn't recommend putting in icons in this way.

> Avoid using CSS to create meaningful content that is integral to the understanding of the page.

For a few reasons
- CSS Generated Content will not translate into other languages via automated tools
- The content is only accessible when CSS is available (For example, a user might be using "Reader Mode", which strips away the majority of CSS)
- CSS generated content is not easily customizable and may become inaccessible in Forced Colors environments.
	- Depending on certain Forced Colors modes, the icon can be completely inaccessible or invisbile
- When the url() references a broken image, the alt text of the image is not shown in place of the broken image (in most browsers). But the alt text still contributes to an element's Accessible Name. Resulting in an immediate violation of SC 2.5.3 Label in Name


> "Don't rely on alternative text on CSS generated content, especially for any kind of interactive control. Stick with HTML \<img\>." - Adrian Roselli
> 
> If the content is integral to the understanding of the page, add it in HTML

Does this mean that alt text for CSS generated content isn't useful?

Actually not. Author uses it for providing an empty alt string ("") for all decorative images.

Current Recommendations concerning CSS Generated Content:
- Avoid using CSS pseudo-elements for adding meaningful content. Stick with HTML.
- (When support is there and behavior is consistent) Hide decorative and redundant CSS content by giving it an empty alt text.
	- Until then, you can insert the decorative content into a "visually hidden" \<span\> inside the element to keep it hidden from screen readers.


## CSS Can completely strip an element of it's Accessible Name if the source of the name is hidden in a way that removes from the accessibility tree. (36:57)

For example, if an input field gets it's name from a \<label\> element using "for" and "id" attributes, but that \<label\> is hidden via display:none in CSS, the label text does not get applied to the Accessibile Name on the \<input\> element.

But...

> "By default, assistive technologies do not relay hidden information, but an author can explicitly override that and include hidden text as part of the accessible name or accessible description by using aria-labelledby or aria-describedby" 
>
> -- Accessible Name and Description Computation 1.1 

So, this means that you can use aria-labelledby to re-use the label as an accessible name for the input, even if the label is hidden. Maybe in cases where you can't change CSS, but you can change the markup. In fact, this is actually better for some use cases rather than using the "visually-hidden" utility class.

> My Note: Her next piece of speech is a little hard to decipher, but I think what she is saying is that if you hide the label via the "visually-hidden" class, then it will read the \<label\> text TWICE; once for the label and once for the 
> associated \<input\> element.

"A lot of developers resort to aria-label, but aria-label doesn't translate well and should be your last resort."
> My Note: Presumably, she means translate into other languages?


## CSS does *not* affect the state of an element in the Accessibility Tree

CSS does not affect the semantic state of an element. Like if a checkbox is clicked or not. 

Browsers, on interactive elements like checkboxes, will inform screen reader users of state changes. Like "This checkbox has been clicked/unclicked!". So the user knows changes have occurred as result of their interaction. However, this is not achieved on some custom elements, such as Modals.

If a user clicks on a button and there's no way for that user to see if the button is doing something, it's confusing.

So, if an element controls another element (like a button opening a modal), the element's state must be conveyed to the user, so the user knows that something has happened in response to their interaction. So it needs to expose that state to the user.

When you show a Popover on hover, you actually violate SC 1.4.13: Content on Hover or Focus (Level AA), which indicates that there must be a mechanism available to dismis the additional content without moving pointer hover or keyboard focus. Also, the user must be able to move their cursor to the content without it disappearing, which isn't the case for many tooltips.

As far as screen reader users are concerned, there's no default state indicating that the \<button\> opens this tooltip.

There's no shortage of CSS-only widgets online, but they are usually quite inaccessible. Adrian Roselli also has an article "CSS-only Widgets are Inaccessible" which also goes over this.

> "Modal dialogs must track focus and, when they are closed, focus must move back to the element that opened them. When they are open, the content of the page behind them must be made inert so the screen reader user can't access the content behind the modal while it's open. Users must also be informed that they are 'trapped' in a modal dialog so they aren't confused why their focus has been trapped. For this, you need to use the 'dialog' aria rule."

With the new Popover API now available to us, we can use less JavaScript to create simple patterns that used to require JS to be accessible. There's also an article on what exactly the popover API does and what it doesn't do for accessibility. This article is required reading for anything you do with the PopOver API: https://hidde.blog/popover-accessibility/

> "Popovers created using the Popover API are always non-modal. If you want to create a modal popover, a \<dialog\> element is the right way to go" -MDN

If you use the popover API to create a modal dialog, you still need to use JS to supplement the dialogs expected keyboard interactions. As this is not meant to create a modal dialog, but a non-modal dialog. And you will need JS for all of this.

So, the Popover attribute can be used as a great starting point, but depending on what you use it for, you may need to still use JS to update roles, state, etc...

When you build UI elements, ask yourself if you are making the same affordances to screen reader users and keyboard users as you are to sighted users.

If you remove the modal requirement (and the slight black transparent backdrop) from the rest of the page, this helps because you don't have to trap focus anymore. But when focus moves outside of the navigation, the navigation needs to automatically close. But the Popover API doesn't automatically do this.

Also, it creates a problem under WCAG's SC 2.4.11 called "Focus not Obscured (Minimum) (Level AA)" where the keyboard can focus on something that is behind the navigation and isn't currently visible. This rule indicates that, when focus moves to an element, that it should be *at least* partially visible.

So, basically, use the Popover API as a helper, but use JavaScript to further make sure that it is fully accessible. Also close navigation when keyboard navigation moves outside of it.

## Changes of Context

With more powerful CSS features available today, you can code a lot more in just basic CSS that responds to user interaction. Especially with the :has() selector. While some things are used in appropriate contexts, they can be problematic in other contexts.

Be aware of changes that cause a "change of context". This can violate SC 3.2.2: On Input (Level A)

"Changing the setting of any User Interface component does not automatically cause a change of context unless the user has been advised of the behavior before using the component"

> "Make sure that the user knows what's going to happen next."

Opening a new window, moving focus to a different component, going to a new page (including anything that would look to a user as if they had moved to a new page), or signficantly re-arranging the content of a page are examples of changes of context.

> "Not all changes need to be announced. Changing the background color or the themes on the page, that's not a change of context."

## Hacking your way around using JS will most often create barriers to access

> "When you use CSS to work your way around using JS, always ask yourself if the visual affordances you are providing are also available to screen reader users and if the keyboard experience also matches those affordances."

You may get away with creating some interactive elements without JavaScript. But, you still need JS to convey state, update properties and values, and update roles. As well as expected keyboard interactions where they are needed.


## Progressive Enhancement

Big proponent of progressive enhancement and the rule of least power

"The rule of least power is a design principle that suggests choosing the least powerful \[computer\] language suitable for a given purpose" - Wikipedia

"The rule of least power is all about evaluating technology; choosing the most appropriate technology for the task at hand" - Jeremy Keith

CSS is not "the most appropriate technology" to create custom interactive widgets.

HTML carries semantics and meaning, and their elements come with keyboard interactions built in. You will need to use ARIA and JS to add semantics and meaning to other elements.

> "Always think about how the code you write affects the user experience, instead of just your developer experience."

> "If a trade-off needs to be made, always put user needs above all."


## Questions
Author personally uses visually-hidden class mostly for text content.


## Master Table of all CSS and HTML Hiding techniques

| Technique                                 | Exposed to a11y APIs | keyboard accessible | visually accessible (rendered) | children exposed to a11y APIs |
| ----------------------------------------- | -------------------- | ------------------- | ------------------------------ | ----------------------------- |
| display:none;                             | No | No | No | No |
| visibility:hidden;                        | No | No | No | No |
| opacity:0; and filter:opacity(0);         | Yes | Yes | No | Yes |
| clip-path: inset(100%)                    | Yes | Yes | No | Yes |
| position (off-canvas)                     | Yes | Yes | No | Yes |
| .visually-hidden class                    | Yes | Yes | No | Yes |
| hidden attribute                          | No | No | No | No |
| inert attribute                           | No | No | Yes | No |
| tabindex="-1"                             | Yes | Not reachable via tab key | Yes | Yes |
| disabled attribute                        | Yes | Not reachable via tab key | Yes | Yes |
| aria-hidden attribute                     | No | Yes | Yes | No |
| role="none"/role="presentation" attribute | No | Yes | Yes | Yes, unless they are semantically tied to the element |





# Look into further:
- Forced Colors Modes
- Speech Control Users
- Popover API
