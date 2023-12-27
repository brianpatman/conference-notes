# 10-18-23 WordPress Security: Proven Ways to Protect your Site

## Welcome & Introductions

- Krystal O'Connor - Sr. Product Manager, WPEngine
- James Browne - Digital Directory at Flipside Group, UK
- Scott Jones - CEO, Illustrate Digital
- Alain Schlesser - Directory of Technology & Innovation, XWP

## Security 101: What you need to be aware of
	
### More than half of cyber attacks target small businesses.

DDoS attacks are up 200%+ in 2022

Out of date WP, themes, and plugins - 92% of all security breaches on websites exploit outdated software

- Security is evolving and is in a constant state of update
- Stay current with changes
- Backup often
- User Management
- Have a security conscious host
- Impact of insufficient security

### Change is part of the process

CIA Triad
- Confidentiality
- Integrity
- Availability

Defense in depth

Principle of Least Privilege

### Updates are Important

Most WordPress runs on a LAMP stack, which is also important to update

User Management
- Strong Passwords
- Two Factor Authentication
- Change Login Path
- Monitor User Activity

User Privileges
- WordPress Roles
- User capabilities
- Granular privleges

Change default /wp-login.php or /wp-admin/ URL

### Pick a good partner

The right web hosts understands You

Functionalities
- WordPress and software updates
- Backups
- SSLs
- WAFs
- 3rd party audited

### Imact of Security Breach
There's more at risk than security

- Brand Impact
- Trust
- Financial Cost
- Legal Consequences
- Indentity Theft
- Loss of competitve data
- Loss of data
- Business disruption


### Site maintenance is site security
- 92% of vulnerabilities come from out of date plugins
- 3% from core wordpress
- Themes 5%

Easy automated WP, PHP, and MySQL updates

WPEngine runs regular vulnerability scans on your site for plugins and themes

WPengine also runs automated Php and MySQL updates

### Leave WP Security to the experts

WPengine blocks 26B attacks a year

## Panel Q&A

Having plugins is like having additional windows in your house; the more you have, the more attack surface you have.

Accountability between teams so that you have all things covered, such as plugin updates, etc...

Security-First

In the old days, websites weren't really built with security in mind. But lots of those were just static HTML. Today, there's lots of more complex pieces that all communicate together, and you need to secure all of the communication between these components. Websites are more like full-stack applications today rather than just websites.

Network Layer attacks
- "Ping of Death" attacks
- "Syn Flood" attacks
- DDos and DoS attacks

James - One Client is constantly under attack and we've put in systems in place where we don't really see it anymore

But it used to be that CPU is 100%, alarms start going off, and then you have to dig into the log files to see that "Oh we've had an absolutely massive amount of traffic to the site from a malicious actor"

DDoS - "A DDoS looks like your server is dying" -> James Browne


### DDoS attack - How to get back online and how to deal with attacks

Getting back online
- First Mitigate it; you will have time to analyze it later, but the most important thing is to successfully mitigate it
- While attack is happening, this is not only causing strain and extra cost to your systems, but also you're not available to your visitors anymore.
- If you're runing an e-commerce site, no one will be able to buy things
- Deflecting
	- If responsible for an application, you should have a strong partner like WPEngine, as well as sytems in place like Cloudflare that has a protective layer protecting against that and systems in place to help block traffic based on some criteria

Ideally, have the systems in place already before that starts

IF you just have a single server that you've just put on the internet, it's really difficult to defend against DDoS attacks. You need services in place beforehand.

If you didn't plan for DDoS attack, you won't be able to do much for your visitors during the attack.

Being offline for several hours can have an immediate negative impact on your business. Even if nothing happens other than being offline, you will have a hit on your reputation and your business, so you need to prepare for that.

WPEngine has the specialization within WordPress that means that any known vulnerabilities and things are already taken care of. Having a good hosting provider is essential.

The longer a website is offline, the worse it is for credibility and reputation. 

> Oliver Bishop - "Have a DR plan, regardless of your preventative measures."

### Why are plugins such a vector and what can we do to mitigate that?
Periodically audit the need for plugins

The best thing about WordPress is it's extensibility. There's a number of different extensions for forms, ecommerce, etc...

Is the functionality of the plugin mission critical? Is it possible to do what you're doing with hard code without having to put too much more effort into having another plugin? Is the functionality of the plugin covered by other plugins on your site?

On plugins
- Who was the developer? Do they have a reputation? Is it the brand themselves, which is a pretty good sign?
- How many reviews does it actually have on the WordPress plugin repository
- When was it last updated and what version number is it relevant for? If it has 5 stars, but was updated 2 years ago, then steer clear of it.

If you operate a plugin, and you haven't updated it in a few years, you should make one that confirms that you've tested on the most recent version of WordPress and all

James - People think since they can add plugins so easily, that they're all similar.

There are plugins that do very simple things you could almost do yourself and not open up another "window" in your site

Alain - "How many plugins is too much or too few?"
It's not the exact number of plugins, but each plugin is a bet that each plugin is perfectly secure.

A lot of plugins aren't made with the best security focus in mind

Alain - At XWP, we try to have as few plugins as possible. Not only for security reasons, but also for scalability reasons. At a certain level of scale, you find that most plugins are just not built for that. We tend to custom code a lot of that functionality anyway.

Alain - It's not the number that is the issue, it's just the number of untrusted dependencies that you are adding to your site.

### There are a number of things they can do, from website defacement to a data breach. What are the first things we should be thinking of with a data breach and how do we further protect the data of our customers and our business reputation?

Scott - One of the things that can do in advance to mitigate 
- Get a third party in to do an audit. It could be a full ISO audit, or could even be a friend who pokes around a bit.
- It's really good to be exposed in a safe environment, before you are exposed to the world.

Alain - A bit earlier than the breach
- The best backup in the world won't matter if the recovery process doesn't work.
- It's only safe if it helps in the case of a problem.
- Same in the case of security
- You should try to see if someone can get past your defenses
- These things need to be directly tested by a 3rd-party to make sure everything is secure and that things work as intended.

Data Breach - All the security best practices try to lower the probabilities of breaches, but it never reaches 0% entirely.


> Oliver Bishop - "If you're generating revenue from your site, you should subcribe to a yearly pen-test. Most insurance companies offer it as a free service if you have digital insurance"


In terms of marketing, data is an asset!

In terms of security, data is a liability. Whatever breach happens, the consequences will be multiplied by how much data there is available.

If you start by anonymizing data or not collecting data that you don't need, you can mimimize the liability that you are exposing yourself to in the case of a data breach.

"Do you REALLY need this data on your site?" - If you have more data, you're more of an attractive target for attackers.

> Oliver Bishop - "As someone who worked in the access to information and privacy industry, there is no such thing as innocent data"


## Audience Q&A

How to implement a serious CSP without breaking WordPress?
- There's a lot of areas in stock wordpress that could be written in a better way to combine them with good security practices.
- On the WordPress backend, it's already behind an authentication wall, so you should begin by separating CSP policies between frontend and backend. That way, you can figure out what to do for those two different parts of the website differently.
- Generally, consider frontend and backend to be separate for a CSP and for security concerns.


Does disabling a plugin do the same as removing it or deleting it?
- It helps to disable it, but it doesn't do the job entirely. If the plugin is built correctly, it's fine. But did the plugin creator build it correctly to turn everything off? Who can say?
- In terms of security, disabling and deleting are two different things. Disabling means that the files are still available, but not being loaded by WordPress, and depending on how you mess with those, it can still be a security risk.
- If the Web server is misconfigured to allow direct code execution, then that would also be a problem meaning that disabling the plugin won't remove security issues.


Any difference between storing backups on the server your website is running on or offsite?
- If it's on your server, and your server is compromised, that backup is ALSO at risk.


> Oliver Bishop -> It's almost as important to delete the DB tables that a plugin creates, if there is anything that runs against those tables

> Me -> Hmm, do you usually just delete them manually, Oliver? Like account for them and delete them in PHPMyAdmin? Or do you have some sort of automated solution?

> Oliver Bishop -> Luckily, in my WP setup, it hasn't been needed, but I've learnt this from other sites I used to host. Backup, test in a UAT version, validate, then execute the same on prod

> JD Arbuckkle -> Also interested in that Oliver. With how fragmented WooCommerce is in the DB (being kinda fixed in HPOS, a good step), I bet Woo plugins inject themselves everywhere.



As a small business admin in house, do you have a good process to do an inventory of plugins or of the software on your site?
- First do plugins, and then look into Tools > Site Health to see what else is going on there.
- Outsource most of your security problems to security experts in the field. 
- Consider the impact of adding more data and stuff to your site. You're trading between one new feature and one new security liability.
