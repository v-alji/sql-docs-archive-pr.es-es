---
title: 'Ejemplo: Especificación de la directiva ELEMENT | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- ELEMENT directive
ms.assetid: 80dd5d1f-fa90-4f97-a186-8fa3f460a7f3
author: rothja
ms.author: jroth
ms.openlocfilehash: a03d1049fa9df23eff759634bcd74f88f842a8e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744009"
---
# <a name="example-specifying-the-element-directive"></a><span data-ttu-id="72859-102">Ejemplo: Especificación de la directiva ELEMENT</span><span class="sxs-lookup"><span data-stu-id="72859-102">Example: Specifying the ELEMENT Directive</span></span>
  <span data-ttu-id="72859-103">Se recupera información de los empleados y se genera XML centrado en elementos como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="72859-103">This retrieves employee information and generates element-centric XML as shown in the following:</span></span>  
  
```  
<Employee EmpID=...>  
  <Name>  
    <FName>...</FName>  
    <LName>...</LName>  
  </Name>  
</Employee>  
```  
  
 <span data-ttu-id="72859-104">La consulta solo cambia en que se agrega la directiva `ELEMENT` en los nombres de columna.</span><span class="sxs-lookup"><span data-stu-id="72859-104">The query remains the same, except you add the `ELEMENT` directive in the column names.</span></span> <span data-ttu-id="72859-105">Por lo tanto, en lugar de atributos, se agregan los elementos secundarios <`FName`> y <`LName`> al elemento <`Name`>.</span><span class="sxs-lookup"><span data-stu-id="72859-105">Therefore, instead of attributes, the <`FName`> and <`LName`> element children are added to the <`Name`> element.</span></span> <span data-ttu-id="72859-106">Puesto que la columna `Employee!1!EmpID` no especifica la directiva `ELEMENT`, `EmpID` se agrega como atributo del elemento <`Employee`>.</span><span class="sxs-lookup"><span data-stu-id="72859-106">Because the `Employee!1!EmpID` column does not specify the `ELEMENT` directive, `EmpID` is added as the attribute of the <`Employee`> element.</span></span>  
  
```  
SELECT 1    as Tag,  
       NULL as Parent,  
       E.BusinessEntityID as [Employee!1!EmpID],  
       NULL       as [Name!2!FName!ELEMENT],  
       NULL       as [Name!2!LName!ELEMENT]  
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P  
ON  E.BusinessEntityID = P.BusinessEntityID  
UNION ALL  
SELECT 2 as Tag,  
       1 as Parent,  
       E.BusinessEntityID,  
       FirstName,   
       LastName   
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P  
ON  E.BusinessEntityID = P.BusinessEntityID  
ORDER BY [Employee!1!EmpID],[Name!2!FName!ELEMENT]  
FOR XML EXPLICIT;  
```  
  
 <span data-ttu-id="72859-107">El resultado parcial es el siguiente.</span><span class="sxs-lookup"><span data-stu-id="72859-107">This is the partial result.</span></span>  
  
 `<Employee EmpID="1">`  
  
 `<Name>`  
  
 `<FName>Ken</FName>`  
  
 `<LName>S??nchez</LName>`  
  
 `</Name>`  
  
 `</Employee>`  
  
 `<Employee EmpID="2">`  
  
 `<Name>`  
  
 `<FName>Terri</FName>`  
  
 `<LName>Duffy</LName>`  
  
 `</Name>`  
  
 `</Employee>`  
  
 `...`  
  
## <a name="see-also"></a><span data-ttu-id="72859-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="72859-108">See Also</span></span>  
 [<span data-ttu-id="72859-109">Usar el modo EXPLICIT con FOR XML</span><span class="sxs-lookup"><span data-stu-id="72859-109">Use EXPLICIT Mode with FOR XML</span></span>](use-explicit-mode-with-for-xml.md)  
  
  
