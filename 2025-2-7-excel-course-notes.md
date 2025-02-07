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

## Understanding Excel List Structure

Excel looks for headers in the first row and will use those column names while filtering and stuff like that.

Make sure your list doesn't have empty rows because that indicates to Excel that your single table is actually two different tables
