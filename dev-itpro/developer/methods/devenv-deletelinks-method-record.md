---
title: "DELETELINKS Method (Record)"
ms.custom: na
ms.date: 10/01/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: dynamics365-business-central
ms.assetid: 84041383-ddd5-4762-8298-5ebbee2ac562
author: SusanneWindfeldPedersen
manager: edupont
redirect_url: /dynamics365/business-central/dev-itpro/developer/methods-auto/library
---

 

# DELETELINKS Method (Record)
Deletes all of the links that have been added to a record.  
  
## Syntax  
  
```  
  
Record.DELETELINKS  
```  
  
#### Parameters  
 *Record*  
 Type: Record  
  
 The record that contains the links to delete.  
  
## Example  
 The following example removes all the links from the specified record \(number 30000\) in the Vendor table. This example requires that you create the following global variable.  
  
|Variable name|DataType|Subtype|  
|-------------------|--------------|-------------|  
|MyRecord|Record|Vendor|  
  
```  
  
MyRecord.GET('30000');  
MyRecord.DELETELINKS;  
  
```  
  
## See Also  
 [DELETELINKS Method \(RecordRef\)](devenv-DELETELINKS-Method-RecordRef.md)   
 [Record Data Type](../datatypes/devenv-Record-Data-Type.md)