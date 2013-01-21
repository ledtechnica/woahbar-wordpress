# Installing WOAHBar on WordPress #

Attached are the source files I used to install [WOAHBar](http://haatch.com/WOAHbar/ "WOAHBar") on a WordPress blog.

Basically I have copied the woahbar folder under my theme directory and add the following lines at the bottom of the theme's function.php file:

```php
function woahbar_scripts() {
  wp_enqueue_script('woahbar_js', get_template_directory_uri() . '/woahbar/woahbar.js', array('jquery'));
}
add_action('wp_enqueue_scripts', 'woahbar_scripts');

function woahbar_styles() {
  wp_register_style('woahbar_css', get_bloginfo('stylesheet_directory') . '/woahbar/woahbar.css');
	wp_enqueue_style('woahbar_css');
}
add_action('wp_enqueue_scripts', 'woahbar_styles');
```

I also added a link to the woahbar.php file from the theme's header.php file - right after the body tag:

```php
<?php include(TEMPLATEPATH . '/woahbar/woahbar.php'); ?>
```