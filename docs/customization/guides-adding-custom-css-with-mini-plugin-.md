# Guides Adding Custom Css With Mini Plugin


*Source: [https://simplyscheduleappointments.com/guides/adding-custom-css-with-mini-plugin/](https://simplyscheduleappointments.com/guides/adding-custom-css-with-mini-plugin/)*

- Basic Edition
- Plus Edition
- Pro Edition
- Business Edition

You can install the mini-plugin on your site like any regular plugin. To do so, take the following steps.

1. Download the mini-plugin zip via the following link:https://github.com/nsquared-team/ssa-custom-styling
2. Log into your WordPress website as an administrator and head over toPlugins > Add New Plugin > Upload Plugin > Choose File.
3. Upload the downloaded mini-plugin file to your WordPress site. Once the file is loaded, install and activate the plugin, after which the mini-plugin should be displayed in the list ofInstalled Plugins.

### Adding custom CSS to the Mini-plugin

Once the plugin is activated, go toPlugins > Plugin File Editorand select SSA Customization—Custom Styling under theSelect Plugin to editoption.

Once the customize.php file for theSSA Customization—Custom Stylingis loaded, you will see three add_action functions with options to add CSS to the following:

- SSA BACKEND admin app: stylize the admin dashboard, accessible through your site’s backend via the WordPress Dashboard> Appointments.
- SSA booking app: stylize the frontendbooking calendars displayed on your site.
- SSA FRONTEND admin app: stylize the admin dashboard, which is accessible via frontend WordPress website when embedding the admin app shortcode on a page.

Add the custom CSS to the corresponding option and update the file.

With this method, some custom CSS snippets might not work as intended, as the SSA plugin style settings might overwrite the CSS you added. Adding the important tags (!important) at the end of the CSS snippets for the code section should fix the issue. However, feel free to write to ourSupport Teamif you need further assistance.

#### Appointments Tab for Member Dashboards

#### ssa/appointments/customer_information/get_defaults Filter

#### ssa/templates/get_template_vars Filter
