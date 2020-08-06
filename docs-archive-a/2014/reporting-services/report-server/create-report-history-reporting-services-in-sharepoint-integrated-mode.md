---
title: Crear historial de informes (Reporting Services en el modo integrado de SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- report history [Reporting Services], SharePoint
ms.assetid: e57ec746-05ae-4ff6-8e39-6cde87310daa
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 996202580bbacc24080460c2c43218db27294d76
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674575"
---
# <a name="create-report-history-reporting-services-in-sharepoint-integrated-mode"></a><span data-ttu-id="73974-102">Crear historial de informes (Reporting Services en el modo integrado de SharePoint)</span><span class="sxs-lookup"><span data-stu-id="73974-102">Create Report History (Reporting Services in SharePoint Integrated Mode)</span></span>
  <span data-ttu-id="73974-103">El historial de informes es un conjunto de instantáneas de informe que se crean a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="73974-103">Report history is a collection of report snapshots that you create over time.</span></span> <span data-ttu-id="73974-104">Cada instantánea es una copia del informe como existía cuando se creó.</span><span class="sxs-lookup"><span data-stu-id="73974-104">Each snapshot is a copy of the report as it existed when it was created.</span></span> <span data-ttu-id="73974-105">Incluye el diseño y los datos del informe cuando se creó la instantánea.</span><span class="sxs-lookup"><span data-stu-id="73974-105">It includes the layout and data that was current for the report when the snapshot was created.</span></span> <span data-ttu-id="73974-106">La información de representación no está almacenada con la instantánea.</span><span class="sxs-lookup"><span data-stu-id="73974-106">Rendering information is not stored with the snapshot.</span></span> <span data-ttu-id="73974-107">Al abrir una instantánea en un historial de informes, se abre en un HTML en el elemento web Visor de informes.</span><span class="sxs-lookup"><span data-stu-id="73974-107">When you open a snapshot in report history, it opens in HTML in the Report Viewer Web Part.</span></span> <span data-ttu-id="73974-108">Una vez representada, puede exportarla a otros formatos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="73974-108">After it is rendered, you can export it to other application formats.</span></span>  
  
 <span data-ttu-id="73974-109">Para crear el historial de informes, el informe debe poder ejecutarse en modo desatendido (es decir, el servidor de informes debe ser capaz de ejecutar el informe sin la intervención del usuario).</span><span class="sxs-lookup"><span data-stu-id="73974-109">To create report history, the report must be able to run unattended (that is, the report server must be able to run the report without user interaction).</span></span> <span data-ttu-id="73974-110">Debe tener el permiso Editar elementos en la biblioteca que contiene el informe.</span><span class="sxs-lookup"><span data-stu-id="73974-110">You must have Edit Items permission on the library that contains the report.</span></span> <span data-ttu-id="73974-111">Para ver o eliminar el historial de informes, debe contar con los permisos Ver versiones o Eliminar versiones.</span><span class="sxs-lookup"><span data-stu-id="73974-111">To view or delete report history, you must have View Versions or Delete Versions permissions.</span></span>  
  
### <a name="to-create-a-snapshot-or-report-history-on-demand"></a><span data-ttu-id="73974-112">Crear una instantánea o historial de informes a petición</span><span class="sxs-lookup"><span data-stu-id="73974-112">To create a snapshot or report history on demand</span></span>  
  
1.  <span data-ttu-id="73974-113">Elija el informe.</span><span class="sxs-lookup"><span data-stu-id="73974-113">Point to the report.</span></span>  
  
2.  <span data-ttu-id="73974-114">Haga clic para que se muestre la flecha abajo y, a continuación, seleccione **Ver historial de informes**.</span><span class="sxs-lookup"><span data-stu-id="73974-114">Click to display the down arrow, and then select **View Report History**.</span></span>  
  
3.  <span data-ttu-id="73974-115">Haga clic en **Nueva instantánea**.</span><span class="sxs-lookup"><span data-stu-id="73974-115">Click **New Snapshot**.</span></span> <span data-ttu-id="73974-116">Si el botón no está visible, se debe a que no tiene permiso para crear instantáneas en el historial de informes.</span><span class="sxs-lookup"><span data-stu-id="73974-116">If the button is not visible, it is because you do not have permission to create snapshots in report history.</span></span>  
  
4.  <span data-ttu-id="73974-117">Para ver la instantánea que acaba de crear, selecciónela en la lista.</span><span class="sxs-lookup"><span data-stu-id="73974-117">To view the snapshot you just created, select it from the list.</span></span> <span data-ttu-id="73974-118">Cada instantánea se identifica mediante una marca de tiempo que muestra cuándo se creó la instantánea.</span><span class="sxs-lookup"><span data-stu-id="73974-118">Each snapshot is identified by a timestamp that shows when the snapshot was created.</span></span> <span data-ttu-id="73974-119">No puede cambiar el nombre de una instantánea, ni moverla a otra ubicación ni modificarla.</span><span class="sxs-lookup"><span data-stu-id="73974-119">You cannot rename the snapshot, move it to another location, or modify it.</span></span>  
  
### <a name="to-schedule-report-history"></a><span data-ttu-id="73974-120">Para programar el historial de informes</span><span class="sxs-lookup"><span data-stu-id="73974-120">To schedule report history</span></span>  
  
1.  <span data-ttu-id="73974-121">Elija el informe.</span><span class="sxs-lookup"><span data-stu-id="73974-121">Point to the report.</span></span>  
  
2.  <span data-ttu-id="73974-122">Haga clic para que se muestre la flecha abajo y, a continuación, seleccione **Administrar opciones de procesamiento**.</span><span class="sxs-lookup"><span data-stu-id="73974-122">Click to display the down arrow, and then select **Manage Processing Options**.</span></span>  
  
3.  <span data-ttu-id="73974-123">En **Opciones de instantáneas del historial**, haga clic en **Crear instantáneas del historial de informes según una programación**.</span><span class="sxs-lookup"><span data-stu-id="73974-123">In **History Snapshot Options**, click **Create report history snapshots on a schedule**.</span></span>  
  
4.  <span data-ttu-id="73974-124">Si tiene una programación compartida que contiene la información de programación que desea usar, haga clic en **Según una programación compartida** y seleccione la programación que desee usar.</span><span class="sxs-lookup"><span data-stu-id="73974-124">If you have a shared schedule that contains the schedule information you want to use, click **On a shared schedule** and select the schedule you want to use.</span></span> <span data-ttu-id="73974-125">De lo contrario, haga clic en **Según una programación personalizada**y, a continuación, haga clic en **Configurar** para especificar las opciones para crear el historial según una programación periódica.</span><span class="sxs-lookup"><span data-stu-id="73974-125">Otherwise, click **On a custom schedule**, and then click **Configure** to specify options to create report history on a recurring schedule.</span></span>  
  
### <a name="to-create-report-history-when-data-is-refreshed-in-a-report"></a><span data-ttu-id="73974-126">Para crear el historial de informes cuando se actualizan los datos de un informe</span><span class="sxs-lookup"><span data-stu-id="73974-126">To create report history when data is refreshed in a report</span></span>  
  
1.  <span data-ttu-id="73974-127">Elija el informe.</span><span class="sxs-lookup"><span data-stu-id="73974-127">Point to the report.</span></span>  
  
2.  <span data-ttu-id="73974-128">Haga clic para que se muestre la flecha abajo y, a continuación, seleccione **Administrar opciones de procesamiento**.</span><span class="sxs-lookup"><span data-stu-id="73974-128">Click to display the down arrow, and then select **Manage Processing Options**.</span></span>  
  
3.  <span data-ttu-id="73974-129">En **Opciones de instantáneas del historial**, haga clic en **Almacenar todas las instantáneas de datos de informe en el historial de informes**.</span><span class="sxs-lookup"><span data-stu-id="73974-129">In **History Snapshot Options**, click **Store all report data snapshots in report history**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73974-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="73974-130">See Also</span></span>  
 [<span data-ttu-id="73974-131">Establecer opciones de procesamiento &#40;Reporting Services en el modo integrado de SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="73974-131">Set Processing Options &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](../set-processing-options-reporting-services-in-sharepoint-integrated-mode.md)  
  
  
