# Accessibility Notes One-Pager
This is my attempt to make my previous accessibility-notes.md file a little smaller and something I can potentially turn into a physical cheatsheet for Web Accessibility

## Step 1: Use Semantic HTML
Use Semantic HTML Elements whenever possible

Use an \<a\> tag for elements that navigation to another page
Use a \<button\> tag for elements that should preform an action on the same page (open a modal, delete an item, etc...)

If you are forced to use an unsemantic element, you must make the element behave as the desired semantic element (like adding role="button" and tabindex="0" attributes to an \<a\> tag that should be a \<button\>)

## Step 2: Color Accessibility
Design in grayscale; if it's good in black/white, it's good in color.

Do not rely on color to transfer meaning. Color swatches for shirts on an e-commerce store should have names attached, form errors should look different from normal text (even if their text is colored red), etc...

Contrast - Need sufficient contrast between text and background for older users and for colorblind users. Use https://webaim.org/resources/contrastchecker/

In Chrome DevTools, you can use Ctrl+Shift+P, type rendering, and click the "Show Rendering" to emulate certain different visual deficiencies, including colorblindness

## Step 3: ARIA Attributes

ARIA attributes make HTML elements more accessible and make it easier for screen readers and other assistive tech to understand what you mean with certain elements. Most start with "aria-"

| Attribute        | Use |
|------------------|-----|
| aria-describedby | Identifies an element that describe the element on which this attribute is set. Screen readers will read the text of the element first and then read the text of the attribute it's aria-describedby points to |
| aria-expanded    | Set to true/false. Used on an element to indicate if a control is expanded or collapsed, and whether or not the controlled elements are displayed or hidden |
| aria-hidden      | Set to true/false. Indicates whether an element should be hidden from screen readers |
| aria-label       | This gives an alternate accessible name to that defined in the text of the interactive element. The default text of the interactive element is not read when there is an aria label |
| aria-labelledby  | Similar to aria-describedby, but aria-labelledby will overwrite any semantically derived label. Similar to aria-label, the default text of the interactive element is not read. |
| aria-live        | Indicates a "live region", which will notify the screen reader whenever the text inside of it is changed. Useful for JavaScript applications where you need to indicate that certain actions have happened successfully. |
| aria-pressed     | Set to true/false. Indicates the current "pressed" state of a toggle button. |
| aria-required    | Set to true/false. On Form Fields with custom validation, this will mark a otherwise not required field as required by screen readers. |
| role             | An ARIA attribute that indicates the "role" of an element is different from it's semantic role (You can set an \<a\> tag to have a role of "button", for instance) |

## Step 4: Accessible Images
Background images don't need any accessible fixes.

Regular Images
- If they are decorative, you should set them to have a blank alt attribute
- Don't use "Image of " at the start of your alt tags
- For images inside of links, write the alt tags as if you are labelling where the link leads
- On E-Commerce products, be even MORE descriptive because someone will make a purchase decision based on the details you provide
- If there's a caption nearby, leave the alt tag blank; you could also leave alt tag empty and use "aria-labelledby" with the ID of the caption


## Step 5: Outline
Everytime you focus on an element with a keyboard, an outline should appear around it. Use the css "outline" property, as it doesn't move the content around it like the "border" property will.

	*:focus{
		outline:2px solid lime;
	}

Choose a complementary color to your main design color for your outline.

Also, all :hover handlers should also include :focus.

## Step 6: Tabindex
Only use tabindex 0 and -1. 0 means it's interactive (can be focused on), and -1 means it's not (but can be focused on with JavaScript).

Use tabindex=-1 on modal windows when they aren't in view


## Step 7: Bypass Blocks
Sometimes, if keyboard users need to navigate through a lot of repetitive content to get to the main content of your page, you might want to add a Bypass Block that allows keyboard users to skip straight to the main content.

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


## Step 8: Navigation
Use a (nav > ul > li > a) structure.

If you have multiple navigation elements on the site, add aria-labels to each \<nav\> element indicating what navigation this is. Otherwise, no need to label it.

Consider adding some visual cue within the nav as to what page the user is actually on, as well as "aria-current='page'"

For Hamburgers
- Try to make sure the width/height is at least 44px square to meet a WCAG AAA Success Criterion
- Hamburgers should expand when the user is focused on them and hits the Space or Enter key
- Set "aria-expanded" on hamburgers and set it to true/false through JS as the menu opens and closes


## Step 9: Accessible IFrame
Add a "title" attribute to ALL Iframes to indicate to screen readers what the iframe is meant to do

Also, on a map iframe, add the address separate from the Iframe so screen reader users can read that instead. You can also link out to a "Driving Directions" page, or explain in common language where the location within the iframe is ("In the Turtle Creek Mall, next to the Target")


## Step 10: Accessible Forms
Ideally, for every form input element (\<input\>,\<select\>,\<textarea\>,etc...), there should be a cooresponding \<label\> element.

Make sure that users can "Tab" through every field of the form and that each field has an "outline" show when focused on.

Author blasts placeholders because
- Placeholders don't stand out enough for people with visual disabilities, because the contrast is so low
- Not all screen readers announce placeholders as the name of the fields
- The placeholder might make users think the form field is already populated

If you can't use the "required" attribute due to some custom JS validation, set required fields to have the attribute "aria-required='true'"

Set the "Submit" button to describe what submitting the form is actually meant to do. So, in the case of a contact form, change "Submit" to something like "Send us a Message".

Author also suggests additional steps:
- Add "aria-hidden='true'" attribute to every * mark marking a field as required, since blind users will know they are required via the "aria-required" attribute
- Don't add extraneous links in between input elements, as they will annoy blind users navigating by screen readers
- Author also suggests adding something at the top of the form reading "All fields marked with an asterisk (\*) are required" to help users that are sighted but need additional context


## Step 11: Accessible Icons
SVGs are always preferable for icons, but font icons can also be used.

Be sure to give icons sufficient contrast against the background for older people and those with visual impairments who aren't totally blind.

Also, unless the icons are very well known social media, you should always put text next to the icons to indicate what they mean.

For decorative icons, set the attribute "aria-hidden='true'"

For social media links, or for links that can't have text next to them, add an aria-label to the link and set the inner icon to be "aria-hidden='true'"

## Step 12: Accessible Links
Author says you should never open up links in a new window if you can help it. If you have to, go ahead and set an ARIA label with the descriptive name of the link that ends with " - opens in a new tab"

You could also add an external link icon to any links that go outside the main domain.

Use text-decoration on links, but not on normal text, as you'll confuse users that something is a link when it actually isn't. If you want to add emphasis, use bold instead of underline.

Don't name links generically. Turn "To make an appointment, click \<a href=''\>here.\</a\>" to "\<a href=''\>Make an Appointment Today!\</a\>"

When you have an image inside of a link, make the "alt" text of the image what you would write if the image wasn't there.

Also, make sure that there is some visual indication on a linked image (like a color overlay) to indicate that this element is clickable.
	

## Step 13: Testing a Site
- A: Test if all Interactive Elements are Focusable
- B: Zoom into the website to 200% and 400% and make sure things look okay. These items are from the WCAG criteria. Horizontal scrollbar bad while being zoomed in, unless there's some large table or big flowchart image. Also, make sure that text enlarges and scales as you zoom in, or this isn't accessible.
- C: [Accessibility Checklist](https://www.a11yproject.com/checklist/). Use this to make sure you don't forget anything. Author only goes down to AA criteria most of the time.
- D: High-Contrast Mode Testing:
	- Chrome: Searchbar > "Ease of Access High Contrast Settings" and turn on "high contrast"
	- Make sure your logo is designed to work within High contrast
- E: Make sure site scrolls via the arrow keys


## JavaScript Apps
She's making an accessible JavaScript ToDo List in this example.

Inclusive Components has many good and accessible web components: [Inclusive Components ToDo List](https://inclusive-components.design/a-todo-list/)

Even if you aren't going to have a form action, put sets of form elements in a \<form\> element and then just disable the default "submit" action via JavaScript.

You might want to add hints to an input. You can't add another \<label\> element, but you can add a \<p\>, \<div\>, or \<span\> element nearby with an example of what should go in this input element. Be sure to set an "aria-describedby" on the \<input\> that points to the ID of that description element.

Next thing is to add what's known as a "live region". This is just an element that you can basically update the text of with JavaScript that screen readers will read off when it changes. Use this:

	<div role="status" aria-live="polite" id="feedback" class="feedback"></div>

She actually doesn't hide this status field, just because screen readers have very mixed support for status fields and may get confused and not read it if the field is set to display:none. You can then update this field with text like "Added Item Feed the Chicken" or "Deleted Item File Taxes" to indicate to blind users using screen readers what exactly happened.

WCAG Guidelines - Elements should be at least 44px wide by 44px high.

On the Delete Task button, however, there's a problem. When you delete the task, the focus ring disappears, which makes screen readers "lose their place".

There are multiple ways to skin this cat, but she went ahead and re-focused on the heading above the form (which has tabindex=-1, so it can be programmatically focused).

## Modal Attributes

All modals should have the following attributes
- role="dialog"
- aria-modal="true"
- aria-labelledby="\[ID_OF_MAIN_POPUP_HEADING\]" - Set this to the ID of the main heading within the modal; if there is no heading, use aria-label instead
- tabindex="-1"
