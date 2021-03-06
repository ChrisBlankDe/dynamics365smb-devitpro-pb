---
title: "AddFieldNo Method"
ms.author: solsen
ms.custom: na
ms.date: 10/17/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: "dynamics365-business-central"
author: solsen
---
[//]: # (START>DO_NOT_EDIT)
[//]: # (IMPORTANT:Do not edit any of the content between here and the END>DO_NOT_EDIT.)
[//]: # (Any modifications should be made in the .xml files in the ModernDev repo.)
# AddFieldNo Method
Adds a table field to the filter control for a table on the filter page.

## Syntax
```
[Ok := ]  FilterPageBuilder.AddFieldNo(Name: String, FieldNo: Integer, [Filter: String])
```
## Parameters
*FilterPageBuilder*  
&emsp;Type: [FilterPageBuilder](filterpagebuilder-data-type.md)  
An instance of the [FilterPageBuilder](filterpagebuilder-data-type.md) data type.  

*Name*  
&emsp;Type: [String](../string/string-data-type.md)  
The name that is assigned to the table in the filter control. This value must match the value of the Name parameter that was specified by AddTable, AddRecord, or AddRecordRef method that adds the table to the filter control.
        
*FieldNo*  
&emsp;Type: [Integer](../integer/integer-data-type.md)  
The number that is assigned to the field in the table as specified by the Field No. Property.
        
*Filter*  
&emsp;Type: [String](../string/string-data-type.md)  
A default filter on the field that is specified by the Field parameter.  


## Return Value
*Ok*  
&emsp;Type: [Boolean](../boolean/boolean-data-type.md)  
**true** if the field was added to the field list for the specified filter control; otherwise **false**.If you omit this optional return value and the operation does not execute successfully, a runtime error will occur.    


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 If the filter page implementation will call a SETVIEW method, then the SETVIEW method must be called before the ADDFIELDNO method call, otherwise the default filter that is specified by the *Filter* parameter for field, if any, will be cleared by SETVIEW.  

 The filter that is specified by the *Filter* parameter will overwrite any previously defined filters for the field which were set by ADDVIEW method or read from the record or recordRef instance that defined the filter control.  

## Example  
 The following example initializes a filter page object that includes a filter control for the **Date** system table. The filter control has the caption of **Date record**. The example adds two fields of the **Date** record variable which will be available in the filter control on the filter page: **Period End** and **Period Start**. A default filter is set on the **Period End** field.  

 This example requires that you create the following global variables.  

|Variable name|DataType|SubType|  
|-------------------|--------------|-------------|  
|varDateItem|Text||  
|varDateRecord|Record|Date|  
|varFilterPageBuilder|FilterPageBuilder||  

```  
varDateItem := 'Date record';  
varFilterPageBuilder.ADDRECORD(varDateItem, varDateRecord);  
varFilterPageBuilder.ADDFIELDNO(varDateItem, varDateRecord.FIELDNO(varDateRecord."Period End"),'03032014D');  
varFilterPageBuilder.ADDFIELDNO=(varDateItem, varDateRecord.FIELDNO(varDateRecord."Period Start"));  

```  

## See Also
[FilterPageBuilder Data Type](filterpagebuilder-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)