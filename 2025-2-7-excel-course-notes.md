# Udemy Course: All-in-One Excel Training: Transform Your Skills with Hands-On Projects and Real World Applications

## Keyboard Shortcuts
Ctrl + DownArrow - Go to last row in the current sheet
Ctrl + RightArrow - Go to the last column in the current sheet
Ctrl + Home - Go back to cell A1 of the current sheet

Multi-Select Rows/Columns
	- Highlight first selection
	- Hold down Ctrl
	- Select each new selection; they should be highlighted along with your first selection


## Relative References vs Absolute References
Absolute References are written like so:

	$E$9

Relative References are written like normal:

	E4

The difference is that "Relative References" will change as you paste them into new cells based on their position to other values. Whereas, an absolute reference will ALWAYS, no matter where or how you paste it, refer to the cell you specified.

Saves a lot of time as you drag formulas into other cells.


## Evaluating Formulas
You can walk through a formula by
- Go to the "Formulas" tab
- Look under the "Formula Auditing" seciton
- Click the "Evaluate Formula" button

This will bring up the formula in the current selected cell in a window where you can walk through every step and make sure you got your PEMDAS logic correct.


## Functions
=SUM(B4:B8)
=MIN(B4:B8)
=MAX(B4:B8)
=AVERAGE(B4:B8)
=COUNT(B4:B8) - counts the number of cells in a range that contain numbers

Formulas tab has several books with all the available formulas in Excel


## Adjacent Cells
Excel may sometimes give you an error saying "Formula Omits Adjacent Cells". In certain cases, this is Excel not understanding what you are trying to do here and thinking unrelated numbers are included in a calculation. You can disable this error.


## AutoSum
Excel has an "AutoSum" button that is a shortcut to sum up a bunch of cells. However, this AutoSum button can soemtimes not be right with the cells that it grabs, so you sometimes have to reselect the correct cells you want.

This AutoSum button also has a dropdown where you can select an automatic average, min, max, etc...

You can also use the keyboard shortcut Alt+= to trigger the AutoSum.


## Moving and Copying Data in an Excel Worksheet

First, if you need to move a table within the same workbook or sheet, you can highlight the section you want to move. Then, hover over the border until your cursor becomes a 4-way arrow icon. Once it is on this icon, you can drag this section to another place in your same workbook


Esc - Remove selection ("marching ants")


## Inserting and Deleting Rows & Columns

Insert a New Row Above - Click the row that you want to be below your new row. Hold Ctrl and hit the "+" icon on your number pad. Or your can use Ctrl+Shift++ to use the + icon on your normal keyboard.

This is also really powerful because Excel will automatically update all of our formulas associated with that range of cells to include the new row!

You can also use Ctrl+- to remove a row!

## Change Width/Height of Cells

Working with Multiple Columns - If you want to adjust multiple columns at once, you can click on the column headings to highlight all columns and then you can:

1) Double click on the line between two-columns to Auto-Fit all selected columns to the width of the largest item in that column
2) Drag the line between two columns to adjust the width of ALL selected columns at once.

## Hiding or Unhiding Columns

Hidden content doesn't print out when you hit the Print key for a worksheet.

You can right-click on a column and choose the "Hide" option to make the width of said column to 0.

To unhide it, you can just click in the little space for the hidden column in the header and drag it out again.

Later in the course, he'll talk about Review > Protect sheet

## Moving and Copying an Excel Worksheet

You can hold down "Ctrl" while dragging a worksheet to make a copy of it.

You can move worksheets to a totally different Excel file if you need to.

## Working with Font Formatting Controls

The theme determines what colors you have for Text under "Theme Colors".

Page Layout > Themes is where you can control the theme colors (and fonts) of the current document

## Change Background Color of a Cell

## Adding Borders to Cells
## Excel Borders Continued

"More Borders" => Allows you to go more in depth with borders

## Formatting Data as Currency Values
## Formatting Percentages

Add/Remove decimal places buttons in the "Number Formatting" options

## Using Excel's Format Painter

Format Painter allows you to copy the format from one cell and apply it to others.

Click "Format Painter" menu button once to only apply it to one cell and twice to keep it open for application to multiple cells.

"Esc" to stop using format painter

## Creating Styles to Format Data

Styles > Cell Styles > Neew Cell Style to create a new style you can use across the document

You can also Modify existing Custom Cell Styles to apply it everywhere you used it.

## Merging and Centering Cells

Highlight Cells you want to Merge and Under "Alignment", hit the "Merge and Center" button

## Conditional Formatting


## Inserting Images and Shapes into an Excel Worksheet
## Inserting Excel Shapes

## Formatting Excel Shapes

On click shape:
- White Markers are to resize the shape
- Orange Markers are to change the size of certain portions of the shape


## Working with Excel SmartArt

SmartArt allows you to create diagrams in Excel



## Charts

Insert > Charts

Switch Row/Column button

"Select Data" button -> Allows you to exclude certain columns or rows of data with a chart

Can make the chart title follow the title in your main chart by going to the formula tab and starting with an = sign before choosing an excel cell

"Add Chart Element" button - can also modify existing chart elements like axis labels, legend, etc...

You can also use the "Move Chart" button to either move the chart to a different existing worksheet, or to move it to a new sheet that will be a "Chart Sheet" and will only contain the chart itself.

Pie Charts are more suited to display a single row or column of data. To change what month is displayed, use "Select Data"

Change Chart Labels to Percentage instead of Value
- Right-Click on one of the labels
- Choose "Format Data Labels"
- Click the desired format, between value, percentage, etc...

Filter by clicking little Funnel Icon next to chart

To print Chart ONLY, select chart and go to File > Print
To print Chart and Worksheet, don't select the chart and go to File > Print

## Print an Excel Workbook

Use Dotted lines that appear after Print Preview to reformat the workbook.

You can change:
- Margins of the printout
- Scaling of the printout (Make things larger or smaller)
- Whether to Print Out in Portrait or Landscape


## Page Layout View

View > Workbook Views > Page Layout
- Shows individual pages instead of a full workbook


## Header and Footer Content

Zoom In/Out - Hold Ctrl and Use scroll wheel to zoom in and out


## Printing a Specific Range of Cells

You can select a subset of a document and go to Print and select under "Settings" to "Print Selection" instead of "Print Active Sheets"

You can also select an area of your sheet you want to print off and go to Page Layout > Print Area > Set Print Area. When you do that, this document will always just pring that one area. There's also an option to "Ignore Print Area" if you need that.


## Working with Excel Templates

### Using an Existing Template

File > New has several templates from Office that you can use 

### Creating a Custom Template

Make a Copy of the Existing Budget Worksheet in a New Sheet

File > Save As

Chose ".xltx" extension for Excel Template and Save it to the "Custom Office Templates" directory so it's easy for Excel to find again.


# Excel 102

## Working with an Excel List

### Understanding Excel List Structure
Excel looks for headers in the first row and will use those column names while filtering and stuff like that.

Make sure your list doesn't have empty rows because that indicates to Excel that your single table is actually two different tables


### Sorting a List Using Single Level Sort
We want to sort a list to find the records, but it depends on what application we want.

Data > Sort & Filter

Two Buttons; Ascending and Descending Order


### Sorting a List Using Multi-Level Sort
Sometimes we want to sort a list by multiple columns; in this case, Last Name AND First name

Data > Sort & Filter > Sort

Add multiple sort levels; can add up to 64 levels of sorting


### Using Custom Sorts in an Excel List
Data > Sort & Filter > Sort

Under "Order" of a sorting rule, choose "Custom List..." where you can specify a list of values in order. Days of the week and months of the year are already specified.

### Filter an Excel List using the AutoFilter Tool
Data > Sort & Filter > Filter

This adds an arrow to each header that allows you to show only the values you want in each column

Data > Sort & Filter > Clear - To remove all current filters


### Creating Subtotals in a List
Want to find total sales for each of the products. Can use a subtotal to achieve this goal.

First, sort the table by the Product column to split the transactions into groups of sales by product.

Then go to Data > Subtotal. You need to tell it to Subtotal "At each change in:" (Product), "Use Function:"(Sum), and "add subtotal to:"(Sales)

This also gives you the ability to collapse groups of transactions to where you only show subtotals of certain groups.


### Format a List as a Table
When you use a table like one of employee records, it can be useful to add color coding to every other row or to add calculations to the bottom of the table (like number of employees). But Sorting and Filtering can often screw these sorts of things up.

Use:

Home > Format as Table

This does a few things.
- First, whatever table style you specify gets applied. If your table has alternating row colors, then those row colors stay alternated no matter how you sort and filter the list
- Second, you have other cool functionality through the new "Table Design" tab. You can actually ad a "Total" row, which can count the number of records, sum up any column, and so on...
- You can also drag down the little backwards "L" at the bottom of the table to add several rows at once to this table


### Using Conditional Formatting to Find Duplicates
Sometimes you might have duplicates in a table. First, we'll Identify the Duplicates, then we'll remove them.

To identify them, you need to first find a column where the data is guaranteed to be unique amongst employees (Employee Id, for example)

Then go to:
	Home > Styles > Conditional Formatting > Highlight Cells Rules > Duplicate Values

Once you hit this, it will open up a dialog previewing the changes and asking how you want to highlight duplicate values. If you click OK, it applies the changes to your current sheet.

#### Keyboard Shortcut
Ctrl + Shift + DownArrow -> advances selection to grab the whole table column (or wherever it finds an empty cell first)


### Removing Duplicates

Now that we've identified the duplicates, we need to do something with them. In this case, we'll remove them.

If you've Formatted your List as a table, you can go to this built-in tool to remove duplicates:
	Table Design > Tools > Remove Duplicates

If you haven't, you need to go to:
	Data > Data Tools > Remove Duplicates

Both do the same thing. When you open it, the tool will ask you to select what columns should be compared when deciding if a value is a duplicate. 

If you leave all of them selected, it's possible you could miss duplicates. For example, what if someone put in a "Robert" entry a second time, but called him "Rob". By default, Excel will consider that a unique value even if all of the other info is the same.

For that reason, in our case, we're just going to go with "Employee ID". Hit OK, and it'll automatically remove those duplicates.


## Excel List Functions
### Introduction to Excels Functions: DSUM()

SUM is very popular in Excel. But what if you wanted to SUM up a set of columns, but only when the record matches a specific condition (For example, when the row specifies "Rent" as the category)

Drop in the Column Name in one cell and the value you want to use in the cell below it

	**Category**
	Rent

### Excel DSUM function single criteria

Ctrl+Shift+Down Arrow - Select all rows of the current list
Ctrl+Shift+Right Arrow - Select all columns of the current list

DSUM(database, field, criteria)
**database** - select your table where you want to do the calculations
(in our case, A1:F59)

**field** - What column value do you want to sum up based on the criteria? Choose the column header (In our case, F1)

**criteria** - Select the criteria you put down earlier across 2 cells (In our case, I2:I3)

Hit enter and you'll get the necessary value of all "Rent" Sales within the list

### Excel DSUM Function with OR criteria

Right now, we have only one criteria; Category = Rent.

For this lesson, let's get the sum of Category = Rent OR Category = Software

So, in this case, just add "Software" in a cell below "Rent" that we had added earlier. This is an OR statement Your criteria column should look like this:

	**Category**
	Rent
	Software

Then, change up the range on the DSUM to, instead of using I2:I3, it uses I2:I4


### Excel DSUM Function with AND criteria
This time, we'll focus on an AND criteria

Change the criteria column back to what it was before the OR example and change the formula back to use I2:I3 for the criteria:

	**Category**
	Rent

Then, we're going to add another column, as we're also going to SUM based on Division at the same time. Make the column look like so:

	**Division**
	North

So now, we're saying to SUM up stuff based on only "Rent" categories where the Division is equal to "North". Here's the full criteria column:

	**Division**     |     **Category**
	North            |     Rent

Then, change up your criteria in the DSUM to use this new range; in our case, H2:I4. Hit enter, and we'll get all Rent charges from the North Division from this worksheet.

We can also combine OR and AND statements via the following:

	**Division**     |     **Category**
	North            |     Rent
	North            |     Software

So this SUMs all values in Total Sales that have Division = North AND Category = Rent OR Software.

Make sure the colum headers and values are spelled exactly as they are spelled in the table, so Excel knows what to look for.

	=DSUM(A1:F59,F1,H2:I4)

### Excel DAVERAGE function
There are several Database functions within Excel and they are setup fairly similarly, minus what it outputs.

In our case, we're going to add a DAVERAGE, which does the same thing as DSUM, but instead of a SUM, it provides an Average.

Same exact function, but this time, we're getting the average.

	=DAVERAGE(A1:F59,F1,H2:I4)

### Excel DCOUNT() function

	=DCOUNT(A1:F59,F1,I8:I9)

We also have a DCOUNTA funciton. If you were trying to count not only numeric values, but alphabetical values, use the alternate DCOUNTA function.

We make a new column like so:

	**Category**
	Supplies

And then put in the DCOUNT, setting the criteria to those cells.


### Excel SUBTOTAL() function
Still a database function, but has one huge difference.

The first argument in =SUBTOTAL is the number referencing what function you want to use on it. In this case, we will use a 9 for the SUM.

The second argument is the reference, so we will select the entire "Total Sales" column. This gives us the same value as if we used a SUM on this column.

Why do this? Because when you go and Filter the list, the SUBTOTAL function will update itself based on the filters you specify.

So if you filter the list; "I want only Sales from the East Division", then the Subtotal field will update to show the total of only those sales.

Similar to how we used the DSUM/DAVERAGE/DCOUNT function earlier, but a little bit different because you don't need the extraneous columns with the criteria


## Excel Data Validation
### Understanding the Need for Excel Data Validation
Need consistent values in each column when many people are going to be editing a worksheet. This makes sure that values within a list in Excel are easily filterable by end users and reports can be made from them.

### Creating an Excel Data Validation List
First, we want to validate the "Make" to only use established car brands.

- Select the entire column
- Data > Data Tools > Data Validation > Data Validation
- This opens a window where you can set what values to allow within these cells.
- Select "Allow: List" and input all of the car models you want within the "Source" cell separated by commas (in our case, Chevy, Dodge, Ford, etc...)
- Click OK

Now, when you go to add a value to those cells, or change a value, it gives you a dropdown with all of the available values for these cells. Also, you will get an error message if you add a value outside of the available values.


### Excel Decimal Data Validation
Now, we're going to add validation to the "Rate" column to keep all prices within this column between $14.95 and $35.95

- Select the entire column
- Data > Data Tools > Data Validation > Data Validation
- This opens a window where you can set what values to allow within these cells.
- Set "Allow" to "Decimal" and set the "Minimum" and "Maximum" values
- In our case, Minimum = 14.95 and Maximum = 39.95

You'll now get an error message if you try to add a value outside of that range.


### Adding a Custom Excel Data Validation Error
Existing error messages are vague and don't exactly tell users what they did wrong.

Select your same range of cells that you selected before and click the "Data Validation" option. When you get the window, go over to "Error Alert" to customize the error message.

You can also change between various styles of error messages. If you use a Warning or Info error message, you'll get a button to continue instead of just having to Retry or Cancel


### Dynamic Formulas by Using Excel Data Validation Techniques
You can also point an Excel Data Validation List to a range of cells that contain the list of allowable values, especially when you have a set of cells with an active formula


## Importing and Exporting Data
### Importing Data from Text Files into Excel
	Data > Get Data > From File > From Text/CSV

Then this will show a menu helping you import text successfully with various delimiters. Excel often predicts this automatically.

You can Load the data as is, or you can "Transform Data", which will send you to Excel PowerQuery.

Also, the data in this table is actually "linked" to the original file and, if that txt file you originally imported from changes, then your excel table will follow suit.


### Importing Data from Microsoft Access
	Data > From Database > From Microsoft Access Database

You can then import individual tables or queries from the Access database. And, minus some formatting, it will load it into an existing worksheet.

Just like in the TXT file before, updating the Access database will also update your cooresponding Excel document.


### Microsoft Excel Legacy Import Options for New Excel Versions
If you like the old interface for importing data, you can actually turn those on via the File menu.

	File > Options > Data > Show Legacy Data Import Wizards > Check the "From Text (Legacy)" or "From Access (Legacy)"


### Exporting Data to a Text File

Might be useful on importing into other programs or if you only need a small amount of data. There are several options, but to export to a tab-delimited file, you can use:

	File > Export > Change File Type > Text (Tab Delimited)


## Excel Pivot Tables

### Understanding Excel PivotTables
Pivot Tables are designed to summarize large tables of data (For example, sales data) and organize it by a certain criteria. Like Month and Year or Salesperson, or Region.

### Creating an Excel PivotTable

Quick Tip: You can either reference a set of cells within a pivot table, or use the table name. Go ahead and use the table name so that the pivot table automatically updates.

Click into Main Table > Insert > PivotTable and this will open up a dialog to create your pivot table

You can sometimes use an external data source and use that for a Pivot Table.


### Modifying Excel PivotTable Calculations
4 Areas
- Filters
- Columns
- Rows
- Values


### Grouping PivotTable Data
Originally organized data with "Month" as our Rows, "Sum of Sales" as our Values, and "Type" as our Columns.

We'd like to group our data by quarters. So Jan-Mar, Apr-June, July-Sep, and Oct-Dec.

Highlight January, February, and March
	PivotTable Analyze > Group > Group Selection

Then you have those grouped under a single tab called "Group 1". You can also change this name to be something more like "1st Quarter".

Also, it puts the actual Group into the Pivot Table Fields. In this case, it calls it "Month 2".

Now Change it up to where we see sales for each region broken up by Salesperson. Drag "Region" and "Salesperson" to the "Rows" field. Easy as that.


### Formatting PivotTable Data
PivotTables do their best job of formatting data, but sometimes they mess up.

You can always format something through the commands shown earlier in the course, but that formats the cells, not the individual table fields. To do this, you need to go to your "PivotTable Fields" sidebar and find the field you want to format.

Click the little arrow beside the name and click "Value Field Settings". This window has a lot of settings like if to sum the values up or to average them, etc... But we are interested in the "Number Format" button which is the format method we want to


### Modifying PivotTable Calculations
Like we said earlier, you can actually use the "Value Field Settings" to change how the PivotTable calculates the value. So, Sales usually uses a "Sum", but we can change it to a "Count" or "Average" or...

Excel makes it's best guess, but you can override it if necessary.

If you want to show a sum AND an average, you can drag the column down to "Values" again, and change up the function for that. So you can have "Sum of Sales" and "Average of Sales".

Another thing we can do is add what the difference was in Sales between months (So did we increase/decrease in sales between Jan and Feb? And how much?)

Drag over another "Sales" field and open the "Value Field Settings". In this menu, you can move over to the "Show Values As" tab and set the following settings:
- % Difference From
- Base Field: Month
- Base Item:  (previous)


### Drilling Down into PivotTable Data
Sometimes, while viewing a pivot table, you might be interested in a certain column. So, for example, in our PivotTable, April increased 51% over March. If you wanted to drill into the April Data, you can simply select a cell within the April row and double-click it.

This will open up all the rows in your original table that are from that month into a new worksheet that you can peruse and create additional calculations from. Be sure you rename the Detail sheet so you don't get confused on what it was for.


### Creating PivotCharts
Creating Charts based on a PivotTable

Click within your PivotTable
	PivotTable Analyze > PivotChart

Choose your chart and hit "OK".

Removing columns or values will reflect in the PivotChart and automatically update.


### Filtering PivotTable Data
Two ways to filter within a PivotTable - One is using the Filter within PivotTables and the other is using the Slicer tool.

To add a filter, which is a little like a control element, you drag one of your Fields within the "Filters" area in the PivotTable sidebar. In our case, we add "Year" as a Filter.

Then, through the sheet, you will be able to choose one or many years to show data for.


### Filtering with the Slicer Tool
Click Within your PivotTable
	PivotTable Analyze > Insert Slicer

This adds another type of control to the worksheet that allows you to choose between one or more values within that column of data, but it just looks a lot more stylish than the Filter within PivotTables that we saw before.
