=== Developer Share Buttons ===

Contributors: terminalpixel
Tags: share buttons, developer, social
Requires at least: 3.5
Tested up to: 3.9.1
Stable tag: 1.0.5

A super lightweight social sharing solution. No JavaScript. No images. No CSS.

== Description ==

A simple, customisable share buttons solution designed specifically for theme developers.

If you would like to help out please contribute to the [GitHub repository](https://github.com/terminalpixel/Developer-Share-Buttons)

== Installation ==

It has an admin page to control which Install the plugin in whatever way you deem fit. Once installed you can set the default settings on the options page. Use some other plugin like Header and Footer to echo the output. You can use this syntax on template or via any plugin :

`<?php the_dev_share_buttons (); ?>`


== Frequently Asked Questions ==

= What functions are available to use? =

There are 4 functions available to use:

1. `get_dev_share_buttons` returns html of share links
2. `the_dev_share_buttons` a wrapper just to echo `get_dev_share_buttons`
3. `get_dev_profile_links` returns an array of the links to social pages that are saved in the admin area
4. `the_dev_profile_links` echos the links as `a` tags in a `div`

`get_dev_share_buttons` and `the_dev_share_buttons` both accept 5 optional parameters:

1. services - An array of service ids eg `array( 'facebook', 'twitter', 'google' )`. Defaults to the options saved on the options page
2. url - The url to share. Defaults to value of `get_the_permalink()`
3. title - The title of the item to share. Defaults to the value of `get_the_title()`
4. text - The text that appears before a service title eg "Share on". Defaults to the value set on the options page.
5. image - The url of an image to go along with the main item, only used by certain services. Defaults to the post thumbnail.

= Are there default styles for this plugin? =

No. Do it yourself.


= Does it loads any Javascript? =

No. It is fat free.

= How I can add more services? =

You can add more services using a filter:

`add_filter( 'dev_share_buttons_services', 'my_new_service' );
function my_new_service( $services ) {
    $services['myserviceid'] = array(
        'id' => 'myserviceid',
        'title' => 'My Service Title',
        'url_structure' => 'http://www.shareurl.com/?url=%1$s&title=%2$s&text=%3$s&image=%4$s',
        'url_after_title' => false
    );
    return $services;
}`

= What Theme Frameworks it supports? =

It supports all WordPress themes and frameworks. Genesis (latest) and Woo (latest) are tested.

= Bugs =

Pinterest share has issue to detect post images on Genesis. It will be fixed soon ;)

= Skins and Icons =

Some skins and icons will be added for the new users. All fat free.

== Changelog ==


= 1.0.1 =
* Prevent `the_` functions from returning values
* Add spaces between profile links

= 1.0.3 =
* Fix profile link widget

= 1.0.4 =
* Improve support for non post object based pages

= 1.0.5 =
* Add `rel="me"` support for profile links

= 1.0.5.1 =
* Dr. Abhishek Ghosh is trying to help, no credit required
* Pinterest image grab url fixed - http://www.pinterest.com/pin/find/?url=
