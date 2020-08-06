---
title: Creación de vistas sobre columnas XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- views [XML in SQL Server]
ms.assetid: eb5f0439-1f69-49c2-8759-e59bda1633b7
author: rothja
ms.author: jroth
ms.openlocfilehash: bf06f1107cbf4875eb63fe6747775b5c5c04810c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748689"
---
# <a name="create-views-over-xml-columns"></a><span data-ttu-id="f6405-102">Crear vistas sobre columnas XML</span><span class="sxs-lookup"><span data-stu-id="f6405-102">Create Views over XML Columns</span></span>
  <span data-ttu-id="f6405-103">Puede utilizar una columna de tipo `xml` para crear vistas.</span><span class="sxs-lookup"><span data-stu-id="f6405-103">You can use an `xml` type column to create views.</span></span> <span data-ttu-id="f6405-104">En el ejemplo siguiente se crea una vista en la que se recupera el valor de una columna de tipo `xml` mediante el método `value()` del tipo de datos `xml`.</span><span class="sxs-lookup"><span data-stu-id="f6405-104">The following example creates a view in which the value from an `xml` type column is retrieved using the `value()` method of the `xml` data type.</span></span>  
  
```  
-- Create the table.  
CREATE TABLE T (  
    ProductID          int primary key,   
    CatalogDescription xml)  
GO  
-- Insert sample data.  
INSERT INTO T values(1,'<ProductDescription ProductID="1" ProductName="SomeName" />')  
GO  
-- Create view (note the value() method used to retrieve ProductName   
-- attribute value from the XML).  
CREATE VIEW MyView AS   
  SELECT ProductID,  
         CatalogDescription.value('(/ProductDescription/@ProductName)[1]', 'varchar(40)') AS PName  
  FROM T  
GO   
```  
  
 <span data-ttu-id="f6405-105">Ejecute la consulta siguiente con la vista:</span><span class="sxs-lookup"><span data-stu-id="f6405-105">Execute the following query against the view:</span></span>  
  
```  
SELECT *   
FROM   MyView  
```  
  
 <span data-ttu-id="f6405-106">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="f6405-106">This is the result:</span></span>  
  
```  
ProductID   PName        
----------- ------------  
1           SomeName   
```  
  
 <span data-ttu-id="f6405-107">Tenga en cuenta los puntos siguientes sobre cómo utilizar el tipo de datos `xml` para crear las vistas:</span><span class="sxs-lookup"><span data-stu-id="f6405-107">Note the following points about using the `xml` data type to create views:</span></span>  
  
-   <span data-ttu-id="f6405-108">El tipo de datos xml se puede crear en una vista materializada.</span><span class="sxs-lookup"><span data-stu-id="f6405-108">The xml data type can be created in a materialized view.</span></span> <span data-ttu-id="f6405-109">La vista materializada no puede basarse en un método de tipo de datos xml.</span><span class="sxs-lookup"><span data-stu-id="f6405-109">The materialized view cannot be based on an xml data type method.</span></span> <span data-ttu-id="f6405-110">Sin embargo, puede convertirse en una colección de esquemas XML distinta del tipo de columna xml de la tabla base.</span><span class="sxs-lookup"><span data-stu-id="f6405-110">However, it can be cast to an XML schema collection that is different from the xml type column in the base table.</span></span>  
  
-   <span data-ttu-id="f6405-111">El tipo de datos `xml` no se puede utilizar en vistas distribuidas con particiones.</span><span class="sxs-lookup"><span data-stu-id="f6405-111">The `xml` data type cannot be used in Distributed Partitioned Views.</span></span>  
  
-   <span data-ttu-id="f6405-112">Los predicados de SQL que se ejecutan con la vista no se insertarán en la expresión XQuery de la definición de vista.</span><span class="sxs-lookup"><span data-stu-id="f6405-112">SQL predicates running against the view will not be pushed into the XQuery of the view definition.</span></span>  
  
-   <span data-ttu-id="f6405-113">Los métodos del tipo de datos XML de una vista no son actualizables.</span><span class="sxs-lookup"><span data-stu-id="f6405-113">XML data type methods in a view are not updatable.</span></span>  
  
  
