# Guides Redirect After Booking Custom Confirmation Page


*Source: [https://simplyscheduleappointments.com/guides/redirect-after-booking-custom-confirmation-page/](https://simplyscheduleappointments.com/guides/redirect-after-booking-custom-confirmation-page/)*

- Basic Edition
- Plus Edition
- Pro Edition
- Business Edition

This guide will show you how to redirect users to a new page after submitting their booking. This is handy for creating a custom confirmation page or tracking booking conversions based on the page sessions instead of custom events.

This can only redirect to pages on thesameWordPress website since the new shortcode attribute requires apost ID.

### Create the New Confirmation Page on Your Website

Embed the following shortcode on your new confirmation page:

```
[ssa_confirmation]
```

`[ssa_confirmation]`

By default, this shortcode says, “Simply Schedule Appointments Booking Confirmation.” You’re welcome tochange the texthere but remember that this converts into the confirmation module during the redirection process.

#### Find the Post ID

While creating this new page, take note of thePost IDsince you’ll need this for the next steps. To find the Post ID, open the page’s editor and look at the URL. The number will be listed afterpost=.

For example, your URL may look like this:

https://yourwebsite.com/wp-admin/post.php?post=1234&action=edit

In the example above, the post ID is 1234.

### Update the Booking Page Shortcode

Embed the booking calendarusing a shortcode along with the new redirect attribute,redirect_post_id:

```
[ssa_booking redirect_post_id="1234"]
```

`[ssa_booking redirect_post_id="1234"]`

Replace1234with thePost IDwe collected in the previous step.

### Redirect to Custom Confirmation Page After Booking Demo

In this example, we have one page for booking appointments and another for confirmation. The confirmation page can be customized to your heart’s content. In this case, we added an image, text, and buttons.

#### Installing a Paid Premium Edition

#### Start Here – After the Setup Wizard

#### Display the Booking Calendars
