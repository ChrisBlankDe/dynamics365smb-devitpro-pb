---
title: "IsCode Method"
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
# IsCode Method
Indicates whether an AL variant contains a Code variable.

## Syntax
```
Ok :=   Variant.IsCode()
```
> [!NOTE]  
> This method can be invoked using property access syntax.  

## Parameters
*Variant*  
&emsp;Type: [Variant](variant-data-type.md)  
An instance of the [Variant](variant-data-type.md) data type.  

## Return Value
*Ok*  
&emsp;Type: [Boolean](../boolean/boolean-data-type.md)  
**true** if the AL variant contains a Code variable, otherwise **false**.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Example  
 The following example determines whether an AL variant contains a code variable. The code initializes the MyCode variable with a string value. The MyCode variable is assigned to the variant variable that is named MyVariant. The **ISCODE** method determines whether the variant contains a code variable and stores the return value in the varResult variable. In this case, the variant contains a code variable so **true** is returned and displayed in a message box. The [ISTEXT Method (Variant)](../../methods/devenv-istext-method-variant.md) determines whether the variant contains a text variable. The return value is **false** because the variant does not contain a text. This example requires that you create the following global variables and text constants.  
  
|Variable name|DataType|Length|  
|-------------------|--------------|------------|  
|MyCode|Code|100|  
|MyVariant|Variant|Not applicable|  
|varResult|Boolean|Not applicable|  
  
|Text constant name|ConstValue|  
|------------------------|----------------|  
|Text000|Does the variant >%1\< contain a code variable? %2.|  
|Text001|Does the variant >%1\< contain a text variable? %2.|  
  
```  
MyCode := 'A1297';  
MyVariant :=  MyCode;  
varResult := MyVariant.ISCODE;  
MESSAGE(Text000,MyVariant,varResult);  
varResult := MyVariant.ISTEXT;  
MESSAGE(Text001,MyVariant,varResult);  
```  
  

## See Also
[Variant Data Type](variant-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)