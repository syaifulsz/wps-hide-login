=== Rename wp-login.php ===

Contributors: avryl
Donate link: https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=49WXVSPP2HUKG
Tags: rename, login, wp-login, wp-login.php, brute force attacks, custom login url, security
Requires at least: 3.8
Tested up to: 3.8
Stable tag: 2.1.1
License: GPLv2 or later
License URI: http://www.gnu.org/licenses/gpl-2.0.html

Change wp-login.php to anything you want. It can also prevent a lot of brute force attacks.

== Description ==

*Rename wp-login.php* is a very light plugin that lets you easily and safely change wp-login.php to anything you want. It doesn’t literally rename or change files in core, nor does it add rewrite rules. It simply intercepts page requests and works on any WordPress website. The wp-admin directory and wp-login.php page become inaccessible, so you should bookmark or remember the url. Deactivating this plugin brings your site back exactly to the state it was before.

= Compatibility =

Requires WordPress 3.8 or higher. All login related things such as the registration form, lost password form, login widget and expired sessions just keep working.

It’s also compatible with any plugin that hooks in the login form, including

* BuddyPress,
* bbPress,
* Limit Login Attempts,
* and User Switching.

Obviously it doesn’t work with plugins that *hardcoded* wp-login.php.

This also works with multisite! Activating it for a network allows you to set a networkwide default. Individual sites can still rename their login page to something else.

If you’re using a **page caching plugin** you should add the slug of the new login url to the list of pages not to cache. For W3 Total Cache and WP Super Cache this plugin will give you a message with a link to the field you should update.

= Benefits =

Not only does it allow you to further customise your login page, it also prevents brute force attacks that are targeted specifically to wp-login.php. Both the wp-login.php page and the wp-admin directory (if not logged in) become inaccessible.

While you could use this plugin to prevent a lot of brute force attacks, it does not mean you don’t need a strong password. Read [this codex article](http://codex.wordpress.org/Brute_Force_Attacks) for more information on how to protect your website.

Of course, if you want to keep your login page secret, you should make sure there aren’t any links pointing to it on your website.

= GitHub =

This plugin has a [mirror](https://github.com/avryl/rename-wp-login) on GitHub.

== Installation ==

1. Go to Plugins › Add New.
2. Search for *Rename wp-login.php*.
3. Look for this plugin, download and activate it.
4. The page will redirect you to the settings. Rename wp-login.php there.
5. You can change this option any time you want, just go back to Settings › Permalinks › Rename wp-login.php.

== Frequently Asked Questions ==

= I forgot my login url!  =

Either go to your MySQL database and look for the value of `rwl_page` in the options table, or remove the `rename-wp-login` folder from your `plugins` folder, log in through wp-login.php and reinstall the plugin.

== Changelog ==

= 2.1 =

* Works now with non-pretty permalinks!
* Gives a message when using W3 Total Cache or WP Super Cache to update options.

= 2.0.1 =

* Prevents pretty redirects such as /login and /admin.
* Simplifies some code.
* Forces login page with trailing slash.
* Replaces a wp_redirect with wp_safe_redirect.
* Shows error message in the network admin if permalinks are not enabled for the main site.

= 2.0 =

* This plugin can now be activated for a network and a networkwide default can be set.
* The plugin now hooks in after init to make sure any customisations to the login form are hooked in before it.
* Links should now be fixed when SSL is enabled.

= 1.9 =

* wp-admin will now have a `wp_die()` message instead of a 404 template because this caused problems.
* Minimum version is now 3.8.
* Added updates from wp-login.php in 3.8.

= 1.8 =

* OOP PHP.
* Requires WordPress 3.7 or higher.
* MultiViews compatible.

= 1.7 =

* Made compatible with WordPress 3.7.

= 1.6 =

* Fixed the login link when `site_url()` ≠ `home_url()`.
* Added a [mirror](https://github.com/avryl/rename-wp-login) on GitHub.

= 1.5 =

* Made [User Switching](http://wordpress.org/plugins/user-switching/) compatible.

= 1.4 =

* Faster page load.
* Fixed 404 error for permalink structures with a prefixed path. “Almost pretty” permalinks work now too.
* Code clean-up.

= 1.3 =

* Prevents the plugin from working when there is no permalink structure.

= 1.2 =

* Fixed status code custom login page.

= 1.1 =

* Blocked access to wp-admin to prevent a redirect the the new login page.

= 1.0 =

* Initial version.
