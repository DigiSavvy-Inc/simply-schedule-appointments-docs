# Guides Zapier Integration Webhooks


*Source: [https://simplyscheduleappointments.com/guides/zapier-integration-webhooks/](https://simplyscheduleappointments.com/guides/zapier-integration-webhooks/)*

- Basic Edition
- Plus Edition
- Pro Edition
- Business Edition

Simply Schedule Appointments and Webhooks work together to trigger an action inZapier. Zapier can then integrate with various other apps such as ActiveCampaign, Salesforce, Zendesk, Evernote, and 1000+ others.

#### Example Use Cases

- Send a Slack notification to your employees anytime someone books an appointment.
- Add a contact to an ActiveCampaign from booked appointments.
- Analyze appointment booked data by integrating with Google Sheets.

Feel free to also check out our guide thatprovides an overview of the Webhooks feature.

### Setting Up A Webhook Trigger in Zapier

Start by creating an account onZapier.To use their Webhooks feature, you’ll need to use one of their plans that includes access to Premium Apps.But you can still follow along with this tutorial using the Free plan.

#### Create a New Zap

Once logged in, choose theCreate Zapoption in your Zapier Dashboard. You’ll be redirected to the Zap Editor screen. You’ll need to select theWebhook app as the trigger; this is what we’ll use to integrate with Zapier on our end.

A zap is an automated task that you want to run repeatedlybetween two online apps.

#### Catch Hook Option for Webhooks

When it asks you toChoose App & Event, make sure to chooseCatch Hook, this will allow us to receive the Appointment information automatically and organizes the fields we pass to it.

#### Customize the Hook for Webhooks

Copy theCustom Webhook URLso that we can paste this back into SSA in the following steps.

### Creating a New Webhook in SSA

Go to SSA Settings > Webhooks. Click the toggle to enable this feature, and then clickEdit.On the Webhooks screen, clickAdd a New Webhook.

#### Configure your Webhook in SSA

The SSA webhooks will automatically notify and send Zapier Appointment information depending on your chosen trigger.

- Name: An optional name for you to help keep track of your webhooks.
- Token: A unique token you can use to verify the request. To refresh the token, click the refresh arrow on the right-hand side of the token field.
- Trigger: Select which actions should trigger this webhook
- URLs: The URLs where the webhooks will be sent
- Appointment types: Select all appointment types or select certain appointment types that will trigger the webhook

#### Pasting the Zapier Custom Webhook URL into a New SSA Webhook

Under theURLsfield, paste theCustom Webhook URLyou copied from Zapier earlier.

Now, copy theTokenyou need for the next step.Savethe Webhook.

### Finish Setting Up Webhook Trigger in Zapier

Going back to theMake a Zapeditor, take theTokenyou just copied and paste it into thePick Off A Child Keyfield.

#### Testing the SSA Trigger in Zapier

The next screen in the Zapier editor will ask you to test your trigger. Go back to your SSA page, and depending on what Trigger you chose for your Webhook,you’ll need to set off that trigger.

For example, if you chose Appointment Booked, go to your Booking Calendar and book a test/fake appointment.

Once you’ve set off the webhook, you’ll want to go back to the Zapier editor and selectTest Trigger. You should see a page like this:

### Setting Up Action in Zapier

Lastly, you’ll want to customize the new action in Zapier; in this example, I’ll create a new Trello card whenever someone books an appointment.

Notice that the fields are filled in byWebhooks datathat uses SSA Appointment Information. You can customize your actions using any data pulled in from the payload delivered by the webhook.

Fields like the Name, Start Time, Timezone, Email, Custom Fields, etc… can go here.

Make sure to format your data the way you’d like to see it on your other application. For example, use new lines, dashes, commas, colons, etc…

#### Double-Check Last Details

In your Zapier Dashboard, go to the Zaps page and make sure your new Zap isON.

And that’s it! Now you’re ready to connect your Appointments to any other application supported by Webhooks.

#### Conversion Tracking Overview

#### Payments Setup

#### SMS Notifications
