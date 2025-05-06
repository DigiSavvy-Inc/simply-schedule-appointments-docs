# Guides Ssa Appointment Customer Information Edited


*Source: [https://simplyscheduleappointments.com/guides/ssa-appointment-customer-information-edited/](https://simplyscheduleappointments.com/guides/ssa-appointment-customer-information-edited/)*

- Basic Edition
- Plus Edition
- Pro Edition
- Business Edition

WordPress Hook that fires once there is a change to the customer information of a booked appointment. The key it’s watching iscustomer_information.

`customer_information`

#### Placement

This code should be placed in your custom plugin file.

#### Source Code

This action is located in theSSA_Hooks::maybe_do_appointment_customer_information_edited_hook()function inclass-hooks.php.

`SSA_Hooks::maybe_do_appointment_customer_information_edited_hook()`

### Usage for ssa/appointment/customer_information_edited

```
add_action('ssa/appointment/customer_information_edited', 'new_function_name', 10, 4);
```

`add_action('ssa/appointment/customer_information_edited', 'new_function_name', 10, 4);`

### Parameters

- $appointment_id intThe ID of the appointment where customer information changed.

`$appointment_id int`

- $data_after arrayThe data of the booked appointment after customer information changed, which includes several keys as discussed inssa/appointment/booked.

`$data_after array`

- $data_before arrayThe data of the booked appointment before the customer information changed, which includes several keys as discussed inssa/appointment/booked.

`$data_before array`

- $responseThe response of editing customer information for the appointment.

`$response `

### Example – Show an Alert when the Customer Information is Edited

```
add_action('ssa/appointment/customer_information_edited', 'alert_customer_info_edited', 10, 4);

function alert_customer_info_edited($appointment_id, $data_after, $data_before, $response)
{
    echo "The customer information of the appointment with ID: $appointment_id has changed.";
}
```

`add_action('ssa/appointment/customer_information_edited', 'alert_customer_info_edited', 10, 4);

function alert_customer_info_edited($appointment_id, $data_after, $data_before, $response)
{
    echo "The customer information of the appointment with ID: $appointment_id has changed.";
}`

#### Appointments Tab for Member Dashboards

#### ssa/appointments/customer_information/get_defaults Filter

#### ssa/templates/get_template_vars Filter
