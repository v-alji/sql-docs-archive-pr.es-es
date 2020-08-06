---
title: Administrar mis alertas de datos en el Administrador de alertas de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- managing, alerts
- managing, data alerts
ms.assetid: e0e4ffdf-bd4c-4ebd-872b-07486cbb47c2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 371c62c2f97334e20280a659c8039ab20852ccfb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748020"
---
# <a name="manage-my-data-alerts-in-data-alert-manager"></a><span data-ttu-id="407bd-102">Administrar mis alertas de datos en el Administrador de alertas de datos</span><span class="sxs-lookup"><span data-stu-id="407bd-102">Manage My Data Alerts in Data Alert Manager</span></span>
  <span data-ttu-id="407bd-103">Los usuarios de SharePoint pueden ver una lista de las alertas de datos que han creado e información acerca de las alertas.</span><span class="sxs-lookup"><span data-stu-id="407bd-103">SharePoint users can view a list of the data alerts that they created and information about the alerts.</span></span> <span data-ttu-id="407bd-104">También pueden eliminar sus alertas, abrir las definiciones de las alertas para modificarlas en el Diseñador de alertas de datos y ejecutar sus alertas.</span><span class="sxs-lookup"><span data-stu-id="407bd-104">Users can also delete their alerts, open alert definitions for edit in Data Alert Designer, and run their alerts.</span></span> <span data-ttu-id="407bd-105">En la imagen siguiente se muestran las características disponibles en el Administrador de alertas de datos para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="407bd-105">The following picture shows the features available to users in Data Alert Manager.</span></span>  
  
 <span data-ttu-id="407bd-106">![Características del Administrador de alertas para los usuarios de SharePoint](media/rs-alertmanageriw.gif "Características del Administrador de alertas para los usuarios de SharePoint")</span><span class="sxs-lookup"><span data-stu-id="407bd-106">![Alert Manager features for SharePoint users](media/rs-alertmanageriw.gif "Alert Manager features for SharePoint users")</span></span>  
  
### <a name="to-view-a-list-of-your-alerts"></a><span data-ttu-id="407bd-107">Para ver una lista de sus alertas</span><span class="sxs-lookup"><span data-stu-id="407bd-107">To view a list of your alerts</span></span>  
  
1.  <span data-ttu-id="407bd-108">Vaya a la biblioteca de SharePoint donde guardó los informes para los que creó alertas de datos.</span><span class="sxs-lookup"><span data-stu-id="407bd-108">Go to the SharePoint library where you saved the reports on which you created data alerts.</span></span>  
  
2.  <span data-ttu-id="407bd-109">Haga clic en el icono para expandir el menú desplegable de un informe y haga clic en **Administrar alertas de datos**.</span><span class="sxs-lookup"><span data-stu-id="407bd-109">Click the icon for the expand drop-down menu on a report and click **Manage Data Alerts**.</span></span> <span data-ttu-id="407bd-110">La imagen siguiente muestra el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="407bd-110">The following picture shows the drop-down menu.</span></span>  
  
     <span data-ttu-id="407bd-111">![Abrir el Administrador de alertas desde el menú contextual del informe](media/rs-openalertmanager.gif "Abrir el Administrador de alertas desde el menú contextual del informe")</span><span class="sxs-lookup"><span data-stu-id="407bd-111">![Open Alert Manager from report context menu](media/rs-openalertmanager.gif "Open Alert Manager from report context menu")</span></span>  
  
     <span data-ttu-id="407bd-112">Se abre el Administrador de alertas de datos.</span><span class="sxs-lookup"><span data-stu-id="407bd-112">Data Alert Manager opens.</span></span> <span data-ttu-id="407bd-113">De forma predeterminada, se muestran las alertas del informe que seleccionó en la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="407bd-113">By default, it lists the alerts for the report that you selected in the library.</span></span>  
  
3.  <span data-ttu-id="407bd-114">Haga clic en la flecha abajo que aparece junto a la lista **Ver las alertas del informe** y seleccione un informe para ver sus alertas, o haga clic en **Mostrar todas** para ver todas las alertas.</span><span class="sxs-lookup"><span data-stu-id="407bd-114">Click the down arrow next to the **View alerts for report** list and select a report to view its alerts, or click **Show All** to list all alerts.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="407bd-115">Si el informe que seleccionó no tiene ninguna alerta, no tiene que volver a la biblioteca de SharePoint para buscar y seleccionar un informe que tenga alertas.</span><span class="sxs-lookup"><span data-stu-id="407bd-115">If the report that you selected does not have any alerts, you do not have to return to the SharePoint library to locate and select a report that hasalerts.</span></span> <span data-ttu-id="407bd-116">En su lugar, haga clic en **Mostrar todas** para ver una lista de todas sus alertas.</span><span class="sxs-lookup"><span data-stu-id="407bd-116">Instead, click **Show All** to see a list of all your alerts.</span></span>  
  
     <span data-ttu-id="407bd-117">Aparece una tabla con el nombre de la alerta, el nombre del informe, su nombre como creador de la alerta, el número de veces que se envió la alerta, la última vez que se modificó la definición de la alerta y el estado de la alerta.</span><span class="sxs-lookup"><span data-stu-id="407bd-117">A table lists the alert name, report name, your name as the creator of the alert, the number the alert was sent, the last time the alert definition was modified, and the status of the alert.</span></span> <span data-ttu-id="407bd-118">Si la alerta no se puede generar o enviar, la columna de estado contiene información sobre el error que le ayudará a solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="407bd-118">If the alert cannot be generated or sent, the status column contains information about the error and helps you troubleshoot the problem.</span></span>  
  
### <a name="to-edit-an-alert-definition"></a><span data-ttu-id="407bd-119">Para editar una definición de alerta</span><span class="sxs-lookup"><span data-stu-id="407bd-119">To edit an alert definition</span></span>  
  
-   <span data-ttu-id="407bd-120">Haga clic con el botón derecho en la alerta de datos cuya definición de alerta quiere modificar y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="407bd-120">Right-click the data alert for which you want to edit the alert definition and click **Edit**.</span></span>  
  
     <span data-ttu-id="407bd-121">La definición de alerta se abre en el Diseñador de alertas de datos.</span><span class="sxs-lookup"><span data-stu-id="407bd-121">The alert definition opens in Data Alert Designer.</span></span> <span data-ttu-id="407bd-122">Para más información, vea [Modificar una alerta de datos en el Diseñador de alertas](edit-a-data-alert-in-alert-designer.md) y [Diseñador de alertas de datos](../../2014/reporting-services/data-alert-designer.md).</span><span class="sxs-lookup"><span data-stu-id="407bd-122">For more information, see [Edit a Data Alert in Alert Designer](edit-a-data-alert-in-alert-designer.md) and [Data Alert Designer](../../2014/reporting-services/data-alert-designer.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="407bd-123">Solo el usuario que creó la definición de alerta de datos puede modificarla.</span><span class="sxs-lookup"><span data-stu-id="407bd-123">Only the user that created the data alert definition can edit it.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="407bd-124">Si el informe ha cambiado y las fuentes de distribución de datos generadas desde el informe han cambiado, la definición de la alerta podría no ser válida.</span><span class="sxs-lookup"><span data-stu-id="407bd-124">If the report has changed and the data feeds generated from the report have changed the alert definition might no longer be valid.</span></span> <span data-ttu-id="407bd-125">Esto sucede cuando una columna a la que hacen referencia las reglas de la alerta se elimina del informe, su tipo de datos cambia, se incluye en otra fuente de distribución de datos o se elimina o mueve el informe.</span><span class="sxs-lookup"><span data-stu-id="407bd-125">This occurs when a column that the alert references in its rules is deleted from the report, changes data type, or is included in a different data feed or the report is deleted or moved.</span></span> <span data-ttu-id="407bd-126">Puede abrir una definición de alerta que no sea válida, pero no puede volver a guardarla hasta que sea válida con arreglo a la versión actual de la fuente de distribución de datos del informe en la que se basa.</span><span class="sxs-lookup"><span data-stu-id="407bd-126">You can open an alert definition that is not valid, but you cannot resave it until it is valid based on the current version of the report data feed that it is built upon.</span></span> <span data-ttu-id="407bd-127">Para más información sobre cómo se generan las fuentes de datos de informes, vea [Generar fuentes de distribución de datos a partir de informes &#40;Generador de informes y SSRS&#41;](report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="407bd-127">To learn more about how data feeds are generated from reports, see [Generating Data Feeds from Reports &#40;Report Builder and SSRS&#41;](report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span></span>  
  
### <a name="to-delete-an-alert-definition"></a><span data-ttu-id="407bd-128">Para eliminar una definición de alerta</span><span class="sxs-lookup"><span data-stu-id="407bd-128">To delete an alert definition</span></span>  
  
-   <span data-ttu-id="407bd-129">Haga clic con el botón derecho en la alerta de datos que quiere eliminar y haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="407bd-129">Right-click the data alert that you want to delete and click **Delete**.</span></span>  
  
     <span data-ttu-id="407bd-130">Después de eliminar la alerta, no se envían más mensajes de alerta.</span><span class="sxs-lookup"><span data-stu-id="407bd-130">When you delete the alert, no further alert messages are sent.</span></span>  
  
### <a name="to-run-an-alert"></a><span data-ttu-id="407bd-131">Para ejecutar una alerta</span><span class="sxs-lookup"><span data-stu-id="407bd-131">To run an alert</span></span>  
  
-   <span data-ttu-id="407bd-132">Haga clic con el botón derecho en la alerta de datos que quiere ejecutar y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="407bd-132">Right-click the data alert that you want to run and click **Run**.</span></span>  
  
     <span data-ttu-id="407bd-133">Se crea la instancia de alerta y el mensaje de alerta de datos se envía inmediatamente, independientemente de las opciones de programación que haya especificado en el Diseñador de alertas de datos.</span><span class="sxs-lookup"><span data-stu-id="407bd-133">The alert instance is created and the data alert message is immediately sent, regardless of the schedule options you specified in Data Alert Designer.</span></span> <span data-ttu-id="407bd-134">Por ejemplo, se enviará una alerta configurada para su envío semanal y solo si cambian los resultados.</span><span class="sxs-lookup"><span data-stu-id="407bd-134">For example, an alert configured to be sent weekly and then only if the results change is sent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="407bd-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="407bd-135">See Also</span></span>  
 <span data-ttu-id="407bd-136">[Administrador de alertas de datos para administradores de alertas](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) </span><span class="sxs-lookup"><span data-stu-id="407bd-136">[Data Alert Manager for Alerting Administrators](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) </span></span>  
 [<span data-ttu-id="407bd-137">Alertas de datos de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="407bd-137">Reporting Services Data Alerts</span></span>](../ssms/agent/alerts.md)  
  
  
