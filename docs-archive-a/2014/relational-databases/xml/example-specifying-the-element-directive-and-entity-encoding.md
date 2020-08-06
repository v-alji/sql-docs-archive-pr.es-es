---
title: 'Ejemplo: Especificar la directiva ELEMENT y la codificación de entidades | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- ELEMENT directive
- entity encoding [XML]
ms.assetid: 50cda5c1-7293-4080-93b3-872e3b8d484e
author: rothja
ms.author: jroth
ms.openlocfilehash: 4ba4e419d31aa7c02cc2dc8f19a3350c233f042b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744014"
---
# <a name="example-specifying-the-element-directive-and-entity-encoding"></a><span data-ttu-id="57250-102">Ejemplo: Especificación de la directiva ELEMENT y la codificación de entidades</span><span class="sxs-lookup"><span data-stu-id="57250-102">Example: Specifying the ELEMENT Directive and Entity Encoding</span></span>
  <span data-ttu-id="57250-103">Este ejemplo muestra la diferencia entre las directivas **ELEMENT** y **XML** .</span><span class="sxs-lookup"><span data-stu-id="57250-103">This example illustrates the difference between the **ELEMENT** and **XML** directives.</span></span> <span data-ttu-id="57250-104">La directiva **ELEMENT** crea entidades para los datos, pero la directiva **XML** no lo hace.</span><span class="sxs-lookup"><span data-stu-id="57250-104">The **ELEMENT** directive entitizes the data, but the **XML** directive does not.</span></span> <span data-ttu-id="57250-105">Al elemento \<Summary> se le asigna el XML, `<Summary>This is summary description</Summary>`, en la consulta.</span><span class="sxs-lookup"><span data-stu-id="57250-105">The \<Summary> element is assigned XML, `<Summary>This is summary description</Summary>`, in the query.</span></span>  
  
 <span data-ttu-id="57250-106">Considere esta consulta:</span><span class="sxs-lookup"><span data-stu-id="57250-106">Consider this query:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT  1 as Tag,  
        0 as Parent,  
        ProductModelID  as [ProductModel!1!ProdModelID],  
        Name            as [ProductModel!1!Name],  
        NULL            as [Summary!2!SummaryDescription!ELEMENT]  
FROM    Production.ProductModel  
WHERE   ProductModelID=19  
UNION ALL  
SELECT  2 as Tag,  
        1 as Parent,  
        ProductModelID,  
        NULL,  
       '<Summary>This is summary description</Summary>'  
FROM   Production.ProductModel  
WHERE  ProductModelID=19  
FOR XML EXPLICIT  
```  
  
 <span data-ttu-id="57250-107">Éste es el resultado.</span><span class="sxs-lookup"><span data-stu-id="57250-107">This is the result.</span></span> <span data-ttu-id="57250-108">Se crea una entidad en el resultado para la descripción resumida.</span><span class="sxs-lookup"><span data-stu-id="57250-108">The summary description is entitized in the result.</span></span>  
  
```  
<ProductModel ProdModelID="19" Name="Mountain-100">  
  <Summary>  
    <SummaryDescription><Summary>This is summary description</Summary></SummaryDescription>  
  </Summary>  
</ProductModel>  
```  
  
 <span data-ttu-id="57250-109">Ahora, si se especifica la directiva **XML** en el nombre de columna `Summary!2!SummaryDescription!XML`, en lugar de la directiva **ELEMENT** , se recibirá la descripción resumida sin la creación de entidades.</span><span class="sxs-lookup"><span data-stu-id="57250-109">Now, if you specify the **XML** directive in the column name, `Summary!2!SummaryDescription!XML`, instead of the **ELEMENT** directive, you will receive the summary description without entitization.</span></span>  
  
```  
<ProductModel ProdModelID="19" Name="Mountain-100">  
  <Summary>  
    <SummaryDescription>  
      <Summary>This is summary description</Summary>  
    </SummaryDescription>  
  </Summary>  
</ProductModel>  
```  
  
 <span data-ttu-id="57250-110">En lugar de asignar un valor XML estático, la consulta siguiente usa el método **query()** del tipo **xml** para recuperar la descripción resumida del modelo de productos de la columna CatalogDescription de tipo **xml** .</span><span class="sxs-lookup"><span data-stu-id="57250-110">Instead of assigning a static XML value, the following query uses the **query()** method of the **xml** type to retrieve the product model summary description from the CatalogDescription column of **xml** type.</span></span> <span data-ttu-id="57250-111">Como se sabe que el resultado es de tipo **xml** , no se aplica la creación de entidades.</span><span class="sxs-lookup"><span data-stu-id="57250-111">Because the result is known to be of **xml** type, no entitization is applied.</span></span>  
  
```  
SELECT  1 as Tag,  
        0 as Parent,  
        ProductModelID  as [ProductModel!1!ProdModelID],  
        Name            as [ProductModel!1!Name],  
        NULL            as [Summary!2!SummaryDescription]  
FROM    Production.ProductModel  
WHERE   CatalogDescription is not null  
UNION ALL  
SELECT  2 as Tag,  
        1 as Parent,  
        ProductModelID,  
        Name,  
       (SELECT CatalogDescription.query('  
            declare namespace pd="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
          /pd:ProductDescription/pd:Summary'))  
FROM     Production.ProductModel  
WHERE    CatalogDescription is not null  
ORDER BY [ProductModel!1!ProdModelID],Tag  
FOR XML EXPLICIT  
```  
  
## <a name="see-also"></a><span data-ttu-id="57250-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="57250-112">See Also</span></span>  
 [<span data-ttu-id="57250-113">Usar el modo EXPLICIT con FOR XML</span><span class="sxs-lookup"><span data-stu-id="57250-113">Use EXPLICIT Mode with FOR XML</span></span>](use-explicit-mode-with-for-xml.md)  
  
  
