# CHANGELOG

## v0.9.9.7

* Increased page title and slug length from 60 to 255.
* Removed all non-cool characters from Widget short name to stop you having to.
* Added Dutch language pack.

### Bugs

* Language switcher will now work when Pyro is installed out of web root.

## v0.9.9.6

* {js('http://example.com/foo.js')} will now work as <script> are stripped.
* <script>, <iframe>, etc are no longer removed from pages.
* Added {$pyro.server.xxxx} for things like {$pyro.server.server_name}.

## v0.9.9.5

* Loading CP > Widgets will now automatically install any new widgets found.

### Bugs

* Fixed Widget title validation error.

### Bugs

* Fixed issue #251: MySQL Strict mode error for page_layouts.theme_layout.
* Fixed XSS security issue.
* Fixed issue where new modules were not automatically imported when viewing the Modules list.

## v0.9.9.4

* Added a "Script" tab to CP > Pages which contains a JavaScript editor.
* Upgraded TinyMCE to 3.3.8.
* The first photo will be displayed beside the description on the frontend.
* Admin login now shows login error messages.

### Bugs

* Added mime type support for "application/octet-stream" to zip.
* Running PyroCMS on a port other than 80 will no longer break login.
* Fixed issue #236: TinyMCE missing images.
* Fixed link in forgotten password email.
* Fixed broken TinyCIMM record in Permissions list.
* Fixed syntax error in french admin language file.
* Fixed "Read more" link in Spanish.
* Fixed issue of thumbnails not being created on photo upload.
* Drag and drop sorting that you do in the admin panel is reflected on the front end.


## v0.9.9.3

### Bugs

* Fixed issue #234. Admin's could not log in due to Validation being called instead of Form_validation.
* Fixed "MX_Language not found" bug.
* Patched a MySQL Strict Mode error in permission_rules.user_id.
* Fixed theme layouts attached to page layouts.
* Improved admin rounded corners for WebKit.


## v0.9.9.2

* If a module is missing a language file for the current language, then it now falls back to english, instead of breaking.
* Updated navigation widget to add class="current" to the current navigation list item.

### Bugs

* Fixed issue #218: theme_layout field was missing from page_layouts table.
* Fixed issue #223: _parse_xml in modules doesn't parse XML controller for multiple controllers.
* Fixed cookie settings that were being reset to blank in the config file.
* Fixed issue #228: Removed random / in the Spanish navigation lang.
* Fixed an issue that caused cookies not to function correctly when running PyroCMS locally.

## v0.9.9.1

### Bugs

* Fixed issue #211: Field 'display_name' doesn't have a default value (MySQL Strict Mode).
* Fixed User edit in CP.  Can now change password.
* Fixed issue #210: Breadcrumb "Array" issue in CrystalX theme.
* Fixed issue #213: Navigation target causing HTML validation failure when set to "Current window"
* Fixed issue #145: News titles now allow html characters without blowing up everything.

## v0.9.9

* Theme Layouts can now be assigned to Page Layouts.
* Installer can now get server information from (and install to) remote database servers.
* Comments can be added to a Page with a checkbox on Add/Edit "Options" tab.
* Added third_party/widgets so you can add your own Widgets out of the way of application folder.
* Query strings are now fully supported.
* Added hooks for post_user_activation and post_user_login for custom actions.
* Twitter/News integration now handles errors gracefully and gives you any error Twitter returns.
* Modules have been moved to the DB (details.xml still required for import).
* Themes with no theme.xml will still function fine, they just won't have author name, website, etc.
* Widget tags added to Control Panel to show how to insert widgets and widget areas.
* DEPRECATED support for .php in themes, use .html for all theme view files and theme layouts.
* Modules can now be uploaded, installed, uninstalled, enabled and disabled via the admin panel.
* A Module's details.xml can now contain SQL data to be run on module upload (see the forums details.xml for example).

### Bugs

* Fixed issue #200: Call to undefined method Permissions_m::checkRuleByRole().
* Fixed table and column collation in the forum tables.
* Fixed Tiny MCE bug that prevented the image manager from working when PyroCMS was installed in a sub-directory.
* Fixed enable_query_string setting in the installer config template.
* Fixed error in users/register that prevented form_validation errors from displaying.
* Fixed issue #205: The news article date cannot be changed on creation or edit.
* Fixed upgrade script issue that caused an error by trying to create a column in a table that didn't exist yet.
* Fixed issue #206: Twitter/News integration issues.
* Fixed redirect loop for any users logging in with a direct visit to /users/login that only affected root installs.
* Fixed CP > Themes > Upload Theme.

## v0.9.8

* Added "Widgets" which allow very flexible chunks of code to be placed almost anywhere.
* Added custom CSS area for pages.
* Added GUI editable "Page layouts" to control shared layouts for grouped pages.
* "Check all" boxes and CTRL + Click selecting added to all listing pages.
* Switched module system from Matchbox to Modular Separation (minor performance boost).
* Switched template system from HelpfulParser to Dwoo (dramaticallty improved syntax support, if/else, loops, etc).
* Removed Layout library and replaced with the much cleaner Template library.
* Removed all PHP short-tags.
* Standardized much of the model code, and removed deprecated CodeIgniter ActiveRecord methods like getwhere().
* Disabled GZIP compression by default. If you want it, re-enable in application/config/config.php.
* Settings library now loads all settings on instantiation, instead of one query-per-setting.
* Added "Preview" windows for pages and news, much more accurate than before.
* Draft/Live status added for pages, admins can see pages anyway.
* Swapped Facebox for Fancybox. Mainly iframe support, but it seems generally better.
* Re-enabled page slug editing.
* Navigation add/edit form is now much more user-friendly.
* Removed all CAPTCHAs and use Akismet and some clever trickery to check for spam.
* Upgraded to Google Async Analytics (much quicker).
* Added editable 404 page which actually sends 404 header.
* Navigation links are drag/drop sortable in admin.
* URI slugs in News and Pages are now editable.
* Upgraded Dwoo to v1.1.1.
* Upgraded jQuery to v1.4.2.
* Upgraded jQuery UI to v1.7.2.
* Updated default theme to use entirely Dwoo syntax as an example.
* Required metadata such as jQuery / front.js loading is now handled internally so theme designers dont need to remember it.
* Optional RSS feeds of a pages children, available for any page.
* Tidied up the dashboard, added recent users & comments and made it multi-lang.
* Added Polish language support.
* Added "Variables" module which allows user-defined variables accross the site.
* Merged Ion Auth project into the core to replace legacy user system
* Added /third_party folder to store downloadable modules and themes.
* Error message added in case active theme is deleted.
* Added IP tracking to comments.

## v0.9.7.4
 
* Full support for PHP 5.3.
* Fixed "could not open application/assets/config/config.php" error on Install Step 4.
* Extra support for different server types.
* index.php is no longer removed by default, unless a supported server is picked.

## v0.9.7.3

* Removed MySQLi as a dependency - should fix installer.
* Fixed AJAXify for FF2 and IE7. 
* Fixed loads of TinyCIMM bugs (Image Manager)
* Added better JS support for IE6 (not going to make a habit of that)
* Added German language support.
* Stopped PHP errors showing if you clicked Publish/Delete with no news articles selected.

## v0.9.7.2

* Contact captcha fixed
* More installer bugs fixed
* Added "target" to navigation links
* Fixed an issue with Cache library lazy-loading that was breaking lazydays theme

## v0.9.7.1

* Improved PHP 5.3 support
* Several installer bugs fixed
* Added Gravatar support to comment
* Enabled short-tag rewriting by default.

## v0.9.7

* New Page manager - Use a tree navigation view to manage and link your unlimited levels of pages.
* Image uploading via TinyMCE - Not just any plugin, Richard Wills (@badsyntax) has been going nuts on the development here and made an amazing plugin which strongly integrated with PyroCMS.
* Improved interface - Now using a slightly darker theme. Less brown, more black and orange.
* Added French language pack
* Cross-browser improvements - much better support for Safari, Opera and Chrome.
