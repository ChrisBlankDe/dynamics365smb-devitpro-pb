---
title: "Length Method"
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
# Length Method
Retrieves the length of the text stored in this BigText instance.

## Syntax
```
Length :=   BigText.Length()
```
> [!NOTE]  
> This method can be invoked using property access syntax.  

## Parameters
*BigText*  
&emsp;Type: [BigText](bigtext-data-type.md)  
An instance of the [BigText](bigtext-data-type.md) data type.  

## Return Value
*Length*  
&emsp;Type: [Integer](../integer/integer-data-type.md)  
The length of the text stored in this BigText instance.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 To delete the content in a BigText variable use the [CLEAR Method](../../methods/devenv-clear-method.md). The syntax for the CLEAR method is shown in the following code snippet: `CLEAR(BigText)`.  
  
## Example  
 The following example demonstrates how to retrieve the length of a BigText variable. This example requires that you create the following global variables and text constant.  
  
|Variable name|DataType|  
|-------------------|--------------|  
|MyBigText|BigText|  
|VarLength|Integer|  
  
|Text constant name|ENU value|  
|------------------------|---------------|  
|Text000|VarLength = %1|  
  
 In this example, the BigText variable is initialized with the text ‘ABCDEFG’. The length, which is 7, is stored in the VarLength variable and displayed in a message box.  
  
```  
MyBigText.ADDTEXT('ABCDEFG');  
VarLength := MyBigText.LENGTH;  
MESSAGE(Text000, VarLength);  
  
```  
  

## See Also
[BigText Data Type](bigtext-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)