---
sidebar_position: 2
---

# Configuration

This section describes the configuration options for the Browse section.

## General Browse Options

| Option Name   | Explanation  | Example  |
| ------------- | --- | --- |
| `cache_timeout` | Set to the number of seconds the browse cache should persist.  Set to 0 to disable caching | `360` |
| `generalSearchTargets` | Set to the keys of the BrowseTypes configuration to include in general search (search across all record types often linked to in navbar). This also controls the order blocks of results appear in general search. |	`[collections, entities, occurrences, objects]` |
| `browse_menu_button_text` | Text for Browse menu item in nav bar, default when left blank is "Browse".  | `Find` |
| `defaultHitsPerBlock` | Number of results to load per page/ajax load | `36` |

## Views Icons

Options for supported results views.  Supported views are images, list, and map.  icon option defines the class name of icon to use in view button at top of results

```plaintext 
views = {
	images = {
		icon = bi-grid-fill
	},
	list = {
		icon = bi-list-task
	},
	map = {
		icon = bi-globe
	}
}
```


## Configuring different browse targets

The `browseTypes` object is used to configure each browse target for the site.  Keys in `browseTypes` coorespond to the URL used to load the browse.  For example, the key 'objects' would coorespond to /Browse/objects.  

Example configuration for an objects browse:

```plaintext
browseTypes = {
	objects = {
		displayName = _(Objects),
		labelSingular = _("object"),
 		labelPlural = _("objects"),
		table = ca_objects,
		restrictToTypes = [],
		dontShowInBrowseMenu = 0, # --- set to true or 1 to hide in main site navigation leave empty or 0 to display in menu
		
		#dontShowChildren = 1,
		#dontExpandTypesHierarchically = true,
		availableFacets = [],
		
		# formats available for display of results
		# possible values are: images, list, map
		views = {
			images = {
				result_caption = "<div class='card-title'><small class='text-body-secondary'>^ca_objects.idno</small><div class='fw-medium lh-sm fs-5'><l>^ca_objects.preferred_labels</l></div></div><ifdef code='ca_objects.work_description'><p class='card-text small lh-sm text-truncate'>^ca_objects.work_description</p></ifdef>",
				image_format = cover, # --- contain or cover - default is cover
			},
			list = {
				result_caption = "<div class='card-title'><small class='text-body-secondary'>^ca_objects.idno</small><div class='fw-medium lh-sm fs-5'><l>^ca_objects.preferred_labels</l></div></div><ifdef code='ca_objects.work_description'><p class='card-text small lh-sm text-truncate'>^ca_objects.work_description</p></ifdef>",
				image_format = contain, # --- contain or cover - default is cover
				list_format = image, # --- image or text where text is a simple grid of cards with no media
			},
			map = {
				data = ca_objects.georeference,
				width = 100%,
				height = 600px,
				minZoomLevel = 2,
				maxZoomLevel = 18,
				display = {
					labelTemplate = <l>^ca_objects.preferred_labels.name</l> (^ca_objects.idno),
					contentTemplate = <div style='float:left; margin:0px 10px 10px 0px;'>^ca_object_representations.media.icon</div><p>^ca_objects.description</p>
				}
			}
		},
		sortBy = {
			Identifier = ca_objects.idno,
			Title = ca_object_labels.name
		},
		# --- default sort direction for the sortBy options
		sortDirection = {
			Identifier = asc,
			Title = desc
		},
#		options = {
#			selectMediaUsingRelationshipTypes = [relationshipType],
#			selectMediaUsingTypes = [objectType],
#			extendedInformationTemplate = ^ca_objects.description
#		},
		generalSearchOptions = {
			resultCaption = "<div class='card-title'><small class='text-body-secondary'>^ca_objects.idno</small><div class='fw-medium lh-sm fs-5'><l>^ca_objects.preferred_labels</l></div></div><ifdef code='ca_objects.work_description'><p class='card-text small lh-sm text-truncate'>^ca_objects.work_description</p></ifdef>",
			searchView = general_image_results_html.php,
			imageFormat = cover, # --- contain or cover - default is cover
			numItemsToShow = 8,
			sortBy = _natural,
			sortDirection = asc,
		}
		
	}
}
```