---
title: Consideraciones de seguridad de FOR XML (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- NESTED mode
- client-side XML formatting
- FOR XML clause, security
- server-side XML formatting
- AUTO mode
- security [SQLXML], FOR XML
ms.assetid: facba279-df93-475b-ad43-0043dc5bae03
author: rothja
ms.author: jroth
ms.openlocfilehash: 9a64fa61848e4b5435b2aa944c53953a8c083ab6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675773"
---
# <a name="for-xml-security-considerations-sqlxml-40"></a><span data-ttu-id="63988-102">Consideraciones de seguridad de FOR XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="63988-102">FOR XML Security Considerations (SQLXML 4.0)</span></span>
  <span data-ttu-id="63988-103">El modo AUTO de FOR XML genera una jerarquía XML en la que los nombres de elemento se asignan a nombres de tabla y los nombres de atributos se asignan a nombres de columna.</span><span class="sxs-lookup"><span data-stu-id="63988-103">The FOR XML AUTO mode generates an XML hierarchy in which element names map to table names and attribute names map to column names.</span></span> <span data-ttu-id="63988-104">Esto expone la información de las tablas y columnas de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="63988-104">This exposes the database table and column information.</span></span> <span data-ttu-id="63988-105">Puede ocultar la información de la base de datos con el modo AUTO (formato aplicado en el servidor) especificando alias de tabla y columna en la consulta.</span><span class="sxs-lookup"><span data-stu-id="63988-105">You can hide the database information when you use AUTO mode (server-side formatting) by specifying table and column aliases in the query.</span></span> <span data-ttu-id="63988-106">Estos alias se devuelven en el documento XML resultante como nombres de elemento y atributo.</span><span class="sxs-lookup"><span data-stu-id="63988-106">These aliases are returned in the resulting XML document as element and attribute names.</span></span>  
  
 <span data-ttu-id="63988-107">Por ejemplo, la consulta siguiente especifica el modo AUTO; por tanto, la aplicación de formato XML se realiza en el servidor:</span><span class="sxs-lookup"><span data-stu-id="63988-107">For example, the following query specifies AUTO mode; therefore, the XML formatting is done on the server:</span></span>  
  
```  
SELECT C.FirstName as F,C.LastName as L   
FROM Person.Contact C   
FOR XML AUTO  
```  
  
 <span data-ttu-id="63988-108">En el documento XML resultante, los alias se utilizan para los nombres de elemento y atributo:</span><span class="sxs-lookup"><span data-stu-id="63988-108">In the resulting XML document, the aliases are used for element and attribute names:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<root>  
  <C F="Nancy" L="Fuller" />   
  <CE F="Andrew" L="Peacock" />   
  <C F="Janet" L="Leverling" />   
  ...  
</root>  
```  
  
 <span data-ttu-id="63988-109">Al utilizar el modo NESTED (formato aplicado del lado cliente), los alias solo se devuelven para los atributos en el documento XML resultante.</span><span class="sxs-lookup"><span data-stu-id="63988-109">When you use NESTED mode (client-side formatting), aliases are returned only for attributes in the resulting XML document.</span></span> <span data-ttu-id="63988-110">Los nombres de las tablas base siempre se devuelven como nombres de elemento.</span><span class="sxs-lookup"><span data-stu-id="63988-110">The names of the base tables are always returned as element names.</span></span> <span data-ttu-id="63988-111">Por ejemplo, la consulta siguiente especifica el modo NESTED.</span><span class="sxs-lookup"><span data-stu-id="63988-111">For example, the following query specifies NESTED mode.</span></span>  
  
```  
SELECT C.FirstName as F,C.LastName as L   
FROM Person.Contact C   
FOR XML AUTO  
```  
  
 <span data-ttu-id="63988-112">En el documento XML resultante, los nombres de las tablas base se devuelven como nombres de elemento y no se utilizan alias de tabla:</span><span class="sxs-lookup"><span data-stu-id="63988-112">In the resulting XML document, the names of the base tables are returned as element names and table aliases are not used:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<root>  
  <Person.Contact F="Nancy" L="Fuller" />   
  <Person.Contact F="Andrew" L="Peacock" />   
  <Person.Contact F="Janet" L="Leverling" />   
       ...  
</root>  
```  
  
  
