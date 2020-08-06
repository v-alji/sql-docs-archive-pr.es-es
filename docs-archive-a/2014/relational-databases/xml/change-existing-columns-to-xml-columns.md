---
title: Cambio de columnas existentes a columnas XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- tables [XML]
ms.assetid: 0d951424-9862-41fe-bd46-127f1c059bcb
author: rothja
ms.author: jroth
ms.openlocfilehash: 32447851fcfe2a54143a028a94539532bba6708d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662709"
---
# <a name="change-existing-columns-to-xml-columns"></a><span data-ttu-id="8c5fd-102">Cambiar columnas existentes a columnas XML</span><span class="sxs-lookup"><span data-stu-id="8c5fd-102">Change Existing Columns to XML Columns</span></span>
  <span data-ttu-id="8c5fd-103">La instrucción ALTER TABLE admite el tipo de datos `xml`.</span><span class="sxs-lookup"><span data-stu-id="8c5fd-103">The ALTER TABLE statement supports the `xml` data type.</span></span> <span data-ttu-id="8c5fd-104">Por ejemplo, puede cambiar cualquier columna de tipo de cadena al tipo de datos `xml`.</span><span class="sxs-lookup"><span data-stu-id="8c5fd-104">For example, you can alter any string type column to the `xml` data type.</span></span> <span data-ttu-id="8c5fd-105">Tenga en cuenta que, en estos casos, los documentos contenidos en la columna deben tener un formato correcto.</span><span class="sxs-lookup"><span data-stu-id="8c5fd-105">Note that in these cases, the documents contained in the column must be well formed.</span></span> <span data-ttu-id="8c5fd-106">Asimismo, si cambia el tipo de la columna de cadena a xml con tipo, los documentos de la columna se validarán con los esquemas XSD especificados.</span><span class="sxs-lookup"><span data-stu-id="8c5fd-106">Also, if you are changing the type of the column from string to typed xml, the documents in the column are validated against the specified XSD schemas.</span></span>  
  
```  
CREATE TABLE T (Col1 int primary key, Col2 nvarchar(max))  
GO  
INSERT INTO T   
VALUES (1, '<Root><Product ProductID="1"/></Root>')  
GO  
ALTER TABLE T   
ALTER COLUMN Col2 xml  
GO  
```  
  
 <span data-ttu-id="8c5fd-107">Puede cambiar una columna de tipo `xml` de XML sin tipo a XML con tipo.</span><span class="sxs-lookup"><span data-stu-id="8c5fd-107">You can change an `xml` type column from untyped XML to typed XML.</span></span> <span data-ttu-id="8c5fd-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8c5fd-108">For example:</span></span>  
  
```  
CREATE TABLE T (Col1 int primary key, Col2 xml)  
GO  
INSERT INTO T   
values (1, '<p1:ProductDescription ProductModelID="1"   
xmlns:p1="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription">  
            </p1:ProductDescription>')  
GO   
-- Make it a typed xml column by specifying a schema collection.  
ALTER TABLE T   
ALTER COLUMN Col2 xml (Production.ProductDescriptionSchemaCollection)  
GO  
```  
  
> [!NOTE]  
>  <span data-ttu-id="8c5fd-109">el script se ejecutará sobre la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] porque la colección de esquemas XML, `Production.ProductDescriptionSchemaCollection`, se crea como parte de la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8c5fd-109">The script will run against [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, because the XML schema collection, `Production.ProductDescriptionSchemaCollection`, is created as part of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
 <span data-ttu-id="8c5fd-110">En el ejemplo anterior, todas las instancias almacenadas en la columna se validan y se les asigna un tipo con los esquemas XSD de la colección especificada.</span><span class="sxs-lookup"><span data-stu-id="8c5fd-110">In the previous example, all the instances stored in the column are validated and typed against the XSD schemas in the specified collection.</span></span> <span data-ttu-id="8c5fd-111">Si la columna contiene una o varias instancias XML no válidas respecto al esquema especificado, la instrucción `ALTER TABLE` no se ejecutará y no podrá cambiar la columna XML sin tipo a XML con tipo.</span><span class="sxs-lookup"><span data-stu-id="8c5fd-111">If the column contains one or more XML instances that are invalid with regard to the specified schema, the `ALTER TABLE` statement will fail and you will not be able to change your untyped XML column into typed XML.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8c5fd-112">Si una tabla es de gran tamaño, la modificación de una columna de tipo `xml` puede resultar costosa.</span><span class="sxs-lookup"><span data-stu-id="8c5fd-112">If a table is large, modifying an `xml` type column can be costly.</span></span> <span data-ttu-id="8c5fd-113">Esto se debe a que se tiene que comprobar que el formato de cada documento es correcto y, además, se deben validar los de XML con tipo.</span><span class="sxs-lookup"><span data-stu-id="8c5fd-113">This is because each document must be checked for being well formed and, for typed XML, must also be validated.</span></span>  
  
 <span data-ttu-id="8c5fd-114">Para obtener más información sobre XML con tipo, vea [Comparar XML con tipo y XML sin tipo](compare-typed-xml-to-untyped-xml.md).</span><span class="sxs-lookup"><span data-stu-id="8c5fd-114">For more information about typed XML, see [Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md).</span></span>  
  
  
