# Creating a Child Theme

1) Create a folder in the themes folder, obviously a child version of a main theme.
2) Add `style.css` file to folder.
3) Add to top of file:
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