# My Bootstrap 4 Classic WordPress Theme

A responsive classic WordPress theme built with PHP templates, integrated with local Bootstrap v4.0.0 assets, featuring 4 custom menu locations, custom post types, and highly flexible, page-builder-friendly layouts.

## Requirements

* WordPress version: 6.0 or higher
* PHP version: 8.0 or higher

## Features

* Built-in **Bootstrap v4.0.0** grid system and utility classes
* Localized assets for faster offline development and security
* **Customizer-Ready Homepage:** 4 unique landing sections, hero image & call-to-action button manageable directly via the dashboard
* **4 Menu Locations:** Comprehensive site-wide navigation control
* **Custom Post Types & Shortcodes:** Dedicated data structure company services/values/testimonials and shortcodes to display it.
* **Page Builder Friendly:** Minimal inner page layouts designed to work seamlessly with Gutenberg, Elementor or any other page-builders.

## Installation

1. Download the latest release from this repo into your WordPress installation:
   `/wp-content/themes/htfn/`
2. Log in to your WordPress Dashboard.
3. Navigate to **Appearance > Themes**.
4. Find **HTFN** and click **Activate**.

## Homepage Configuration

This theme requires a static page setup to render the homepage correctly. It does not support displaying the latest blog roll directly on the homepage.

### Step 1: Mandatory Static Homepage Setup
1. Create two new pages in WordPress: one named **Home** (or your preferred landing name) and one named **Blog** (or **News**).
2. Navigate to **Settings > Reading** in your dashboard.
3. For **Your homepage displays**, select **A static page**.
4. Set **Homepage** to your **Home** page (intercepted by `front-page.php`).
5. Set **Posts page** to your **Blog** page.
*The theme will automatically route your default blog roll loop through `index.php`.*
6. Click **Save Changes**.

### Step 2: Customizing the 4 Homepage Sections
Navigate to **Appearance > Customize > Homepage Options** to configure the 4 content zones rendering inside `front-page.php`:
1. **Hero/Banner Section:** Edit the background image, and call-to-action button.
2. **Features/Services Section (First to Fourth):** Configure a multi-column Bootstrap grid highlighting key features or services and a section image.
*One way to configure would be to add the custom-post-types (service/values/testimonials) and display it using shortcodes in one of the textboxes. Ex: [display_services count="4"] latest four service custom-post-types*

### Step 3: Customizing header/footer background colors
Navigate to **Appearance > Customize > Header/Footer Options** to configure the background colors for header/footer:
1. **Header Background Color:** Edit the header background color.
2. **Upper Footer Background Color:** Edit the upper-footer background color. This section has all the footer links.
3. **Lower Footer Background Color:** Edit the lower-footer background color. This section has the copyright section.
4. **Lower footer Font Color:** Edit the font color of the copyright section.

## Navigation Menus

The theme registers **4 unique menu locations** managed under **Appearance > Menus** or the Customizer:

1. **Primary Menu (`primary`):** The main header navigation menu, optimized with Bootstrap dropdowns.
2. **First footer Menu (`footer-1`):** Located in the site footer for legal pages, sitemaps, or privacy links.
3. **Second footer Menu (`footer-2`):** Located in the site footer for legal pages, sitemaps, or privacy links.
4. **Social Links Menu (`social`):** Tailored for mapping social media profile links to matching icons.
**Supports only linkedin and facebook icons for now. Make sure to clearly specify LinkedIn/Facebook in the menu items navigation label as the icons are generated from this.  

## Custom Post Types (CPTs)

This theme automatically registers a few Custom Post Types tailored for the company descriptions directly via `inc/class-htfn-cpt.php` (hooked into `init`).
Following are the list of CPTs available:
1. **Services:** Enter various services offered by the company. Display it on the front-end using shortcode [display_services count="4"].
2. **Values:** Enter company values and display it on the front-end using [display_values count="4"].
3. **Testimonials:** Enter client testimonials and display it on the front-end using [display_testimonials count="4"].

* **Single Template:** `single.php` a common template file for all post types.


## Internal Page Architecture

To grant content creators maximum styling freedom, internal pages (`page.php`) utilize a minimalist, non-intrusive Bootstrap grid structure:
* **Left Column (`.col-md-4`):** Displays the featured image (thumbnail).
* **Right Column (`.col-md-8`):** Unlocks the main content canvas. 

This unrestrictive, clean canvas structure prevents theme layout conflicts, allowing users to safely build complex designs using modern drag-and-drop page builders.

## Bootstrap 4 Theme Integration

* **Navigation:** For native Bootstrap navbar dropdown support, use a standard custom `WP_Bootstrap_Navwalker` class within `header.php` for the `primary` menu position.
* **Containers:** Theme containers utilize `.container` or `.container-fluid` directly inside template files to wrap the core loops.

## License

This theme is licensed under the [GNU General Public License v2 or later](https://gnu.org).