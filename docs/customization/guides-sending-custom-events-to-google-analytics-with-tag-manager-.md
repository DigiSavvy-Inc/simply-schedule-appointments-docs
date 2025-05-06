# Guides Sending Custom Events To Google Analytics With Tag Manager


*Source: [https://simplyscheduleappointments.com/guides/sending-custom-events-to-google-analytics-with-tag-manager/](https://simplyscheduleappointments.com/guides/sending-custom-events-to-google-analytics-with-tag-manager/)*

- Basic Edition
- Plus Edition
- Pro Edition
- Business Edition

In the past, turning on theSSA Tracking featurealone would automatically pass the booking apps’ custom events to Google Analytics.But with the recent transition to Google Analytics 4 from Universal Analytics, the process is now complex because of the need to pass the custom events through Google Tag Manager.

To pass custom events from our plugin requires that you do so throughGoogle Tag Manager. This includes setting up the Trigger, Variables, and the Tags in a container to pass onto Google Analytics.

There’s not much documentation online to help you do this, so we wanted to put together some resources so that our tracking feature can continue to be useful to your analytics research.

#### Two methods we’re going to cover

1. Import the container we’ve created and merge it into your existing (or new) container in GTM
2. Or, create each Trigger, Variable, and Tag from scratch: Coming soon!

#### Universal Analytics vs. Google Analytics 4

Universal Analytics (UA) is the previous generation of Google Analytics; if you set up Google Analytics on your site before October 14, 2020, you’re most likely using UA.

Google Analytics 4 (GA4) is the new generation of Google Analytics that promises more helpful insights through machine learning models. Google claims that this is now the default experience for GA and is where they will be investing all their future improvements.

If you’re using the older UA properties on your site, Google recommends that you begin using the new GA4 properties alongside your existing ones. Read more about what Google has to say about this transitionhere.

#### Important Notes Before We Start

Before we start, we want to outline a couple of things.

- We don’t offer support for Google Analytics or Google Tag Manager. This is beyond our level of knowledge.If you need additional help, we recommend you reach out to ananalytics developer.
- The plugin is tracking-ready; this only means that we’ve done the work of adding the Javascript necessary to pass information to Google Tag Manager.
- Simply Schedule Appointments is a single-page application built using Vue.js and the WordPress REST API. Because of this, there aren’t any actual page views to track; you can only track virtual page views.

### Method 1: Importing Our Pre-Made Google Tag Manager Container

#### Pre-Requisites

- AGoogle Tag ManagerandGoogle Analyticsaccount.
- Make sure toset up the Google Manager scriptson your website. (I used theInsert Headers and Footerplugin for this).
- Turn on theSSA Trackingsettings in the plugin.

#### Download the Container’s JSON File

To start, you will need to download the pre-made container; this holds the Triggers, Variables, and Tags you need to send the custom events to Google Analytics.

Download the JSON Container File Here

Link to Github Repo

#### Import the Container

If you do not have an existing container for your website, you’ll need to create a new one onGoogle Tag Manager.

After creating a container, or if you already have an existing one, you’ll need toaccess the Admin tab from the container’s main dashboard.

Next, you’ll need toselect the Import Containertab.

From here, you can upload the JSON file you collected earlier, choose a workspace, and choose your import option.

For my set up, I chose anExistingworkspace. And, for the import option, I would suggest you choose what’s best for you.

If you just created anew container, feel free to use theOverwriteoption.

But, if you had apre-existing container, I’d suggest you choose theMergeoption and Rename Conflicting Tags, Triggers, and Variables.

ClickConfirmto continue.

#### Replace the Measurement ID

Now that you’ve imported the container, you’ll need to replace the Measurement ID in the GA4 Tag.

Please refer to the Youtube video above if you’re stuck on this step.

Here are a couple of guides to find the Measurement ID in both GA4 and Universal Analytics:

- How to find the Measurement ID
- Setup GA4 Property to an Existing Universal Analytics Property

After collecting the Measurement ID (or “G-” ID), go to Google Tag Manager and open theTagstab. Open theGA4 Tag.

Go ahead andreplace the Measurement IDyou see there with the one you collected from your Google Analytics account. ClickSave.

#### Publish the Container and Wait

After changing the Measurement ID, go ahead and Save/Publish the container. Here’s a Google guide withmore information on Publishing.

It will take up to 24 hours to see your changes take place in the Events tab in Google Analytics.

### Method #2: Create Each Trigger, Variable, and Tag From Scratch in Google Tag Manager

Instructions are coming soon! In the meantime, here is a list of all the virtual paths and events coded into the plugin:

#### Google Tag Manager Page Tracking

We’re sending the following information about the virtual paths to Google Tag Manager when a customer books an appointment:

* Page titles are translatable. If you’ve translated your site/SSA into another language, you will have different page titles

#### Google Tag Manager Event Tracking

We’re tracking the following events and data for Google Tag Manager:

### Basic Event Configuration and Reporting in Google Analytics

Now that you’ve passed the custom events through Google Tag Manager, you’ll be well on your way to begin tracking the Simply Schedule Appointments events in Google Analytics.

After finishing with either Method 1 or 2 from above and waiting for at least 24 hours, you can continue to either view your events or mark some of them as conversions.

#### Viewing the Google Analytics 4 Events and Conversions

Events are actions that visitors or leads take on your website. It’s vital information to know as you can make informed decisions based on actions your visitors take on your website.

Realtime View

Go toGoogle Analytics > Reports > Realtime. Go ahead and poke around your site’s booking page and calendars to see the events happening in real time.

Events View

Another viewing option is to visitGoogle Analytics > Reports > Engagement > Events. You’ll be able to view various GA4 events here, includingbookingCompletedevents and other related SSA events.

Conversions View

Lastly, to view the events that you’ve marked as conversions, visitGoogle Analytics > Reports > Engagement > Conversions. You’ll see statistics that demonstrate which users have completed a conversion event.

#### Marking an SSA Custom Event as a conversion

A conversion is an event that happens where a site visitor or lead takes an action that demonstrates intent. A conversion can be a purchase, a form submission, or booking an appointment (lucky you!).

To mark an SSA event as a conversion, go toGoogle Analytics > Configure > Events.Here, you’ll see the various existing SSA events already configured for you. To mark one as a conversion, simply click the respective toggle under the “Mark as conversion” column.

Find an event that indicatesintent,such as booking an appointment. For example, SSA creates an event calledbookingCompleted.Find that event and click the switch to mark that event as a conversion.

#### Facebook Pixel Tracking

#### Segment Tracking
