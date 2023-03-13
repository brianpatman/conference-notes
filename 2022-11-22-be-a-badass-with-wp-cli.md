# Developers, Be a Bada$$ with WP-CLI

https://wpengine.com/resources/on-demand-webinar-developers-bada-wp-cli/

WP CLI - A text-based interface and a way to supercharge productivity on your WordPress sites

## Top Use Cases
+ Setup new sites quickly
+ Maintain multiple sites easily
+ Troubleshoot WordPress faster
+ Database Administration
+ Working with WP-CLI packages

## Before You Start
+ Installing WP-CLI locally allows you to remotely execute commands from your machine. It basically reaches out and connects to the sites you specify via the YAML config file. WordPress.org recommends you install this by downloading the Phar build and adding it to your machine's path
+ You can then create a YAML config file that allows you to define aliases such as production, dev, and all

## Example YAML Config File
	@jrd2:
		ssh: jrdelarosa2@jrdelarosa2.ssh.wpengine.net	

	@jrd3:
		ssh: jrdelarosa3@jrdelarosa3.ssh.wpengine.net	

	@jrd4:
		ssh: jrdelarosa4@jrdelarosa4.ssh.wpengine.net


	@production:
		- @jrd2

	@dev:
		- @jrd3
		- @jrd4

	@all:
		- @jrd2
		- @jrd3
		- @jrd4

## Setting up Sites Quickly
By using WP-CLI, we can quickly perform common tasks like installing plugins, importing users, and adding a theme to a group of sites

### Bulk Add Users
This command imports a list of users from a CSV file. The --skip-update flag tells the command to NOT update existing users with the info from the CSV file

	wp user import-csv users.csv --skip-update

### Install and Activate Plugins 
This command installs a certain list of plugins onto my new install. The --activate flag also activates those plugins

	wp plugin install woocommerce jetpack wordpress-seo --activate

If the plugin is already installed, then WP CLI will go ahead and tell you that it already is installed.

### Install/Activate Theme
Pretty similar to the plugin command above

	wp theme install twentythirteen --activate


### Using Config Files to Batch Commands to Several Sites
You can also use an alias defined in a config file to script out a command to several sites:

	wp @all theme install twentythirteen --activate


It's important to know that WP-CLI has lots of great built-in documentation via the "help" command. Example:

	wp help theme



## Maintaining Sites Easier
Perform common maintenance tasks around things like plugin updates, user permissions, and comment moderation

### Check to see which active plugins heve updates pending
Just spits out a list of plugins, if they are active or not, and if they have any updates pending

	wp plugin list --update=available --status=active

### Update all plugins, except for WooCommerce and WordPress SEO
Update all plugins, EXCEPT for WooCommerce and Yoast SEO, which can have bad side effects sometimes

	wp @dev plugin update --all --exclude=woocommerce,wordpress-seo

### Delete the user associated with ID 123 and assign all posts to user 567

	wp user delete 123 --reassign 567

### Delete all comments that have been flagged as spam
This actually uses the output of one WP CLI command to another. You list out all of the comments marked as spam and then pass that list to wp comment delete to delete all the spam comments

	wp comment delete `wp comment list --status=spam --format=ids`


## Troubleshooting Sites
This is more of a BASH thing, but you can also use a command like 'tail' in this way to live monitor error messages within WP-CLI

	tail -f wp-content/debug.log


### Create List of Plugins
Here's a useful little script snippet that both creates a list of active plugins, and then starts deactivating them for a minute each before reactivating them and moving on to the next plugin. Useful for debugging sites if you believe a plugin is behind your issue.

First, we create a list of plugins and store it in a text file:

	wp plugin list --status=active --skip-plugins --field=name > tmp/plugin-list.txt

Then, we loop through that list and deactivate each plugin for 60 seconds before we reactivate it and move on to the next plugin:

	while read -r plugin
	do
		echo "----------------------------"
		echo "Deactivating-$plugin"
		wp plugin deactivate $plugin --skip-plugins
		sleep 60
		echo "Reactivating-$plugin"
		wp plugin activate $plugin --skip-plugins
	done < /tmp/plugin-list.txt


## Database Administration
A few useful commands that help with database maintenance

### Export a database dump to your local machine, titled with the current date
	DATE = `date +%Y-%m-%d`; wp @prod db export - > wp_jdelarosa2_$DATE.sql

### Run WP-CLI search and replace (often useful when adding SSL to a site)
Go ahead and remove the "--dry-run" flag if you want to actually run this. This flag just outputs the changes that you are going to make before doing the operation for real.

	wp search-replace "http://jrdelarosa2.wpengine.com" "https://jrdelarosa2.wpengine.com" -- precise --all-tables --skip-columns=guid --dry-run

### Delete Revisions from a Database
	wp post delete `wp post list --post_type=revision --format=ids`


## How to work with WP-CLI Packages
Packages are a great way to extend the functionality of WP-CLI
WP-CLI Package Index: http://wp-cli.org/package-index/

### WP CLI Login
This package allows you to login to WordPress with secure passwordless magic links

	wp package install aaemnosttv/wp-cli-login-command
	wp login create <USER>

### WP Checksum
Run checksums on your themes and plugins to see if any of those files were modified

	wp package install eriktorsner/wp-checksum
	wp checksum all

### WP Sec
Allows you to check your WordPress install for CVE security issues reported at wpvulndb.com

	wp package install markri/wp-sec
	wp wp-sec check --type=core
	wp wp-sec check --type=all


## Questions from the Audience

### What are the limitations on the SSH gateway?
At WPEngine, you can't use the "sudo" command. Also, the connection will timeout after 10 minutes. Generally, you won't be able to modify the container itself, but you will be able to mess with your own files and install.

The commands within WP-CLI actually run on a separate Kubernetes cluster, so it doesn't actually eat up your WordPress site's resources

### Any way to add custom post type posts?
You can generate instances of posts and you can also define a new custom post type with the "scaffold" command. But, as far as generating a new CPT, not sure

You can use a --post-type argument on the wp create post command

### Add Multiple Posts at the Same Time
Yep, there are ways to do this. You can also do something like a loop of current posts to change authors of current posts.

### Are Passwords Stored Here?
Yes, you can fetch/update hashed passwords and stuff from WP-CLI. Only let authorized users access WP-CLI, because with great power comes great responsibility.

### Command for Optimizing Images Already Uploaded
WP-CLI Kraken Image Optimizer package is an option you can install for WP-CLI

### Command to delete user across environment, but also delete content associated with the users
Might have to do three commands; one for user and one for content
	- Get List of All Content Associated with one User
	- Delete Content
	- Delete User

### Can you use WP-CLI to download wp-content folder?
Not on WP-CLI, but you can do so through rsync

### Is there a utility for taking a snapshot of an instance?
A lot of people just download a database backup or zip it up with the website files; may not be one command or utility

### Can you script commands across all your environments?
Use a config file to list out all of the installs you have; not a way to automatically detect all the installs you have on your account

### Is there any SSH Whitelisting?
SSH is open to any IP; you don't have to contact support to SSH into your site

### Can you use WP-CLI to clear WPEngine's Cache?
You can't clear the WP Engine cache through WP-CLI or terminal access.

### How does Search/Replace handle serialized data?
In the Correct Way. Your serialized arrays will get updated the way you would expect them to.

### Are daily WP Engine backups safe from WP-CLI Mishaps?
Yes, anything run inside the WP-CLI container will not affect any backups, as those are all stored offsite.

### What are the requirements to use WP CLI?
On WPEngine, WP CLI is available on Premium and Enterprise WPEngine plans. On other hosts, you'll have to check with them.

### Can WP-CLI commands be run in cron jobs?
Yes, you would just put WP CLI in the cron job if you wanted something to run everyday at 6am, for example.

### WP CLI - Can you initiate backups on all installs?
Not a functionality of WP CLI, but could be done via a regular BASH script

### Can You Install New WP-CLI Packages on WP Engine?
Yes, but because it's a Kubernetes cluster, anything you install will disappear when you end the session. So, you will need to re-install those packages when you log back into WP-CLI.

### Can You Use WP-CLI to delete database transients?
Yep, there's a command for that.

### Anything that WP-CLI can do that can't be achieved with Wordpress/PHP functions?
Nope.