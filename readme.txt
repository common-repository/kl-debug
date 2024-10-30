=== KL Debug ===
Contributors: krealab
Donate link: https://www.krealab.fr/
Tags: debug, toolbar, developer
Requires at least: 5.2
Tested up to: 6.0
Requires PHP: 7.2
Stable tag: 1.0.5
License: GPLv3
License URI: http://www.gnu.org/licenses/gpl-3.0.html

Friendly debug bar for developer, debug variables helpers and pretty error handler interface(powered by Whoops).

== Description ==
Add a Debug Bar to your Wordpress website to debug and develop your themes, plugins, etc...

With the plugin you can find every variables you want to debug in the same place and use debug functions to display them.

= Prerequisites =

To fully help you to debug your website you need to add some code to your `wp-config.php` file.

`
define( 'WP_DEBUG', true ); // PHP errors, notices and warnings will be displayed
define( 'SAVEQUERIES', true ); // Display queries in current page
define( 'WP_DISABLE_FATAL_ERROR_HANDLER', true ); // Disable WP Fatal error handler
`

= Usage of the debug functions =
To debug a simple variable you can use:
`
<?php dump( $var ); // Dump the variable(s) ?>
`

To debug a variable and stop the process after you can use:
`
<?php dd( $var ); // This will die after dumping the variable(s) ?>
`

= Debug a variable in the debug bar =
This is one of the main aspect of the plugin, to debug variables in a separate place.

The most difficult task when you debug a variable is to deal with container width, with the plugin you have a debug bar where you can add the variables of the current page.

To add a variable to the debug bar you can use the function bellow:
`
<?php kl_debug_add_var( $var ); ?>
`

You can add custom tabs in the debug bar to filter you variables:
`
<?php
kl_debug_add_var(
    $var, // The variable you want to debug
    'Your variable title', // If you want to name the variable
    'The section title', // The tab title
    'the-section-slug' // The tab slug
);
?>
`

= What's Whoops in the setting panel? =
Whoops is the framework that we use to display error handling. (cf. Pretty error handler with stack frames)

== Installation ==
= Requirements =
This plugin requires at least PHP 7.2.

= How to install the plugin =
1. Upload the plugin files to the `/wp-content/plugins/kl-debug` directory, or install the plugin through the WordPress plugins screen directly.
1. Activate the plugin through the \'Plugins\' screen in WordPress
1. Use the Tools->KL Debug screen to configure the plugin

== Frequently Asked Questions ==
= How to set which PHP errors are reported? =
Simply add `error_reporting(E_ALL & ~E_NOTICE);` to the top of your theme functions.php file. This will only display errors that are not notices.

= How can I deactivate the plugin if I can't access the admin screen ? =
Go to your FTP explorer and navigate to the plugin: wp-content>plugins. Rename the folder by adding an _ in the beginning of the folder name.

== Screenshots ==
1. Debug bar open
2. Settings interface
3. Pretty error handler with stack frames(powered by Whoops)

== Changelog ==
= 1.0.5 =
* [Added] Tested up to Wordpress 6.0
* [Updated] Composer dependencies

= 1.0.4 =
* [Added] Tested up to Wordpress 5.8.2

= 1.0.3 =
* [Added] Tested up to Wordpress 5.7.2

= 1.0.2 =
* [Added] Optimize autoload.php
* [Fixed] autoload.php require path that can cause error 500

= 1.0.1 =
* [Fixed] jQuery error when plugin installed on WordPress 5.5

= 1.0 =
* [Added] Initial release

== Upgrade Notice ==
= 1.0 =
Initial release
