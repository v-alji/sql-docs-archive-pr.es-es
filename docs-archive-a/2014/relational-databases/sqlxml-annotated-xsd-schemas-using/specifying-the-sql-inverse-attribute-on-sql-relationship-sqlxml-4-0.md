---
title: 'Especificar el atributo SQL: inverso en SQL: Relationship (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- sql:relationship
- bulk load [SQLXML]
- inverse attribute
- relationships [SQLXML], inverse orders
- relationship annotation
- XSD schemas [SQLXML], relationships
- annotated XSD schemas, relationships
- updategrams [SQLXML], relationships
- sql:inverse
ms.assetid: 08904cbd-9c86-493d-90c3-f5e1d13ce59d
author: rothja
ms.author: jroth
ms.openlocfilehash: 5b0781102371b98cced72a5a0edee70c9567c372
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672894"
---
# <a name="specifying-the-sqlinverse-attribute-on-sqlrelationship-sqlxml-40"></a><span data-ttu-id="2c925-102">Especificar el atributo sql:inverse en sql:relationship (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="2c925-102">Specifying the sql:inverse Attribute on sql:relationship (SQLXML 4.0)</span></span>
  <span data-ttu-id="2c925-103">El atributo `sql:inverse` solamente resulta útil cuando se utiliza el esquema XSD, ya sea para la carga masiva o por parte de un diagrama de actualización.</span><span class="sxs-lookup"><span data-stu-id="2c925-103">The `sql:inverse` attribute is useful only when the XSD schema is used for either bulk load or by an updategram.</span></span> <span data-ttu-id="2c925-104">El `sql:inverse` atributo se puede especificar en el **\<sql:relationship>** elemento.</span><span class="sxs-lookup"><span data-stu-id="2c925-104">The `sql:inverse` attribute can be specified on the **\<sql:relationship>** element.</span></span> <span data-ttu-id="2c925-105">En diagramas de actualización, la lógica del diagrama de actualización interpreta el esquema para determinar las tablas y columnas actualizadas mediante la operación del diagrama de actualización.</span><span class="sxs-lookup"><span data-stu-id="2c925-105">In updategrams, the updategram logic interprets the schema in determining the tables and columns that are updated by the updategram operation.</span></span> <span data-ttu-id="2c925-106">Las relaciones entre elementos primarios y secundarios que se especifican en el esquema determinan el orden en que se modifican (insertan o eliminan) los registros.</span><span class="sxs-lookup"><span data-stu-id="2c925-106">The parent-child relationships that are specified in the schema determine the order in which the records are modified (inserted or deleted).</span></span>  
  
 <span data-ttu-id="2c925-107">Si tiene un esquema XSD en el que la relación entre elementos primarios y secundarios se especifica en el orden inverso de la relación de clave principal y clave externa entre las columnas de base de datos correspondientes, se producirán errores en la operación de inserción o eliminación del diagrama de actualización debido a una infracción de clave principal o clave externa.</span><span class="sxs-lookup"><span data-stu-id="2c925-107">If you have an XSD schema in which the parent-child relationship is specified in the inverse order of the primary-key/foreign-key relationship between the corresponding database columns, the insert or delete updategram operation will fail because of the primary-key/foreign-key violation.</span></span> <span data-ttu-id="2c925-108">En tales casos, el `sql:inverse` atributo se especifica ( `sql:inverse="true"` ) en el **\<sql:relationship>** elemento y la lógica diagrama inversa su interpretación de la relación de elementos primarios y secundarios especificada en el esquema.</span><span class="sxs-lookup"><span data-stu-id="2c925-108">In such cases, the `sql:inverse` attribute is specified (`sql:inverse="true"`) in the **\<sql:relationship>** element, and the updategram logic inverses its interpretation of the parent-child relationship specified in the schema.</span></span>  
  
 <span data-ttu-id="2c925-109">El atributo `sql:inverse` toma un valor booleano (0=false, 1=true).</span><span class="sxs-lookup"><span data-stu-id="2c925-109">The `sql:inverse` attribute takes a Boolean value (0=false, 1=true).</span></span> <span data-ttu-id="2c925-110">Los valores permitidos son 0, 1, true y false.</span><span class="sxs-lookup"><span data-stu-id="2c925-110">The acceptable values are 0, 1, true, and false.</span></span>  
  
 <span data-ttu-id="2c925-111">Para obtener un ejemplo funcional del uso de la `sql:inverse` anotación, vea [especificar un esquema de asignación anotado en un diagrama](../sqlxml-annotated-xsd-schemas-xpath-queries/updategrams/specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="2c925-111">For a working sample using the `sql:inverse` annotation, see [Specifying an Annotated Mapping Schema in an Updategram](../sqlxml-annotated-xsd-schemas-xpath-queries/updategrams/specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c925-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2c925-112">See Also</span></span>  
 [<span data-ttu-id="2c925-113">Especificar relaciones mediante SQL: Relationship &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="2c925-113">Specifying Relationships Using sql:relationship &#40;SQLXML 4.0&#41;</span></span>](specifying-relationships-using-sql-relationship-sqlxml-4-0.md)  
  
  
