# The APML v0.6 Specification

## Contributors

### Concept

Ashley Angell, Chris Saad

### Editors

Ashley Angell, Chris Saad, Stephen Kelly, Paul Jones, Nik Seirlis

### Authors

Ashley Angell, Chris Saad, Paul Jones

### Additional Contribution

{link to page}

## Copyright

This specification is offered by the Faraday Media and the APML Workgroup under the terms of the Attribution/Share Alike Creative Commons [licence](http://creativecommons.org/licenses/by-sa/3.0/). At the appropriate time it will be submitted to a standards body for liberal licensing. Anyone contributing to this document should understand that their work will be distributed in this manner.

## Acknowledgements

Thanks to:

* Nik Seirlis for his invaluable advice and assitance
* Martin Wells ([Tangler](http://www.tangler.com/)) for his valuable advice and assistance
* Michael McNeil for his awesome work with the first APML Handler Library
* Marjolein Hoekstra ([CleverClogs](http://www.cleverclogs.org/))

## Introduction

Attention Profiling Markup Language (APML) is an open standard that encapsulates a summary of your interests (across multiple profiles) in a simple, portable way.

### Problem Statement

Attention Data comes in many forms. These include specifically designed, high-resolution file formats such as Attention.XML or more familiar forms of user data storage such as IM chat logs, browser history and cache, email inboxes, documents, OPML etc.

In some usage scenarios, however, it is necessary to analyze all available Attention Data to determine an Attention Profile - a compressed, portable and open-standard description of one’s ranked personal interests.

A portable Attention Profile would allow a user to own (and optionally submit) a meta view of their interests to create instant relationships with “attention aware” products and services. This creates an instantly customized user experience.

### Known Exclusions

For this version of the spec we have left out:

* Types - Types might include Books, Events, People, Movies etc.
* Microformats - It has been suggested that Microformats might also be included in some way
* Probably a few other things - let us know what you think!

We believe that while it may be important to describe interests as they relate to specific types (perhaps using Microformats as a basis), we feel the specific nature of types support might be better left for:

1. Community discussion before inclusion.
1. A second version of this specification (in keeping with the ‘less is better’ philosophy).

We shall leave it up to the community to help make this decision.

## Definitions Of Elements

There are consistently questions raised about the meanings of various Elements found in an APML document. Particularly about when the "updated" and "from" attributes should be added. Here are some brief descriptions.

**Explicit data** is for items that are explicitly added by a user to represent something. So for example, a user could edit their own APML file and add items they know they're interested in. That's why the updated tag isn't needed on items in ExplicitData, because it's a manual process.

Whereas with **Implicit data**, it is added by machines/computers that try to make some informed guesses about the things that you are interested in. This stuff will change over time and are added with a certain degree of confidence that may have a decay in certain applications. That's why it is important to keep a track of when things were added/modified.

Concepts mean "ideas" basically. General "things" you may be interested in. Sources are specific sources of information that you are interested in. Like a particular website or rss feed or something. Authors can be authors of a source, or just plain old authors. It is worth noting that the idea of an author/people is under review for APML Version 1.0, please see v1_agenda.

## Discovery

The APML document representing a particular page (or blog/feed) can be found in the header of the page. It is represented by a html element that looks like this:

```HTML
<link rel="meta" type="application/xml+apml" title="APML 0.6" href="http://apml.pbwiki.com/apml"/>
```

This will allow APML aware browsers and tools to find the APML document representing a page.

## HTTP Content Type Header

`Content-Type: application/xml+apml`

## Format

APML is an XML file that contains an outline of Implicit and Explicit interests, Source and Author Rankings by Profile. See `apml.xml` for example.

## Format Schema

The XML Schema for APML is defined in `apml.xsd`
