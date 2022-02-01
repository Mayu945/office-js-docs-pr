---
title: Excel JavaScript API requirement set 1.14
description: 'Details about the ExcelApi 1.14 requirement set.'
ms.date: 12/08/2021
ms.prod: excel
ms.localizationpriority: medium
---

# What's new in Excel JavaScript API 1.14

The ExcelApi 1.14 added objects to control the data table feature of a chart, a method to locate all the precedent cells of a formula, and worksheet protection events to track changes to the protection state of a worksheet. It also added multiple [`getItemOrNullObject`](../../develop/application-specific-api-model.md#ornullobject-methods-and-properties) methods for objects like `CommentCollection`, `ShapeCollection`, and `StyleCollection` to improve error handling.

| Feature area | Description | Relevant objects |
|:--- |:--- |:--- |
| [Chart data tables](../../excel/excel-add-ins-charts.md#add-and-format-a-chart-data-table) | Control appearance, formatting, and visibility of data tables on charts. | [Chart](/javascript/api/excel/excel.chart), [ChartDataTable](/javascript/api/excel/excel.chartdatatable), [ChartDataTableFormat](/javascript/api/excel/excel.chartdatatableformat) |
| [Formula precedents](../../excel/excel-add-ins-ranges-precedents-dependents.md#get-the-precedents-of-a-formula) | Return all the precedent cells of a formula. | [Range](/javascript/api/excel/excel.range) |
| Queries | Retrieve Power Query attributes like name, refresh date, and query count. | [Query](/javascript/api/excel/excel.query), [QueryCollection](/javascript/api/excel/excel.querycollection)|
| [Worksheet protection events](../../excel/excel-add-ins-worksheets.md#detect-changes-to-the-worksheet-protection-state) | Track changes to the protection state of a worksheet and the source of those changes. | [WorksheetProtectionChangedEventArgs](/javascript/api/excel/excel.worksheetprotectionchangedeventargs), [Worksheet](/javascript/api/excel/excel.worksheet), [WorksheetCollection](/javascript/api/excel/excel.worksheetcollection) |

## API list

The following table lists the APIs in Excel JavaScript API requirement set 1.14. To view API reference documentation for all APIs supported by Excel JavaScript API requirement set 1.14 or earlier, see [Excel APIs in requirement set 1.14 or earlier](/javascript/api/excel?view=excel-js-1.14&preserve-view=true).

| Class | Fields | Description |
|:---|:---|:---|
|[AutoFilter](/javascript/api/excel/excel.autofilter)|[clearColumnCriteria(columnIndex: number)](/javascript/api/excel/autofilter#excel-excel-autofilter-clearColumnCriteria-member(1))|Clears the column filter criteria of the AutoFilter.|
|[ChangeDirectionState](/javascript/api/excel/excel.changedirectionstate)|[deleteShiftDirection](/javascript/api/excel/changedirectionstate#excel-excel-changedirectionstate-deleteShiftDirection-member)|Represents the direction (such as up or to the left) that the remaining cells will shift when a cell or cells are deleted.|
||[insertShiftDirection](/javascript/api/excel/changedirectionstate#excel-excel-changedirectionstate-insertShiftDirection-member)|Represents the direction (such as down or to the right) that the existing cells will shift when a new cell or cells are inserted.|
|[Chart](/javascript/api/excel/excel.chart)|[getDataTable()](/javascript/api/excel/chart#excel-excel-chart-getDataTable-member(1))|Gets the data table on the chart.|
||[getDataTableOrNullObject()](/javascript/api/excel/chart#excel-excel-chart-getDataTableOrNullObject-member(1))|Gets the data table on the chart.|
|[ChartDataTable](/javascript/api/excel/excel.chartdatatable)|[format](/javascript/api/excel/chartdatatable#excel-excel-chartdatatable-format-member)|Represents the format of a chart data table, which includes fill, font, and border format.|
||[showHorizontalBorder](/javascript/api/excel/chartdatatable#excel-excel-chartdatatable-showHorizontalBorder-member)|Specifies whether to display the horizontal border of the data table.|
||[showLegendKey](/javascript/api/excel/chartdatatable#excel-excel-chartdatatable-showLegendKey-member)|Specifies whether to show the legend key of the data table.|
||[showOutlineBorder](/javascript/api/excel/chartdatatable#excel-excel-chartdatatable-showOutlineBorder-member)|Specifies whether to display the outline border of the data table.|
||[showVerticalBorder](/javascript/api/excel/chartdatatable#excel-excel-chartdatatable-showVerticalBorder-member)|Specifies whether to display the vertical border of the data table.|
||[visible](/javascript/api/excel/chartdatatable#excel-excel-chartdatatable-visible-member)|Specifies whether to show the data table of the chart.|
|[ChartDataTableFormat](/javascript/api/excel/excel.chartdatatableformat)|[border](/javascript/api/excel/chartdatatableformat#excel-excel-chartdatatableformat-border-member)|Represents the border format of chart data table, which includes color, line style, and weight.|
||[fill](/javascript/api/excel/chartdatatableformat#excel-excel-chartdatatableformat-fill-member)|Represents the fill format of an object, which includes background formatting information.|
||[font](/javascript/api/excel/chartdatatableformat#excel-excel-chartdatatableformat-font-member)|Represents the font attributes (such as font name, font size, and color) for the current object.|
|[CommentCollection](/javascript/api/excel/excel.commentcollection)|[getItemOrNullObject(commentId: string)](/javascript/api/excel/commentcollection#excel-excel-commentcollection-getItemOrNullObject-member(1))|Gets a comment from the collection based on its ID.|
|[CommentReplyCollection](/javascript/api/excel/excel.commentreplycollection)|[getItemOrNullObject(commentReplyId: string)](/javascript/api/excel/commentreplycollection#excel-excel-commentreplycollection-getItemOrNullObject-member(1))|Returns a comment reply identified by its ID.|
|[ConditionalFormatCollection](/javascript/api/excel/excel.conditionalformatcollection)|[getItemOrNullObject(id: string)](/javascript/api/excel/conditionalformatcollection#excel-excel-conditionalformatcollection-getItemOrNullObject-member(1))|Returns a conditional format identified by its ID.|
|[GroupShapeCollection](/javascript/api/excel/excel.groupshapecollection)|[getItemOrNullObject(key: string)](/javascript/api/excel/groupshapecollection#excel-excel-groupshapecollection-getItemOrNullObject-member(1))|Gets a shape using its name or ID.|
|[Query](/javascript/api/excel/excel.query)|[error](/javascript/api/excel/query#excel-excel-query-error-member)|Gets the query error message from when the query was last refreshed.|
||[loadedTo](/javascript/api/excel/query#excel-excel-query-loadedTo-member)|Gets the query loaded to object type.|
||[loadedToDataModel](/javascript/api/excel/query#excel-excel-query-loadedToDataModel-member)|Specifies if the query loaded to the data model.|
||[name](/javascript/api/excel/query#excel-excel-query-name-member)|Gets the name of the query.|
||[refreshDate](/javascript/api/excel/query#excel-excel-query-refreshDate-member)|Gets the date and time when the query was last refreshed.|
||[rowsLoadedCount](/javascript/api/excel/query#excel-excel-query-rowsLoadedCount-member)|Gets the number of rows that were loaded when the query was last refreshed.|
|[QueryCollection](/javascript/api/excel/excel.querycollection)|[getCount()](/javascript/api/excel/querycollection#excel-excel-querycollection-getCount-member(1))|Gets the number of queries in the workbook.|
||[getItem(key: string)](/javascript/api/excel/querycollection#excel-excel-querycollection-getItem-member(1))|Gets a query from the collection based on its name.|
||[items](/javascript/api/excel/querycollection#excel-excel-querycollection-items-member)|Gets the loaded child items in this collection.|
|[Range](/javascript/api/excel/excel.range)|[getPrecedents()](/javascript/api/excel/range#excel-excel-range-getPrecedents-member(1))|Returns a `WorkbookRangeAreas` object that represents the range containing all the precedents of a cell in the same worksheet or in multiple worksheets.|
|[ShapeCollection](/javascript/api/excel/excel.shapecollection)|[getItemOrNullObject(key: string)](/javascript/api/excel/shapecollection#excel-excel-shapecollection-getItemOrNullObject-member(1))|Gets a shape using its name or ID.|
|[StyleCollection](/javascript/api/excel/excel.stylecollection)|[getItemOrNullObject(name: string)](/javascript/api/excel/stylecollection#excel-excel-stylecollection-getItemOrNullObject-member(1))|Gets a style by name.|
|[TableScopedCollection](/javascript/api/excel/excel.tablescopedcollection)|[getItemOrNullObject(key: string)](/javascript/api/excel/tablescopedcollection#excel-excel-tablescopedcollection-getItemOrNullObject-member(1))|Gets a table by name or ID.|
|[Workbook](/javascript/api/excel/excel.workbook)|[queries](/javascript/api/excel/workbook#excel-excel-workbook-queries-member)|Returns a collection of Power Query queries that are part of the workbook.|
|[Worksheet](/javascript/api/excel/excel.worksheet)|[onProtectionChanged](/javascript/api/excel/worksheet#excel-excel-worksheet-onProtectionChanged-member)|Occurs when the worksheet protection state is changed.|
||[tabId](/javascript/api/excel/worksheet#excel-excel-worksheet-tabId-member)|Returns a value representing this worksheet that can be read by Open Office XML.|
|[WorksheetChangedEventArgs](/javascript/api/excel/excel.worksheetchangedeventargs)|[changeDirectionState](/javascript/api/excel/worksheetchangedeventargs#excel-excel-worksheetchangedeventargs-changeDirectionState-member)|Represents a change to the direction that the cells in a worksheet will shift when a cell or cells are deleted or inserted.|
||[triggerSource](/javascript/api/excel/worksheetchangedeventargs#excel-excel-worksheetchangedeventargs-triggerSource-member)|Represents the trigger source of the event.|
|[WorksheetCollection](/javascript/api/excel/excel.worksheetcollection)|[onProtectionChanged](/javascript/api/excel/worksheetcollection#excel-excel-worksheetcollection-onProtectionChanged-member)|Occurs when the worksheet protection state is changed.|
|[WorksheetProtectionChangedEventArgs](/javascript/api/excel/excel.worksheetprotectionchangedeventargs)|[isProtected](/javascript/api/excel/worksheetprotectionchangedeventargs#excel-excel-worksheetprotectionchangedeventargs-isProtected-member)|Gets the current protection status of the worksheet.|
||[source](/javascript/api/excel/worksheetprotectionchangedeventargs#excel-excel-worksheetprotectionchangedeventargs-source-member)|The source of the event.|
||[type](/javascript/api/excel/worksheetprotectionchangedeventargs#excel-excel-worksheetprotectionchangedeventargs-type-member)|Gets the type of the event.|
||[worksheetId](/javascript/api/excel/worksheetprotectionchangedeventargs#excel-excel-worksheetprotectionchangedeventargs-worksheetId-member)|Gets the ID of the worksheet in which the protection status is changed.|

## See also

- [Excel JavaScript API Reference Documentation](/javascript/api/excel?view=excel-js-1.14&preserve-view=true)
- [Excel JavaScript API requirement sets](excel-api-requirement-sets.md)
