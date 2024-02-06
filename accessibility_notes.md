# Creating Accessible Websites by Stefany Newman - Course Notes
https://www.udemy.com/course/creating-accessible-websites/


## Lesson 1: Semantic HTML
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

## Lesson 2: Color Accessible Webpages
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


## Lesson 3: ARIA Attributes

ARIA (Accessible Reach Internet Applications) attributes make HTML elements more accessibility and make it easier for screen readers and other assistive tech to understand. Most of them start with "aria-"

- aria-label - Labels current element with the custom text
- aria-expanded - Shows whether or not the current element is expanded; like on a hamburger menu. "false" or "true". For example, on the hamburger, you need to have it read "false" when not open, and "true" when you click on it

- aria-labelledby - Indicates that the image is labelled by a specific caption or text; use the ID of your caption element within the attribute value


Example of aria-label
	- On icons inside of links - If you just add the icon inside the anchor tag, it isn't very accessible. Visually disabled users wouldn't know that the icon is to Instagram, for example.

role attribute - change the semantics of the element. always add "tabindex=0" after the role attribute. This will make sure the element gets added into the tab order

## Lesson 4: Accessible Images

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

## Lesson 5: Outline Property 

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

## Lesson 6: Tabindex

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

## Lesson 7: Bypass Blocks

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


## Lesson 8: Accessible Video & Audio for the Web

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

## Lesson 9: Inaccessible Website Overview
- First problem: No outline on focused elements
- Second problem: Google Maps Iframe has no title, so screen readers will skip it
- ~Buttons here, but these are links that are styled as buttons. Don't do this~

> **Brian's Note:** Respectfully, I disagree. As long as links point to other pages, 
> and buttons do something on the page, I think we can definitely style a link 
> as a button. It's way better than setting up a button element that's hacked 
> to send users to another page

Emojis are announced by newest screen readers, but older ones will only announce the unicode code for the emoji
Carousel totally inacessible
Contact form has no labels, only placeholders, and not a descriptive submit button
Social Media Icons are too claose together and don't have an aria label

Link opening in new tabs bad for accessibility

## Lesson 10: Accessible Navigation
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

## Lesson 11: Accessible Hamburger Menu
Most websites don't have a good hamburger menu.

Use a button element for a hamburger element.

All hamburger menus should 
- Be navigable by the Tab key
- Should announce through the screen reader when the menu is expanded and collapsed

	<button id="hamburger" aria-expanded="false" aria-label="Menu">
		<span>Menu</span>
		<svg></svg>
	</button>

The problem with uppercase text is that it is typically really bad for people with dyslexia, because all of the letters are the same size and the same shape (basically a rectangle) and so it makes it harder for dyslexic people to read that text.




## Other Notes

Use an <a> tag when you want to navigate to a new page or an external resource i.e. links.

Use a <button> tag to perform an action like to open a modal, delete an item, close a modal, etc.
