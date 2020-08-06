---
title: Buscar actualizaciones o desactivar las actualizaciones (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 9c69792d-d7c4-453b-ae2f-6d2d071d8606
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 088d41e71d770f746367f2760cff8ff67b15623c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672791"
---
# <a name="check-for-updates-or-turn-updates-off-report-builder-and-ssrs"></a><span data-ttu-id="41c0a-102">Buscar o desactivar actualizaciones (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="41c0a-102">Check for Updates or Turn Updates Off (Report Builder and SSRS)</span></span>
  <span data-ttu-id="41c0a-103">Cada vez que abre un informe, el Generador de informes comprueba si las instancias publicadas de los elementos de informe se han actualizado en el servidor de informes o en el sitio de SharePoint integrado con un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="41c0a-103">Every time you open a report, Report Builder checks to see if the published instances of report parts in that report have been updated on the report server or SharePoint site integrated with a report server.</span></span> <span data-ttu-id="41c0a-104">También comprueba los cambios de los elementos dependientes de elementos de informe, como el conjunto de datos y los parámetros.</span><span class="sxs-lookup"><span data-stu-id="41c0a-104">It also checks for changes in the report parts' dependent items, such as the dataset and parameters.</span></span> <span data-ttu-id="41c0a-105">Si algún elemento de informe o sus dependencias se han actualizado en el servidor o en el sitio, una barra de información del informe muestra el número de componentes actualizados.</span><span class="sxs-lookup"><span data-stu-id="41c0a-105">If any report parts or their dependencies have been updated on the site or server, an information bar in your report displays the number of updated parts.</span></span> <span data-ttu-id="41c0a-106">Puede elegir ver, y aceptar o rechazar las actualizaciones, o bien descartar la barra de información.</span><span class="sxs-lookup"><span data-stu-id="41c0a-106">You can choose to view and accept or reject the updates, or dismiss the information bar.</span></span>  
  
 <span data-ttu-id="41c0a-107">Puede deshabilitar la barra de información y no recibir información sobre los cambios de las instancias publicadas de elementos de informe.</span><span class="sxs-lookup"><span data-stu-id="41c0a-107">You can also disable the information bar and not be informed if published instances of report parts have changed.</span></span> <span data-ttu-id="41c0a-108">Esta es una configuración de usuario; se deshabilitará para todos los informes que abra.</span><span class="sxs-lookup"><span data-stu-id="41c0a-108">This is a user setting; it will be disabled for all reports that you open.</span></span> <span data-ttu-id="41c0a-109">Aunque haya deshabilitado la barra de información, aún puede comprobar las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="41c0a-109">Even if you have disabled the information bar, you can still check for updates.</span></span>  
  
### <a name="to-turn-on-and-off-report-part-updates"></a><span data-ttu-id="41c0a-110">Para activar y desactivar las actualizaciones de elementos de informe</span><span class="sxs-lookup"><span data-stu-id="41c0a-110">To turn on and off report part updates</span></span>  
  
1.  <span data-ttu-id="41c0a-111">Haga clic en el botón Generador de informes y, a continuación, haga clic en **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="41c0a-111">Click the Report Builder button, and then click **Options**.</span></span>  
  
2.  <span data-ttu-id="41c0a-112">En el cuadro de diálogo **Opciones** , en la pestaña **recursos** , Active o desactive la casilla **Mostrar actualizaciones de elementos de informe en mis informes** .</span><span class="sxs-lookup"><span data-stu-id="41c0a-112">In the **Options** dialog box, on the **Resources** tab, select or clear the **Show updates to report parts in my reports** check box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="41c0a-113">Se trata de una opción de usuario.</span><span class="sxs-lookup"><span data-stu-id="41c0a-113">This is a user setting.</span></span> <span data-ttu-id="41c0a-114">Estará deshabilitada en todos los informes que abra.</span><span class="sxs-lookup"><span data-stu-id="41c0a-114">It will be disabled for all reports that you open.</span></span>  
  
### <a name="to-check-for-updates"></a><span data-ttu-id="41c0a-115">Para comprobar si hay actualizaciones</span><span class="sxs-lookup"><span data-stu-id="41c0a-115">To check for updates</span></span>  
  
-   <span data-ttu-id="41c0a-116">Haga clic con el botón secundario en la superficie de diseño fuera del informe o en el cuerpo del informe y haga clic en **Buscar actualizaciones**.</span><span class="sxs-lookup"><span data-stu-id="41c0a-116">Right-click the design surface outside the report, or in the report body, and click **Check for Updates**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41c0a-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="41c0a-117">See Also</span></span>  
 <span data-ttu-id="41c0a-118">[Elementos de informe &#40;Generador de informes y SSRS&#41;](report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="41c0a-118">[Report Parts &#40;Report Builder and SSRS&#41;](report-parts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="41c0a-119">[Publicar y volver a publicar elementos de informe &#40;Generador de informes y SSRS&#41;](report-design/publish-and-republish-report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="41c0a-119">[Publish and Republish Report Parts &#40;Report Builder and SSRS&#41;](report-design/publish-and-republish-report-parts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="41c0a-120">[Buscar elementos de informe y establecer una carpeta predeterminada &#40;Generador de informes y SSRS&#41;](report-design/browse-for-report-parts-and-set-a-default-folder-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="41c0a-120">[Browse for Report Parts and Set a Default Folder &#40;Report Builder and SSRS&#41;](report-design/browse-for-report-parts-and-set-a-default-folder-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="41c0a-121">[Solucionar problemas de elementos de informe &#40;Generador de informes y SSRS&#41;](../../2014/reporting-services/troubleshoot-report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="41c0a-121">[Troubleshoot Report Parts &#40;Report Builder and SSRS&#41;](../../2014/reporting-services/troubleshoot-report-parts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="41c0a-122">Elementos de informe y conjuntos de datos en el Generador de informes</span><span class="sxs-lookup"><span data-stu-id="41c0a-122">Report Parts and Datasets in Report Builder</span></span>](report-data/report-parts-and-datasets-in-report-builder.md)  
  
  
