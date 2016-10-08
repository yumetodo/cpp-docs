---
title: "IRowsetImpl::GetDBStatus"
ms.custom: na
ms.date: 10/03/2016
ms.devlang: 
  - C++
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-cpp
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: e51d8ee2-fc0c-4909-861c-026c94fb0dfc
caps.latest.revision: 8
manager: ghogen
translation.priority.ht: 
  - cs-cz
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - pl-pl
  - pt-br
  - ru-ru
  - tr-tr
  - zh-cn
  - zh-tw
---
# IRowsetImpl::GetDBStatus
Returns the `DBSTATUS` status flags for the specified field.  
  
## Syntax  
  
```  
  
      virtual DBSTATUS GetDBStatus(  
   RowClass* currentRow,  
   ATLCOLUMNINFO* columnNames   
);  
```  
  
#### Parameters  
 [in] `currentRow`  
 The current row.  
  
 [in] `columnNames`  
 The column for which status is being requested.  
  
## Return Value  
 The [DBSTATUS](https://msdn.microsoft.com/en-us/library/ms722617.aspx) flags for the column.  
  
## Requirements  
 **Header:** atldb.h  
  
## See Also  
 [IRowsetImpl Class](../VS_visualcpp/IRowsetImpl-Class.md)