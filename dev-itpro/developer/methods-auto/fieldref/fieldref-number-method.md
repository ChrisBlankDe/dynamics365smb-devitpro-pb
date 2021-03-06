---
title: "Number Method"
ms.author: solsen
ms.custom: na
ms.date: 11/06/2018
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
# Number Method
Gets the number of a field as a string.

## Syntax
```
No :=   FieldRef.Number()
```
> [!NOTE]  
> This method can be invoked using property access syntax.  

## Parameters
*FieldRef*  
&emsp;Type: [FieldRef](fieldref-data-type.md)  
An instance of the [FieldRef](fieldref-data-type.md) data type.  

## Return Value
*No*  
&emsp;Type: [Integer](../integer/integer-data-type.md)  
  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 This method is like the [FIELDNO Method \(Record\)](../../methods/devenv-fieldno-method-record.md) method.  
  
## Example  
 The following example displays the caption and the field number of the first 10 fields in the Location table. The Location table is open as a [RecordRef Data Type](../../datatypes/devenv-recordref-data-type.md) object and the reference is stored in the LocationRecref variable. The FieldIndex variable that stores the field index is initialized to 0. The LocationRecref variable uses the [FIELDINDEX Method \(RecordRef\)](../../methods/devenv-fieldindex-method-recordref.md) to create a FieldRef that is named MyFieldRef for the specified field index. MyFiledRef now references the field that is specified by the FieldIndex. MyFieldref is then used to display the number and caption of the field The [NUMBER Method \(FIELDREF\)](../../methods/devenv-number-method-fieldref.md) method retrieves the field number. This is repeated for the first ten fields in the table. This example requires that you create the following global variables.  
  
|Variable name|DataType|  
|-------------------|--------------|  
|LocationRecref|RecordRef|  
|MyFieldRef|FieldRef|  
|FieldIndex|Integer|  
  
```  
  
LocationRecref.OPEN(DATABASE::Location);  
FieldIndex := 0;  
REPEAT  
  FieldIndex  := FieldIndex + 1;  
  MyFieldRef := LocationRecref.FIELDINDEX(FieldIndex);  
  MESSAGE('Field Number: %1  Field Caption: %2.' , MyFieldRef.NUMBER, MyFieldRef.CAPTION);  
UNTIL FieldIndex = 10;  
```  
  

## See Also
[FieldRef Data Type](fieldref-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)