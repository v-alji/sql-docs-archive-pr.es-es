---
title: Página buscar (Administrador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 51ffdc07-e1b9-4ed7-acb3-dd98d7cce273
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2528133f5b2ecc4bed4c16fdd476591b3bab52d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673483"
---
# <a name="search-page-report-manager"></a><span data-ttu-id="d4697-102">Buscar (página del Administrador de informes)</span><span class="sxs-lookup"><span data-stu-id="d4697-102">Search Page (Report Manager)</span></span>
  <span data-ttu-id="d4697-103">Use la página Resultados de la búsqueda para ver los resultados de una operación de búsqueda especificada para un informe, un informe vinculado, un modelo de informe, un origen de datos compartido, una carpeta o un recurso.</span><span class="sxs-lookup"><span data-stu-id="d4697-103">Use the Search Results page to view the results of a search operation specified for a report, linked report, report model, shared data source, folder, or resource.</span></span> <span data-ttu-id="d4697-104">Los resultados de la búsqueda se muestran ordenados alfabéticamente.</span><span class="sxs-lookup"><span data-stu-id="d4697-104">Search results are listed alphabetically.</span></span> <span data-ttu-id="d4697-105">Se pueden ordenar por tipo, nombre o descripción.</span><span class="sxs-lookup"><span data-stu-id="d4697-105">You can sort by type, name, or description.</span></span>  
  
 <span data-ttu-id="d4697-106">En una operación de búsqueda no se incluyen los elementos siguientes: instantáneas de informe incluidas en un historial de informes, suscripciones y programaciones compartidas.</span><span class="sxs-lookup"><span data-stu-id="d4697-106">The following items are excluded from a search operation: report snapshots contained in report history, subscriptions, and shared schedules.</span></span> <span data-ttu-id="d4697-107">De manera similar, si no se tienen permisos suficientes para ver una carpeta o un informe, ese elemento se excluye de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d4697-107">Similarly, insufficient permission to view a folder or report excludes that item from a search.</span></span>  
  
 <span data-ttu-id="d4697-108">No puede buscar el texto dentro de un informe o modelo.</span><span class="sxs-lookup"><span data-stu-id="d4697-108">You cannot search for text within a report or model.</span></span> <span data-ttu-id="d4697-109">Para buscar texto específico dentro de un informe, use la barra de herramientas situada en la parte superior del informe.</span><span class="sxs-lookup"><span data-stu-id="d4697-109">To search for specific text within a report, use the toolbar at the top of the report.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="d4697-110">Navegación</span><span class="sxs-lookup"><span data-stu-id="d4697-110">Navigation</span></span>  
 <span data-ttu-id="d4697-111">Utilice el procedimiento siguiente para navegar hasta esta ubicación en la interfaz de usuario (IU).</span><span class="sxs-lookup"><span data-stu-id="d4697-111">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-search-results-page"></a><span data-ttu-id="d4697-112">Para abrir la página Resultados de la búsqueda</span><span class="sxs-lookup"><span data-stu-id="d4697-112">To open the Search Results page</span></span>  
  
1.  <span data-ttu-id="d4697-113">Abra el Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="d4697-113">Open Report Manager.</span></span>  
  
2.  <span data-ttu-id="d4697-114">En la parte superior de la página, escriba sus criterios de búsqueda en el cuadro **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="d4697-114">At the top of the page, type your search criteria in the **Search** box.</span></span> <span data-ttu-id="d4697-115">A continuación, presione Entrar o haga clic en la flecha Buscar.</span><span class="sxs-lookup"><span data-stu-id="d4697-115">Then press Enter or click the Search arrow.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d4697-116">Opciones</span><span class="sxs-lookup"><span data-stu-id="d4697-116">Options</span></span>  
 <span data-ttu-id="d4697-117">**Eliminar**</span><span class="sxs-lookup"><span data-stu-id="d4697-117">**Delete**</span></span>  
 <span data-ttu-id="d4697-118">Haga clic para quitar un elemento de una base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="d4697-118">Click to remove an item from a report server database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d4697-119">Este botón solo está disponible en la vista **Detalles**.</span><span class="sxs-lookup"><span data-stu-id="d4697-119">This button is available only in **Details View**.</span></span> <span data-ttu-id="d4697-120">Sin embargo, puede mantener el mouse sobre un elemento y utilizar el menú para obtener acceso a la funcionalidad de eliminar en la vista **Detalles** o en la **Vista de lista**.</span><span class="sxs-lookup"><span data-stu-id="d4697-120">However, you can hover over an item and use the menu to access the delete functionality in either **Details View** or in **List View**.</span></span>  
  
 <span data-ttu-id="d4697-121">**Mover**</span><span class="sxs-lookup"><span data-stu-id="d4697-121">**Move**</span></span>  
 <span data-ttu-id="d4697-122">Haga clic para cambiar la ubicación de un elemento.</span><span class="sxs-lookup"><span data-stu-id="d4697-122">Click to relocate an item.</span></span> <span data-ttu-id="d4697-123">Al hacerlo, se abre la página para mover elementos, en la que puede seleccionar una nueva ubicación de carpeta.</span><span class="sxs-lookup"><span data-stu-id="d4697-123">This opens the Move Items page, where you can select a different folder location.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d4697-124">Este botón solo está disponible en la vista **Detalles**.</span><span class="sxs-lookup"><span data-stu-id="d4697-124">This button is available only in **Details View**.</span></span> <span data-ttu-id="d4697-125">Sin embargo, puede desplazar el mouse sobre un elemento y utilizar el menú para obtener acceso a la funcionalidad de mover en la vista **Detalles** o en la **Vista de lista**.</span><span class="sxs-lookup"><span data-stu-id="d4697-125">However, you can hover over an item and use the menu to access the move functionality in either **Details View** or in **List View**.</span></span>  
  
 <span data-ttu-id="d4697-126">Cuadro de búsqueda</span><span class="sxs-lookup"><span data-stu-id="d4697-126">Search box</span></span>  
 <span data-ttu-id="d4697-127">Escriba la totalidad o parte del nombre de un elemento que desee ubicar y, a continuación, haga clic en **Ir** para iniciar la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d4697-127">Type all or part of the name of an item that you want to locate, and then click **Go** to start the search.</span></span> <span data-ttu-id="d4697-128">La longitud máxima de una cadena de búsqueda es 128 caracteres.</span><span class="sxs-lookup"><span data-stu-id="d4697-128">The longest string you can search for is 128 characters.</span></span>  
  
 <span data-ttu-id="d4697-129">En los resultados de la búsqueda, se incluyen los nombres o las descripciones de los elementos que contengan la cadena de búsqueda completa en cualquier lugar del valor de texto.</span><span class="sxs-lookup"><span data-stu-id="d4697-129">Item names or descriptions that contain the entire search string anywhere in the text value are included in the search results.</span></span>  
  
 <span data-ttu-id="d4697-130">No se admiten operadores booleanos, como el signo más (+).</span><span class="sxs-lookup"><span data-stu-id="d4697-130">Boolean operators such as the plus character (+) are not supported.</span></span>  
  
 <span data-ttu-id="d4697-131">**Vista de detalles**</span><span class="sxs-lookup"><span data-stu-id="d4697-131">**Details View**</span></span>  
 <span data-ttu-id="d4697-132">Haga clic para mostrar la página Resultados de la búsqueda en una lista que contiene información adicional sobre los elementos, como el tipo de elemento, nombre, la descripción, la carpeta en la que se encuentra y la última vez que se ejecutó.</span><span class="sxs-lookup"><span data-stu-id="d4697-132">Click to display the Search Results page in a list that contains additional information about items, such as the item type, name, description, the folder in which the item is located, and when it was last run.</span></span> <span data-ttu-id="d4697-133">En la vista **Detalles**puede utilizar los botones **Eliminar** y **Mover** para quitar y reubicar los elementos de una carpeta.</span><span class="sxs-lookup"><span data-stu-id="d4697-133">In **Details View**, you can use **Delete** and **Move** buttons to remove and relocate items in the folder.</span></span>  
  
 <span data-ttu-id="d4697-134">Mantenga el mouse sobre un elemento y haga clic en la flecha de lista desplegable para abrir el menú desplegable donde podrá obtener acceso a las propiedades del elemento seleccionado y configurarlas.</span><span class="sxs-lookup"><span data-stu-id="d4697-134">Hover over an item and click the drop-down arrow to open the drop-down menu from which you can access and configure properties of the selected item.</span></span>  
  
 <span data-ttu-id="d4697-135">**Vista de lista**</span><span class="sxs-lookup"><span data-stu-id="d4697-135">**List View**</span></span>  
 <span data-ttu-id="d4697-136">Haga clic para mostrar la página Resultados de la búsqueda sin detalles como en la vista **Detalles**.</span><span class="sxs-lookup"><span data-stu-id="d4697-136">Click to display the Search Results page without details as in **Details View**.</span></span> <span data-ttu-id="d4697-137">Vista de lista es la vista predeterminada que se utiliza al abrir la página Resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d4697-137">List View is the default view when the Search Results page opens.</span></span>  
  
 <span data-ttu-id="d4697-138">Mantenga el mouse sobre un elemento y haga clic en la flecha de lista desplegable para abrir el menú desplegable donde podrá obtener acceso a las propiedades del elemento seleccionado y configurarlas.</span><span class="sxs-lookup"><span data-stu-id="d4697-138">Hover over an item and click the drop-down arrow to open the drop-down menu from which you can access and configure properties of the selected item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4697-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d4697-139">See Also</span></span>  
 <span data-ttu-id="d4697-140">[Administrador de informes &#40;Modo nativo de SSRS&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="d4697-140">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 [<span data-ttu-id="d4697-141">Administrador de informes (Ayuda F1)</span><span class="sxs-lookup"><span data-stu-id="d4697-141">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
