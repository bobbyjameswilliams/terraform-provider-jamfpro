---
page_title: "jamfpro_computer_inventory_collection_settings"
description: |-
  
---

# jamfpro_computer_inventory_collection_settings (Resource)


## Example Usage
```terraform
resource "jamfpro_computer_inventory_collection_settings" "example" {
  computer_inventory_collection_preferences {
    monitor_application_usage                          = true
    include_fonts                                      = true
    include_plugins                                    = true
    include_packages                                   = true
    include_software_updates                           = true
    include_software_id                                = true
    include_accounts                                   = true
    calculate_sizes                                    = true
    include_hidden_accounts                            = true
    include_printers                                   = true
    include_services                                   = true
    collect_synced_mobile_device_info                  = true
    update_ldap_info_on_computer_inventory_submissions = true
    monitor_beacons                                    = true
    allow_changing_user_and_location                   = true
    use_unix_user_paths                                = true
    collect_unmanaged_certificates                     = true
  }

  application_paths {
    path = "/Applications/Custom/App1"
  }
  application_paths {
    path = "/Applications/Custom/App2"
  }
  application_paths {
    path = "/Applications/Adobe/Creative Cloud"
  }

  font_paths {
    path = "/Library/Fonts/Custom/Font1"
  }

  font_paths {
    path = "/Library/Fonts/Custom/Font2"
  }

  plugin_paths {
    path = "/Library/Plugins/Custom/plugin1"
  }

  plugin_paths {
    path = "/Library/Plugins/Custom/plugin2"
  }
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `computer_inventory_collection_preferences` (Block List, Min: 1, Max: 1) (see [below for nested schema](#nestedblock--computer_inventory_collection_preferences))

### Optional

- `application_paths` (Block Set) Custom paths to use for collecting applications. These paths will also be used for collecting Application Usage information (if enabled) (see [below for nested schema](#nestedblock--application_paths))
- `font_paths` (Block Set) Custom paths to use when collecting fonts. Collect names, version numbers, and paths of installed fonts (see [below for nested schema](#nestedblock--font_paths))
- `plugin_paths` (Block Set) Custom paths to use when collecting plug-ins. Collect names, version numbers, and paths of installed plug-ins (see [below for nested schema](#nestedblock--plugin_paths))
- `timeouts` (Block, Optional) (see [below for nested schema](#nestedblock--timeouts))

### Read-Only

- `id` (String) The ID of this resource.

<a id="nestedblock--computer_inventory_collection_preferences"></a>
### Nested Schema for `computer_inventory_collection_preferences`

Required:

- `allow_changing_user_and_location` (Boolean) Collect user and location information from Directory Service.
- `calculate_sizes` (Boolean) Calculate sizes of items in inventory collection.
- `collect_synced_mobile_device_info` (Boolean) Collect information about synced mobile devices.
- `collect_unmanaged_certificates` (Boolean) Collect unmanaged certificates (managed certificates are always collected).
- `include_accounts` (Boolean) Collect UIDs, usernames, full names, and home directory paths for local user accounts.
- `include_fonts` (Boolean) Include fonts in inventory collection.
- `include_hidden_accounts` (Boolean) Include hidden accounts in inventory collection.
- `include_packages` (Boolean) Include packages in inventory collection.
- `include_plugins` (Boolean) Include plugins in inventory collection.
- `include_printers` (Boolean) Include printers in inventory collection.
- `include_services` (Boolean) Include services in inventory collection.
- `include_software_id` (Boolean) Include software ID in inventory collection.
- `include_software_updates` (Boolean) Include software updates in inventory collection.
- `monitor_application_usage` (Boolean) Collect the number of minutes applications are in the foreground.
- `monitor_beacons` (Boolean) Monitor iBeacon regions and have computers submit information to Jamf Pro when they enter or exit a region.
- `update_ldap_info_on_computer_inventory_submissions` (Boolean) Update LDAP information when computer inventory is submitted.
- `use_unix_user_paths` (Boolean) Allow local administrators to use the jamf binary recon verb to change User and Location inventory information in Jamf Pro.


<a id="nestedblock--application_paths"></a>
### Nested Schema for `application_paths`

Required:

- `path` (String) Custom path to be included in inventory collection.

Read-Only:

- `id` (String) Unique ID for this inventory collection custom path.


<a id="nestedblock--font_paths"></a>
### Nested Schema for `font_paths`

Required:

- `path` (String) Custom path to be included in inventory collection.

Read-Only:

- `id` (String) Unique ID for this inventory collection custom path.


<a id="nestedblock--plugin_paths"></a>
### Nested Schema for `plugin_paths`

Required:

- `path` (String) Custom path to be included in inventory collection.

Read-Only:

- `id` (String) Unique ID for this inventory collection custom path.


<a id="nestedblock--timeouts"></a>
### Nested Schema for `timeouts`

Optional:

- `create` (String)
- `delete` (String)
- `read` (String)
- `update` (String)