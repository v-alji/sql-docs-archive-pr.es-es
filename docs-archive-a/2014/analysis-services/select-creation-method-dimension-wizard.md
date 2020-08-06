---
title: Seleccionar método de creación (Asistente para dimensiones) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.dimensiondefinition.f1
ms.assetid: 291b0b2d-a03a-4df6-82f7-90ad92d4d1cf
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6338a0bde7865482fb7a98d7ec36ba5a71feb806
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744384"
---
# <a name="select-creation-method-dimension-wizard"></a><span data-ttu-id="836b5-102">Seleccionar método de creación (Asistente para dimensiones)</span><span class="sxs-lookup"><span data-stu-id="836b5-102">Select Creation Method (Dimension Wizard)</span></span>
  <span data-ttu-id="836b5-103">Use la página **Seleccionar método de creación** para seleccionar cómo se crea la dimensión.</span><span class="sxs-lookup"><span data-stu-id="836b5-103">Use the **Select Creation Method** page to select how to create the dimension.</span></span>  
  
 <span data-ttu-id="836b5-104">**Para abrir el Asistente para dimensiones**</span><span class="sxs-lookup"><span data-stu-id="836b5-104">**To open the Dimension Wizard**</span></span>  
  
-   <span data-ttu-id="836b5-105">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], en el **Explorador de soluciones**, haga clic con el botón derecho en la carpeta **Dimensiones** para un proyecto de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] y, luego, haga clic en **Nueva dimensión**.</span><span class="sxs-lookup"><span data-stu-id="836b5-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in **Solution Explorer**, right-click the **Dimensions** folder for an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, and then click **New Dimension**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="836b5-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="836b5-106">Options</span></span>  
 <span data-ttu-id="836b5-107">**Usar una tabla existente**</span><span class="sxs-lookup"><span data-stu-id="836b5-107">**Use an existing table**</span></span>  
 <span data-ttu-id="836b5-108">Cree una dimensión a partir de una o más tablas en un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="836b5-108">Create a dimension from one or more tables in a data source.</span></span> <span data-ttu-id="836b5-109">Los atributos que están disponibles para la dimensión dependerán de la estructura de los datos de la tabla.</span><span class="sxs-lookup"><span data-stu-id="836b5-109">The attributes that are available for the dimension will depend on the structure of the data in the table.</span></span>  
  
 <span data-ttu-id="836b5-110">Para más información, vea [Crear una dimensión usando una tabla existente](multidimensional-models/create-a-dimension-by-using-an-existing-table.md).</span><span class="sxs-lookup"><span data-stu-id="836b5-110">For more information, see [Create a Dimension by Using an Existing Table](multidimensional-models/create-a-dimension-by-using-an-existing-table.md).</span></span>  
  
 <span data-ttu-id="836b5-111">**Generar una tabla de tiempos en el origen de datos**</span><span class="sxs-lookup"><span data-stu-id="836b5-111">**Generate a time table in the data source**</span></span>  
 <span data-ttu-id="836b5-112">Cree una tabla de tiempos en el origen de datos subyacente y, a continuación, use dicha tabla para crear una dimensión de tiempo.</span><span class="sxs-lookup"><span data-stu-id="836b5-112">Create a time table in the underlying data source and then use that table to create a time dimension.</span></span> <span data-ttu-id="836b5-113">Use esta opción cuando no existe dicha tabla y no desea usar un script para crear una.</span><span class="sxs-lookup"><span data-stu-id="836b5-113">Use this option when no such table exists and you do not want to use a script to create one.</span></span> <span data-ttu-id="836b5-114">La nueva tabla de tiempos contendrá datos para el intervalo de fechas, atributos y calendarios que especifica en el asistente.</span><span class="sxs-lookup"><span data-stu-id="836b5-114">The new time table will contain data for the date range, attributes, and calendars that you specify in the wizard.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="836b5-115">Para usar esta opción, debe tener permiso para crear objetos en el origen de datos subyacente.</span><span class="sxs-lookup"><span data-stu-id="836b5-115">To use this option, you must have permission to create objects in the underlying data source.</span></span> <span data-ttu-id="836b5-116">Si no tiene permiso para crear objetos en el origen de datos, intente usar la opción **Generar una tabla de tiempos en el servidor** en su lugar</span><span class="sxs-lookup"><span data-stu-id="836b5-116">If you do not have permission to create objects on the data source, try to use the **Generate a time table on the server** option instead.</span></span>  
  
 <span data-ttu-id="836b5-117">Para más información, vea [Crear una dimensión de tiempo generando una tabla de tiempos](multidimensional-models/create-a-time-dimension-by-generating-a-time-table.md).</span><span class="sxs-lookup"><span data-stu-id="836b5-117">For more information, see [Create a Time Dimension by Generating a Time Table](multidimensional-models/create-a-time-dimension-by-generating-a-time-table.md).</span></span>  
  
 <span data-ttu-id="836b5-118">**Generar una tabla de tiempos en el servidor**</span><span class="sxs-lookup"><span data-stu-id="836b5-118">**Generate a time table on the server**</span></span>  
 <span data-ttu-id="836b5-119">Cree una tabla de tiempos directamente en el servidor y, a continuación, use dicha tabla para crear una dimensión de tiempos.</span><span class="sxs-lookup"><span data-stu-id="836b5-119">Create a time table directly on the server and then use that table to create a time dimension.</span></span> <span data-ttu-id="836b5-120">Use esta opción si no tiene permiso para crear objetos en el origen de datos subyacente.</span><span class="sxs-lookup"><span data-stu-id="836b5-120">Use this option if you do not have permission to create objects in the underlying data source.</span></span> <span data-ttu-id="836b5-121">La nueva dimensión de tiempos contendrá datos para el intervalo de fechas, atributos y calendarios que especifica en el asistente.</span><span class="sxs-lookup"><span data-stu-id="836b5-121">The new time dimension will contain data for the date range, attributes, and calendars that you specify in the wizard.</span></span>  
  
 <span data-ttu-id="836b5-122">Para más información, vea [Crear una dimensión de tiempo generando una tabla de tiempos](multidimensional-models/create-a-time-dimension-by-generating-a-time-table.md).</span><span class="sxs-lookup"><span data-stu-id="836b5-122">For more information, see [Create a Time Dimension by Generating a Time Table](multidimensional-models/create-a-time-dimension-by-generating-a-time-table.md).</span></span>  
  
 <span data-ttu-id="836b5-123">**Generar una tabla que no sea de tiempos en el origen de datos**</span><span class="sxs-lookup"><span data-stu-id="836b5-123">**Generate a non-time table in the data source**</span></span>  
 <span data-ttu-id="836b5-124">Diseñe la dimensión sin un origen de datos relacional subyacente y, a continuación, genere el esquema necesario para el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="836b5-124">Design the dimension without an underlying relational data source, and then generate the necessary schema for the data source.</span></span> <span data-ttu-id="836b5-125">Este enfoque se conoce como modelado de arriba a abajo.</span><span class="sxs-lookup"><span data-stu-id="836b5-125">This approach is known as top-down modeling.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="836b5-126">Para usar esta opción, debe tener permiso para crear objetos en el origen de datos subyacente.</span><span class="sxs-lookup"><span data-stu-id="836b5-126">To use this option, you must have permission to create objects in the underlying data source.</span></span>  
  
 <span data-ttu-id="836b5-127">Puede generar la dimensión con o sin una plantilla.</span><span class="sxs-lookup"><span data-stu-id="836b5-127">You can build the dimension with or without a template.</span></span> <span data-ttu-id="836b5-128">Para generar la dimensión con una plantilla, seleccione la plantilla en la lista **Plantilla** .</span><span class="sxs-lookup"><span data-stu-id="836b5-128">To build the dimension with a template, select the template from the **Template** list.</span></span>  
  
 <span data-ttu-id="836b5-129">Para más información, vea [Crear una dimensión generando una tabla que no sea de tiempos en el origen de datos](multidimensional-models/create-a-dimension-by-generating-a-non-time-table-in-the-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="836b5-129">For more information, see [Create a Dimension by Generating a Non-Time Table in the Data Source](multidimensional-models/create-a-dimension-by-generating-a-non-time-table-in-the-data-source.md).</span></span>  
  
 <span data-ttu-id="836b5-130">**Plantilla**</span><span class="sxs-lookup"><span data-stu-id="836b5-130">**Template**</span></span>  
 <span data-ttu-id="836b5-131">Seleccione la plantilla que desea usar para crear la dimensión.</span><span class="sxs-lookup"><span data-stu-id="836b5-131">Select the template that you want to use to create the dimension.</span></span> <span data-ttu-id="836b5-132">Las plantillas proporcionan un completo conjunto de atributos y definiciones de jerarquías orientadas a un fin empresarial específico.</span><span class="sxs-lookup"><span data-stu-id="836b5-132">Templates provide a complete set of attribute and hierarchy definitions oriented towards a specific business purpose.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="836b5-133">Esta opción solo está disponible cuando se ha seleccionado la opción **Generar una tabla que no sea de tiempos en el origen de datos** .</span><span class="sxs-lookup"><span data-stu-id="836b5-133">This option is only available when the **Generate a non-time table in the data source** option has been selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="836b5-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="836b5-134">See Also</span></span>  
 <span data-ttu-id="836b5-135">[Asistente para dimensiones (ayuda F1)](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="836b5-135">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="836b5-136">[Dimensiones &#40;Analysis Services de datos multidimensionales&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="836b5-136">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="836b5-137">Dimensiones en modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="836b5-137">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
