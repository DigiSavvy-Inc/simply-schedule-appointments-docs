# Guides Google Api Credentials


*Source: [https://simplyscheduleappointments.com/guides/google-api-credentials/](https://simplyscheduleappointments.com/guides/google-api-credentials/)*

- Basic Edition
- Plus Edition
- Pro Edition
- Business Edition

To start syncing with Google Calendar, you’ll need to collect the Client ID and Client Secret from your Google API.

Our other guide covers enabling and using the Google Calendar Sync with your Appointments and Booking Calendar:Syncing with Google Calendar.

This process changes all the time. We do our best to keep this up to date, but there’s usually no warning or notification that the process has changed.

Guide Last Updated: October 13th, 2022

### Video Walkthrough of the Entire Setup Process

Video Last Updated: March 30th, 2022

### Open the Google Developer APIs and Services Dashboard

Go to theGoogle Developer APIs and Services Dashboard.

Make sure you log in to the Google account you’d like to sync with. You may also need to accept the Google Cloud Platform Terms of Service.

### 1. Create a New Project

Once you’re on the dashboard,create a new project or choose an existing one. Creating a new project may take a moment. You may have to refresh the page to see your new project.

If you created a new project, you can use the following settings:

- Nameit “Booking Calendar Sync”,
- and leave theLocationset to No Organization.

Google Suite users can proceed with using theirorganization nameas the Location. Can’t click on any organizations?Go to our Can’t Create a Project section.

Go back to the APIs and Services Dashboard.

#### Alternate Screen After Creating a New Project

If you see this screen after starting a new project, click on theExplore and enable APIsoption under the Getting Started section.

#### Can’t Create a New Project?

Only the domain owner can create a new Google Cloud Platform Project. If you can’t create a new project, contact the domain owner to create the project for you and add you as a collaborator to the project.

Here are some guides to help you get this sorted out:

- Add collaborators to a Google Cloud Project
- Grant a single role to a collaborator for the Google Cloud Project

### 2. Searching the API Library

Inside the Dashboard, press the button that saysLibraryon the left-side panel. That should take you to the Google API Library.

In the Google API Library, search for “Calendar”. Select the Google Calendar APIoption.

Within the Google Calendar API page, click theEnablebutton to add the Google Calendar API to your project.

### 3. Creating Credentials

The SSA plugin is self-hosted, meaning our company never accesses your data. This app is set up as your own, where your website is the host, and you’re technically the developer for this Google App.

From here, we can start the path to creating the API credentials. Select theCreate Credentialsbutton.

#### 3A. Credential Type

Select theGoogle Calendar APIfrom the Select an API dropdown. A set of radio buttons will appear; click on theUser dataoption. ClickNext.

#### 3B. OAuth Consent Screen

Fill in the following fields:

##### App Information:

- App name: “Booking Calendar Sync”
- User Support email: Use your email address

##### Developer Contact Information:

- Email Addresses: Use your email address

ClickSave and Continue.

#### 3C. Adding the Scope

Select theAdd or Remove Scopesbutton.

Addonlythe Google Calendar API with the…auth/calendarscope, and use the search filter to search for “Calendar”. After selecting the scope, scroll to the end and chooseUpdate.

ClickSave and Continue.

#### 3D. OAuth Client ID Application

Fill in the following fields:

- Application Type: select Web application
- Name: Type in something like “Booking Calendar Sync”
- Authorized redirect URLs:  enter your website’s URL with the https:// and don’t include any subdomains.

When you’re done, clickCreate.

#### 3E. Your Credentials

We don’t have to copy the credentials from here yet; we still need to make some adjustments to our OAuth Consent Screen.

Go ahead and clickDone.

### 4. Last Adjustments to OAuth Consent Screen (Don’t Skip!)

Select theOAuth Consent Screen tab. We’ll need to double-check the following:

- External vs. Internal User Types
- Publishing Status

#### 4A. External vs. Internal User Type

External vs. Internal, more informationhere:

- Externalapps also allow users outside your organization (@your_organization.com) to connect SSA to their personal Google Calendar. Available to any test user with a Google Account.
- Internalapps allow only users within your organization (@your_organization.com) to connect SSA to their personal Google Calendar.

Please selectExternalunlessyou own aGoogle Suite or Workspaceaccount and plan to use your custom email address to sync to SSA.

#### 4B. Publishing Status (Only if selected External in 4A)

By default, the Publishing Status will be set to Testing. Weneed to make sure this is set toIn Production. Click onPublish App.

This should show you a pop-up with some warnings. ClickConfirmon the pop-up.

Since this is for personal use,you do not have to verify the app or make a Youtube video.YOUDO NOTHAVE TO PREPARE FOR VERIFICATION.

### 5. Collecting the OAuth Client ID and Client Secret and Add to SSA

Now, we’ll be able to collect the Client ID and Client Secret for the Simply Schedule Appointments sync settings.

Go toCredentialsfrom the left-side menu.

Click on theClient ID Namein theOAuth 2.0 Client IDs table.You should see yourClient ID and Client secretin the top-right corner of the page.

#### Adding the Client ID and Client Secret to SSA

Paste your Client ID and Client Secret to the Google Calendar Sync settings in Simply Schedule Appointments. ClickSave and Authorize.

Google will now ask permission for Simply Schedule Appointments to access your calendar. Go through those prompts to accept the permissions.

How to resolve 400 redirect_uri_mismatch errors

#### Bypassing “This app isn’t verified” message

If you choose the External app type, you may see a screen thatsaysThis app isn’t verified.To bypass this, click on theAdvancedlink and then the link that saysGo to yoursite.com (unsafe). That should allow you to see the permission prompts.

Learn more about the “This app isn’t verified” errorand why it won’t affect Google Calendar Sync.

### 6. Finish Setting Up Your Appointment Types (Required)

After you have set up your Google Calendar client ID, your Simply Schedule Appointments calendar syncs with Google Calendar.Now, finish setting upGoogle Calendar in the Appointment Type settings.

#### Google Calendar FAQ

#### Google Calendar Not Syncing or Checking for Conflicts

#### 400 redirect_uri_mismatch Error
