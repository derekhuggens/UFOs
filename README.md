# UFOs
Javascript Web Development

The written analysis has the following:

There is a description of how to perform a search, with images. (4 pt)

Summary:

The summary addresses one drawback of this webpage (2 pt)
The summary addresses two additional recommendations for further development (4 pt)

## Overview of the Project
<br>

#### The purpose of this project is to showcase an interactive UFO Sightings website.

<br>

The interactive portion of the website is a table who's data was entered using `forEach` through a JS function that appended rows, `tr`, data, `td`, and finally, `cell.text` for the values. The table is made interactive via functions that filter and update the table using `d3.select`. Entered filters such as `datetime`, `city`, `state`, `country`, and `shape` for UFO sightings are saved and checked in an empty `filters = {}` object and update the table via an event handler: `d3.selectAll("input").on("change", updateFilters);`

<br>

This project also showcases proper folder directory creation for static documents such as the website's css, images, and Javascript folders, as well as the root folder holding `index.html` (the home page).

<br>

### Results

<br>

Results: Describe to Dana how someone might use the new webpage by walking her through the process of using the search criteria. Use images of your webpage during the filtering process to support your explanation.

Webpage Use Tutorial:

At the top of the page one can see the navbar titled, `UFO Sightings`, and if you hover over it, you can see (on desktops) that your cursor changes and that you can click on it to refresh the page to the default table layout.

Next, a Bootstrap design `jumbotron` is used to with a background NASA image and the title, `The Truth is out There`.

Below the `jumbotron` class image and title, one can see that a new introduction container is made to hold two sections within columns of appropriate ratios. On the left, the `<h3>` title, `UFO Sightings: Fact or Fancy? Ufologists Weigh In`, and on the right, a `<p>` website introduction paragraph `</p>`

The interesting part begins below this introduction container in a new container made where one row and column class is made for the `<form>` tag titled "Filter Search" and 5 different filters within `<li>` tags nested in a `<ul>` and the parent `<form>` tag. Each filter: `date`, `city`, `state`, `country`, and `shape` are written in HTML with associated `id = ""` parameters for Javascript code to identify and store entered form information. For example:

HTML DATE FILTER

```html
<li class="list-group-item bg-dark" style = "font-family: inherit; font-size: 1rem;">
    <label for="date">Enter Date</label>
    <input type="text" placeholder="1/10/2010" id="datetime" />
                                
```

ASSOCIATED JS FOR DATE FILTER IN `app.js`

```js
function filterTable() {    
    let date = d3.select("#datetime").property("value");
    let filteredData = tableData;
    if (date) {
      // Apply 'filter' to the table data to only keep the rows where the 'datetime' value matches the filter value
      filteredData = filteredData.filter(row => row.datetime === date);
    };
    buildTable(filteredData);
}
```

The code above shows the HTML and JS relationship for filtering an interactive table.

<br>

This is the filter section of the webpage:

![Filters](https://github.com/derekhuggens/UFOs/blob/be49e6f404e2be5d577165f6fd8f81c11b0abc81/readMeImages/filters.png)

<br>

Below you can see multiple examples of the table being filtered using the different filter forms:

<br>

![City](https://github.com/derekhuggens/UFOs/blob/be49e6f404e2be5d577165f6fd8f81c11b0abc81/readMeImages/datecity.png)

<br>

![State](https://github.com/derekhuggens/UFOs/blob/be49e6f404e2be5d577165f6fd8f81c11b0abc81/readMeImages/datestate.png)

<br>

![Country](https://github.com/derekhuggens/UFOs/blob/be49e6f404e2be5d577165f6fd8f81c11b0abc81/readMeImages/country.png)

<br>

![Shape](https://github.com/derekhuggens/UFOs/blob/be49e6f404e2be5d577165f6fd8f81c11b0abc81/readMeImages/circle.png)

<br>

### Summary

<br>


A drawback of the UFO Sighting website design is that no one can add to the dataset. If site visitors could create an account and login, then be directed to a form with the same table header information: `Date`, `City`, `State`, `Country`, `Shape`, `Duration`, and `Comments` to fill out. Then the website would be more interesting and would be able to grow. More sightings equals more believability! If users wanted to know specifics about other people's sightings, there should be another filter to search for keywords within the `Comments` column. Also, the `Duration` column could be made filterable to sort sightings by ascending or descending times, or by `<`, `>`, `>=`, or `<=`.