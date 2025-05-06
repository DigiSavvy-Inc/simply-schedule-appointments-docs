# Guides Ssa Appointments Customer Information Get Defaults


*Source: [https://simplyscheduleappointments.com/guides/ssa-appointments-customer-information-get-defaults/](https://simplyscheduleappointments.com/guides/ssa-appointments-customer-information-get-defaults/)*

- Basic Edition
- Plus Edition
- Pro Edition
- Business Edition

WordPress filter that enables access to the customer information defaults that Simply Schedule Appointments uses to auto-fill the booking form for logged-in users.

At the moment, only theNameandEmailfields are auto-filled,but using this filter allows you to add new custom variables to auto-fill automatically in the booking form when a user is logged in.

Learn about theAuto-populate behavior for the Name and Email fieldsfor WordPress users.

#### Placement

This code should be placed in your custom plugin file.

#### Source Code

This filter is located in theSSA_Customer_Information::get_defaults()function inclass-customer-information.php.

`SSA_Customer_Information::get_defaults()`

### Usage for ssa/appointments/ customer_information/get_defaults Filter

```
add_filter(
	'ssa/appointments/customer_information/get_defaults',
	'new_function_name',
	1,
	1
);
```

`add_filter(
	'ssa/appointments/customer_information/get_defaults',
	'new_function_name',
	1,
	1
);`

### Parameters

- $defaults arrayThe variables of the customer information, which includes Name and Email as defaults.

`$defaults array`

### Example – Customize Default Customer Information

```
add_filter(
	'ssa/appointments/customer_information/get_defaults',
	'ssa_customize_customer_information_defaults',
	1,
	1
);

function ssa_customize_customer_information_defaults( $defaults ) {
	$defaults = array_merge( $defaults, array(
		// automatically populate the Address field in SSA with data from the user's profile
		'Address' => get_user_meta( get_current_user_id(), 'address', true )
	) );
	
	return $defaults;
}
```

`add_filter(
	'ssa/appointments/customer_information/get_defaults',
	'ssa_customize_customer_information_defaults',
	1,
	1
);

function ssa_customize_customer_information_defaults( $defaults ) {
	$defaults = array_merge( $defaults, array(
		// automatically populate the Address field in SSA with data from the user's profile
		'Address' => get_user_meta( get_current_user_id(), 'address', true )
	) );
	
	return $defaults;
}`

#### Appointments Tab for Member Dashboards

#### ssa/templates/get_template_vars Filter

#### ssa/forms/gravity/should_copy_field_to_ssa Filter
