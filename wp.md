# Installation

1. Download latest WP version from www.wordpress.org
2. Download and install XAMPP from www.apachefriends.org. Start Apache and MySQL.
3. Download and install HeidiSQL
4. Open HeidiSQL, and create a new session, and a new database.
5. Unzip Wordpress download, and open the "Explorer" button in the XAMPP control panel. Drop the unzipped wp folder in the htdocs folder, and rename as needed.
6. Open a browser and navigate to 'localhost/<nameoffile> (localhost/udemy, in my case)
7. Follow the prompts to set up based on your DB information
8. Once installed, go to 'Settings' -> 'Permalinks', and make sure it's set on 'Post Name' for cleaner route names

# Knowledge prerequisites

# Getting acquainted

- The `wp-config.php` contains basic configuration settings.
- The `wp-includes` folder contains functions and classes used throughout Wordpress
- The `wp-content` folder contains all user-created content, plus themes and plugins

# Theme Creation

-Themes need an `index.php` and `style.css` file(s), with the file header containing the theme name at a bare minimum.

-The `functions.php` file contains helper functions, action hooks, etc.

-Hooks listen for an event and execute code when the proper conditions are met.

-When naming functions, classes, and variables, aim for names that are descriptive but unique, as to not conflict with standard Wordpress library items.

-Scripts and stylesheets need to be enqueued and registered before they are loaded.

-`wp_head` and `wp_footer` files tell wordpress where to load scripts and stylesheets.

# Theme Fundamentals

`register_nav_menu` and `wp_nav_menu` are vital functions to registering and displaying menus

# Creating a Child Theme

1. Create a folder in the themes folder, obviously a child version of a main theme.
2. Add `style.css` file to folder.
3. Add to top of file:
   ```
   /*
   Theme Name: <THEME_NAME>
   Theme URI: <SITE_URL>
   Description: Add a description
   Author: Author name
   Author URI: Your website
   Template: Name of parent theme
   Version: Parent version
   */
   @import url("../parent-theme/style.css");
   ```

# The Loop

-The Loop is a PHP 'while' loop that puts all post-related content on the site
