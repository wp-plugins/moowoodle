=== MooWoodle ===
Contributors: Dualcube, debjyati_dc
Tags: wordpress, moodle, wooCommerce, wordpress-moodle, wooCommerce-moodle
Donate link: https://dualcube.com
Requires at least: 4.1.1
Tested up to: 4.2.2
Stable tag: 1.0.0
License: GPLv2 or later
License URI: http://www.gnu.org/licenses/gpl-2.0.html

The MooWoodle plugin is an extention of WooCommerce that acts as a bridge between WordPress/Woocommerce and Moodle.

== Description ==
The MooWoodle plugin is an extention of WooCommerce that acts as a bridge between WordPress/Woocommerce and Moodle. It fetches all the courses from your Moodle instance and makes them available for sale, which may be bought by users through WooCommerce. It reduces your effort by synchronising your LMS site with your online store. And when someone purchases a course from the store he/she is automatically gets registered for the course in the LMS site. More over this plugin works with WooCommerce subscription plugin too.

= Compatibility =
* WooCommerce 2.2.1+
* WordPress 4.1.1+
* Multilingual Support is included with the plugin and is fully compatible with WPML.

= Configurable =
WP site setup:
1. To set up the plugin: Synchronise > Settings > Fill up `Access URL` (site url of your moodle site) and `Webservice Token` (generated from your moodle site; a more detailed guide is given below).

2. Check `Create Products From Courses` checkbox if you want to create product from courses during course sync; otherwise leave it unchecked. In that case the courses will be saved in wordpress site and you can manually add products for courses later.

3. Check `Update user info with order info` checkbox to update user info with new order info.

4. By default, the users will be enrolled in the course with student role. If you want to assign any custom role to the user you have to enter the role id in the `Moodle user role id in a course.

Moodle site set up:
Create and setup webservice:
1. Administration > Site administration > Advanced features > Enable webservice > Save changes.

2. Administration > Site administration > Plugins > Manage protocols > Enable `XML-RPC protocol`.

3. Administration > Site administration > Plugins > External services > Add > Give a `Name` and chack `Enabled` > Add service > Add functions > Add the following functions to your webservice:
	i. core_user_create_users: Create users
	ii. core_user_get_users_by_field
	iii. core_user_update_users
	iv. core_course_get_courses: Return course details
	v. core_course_get_categories: Return category details
	vi. enrol_manual_enrol_users: Manual enrol users

4. Administration > Site administration > Plugins > Manage tokens > Add > Select user (Admin) from users\' list > Select your service form services\' list > Save changes.

Disable password policy:
The password policy settings needed to be disabled since the user password will be generated in WordPress end and will not match the password policy of Moodle. The steps to disable password policy are given below.

1. Administration > Site administration > Security > Site policies > Uncheck `Password policy` > Do not forget to save changes.

== Installation ==
NOTE: Woo-Moodle bridge plugin is a extention of WooCommerce, so the WooCommerce plugin must be installed and activated in your WordPress site for this plugin to work properly.

1. Download and install MooWoodle plugin using the built-in WordPress plugin installer.
If you download Woo-Moodle bridge plugin manually, make sure it is uploaded to `/wp-content/plugins/ MooWoodle /`. Or follow the steps below:
Plugins > Add new > Upload plugin > Upload MooWoodle.zip > Install Now.

2. Activate the plugin through the \'Plugins\' menu in WordPress.

== Frequently Asked Questions ==
= Does this plugin work with newest WP version and also older versions? =
Yes, this plugin works really fine with WordPress 4.2.2! It is also compatible for older WordPress versions upto 4.1.1.
= Up to which version of WooCommerce this plugin compatible with? =
This plugin is compatible with the latest version of WooCommerce, that is, Version 2.2.1.
= Does this plugin work with WooCommerce Subscription? =
Yes, it works with WooCommerce Subscription.

== Screenshots ==
1. Fill up `Access URL`, `Webservice token` and other settings fields.
2. Select `Yes` and click on `Synchronise` to sync courses and course categories from your moodle site.
3. In advanced features check `Enable web service` check box and save changes to enable web service for your moodle site.
4. Enable XML-RPC protocol from manage protocol of your moodle site.
5. In `External services` click on `Add` to add your external service.
6. Give a `Name` to your external service and check `Enabled` then `Add service` to add your external service.
7. Click on `Add functions` to add functions to your service.
8. Add above mentioned functions mentioned to your service.
9. In `Manage tokens` click on `Add` to generate new webservice token for your service.
10. Select the admin user from the `User` list and your service form `Service` list the save changes.
11. The token generated for your service. (Copy this token and pest it in `Webservice token` field in our WordPress plugin settings.)
12. Uncheck `Password policy` then save changes to disable Moodle's default password policy checking.

== Changelog ==
1.0.0

== Upgrade Notice ==
1.0.0
