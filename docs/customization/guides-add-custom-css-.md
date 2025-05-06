# Guides Add Custom Css


*Source: [https://simplyscheduleappointments.com/guides/add-custom-css/](https://simplyscheduleappointments.com/guides/add-custom-css/)*

- Basic Edition
- Plus Edition
- Pro Edition
- Business Edition

The usual methods ofenqueuing custom CSSstylesheets won’t affect the styling of Simply Schedule Appointments.

This is because SSA is written as two single-page apps (one for booking and one for admin) using Vue.js and the WordPress REST API.You can, however, still change the appearance of both apps.

This is mainly directed toward developers who are comfortable with accessing their theme files and writing CSS.Please see the section below on using the WP File Manager plugin if you’re not too familiar.

We also offer some morebeginner-friendly ways to style the booking app. We’ve also written outhelpful CSS snippetsto help you target specific styles.

### Admin App Custom CSS

The Admin App includes everything you see on the SSA Admin Appointments page. You’re welcome tohide our logo, change the layout, or hide the foxy images.

To style the admin app, add a file at this location:

wp-content/themes/your-theme/ssa/admin-app/custom.css

`wp-content/themes/your-theme/ssa/admin-app/custom.css`

whereyour-themeis the name of your theme folder.

`your-theme`

You’ll also need to create thessaandadmin-appfolders in your theme.

### Booking App Custom CSS

Like the admin app, you can style the booking form by adding your own CSS files to your theme. This includes the Booking Calendar and the Upcoming Appointments modules.

To style the booking app, add a file at this location:

wp-content/themes/your-theme/ssa/booking-app/custom.css

`wp-content/themes/your-theme/ssa/booking-app/custom.css`

whereyour-themeis the name of your theme folder.

`your-theme`

You’ll also need to create thessaandbooking-appfolders in your theme.

### Using WP File Manager

If you need help adding a custom.css file to the booking or admin app, an easy way to do this is with the freeWP File Manager plugin.

This plugin will let you add and edit a custom.css file directly in your theme.

#### Navigating To The Theme’s SSA Folder

After activating, go to the newWP File Manager tabon the left panel of the WordPress Dashboard.

You should see a screen like this.

To edit either the booking app or the admin app, you’ll need to navigate to the SSA folder withinyour active theme.

wp-content/themes/your-theme/ssa/

`wp-content/themes/your-theme/ssa/`

Now, depending on whether you want to edit the Booking or Admin App, you’ll choose one of the folders within the SSA folder.

- booking-app
- admin-app

#### Adding and Editing a Custom.css File

For this example, we want to add the custom.css file toWhite Label the Admin App.

So, we’ll need to go to the admin-app folder.Once inside, right-click on the File Manager interface and click on New File > CSS: Cascading Style Sheets.

After adding the file, you can name it anything, but we’ll go ahead and call itcustom.css.

Now, you can right-click on your new custom.css file and click on the Code Editor option.

This should open a popup where you can add your CSS andSave. You should see changes to the booking or admin app immediately after saving.

Custom CSS files added to the parent theme will be overwritten/removed when the theme is updated. Please add any custom CSS files for the SSA plugin to achild themeto avoid losing your customizations.

#### Helpful Customization Guides

#### Custom Email Styles for Notifications

#### White Label Admin with CSS
