---
sidebar_position: 3
---

# Views
Views related to the lightbox are located in your [theme]/views/Contribute directory. 

Required views include:

| View  				| Description  				| 
| --- 					| --- 						|
|  list_html.php 		| Formats Contribute landing page and submission list 	| 
|  `<form code>`_form_html.php| Each form configured in `contribute.conf` must have a corresponding view. The view will include tags for all included fields. 	|
|  result_json.php | JSON response view. Formats JSON responses for autocomplete fields. | 

## The form view

Each Contibute form must have a corresponding "_form_html.php" view defined. This view formats the form and lays out form elements. 
To include a fields from the form's table, use the standard bundle code wrapped in triple-curly-bracket. For example, for a field named "repository" in a form for occurrences:

```
{{{ca_occurrences.repository}}}
```

Options, including custom CSS classes, can be set by appending URL-style key value pairs separated from the bundle name by a "%" character:

```
{{{ca_occurrences.repository%class=form-control w-100}}}
```

To display field-specific error messages, use the bundle code followed by ":error"
```
{{{ca_occurrences.repository:error}}}
```

The form as a whole must be wrapped in `{{{form}}}` and `{{{/form}}}` tags. All form elements must be inside of this tag pair. Within the form the following control elements should
be included:

To display general form errors, set a template that uses the `^errors` tag:

```
{{{<ifdef code="errors"><div class="notificationMessage">^errors</div></ifdef>}}}
```

To display a form submit and/or reset button use the following tags:

```
{{{submit%label=Save}}}
{{{reset%label=Reset}}} 
```

## Variables for `list_html.php`

| Variable  				| Description  				| 
| --- 						| --- 						|
| submissions_by_form  | 	| 							|
| completed_status_list 	| 							|
| available_forms 	| 							|
| introduction_global_value 	| 							|

## Variables for `<form code>_form_html.php`

| Variable  				| Description  				| 
| --- 						| --- 						|
| t_subject  | 	Instance of model for form table| 							|
| form_info 	| Configuration values for current form						|

