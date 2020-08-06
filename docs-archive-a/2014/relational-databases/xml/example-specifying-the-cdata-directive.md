---
title: 'Ejemplo: Especificación de la directiva CDATA | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- CDATA directive
ms.assetid: 949071e6-787f-480d-bb86-3ac16a027af1
author: rothja
ms.author: jroth
ms.openlocfilehash: 9b4f949ae1e9f309a13906efe44b329db2e47ec1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744017"
---
# <a name="example-specifying-the-cdata-directive"></a><span data-ttu-id="8a8d1-102">Ejemplo: Especificación de la directiva CDATA</span><span class="sxs-lookup"><span data-stu-id="8a8d1-102">Example: Specifying the CDATA Directive</span></span>
  <span data-ttu-id="8a8d1-103">Si se establece la directiva en **CDATA**, los datos contenidos no se codifican por entidad, pero se colocan en la sección CDATA.</span><span class="sxs-lookup"><span data-stu-id="8a8d1-103">If the directive is set to **CDATA**, the contained data is not entity encoded, but is put in the CDATA section.</span></span> <span data-ttu-id="8a8d1-104">Los atributos **CDATA** no deben tener nombre.</span><span class="sxs-lookup"><span data-stu-id="8a8d1-104">The **CDATA** attributes must be nameless.</span></span>  
  
 <span data-ttu-id="8a8d1-105">La siguiente consulta engloba la descripción resumida de modelos de productos en una sección CDATA.</span><span class="sxs-lookup"><span data-stu-id="8a8d1-105">The following query wraps the product model summary description in a CDATA section.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT  1 as Tag,  
        0 as Parent,  
        ProductModelID  as [ProductModel!1!ProdModelID],  
        Name            as [ProductModel!1!Name],  
        '<Summary>This is summary description</Summary>'     
            as [ProductModel!1!!CDATA] -- no attribute name so ELEMENT assumed  
FROM    Production.ProductModel  
WHERE   ProductModelID=19  
FOR XML EXPLICIT  
```  
  
 <span data-ttu-id="8a8d1-106">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="8a8d1-106">This is the result:</span></span>  
  
```  
<ProductModel ProdModelID="19" Name="Mountain-100">  
   <![CDATA[<Summary>This is summary description</Summary>]]>  
</ProductModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8a8d1-107">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8a8d1-107">See Also</span></span>  
 [<span data-ttu-id="8a8d1-108">Usar el modo EXPLICIT con FOR XML</span><span class="sxs-lookup"><span data-stu-id="8a8d1-108">Use EXPLICIT Mode with FOR XML</span></span>](use-explicit-mode-with-for-xml.md)  
  
  
