---
sidebar_position: 2
---

# Configuration

The `detail.conf` file configures the behavior of detail pages for various record types (e.g., objects, entities, occurrences, places, collections) in the system. 

| Option                      | Explanation                              | Example                                                  |
|-----------------------------|------------------------------------------|----------------------------------------------------------|
| `allow_ca_objects_representation_download` | Controls who can download object representations. Accepted values: `anyone`, `logged_in`, `logged_in_privileged`. | `allow_ca_objects_representation_download = anyone`                                                        |
| `displayName`       | The user-friendly label for the record type.         | `displayName = _(Objects)` |
| `table`             | Specifies the database table for the record type     | `table = ca_objects`       |
| `restrictToTypes`   | Restricts detail pages to specific types within the record type.   | `restrictToTypes = [a, b]` |
| `nextLink`          | Template for the "Next" navigation link.             | `nextLink = Next <i class='bi bi-chevron-right'></i>`  |
| `previousLink`      | Template for the "Previous" navigation link.         | `previousLink = <i class='bi bi-chevron-left'></i> Previous`   |
| `resultsLink`       | Template for the "Back" navigation link.  | `resultsLink = <i class='bi-chevron-double-up'></i> Back`   |
| `detailNavLinkClass`| CSS classes for styling navigation links.                | `detailNavLinkClass = btn btn-sm btn-white ps-3 pe-0 fw-medium`   |
| `enableComments`    | Enables or disables comments on detail pages.            | `enableComments = 1`       |
| `enablePDF`         | Enables or disables PDF export for the record type.      | `enablePDF = 1`  |
| `enableInquire`     | Enables or disables the "Inquire" button for sending inquiries.  | `enableInquire = 1`    |
| `enableCopyLink`    | Enables or disables the "Copy Link" button.              | `enableCopyLink = 1`   |
| `mediaCaptionTemplate` | Template for captions displayed in the media viewer.  | `<div class='small text-center'>^ca_object_representations.preferred_labels.name</div>`   |
| `allowMediaDownload`   | Enables or disables the ability to download media.    | `allowMediaDownload = 1`               |
| `requireLoginForMediaDownload` | Requires login to download media.             | `requireLoginForMediaDownload = 1`    |
| `mapAttributes`        | List of attributes used for mapping in detail pages.  | `mapAttributes = [ca_objects.georeference]`    |
| `mapZoomLevel`         | Default zoom level for maps.                          | `mapZoomLevel = 15`             |
| `mapMinZoomLevel`      | Minimum zoom level allowed for maps.                  | `mapMinZoomLevel = 1`           |
| `mapMaxZoomLevel`      | Maximum zoom level allowed for maps.                  | `mapMaxZoomLevel = 18`       |
| `mapItemInfoTemplate`  | Template for the item information displayed on the map. | `<div class='fw-medium fs-5'>^ca_objects.preferred_labels.name, ^ca_objects.idno</div>`   |
| `pdfExportTitle`       | Customizes the title of exported PDFs.                | `pdfExportTitle = ^ca_objects.preferred_labels.name`       |

