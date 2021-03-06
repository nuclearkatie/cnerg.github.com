# Data files used to populate CNERG Web Pages

The CNERG web pages are built by processing template files using to incorporate
data.  Each of the templates has a slightly different expectation of the data it
will use.

## Menu data

### Navbar data

The `navbar` data populates the primary navigation menu.  This data file
consists of a list of entries, each of which is a dictionary containing:
* `title` => text to be rendered in menu
* `url` => link destination if there is no submenu
* `subcategories` => a list of dictionaries for submenu items, each of which
  contains:
    * `subtitle` => text to be rendered in submenu
    * one of:
        * `exturl` => external URL destination of menu entry
        * `target` => browser window target (often `_blank` for new tab)
    * or:
        * `suburl` => internal link target of menu entry

### UW Navbar data

The `uw_navbar` data populates the top-of-screen menu to link to other UW sites.
It contains a list of dictionaries, with each entry containing:
* `name` => hyperlink text
* `url` => link destination

## Content data

### Description list data

These data files are rendered by the `desc_list.html` template to generate lists
for which each item has a description and a list of hyperlinks. A specific data
file can be selected in this template by setting the `data` variable of the page
data. The data file should have a list of entries, each being a dictionary with:
* `title` => text to render as title
* `desc`=> text to render as description
* `links` => list of dictionaries each with:
    * `url` => URL of link
    * `text` => text of hyperlink

Data files in this format include:
* events
* tasks_roles
* tools
* resources
* skills
* guides

Examples include the [Community Events](community/events.md), and many of the
lists of resources in the manual.

### Presentation data

These data files contain information that can be used to provide a list of
presentations, appearances, or outreach publications, including hyperlinks.

The data is a list of dictionaries, each consisting of:
* `date` => date to be rendered as text
* `title` => title of presentation
* `url` => link to presentation materials (e.g. published google slides)
* `venue` => the event, location, publication
* `venue_url` => URL to the venue if available
* `person` => name of individual who appeared/presented
* `person_dir` => CNERG personnel directory

Data files in this format include:
* outreach

Note: this could be replaced by a Zotero-generated file in the future

### People data

These data files contain lists of individuals organized into groups.  The data
is a list of dictionaries, each consisting of:
* `group` => the name of the group to be rendered as a heading
* `people` => a list of dictionaries containing data for each individual:
    * `name` => preferred name
    * `url` => directory name of person's data
    * `image` => image file to be used for that person
    * `role` => description of role to be included in list

This data is rendered into a grid of photos and text info, each linked to the
individual's home page.

Data files in this format include:
* people

### URL data

The `urls` file is a list of urls to be used throughout the site and changed in a single location.

## Zotero-generated data

Some data is generated by dumping JSON files from Zotero.  These files contain a
format defined by Zotero.