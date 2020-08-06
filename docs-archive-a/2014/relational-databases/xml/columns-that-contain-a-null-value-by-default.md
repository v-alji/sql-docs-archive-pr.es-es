---
title: Columnas que incluyen un valor NULL de forma predeterminada | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- columns [XML in SQL Server], null default value
ms.assetid: 9381c07f-6887-4a62-9730-32661f9aa87c
author: rothja
ms.author: jroth
ms.openlocfilehash: 92ea51101f73695be2075a1b41deb62ca021f496
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662700"
---
# <a name="columns-that-contain-a-null-value-by-default"></a><span data-ttu-id="65b47-102">Columnas que incluyen un valor NULL de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="65b47-102">Columns that Contain a Null Value By Default</span></span>
  <span data-ttu-id="65b47-103">De forma predeterminada, un valor NULL en una columna se asigna a la ausencia del atributo, nodo u elemento.</span><span class="sxs-lookup"><span data-stu-id="65b47-103">By default, a null value in a column maps to the absence of the attribute, node, or element.</span></span> <span data-ttu-id="65b47-104">Este comportamiento predeterminado se puede sobrescribir solicitando XML centrado en elementos mediante la directiva ELEMENTS y especificando XSINIL a fin de solicitar la adición de elementos para valores NULL, tal y como se muestra en la consulta siguiente:</span><span class="sxs-lookup"><span data-stu-id="65b47-104">This default behavior can be overwritten by requesting element-centric XML using the ELEMENTS directive and specifying XSINIL to request adding elements for NULL values, as shown in the following query:</span></span>  
  
```  
SELECT EmployeeID as "@EmpID",   
       FirstName  as "EmpName/First",   
       MiddleName as "EmpName/Middle",   
       LastName   as "EmpName/Last"  
FROM   HumanResources.Employee E, Person.Contact C  
WHERE  E.EmployeeID = C.ContactID  
AND    E.EmployeeID=1  
FOR XML PATH, ELEMENTS XSINIL  
```  
  
 <span data-ttu-id="65b47-105">A continuación se muestra el resultado.</span><span class="sxs-lookup"><span data-stu-id="65b47-105">The following shows the result.</span></span> <span data-ttu-id="65b47-106">Tenga en cuenta que si no se especifica XSINIL, el elemento <`Middle`> estará ausente.</span><span class="sxs-lookup"><span data-stu-id="65b47-106">Note that if XSINIL is not specified, the <`Middle`> element will be absent.</span></span>  
  
```  
<row xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" EmpID="1">  
  <EmpName>  
    <First>Gustavo</First>  
    <Middle xsi:nil="true" />  
    <Last>Achong</Last>  
  </EmpName>  
</row>  
```  
  
## <a name="see-also"></a><span data-ttu-id="65b47-107">Consulte también</span><span class="sxs-lookup"><span data-stu-id="65b47-107">See Also</span></span>  
 [<span data-ttu-id="65b47-108">Usar el modo PATH con FOR XML</span><span class="sxs-lookup"><span data-stu-id="65b47-108">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
