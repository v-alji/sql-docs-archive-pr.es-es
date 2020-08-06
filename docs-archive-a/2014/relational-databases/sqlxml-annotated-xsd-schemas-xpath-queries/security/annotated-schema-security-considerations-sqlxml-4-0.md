---
title: Consideraciones sobre la seguridad de esquemas anotados (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- mapping schema [SQLXML], security
- annotated XDR schemas, security
- XDR schemas [SQLXML], security
- annotations [SQLXML]
- annotated XSD schemas, security
- SQLXML, annotated XSD schemas
- SQLXML, annotated XDR schemas
- security [SQLXML], annotated schemas
- XSD schemas [SQLXML], security
ms.assetid: 7d7e44dc-b6d3-4e0f-95c7-8f99930c94f2
author: rothja
ms.author: jroth
ms.openlocfilehash: 098f554410a846ed0223d17117b51025dfcf7897
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662738"
---
# <a name="annotated-schema-security-considerations-sqlxml-40"></a><span data-ttu-id="03b41-102">Consideraciones de seguridad de esquemas anotados (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="03b41-102">Annotated Schema Security Considerations (SQLXML 4.0)</span></span>
  <span data-ttu-id="03b41-103">A continuación figuran las instrucciones de seguridad para utilizar esquemas anotados:</span><span class="sxs-lookup"><span data-stu-id="03b41-103">The following are security guidelines for using annotated schemas:</span></span>  
  
-   <span data-ttu-id="03b41-104">Evite el uso de asignaciones predeterminadas en los esquemas de asignación.</span><span class="sxs-lookup"><span data-stu-id="03b41-104">Avoid using default mapping in the mapping schemas.</span></span> <span data-ttu-id="03b41-105">La asignación predeterminada expone la información de la base de datos (nombres de tabla y columnas) en el documento XML resultante ya que, de forma predeterminada, los nombres de elementos se asignan a los nombres de tabla y los nombres de atributo se asignan a las nombres de columna.</span><span class="sxs-lookup"><span data-stu-id="03b41-105">The default mapping exposes the database information (table and column names) in the resulting XML document because, by default, the element names map to table names and attribute names map to column names.</span></span> <span data-ttu-id="03b41-106">Por lo tanto, cualquier usuario que vea el documento XML tendrá acceso a la información de tablas y columnas de la base de datos, lo que supone un riesgo de seguridad potencial.</span><span class="sxs-lookup"><span data-stu-id="03b41-106">Therefore, any user who sees the XML document has access to the table and column information in the database, presenting a potential security risk.</span></span> <span data-ttu-id="03b41-107">Para evitar este riesgo, especifique nombres de elementos y atributos arbitrarios en el esquema y use anotaciones para asignarlos explícitamente a las tablas y columnas.</span><span class="sxs-lookup"><span data-stu-id="03b41-107">To avoid this risk, specify arbitrary element and attribute names in the schema and use annotations to explicitly map them to the tables and columns.</span></span> <span data-ttu-id="03b41-108">Para obtener más información acerca del uso de la asignación predeterminada al crear esquemas XSD, vea [asignación predeterminada de elementos y atributos XSD a tablas y columnas &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-using/default-mapping-of-xsd-elements-and-attributes-to-tables-and-columns-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="03b41-108">For more information about using default mapping when you create XSD schemas, see [Default Mapping of XSD Elements and Attributes to Tables and Columns &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-using/default-mapping-of-xsd-elements-and-attributes-to-tables-and-columns-sqlxml-4-0.md).</span></span>  
  
-   <span data-ttu-id="03b41-109">Cuando se especifica una asignación explícita utilizando anotaciones, la información de bases de datos (como nombres de tablas y columnas) queda expuesta.</span><span class="sxs-lookup"><span data-stu-id="03b41-109">The explicit mapping specified using the annotations exposes the database information (such as table names and column names).</span></span> <span data-ttu-id="03b41-110">Por consiguiente, seguramente no quiera que estos esquemas estén disponibles de forma pública.</span><span class="sxs-lookup"><span data-stu-id="03b41-110">Therefore, you may not want to make these schemas available publicly.</span></span>  
  
-   <span data-ttu-id="03b41-111">Ciertas consultas como las especificadas contra esquemas de asignación con recursividad (especificadas utilizando la anotación `max-depth` establecida en un valor más alto) pueden tardar mucho más tiempo en ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="03b41-111">Certain queries such as those specified against mapping schema with recursion (specified using `max-depth` annotation set to a higher value) may take longer to execute.</span></span> <span data-ttu-id="03b41-112">Opcionalmente, puede especificar un límite de tiempo de espera estableciendo la propiedad tiempo de espera del comando (en segundos).</span><span class="sxs-lookup"><span data-stu-id="03b41-112">You can optionally specify a time-out limit by setting the Command Time Out property (in seconds).</span></span> <span data-ttu-id="03b41-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="03b41-113">For example:</span></span>  
  
    ```  
    cn.Open "Provider=SQLOLEDB;Server=localhost;Database=tempdb;Integrated Security=SSPI;Command Properties='Command Time Out=50';"  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="03b41-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="03b41-114">See Also</span></span>  
 [<span data-ttu-id="03b41-115">Esquemas XSD anotados en SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="03b41-115">Annotated XSD Schemas in SQLXML 4.0</span></span>](../../sqlxml/annotated-xsd-schemas/annotated-xsd-schemas-in-sqlxml-4-0.md)  
  
  
