---
title: Especificar las rutas de acceso a los elementos externos (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4fe513da-f3c5-479c-9fec-8662b91a0d6d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 097a3566f914e7810039ee07bc3d3bf3185d7f06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662530"
---
# <a name="specifying-paths-to-external-items-report-builder-and-ssrs"></a><span data-ttu-id="42a24-102">Especificar las rutas de acceso a los elementos externos (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="42a24-102">Specifying Paths to External Items (Report Builder and SSRS)</span></span>
  <span data-ttu-id="42a24-103">Especifique rutas de acceso en las propiedades de los elementos de informe para hacer referencia a elementos tales como informes detallados, subinformes y archivos de imagen que son externos al archivo de definición de informe y se guardan en un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="42a24-103">You specify paths in report item properties to reference items such as drillthrough reports, subreports, and image files that are external to the report definition file and are stored on a report server.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
> [!NOTE]  
>  <span data-ttu-id="42a24-104">En el Generador de informes, las rutas de acceso a los elementos deben especificar los elementos en un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="42a24-104">In Report Builder, paths to items must specify items on a report server.</span></span> <span data-ttu-id="42a24-105">No se admiten las rutas de acceso a los elementos que están en un sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="42a24-105">Paths to items on a file system are not supported.</span></span> <span data-ttu-id="42a24-106">Puede obtener una vista previa de un informe que solamente utilice estos elementos si está conectado al servidor de informes donde se encuentran los elementos.</span><span class="sxs-lookup"><span data-stu-id="42a24-106">You can preview a report that uses these items only if you are connected to the report server where the items are located.</span></span>  
  
 <span data-ttu-id="42a24-107">Al especificar una ruta de acceso para un elemento externo en un cuadro de diálogo de acciones, subinformes o imágenes, puede ir directamente al servidor de informes y seleccionar el elemento.</span><span class="sxs-lookup"><span data-stu-id="42a24-107">When you specify a path for an external item in a dialog box for actions, subreports, or images, you can browse directly to the report server and select the item.</span></span> <span data-ttu-id="42a24-108">Se recomienda ir a un elemento y seleccionarlo directamente para especificar un informe detallado o subinforme.</span><span class="sxs-lookup"><span data-stu-id="42a24-108">Browsing to an item and selecting it directly is the recommended way to specify a drillthrough report or subreport.</span></span> <span data-ttu-id="42a24-109">De esa forma, los nombres de parámetro correctos estarán disponibles en una lista desplegable al especificar los parámetros de un informe o un subinforme.</span><span class="sxs-lookup"><span data-stu-id="42a24-109">That way the correct parameter names will be available in a drop-down list when you specify report or subreport parameters.</span></span> <span data-ttu-id="42a24-110">Al cambiar una ruta de acceso a un elemento para que señale a un elemento diferente, debe actualizar manualmente los valores y nombres de parámetro correctos según corresponda.</span><span class="sxs-lookup"><span data-stu-id="42a24-110">When you change an item path to point to a different item, you must manually update the correct parameter names and values as needed.</span></span>  
  
 <span data-ttu-id="42a24-111">En un servidor de informes configurado en modo nativo, especifique un nombre de informe detallado sin la extensión de archivo .rdl.</span><span class="sxs-lookup"><span data-stu-id="42a24-111">On a report server configured in native mode, specify a drillthrough report name without the file extension .rdl.</span></span>  
  
 <span data-ttu-id="42a24-112">En un servidor de informes configurado en modo integrado de SharePoint, debe incluir la extensión de archivo .rdl.</span><span class="sxs-lookup"><span data-stu-id="42a24-112">On a report server configured in SharePoint integrated mode, you must include the file extension .rdl.</span></span> <span data-ttu-id="42a24-113">La ruta de acceso puede ser una de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="42a24-113">The path can be one of the following:</span></span>  
  
-   <span data-ttu-id="42a24-114">**Una ruta de acceso relativa al elemento desde el informe principal.**</span><span class="sxs-lookup"><span data-stu-id="42a24-114">**A relative path to the item from the main report.**</span></span> <span data-ttu-id="42a24-115">Por ejemplo, ../TodosLosSubinformes/Subinforme1.</span><span class="sxs-lookup"><span data-stu-id="42a24-115">For example, ../AllSubreports/Subreport1.</span></span> <span data-ttu-id="42a24-116">En este ejemplo, el signo **..**</span><span class="sxs-lookup"><span data-stu-id="42a24-116">In this example, the **..**</span></span> <span data-ttu-id="42a24-117">indica la carpeta que está encima de aquella donde se encuentra el informe principal.</span><span class="sxs-lookup"><span data-stu-id="42a24-117">indicates the folder above the folder where the main report is located.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="42a24-118">No se admiten las rutas de acceso relativas cuando el informe se ejecuta dentro del Generador de informes.</span><span class="sxs-lookup"><span data-stu-id="42a24-118">Relative paths are not supported when the report is run inside Report Builder.</span></span> <span data-ttu-id="42a24-119">Para ver un informe que usa rutas de acceso relativas a los elementos externos, guárdelo en el servidor de informes y ejecútelo desde allí</span><span class="sxs-lookup"><span data-stu-id="42a24-119">To view a report that uses relative paths to external items, save the report to the report server, and run the report from there</span></span>  
  
-   <span data-ttu-id="42a24-120">**Una ruta de acceso completa al elemento.**</span><span class="sxs-lookup"><span data-stu-id="42a24-120">**A full path to the item.**</span></span>  
  
    -   <span data-ttu-id="42a24-121">**En un servidor de informes:** la ruta de acceso empieza desde **/** , la carpeta particular.</span><span class="sxs-lookup"><span data-stu-id="42a24-121">**On a report server:** The path starts from **/**, the Home folder.</span></span> <span data-ttu-id="42a24-122">Por ejemplo, /Informes/TodosLosSubinformes/Subinforme1.</span><span class="sxs-lookup"><span data-stu-id="42a24-122">For example, /Reports/AllSubreports/Subreport1.</span></span>  
  
    -   <span data-ttu-id="42a24-123">**En un sitio de SharePoint** : debe especificar el nombre del informe en una expresión, con la dirección URL completa del elemento y la extensión de archivo .rdl.</span><span class="sxs-lookup"><span data-stu-id="42a24-123">**On a SharePoint site:** You must specify the report name in an expression, with the full URL of the item and the file extension .rdl.</span></span> <span data-ttu-id="42a24-124">Por ejemplo, `="http://server/site/library/folder/Report1.rdl"`.</span><span class="sxs-lookup"><span data-stu-id="42a24-124">For example, `="http://server/site/library/folder/Report1.rdl"`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42a24-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="42a24-125">See Also</span></span>  
 <span data-ttu-id="42a24-126">[Agregar una imagen externa &#40;Generador de informes y SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="42a24-126">[Add an External Image &#40;Report Builder and SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="42a24-127">[Agregar un subinforme y parámetros &#40;Generador de informes y SSRS&#41;](add-a-subreport-and-parameters-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="42a24-127">[Add a Subreport and Parameters &#40;Report Builder and SSRS&#41;](add-a-subreport-and-parameters-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="42a24-128">Agregar una acción de obtención de detalles en un informe &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="42a24-128">Add a Drillthrough Action on a Report &#40;Report Builder and SSRS&#41;</span></span>](add-a-drillthrough-action-on-a-report-report-builder-and-ssrs.md)  
  
  
