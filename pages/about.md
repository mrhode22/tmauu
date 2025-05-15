---
title: About
layout: about
permalink: /about.html
# include CollectionBuilder info at bottom
credits: true
# Edit the markdown on in this file to describe your collection
# Look in _includes/feature for options to easily add features to the page
---

{% include feature/jumbotron.html objectid="tmauu033" %}

{% include feature/nav-menu.html sections="About the Collection;About Me;Challenges & Obstacles;Technical Details" %}

## About the Collection

This site is generated using [CollectionBuilder-GH](https://collectionbuilding.github.io/gh/), a project to create a free and simple digital collection using [GitHub Pages](https://pages.github.com/) from: 

- a CSV of collection metadata
- a folder of JPG images or PDF documents

The template repository features four objects from the University of Idaho Library's [Digital Collections](https://www.lib.uidaho.edu/digital). 

For full details of creating your own collection site, visit [CollectionBuilder Documentation](https://collectionbuilder.github.io/cb-docs/)!

This collection is a prototype digital library designed for Union University using resources provided by the Taubman Museum of Art and Virginia Tech.

### Taubman Museum of Art

The Taubman Museum of Art (TMA) is a visual art institution in Roanoke, Virginia. It is accredited by the American Alliance of Museums and boasts over two thousand pieces in its permanent collection. Eleven galleries host fifteen to twenty exhibitions of featured artists each year. The museum itself is housed in a work of art—an avant-garde building designed by architect Randall Stout. TMA offers all of this to its visitors at no cost for general admission.

The permanent collection at TMA includes chiefly American art from the 19th- and early 20th-centuries, modern and contemporary art, photography, design, and decorative arts, and other selections including Southern folk art. There is not enough space to showcase all of these works at once, so they are regularly rotated and highlighted, providing different experiences to frequent visitors. The exhibitions TMA hosts are wide-ranging in genre, style, and media and may focus on a particular artist, region, works from other institutions, or a number of other topics.

### Union University

Union University is a Christian liberal arts college located in Jackson, Tennessee. It offers a traditional array of liberal arts disciplines, but—most significant to this project—boasts the top-ranked Christian visual arts program in the nation. Art and Studio Art majors include ceramics, drawing, graphic design, painting, photography, pre-professional art therapy, and sculpture. Union art students (and all students completing the required Arts in Western Civilization course) will benefit from having access to TMA’s rich collections.

### Virginia Tech

TMA collaborated with Virginia Tech (VT) to digitize its many works, beginning with items on permanent display. The digital collection is hosted in VT’s digital library, providing the museum with two advantages: first, that the collection can be accessed online, and second, that the items are preserved digitally. VT worked with TMA to send a photographer to the museum and take digital images for the online collection.

## About Me

Greetings! My name is Micah Rhodes. I am a graduate student pursuing a Master's degree in Information Science from the University of Tennessee. I am also the Cataloging Associate at the library of Union University, my alma mater.

{% include feature/image.html objectid="https://www.uu.edu/employee/photos/1264838-275.jpg" width=25 %}

I took an honors course during my undergraduate studies called "Beauty" and some of my friends were art majors, so I immediately thought of building this collection for use at Union as soon as I read the project description. I selected a variety of artistic styles and mediums for my prototype collection because I thought they were representative of the kind of resource that would be useful to students and faculty in the Art Department at Union. With such a well-established program and various disciplines taught, the collection needs to contain a breadth and diversity of works. This also supports a core class required for all undergraduates: Arts in Western Civilization, a traditional liberal arts course surveying large portions of art movements throughout history. The permanent collection of the Taubman Museum of Art is primarily but not exclusively focused on American art and artists, so a digitized library of those works would support portions of that course and others.

## Challenges & Obstacles

At the beginning of this project, I was intending to use Omeka.net as my Digital Asset Management (DAM) system with Dublin Core as my metadata framework. I completed the Controlled Vocabularies and Metadata Application Profile assignments with this DAM system in mind. However, after I started to actually construct the library in Omeka.net, I quickly realized it would be difficult to get the platform to handle the functional requirements I had determined. This led me to switch to CollectionBuilder-GH as my DAM system.

Of course, this necessitated revisions to my application profile and added several controlled vocabularies or encoding schemes. I went through a lot of trial and error figuring out how to use CollectionBuilder. Early on, I moved too fast and made too many changes, breaking something in the HTML or CSS and preventing the site from displaying properly. Since I had my metadata and files organized, I actually just deleted that repository since I couldn't figure out what I had done wrong. Starting from scratch was a bit tedious, but not too much of a setback at that point.

Later on, I tried to add my custom metadata elements to the search configuration, but after committing I would get no search results whatsoever. It turned out that the cause was a special character "/" in one of my element names. After correcting, my search function worked as intended.

Finally, with more time, resources, and people, I think implementing CDWA standards would be very beneficial for this collection. Unfortunately, I did not have enough time left in the semester to revise or explore this option further.

## Technical Details

### Digitization Guidelines

https://collectionbuilder.github.io/cb-docs/ 

CollectionBuilder provides robust documentation for creating a digital collection. I found the instructions very clear and helpful as it walked me through all the requirements and encoding steps.

### Controlled Vocabularies

Visual art terms: https://www.getty.edu/research/tools/vocabularies/ 
Subject control: https://authorities.loc.gov/ 
Format element: https://www.iana.org/assignments/media-types/media-types.xhtml 
Date element: https://www.iso.org/iso-8601-date-and-time-format.html 
Type element: https://www.dublincore.org/specifications/dublin-core/dcmi-type-vocabulary/2003-02-12/ 
Language element: https://www.loc.gov/standards/iso639-2/php/code_list.php 
Rights elements: https://rightsstatements.org/page/1.0/?language=en 

### Metadata Application Profile

| Element           | Cardinality    | Obligation                    | Vocabulary                       | Directions                                                                                                                                                                                                                                                                                               | Examples                                                     |
|-------------------|----------------|-------------------------------|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------|
| objectid          | not repeatable | required                      | n/a                              | Create unique ids following this template: “tmauu###,” where “#” are numbers.                                                                                                                                                                                                                            | tmauu002                                                     |
| parentid          | not repeatable | required for compound objects | n/a                              | [Compound objects only] Input the objectid of the parent record.                                                                                                                                                                                                                                         | tmauu001                                                     |
| filename          | not repeatable | required                      | n/a                              | Input the name of the digital file for the object. Include file type suffixes.                                                                                                                                                                                                                           | 1963.003.jpg                                                 |
| title             | not repeatable | required                      | CONA if available                | For parent records or .jpg files, transcribe from the provided .csv file, unless the work is cataloged in CONA. For .pdf files, precede title with “museum label for “ Correct to standard title capitalization, if necessary.                                                                           | APARTMENT ‘C’ → Apartment ‘C’ museum label for Apartment ‘C’ |
| artist            | repeatable     | required if provided          | ULAN                             | Terms must be from the ULAN. If the artist is not in ULAN, input using the following format: “last-name, first-name middle-name”. If the artist is unknown, simply put “unknown”; this conforms to the ULAN authority.                                                                                   | Clifton, Jack..                                              |
| medium_technique | repeatable     | required                      | AAT                              | Terms must be from the AAT.                                                                                                                                                                                                                                                                              | oil painting (technique)                                     |
| date              | not repeatable | required                      | ISO 8601                         | Use ISO standards (YYYY) for date input using the “Dated” field in the .csv file.                                                                                                                                                                                                                        | 1985                                                         |
| classification    | not repeatable | required                      | Local vocabulary                 | Use one of the following terms from the Taubman metadata: Paintings, Metal, Prints, Ceramics, Sculptures, Multi-media, Water Media, Stone, Glass, Wood, Drawings, Book Arts, Bone, Weapons, Tools and Equipment, Photographs, Textiles, Furniture, Stencils, Electronic Media, Works on Paper, Plastics. | Paintings                                                    |
| subject           | repeatable     | optional                      | LCSH                             | Terms must be from the LCSH. Perform subject analysis using the provided Description and Title fields along with the digitized image to determine subject terms.                                                                                                                                         | Apartment buildings; Doors                                   |
| nation of origin  | not repeatable | optional                      | TGN                              | Terms must be from the TGN. Use the “nation” terms in TGN rather than “region.” It may be necessary to derive geographic terms from provided cultural terms (e.g. “French” = “France”).                                                                                                                  | United States                                                |
| description       | not repeatable | optional                      | n/a                              | Transcribe directly from the provided .csv file.                                                                                                                                                                                                                                                         | (not provided for this work)                                 |
| size              | not repeatable | optional                      | n/a                              | Transcribe from the provided .csv file.  Omit any additional text besides the dimensions in inches and centimeters.                                                                                                                                                                                      | 31 1/4 x 44 1/2 in. (79.4 x 113 cm)                          |
| source            | not repeatable | required                      | n/a                              | Input according to CollectionBuilder documentation.                                                                                                                                                                                                                                                      | Permanent Collection, Taubman Museum of Art                  |
| object number     | not repeatable | required                      | n/a                              | Transcribe directly from the provided .csv file.                                                                                                                                                                                                                                                         | 1963.003                                                     |
| type              | not repeatable | required                      | DCMI Type Vocabulary             | Terms must be from the DCMI Type Vocabulary. Input according to CollectionBuilder documentation.                                                                                                                                                                                                         | Image;StillImage Text                                        |
| format            | not repeatable | required                      | IANA Media Types (formerly MIME) | Terms must be from the Media Types vocabulary. For parent records of compound objects, instead input “compound_object”.                                                                                                                                                                                  | compound_object image/jpeg application/pdf                   |
| language          | not repeatable | required                      | ISO 639-2                        | Terms must be from the ISO vocabulary.                                                                                                                                                                                                                                                                   | eng                                                          |
| rights            | not repeatable | required                      | RightsStatements.org vocabulary  | Input “Copyright Undetermined” unless rights have been defined.                                                                                                                                                                                                                                          | Copyright Undetermined                                       |
| rightsstatement   | not repeatable | required                      | RightsStatements.org vocabulary  | Input the URI from RightsStatements.org.                                                                                                                                                                                                                                                                 | https://rightsstatements.org/page/UND/1.0/                   |

<!-- IMPORTANT!!! DELETE this comment and the include below when you are finished editing this page for your collection. The include below introduces about page features. They will show up on your collection's about page until you delete it.  -->
{% include cb/about_the_about.md %} 
