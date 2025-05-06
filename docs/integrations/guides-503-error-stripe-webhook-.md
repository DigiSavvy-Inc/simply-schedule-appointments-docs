# Guides 503 Error Stripe Webhook


*Source: [https://simplyscheduleappointments.com/guides/503-error-stripe-webhook/](https://simplyscheduleappointments.com/guides/503-error-stripe-webhook/)*

- Basic Edition
- Plus Edition
- Pro Edition
- Business Edition

We’ve had some customers experience issues with the Stripe Webhook in Simply Schedule Appointments when using Cloudflare. Stripe will notify you on your online account or through email that you have an error. Or, you may notice that the SSA Stripe integration is not working correctly.

If you’renotusing Cloudflare and experiencing payment issues,please contact our support team.

### How to Resolve HTTP 503 Stripe Webhook Errors

This error is caused when Stripe cannot make a successful call to theWebhook URL created through the SSA Stripe integration.The URL looks like this:

```
https://www.YourSite.com/index.php?ssa-listener=stripe
```

`https://www.YourSite.com/index.php?ssa-listener=stripe`

To fix this, you’ll need to add Stripe’s Webhook IP addresses to Cloudflare’s IP whitelist on your account:

1. Obtain all Stripe’s Webhook IP addresses.
2. Thenadd those IP addresses to Cloudflare’s whitelistfollowing their instructions or your hosting providers instructions if they integrate with Cloudflare for you.

After doing so, you can eithermanually test if the Webhook is successful.Or, you can reach out to the Stripe support team, and they’ll be happy to test it for you.

#### Payments, Stripe and PayPal FAQ

#### Stripe Test Mode

#### Stripe Setup
