---
title: "Count Method"
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
# Count Method
Counts the number of records in a table.

## Syntax
```
Number :=   Table.Count()
```
> [!NOTE]  
> This method can be invoked using property access syntax.  

## Parameters
*Table*  
&emsp;Type: [Table](table-data-type.md)  
An instance of the [Table](table-data-type.md) data type.  

## Return Value
*Number*  
&emsp;Type: [Integer](../integer/integer-data-type.md)  
  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 This method returns the number of records that meet the conditions of any filters associated with the records. If no filters are set, then the method shows the total number of records in the table.

> [!IMPORTANT]
> If you use the COUNT method to return the number of records in a CRM integration table, a maximum count of 5000 is returned. The software development kit for Dynamics 365 for Sales does not include support for counting large entity collections. As a result, if a CRM integration table contains thousands of records, COUNT returns a maximum count of 5000.  
>
>  The **COUNT** method does not lock the table before retrieving the number of records in the table. This means that the method reads both uncommitted and committed data, which could cause the number of records that are returned to be inaccurate. To ensure that the count is accurate, use the [LOCKTABLE Method \(Record\)](../../methods/devenv-locktable-method-record.md) before you use the **COUNT** method.  

 In previous versions of [!INCLUDE[d365fin_md](../../includes/d365fin_md.md)], the **COUNT** method ignored security filters and always returned the total number of records unless you called the **SETPERMISSIONFILTER** method to get a filtered count. In [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)], the **COUNT** method adheres to the [SecurityFiltering Property](../../properties/devenv-securityfiltering-property.md). <!--Links For more information, see [Security Filter Modes](Security-Filter-Modes.md)-->.  

## Example  
 This example requires that you create the following variables.  

|Variable name|DataType|Subtype|  
|-------------------|--------------|-------------|  
|CustomerCount|Integer|Not applicable|  
|CustomerRec|Record|Customer|  

```  
CustomerCount := CustomerRec.COUNT;  
// This statement assigns the number of records in the Customer table  
// to the CustomerCount variable. This statement is the same as:  
CustomerCount := 0;  
IF CustomerRec.FIND('-') THEN  
  REPEAT  
    CustomerCount := CustomerCount + 1;  
  UNTIL CustomerRec.NEXT = 0;  
```  

 Retrieving the count by using the first statement in the example is much faster because only one command to the Database Management System \(DBMS\) is needed.  

## See Also
[Table Data Type](table-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)