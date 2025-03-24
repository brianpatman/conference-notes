# Smashing Meets Accessibility: Common Data Visualization Issues by Sarah L. Fossheim
https://www.youtube.com/watch?v=z6jdEqz7qf8

## Visual Issues - Color Issues
### 1) Visual elements lacking color contrast against the background
Regular text should have 4.5:1 contrast with it's background
Graphical objects should have at least 3:1 contrast with adjacent colors

Small issue with a large accessibility impact. It becomes difficult or impossible to read for people with low vision or impaired contrast perception. But it also affects those who don't have high resolution screens or if you print to paper. People can print for several reasons, such as if they get migraines, to make annotations, and if they are easily distracted by screens

Lighthouse, axe, or other testing tools will also be able to test contrast directly in the browser. Colors can also be tested via WebAIM contrast checker

### 2) Relying on color alone to explain data
If you have one of the many types of colorblindness, it can be hard to parse results of data visualizations that use color exclusively to present data

Tools like Viz Palette can help plan for color blind friendly color palettes 
Browser tools can also be used to simulate color blindness on live websites

Explain and label categories, trends, and special values directly through text labels.
Or you can use unique symbols or patterns to categorize the data


## Visual Issues - Zooming Behavior
### 3) Not possible to zoom or enlarge the text without breaking the layout

When zooming into CNN's US Election Results, you have a sticky header and you eventually run into a sticky table header, both of which make the actual space you can see while zooming in at 200% and 400% very small and annoying to use.

Test the layout at 200% and 400% zoom and with enlarged font sizes and use width/height media queries to adapt the layout to different viewports just like you would do with mobile (with REMs)


## Assistive Tech Issues - Keyboard Interaction
### 4) Not possible to perform interactions using keyboard only
Visualizations often also have tooltips that expose more detailed info on hover

Just test the layout using a keyboard while developing to catch the obvious issues


### 5) Keyboard interaction that's not intuitive or understandable
It's not enough that interaction can bne peformed by keyboard. It has to make sense UI-wise as well.

For example, on CNN Election results, the tab key between states is almost totally random, as opposed by being in left to right order

Designers can document the expected behavior in their design files


## Assistive Tech Issues - Screen Reader Alternatives
### 6) Not doing anything for the accessibility of SVG elements
Screen readers can use the following to infer things about the page
- Semantic elements let the user know what action they can peform on that element
- Headers can be a decent way for a screen reader user to scan the page for relevant info
- Landmarks (like <nav> <footer> <aside>) can be used to navigate between specific sections of the webpage

But SVGs don't contain any semantic meaning.

By default, when we don't do anything with our SVGs, the only thing the screen reader will announce is the text contained within the SVG and not anything about the graphics.

Blind and low-vision people using screen readers won't get access to any of the information within the SVG. And in some cases it will just result in a collection of nonsense (like the screen reader will just announce "image image image image image image image...") This might not be an issue with an experienced screen reader user who has shortcuts to move past the 500+ instances of "image", but can be a real big issue for those less advanced screen reader users who don't know all the shortcuts.

Test the Data Visualizations using a screen reader to detect missing information and obvious mistakes. But, you should use accessibility specialists to verify the actual issues, possible fixes, and user tests to place them in context.

One way to solve this issue is by creating a table alternative for screen reader users. This will make all data available for those users with a recognizable browsing pattern.

You can also turn chart elements into elements that have semantic meaning using roles and ARIA.


### 7) Not communicating the *right information*
For example, on a US election results map, many of these map images just have an alt text of "Map of the US" and call it a day, whereas sighted users can see the breakdown of electoral votes by state.

Or on an ABC News election results map, it just indicates to the screen reader what states are North/South/East/West of the current states, but not the actual electoral votes.

Don't put all the work on developers, have designers document the expected experience based on user research and workflows

Accessibility knowledge needed for following best practices and guidelines.

### 8) Incorrect usage of ARIA or wrong HTML elements for function at hand
Example: <button> elements nested in <a> tags
Example: <table> elements purely for layout

If the screen reader user encounters non-standard elements, then it creates confusion about what to expect when interacting with that element

This can also make adapting the layout with custom stylesheets so much harder.

Lighthouse, AXE, or other testing tools can uncover SOME of the issues. But, you still need manual testing, as Lighthouse doesn't know your intentions with what you are building.

Often most of these Issues are all caused by the same thing

## Culture Issues
### 9) Work Culture that doesn't value or prioritize accessibility work properly

Bootcamps often don't include accessibility in the curriculum.
Workplaces don't always prioritize accessibility issues.

Some people don't get exposed to it, or never learn about the impact.
Some know the importance of it and want to work on it, but aren't given time, budget, or opportunity to learn or make improvements. How do you learn new skills on top of a 40+ hour work week, especially with family, kids, etc...?

> Prioritize Progress over Perfection

Sneak Accessibility Improvements into other PRs for other things
Make Accessibility Part of the Process


## Question: "Any sites that do data visualizations really well?"

"High Charts" and "Apple's" Website Charts





# Designing for Accessibility Right From the Start by Stephanie Walter
https://www.youtube.com/watch?v=2juq00vrvl0

Be careful about the usage of colors. Make sure that color is not the only way to visually convey information.

Ensure the text on elements have enough contrast

For text less than 24px or 19px bold, text needs to be 4.5:1. For text higher, text needs to be 3:1

User Interface Components (like input elements) need to have their visual indicators (like borders) to have contrast of 3:1

Focus Indicators need to have a contrast of 3:1 against adjacent colors

Graphical Objects required to understand the content need to have a contrast of 3:1 against adjacent colors

Designers should document states for developers, especially the focused/hover states

Links, if you don't underline them, also have a triangular rule where you have to get their contrast against the background, against the other text, etc... correct. Author's suggestion is just to underline the links and call it a day.


## Build & Document an Accessible Color Palette

In a color palette, you have your main colors. When you are going to create shades of your main colors (darker, lighter, etc...), you should make sure those color variations work together as text on background.

When building shades lighter/darker, make sure you can always use, within one color, that you can use your darkest color with your lightest and with white. She aims for 4.5 color contrast

A contrast grid matrix can also help to define & document color combinations

Adapt color combination for dark mode based on our palette


## Text Resizing and Typography
More of a dev concern.

Just make sure the text content can be enlarged to 200% without hiding elements and missing functionality of the site

However, sometimes you don't need to make the actual images bigger than normal at 200%. Focus on things like star ratings, text, category labels, etc...

## Interactions and Interactivity

### Buttons and Links
Make sure the user understands what will happen if they click/tap/interact with it

"Search Now" over "Find my Panama"
"Send me text alerts" over Keep me in in the loop"

Avoid the "click here" no context link label

Instead of:

> "For more information about Husky Athletics, click here"

Use the following:

> "For more information, see Husky Athletics"


### Target Size

Check that the size of a clickable/tappable area is at least 24x24 CSS pixels

This doesn't apply to links in blocks of text.

If it's not 24px, you can use spacing to reach this size

### Forms and Input

All the fields in a form need to have a clear, easy to understand, visible label (*or programmatic invisible label*)
	- Sometimes you might have an invisible label on a searchbar, but still put that label to where it can be read by screen readers

The label is NOT a placeholder, as placeholders aren't read by most screen readers.


> A form is like a board game: you must explain the rules at the beginning, otherwise nobody can win.

> Display instructions at the beginning of your form, not at the end.

**Help Users Fill the Form**

- Help users prevent errors (expected format, instructions, mandatory fields, etc...)
- Help to recover from errors (errors are marked, clear messages, etc...)
- Avoid redundant entries; dont make users input the same information twice (except for security reasons)


As designers, document error styles + detail cases for error recovery

Inactive States for checkboxes, radio buttons, etc...

## Keyboard Support 

Skip Links to enable keyboard users to skip repeating content, such as a nav

Focus order should follow the logic and flow of the page.

## Complex Component Navigation & alternatives for complex movements

Users need to be able to navigate and interact with all components, using different pointing and interaction devices (mouse, keyboard, etc...)

Interaction Flows - How should this component work on mouse/keyboard?

Alternatives for multipoint or path-based gestures
- Complex Gesture -> Swipe Right to Archive
- Alternative -> Long Press to show the toolbar, and then press the "archive" icon at the top
- Alternative -> open the mail details and hit the "archive" icon at the top.

You don't need to have the alternative be the same number of steps as the primary complex gesture, but there should be an alternative.

### Drag & Drop
Instead of just using the drag and drop functionality, use little up and down arrow icons as well to aid those users who can't do drag and drop or find it difficult

## Navigation and Wayfinding

### Headings
The label of the heading is descriptive, clear, and accurately describes the content that follows.

Don't use paragraphs with bigger font, use header tags (h1,h2,h3,h4,etc...) instead

Don't use illogical order; don't skip heading levels, etc...

Plan your page content and structure ahead of time.
- And work with UX writers and SEO people on these.

Document headings using annotations.


## Content Access

### Images, Icon, and Screen Reader Content
What should the screen reader announce for certain images? (For images that are not purely decorative)

Use "Announced text" for functional icons that replace text (with an aria-label, for example)

On star ratings, announce "Rating X out of 5 stars" as opposed to "Filled Star, Filled Star, Filled Star, Filled Star, Empty Star"

### Video/Audio and Moving Content

Use Video Captions for videos and transcripts for podcasts

Captions for Live Audio 

For pre-recorded media, you also need descriptive text or an audio description of other things that are happening in the video minus just the speech.


### Support Both Portrait and Landscape mode

### Animations that start automatically and last more than 5 seconds must have a way to pause them


This is just a baseline, the minimum designers can do to make products accessible. It won't be enough, but it should help avoid a few issues.

### What is 1 thing that you can do tomorrow to start improving accessibility?
Start with that and build upon this base


## Questions
### Q: What can teams do to rally around an accessibility from the start mentality?
We need someone to start somewhere (either bottom to top; devs and designers bring it up the chain) and grow from there.


### Q: How can someone become more proficient with accessibility without becoming overwhelmed with information?

The accessibility community has amazing people who are more than willing to help, so you have a lot of people willing to help.

But, start somewhere and build from there.

> "It doesn't have to be perfect; it just has to be better than yesterday"

If you can have people with disabilities navigate the web or just look into videos of how different disabled people navigate the web. You'll be surprised how shoddy the web is in accessibility.

### Q: What do you think about using placeholders along with labels?

The problem is that placeholders don't have enough contrast, but if you make them darker, the form fields look pre-filled. So there's just not a great use for placeholders on the web

### Q: Is ADA different from WCAG?

ADA is codified law in the US, whereas WCAG is the guidelines you are supposed to follow, but isn't legally binding.

### Q: If you (a developer) receive a design that has an accessibility concern, what to do?

The best thing is to talk to the designer and get in touch about what to do to fix accessibility issues. Open a channel of communication; let's find another solution.





# Panel Discussions
https://www.youtube.com/watch?v=Ej0mvbTXCaI

## Tools for Day-to-Day Work
Color Contrast Checker Tools

Focus Order plugin and Aria Role plugins in Figma

## Are there other types of ways we can accentuate color?
Sarah talks about how, when she is dealing with a large chart that's too difficult to make accessible, she wonders if she then needs to split up the data into different charts to simplify the design and simplify the accessibility concerns.

You can use textures, shapes, etc... to also help with these concerns.

The trick with clients is to convince them that there are your brand colors, but then there are also your *system* colors for use on your website.

Stephanie also talks about how, if you can have text instead of relying on color, that's another way you can do things.

## Ways to convince upper management to care about accessibility
You need to convince what makes them click.

People have successfully tied accessibility initiatives into security, money, and the environment.

There are 1.3 billion people living with disabilities and that will only increase with us living longer and that's a HUGE market.

AirBNB invested a lot of time and money in accessibility and got a major return.
