---
title: Consideraciones de seguridad de diagrama (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXML, updategrams
- security [SQLXML], updategrams
- updategrams [SQLXML], security
ms.assetid: 00dc6cf4-a2e8-4cca-bdd6-d5122102a82d
author: rothja
ms.author: jroth
ms.openlocfilehash: eb0319285e6e8cf6e8b3e70f3eb6b9923de06f55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675768"
---
# <a name="updategram-security-considerations-sqlxml-40"></a><span data-ttu-id="de29a-102">Consideraciones de seguridad sobre los diagramas de actualización (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="de29a-102">Updategram Security Considerations (SQLXML 4.0)</span></span>
  <span data-ttu-id="de29a-103">A continuación, se muestran una serie de instrucciones de seguridad para usar diagramas de actualización:</span><span class="sxs-lookup"><span data-stu-id="de29a-103">The following are security guidelines for using updategrams:</span></span>  
  
-   <span data-ttu-id="de29a-104">Evite el uso de la asignación predeterminada cuando utilice los diagramas de actualización para actualizar datos.</span><span class="sxs-lookup"><span data-stu-id="de29a-104">Avoid using default mapping when you use updategrams to update data.</span></span> <span data-ttu-id="de29a-105">Cuando se utiliza la asignación predeterminada, un nombre de elemento de un diagrama de actualización se asigna a un nombre de tabla y un nombre de atributo se asigna a una columna.</span><span class="sxs-lookup"><span data-stu-id="de29a-105">When you use default mapping, an element name in an updategram maps to a table name, and an attribute name maps to a column.</span></span> <span data-ttu-id="de29a-106">De esta forma, la información de la columna y la tabla de base de datos se expone en la base de datos, lo que puede suponer un riesgo potencial para la seguridad.</span><span class="sxs-lookup"><span data-stu-id="de29a-106">This exposes the database table and column information in the database, which can be a potential security risk.</span></span> <span data-ttu-id="de29a-107">En lugar de ello, si especifica un esquema de asignación independiente que asigne los elementos y atributos de un diagrama de actualización a las columnas y las tablas de base de datos, los nombres de los atributos y los elementos del diagrama de actualización pueden ser arbitrarios y el esquema realiza la asignación necesaria de estos nombres a las columnas y las tablas de base de datos.</span><span class="sxs-lookup"><span data-stu-id="de29a-107">Instead, if you specify a separate mapping schema that maps the elements and attributes in an updategram to the database tables and columns, your updategram element and attribute names can be arbitrary, and the schema does necessary mapping of these names to the database tables and columns.</span></span> <span data-ttu-id="de29a-108">Así, la información de la base de datos no se expone en un diagrama de actualización.</span><span class="sxs-lookup"><span data-stu-id="de29a-108">Thus, the database information is not exposed in an updategram.</span></span>  
  
-   <span data-ttu-id="de29a-109">No permita que los usuarios creen y ejecuten sus diagramas de actualización.</span><span class="sxs-lookup"><span data-stu-id="de29a-109">Do not allow users to create and execute their updategrams.</span></span> <span data-ttu-id="de29a-110">Es recomendable que los diagramas de actualización residan como plantillas en un servidor en lugar de crearlos dinámicamente en aplicaciones de tipo ASP, lo que podría poner en peligro los datos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="de29a-110">It is recommended having updategrams reside as templates on a server rather than creating them dynamically in ASP-type applications, which could put the data in the database at risk.</span></span> <span data-ttu-id="de29a-111">Permitir que los usuarios obtengan acceso a los datos solamente a través de los diagramas de actualización, suministrados como plantillas, puede eliminar este riesgo.</span><span class="sxs-lookup"><span data-stu-id="de29a-111">Allowing users to access the data only through the updategrams provided as templates, can eliminate this risk.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de29a-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="de29a-112">See Also</span></span>  
 [<span data-ttu-id="de29a-113">Utilizar los diagramas de actualización para modificar datos en SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="de29a-113">Using Updategrams to Modify Data in SQLXML 4.0</span></span>](../updategrams/using-updategrams-to-modify-data-in-sqlxml-4-0.md)  
  
  
