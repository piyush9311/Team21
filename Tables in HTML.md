# Table

## [What is a table ?](https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables/Basics#what_is_a_table "Permalink to What is a table ?")

A table is a structured set of data made up of rows and columns (**tabular data**). A table allows you to quickly and easily look up values that indicate some kind of connection between different types of data, for example a person and their age, or a day of the week, or the timetable for a local swimming pool.

### [How does a table work?](https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables/Basics#how_does_a_table_work "Permalink to How does a table work?")

The point of a table is that it is rigid. Information is easily interpreted by making visual associations between row and column headers.

### [Table styling](https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables/Basics#table_styling "Permalink to Table styling")

You can also have a  [look at the live example](https://mdn.github.io/learning-area/html/tables/assessment-finished/planets-data.html)  on GitHub! One thing you'll notice is that the table does look a bit more readable there — this is because the table you see above on this page has minimal styling, whereas the GitHub version has more significant CSS applied.

Be under no illusion; for tables to be effective on the web, you need to provide some styling information with  [CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS), as well as good solid structure with HTML. In this module we are focusing on the HTML part; to find out about the CSS part you should visit our  [Styling tables](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Styling_tables)  article after you've finished here.

We won't focus on CSS in this module, but we have provided a minimal CSS stylesheet for you to use that will make your tables more readable than the default you get without any styling. You can find the  [stylesheet here](https://github.com/mdn/learning-area/blob/master/html/tables/basic/minimal-table.css), and you can also find an  [HTML template](https://github.com/mdn/learning-area/blob/master/html/tables/basic/blank-template.html)  that applies the stylesheet — these together will give you a good starting point for experimenting with HTML tables.

### [When should you NOT use HTML tables?](https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables/Basics#when_should_you_not_use_html_tables "Permalink to When should you NOT use HTML tables?")

HTML tables should be used for tabular data — this is what they are designed for. Unfortunately, a lot of people used to use HTML tables to lay out web pages, e.g. one row to contain the header, one row to contain the content columns, one row to contain the footer, etc. You can find more details and an example at  [Page Layouts](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#page_layouts)  in our  [Accessibility Learning Module](https://developer.mozilla.org/en-US/docs/Learn/Accessibility). This was commonly used because CSS support across browsers used to be terrible; table layouts are much less common nowadays, but you might still see them in some corners of the web.

In short, using tables for layout rather than [CSS layout techniques](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout)  is a bad idea. The main reasons are as follows:

1.  **Layout tables reduce accessibility for visually impaired users**:  [Screenreaders](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Cross_browser_testing/Accessibility#screenreaders), used by blind people, interpret the tags that exist in an HTML page and read out the contents to the user. Because tables are not the right tool for layout, and the markup is more complex than with CSS layout techniques, the screenreaders' output will be confusing to their users.
2.  **Tables produce tag soup**: As mentioned above, table layouts generally involve more complex markup structures than proper layout techniques. This can result in the code being harder to write, maintain, and debug.
3.  **Tables are not automatically responsive**: When you use proper layout containers (such as  [`<header>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/header),  [`<section>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/section),  [`<article>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/article), or  [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)), their width defaults to 100% of their parent element. Tables on the other hand are sized according to their content by default, so extra measures are needed to get table layout styling to effectively work across a variety of devices.

## [Active learning: Creating your first table](https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables/Basics#active_learning_creating_your_first_table "Permalink to Active learning: Creating your first table")

We've talked table theory enough, so, let's dive into a practical example and build up a simple table.

1.  First of all, make a local copy of  [blank-template.html](https://github.com/mdn/learning-area/blob/master/html/tables/basic/blank-template.html)  and  [minimal-table.css](https://github.com/mdn/learning-area/blob/master/html/tables/basic/minimal-table.css)  in a new directory on your local machine.
2.  The content of every table is enclosed by these two tags :  **`[<table></table>](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table)`**. Add these inside the body of your HTML.
3.  The smallest container inside a table is a table cell, which is created by a  **`[<td>](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/td)`**  element ('td' stands for 'table data'). Add the following inside your table tags:
4. If we want a row of four cells, we need to copy these tags three times. Update the contents of your table to look like so:
As you will see, the cells are not placed underneath each other, rather they are automatically aligned with each other on the same row. Each  `<td>`  element creates a single cell and together they make up the first row. Every cell we add makes the row grow longer.

To stop this row from growing and start placing subsequent cells on a second row, we need to use the  **`[<tr>](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tr)`**  element ('tr' stands for 'table row'). Let's investigate this now.

1.  Place the four cells you've already created inside  `<tr>`  tags, like so
2.  Now you've made one row, have a go at making one or two more — each row needs to be wrapped in an additional  `<tr>`  element, with each cell contained in a  `<td>`.
