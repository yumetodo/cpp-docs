---
title: "Add Member Function Wizard"
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
ms.assetid: 13b6defc-faa6-4d57-83db-9dd854cbea3d
caps.latest.revision: 6
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
# Add Member Function Wizard
This wizard adds a member function declaration to the header file and a stub member function implementation to the implementation file for the selected class.  
  
 Once you have added the member function using the wizard, you can edit the code in the development environment.  
  
 **Return type**  
 Sets the return type for the member function you are adding. You can provide your own return type, or you can select from the list of available types. For information about the types, see [Fundamental Types](../VS_visualcpp/Fundamental-Types---C---.md).  
  
||||  
|-|-|-|  
|`char`|`int`|`unsigned int`|  
|**double**|**long**|`unsigned long`|  
|**float**|**short**|`void`|  
|`HRESULT`|`unsigned char`||  
  
 **Function name**  
 Sets the name of the member function you are adding.  
  
 **Parameter type**  
 Sets the type of parameter you are adding for the member function, if the member function has parameters. You can provide your own parameter type, or you can select from the list of available types.  
  
||||  
|-|-|-|  
|`char`|`int`|`unsigned char`|  
|**double**|**long**|`unsigned int`|  
|**float**|**short**|`unsigned long`|  
  
 **Parameter name**  
 Sets the name of a parameter you are adding for the member function, if the member function has parameters.  
  
 **Parameter list**  
 Displays a list of parameters you have added to the member function. To add a parameter to the list, provide a type and name in the **Parameter type** and **Parameter name** boxes and click **Add**. To remove a parameter from the list, select the parameter and click **Remove**.  
  
 **Access**  
 Sets the access to the member function. Access modifiers are keywords that specify the access other classes have to the member function. See [Member-Access Control](../VS_visualcpp/Member-Access-Control--C---.md) for more information about specifying access. The member function access level is set to **public** by default.  
  
-   [public](../VS_visualcpp/public--C---.md)  
  
-   [protected](../VS_visualcpp/protected--C---.md)  
  
-   [private](../VS_visualcpp/private--C---.md)  
  
 Check whether the new member function is static or virtual, and whether it is inline or pure. If you set the member function to be pure, the `Virtual` check box is selected, and the **Inline** check box becomes unavailable. The default is a nonstatic, nonvirtual member function.  
  
|Option|Description|  
|------------|-----------------|  
|[Static](../Topic/Static%20\(C++\).md)|Specifies that the function acts like a global and can be called outside of the class, even with no class instantiation. The member function has no access to non-static members. A member function specified as `Static` cannot be virtual.|  
|[Virtual](../VS_visualcpp/virtual--C---.md)|Ensures that the correct member function is called for an object, regardless of the expression used to make the member function call. A member function specified as `Virtual` cannot be static.|  
|**Pure**|Indicates that no implementation is supplied for the virtual member function being declared; therefore, **Pure** can be specified only on virtual member functions. See [Class-Member Declaration Syntax](../Topic/Class-Member%20Declaration%20Syntax.md) for more information.<br /><br /> A class that contains at least one pure virtual member function is considered an abstract class. Classes derived from the abstract class must implement the pure virtual member function or they, too, are abstract classes.|  
|[Inline](../VS_visualcpp/Inline-Functions--C---.md)|Instructs the compiler to insert a copy of the member function body into each place the member function is called. A member function specified as **Inline** cannot be pure.|  
  
 **.cpp file**  
 Sets the file location where the stub member function implementation is written. By default, it is written to the .cpp file for the class to which the member function is added. Click the ellipsis button to change the file name. The member function implementation is added to the contents of the selected file.  
  
 **Comment**  
 Provides a comment in the header file for the member function.  
  
 **Function signature**  
 Displays the member function as it appears in the code when you click **Finish**. You cannot edit the text in this box. To change the member function, change the appropriate boxes in the wizard.  
  
## See Also  
 [Adding a Member Function](../VS_visualcpp/Adding-a-Member-Function--Visual-C---.md)