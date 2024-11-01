BigBlueButton Extension - BN URL
=======================
* Copyright: Blindside Networks Inc
* License:  GNU GENERAL PUBLIC LICENSE Version 3

Overview
===========
The BN URL subplugin enhances the BigBlueButtonBN module by passing additional data to BigBlueButton through the URL. This data can be sent when a BigBlueButtonBN session is created, joined or both. Custom defined values or data from user, course and activity module entities can be included.

Features
===========
* **Add new parameters to URLs:** Pass extra data from Moodle to BigBlueButton using action URLs.
* **Manage information that can be sent to BigBlueButton:** Control what Moodle data can be used as a parameter.

Installation
============
Prerequisites
------------
* Moodle environment with BigBlueButtonBN module installed.

Git installation
------------
1. Clone the repository:

`git clone https://github.com/blindsidenetworks-ps/moodle-bbbext_bnurl.git`

2. Rename the downloaded directory:

`mv moodle-bbbext_bnurl bnurl`

3. Move the folder to the Moodle BigBlueButtonBN extensions directory:

`mv bnurl /var/www/html/moodle/mod/bigbluebuttonbn/extension/`

4. Run the Moodle upgrade script:

`sudo /usr/bin/php /var/www/html/moodle/admin/cli/upgrade.php`

Manual installation
------------
1. Download the sub plugin zip file and extract it.
2. Place the extracted folder into `mod/bigbluebuttonbn/extension/`
3. Rename the folder `bnurl`
4. Access Moodle's Admin UI at `Site administration > Plugins > Install plugins` to complete the installation.

Configuration
============
Access the subplugin configuration under
`Site Administration > Plugins > BigBlueButton > Manage BigBlueButton extension plugins`

Here, admins can enable/disable the subplugin, manage settings, or uninstall it.


Usage
============
Creating New Parameters
------------
From the BigBlueButton activity settings under the “Extra parameters” section, use the “Add a new parameter” button. For each parameter, a name and value must be entered in the corresponding text fields. Configure when to pass the parameter from the list of options (e.g. pass on Create, Join or both action URLs).

Passing Custom Parameters and Meta parameters
------------
Meta parameters follow the notation `meta_KEY=VALUE`. To pass meta parameters, the `KEY` must be anything that can be a parameter in a standard URL, such as the following:
* `meta_paramname=paramvalue`

For custom parameters, the following example format is supported:
* `paramname=paramvalue`

Configuring Moodle Data as Parameters
------------
Moodle data can be used for parameter values, provided the Site Administrator has selected the relevant category in the subplugin settings (see Manage information that can be used as a parameter). To use this data, select the desired information from the dropdown list when setting the value in the activity settings.

Managing Information Used as a Parameter
------------
From the subplugin settings, Site Administrators can select data available as parameter values.
The available categories are:
* **Activity Information:** Details about the BigBlueButton activity such as name and activity ID.
* **Course Information:** Overall course structure and content.
* **Basic User Information:** User details, such as name and email address.

Troubleshooting
============
* **Parameters missing when passed:** The subplugin supports parameter names that BigBlueButton accepts, which must conform to the pattern `[a-zA-Z][a-zA-Z0-9-]*$` Note that parameter names containing uppercase will be converted to lowercase by BigBlueButton.


Requirements
============
Requires BigBlueButtonBN module version > 2022112802

For more detailed updates and support, visit the [BN URL Subplugin GitHub Repository](https://github.com/blindsidenetworks-ps/moodle-bbbext_bnurl)
