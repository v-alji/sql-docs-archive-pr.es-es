---
title: Seleccionar tablas y vistas (Asistente para vistas del origen de datos) (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.datasourceviewwizard.selecttablesandviews.f1
ms.assetid: ea7d1232-f213-46e9-90d9-0fd616ca003d
author: minewiskan
ms.author: owend
ms.openlocfilehash: ac7159255ef526d871ed8906fc873d9f16d2eb64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748958"
---
# <a name="select-tables-and-views-data-source-view-wizard-analysis-services"></a><span data-ttu-id="94993-102">Seleccionar las tablas y vistas (Asistente para vistas del origen de datos) (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="94993-102">Select Tables and Views (Data Source View Wizard) (Analysis Services)</span></span>
  <span data-ttu-id="94993-103">Utilice la página **Seleccionar tablas y vistas** para seleccionar las tablas o las vistas del origen de datos que desea incluir en la vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="94993-103">Use the **Select Tables and Views** page to select the tables or views from the data source that you want to include in the data source view.</span></span>  
  
## <a name="options"></a><span data-ttu-id="94993-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="94993-104">Options</span></span>  
 <span data-ttu-id="94993-105">**Available objects**</span><span class="sxs-lookup"><span data-stu-id="94993-105">**Available objects**</span></span>  
 <span data-ttu-id="94993-106">Enumera las tablas y vistas del esquema del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="94993-106">Lists the tables and views in the data source schema.</span></span> <span data-ttu-id="94993-107">Si se enumera más de un objeto, el nombre del esquema utiliza un prefijo en el nombre de cada objeto.</span><span class="sxs-lookup"><span data-stu-id="94993-107">The schema name prefixes the name of every object if more than one schema is listed.</span></span> <span data-ttu-id="94993-108">Si solo se enumera uno, el nombre del esquema no utiliza ningún prefijo en los nombres de objeto.</span><span class="sxs-lookup"><span data-stu-id="94993-108">If only one schema is listed, the schema's name does not prefix the object names.</span></span>  
  
 <span data-ttu-id="94993-109">Para ordenar la lista en sentido ascendente o descendente, haga clic en **Nombre** o **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="94993-109">To reorder the list in ascending or descending order, click either **Name** or **Type**.</span></span>  
  
 <span data-ttu-id="94993-110">**Included objects**</span><span class="sxs-lookup"><span data-stu-id="94993-110">**Included objects**</span></span>  
 <span data-ttu-id="94993-111">Enumera las tablas y vistas que deben incluirse en la vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="94993-111">Lists the tables and views to include in the data source view.</span></span>  
  
 <span data-ttu-id="94993-112">Para ordenar la lista en sentido ascendente o descendente, haga clic en **Nombre** o **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="94993-112">To reorder the list in ascending or descending order, click either **Name** or **Type**.</span></span>  
  
 <span data-ttu-id="94993-113">**Filter**</span><span class="sxs-lookup"><span data-stu-id="94993-113">**Filter**</span></span>  
 <span data-ttu-id="94993-114">Filtra los objetos que se indican en **Objetos disponibles**.</span><span class="sxs-lookup"><span data-stu-id="94993-114">Filters the objects listed under **Available objects**.</span></span> <span data-ttu-id="94993-115">Escriba una cadena y haga clic en **Filtro** para obtener una lista de los elementos que contienen la cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="94993-115">Type a string, and then click **Filter** to list only the names that contain a specified string.</span></span> <span data-ttu-id="94993-116">Para buscar una cadena exacta de caracteres, especifique la cadena entre comillas dobles.</span><span class="sxs-lookup"><span data-stu-id="94993-116">To find an exact string of characters, enclose the string between double quotation marks.</span></span> <span data-ttu-id="94993-117">El filtro no distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="94993-117">The filter is not case sensitive.</span></span>  
  
 <span data-ttu-id="94993-118">En cualquier punto de la cadena del filtro puede incluir los caracteres comodín que se indican en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="94993-118">You can include the wildcard characters listed in the following table anywhere in the filter string.</span></span>  
  
|<span data-ttu-id="94993-119">Carácter comodín</span><span class="sxs-lookup"><span data-stu-id="94993-119">Wildcard character</span></span>|<span data-ttu-id="94993-120">Value</span><span class="sxs-lookup"><span data-stu-id="94993-120">Value</span></span>|  
|------------------------|-----------|  
|**\***|<span data-ttu-id="94993-121">Cualquier cadena de caracteres</span><span class="sxs-lookup"><span data-stu-id="94993-121">Any string of characters</span></span>|  
|**%**|<span data-ttu-id="94993-122">Cualquier cadena de caracteres</span><span class="sxs-lookup"><span data-stu-id="94993-122">Any string of characters</span></span>|  
|<span data-ttu-id="94993-123">**?**</span><span class="sxs-lookup"><span data-stu-id="94993-123">**?**</span></span>|<span data-ttu-id="94993-124">Un único carácter</span><span class="sxs-lookup"><span data-stu-id="94993-124">A single character</span></span>|  
|<span data-ttu-id="94993-125">**"** *cadena* **"**</span><span class="sxs-lookup"><span data-stu-id="94993-125">**"** *string* **"**</span></span>|<span data-ttu-id="94993-126">Cadena literal de caracteres.</span><span class="sxs-lookup"><span data-stu-id="94993-126">A literal string of characters.</span></span> <span data-ttu-id="94993-127">Este carácter comodín establecerá una correspondencia con cualquier subcadena del nombre de objeto.</span><span class="sxs-lookup"><span data-stu-id="94993-127">This wildcard character will match any substring within the object name.</span></span>|  
  
 <span data-ttu-id="94993-128">**Show system objects**</span><span class="sxs-lookup"><span data-stu-id="94993-128">**Show system objects**</span></span>  
 <span data-ttu-id="94993-129">Muestra los objetos del sistema en **Objetos disponibles**.</span><span class="sxs-lookup"><span data-stu-id="94993-129">Displays system objects under **Available objects**.</span></span> <span data-ttu-id="94993-130">Esta opción solo está disponible si el proveedor del origen de datos expone objetos del sistema.</span><span class="sxs-lookup"><span data-stu-id="94993-130">This option is available only if the data source provider exposes system objects.</span></span> <span data-ttu-id="94993-131">Esta opción se selecciona automáticamente al eliminar un objeto del sistema de la lista **Objetos incluidos** .</span><span class="sxs-lookup"><span data-stu-id="94993-131">Removing a system object from the **Included objects** list automatically selects this option.</span></span>  
  
 <span data-ttu-id="94993-132">**Add related tables**</span><span class="sxs-lookup"><span data-stu-id="94993-132">**Add related tables**</span></span>  
 <span data-ttu-id="94993-133">Agrega todas las tablas que están relacionadas con las indicadas en **Objetos incluidos**.</span><span class="sxs-lookup"><span data-stu-id="94993-133">Adds all the tables that are related to those listed under **Included objects**.</span></span> <span data-ttu-id="94993-134">Esta opción no agrega vistas.</span><span class="sxs-lookup"><span data-stu-id="94993-134">This option does not add views.</span></span> <span data-ttu-id="94993-135">No obstante, sí agrega tablas con particiones.</span><span class="sxs-lookup"><span data-stu-id="94993-135">However, this option does add partitioned tables.</span></span> <span data-ttu-id="94993-136">Si selecciona criterios de coincidencia de nombres en la página **Coincidencia de nombres** del asistente, esta opción también incluye tablas relacionadas lógicamente de acuerdo con los criterios seleccionados.</span><span class="sxs-lookup"><span data-stu-id="94993-136">If you select name-matching criteria on the **Name Matching** page of the wizard, this option also includes logically related tables according to the criteria you select.</span></span> <span data-ttu-id="94993-137">Las tablas también se incluyen si están relacionadas con las tablas relacionadas que se acaban de agregar, y si su estructura es idéntica a la de la tabla original.</span><span class="sxs-lookup"><span data-stu-id="94993-137">Tables are also included if they are related to the newly added related tables, and if they have an identical structure to the original table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94993-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="94993-138">See Also</span></span>  
 <span data-ttu-id="94993-139">[Asistente para vistas del origen de datos &#40;de ayuda F1 Analysis Services&#41;](data-source-view-wizard-f1-help-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="94993-139">[Data Source View Wizard F1 Help &#40;Analysis Services&#41;](data-source-view-wizard-f1-help-analysis-services.md) </span></span>  
 [<span data-ttu-id="94993-140">Vistas del origen de datos en modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="94993-140">Data Source Views in Multidimensional Models</span></span>](multidimensional-models/data-source-views-in-multidimensional-models.md)  
  
  
