# Creating Accessible Websites by Stefany Newman - Course Notes
https://www.udemy.com/course/creating-accessible-websites/


## Lesson 3: Semantic HTML
First step in accessibility is using semantic HTML

If you remove the href attribute from a link, it becomes basically nothing; basically like a div element.

Use a button element for a hamburger menu.

Unsemantic - Coding custom form controls
	- Everyone hates filling in forms; making them pretty isn't going to make them any easier
	- Form controls have a lot of accessibility built into them

What if I'm forced to use an unsemantic element?
	- If you absolutely have to, you need to make the element behave as a different element
	- For example, if you have a <a> link as a hamburger menu, use a role="button" and tabindex="0", which will make them focusable

Which element to use?
 	- Ask stack overflow or accessibility friends


### Additional Context
From MDN Docs on tabindex (https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/tabindex)

> tabindex="0" means that the element should be focusable in sequential keyboard navigation, after any positive tabindex values. The focus navigation order of these elements is defined by their order in the document source.

## Lesson 4: Color Accessible Webpages
1 in 200 women and 1 in 12 men are both colorblind

A myth is all colorblind people only see black and white; lots of diff types. Some peoople can't see Red and Green or Blue and Yellow. As well, in rare cases, people see in grayscale

Recommendation is to design in grayscale because if your website looks good in black and white, it'll look good for all colorblind people and in color

Some people who are Red/Green colorblind, they can differentiate between colors if they are very high contrast, but not otherwise

### Red/Green Colorblindness
For these people, red and green appear almost exactly the same in a lot of cases

### Blue/Yellow Colorblindness
For these people blue and yellow often appear as the same


### Do not rely on color to transfer meaning
If you have an error, do not solely use a red color; use a warning icon or make the text stand out by making it bold or increase the font size

Color is fickle. For example, an Amazon Kindle lets you browse websites, but it only does it in Grayscale, so this is also an example of a time when relying on color to transfer meaning might also affect regular non-disabled users.

Example
	- Pick a color for your t-shirt; color swatches without names included
	- Make sure you have text next to each color swatch to make it easier for colorblind users


Example
	-A form; on errors, they show errors, but they make those errors look the same as the rest of the text. They are just in a red font. To a colorblind person, the errors don't stand out. Also makes it worse if a primary color of the website is ALSO red.
	- Fix by adding a warning icons to the errors and making them stand out by increasing the font size

Contrast between text and a background
	- Bad for Colorblind people
	- Also bad for older people; vision starts to go downhill by the time we reach 40. Once we get older, our ability to distinguish colors decreases between low contrast colors
	- Gray background with light gray text is bad
	- If you think "this is a little difficult to read, but I can read it just fine", you should double check and run it through a color contrast checker or change it up
	- If you are forced to use colors that have a lower contrast, it is possible to achieve sufficient contrast by enlarging the font size and bolding the text
	- Use https://webaim.org/resources/contrastchecker/ for checking color contrast of links against a background

Hover effects
	- Example on a Nav
	- Usually, the button darkens on hover, which is something you shouldn't do. Run it through grayscale to check.
	- If you can use color and border, that's perfect for colorblind people!
	- Alternatively, you could make the text of the element go bold on hover
	- Design in grayscale; If it looks good in gray, it'll look good in color
	- Some people say don't use red/green colors because that's the most common type of colorblindness, but instructor disagrees. As long as you are using color as only a secondary point of importance, it's fine to use red and green.


Google Chrome DevTool - Emulate Vision Deficiencies
	- In Chrome DevTools, you can emulate different visual deficincies
	- Open Dev Tools, then press Ctrl+Shift+P and type "Rendering" and click the "Show Rendering" option


## Lesson 5: ARIA Attributes

ARIA (Accessible Reach Internet Applications) attributes make HTML elements more accessibility and make it easier for screen readers and other assistive tech to understand. Most of them start with "aria-"

- aria-label - Labels current element with the custom text
- aria-expanded - Shows whether or not the current element is expanded; like on a hamburger menu. "false" or "true". For example, on the hamburger, you need to have it read "false" when not open, and "true" when you click on it

- aria-labelledby - Indicates that the image is labelled by a specific caption or text; use the ID of your caption element within the attribute value


Example of aria-label
	- On icons inside of links - If you just add the icon inside the anchor tag, it isn't very accessible. Visually disabled users wouldn't know that the icon is to Instagram, for example.

role attribute - change the semantics of the element. always add "tabindex=0" after the role attribute. This will make sure the element gets added into the tab order

## Lesson 6: Accessible Images

Background images don't need any accessible fixes, as screen readers will just skip them. However, any image added with the <img> tag needs an "alt" attribute.

Decorative images should have a blank alt attribute, because otherwise the screen reader will just read the filename

Also, don't use "Image of" in your alt tags, because it will be already known from context that the alt is connected to an image. If your alt tag contains more than one sentence, be sure to use punctuation.

Image inside of a link
	- Fill in the alt attribute of the Image
	- Treat it as if there is no image and just put where the link leads

E-Commerce products
	- Be even MORE descriptive, because someone is going to need to make a purchase decision based on these details

Use "aria-labeledby" with a blank alt if a caption labels the image, and point the aria-labelledby to the ID of the caption element.
	- Course author actually doesn't use this because it tends to repeat the description twice; once for the alt attribute and once when it browses over the actual caption
	- She suggests just use a blank alt tag if there's a caption nearby as the caption will help blind users figure out what they are looking at.


Images with text baked into the image
	- You have to put the full text into the alt attribute

## Lesson 7: The "outline" Property 

Every time you focus on an element with a keyboard, an outline should appear around it.

For some reason, most webmasters hate the outline and get rid of it, which is really bad for accessibility.

Outlines make it easier for users to figure out what element they are on while navigating through the site. They should be on buttons and links or anything interactive

By default, browsers have outlines too. But, author strongly recommends that you have a custom outline. The default browser outline isn't as visually striking as a regular outline.

Firefox's outline is also pretty bad for users who see with high contrast.

You can use a CSS property like this:

	*:focus{
		outline: 4px solid lime;
	}

How to choose the color?

Go with your design color, but change up the primary color to be the opposite. So, if your site is Red, use a Green outline.

ON buttons, make sure that their hover styles (typically darken the button color), set the button :hover effect to use the same effect on focus. So this:

	.btn-primary:hover{
		background-color:blue;
	}

becomes this:

	.btn-primary:hover,
	.btn-primary:focus{
		background-color:blue;
	}

But, this doesn't make it to where you don't need to apply an outline!

Navigate through the site and see what elements don't have an outline or a bad outline and fix 'em!

Sadly, just because you applied an outline to all eleemnts on focus, doesn't mean that those elements will all get the outline. You've got to go through and test manually.

## Lesson 8: Tabindex

The way keyboard users navigate a site is by pressing the "tab" key to navigate through interactive elements (buttons, links, font controls, etc...)

Every element has a "tabindex". This is an automatically assigned attribute that gets incremented as elements are added to the page one after the other.

What happens if you want a non-button to be interactive?
	- Add tabindex="0"

The tabindex 0 is going to just add this element into the tab index "tree". It just tells the browser to add it to the interactive element tree

Don't add tabindex=0 on any element that doesn't have any interaction associated with them. Also don't add tabindex=-1 to interactive elements.

If you set the element as "display:none", the element automatically gets removed from the tabindex. Same thing if you use the "hidden" attribute

What if you want to remove an element from the tabindex?
	- Use tabindex="-1"
	- However, you can still be able to select and animate the element via JavaScript

Only use tabindex 0 and -1. No other numbers.


You can also use tabindex=-1 on modal windows when they are not in view, since you won't want users to be able to select it when it's not displayed.

It isn't suggested that you should create a div into a button, because there's a lot of functionality baked into the <button> and <a> elements to make using those much easier.

## Lesson 9: Bypass Blocks

If you don't have bypass blocks on the site, keyboard users will have a lot of issues navigating it because they have to go through the entire site just to book an appointment or something like that.

This is why this is a level A element in WCAG

These manifest usually as a link that allows blind users to skip straight to the main content

These are typically used at the very least at the top of your site, but if you have a lot of repetitive content, they could also be useful to add into that.

For example, on a product listing site, if you have a Filter on the leftside of the site, you might give the blind user an option to skip directly to the items on the site.


### Adding a skip link

	<div class="skip">
		<a href="#content">Skip to main content</a>
	</div>

	.skip a{
		position:absolute;
		left:10000px;
		top:auto;
		width:1px;
		height:1px;
		overflow:hidden;
		font-size:2em;
		background-white;
		font-weight:bold;
		display:block;
		padding:10px;
	}
	skip a:focus{
		position:static;
		width:auto;
		height:auto;
	}

It's also not a good idea to use IDs in your css. IDs should be something special

It's important for skip links to not be shown immediately (so sighted users don't have to deal with them), but they can be shown once users press the "tab" key


## Lesson 10: Accessible Video & Audio for the Web

For videos and podcasts, you should provide captions for them, which makes it easier for disabled people, but also for search engines, as Googlebot can't play videos or podcasts.

You can get captions by doing it yourself or hiring a freelancer or company to do it for you.

Another options is computer generated captions, but they are quite unreliable, especially if the speaker has an accent.

Two types of captions
	- Open Captioning - Where the captions are "baked into" the video, and all languages have to appear at once. Good for language learning videos, but you are limited in space and the captions will be in the way if you are viewing the video on a narrow viewport
	- Closed Captioning - You can turn these on and off and put them in different languages, but you have to have a video player that supports this and the toggle needs to be easy to find.

Quality captions include:
	- Correct grammar & punctuation
	- All on-screen text, e.g. if the speaker is showing something written in a book or a sign and doesn't say it
	- Audio description e.g. "chimes", "monitor beeping erratically", "door hisses open"
	- Placement that doesn't block important things on the screen (e.g. the speaker's face)

For live broadcasts, live captioning should be provided. The House of Representatives require live captioning contractors to capture accurately 98.6% of all that's being said live. There are also various companies that provide live captioning to events.

If you are hosting a conference, you should provide live captioning so that deaf / hard of hearing people will be able to enjoy it and it will also help people with ADHD.


### Providing sign language translation
Sign language isn't universal nor is it "English on the hands". If you want to add a picture-in-picture sign language translation to your videos, you need to know your audience. There are roughly three hundred sign languages in the world, so you have to figure out which nationality will your visitors be which can be daunting.

If you have an e-commerce site and you are shipping only to USA and Canada, you only need ASL(American Sign Language) and Langue des Signes Québécoise (LSQ) translation. However, if you live and ship in Quebec, just the latter will suffice. So delve into your site analytics and determine the best way to serve your visitors.

You can provide picture-in-picture sign language translation by getting the interpreter's recording and embedding it into the video with a video editing program. Make sure that the media player supports full screen, otherwise the box of the translator might be too small and deaf / hard of hearing  people won't be able to see it. You can also provide side-by-side videos of both the original recording and the interpreter one.

### Avoid harming your audience
Flashy video or animation can harm your visitors if they are suffering from photosensitive epilepsy. It's one of the many reasons why you should never autoplay videos. Before you add a video, watch it and if you are doubting the content is seizure inducing, try consulting with a medical professional. If you must absolutely display such a video, add a warning and don't autoplay it.

Seizure inducing media can even harm people without epilepsy. Children are especially vulnerable. In 1997, a single episode of Pokemon triggered a seizure of over 700 kids and some adults. The serie had red and blue lights flashing for a few seconds, both things that trigger seizures. Imagine something like that autoplaying as a hero video on a website!

Be also careful of auto-playing carousels. While you should avoid adding a carousel  on a website altogether, nowadays fancy and flashy animations are very popular with slideshows.This poses serious risk of inducing seizures or at the very least, migraines.

CSS animations can be even more dangerous because they always autoplay and can't be paused, so you can't even add warnings.

CSS animations have become very popular recently and while they can be helpful, if done poorly they can have the same negative effect. Always check if your animation will be a seizure trigger. After all, one animation send over 700 people to the hospital.

# Making a Real Life Website Accessible
In this section we will be coding a website that's actually currently inaccessible

## Lesson 11: Inaccessible Website Overview
- First problem: No outline on focused elements
- Second problem: Google Maps Iframe has no title, so screen readers will skip it
- ~Buttons here, but these are links that are styled as buttons. Don't do this~

> **Personal Note:** Respectfully, I disagree. As long as links point to other pages, 
> and buttons do something on the page, I think we can definitely style a link 
> as a button. It's way better than setting up a button element that's hacked 
> to send users to another page

Emojis are announced by newest screen readers, but older ones will only announce the unicode code for the emoji
Carousel totally inacessible
Contact form has no labels, only placeholders, and not a descriptive submit button
Social Media Icons are too claose together and don't have an aria label

Link opening in new tabs bad for accessibility

## Lesson 12: Accessible Navigation
First thing we need with accessible navigation is good contrast between navigation items and the background of the navigation bar

Navigation all uppercase - bad for accessibility
	- Screen reader might mistake "CONTACT US" as "Contact U.S."
	- Use sentence case or title case for links in your navigation
	- If you need navigation to be bigger, increase the font size

You don't need to underline links on the navigation, due to the fact that screen readers will announce it as a navigation and those links are obviously visually different from links elsewhere.

Good Nav:

	<nav>
		<ul>
			<li>
				<a href="">Home</a>
			</li>
			<li>
				<a href="">Services</a>
			</li>
			<li>
				<a href="">New Patients</a>
			</li>
		</ul>
	</nav>

If you have multiple navigation elements on the site, it's a good idea to use an aria label on the nav element indicating what navigation this is:

	<nav aria-label="Main">

Don't use navigation in your aria-label due to the fact that will make the screen reader say "navigation" twice.

However, if you only have one navigation element, you don't need to label it.

Also don't space your letters in your nav too close together as that will make it harder for seniors to read.

Also, be sure to highlight in a nav what page the user currently is on by making that link slightly darker background.

As well, make sure that you use "aria-current='page'" attribute to indicate to screenreaders that this page is what the user is currently on.

Never use the "title" attribute on navigation links. It's not accessible and was used in the past before there were a lot of tooltip elements. A screenreader is going to also announce the title and the text of the link at the same time.

Navigation needs to be accessible by keyboard especially so. So this is where an outline is useful.

Why use outline instead of border? They're the same thing, right?
	- Outline doesn't move your content around, because the outline is almost added similarly to "position:absolute"
	- Border would increase your elements height/width as it is activated.

## Lesson 13: Accessible Hamburger Menu
Most websites don't have a good hamburger menu.

Use a button element for a hamburger element.

All hamburger menus should 
- Be navigable by the Tab key
- Should announce through the screen reader when the menu is expanded and collapsed
- Use an "aria-label" or a visible label (author says visible label, but she's pretty hyper accessibility)
- Use aria-expanded

	<button id="hamburger" aria-expanded="false">
		<span>Menu</span>
		<svg aria-hidden="true"></svg>
	</button>

The problem with full text-transform uppercase text is that it is typically really bad for people with dyslexia, because all of the letters are the same size and the same shape (basically a rectangle) and so it makes it harder for dyslexic people to read that text.

The author also tries to makes sure the menu is 44px square, which is a WCAG AAA Success Criterion and is easier for people with Cerebral Palsey or Parkinsons (since they usually have hand tremors) and for people on phones

Hamburgers should expand on Space or Enter key

When you click on the hamburger menu, the focus should stay on that element, and then when the tab key is pressed, it proceeds to the first element of the navigation. Nothing else should get in the way.

Very important to tweak the aria-expanded via JS as the menu is opened and closed.

**Final Course Note:** If you want to make the hamburger even better, you can make it "progressively enhanced". This means that if the user has their JavaScript turned off, the menu shows up expanded on page load, but if their JavaScript is enabled, the menu should be collapsed upon page load


> **Personal Note**: This seems a little overkill to be honest. There's not a whole
> lot of people out there browsing websites without JavaScript. I do regularly try to
> use CSS where JavaScript could otherwise be used, and most of the guidance I've 
> found elsewhere says that's the main thing you should be doing.


## Lesson 14: Accessible Google Maps Iframe

A google maps Iframe is very convenient, but isn't too accessible for screen readers. Often times screen readers can't even read the address or directions from the map, especially if the map is smaller.

Everytime you add an iframe on your site (any type of iframe, not just Google Maps!), you need a "title" attribute so screen readers can read what the IFrame is supposed to do.

The next challenge is that we need to add in the address separate from the Iframe so users with screen readers can read that.

Another thing that would be useful, is to add driving drections in a text-based format.

Nittany Lion Inn has a very accessible google maps page
- Map is the full container width
- It lists the establishment name, address, and phone numbers below the map
- It also has a separate driving directions page that gives a text-based version that has driving directions from several sections nearby.

You can also use common sense language to describe where your business is located "In the Turtle Creek Mall, next to the Target".

In Summary
- Give all IFrames a title
- List address separately from the map
- Explain in common language where the location of the Iframe is
- Link out to a separate page for driving directions


## Lesson 15: Accessible Contact Forms
First problem with the form is that there are no associated labels with the inputs. Designers often do this and just use the placeholders in the individual textboxes as labels. However, not all screen readers will announce the placeholders as the names of these fields.

"...which is what makes using placeholders as labels so inaccessible and you should never do that." - Author Quote

Also, using placeholders secondarily is also a very bad idea because the contrast of the placeholder text won't be very high against the background of the field. This isn't great for people with visual impairments or older people, because it makes it harder for them to read.

"You shouldn't use placeholders at all. The boxes should be empty with labels. This is the most accessible you can get in a form." - Author Quote

On Textareas, you can't add placeholders. However, there are some JavaScript solutions some people use where you add text to the text area, but on click you clear the textarea. This is bad because the placeholder text for the textarea might make users think that the form field is populated.

### Fixing the Form

"The first thing we want to change is; every form must have a heading, okay?" - Author Quote

In the example, there is a paragraph that we have given the appearance of a heading. This is bad because people who use screen readers or keyboard users sometimes actually use the headings to navigate to the different sections of the page.

Next thing we want to fix are the input fields with labels

You can add labels in two ways and they are both accessible:
- You can add the input field within a <label> element
- Or, you can add the label elmement anywhere around it, and give the <label> element a "for" attribute with the ID of the associated input.

If you need more context for a field, never add more than one <label> per input, but you can always add a <span> or <p> element for that additional context.

Also, you can add a <span> to contain the * element to further separate that from the label text

If you can't mark a field as "required", due to the fact that you need to code up a custom JavaScript validation for it, you can use an ARIA attribute for that!

**aria-required** will mark a field as required for screen readers. Uses values of true/false.

Last thing we have to do is fix the submit button. "Submit" is very vague and not good for accessibility. So, instead, write out what the form is actually going to do after you hit the button.

In the example, instead of "Submit", we use "Send Message"


Another thing that's nice to do for non-sighted users is to add **aria-hidden** to the asterisks marking the fields as required. Blind users know that the fields are required due to either the "required" or "aria-required" attributes, so adding the stars is both redundant and could cause confusion.

As well, you should also make sure that, as the user is tabbing through the form, that each hit of the "Tab" key sends them to the next field to fill in.

Sometimes you see links in between input elements "Read our Privacy Policy" or something like that. Author says you shouldn't do that because it's annoying and gets in the way.

Also, when focusing on the form field elements, there should be an outline or different colored border when the field is currently focused on.


## Lesson 16: Form Instructions
If you want to use the asterisk to denote which fields are mandatory, you need to provide instructions on top of the form denoting what the asterisks are used for.

On submit, the author makes a paragraph appear above the form saying "All fields marked with an asterisk (\*) are required"

Even though we added required on each field and screen readers will announce fields as required, people who aren't using screen readers need more context on how to populate the form correctly.

## Lesson 17: Accessible Icons
First step is to use the right markup. SVGs are preferable because you don't have to load another font, they're scalable, and they have the best semantics for icons.

Second thing is to give icons sufficient contrast against the background. Older people and people with visual impairments won't be able to see them

Always put text next to the icons; always. That way it's very obvious what the icons mean. 

Only reason you don't put text next to them is if you are placing Social Media icons. Unless the social media icon is extremely rare, at which point you might want to place text.

Why are you using the icon?
- Decoration?
- Transfer Meaning?

"Any icon is ambiguous. Never never assume the user knows what the icon is. Always put the text right next to it, unless it's really well-known Social Media" - Author Quote

For decorative icons, set **aria-hidden** to "true"

For social media icons links using SVGs, add an aria-label to the link and set the inner svg to have an attribute **aria-hidden** to "true".

Don't be afraid to hide icons if you are just using them for decoration.

If you are using font icons instead of SVG icons, do the exact same thing. Set an aria label on the link and then hide the icon itself with aria-hidden.

## Lesson 18: Accessible Links

Author gives basic of accessible links, but says you should look up more details about it, because it can be quite complicated.

Things to look for a link:
- Contrast of the link against the text and the background
- Link should have an outline when being focused on


For links that open in a new window.

"This is very inaccessible and you should never use target='\_blank'." - Author Quote

If, for some reason, you **have** to open a link in a new tab, there are a few things that you can do to make it more accessible. You need to notify the user that the link is going to open in a new window with a "link external" icon or an ARIA label that ends with "- opens in new tab".

Another solution is to use "aria-describedby" and set that to a hidden div that has the "opens in new tab" text inside of it. Basically what this will do is read the text of the link first and then go and find the element that aria-describedby points to, and then read that text next.

With both solutions, you should hide any external link icons from screen readers.

The next problem is that the link doesn't look like a link, minus a slightly different color. The way to do that is with an underline via text-decoration.

"Now, we need to bring back text decoration for links. And I know people like to disable them, but it's actually bad. So you should never disable the line in links." - Author Quote

Also, don't use text-decoration underline on normal text, because people will think it's a link.

"If you want to add emphasis to text, use bold, not underline" - Author Quote


Also, don't name links generically. Because people use tab order or people that use screen readers typically skim through stuff by tabbing through the focusable elements, that makes links that are named "here", for example, really bad for accessibility.

Instead of 
	<p>... To make an appointment, click <a href="">here!</a></p>

Use:
	<p>... <a href="">Make an appointment today!</a></p>


On an image inside of a link, you should make the "alt" the text that you would use if the image wasn't there. So this, for example for a main logo:
	<a href="/" class="logo-holder">
		<img class="logo" alt="Homepage" src="/assets/templates/images/logo.svg">
	</a>

For sighted users, it's a bit more of a challenge to make sure that they know that the image is a link. Because if you make the image look like a normal image that's not a link, sighted users might not pick up on it.

The author likes to keep the underline even under a linked image to indicate it's a link.

> **Personal Note:** I think rather than add an underline on linked images, 
> what you should do is to make the image have a color overlay via an :after 
> element that appears only on hover. This is WAY more obvious to sighted users 
> and probably way more obvious to people with other visual disabilities, like 
> those who need high contrast.

> Plus this is WAY better design than having a random underline underneath


## Lesson 19: Test our Website with NVDA screen reader on desktop with Chrome

At one point, the screen reader reads "Main Navigation Navigation". It's not a giant accessibility violation, but it is definitely annoying to users that use screen readers.

You need to write down any bugs you come upon as part of the audit so you can address them later.

The IFrame is made by Google Maps, so you can't actually fix that issue directly. But, please repoprt the issue to the vendor so they can fix it.

On an actual form, you also need to test the form when it succeeds and when it errors out.

Use tab key to navigate between interactive elements, while you use the arrow key to enter "Browse mode", which announces absolutely every element, which is useful for blind users reading text on a page.

A failure that makes browsing the site annoying is a stray \<hr\> element, which is used as decoration. But you should mainly use CSS for decoration rather than HTML elements.

Do not have blank elements, as that can make things confusing or hard to navigate.

Some screen readers announce the Copyright symbol as "Copyright", so if you have "Copyright (c) Furbaby All Rights Reserved", it will read it as "Copyright Copyright".

Author of the course suggests that, instead of having an actual interactive Google Map on the homepage, that we should just replace it with an image with a good alt tag and perhaps have the actual interactive Google Map on the Contact page.

It is smartest to test websites as you develop them so you can catch bugs early.

## Lesson 20: How to Test an Accessible Website

Author says that ideally, you want to test the website with 4 screen readers; NVDA, JAWS, and mobile screen readers such as VoiceOver and TalkBack

Test via Chrome Lighthouse to find further accessibility violations. However, don't use these automated tools as the only method to test these kinds of websites.

### First - Test if all interactive elements are focusable.

### Second - Zoom into the website with Ctrl++ or By holding down Ctrl and using your mouse wheel to zoom in. 
- Zoom in 200% and then 400% and make sure things look okay. This is based on the WCAG criteria. When you get down to 400%, most stuff should be in one column.
- Horizontal scrollbar bad when being zoomed in, unless within a table or a big flowchart.

### Third - Accessibility Checklist
- (https://www.a11yproject.com/checklist/). 
- This makes sure you don't forget some things.
- Most of the time (99.9%), under WCAG criteria, the author targets only up to AA criteria.

### Fourth - High Contrast Mode Testing
After this, the author will go ahead and look at the website in high contrast mode. Even though it's not in the WCAG, it's good user experience to make things work for those users and you can still possibly get sued for it.

"High Contrast Mode only works in Edge" - Not sure that this is still true, as Chrome has a High Contrast mode option.
	- Go to Searchbar and go to "Ease of Access High Contrast Settings", and turn on the "high contrast" setting.

The logo isn't showing because it's a black logo on a black background. Author has no suggestion other than to involve a graphic designer to make the logo work better on high contrast mode. It's also not showing as a link, because links are highlighted in yellow.

After this, the site should be good to go!

Also, make sure the website scrolls when using the arrow keys.

Further Tip - If you have friends who are accessibilty experts, send it to them and see what they think, because they might see accessibility issues that you don't see. Kind of like an editor for an article.

When you zoom more than 100%, the text must enlarge or scale as you zoom. Otherwise it's not accessible. Some web developers disable that function if you zoom more than 100%, so make sure that works and that the columns and layout scale at the same time.


# Advanced Web Accessibility Techniques

## Lesson 21: Acccessible Vanilla JavaScript ToDo App - Part 1: Overview

A ToDo List where each element has a checkbox, label, and "Delete Task" button. The task of this section is going to be making this ToDo list in an accessible way.

Idea was inspired by "Inclusive Components" ToDo List article.
https://inclusive-components.design/a-todo-list/

First lesson is going to be the actual HTML/CSS and then the second part is going to be the JavaScript.

## Lesson 22: Acccessible Vanilla JavaScript ToDo App - Part 2: Coding the HTML

People with screen readers will also use hadings to navigate through pages if focusable elements aren't there.

Author Adds a tabindex=-1 on the H1 - She says this is to make the element interactive when tabbing
> ~~ This is just plain wrong; it should be tabindex=0 if she wants it to be interactive ~~
> Welp, I was wrong. Apparently this gives the H1 the ability to be focused by JavaScript, but keeps it out of the flow of keyboard accessible elements.


Author adds a form, even though there is not going to be any "submit" action associated with it. It makes way more accessible semantically if you use the form element by default and then put your input and labels inside that element.

Add an action attribute to the form. Author mentions she is going to later prevent the default action from triggering via Javascript. However, you do need to add text in the "action" attribute to validate as valid HTML. Also set the method to "post".

Author sets label to "Add a new task to your list (required)" just because there's only one. 

Author also adds a \<div\> within the \<label\> and adds an \<input\> inside of that.

She also set the Submit button to have the value of "Add" since that's more valuable than the default "Submit" value.

Author explains that there should be a hint to the users of what kind of value goes in the textbox. Most people use the "placeholder" element, but the placeholder element isn't that acccessible for those with high contrast vision and such.

Another problem is that this kind of hint goes away once the user starts typing, or if the field gets auto-filled with autocomplete. Her recommendation is to add other text on the form that makes it apparent what the hint is:

	<div id="example">
		Example: Feed the Chicken
	</div>

Then, set the "aria-describedby" on the input element to this:

	<input aria-describedby="example" ...

This example must be within the form and can't be a second \<label\> for the input.

The next thing is to add an empty list and what the author calls a "Live Region", which is a markup that you mark with a role saying "you are in charge of notifying the screen reader of any change with the page"

You can use a role of "alert" or "status" on a \<div\> element, and "aria-live" to "polite". You can also set the aria-live to "assertive".
	Polite will wait for the screen reader to be done with it's current elements before announcing this text
	Assertive interrupts the screen reader in the middle of it reading other things.

So something like this:

	<div role="status" aria-live="polite" id="feedback" class="feedback">

Also, she doesn't hide this "status" field, because screen readers have very mixed support for aria-live and may get confused if it's set to display none.

Next lesson we add the styles and JavaScript to make this a little nicer and make it actually work.


## Lesson 23: Acccessible Vanilla JavaScript ToDo App - Part 3
> Note: She's writing most of her JavaScript in very basic vanilla JS without Jquery. I have converted most of these code examples into JQuery since I mostly use that.

Time to code in JavaScript

Need to add value to the status element or "live region" so the screen reader knows what just happened after the item is added to the list. So use this kind of function:

	function screenReaderFeedback(task,feedback="added"){
		// $("#feedback").text($task + " " + $feedback)
		$("#feedback").text(`${task} ${feedback}.`); // Using Template Literals
	}

Template Literals are basically f strings for JavaScript.

She enlarged input and submit button because WCAG tells you that elements need to be at least 44px wide by 44px high.

> ### JavaScript Bubbling
> If you click an element and that element has a click event, that click event actually moves it's way all the way up the DOM tree to the top level \<html\> element
>
> YouTube Video Tutorial about Bubbling: https://youtu.be/SqQZ8SttQsl

Since we don't know how many delete buttons there are, we're gonna use this bubbling method to activate the specific button. We target the #list that contains all tasks and checks that for a click element instead of the delete task button directly.

	$("#list").on("click",function(){
		if($(event.target).hasClass("delete_task")){
			const $li = $(event.target).parent();
			$li.remove();
		}
	});

However, on this Delete Task button, we have a problem. Basically, when you delete the task, the focus ring disappears, forcing users who are blind and using screen readers to navigate the page to "lose their place".

There are different ways to skin this cat. However, what the author is deciding to do is to focus on the \<h1\> heading when the task is deleted.

	function moveFocus($element){
		$element.focus();
	}

	$("#list").on("click",function(){
		if($(event.target).hasClass("delete_task")){
			const $li = $(event.target).parent();
			$li.remove();
			moveFocus( $("h1") );
		}
	});

That tabindex="-1" on the heading allows it to be focused via JavaScript without actually being "focusable" in the regular document flow.

The author also mentions that you can move the focus onto the first element of the task list, but it's mostly personal preference on what you exactly want to do with the focus. Focus management is very tricky sometimes.

The next thing is that we actually also need to update our ARIA live region when a task has been deleted, to keep screen reader users informed of what's going on there. So we'll just amend our previous click function to do that.

	$("#list").on("click",function(){
		if($(event.target).hasClass("delete_task")){
			const $li = $(event.target).parent();
			const taskName = $itemContainer.text();

			$itemContainer.remove();
			moveFocus( $("h1") );
			screenReaderFeedback(taskName,"removed");
		}
	});

Actions and feedback we take for granted with being sighted need a little more feedback for blind users.


Whenever you finish an accessible program, test it on a screen reader just to make sure.


### Lesson 24: Join our Accessibility Community

https://www.youtube.com/@WebAccessibility/videos

https://facebook.com/groups/webaccessibilityeducation

https://medium.com/@web-accessibility-education

Mentions a Discord community, but there's no invite link? @Dagny on Discord.








## Other Notes

Use an \<a\> tag when you want to navigate to a new page or an external resource i.e. links.

Use a \<button\> tag to perform an action like to open a modal, delete an item, close a modal, etc.



aria-pressed - The aria-pressed attribute indicates the current "pressed" state of a toggle button

aria-expanded - The aria-expanded attribute is set on an element to indicate if a control is expanded or collapsed, and whether or not the controlled elements are displayed or hidden.
