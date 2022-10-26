# UFO Analysis

## Overview

Dana is a journalist covering her dream beat: UFO sightings in her home town. Her curiosity compelled her to create a website for her new article on the subject. In addition to displaying the article, Dana wanted to display a table of sightings on her website. To make this table more usable, she also wanted the user to be able to apply filters to aid in their search for answers.

## Results

### Methods and Tools

- Microsoft Visual Studio Code was used to edit all HTML, CSS, and JavaScript files.
- Google Chrome (through Visual Studio Code) was used to preview the site and developer tools were utilized to aid in debugging.
- Bootstrap 4.0.0 was used to style the site.
- The D3 library was used to aid in the JavaScript interaction with HTML.
- An image from NASA is used as the background image.

### Navigation and Filtering

On loading the site the user is presented with the article and an unfiltered table of UFO sightings. Text fields are also provided for the filtering feature.

The data displayed in the table contains:

- Date of sighting
- City
- State
- Country
- Shape
- Duration
- Comments

An overview is shown below:

![Landing](/assets/site_wide.png)

Dana requested that this table be filterable on the categories previously listed, excluding duration and comments.

To begin filtering a user can replace the default or placeholder text with their own. For example, if a user wanted to filter the table to display only sightings in the state of California they would type "ca" into the State field and press enter or simply click out of the field. A snippet of results is shown.


![California](/assets/california_sightings.png)


If the user is interested in sightings with a specific shape in California they can add that to their filters. Adding "Triangle" to the shape filter yields:

![Triangle](/assets/california_triangle.png)

Although both instances occur on the same date, it appears El Cajon, CA may be home to a larger number of sightings. To get a general overview of this city a user can removie the shape filter and add "el cajon" to the city field.

![El_Cajon](/assets/el_cajon.png)

This suggests a cluster of sightings of varying type around 1/1/2010 but no reports since.

Perhaps that data is signifcant? If the user wishes to investigate all sightings on that day they can clear the city and state fields and add "1/1/2010" to the date field.

![New_Year_2010](/assets/new_year_2010.png)

A scroll through this list shows sightings from coast to coast. Perhaps it was an eventful night for the visitors. Notibly, all of these sightings occured in the US, what about international reports? Canada provides only two:

![Canada](/assets/canada.png)

The availibe filtering options provide an expert or a budding UFO investigator the tools they need to zero in on just the data they are looking for.

## Summary

While the current version of this site accomplishes the goals set by Dana, it is incredibly user unfriendly and bordering on user hostile.

The default text in the filter fields is a cue to the input desired but some are not in their usual format (state as lowercase) or may require special knoweldge (shape) to know the options. The response for an unsupported filter is simply a blank table which may not convey to the user that their entry was in the wrong format.

The largest and perhaps most simple fix that should be implemented is to adjust the case of the retrieved text to match the data for comparing during the filtering process.

A further change to address special knowledge or whether the data exists is to change some fields to be drop drown menus (or radio buttons) depending on the number of options. This should be implemented for the following:

- State - while it may seem the state abbreviation should be simple, some people may not know them for every state.
- County - some of these are well known, UK for instance, but depending on the scope of future additions countries with less well known abbreviations may be added. At this point, the primary reason to make this field a drop down is to let the user know what options are availible.
- Shape - Given the variety from triangle to fireball or uknown it seems unreasonable to expect every user to be able to use this field as a filter unless the have looked through the table already. Making this a drop down takes the guesswork out.

Making these two changes is a good first step, further development could venture into:

- Creating an error message for invalid input. Perhaps red text under the input field indicating an error.
- Modifying the data field to allow a range. As an example, the entries for El Cajon, CA are almost all on 1/1/2010 but there is an additional entry a few days later that could be relavent. Allowing for a range of dates would reduce the number of filter requests required to get a full picture in some cases.
- Making the table interactive so that the user could sort on every column except comments.
- Adding a filter for the comments field. This could be implemented as matching one or two words in the comment text. While not exact this serves a useful purpose. For example, there are sightings with an unknown shape that describe the shape in the body of the text.
- Improving the integration of the filter fields into the styling of the site itself, such as making them the same length when displayed.