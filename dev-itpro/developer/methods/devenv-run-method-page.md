---
title: "RUN Method (Page)"
ms.custom: na
ms.date: 10/01/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: dynamics365-business-central
ms.assetid: 892a00dd-6fac-4454-bfae-6a5d5f37f0ff
caps.latest.revision: 9
manager: edupont
redirect_url: /dynamics365/business-central/dev-itpro/developer/methods-auto/library
---

 

# RUN Method (Page)
Creates and launches a page that you specify. You can use [CLEAR Method](devenv-CLEAR-Method.md) to remove the page.  
  
## Syntax  
  
```  
  
Page.RUN  
```  
  
#### Parameters  
 *Page*  
 Type: Page  
  
 After you define this variable, you can run the following page methods:  
  
-   SETTABLEVIEW  
  
-   SETRECORD  
  
-   GETRECORD  
  
-   RUN  
  
-   RUNMODAL.  
  
 The variable is automatically cleared after this method is executed.  
  
 If the page you specify does not exist, you receive a compile error.  
  
## Remarks  
 If, at design time, you know the specific page that you want to run, then you can create a Page variable, set the Subtype of the variable to a specific page, and then use this method or the [RUNMODAL Method \(Page\)](devenv-RUNMODAL-Method-Page.md) on the Page variable.  
  
 If you do not know the page that you want to run, then use the [PAGE.RUN Method](devenv-PAGE-RUN-Method.md) or the [PAGE.RUNMODAL Method](devenv-PAGE-RUNMODAL-Method.md) and specify the page in the *Number* parameter.  
  
 After you define the page variable, you can use it before you run the page. If you use the [RUNMODAL Method \(Page\)](devenv-RUNMODAL-Method-Page.md), you can use the variable before and after you run the page.  
  
## Example  
 This example shows how to use the **RUN** method. Assume the variable MyPage has been defined as Page 1.  
  
```  
MyPage.XXX; // any user-defined method  
MyPage.SETTABLEVIEW(MyRecord);  
MyPage.SETRECORD(MyRecord);  
MyPage.RUN;  
```  
  
## See Also  
 [Page Data Type](../datatypes/devenv-Page-Data-Type.md)