link: https://raw.githubusercontent.com/okeeffed/cheat-sheets/master/wordpress-cheat-sheet.php

**Resources**

wphierarchy.com

![Template Hierarchy](https://developer.wordpress.org/files/2014/10/Screenshot-2019-01-23-00.20.04-1024x639.png)

## WORDPRESS THEME FILES

* style.css – This is your theme’s stylesheet file.

* index.php – This is the main body template for your theme. Its job is to bring together all the information in the other theme files using template tags.

* header.php – This file contains the header information that appears with the <head> section of your site, stuff like metadata and the link to your stylesheet.

* sidebar.php – Everything in you sidebar goes in this file, like widgets, categories, additional menus, search form, etc.

* footer.php – This file contains your footer information, such as copyright details, widgets, and social icons.

* single.php – This file displays just one post.

* page.php – When you create a page on your site, this is the template responsible.

* comments.php – This file is responsible for displaying comments.

* 404.php – When visitors try to visit a page on your site that doesn’t exist, this file will general an error page.

* functions.php – This file is where you can place special functions. We always recommend creating a child theme rather than edit this file directly.

* archive.php – Display an archive with this file so visitors to your site can go way back when and read your Hello World! post.

* search.php – Help your visitors search your site with this page.
* searchform.php – Display a search form for your visitors with this template file.

## WORDPRESS DEFINE NEW THEME

This information goes at the top of your stylesheet.css file.

```css
Theme Name: Twenty Sixteen
Theme URI: https://wordpress.org/themes/twentysixteen/
Author: the WordPress team
Author URI: https://wordpress.org/
Description: Twenty Sixteen is a modernized take on an ever-popular WordPress layout — the horizontal masthead with an optional right sidebar that works perfectly for blogs and websites. It has custom color options with beautiful default color schemes, a harmonious fluid grid using a mobile-first approach, and impeccable polish in every detail. Twenty Sixteen will make your WordPress look beautiful everywhere.
Version: 1.2
License: GNU General Public License v2 or later
License URI: http://www.gnu.org/licenses/gpl-2.0.html
Tags: black, blue, gray, red, white, yellow, dark, light, one-column, two-columns, right-sidebar, fixed-layout, responsive-layout, accessibility-ready, custom-background, custom-colors, custom-header, custom-menu, editor-style, featured-images, flexible-header, microformats, post-formats, rtl-language-support, sticky-post, threaded-comments, translation-ready
Text Domain: twentysixteen

This theme, like WordPress, is licensed under the GPL.
Use it to make something cool, have fun, and share what you've learned with others.
```

## WORDPRESS TEMPLATE INCLUDE TAGS

```php
<?php get_header(); ?> /* Includes the header.php file */
<?php get_sidebar(); ?> /* Includes the sidebar.php file */
<?php get_footer(); ?> /* Includes the footer.php file */
<?php comments_template(); ?> /* Includes your comments */
```

## WORDPRESS HEADER/BLOG INFO TAGS

These are functions you’ll find in your theme’s header.php file, though you’ll also find them in other theme files:

```php
<?php bloginfo('name'); ?> /* The title of your site, or blog name */
<?php bloginfo('url'); ?> /* Your site’s URL */
<?php bloginfo('stylesheet_url'); ?> /* Link to your themes’s stylesheet file */
<?php bloginfo('template_url'); ?> /* Location of your site’s theme file */
<?php bloginfo('description'); ?> /* Displays the tagline of your blog as set in Settings > General. */
<?php bloginfo('atom_url'); ?> /* Link to your site’s atom URL */
<?php bloginfo('rss2_url'); ?> /* RSS feed URL for your site */
<?php bloginfo('pingback_url'); ?> /* Pingback URL for your site */
<?php bloginfo('version'); ?> /* WordPress version number */
<?php bloginfo('html_type'); ?> /* The HTML version your site is using */
<?php site_url(); ?> /* The root URL for your site  */
<?php get_stylesheet_directory(); ?> /* Location of your stylesheet folder */
<?php wp_title(); ?> /* Title of a specific page */
```

## WORDPRESS TEMPLATE TAGS

These tags can be used across all of your template files, such as index.php or page.php, making it easy to display specific information anywhere you want on your site:

```php
<?php the_content(); ?>  /* Displays the content of a post  */
<?php the_excerpt(); ?>  /* Displays the excerpt used in posts  */
<?php the_title(); ?>  /* Title of the specific post  */
<?php the_permalink() ?>  /* Link of a specific post  */
<?php the_category(', ') ?>  /* Category of a specific post  */
<?php the_author(); ?>  /* Author of a specific post  */
<?php the_ID(); ?>  /* ID of a specific post  */
<?php edit_post_link(); ?>  /* Edit link for a post  */
<?php next_post_link(' %link ') ?>  /* URL of the next page  */
<?php previous_post_link('%link') ?>  /* URL of the previous page  */
<?php get_links_list(); ?>  /* Lists all links in blogroll  */
<?php wp_list_pages(); ?>  /* Lists all pages  */
<?php wp_get_archives() ?>  /* List archive for the site  */
<?php wp_list_cats(); ?>  /* Lists all categories  */
<?php get_calendar(); ?>  /* Displays the built-in calendar  */
<?php wp_register(); ?>  /* Displays register link  */
<?php wp_loginout(); ?>  /* Displays login/logout link only to registered users  */
```

## WORDPRESS THE LOOPS

The Loop is the default mechanism in WordPress for displaying all of your posts. Exactly how many posts are retrieved is determined by the number of posts you’ve chosen to display in the “Reading” settings in your WordPress dashboard.

Within the Loop, WordPress loops through each post retrieved for the current page one at a time and formats it according to your theme’s instructions.

You can use the Loop to do a lot of useful stuff, like:
* Display post titles and excerpts on your homepage;
* Display the content and comments on a single post;
* Display the content on an individual page using template tags
* Display data from custom post types and custom fields.

```php
<?php
    if ( have_posts() ) :
        while ( have_posts() ) :
            the_post();
            // Post Content here
        endwhile;
    endif;
?>
```

The Loop can display lots of different element for each post. Some of the most common template tags used in themes (according to the WordPress Theme Handbook) are:

```php
<?php next_post_link() ?> /* A link to the post published chronologically after the current post */
<?php previous_post_link() ?> /* A link to the post published chronologically before the current post */
<?php the_category() ?> /* The category or categories associated with the post or page being viewed */
<?php the_author() ?> /* The author of the post or page */
<?php the_content() ?> /* The main content for a post or page */
<?php the_excerpt() ?> /* The first 55 words of a post’s main content followed by an ellipsis (…) or read more link that goes to the full post. You may also use the “Excerpt” field of a post to customize the length of a particular excerpt. */
<?php the_ID() ?> /* The ID for the post or page */
<?php the_meta() ?> /* The custom fields associated with the post or page */
<?php the_shortlink() ?> /* A link to the page or post using the URL of the site and the ID of the post or page */
<?php the_tags() ?> /* The tag or tags associated with the post */
<?php the_title() ?> /* The title of the post or page */
<?php the_time() ?> /* The time or date for the post or page. This can be customized using standard php date function formatting. */
```

You can also use conditional tags, such as:

```php
<?php is_home() ?> /* Returns true if the current page is the homepage */
<?php is_admin() ?> /* Returns true if an administrator is logged in and visiting the site */
<?php is_single() ?> /* Returns true if the page is currently displaying a single post */
<?php is_page() ?> /* Returns true if the page is currently displaying a single page */
<?php is_page_template() ?> /* Can be used to determine if a page is using a specific template, for example:  is_page_template('about-page.php') */
<?php is_category() ?> /* Returns true if page or post has the specified category, for example is_category('news') */
<?php is_tag() ?> /* Returns true if a page or post has the specified tag */
<?php is_author() ?> /* Returns true if a specific author is logged in and visiting the site */
<?php is_search() ?> /* Returns true if the current page is a search results page */
<?php is_404() ?> /* Returns true if the current page does not exist */
<?php has_excerpt() ?> /* Returns true if the post or page has an excerpt */
```