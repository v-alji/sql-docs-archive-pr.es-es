---
title: Definir relaciones de atributo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- attributes [Analysis Services], relationships
- relationships [Analysis Services], attributes
ms.assetid: 9184d344-e96d-4025-ad6f-3f75129746df
author: minewiskan
ms.author: owend
ms.openlocfilehash: a694c68a55de2533c4ce7791d3be865008b6321f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663170"
---
# <a name="define-attribute-relationships"></a><span data-ttu-id="7b9fa-102">Definir relaciones de atributo</span><span class="sxs-lookup"><span data-stu-id="7b9fa-102">Define Attribute Relationships</span></span>
  <span data-ttu-id="7b9fa-103">En [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , los atributos son el bloque de creación fundamental de una dimensión.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], attributes are the fundamental building block of a dimension.</span></span> <span data-ttu-id="7b9fa-104">Una dimensión contiene un conjunto de atributos que se organizan en función de las relaciones de atributo.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-104">A dimension contains a set of attributes that are organized based on attribute relationships.</span></span>  
  
 <span data-ttu-id="7b9fa-105">Para cada tabla incluida en una dimensión, hay una relación de atributo que relaciona el atributo clave de la tabla con otros atributos en esa tabla.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-105">For each table included in a dimension, there is an attribute relationship that relates the table's key attribute to other attributes from that table.</span></span> <span data-ttu-id="7b9fa-106">Esta relación la crea al crear la dimensión.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-106">You create this relationship when you create the dimension.</span></span>  
  
 <span data-ttu-id="7b9fa-107">Una relación de atributo proporciona las siguientes ventajas:</span><span class="sxs-lookup"><span data-stu-id="7b9fa-107">An attribute relationship provides the following advantages:</span></span>  
  
-   <span data-ttu-id="7b9fa-108">Reduce la cantidad de memoria necesaria para procesar la dimensión.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-108">Reduces the amount of memory needed for dimension processing.</span></span> <span data-ttu-id="7b9fa-109">Esto acelera el procesamiento de dimensiones, particiones y consultas.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-109">This speeds up dimension, partition, and query processing.</span></span>  
  
-   <span data-ttu-id="7b9fa-110">Aumenta el rendimiento de las consultas porque el acceso al almacenamiento es más rápido y se optimizan mejor los planes de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-110">Increases query performance because storage access is faster and execution plans are better optimized.</span></span>  
  
-   <span data-ttu-id="7b9fa-111">Hace que los algoritmos de diseños de agregaciones seleccionen agregados más efectivos, siempre y cuando las jerarquías definidas por el usuario se hayan establecido a lo largo de las rutas de acceso de la relación.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-111">Results in the selection of more effective aggregates by the aggregation design algorithms, provided that user-defined hierarchies have been defined along the relationship paths.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7b9fa-112">Para obtener más información acerca de la importancia e implicaciones de definir y configurar las relaciones de atributo, vea la sección "mejorar el rendimiento de las consultas" en la [Guía de rendimiento de SQL Server 2005 Analysis Services](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span><span class="sxs-lookup"><span data-stu-id="7b9fa-112">For more information about the importance and implications of defining and configuring attribute relationships, see the section, "Enhancing query performance," in the [SQL Server 2005 Analysis Services Performance Guide](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span></span>  
  
## <a name="attribute-relationship-considerations"></a><span data-ttu-id="7b9fa-113">Consideraciones sobre las relaciones de atributo</span><span class="sxs-lookup"><span data-stu-id="7b9fa-113">Attribute Relationship Considerations</span></span>  
 <span data-ttu-id="7b9fa-114">Si los datos subyacentes lo permiten, también debería definir relaciones de atributo únicas entre atributos.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-114">When the underlying data supports it, you should also define unique attribute relationships between attributes.</span></span> <span data-ttu-id="7b9fa-115">Para definir relaciones de atributo únicas, utilice la pestaña **Relación de los atributos** del Diseñador de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-115">To define unique attribute relationships, use the **Attribute Relationships** tab of Dimension Designer.</span></span>  
  
 <span data-ttu-id="7b9fa-116">Cualquier atributo que tenga una relación de salida debe tener una clave única relativa a su atributo relacionado.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-116">Any attribute that has an outgoing relationship must have a unique key relative to its related attribute.</span></span> <span data-ttu-id="7b9fa-117">En otras palabras, un miembro de un atributo de origen solo debe identificar un único miembro de un atributo relacionado.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-117">In other words, a member in a source attribute must identify one and only one member in a related attribute.</span></span> <span data-ttu-id="7b9fa-118">Por ejemplo, considere la relación, Ciudad -> Estado.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-118">For example, consider the relationship, City -> State.</span></span> <span data-ttu-id="7b9fa-119">En esta relación, el atributo de origen es Ciudad y el atributo relacionado es Estado.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-119">In this relationship, the source attribute is City and the related attribute is State.</span></span> <span data-ttu-id="7b9fa-120">El atributo de origen es el lado "varios" y el lado relacionado es el lado "uno" de la relación de varios a uno.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-120">The source attribute is the "many" side and the related side is the "one" side of the many-to-one relationship.</span></span> <span data-ttu-id="7b9fa-121">La clave para el atributo de origen sería Ciudad + Estado.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-121">The key for the source attribute would be City + State.</span></span> <span data-ttu-id="7b9fa-122">Para obtener más información, vea [Crear, modificar o eliminar una relación de atributo](attribute-relationships-create-modify-or-delete-relationship.md).</span><span class="sxs-lookup"><span data-stu-id="7b9fa-122">For more information, see [Create, Modify, or Delete an Attribute Relationship](attribute-relationships-create-modify-or-delete-relationship.md).</span></span>  
  
 <span data-ttu-id="7b9fa-123">Para obtener más información sobre las propiedades de una relación de atributo, vea [Configurar propiedades de relación de los atributos](attribute-relationships-configure-attribute-properties.md).</span><span class="sxs-lookup"><span data-stu-id="7b9fa-123">For more information about properties of an attribute relationship, see [Configure Attribute Relationship Properties](attribute-relationships-configure-attribute-properties.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7b9fa-124">Si las relaciones de atributo no se definen correctamente, puede que los resultados de las consultas no sean válidos.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-124">Defining attribute relationships incorrectly can cause invalid query results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b9fa-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7b9fa-125">See Also</span></span>  
 [<span data-ttu-id="7b9fa-126">Relaciones de atributo</span><span class="sxs-lookup"><span data-stu-id="7b9fa-126">Attribute Relationships</span></span>](../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md)  
  
  
