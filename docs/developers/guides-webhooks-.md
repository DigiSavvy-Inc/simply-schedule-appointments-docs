# Guides Webhooks


*Source: [https://simplyscheduleappointments.com/guides/webhooks/](https://simplyscheduleappointments.com/guides/webhooks/)*

- Basic Edition
- Plus Edition
- Pro Edition
- Business Edition

Use Appointment actions to trigger other apps or services using the Webhooks feature in SSA.

### Webhooks Overview

Webhooks are a way to send data to other sites/services in real-time.

A webhook is automatically triggered when one of the following appointment actions takes place in our plugin:

- Booked
- Edited
- Canceled

Each webhook comes with apayload;in SSA’s case, it’s a packet of information regarding the appointment, customer info, and action that just took place.

When one of the above actions occurs on your site,you can program SSA to send the payload to a specific URL. We can use this to create indirect integrations with automation services or CRMs.

### Recommended Automation Services

Some services make it easy to connect a webhook to thousands of applications you already use in your workflow. Here are some guides to help you get started with each service:

- Zapier
- Make(formerly Integromat)

### SSA Webhooks PayLoad

This is the information included in each webhook payload.

General Information

- Action that triggered the webhook
- Unique token to verify if needed
- Site Name and URL
- Meta and Signature

Booking Information

- Appointment ID
- Appointment Type ID and Title
- Customer Information, including custom fields
- Post Information
- Customer Timezone
- Start date in UTC and in Local timezone
- End date in UTC and in Local timezone
- Date created and date modified
- Web Meeting Link and Password
- Rescheduling/Cancelation Link
- Price paid, if any
- Payment method used, if any
- Team member name, email, and ID

#### Sample Payload

```
{
  "action": "appointment_booked", // possible values of `appointment_booked`, `appointment_edited`, `appointment_canceled`
  "action_noun": "appointment",
  "action_verb": "booked", // possible values of `booked`, `edited`, `canceled`
  "appointment": {
    "id": "123", // Unique ID to reference this appointment
    "appointment_type_id": "36", // Unique value that is consistent even if the type's name/slug changes
    "appointment_type_slug": "2hr-call",
    "customer_id": "1",
    "customer_information": {
      "Name": "Nathan Tyler",
      "Email": "[email protected]"
      // values from your custom fields will also be included here
    },
    "post_information": [],
    "customer_timezone": "Asia/Beirut",
    "start_date": "2018-09-20 16:15:00", // all dates are stored in the UTC timezone
    "end_date": "2018-09-20 18:15:00",
    "status": "booked", // possible values of `booked` or `canceled`
    "date_created": "2018-09-19 01:00:44",
    "date_modified": "2018-09-19 01:00:44",
    "public_edit_url": "http://yoursite.com/appointments/change/e7b9a0a37d18e86ef11b2da12345678900",
    "price_full": 100.00,
    "payment_method": "stripe",
    "web_meeting_url": "https://your-web-meeting-url.com/url/j.php?MTID=m89e2d3199fc229a01732c0964bf48c03",
    "web_meeting_password": "your-meeting-password",
    "appointment_type_title": "2hr Call",
    "local_time_for": {
      "appointment_type": {
        "raw": {
          "start_date": "2023-10-10 10:00:00",
          "end_date": "2023-10-10 11:00:00",
          "date_created": "2023-10-04 22:04:42",
          "date_modified": "2023-10-04 22:04:44"
        },
        "raw_parts": {
          "start_date": {
            "date": "2023-10-10",
            "time": "10:00:00",
            "timezone": "Asia/Beirut",
            "timezone_offset": "+0300"
          },
          "end_date": {
            "date": "2023-10-10",
            "time": "11:00:00",
            "timezone": "Asia/Beirut",
            "timezone_offset": "+0300"
          },
          "date_created": {
            "date": "2023-10-04",
            "time": "22:04:42",
            "timezone": "Asia/Beirut",
            "timezone_offset": "+0300"
          },
          "date_modified": {
            "date": "2023-10-04",
            "time": "22:04:44",
            "timezone": "Asia/Beirut",
            "timezone_offset": "+0300"
          }
        },
        "formatted": {
          "start_date": "October 10, 2023 10:00 am EEST",
          "end_date": "October 10, 2023 11:00 am EEST",
          "date_created": "October 4, 2023 10:04 pm EEST",
          "date_modified": "October 4, 2023 10:04 pm EEST"
        },
        "formatted_parts": {
          "start_date": {
            "date": "October 10, 2023",
            "time": "10:00 am",
            "timezone": "EEST"
          },
          "end_date": {
            "date": "October 10, 2023",
            "time": "11:00 am",
            "timezone": "EEST"
          },
          "date_created": {
            "date": "October 4, 2023",
            "time": "10:04 pm",
            "timezone": "EEST"
          },
          "date_modified": {
            "date": "October 4, 2023",
            "time": "10:04 pm",
            "timezone": "EEST"
          }
        }
      }
    }
  },
  "team_members": [
    {
      "id": 1,
      "wp_user_id": "2",
      "name": "John",
      "display_name": "John",
      "email": "[email protected]"
    }
  ],
  "meta": [],
  "signature": {
    "token": "1a2b3c4d5e6f..."  // so you can verify that the delivered webhook originated from this site
    "site_name": "This WordPress Site"  // in case you have multiple sites sharing the same webhook
    "home_url": "https://thissite'shome.com"  // the homepage URL for your website
    "site_url": "https://thissite.com"  //  in case you have multiple sites sharing the same webhook
    "network_site_url": "1a2b3c4d5e6f..."  // only different than `site_url` if using multisite
  }
}
```

`{
  "action": "appointment_booked", // possible values of `appointment_booked`, `appointment_edited`, `appointment_canceled`
  "action_noun": "appointment",
  "action_verb": "booked", // possible values of `booked`, `edited`, `canceled`
  "appointment": {
    "id": "123", // Unique ID to reference this appointment
    "appointment_type_id": "36", // Unique value that is consistent even if the type's name/slug changes
    "appointment_type_slug": "2hr-call",
    "customer_id": "1",
    "customer_information": {
      "Name": "Nathan Tyler",
      "Email": "[email protected]"
      // values from your custom fields will also be included here
    },
    "post_information": [],
    "customer_timezone": "Asia/Beirut",
    "start_date": "2018-09-20 16:15:00", // all dates are stored in the UTC timezone
    "end_date": "2018-09-20 18:15:00",
    "status": "booked", // possible values of `booked` or `canceled`
    "date_created": "2018-09-19 01:00:44",
    "date_modified": "2018-09-19 01:00:44",
    "public_edit_url": "http://yoursite.com/appointments/change/e7b9a0a37d18e86ef11b2da12345678900",
    "price_full": 100.00,
    "payment_method": "stripe",
    "web_meeting_url": "https://your-web-meeting-url.com/url/j.php?MTID=m89e2d3199fc229a01732c0964bf48c03",
    "web_meeting_password": "your-meeting-password",
    "appointment_type_title": "2hr Call",
    "local_time_for": {
      "appointment_type": {
        "raw": {
          "start_date": "2023-10-10 10:00:00",
          "end_date": "2023-10-10 11:00:00",
          "date_created": "2023-10-04 22:04:42",
          "date_modified": "2023-10-04 22:04:44"
        },
        "raw_parts": {
          "start_date": {
            "date": "2023-10-10",
            "time": "10:00:00",
            "timezone": "Asia/Beirut",
            "timezone_offset": "+0300"
          },
          "end_date": {
            "date": "2023-10-10",
            "time": "11:00:00",
            "timezone": "Asia/Beirut",
            "timezone_offset": "+0300"
          },
          "date_created": {
            "date": "2023-10-04",
            "time": "22:04:42",
            "timezone": "Asia/Beirut",
            "timezone_offset": "+0300"
          },
          "date_modified": {
            "date": "2023-10-04",
            "time": "22:04:44",
            "timezone": "Asia/Beirut",
            "timezone_offset": "+0300"
          }
        },
        "formatted": {
          "start_date": "October 10, 2023 10:00 am EEST",
          "end_date": "October 10, 2023 11:00 am EEST",
          "date_created": "October 4, 2023 10:04 pm EEST",
          "date_modified": "October 4, 2023 10:04 pm EEST"
        },
        "formatted_parts": {
          "start_date": {
            "date": "October 10, 2023",
            "time": "10:00 am",
            "timezone": "EEST"
          },
          "end_date": {
            "date": "October 10, 2023",
            "time": "11:00 am",
            "timezone": "EEST"
          },
          "date_created": {
            "date": "October 4, 2023",
            "time": "10:04 pm",
            "timezone": "EEST"
          },
          "date_modified": {
            "date": "October 4, 2023",
            "time": "10:04 pm",
            "timezone": "EEST"
          }
        }
      }
    }
  },
  "team_members": [
    {
      "id": 1,
      "wp_user_id": "2",
      "name": "John",
      "display_name": "John",
      "email": "[email protected]"
    }
  ],
  "meta": [],
  "signature": {
    "token": "1a2b3c4d5e6f..."  // so you can verify that the delivered webhook originated from this site
    "site_name": "This WordPress Site"  // in case you have multiple sites sharing the same webhook
    "home_url": "https://thissite'shome.com"  // the homepage URL for your website
    "site_url": "https://thissite.com"  //  in case you have multiple sites sharing the same webhook
    "network_site_url": "1a2b3c4d5e6f..."  // only different than `site_url` if using multisite
  }
}`

#### Appointments Tab for Member Dashboards

#### MemberPress FAQ

#### Let Employees Manage Admin Page
