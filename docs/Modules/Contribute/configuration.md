---
sidebar_position: 2
---

# Configuration

This section describes the configuration options for the Contribute feature.

## General settings

These settings control general availability and behaviors of Contribute forms:

| Option                      | Explanation                                 | Example         |
|-----------------------------|---------------------------------------------|-----------------|
| `enabled` | Sets if contribute forms are available or not. Set to non-zero value to enable. | `1`      |
| `admin_notification_email`   | Email address to send notifications to when form is submitted.   | `info@collectiveaccess.org`    |
| `completed_status` | A list of status codes indicating form has been submitted by user. Status codes are identifiers for list items in the `submission_statuses` list.  Submissions assigned any of these statuses will no longer be editable. | `[accepted, rejected, under_review]`|
| `initial_status` | Status given to newly submitted records. Must be present as an identifier in the `submission_statuses` list| `submitted` |
| `introduction_global_value` | Global value used for introduction text on Contribute landing page| | 
| `<table>_id_numbering_plugin` | ID numbering plugin to use for records in a given table. Set to `MultipartIDNumber` unless custom numbering systems are being employed.  You must set this for every table targeted by the Contribute form. | `MultipartIDNumber`|

## Form configuration

The `formTypes` dictionary setting contains definitions for all Contribute forms. Each key in the dictionary is a unique identifier for a form. Values are dictionaries with settings for the form. Settings include:

| Option                     | Explanation                                       | Example                                                                                 |
|----------------------------|---------------------------------------------------|-----------------------------------------------------------------------------------------|
| `table` |  Table of created record  | `ca_objects`                         |
| `type` |  Type of created record. Type code must be valid for `table` | `artwork`                         |
| `formTitle`     | Title of form, for display to user       | `Artefact submission form`                   |
| `shortNameSingular` | Singular name of item submitted by form. | `artefact`                                   
| `shortNameSingular` | Plural name of item submitted by form. | `artefacts`            |  
| `showInUserSubmissionList` | Show form as option for user. Set to a non-zero value to hide navgiation to form from users. | `0`            |                 
| `alwaysUseLocale` | Force local of fields in created record to a specific locale. Locale must be configured for the system. | `en_US`            |                 
| `access` | Access value to set on newly submitted records. Usually set to non-public value (eg `0`) to ensure they are not seen until approved. | `0`            |                
| `status` | Status value to set on newly submitted records. | `0`            |
| `idno` | Template for idno. Use "%" as placeholder for serial numbers in SERIAL numbering formats. | `2025.%`            |                   
| `form_view` | Path to view to use for form, relative to root of theme `views` directory. | `Contribute/artefact_form_html.php`            |        
| `require_login` | Require user to be logged in to use form? Set to a non-zero value to require login, or zero to allow anonymous submissions. | `0`            |        
| `spam_protection` | TODO. Currently not functional. Add captcha to form to mitigate spam/bot abuse? Set to non-zero value to enable. Google Recaptcha keys must be set in `setup.php`. | `1`            |        
| `terms_and_conditions` | TODO. Currently not functional. Require use to confirm acceptance of terms and conditions statement prior to submission? | `0`            |        
| `representation_type` | Type of representation created when media is uploaded in the form. Muse be a valid type code for object representations. | `media`            |        
| `representation_access` | Access value to set on newly submitted media. Usually set to non-public value (eg `0`) to ensure media is not seen until approved. | `0`            |        
| `representation_status` | Status value to set on newly submitted media. | `0`            |        
| `text_delimiters` | Per-field dictionary of delimiters used to break form text into repeating values in the created record. Keys are field codes without table (form table is assumed). Value is a list of delimiters. | `{keywords = [",", ";", "/"]}`            |
| `post_submission_destination` | Where we put the user after a successful form submission. Possible values are:  `front` (redirect to Pawtucket front page), `url` (redirect to Pawtucket url specified in `post_submission_destination_url` setting), `page` (use view specified by `post_submission_view `to format direct response (no redirect).| `page`            |        
| `post_submission_view` | Name of view to use for post submission message. Should be full file name of view with .php extension; assumed to be in theme views/contribute directory. | `Contribute/results_html.php`            |        
| `post_submission_destination_url` | Module/controller/action settings to generate url for page to show post-submission. | `{ module =, controller = Contribute, action = Index }`            |        
| `set_post_submission_notification` | Set notification banner on form submission. Set to a non-zero value to show banner. | `0`            |        
| `post_submission_notification_message` | Message shown to user after successful form submission, when form does not include media. | `Thank you for your submission!`            |        
| `post_submission_notification_message_with_media` | Message shown to user after successful form submission, when form includes media. | `Thank you for your submission! Your media has been successfully added to the archive for review.`            |        
| `related` | Dictionary of relationships supported by the form, and initial values for any newly created related record. Keys are table names. Values are dictionaries specifying default identifier format, access and status values for newly created related records. | ```{ca_entities = { idno = %, access = 1, status = 0 }}```            |        
| `required` | List of form fields to require values for. Errors will be returned if the field is left blank. Fields should be in `table`.`field` format. | `[ca_objects.repository, ca_objects.accession_num, ca_objects.preferred_labels.name]`            |        

## Example

An example `contribute.conf` file:

```plaintext
enabled = 1

admin_notification_email = info@collectiveaccess.org
completed_status = [accepted, rejected, under_review]
initial_status = submitted

introduction_global_value = contribute_introduction

formTypes = {
	inventory = {
		# table of created record
		table = ca_occurrences,
		
		formTitle = Artefact Inventory Contribution,
		shortNameSingular = artefact inventory,
		shortNamePlural = artefact inventories,
		
		showInUserSubmissionList = 1,
		
		alwaysUseLocale = en_CA,
		
		# type of created record
		type = contribution,
		
		access = 0,
		status = 0,
		
		# template for idno; use "%" as placeholder for serial numbers
		idno = BHH.%,
		
		# view to use to render form
		form_view = Contribute/inventory_form_html.php,
		
		errorFormat = <div class='error' style='color: #cc0000; font-weight: bold;'>^ERRORS</div>,
		
		# require user to be logged in?
		require_login = 1,
		
		# Set to 1 if you want on-screen SPAM prevention (in the form of a simple/quick math question)
		spam_protection = 0,
		
		# Set to 1 if you want an on-screen click-through agreement on the form
		terms_and_conditions = 0,
		
		representation_type = media,
		representation_status = 0,
		representation_access = 0,
		
		text_delimiters = {
		    keywords = [",", ";", "/"]
		},
		
		# Where we put the user after a successful form submission
		# Values are:
		#		front = 	redirect to Pawtucket front page
		#		url = 		redirect to Pawtucket url specified in post_submission_destination_url directive
		#		page = 		use view specified by post_submission_view to format direct response (no redirect).
		#						The view should be in the theme's views/contribute directory.
		post_submission_destination = url,
		
		# Name of view to use for post submission message. Should be full file name of view with .php extension; assumed to be in theme views/contribute directory
		post_submission_view = Contribute/results_html.php,
		
		# Module/controller/action settings to generate url for page to show post-submission
		post_submission_destination_url = { module =, controller = Contribute, action = Index },
		
		set_post_submission_notification = 1,
		post_submission_notification_message = _(Thank you for your submission!),
		post_submission_notification_message_with_media = _(Thank you for your submission! Your media has been successfully added to the archive for review.),
	
	    related = {
            ca_entities = {
                idno = %,
                access = 1,
                status = 0
            },
            ca_places = {
                idno = %,
                access = 1,
                status = 0
            },
            ca_occurrences = {
                idno = %,
                access = 1,
                status = 0
            }
        },
        
        required = {
        	ca_occurrences.repository, ca_occurrences.submitted_data, ca_occurrences.submitted_media
        }
	}
	
}


#
# Name of plugin class to use for id number field in objects, object lots
# and authorities that support id numbering (entities, places, collections and occurrences)
#
ca_objects_id_numbering_plugin = MultipartIDNumber
ca_object_lots_id_numbering_plugin = MultipartIDNumber
ca_entities_id_numbering_plugin = MultipartIDNumber
ca_places_id_numbering_plugin = MultipartIDNumber
ca_collections_id_numbering_plugin = MultipartIDNumber
ca_occurrences_id_numbering_plugin = MultipartIDNumber
ca_list_items_id_numbering_plugin = MultipartIDNumber
ca_loans_id_numbering_plugin = MultipartIDNumber
ca_movements_id_numbering_plugin = MultipartIDNumber
ca_tours_id_numbering_plugin = MultipartIDNumber
ca_tour_stops_id_numbering_plugin = MultipartIDNumber
ca_object_representations_id_numbering_plugin = MultipartIDNumber
ca_storage_locations_id_numbering_plugin = MultipartIDNumber

```
