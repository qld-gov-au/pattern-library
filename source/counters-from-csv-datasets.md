# Counters from CSV datasets

New [map patterns](https://govdex.gov.au/confluence/display/SSQSWE/Maps) are now available.

Pages hosted on www.qld.gov.au may include a dynamic, searchable list of counters.
Counters are presented as search results, as specified in the CUE: [Search results presentation](http://www.qld.gov.au/web/cue/module5/)

Each result follows the contact details pattern.

The dataset for counters is to be a CSV file published and maintained by a franchise.

The file should be stored in your `assets/data` folder and named for the type of counter, example: `/law/assets/data/courthouses.csv`
- [Page models](#page-models)
	- [Search results page](#search-results-page)
    - [Counter details page](#counter-details-page)
- [Testing](#testing)
- [Configuration](#configuration)
	- [CSV format](#csv-format)
    	- [Notes on operating hours](#notes-on-operating-hours)
    - [Search parameters](#search-parameters)
    	- [Supported datasets](#supported-datasets)
        - [Sort order](#sort-order)
        - [Pagination](#pagination)
- [Examples](#examples)

## Page models
[Sample CSV, html and include files (ZIP, 33KB)](https://govdex.gov.au/confluence/download/attachments/231310668/counters.zip?version=2&modificationDate=1352855537341&api=v2)

### Search results page
- Page title
- Interactive map of all counters
- Location search options
- Counter listings (contact details)
- Asides [OPTIONAL]

### Counter details page
Each counter will be linked to a dedicated page presenting just that counter.

This is optimised for search engines, so customers can come directly to the counter they are looking for.

This page is almost entirely dynamic, but can be configured with SSI variables (see sample files) to customise the metadata, breadcrumb and heading shown on the section navigation.

Automated metadata is added where possible (including title, geospatial coverage and modified date).

## Testing
You can test your CSV data using this tool: http://toolbox.ssq.qld.gov.au/csv-qa/

To learn how to use the CSV QA tool you can download the user manual: [CSV quality control tool user manual version 1.0.docx](https://govdex.gov.au/confluence/download/attachments/231310668/CSV%20quality%20control%20tool%20user%20manual%20version%201.0.docx?version=1&modificationDate=1376954528469&api=v2)

## Configuration
The server-side include **must** specify a dataset. Optional search parameters are supported and may be hardcoded into the page.

If a search form is provided, the parameters will be passed as a query string.

### CSV format
The CSV file must contain the following columns.

The first row must contain these exact column headings.

Column | Description | Format | Required
------ | ----------- | ------ | --------
**Title** | Name of the counter/business/building | Text (must be unique within the CSV file) | Required
**Description** | Description of the counter (used in metadata only) | Text (not HTML) | Required
**Address 1** | Street address (line 1) | Sentence case | Required
**Address 2** | Street address (line 2) | Sentence case | Required (may be blank)
**Suburb** | Town or suburb | Sentence case | Required 
**State** | *not used* | 3-letter abbreviation | Optional (Qld is assumed)
**Postcode** | Location of counter | 4-digit postcode | Required
**Postal address 1** | Postal address (line 1) | Sentence case | Required
**Postal address 2** | Postal address (line 2) | Sentence case | Required (may be blank)
**Postal suburb** | Town or suburb | UPPERCASE (Australia Post guidelines) | Required
**Postal state** | *not used* | 3-letter abbreviation | Optional (QLD is assumed)
**Postal postcode** | Postal address | 4-digit postcode | Required
**Latitude** | Event location | Signed decimal degrees [(geocoder)](http://gmaps-samples.googlecode.com/svn/trunk/geocoder/singlegeocode.html) | Required
**Longitude** | Event location | Signed decimal degrees [(geocoder)](http://gmaps-samples.googlecode.com/svn/trunk/geocoder/singlegeocode.html) | Required
**Phone** | Phone number | Phone number (follow editorial style guide), separate multiple numbers with ; (semi-colon) | Optional
**Fax** | Fax number | Phone number (follow editorial style guide) | Optional
**Email** | Email address | Email address | Optional
**~~Operating hours~~** | Do not use | Free text | Do not use (use the following columns instead)
**Mon am** | Opening hours for Monday mornings | Time (24hr format) or range | Optional (blank means counter is closed)
**Mon pm** | Opening hours for Monday afternoons | Time (24hr format) or range | Optional (blank means counter is closed) 
**Tues am** | Opening hours for Tuesday mornings | Time (24hr format) or range | Optional (blank means counter is closed) 
**Tues pm** | Opening hours for Tuesday afternoons | Time (24hr format) or range | Optional (blank means counter is closed) 
**Wed am** | Opening hours for Wednesday mornings | Time (24hr format) or range | Optional (blank means counter is closed) 
**Wed pm** | Opening hours for Wednesday afternoons | Time (24hr format) or range | Optional (blank means counter is closed) 
**Thurs am** | Opening hours for Thursday mornings | Time (24hr format) or range | Optional (blank means counter is closed) 
**Thurs pm** | Opening hours for Thursday afternoons | Time (24hr format) or range | Optional (blank means counter is closed) 
**Fri am** | Opening hours for Friday mornings | Time (24hr format) or range | Optional (blank means counter is closed) 
**Fri pm** | Opening hours for Friday afternoons | Time (24hr format) or range | Optional (blank means counter is closed) 
**Sat am** | Opening hours for Saturday mornings | Time (24hr format) or range | Optional (blank means counter is closed) 
**Sat pm** | Opening hours for Saturday afternoons | Time (24hr format) or range | Optional (blank means counter is closed) 
**Sun am** | Opening hours for Sunday mornings | Time (24hr format) or range | Optional (blank means counter is closed) 
**Sun pm** | Opening hours for Sunday afternoons | Time (24hr format) or range | Optional (blank means counter is closed) 
**Closure** | List of dates counter is closed (e.g. Christmas period) | Date ranges | Optional (blank means counter always follows normal operating hours)
**Services** | List of services offered at the counter | Text, separate multiple services with ; (semi-colon) | Optional

#### Notes on operating hours
If a counter is open all day, simply put the opening time in the `am` column for that day and the closing time in the `pm` column. Example: `8:30`, `17:00`

If a counter closes during a lunch period, specify a range in the `am` and `pm` columns. Example: `8:30-12:00`, `13:00-17:00`

If a counter is open in the morning and closed for the afternoon, put a range in the `am` column and leave the `pm` column blank. Example: `8:30-12:00`,

Specify the normal operating hours for the counter. It is assumed counters will be closed on Queensland and local public holidays. This will be managed by the Public holidays API.

Closure dates can be specified as a range. Separate multiple values with semi-colons. Example: `24/12/2012-1/1/2013`; `1/2/2013` means closed from 24 December 2012 through to 1 January 2013 (inclusive) and closed again on 1 February 2013. Only closures that are happening within the next 5 weeks will be displayed on the page.

Custom (free text) messages can be included in the closure column. Example: `after 1.30pm on 27, 28 and 31 December 2012`. Note: *custom messages will* **always be displayed** *as the script cannot reliably determine the date of the closure.*

To remove a custom message, update your CSV file.

Closure messages are displayed as text, with the lead-in phrase ‘We are closed’. Examples:

Closure data type | CSV data | Displayed as
----------------- | -------- | ------------
**Date range** | `24/12/2012-1/1/2013` | We are closed 24 December 2012--1 January 2013.
**Custom** | `after 1.30pm on 27, 28 and 31 December 2012` | We are closed after 1.30pm on 27, 28 and 31 December 2012.
**Multiple dates** | `24/12/2012-26/12/2012; 28/12/2012-1/1/2013` | We are closed 24-~~26 December 2012 and 28 December 2012~~-1 January 2013.
**Mixed** | `24/12/2012-26/12/2012; after 1.30pm on 27, 28 and 31 December 2012; 1/1/2013` | We are closed 24--26 December 2012, after 1.30pm on 27, 28 and 31 December 2012 and 1 January 2013.

Please discuss any additional requirements with the QGov Online team.

### Search parameters
A date range is always used in the search results. By default, all events that occur from today onwards are included (past events are hidden). This includes events that started before the current day and are still running.

Parameter | Description | Format | Default value
--------- | ----------- | ------ | -------------
dataset | Identifies which CSV source file to use. You must contact the QGov Online team to configure new datasets. | Text (see [supported datasets](#supported-datasets) below) | -
location | An address of a location. If specified, the nearest counters will be displayed. | A string which can be geocoded by google | -
distance | Filter results based on distance from the specified `location` | Number (km) | - (no filtering based on distance) 

#### Supported datasets
TBA

Contact the QGov Online team to add your dataset.

#### Sort order
The sort order of the CSV file is preserved.

If a location is specified, search results will be sorted by proximity (counters nearest the search location will appear first). All counters will be included unless a `distance` filter is supplied.

#### Pagination
Results are paginated as specified in the CUE: [Pagination - Search results presentation](http://www.qld.gov.au/web/cue/module5/checkpoints/checkpoint15/)

## Examples
Show community recovery centres near the location entered by the customer, but capped with a 50km radius.
```html
<!--#include virtual="/assets/includes/dynamic/counters/list.php?${QUERY_STRING}&dataset=community-recovery-centres&distance=50" -->
```
Show court houses *near a location entered by the customer*
```html
<!--#include virtual="/assets/includes/dynamic/counters/list.php?${QUERY_STRING}&dataset=courthouses" -->
```
Show all QGAP locations near Townsville
```html
<!--#include virtual="/assets/includes/dynamic/counters/list.php?${QUERY_STRING}&dataset=QGAP&location=Townsville" -->
```
Show **all** court houses

(Query string parameters are required to support pagination)
```html
<!--#include virtual="/assets/includes/dynamic/counters/list.php?${QUERY_STRING}&dataset=courthouses" -->
```
