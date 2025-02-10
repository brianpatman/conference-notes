# How to fix a site you didn't build for optimal performance
https://wpengine.com/resources/decode-2024-fix-a-site-you-didnt-build/

## First thing to do with every new client: A Website Audit
- Google Lighthouse to see what it says
- Look for General SEO Issues
- Look for Broken Links, Broken JavaScript Functionality, Accessibility Issues, etc...
- Take Notes, not only for the client, but also for yourself

Get a feel for if the speed issues are that many versions of low hanging fruit (large images, huge videos, cheap hosting, etc...), because most of that can be dealt with fairly easily. 

But, if you see that all of those things are actually fine, that's where it's likely some deep-rooted issue in the application, server, or somewhere else.

## Other tools other than Lighthouse
- WebPage Test (https://webpagetest.org/)
- Google Page Speed (https://pagespeed.web.dev/)

## How do you decide how to allocate resources while working on optimizing a website?
- Go after low hanging fruit first; large images, large videos, etc...
- First thing recommended is better hosting if someone is running on cheap or shared hosting. Hosting is very much "You get what you pay for".

Often, one issue causing speed problems on the site is how many plugins there are. Someone might have wanted a contact form and installed 5 different form plugins and tried them out before settling, but the old plugins are still just hanging out even though they aren't being used.

Same idea when someone has a Page Builder and then 5-10 extensions to that page builder, all of which do different things. Sometimes you can reduce this to just one or two extensions that handle everything the client wants to do.

If you can reduce dependencies, it will almost always make things run faster.

## How do you manage client expectations and communicate how you want to improve the site?

Great communication on what's possible and what's not.

Clients sometimes have unrealistic expectations, but they don't know what they don't know. So you often have to take a gentle educational approach.

For example, perhaps they have a super slow website, but they are happy with it and want to develop some new functionality on top of it. Often, as a developer, you would probably encourage them to pay to fix some of the wonky pieces of the core site code before further development, to really make that ROI worth it.

Also, you will learn that you will maintain a sliding scale of explanations for clients. Some clients just want to know that the issue is fixed, while others want more detailed explanations on what exactly happened to cause the issue.

One panelist found that, on the clients that don't care about the explanation, they DO care when the bill comes their way. So you have to reassure them that this issue was fixed permanently and your fix wasn't just a band-aid.


There's also a delineation between "Something not working" vs "Something not working how someone thinks it should work"

Balancing what the client wants vs what they can afford is very important. How to find the best way to communicate that to the client?
- Ask them about their goals. What are you trying to accomplish?
- What does the client want vs what do they need? 


Use Humor or Funny Analogies
- Think of their website like a piece of property - If you buy a big mansion in Beverly Hills, you need a lot more effort to manage that place rather than just a small single-family home.
- "you've got a champagne taste, but a box wine budget"
- House is a common analogy - Drywall, electrical, flooring, etc...


## It's not just what your client wants; it's what their clients or customers want. How do you work this into the conversation?

One example: During discussions, client weren't going to be the one who were going to be managing the website; a secretary was. So, one of the things he did was create a small "dashboard" on the main WP-Admin page that had links to the specific jobs they were going to be spending 90% of their time in the website doing.

So, for example, put in a block that has buttons "New Job", "New Invoice", "New RFP", that go to the right place on the site rather than them have to navigate there.


One Panelist said that he has run Usability Experiences before to see what the end users want from the site. However, he said that he is discovering that more often, the Admin Backend experience is also becoming really important. 

If you have tons of plugins doing different things, you're gonna by default have a really wild admin experience.

A lot of times, with these websites, you'll have multiple Admin users that are logging into the WP-Admin to accomplish their specific tasks. You can do a few things to help here:
 - Create custom admin roles that make it to where these different admin roles within the organization are restricted to the operations that they actually need to do.
 - Improving backend admin column experience for post types and column names within WP-Admin
 - It's not a speed metric, but it is a speed issue for the person working in the admin panels

 The Block Editor has moved some of the understanding that the speed optimization isn't just on the frontend, but on the backend too.


 One panelist used to give admin access to the client as soon as the website was done or near done. But, now, he gives them admin access right as they start building it, so they can go and look around and see if the admin interface is how they want it to be. Also, they can do some QA testing for the devs.


 The more possibilities you add in the admin panels, the more things can go wrong. So education is really important in this case. Also having helpful documentation on how to do things.

 Find the balance between limiting things and having flexibility.


## If you had to give one piece of advice to fellow devs working on a site they did not build, what would it be? Performance

David - "You can kind of let the client take the wheel a little bit and give you their list of things that they are not finding the site does great"

Ellis - "Don't be just a yes man. Clients are always going to ask for all kinds of things. But as the person guiding them, you always need to draw a line between what they are askign for and what you are going to build, and deliver business value for them. If you can't figure that equation out, you shouldn't say yes and start developing. Pause, regroup ,and figure that out. BEcause that's what your client will feel in the end."

Sergey - "Educate the clients about hosting. You get what you pay for with hosting."

Jessica - "When a client comes to you with a really bad website, dont' blame them or make them feel bad about their previous decisions. Take it as a chance to educate them and help them with their needs and what they have at this point. You will do this, you will build a lot of trust"


As technologists, it is part of our job to sling code, but it is also part of our job to find what our client actually needs. And think a little higher level about that. Yes, it's about performance, but it's more about how that performance is beneficial. 
