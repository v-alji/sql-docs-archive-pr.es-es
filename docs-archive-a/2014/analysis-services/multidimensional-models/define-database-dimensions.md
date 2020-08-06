---
title: Definir dimensiones de base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- dimensions [Analysis Services], defining
ms.assetid: fe84588b-66a3-4100-a1cf-59b21b7adf01
author: minewiskan
ms.author: owend
ms.openlocfilehash: ad5334e71b0f133f80933a7d1702d8ada7565501
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744401"
---
# <a name="define-database-dimensions"></a><span data-ttu-id="53703-102">Definir dimensiones de base de datos</span><span class="sxs-lookup"><span data-stu-id="53703-102">Define Database Dimensions</span></span>
  <span data-ttu-id="53703-103">Use el diseñador de dimensiones de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] para configurar una dimensión de base de datos existente en un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] proyecto o base de datos de.</span><span class="sxs-lookup"><span data-stu-id="53703-103">Use Dimension Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] to configure an existing database dimension in a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or database.</span></span> <span data-ttu-id="53703-104">Puede usar el Diseñador de dimensiones para realizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="53703-104">You can use Dimension Designer to do the following:</span></span>  
  
-   <span data-ttu-id="53703-105">Configurar las propiedades de dimensión-nivel.</span><span class="sxs-lookup"><span data-stu-id="53703-105">Configure the dimension-level properties.</span></span>  
  
-   <span data-ttu-id="53703-106">Agregar y configurar atributos de dimensión.</span><span class="sxs-lookup"><span data-stu-id="53703-106">Add and configure dimension attributes.</span></span>  
  
-   <span data-ttu-id="53703-107">Definir y configurar jerarquías definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="53703-107">Define and configure user-defined hierarchies.</span></span>  
  
-   <span data-ttu-id="53703-108">Definir y configurar relaciones entre los atributos.</span><span class="sxs-lookup"><span data-stu-id="53703-108">Define and configure relationships between attributes.</span></span>  
  
-   <span data-ttu-id="53703-109">Definir las traducciones de las dimensiones.</span><span class="sxs-lookup"><span data-stu-id="53703-109">Define dimension translations.</span></span>  
  
-   <span data-ttu-id="53703-110">En dimensiones procesadas, puede examinar la estructura de la dimensión y ver sus datos.</span><span class="sxs-lookup"><span data-stu-id="53703-110">For processed dimensions, you can browse the dimension structure and view data.</span></span>  
  
 <span data-ttu-id="53703-111">Después de modificar una dimensión, un atributo o una jerarquía, debe procesar la dimensión para ver los cambios.</span><span class="sxs-lookup"><span data-stu-id="53703-111">After you modify a dimension, attribute, or hierarchy, you must process that dimension to view the changes.</span></span> <span data-ttu-id="53703-112">Al trabajar en modo de proyecto, el usuario implementa los cambios en la instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] antes del procesamiento.</span><span class="sxs-lookup"><span data-stu-id="53703-112">When working in project mode, you deploy the changes to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance before processing.</span></span>  
  
 <span data-ttu-id="53703-113">Para más información sobre cómo abrir una dimensión en el Diseñador de dimensiones, vea [Modificar o eliminar una dimensión de base de datos en el Explorador de soluciones](database-dimensions-modify-or-delete-a-database-dimension-in-solution-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="53703-113">For more information about how to open a dimension in Dimension Designer, see [Modify or Delete a Database Dimension in Solution Explorer](database-dimensions-modify-or-delete-a-database-dimension-in-solution-explorer.md).</span></span>  
  
 <span data-ttu-id="53703-114">El Diseñador de dimensiones tiene tres pestañas, que se describen en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="53703-114">Dimension Designer has three different tabs, which are described in the following table.</span></span>  
  
|<span data-ttu-id="53703-115">Pestaña</span><span class="sxs-lookup"><span data-stu-id="53703-115">Tab</span></span>|<span data-ttu-id="53703-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="53703-116">Description</span></span>|  
|---------|-----------------|  
|<span data-ttu-id="53703-117">**Estructura de dimensión**</span><span class="sxs-lookup"><span data-stu-id="53703-117">**Dimension Structure**</span></span>|<span data-ttu-id="53703-118">Use esta pestaña para trabajar con la estructura de una dimensión: para examinar o crear el esquema de la vista del origen de datos para una dimensión, trabajar con atributos y organizar atributos en jerarquías definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="53703-118">Use this tab to work with the structure of a dimension-to examine or create the data source view schema for a dimension, to work with attributes, and to organize attributes in user-defined hierarchies.</span></span>|  
|<span data-ttu-id="53703-119">**Relaciones de atributo**</span><span class="sxs-lookup"><span data-stu-id="53703-119">**Attribute Relationships**</span></span>|<span data-ttu-id="53703-120">Utilice esta pestaña para crear, modificar o eliminar las relaciones de atributo de una dimensión.</span><span class="sxs-lookup"><span data-stu-id="53703-120">Use this tab to create, modify, or delete the attribute relationships of a dimension.</span></span>|  
|<span data-ttu-id="53703-121">**Translations**</span><span class="sxs-lookup"><span data-stu-id="53703-121">**Translations**</span></span>|<span data-ttu-id="53703-122">Utilice esta pestaña para agregar y modificar traducciones de metadatos de dimensiones en distintos idiomas.</span><span class="sxs-lookup"><span data-stu-id="53703-122">Use this tab to add and edit translations of dimension metadata in different languages.</span></span>|  
|<span data-ttu-id="53703-123">**Browser**</span><span class="sxs-lookup"><span data-stu-id="53703-123">**Browser**</span></span>|<span data-ttu-id="53703-124">Utilice esta pestaña para examinar los miembros de una dimensión procesada y revisar las traducciones de metadatos de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="53703-124">Use this tab to examine the members of a processed dimension and to review translations of dimension metadata.</span></span>|  
  
 <span data-ttu-id="53703-125">En los siguientes temas se describen las tareas que puede realizar en el Diseñador de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="53703-125">The following topics describe the tasks that you can perform in Dimension Designer.</span></span>  
  
 [<span data-ttu-id="53703-126">Referencia de las propiedades de los atributos de dimensión</span><span class="sxs-lookup"><span data-stu-id="53703-126">Dimension Attribute Properties Reference</span></span>](dimension-attribute-properties-reference.md)  
 <span data-ttu-id="53703-127">Describe cómo definir y configurar un atributo de dimensión.</span><span class="sxs-lookup"><span data-stu-id="53703-127">Describes how to define and configure a dimension attribute.</span></span>  
  
 [<span data-ttu-id="53703-128">Crear jerarquías definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="53703-128">Create User-Defined Hierarchies</span></span>](user-defined-hierarchies-create.md)  
 <span data-ttu-id="53703-129">Describe cómo definir y configurar una jerarquía definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="53703-129">Describes how to define and configure a user-defined hierarchy.</span></span>  
  
 [<span data-ttu-id="53703-130">Definir relaciones de atributo</span><span class="sxs-lookup"><span data-stu-id="53703-130">Define Attribute Relationships</span></span>](attribute-relationships-define.md)  
 <span data-ttu-id="53703-131">Describe cómo definir y configurar una relación de atributo.</span><span class="sxs-lookup"><span data-stu-id="53703-131">Describes how to define and configure an attribute relationship.</span></span>  
  
 [<span data-ttu-id="53703-132">Usar el Asistente de Business Intelligence para mejorar dimensiones</span><span class="sxs-lookup"><span data-stu-id="53703-132">Use the Business Intelligence Wizard to Enhance Dimensions</span></span>](../use-the-business-intelligence-wizard-to-enhance-dimensions.md)  
 <span data-ttu-id="53703-133">Describe cómo mejorar una dimensión con el Asistente de Business Intelligence.</span><span class="sxs-lookup"><span data-stu-id="53703-133">Describes how to use the Business Intelligence Wizard to enhance a dimension.</span></span>  
  
  
