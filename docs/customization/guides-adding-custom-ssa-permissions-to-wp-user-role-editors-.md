# Guides Adding Custom Ssa Permissions To Wp User Role Editors


*Source: [https://simplyscheduleappointments.com/guides/adding-custom-ssa-permissions-to-wp-user-role-editors/](https://simplyscheduleappointments.com/guides/adding-custom-ssa-permissions-to-wp-user-role-editors/)*

- Basic Edition
- Plus Edition
- Pro Edition
- Business Edition

At the moment, we only integrate with theMembers plugin for easy permission management of the SSA plugin.But, if you’re already using another User Role Editors plugin, we want to share with you the custom permissions you’re able to add.

If you need help adding the custom permissions, you’ll need to contact the User Role Editors’ support team.

### Custom Permissions for User Role Editor

#### Manage Appointments:

Allow access and editing permissions to the Appointments tab.

```
ssa_manage_appointments
```

`ssa_manage_appointments`

AND

```
ssa_manage_others_appointments
```

`ssa_manage_others_appointments`

#### Manage Appointment Types:

Allow access and editing permissions to the Appointment Types tab.

```
ssa_manage_appointment_types
```

`ssa_manage_appointment_types`

#### Manage SSA Settings

Allow access and editing permissions to the Settings tab. For example, Notifications, Blackout Dates for the whole plugin, Google Calendar, etc.

```
ssa_manage_site_settings
```

`ssa_manage_site_settings`

#### Manage Staff Members

Allow access and editing permissions to the Team/Staff settings. Create or edit staff, change their permissions.

```
ssa_manage_staff
```

`ssa_manage_staff`

#### Manage Staff Blackout Dates

Allow access and editing permissions to the Team/Staff blackout dates.

```
ssa_manage_staff_blackout_dates
```

`ssa_manage_staff_blackout_dates`

### Custom Permissions Code Example

Toaddcustom permissions to theContributoruser role, you can use the following code snippet. Simply add it to your activetheme’sfunctions.phpfile:

`functions.php`

```
function add_custom_permissions_to_contributor() {
    // Get the "Contributor" role
    $role = get_role('contributor');
    
    // Add custom capabilities to the "Contributor" role
    if ($role) {
        $role->add_cap('ssa_manage_appointments');
        $role->add_cap('ssa_manage_others_appointments');
        $role->add_cap('ssa_manage_appointment_types');
        $role->add_cap('ssa_manage_site_settings');
        $role->add_cap('ssa_manage_staff');
        $role->add_cap('ssa_manage_staff_blackout_dates');
    }
}

// Hook the function into WordPress
add_action('admin_init', 'add_custom_permissions_to_contributor');
```

`function add_custom_permissions_to_contributor() {
    // Get the "Contributor" role
    $role = get_role('contributor');
    
    // Add custom capabilities to the "Contributor" role
    if ($role) {
        $role->add_cap('ssa_manage_appointments');
        $role->add_cap('ssa_manage_others_appointments');
        $role->add_cap('ssa_manage_appointment_types');
        $role->add_cap('ssa_manage_site_settings');
        $role->add_cap('ssa_manage_staff');
        $role->add_cap('ssa_manage_staff_blackout_dates');
    }
}

// Hook the function into WordPress
add_action('admin_init', 'add_custom_permissions_to_contributor');`

Please note that our support team cannot help further customize these code examples as they falloutside of our scope of service.

#### Uninstalling the Plugin

#### Migrate Using Import and Export

#### Allow Hidden Fields from Gravity Forms
