---
title: Página elegir vínculo (Administrador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a89a555d-efa3-45d6-951e-db78ec6a2c8e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bc40fe726555babee8d9940e198a93577bd6a09f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670860"
---
# <a name="choose-link-page-report-manager"></a><span data-ttu-id="b6a06-102">Elegir vínculo (página del Administrador de informes)</span><span class="sxs-lookup"><span data-stu-id="b6a06-102">Choose Link Page (Report Manager)</span></span>
  <span data-ttu-id="b6a06-103">Use la página Elegir vínculo para elegir un informe diferente en el que basar el informe vinculado actualmente seleccionado.</span><span class="sxs-lookup"><span data-stu-id="b6a06-103">Use the Choose Link page to choose a different report upon which to base the currently selected linked report.</span></span> <span data-ttu-id="b6a06-104">Los informes vinculados se basan en otros informes ya publicados en un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="b6a06-104">Linked reports are based on other reports already published to a report server.</span></span> <span data-ttu-id="b6a06-105">Un informe vinculado usa el diseño y los datos del informe base, pero tiene páginas de propiedades independientes para que pueda personalizar propiedades de parámetro, configuración de seguridad, nombre, descripción y ubicación.</span><span class="sxs-lookup"><span data-stu-id="b6a06-105">A linked report uses the layout and data of the base report, but has separate property pages so that you can customize parameter properties, security settings, name, description, and location.</span></span>  
  
 <span data-ttu-id="b6a06-106">A través de la página Elegir vínculo, puede elegir un informe publicado diferente para usarlo con el informe vinculado.</span><span class="sxs-lookup"><span data-stu-id="b6a06-106">Through the Choose Link page, you can choose a different published report to use with the linked report.</span></span> <span data-ttu-id="b6a06-107">El resto de la configuración del informe vinculado, como la seguridad y los parámetros, no se verá afectada por los cambios de la información del vínculo.</span><span class="sxs-lookup"><span data-stu-id="b6a06-107">Other settings of the linked report (such as security and parameter settings) are unaffected by changes to the link information.</span></span> <span data-ttu-id="b6a06-108">El servidor de informes no validará su selección, por tanto, asegúrese de elegir un informe que tenga los mismos parámetros que los especificados en el informe vinculado.</span><span class="sxs-lookup"><span data-stu-id="b6a06-108">The report server will not validate your selection, so be sure to choose a report that has the same parameters as those you specified on the linked report.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="b6a06-109">Navegación</span><span class="sxs-lookup"><span data-stu-id="b6a06-109">Navigation</span></span>  
 <span data-ttu-id="b6a06-110">Utilice el procedimiento siguiente para navegar hasta esta ubicación en la interfaz de usuario (IU).</span><span class="sxs-lookup"><span data-stu-id="b6a06-110">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-choose-link-page"></a><span data-ttu-id="b6a06-111">Para abrir la página Elegir vínculo</span><span class="sxs-lookup"><span data-stu-id="b6a06-111">To open the Choose Link page</span></span>  
  
1.  <span data-ttu-id="b6a06-112">Abra el Administrador de informes y busque el informe vinculado que desea cambiar.</span><span class="sxs-lookup"><span data-stu-id="b6a06-112">Open Report Manager, and locate the linked report you want to change.</span></span>  
  
2.  <span data-ttu-id="b6a06-113">Mantenga el mouse sobre el informe vinculado y haga clic en la flecha de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="b6a06-113">Hover over the linked report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="b6a06-114">En el menú desplegable, haga clic en **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="b6a06-114">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="b6a06-115">Se abrirá la página de propiedades **General** correspondiente al informe vinculado.</span><span class="sxs-lookup"><span data-stu-id="b6a06-115">This opens the **General** properties page for the linked report.</span></span>  
  
4.  <span data-ttu-id="b6a06-116">En la pestaña **General** , en la página de propiedades, haga clic en **Cambiar vínculo**.</span><span class="sxs-lookup"><span data-stu-id="b6a06-116">On the **General** tab, on the properties page, click **Change Link**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b6a06-117">Opciones</span><span class="sxs-lookup"><span data-stu-id="b6a06-117">Options</span></span>  
 <span data-ttu-id="b6a06-118">**Ubicación**</span><span class="sxs-lookup"><span data-stu-id="b6a06-118">**Location**</span></span>  
 <span data-ttu-id="b6a06-119">Especifique el nombre completo del informe publicado, incluida la ruta de acceso a la carpeta.</span><span class="sxs-lookup"><span data-stu-id="b6a06-119">Specify the full name of the published report, including the folder path and report name.</span></span> <span data-ttu-id="b6a06-120">Puede escribir el nombre completo o utilizar la vista de árbol para navegar hasta el informe que desee utilizar.</span><span class="sxs-lookup"><span data-stu-id="b6a06-120">You can type the full name of the report or use the tree view to navigate to the report you want to use.</span></span>  
  
 <span data-ttu-id="b6a06-121">**Vista de árbol**</span><span class="sxs-lookup"><span data-stu-id="b6a06-121">**Tree view**</span></span>  
 <span data-ttu-id="b6a06-122">Muestra todas las carpetas de la jerarquía de carpetas del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="b6a06-122">Shows all of the folders in the report server folder hierarchy.</span></span> <span data-ttu-id="b6a06-123">Si desea utilizar la vista de árbol para especificar el campo **Ubicación** , haga clic en el nombre del informe.</span><span class="sxs-lookup"><span data-stu-id="b6a06-123">To use the tree view to fill in the **Location** field, click the name of the report.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6a06-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b6a06-124">See Also</span></span>  
 <span data-ttu-id="b6a06-125">[Página de propiedades generales, informes &#40;Administrador de informes&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="b6a06-125">[General Properties Page, Reports &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span></span>  
 <span data-ttu-id="b6a06-126">[Página nuevo informe vinculado &#40;Administrador de informes&#41;](../../2014/reporting-services/new-linked-report-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="b6a06-126">[New Linked Report Page &#40;Report Manager&#41;](../../2014/reporting-services/new-linked-report-page-report-manager.md) </span></span>  
 [<span data-ttu-id="b6a06-127">Administrador de informes (Ayuda F1)</span><span class="sxs-lookup"><span data-stu-id="b6a06-127">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
