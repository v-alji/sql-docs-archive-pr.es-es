---
title: Activar o desactivar las características de Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services, configuration
- security [Reporting Services], strategies
ms.assetid: b69db02a-43a7-4fdc-ad9b-438d817a7f83
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f56f9984b5b02431db23b782652e5575af557bdb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672615"
---
# <a name="turn-reporting-services-features-on-or-off"></a><span data-ttu-id="98ed9-102">Activar o desactivar las características de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="98ed9-102">Turn Reporting Services Features On or Off</span></span>
  <span data-ttu-id="98ed9-103">Puede desactivar características del servidor de informes que no use como parte de una estrategia de bloqueo para reducir la superficie de ataque de un servidor de informes de producción.</span><span class="sxs-lookup"><span data-stu-id="98ed9-103">You can turn off report server features that you do not use as part of a lockdown strategy for reducing the attack surface of a production report server.</span></span> <span data-ttu-id="98ed9-104">En la mayoría de los casos, le interesará ejecutar las características de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] simultáneamente para poder hacer uso de toda la funcionalidad de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98ed9-104">In most cases, you will want to run [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] features concurrently to use all of the functionality provided in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="98ed9-105">Sin embargo, dependiendo del modelo de implementación, puede deshabilitar aquellas características que no necesite.</span><span class="sxs-lookup"><span data-stu-id="98ed9-105">However, depending on your deployment model, you can disable the features that you do not require.</span></span> <span data-ttu-id="98ed9-106">Por ejemplo, si todo el procesamiento de informes está configurado como operaciones programadas, puede habilitar solo el procesamiento en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="98ed9-106">For example, you can enable only the background processing if all report processing is configured as scheduled operations.</span></span> <span data-ttu-id="98ed9-107">Del mismo modo, puede ejecutar simplemente el servicio web del servidor de informes si solo desea informes a petición e interactivos.</span><span class="sxs-lookup"><span data-stu-id="98ed9-107">Similarly, you can run just the Report Server Web service if you only want interactive, on-demand reporting.</span></span>  
  
 <span data-ttu-id="98ed9-108">En los procedimientos de este tema, se muestra cómo desactivar características de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en modo nativo.</span><span class="sxs-lookup"><span data-stu-id="98ed9-108">The procedures in this topic show you how to turn off native mode [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] features.</span></span> <span data-ttu-id="98ed9-109">Las características se pueden configurar de varias maneras: editando directamente el archivo `RsReportServer.config` o con la faceta **Configuración de área expuesta para Reporting Services** de la administración basada en directivas de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98ed9-109">Features can be configured in different ways, such as by editing the `RsReportServer.config` file directly or by using the **Surface Area Configuration for Reporting Services** facet of Policy-Based Management in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="98ed9-110">Use los vínculos para buscar el procedimiento o los procedimientos en los que se explica cómo activar o desactivar una característica:</span><span class="sxs-lookup"><span data-stu-id="98ed9-110">Use the links to locate the procedure or procedures that explain how to turn a feature on or off:</span></span>  
  
-   [<span data-ttu-id="98ed9-111">Servicio Web del servidor de informes</span><span class="sxs-lookup"><span data-stu-id="98ed9-111">Report Server Web service</span></span>](#RSWebSvc)  
  
-   [<span data-ttu-id="98ed9-112">Eventos y procesamiento programados</span><span class="sxs-lookup"><span data-stu-id="98ed9-112">Scheduled events and processing</span></span>](#Sched)  
  
-   [<span data-ttu-id="98ed9-113">Administrador de informes</span><span class="sxs-lookup"><span data-stu-id="98ed9-113">Report Manager</span></span>](#ReportManager)  
  
-   [<span data-ttu-id="98ed9-114">Generador de informes</span><span class="sxs-lookup"><span data-stu-id="98ed9-114">Report Builder</span></span>](#ReportBuilder)  
  
-   [<span data-ttu-id="98ed9-115">Seguridad integrada de Windows para orígenes de datos de informe</span><span class="sxs-lookup"><span data-stu-id="98ed9-115">Windows Integrated security for report data sources</span></span>](#WinIntSec)  
  
##  <a name="report-server-web-service"></a><a name="RSWebSvc"></a><span data-ttu-id="98ed9-116">Servicio Web del servidor de informes</span><span class="sxs-lookup"><span data-stu-id="98ed9-116">Report Server Web Service</span></span>  
  
#### <a name="to-turn-on-or-off-the-report-server-web-service-by-editing-configuration"></a><span data-ttu-id="98ed9-117">Para activar o desactivar el servicio web del servidor de informes editando la configuración</span><span class="sxs-lookup"><span data-stu-id="98ed9-117">To turn on or off the Report Server Web service by editing configuration</span></span>  
  
1.  <span data-ttu-id="98ed9-118">Abra el archivo `RsReportServer.config` en un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="98ed9-118">Open the `RsReportServer.config` file in a text editor.</span></span> <span data-ttu-id="98ed9-119">Para más información, vea [Modificar un archivo de configuración de Reporting Services &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md) en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98ed9-119">For more information, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
2.  <span data-ttu-id="98ed9-120">Para activar el servicio web del servidor de informes, establezca `IsWebServiceEnabled` en `true`:</span><span class="sxs-lookup"><span data-stu-id="98ed9-120">To turn on the Report Server Web service, set `IsWebServiceEnabled` to `true`:</span></span>  
  
    ```  
    <IsWebServiceEnabled>true</IsWebServiceEnabled>  
    ```  
  
3.  <span data-ttu-id="98ed9-121">Para desactivar el servicio web del servidor de informes, establezca `IsWebServiceEnabled` en `false`:</span><span class="sxs-lookup"><span data-stu-id="98ed9-121">To turn off the Report Server Web service, set `IsWebServiceEnabled` to `false`:</span></span>  
  
    ```  
    <IsWebServiceEnabled>false</IsWebServiceEnabled>  
    ```  
  
4.  <span data-ttu-id="98ed9-122">Guarde los cambios y, a continuación, cierre el archivo.</span><span class="sxs-lookup"><span data-stu-id="98ed9-122">Save your changes and then close the file.</span></span>  
  
#### <a name="to-turn-on-or-off-the-report-server-web-service-by-using-sql-server-management-studio"></a><span data-ttu-id="98ed9-123">Para activar o desactivar el servicio web del servidor de informes con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="98ed9-123">To turn on or off the Report Server Web service by using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="98ed9-124">Abra [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] y conéctese a la instancia de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="98ed9-124">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance that you want to configure.</span></span>  
  
2.  <span data-ttu-id="98ed9-125">En Explorador de objetos, haga clic con el botón secundario en el [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] nodo, seleccione **directivas**y haga clic en **aspectos**.</span><span class="sxs-lookup"><span data-stu-id="98ed9-125">In Object Explorer, right-click the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] node, point to **Policies**, and click **Facets**.</span></span>  
  
3.  <span data-ttu-id="98ed9-126">En la lista **Faceta** , seleccione **Configuración de área expuesta para Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="98ed9-126">In the **Facet** list, select **Surface Area Configuration for Reporting Services**.</span></span>  
  
4.  <span data-ttu-id="98ed9-127">En **Propiedades de faceta**:</span><span class="sxs-lookup"><span data-stu-id="98ed9-127">Under **Facet Properties**:</span></span>  
  
    -   <span data-ttu-id="98ed9-128">Para activar el servicio Web del servidor de informes, establezca **WebServiceAndHTTPAccessEnabled** en `True` .</span><span class="sxs-lookup"><span data-stu-id="98ed9-128">To turn on the Report Server Web service, set **WebServiceAndHTTPAccessEnabled** to `True`.</span></span>  
  
    -   <span data-ttu-id="98ed9-129">Para desactivar el servicio Web del servidor de informes, establezca **WebServiceAndHTTPAccessEnabled** en `False` .</span><span class="sxs-lookup"><span data-stu-id="98ed9-129">To turn off the Report Server Web service, set **WebServiceAndHTTPAccessEnabled** to `False`.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="scheduled-events-and-delivery"></a><a name="Sched"></a> <span data-ttu-id="98ed9-130">Eventos programados y entrega programada</span><span class="sxs-lookup"><span data-stu-id="98ed9-130">Scheduled Events and Delivery</span></span>  
  
#### <a name="to-turn-on-or-off-scheduled-events-and-delivery-by-editing-configuration"></a><span data-ttu-id="98ed9-131">Para activar o desactivar los eventos programados y la entrega programada editando la configuración</span><span class="sxs-lookup"><span data-stu-id="98ed9-131">To turn on or off scheduled events and delivery by editing configuration</span></span>  
  
1.  <span data-ttu-id="98ed9-132">Abra el archivo RsReportServer.config en un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="98ed9-132">Open the RsReportServer.config file in a text editor.</span></span> <span data-ttu-id="98ed9-133">Para más información, vea [Modificar un archivo de configuración de Reporting Services &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md) en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98ed9-133">For more information, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
2.  <span data-ttu-id="98ed9-134">Para activar el procesamiento y la entrega de informes programados, establezca `IsSchedulingService`, `IsNotificationService` e `IsEventService` en `true`:</span><span class="sxs-lookup"><span data-stu-id="98ed9-134">To turn on scheduled report processing and delivery, set `IsSchedulingService`, `IsNotificationService`, and `IsEventService` to `true`:</span></span>  
  
    ```  
    <IsSchedulingService>true</IsSchedulingService>  
    <IsNotificationService>true</IsNotificationService>  
    <IsEventService>true</IsEventService>  
    ```  
  
3.  <span data-ttu-id="98ed9-135">Para desactivar el procesamiento y la entrega de informes programados, establezca `IsSchedulingService`, `IsNotificationService` e `IsEventService` en `false`:</span><span class="sxs-lookup"><span data-stu-id="98ed9-135">To turn off scheduled report processing and delivery, set `IsSchedulingService`, `IsNotificationService`, and `IsEventService` to `false`:</span></span>  
  
    ```  
    <IsSchedulingService>false</IsSchedulingService>  
    <IsNotificationService>false</IsNotificationService>  
    <IsEventService>false</IsEventService>  
    ```  
  
4.  <span data-ttu-id="98ed9-136">Guarde los cambios y, a continuación, cierre el archivo.</span><span class="sxs-lookup"><span data-stu-id="98ed9-136">Save your changes and then close the file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="98ed9-137">No puede desactivar completamente ningún procesamiento en segundo plano porque proporciona la funcionalidad de mantenimiento de las bases de datos que se requiere para las operaciones de servidor.</span><span class="sxs-lookup"><span data-stu-id="98ed9-137">You cannot turn off background processing completely because it provides database maintenance functionality that is required for server operations.</span></span>  
  
#### <a name="to-turn-on-or-off-scheduled-events-and-delivery-by-using-sql-server-management-studio"></a><span data-ttu-id="98ed9-138">Para activar o desactivar los eventos programados y la entrega programada con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="98ed9-138">To turn on or off scheduled events and delivery by using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="98ed9-139">Abra [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] y conéctese a la instancia de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="98ed9-139">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance that you want to configure.</span></span>  
  
2.  <span data-ttu-id="98ed9-140">En Explorador de objetos, haga clic con el botón secundario en el [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] nodo, seleccione **directivas**y haga clic en **aspectos**.</span><span class="sxs-lookup"><span data-stu-id="98ed9-140">In Object Explorer, right-click the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] node, point to **Policies**, and click **Facets**.</span></span>  
  
3.  <span data-ttu-id="98ed9-141">En la lista **Faceta** , seleccione **Configuración de área expuesta para Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="98ed9-141">In the **Facet** list, select **Surface Area Configuration for Reporting Services**.</span></span>  
  
4.  <span data-ttu-id="98ed9-142">En **Propiedades de faceta**:</span><span class="sxs-lookup"><span data-stu-id="98ed9-142">Under **Facet Properties**:</span></span>  
  
    -   <span data-ttu-id="98ed9-143">Para activar los eventos programados y la entrega, establezca **ScheduleEventsAndReportDeliveryEnabled** en `True` .</span><span class="sxs-lookup"><span data-stu-id="98ed9-143">To turn on scheduled events and delivery, set **ScheduleEventsAndReportDeliveryEnabled** to `True`.</span></span>  
  
    -   <span data-ttu-id="98ed9-144">Para desactivar los eventos programados y la entrega, establezca **ScheduleEventsAndReportDeliveryEnabled** en `False` .</span><span class="sxs-lookup"><span data-stu-id="98ed9-144">To turn off scheduled events and delivery, set **ScheduleEventsAndReportDeliveryEnabled** to `False`.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
> [!NOTE]  
>  <span data-ttu-id="98ed9-145">No puede desactivar completamente ningún procesamiento en segundo plano porque proporciona la funcionalidad de mantenimiento de las bases de datos que se requiere para las operaciones de servidor.</span><span class="sxs-lookup"><span data-stu-id="98ed9-145">You cannot turn off background processing completely because it provides database maintenance functionality that is required for server operations.</span></span>  
  
##  <a name="report-manager"></a><a name="ReportManager"></a><span data-ttu-id="98ed9-146">Administrador de informes</span><span class="sxs-lookup"><span data-stu-id="98ed9-146">Report Manager</span></span>  
  
#### <a name="to-turn-on-or-off-report-manager-by-editing-configuration"></a><span data-ttu-id="98ed9-147">Para activar o desactivar el Administrador de informes editando la configuración</span><span class="sxs-lookup"><span data-stu-id="98ed9-147">To turn on or off Report Manager by editing configuration</span></span>  
  
1.  <span data-ttu-id="98ed9-148">Abra el archivo RsReportServer.config en un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="98ed9-148">Open the RsReportServer.config file in a text editor.</span></span> <span data-ttu-id="98ed9-149">Para obtener instrucciones , vea [Modificar un archivo de configuración de Reporting Services &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md) en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98ed9-149">For instructions, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
2.  <span data-ttu-id="98ed9-150">Para activar el Administrador de informes, establezca `IsReportManagerEnabled` en `true`:</span><span class="sxs-lookup"><span data-stu-id="98ed9-150">To turn on Report Manager, set `IsReportManagerEnabled` to `true`:</span></span>  
  
    ```  
    <IsReportManagerEnabled>true</IsReportManagerEnabled>  
    ```  
  
3.  <span data-ttu-id="98ed9-151">Para desactivar el Administrador de informes, establezca `IsReportManagerEnabled` en `false`:</span><span class="sxs-lookup"><span data-stu-id="98ed9-151">To turn off Report Manager, set `IsReportManagerEnabled` to `false`:</span></span>  
  
    ```  
    <IsReportManagerEnabled>false</IsReportManagerEnabled>  
    ```  
  
4.  <span data-ttu-id="98ed9-152">Guarde los cambios y, a continuación, cierre el archivo.</span><span class="sxs-lookup"><span data-stu-id="98ed9-152">Save your changes and then close the file.</span></span>  
  
#### <a name="to-turn-on-or-off-report-manager-by-using-sql-server-management-studio"></a><span data-ttu-id="98ed9-153">Para activar o desactivar el Administrador de informes con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="98ed9-153">To turn on or off Report Manager by using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="98ed9-154">Abra [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] y conéctese a la instancia de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="98ed9-154">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance that you want to configure.</span></span>  
  
2.  <span data-ttu-id="98ed9-155">En el **Explorador de objetos**, haga clic con el botón derecho en el nodo [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , seleccione **Directivas**y, después, haga clic en **Facetas**.</span><span class="sxs-lookup"><span data-stu-id="98ed9-155">In **Object Explorer**, right-click the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] node, point to **Policies**, and click **Facets**.</span></span>  
  
3.  <span data-ttu-id="98ed9-156">En la lista **Faceta** , seleccione **Configuración de área expuesta para Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="98ed9-156">In the **Facet** list, select **Surface Area Configuration for Reporting Services**.</span></span>  
  
4.  <span data-ttu-id="98ed9-157">En **Propiedades de faceta**:</span><span class="sxs-lookup"><span data-stu-id="98ed9-157">Under **Facet Properties**:</span></span>  
  
    -   <span data-ttu-id="98ed9-158">Para activar Administrador de informes, establezca **ReportManagerEnabled** en `True` .</span><span class="sxs-lookup"><span data-stu-id="98ed9-158">To turn on Report Manager, set **ReportManagerEnabled** to `True`.</span></span>  
  
    -   <span data-ttu-id="98ed9-159">Para desactivar Administrador de informes, establezca **ReportManagerEnabled** en `False` .</span><span class="sxs-lookup"><span data-stu-id="98ed9-159">To turn off Report Manager, set **ReportManagerEnabled** to `False`.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="report-builder"></a><span data-ttu-id="98ed9-160">Generador de informes de <a name="ReportBuilder"></a></span><span class="sxs-lookup"><span data-stu-id="98ed9-160"><a name="ReportBuilder"></a> Report Builder</span></span>  
  
#### <a name="to-turn-on-or-off-report-builder-by-using-sql-server-management-studio"></a><span data-ttu-id="98ed9-161">Para activar o desactivar el Generador de informes con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="98ed9-161">To turn on or off Report Builder by using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="98ed9-162">Abra [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] y conéctese a la instancia de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="98ed9-162">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance that you want to configure.</span></span>  
  
2.  <span data-ttu-id="98ed9-163">En el Explorador de objetos, haga clic con el botón derecho en el nodo [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="98ed9-163">In Object Explorer, right-click the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] node, and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="98ed9-164">En el cuadro de diálogo **Propiedades del servidor** , en **Seleccionar una página**, haga clic en **Seguridad**.</span><span class="sxs-lookup"><span data-stu-id="98ed9-164">In the **Server Properties** dialog box, under **Select a page**, click **Security**.</span></span>  
  
    -   <span data-ttu-id="98ed9-165">Para activar el Generador de informes, seleccione la opción **Habilitar ejecuciones de notificaciones ad hoc** .</span><span class="sxs-lookup"><span data-stu-id="98ed9-165">To turn on Report Builder, select the **Enable ad hoc report executions** option.</span></span>  
  
    -   <span data-ttu-id="98ed9-166">Para desactivar el Generador de informes, anule la selección de la opción **Habilitar ejecuciones de notificaciones ad hoc** .</span><span class="sxs-lookup"><span data-stu-id="98ed9-166">To turn off Report Builder, unselect the **Enable ad hoc report executions** option.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="windows-integrated-security"></a><a name="WinIntSec"></a> <span data-ttu-id="98ed9-167">Seguridad integrada de Windows</span><span class="sxs-lookup"><span data-stu-id="98ed9-167">Windows Integrated Security</span></span>  
  
#### <a name="to-turn-on-or-off-windows-integrated-security-by-using-sql-server-management-studio"></a><span data-ttu-id="98ed9-168">Para activar o desactivar la seguridad integrada de Windows con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="98ed9-168">To turn on or off Windows Integrated security by using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="98ed9-169">Abra [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] y conéctese a la instancia de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="98ed9-169">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance that you want to configure.</span></span>  
  
2.  <span data-ttu-id="98ed9-170">En el Explorador de objetos, haga clic con el botón derecho en el nodo [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="98ed9-170">In Object Explorer, right-click the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] node, and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="98ed9-171">En el cuadro de diálogo **Propiedades del servidor** , en **Seleccionar una página**, haga clic en **Seguridad**.</span><span class="sxs-lookup"><span data-stu-id="98ed9-171">In the **Server Properties** dialog box, under **Select a page**, click **Security**.</span></span>  
  
    -   <span data-ttu-id="98ed9-172">Para activar la seguridad integrada de Windows, seleccione la opción **Habilitar la seguridad integrada de Windows para los orígenes de datos de informes** .</span><span class="sxs-lookup"><span data-stu-id="98ed9-172">To turn on Windows Integrated security, select the **Enable Windows Integrated security for report data sources** option.</span></span>  
  
    -   <span data-ttu-id="98ed9-173">Para desactivar la seguridad integrada de Windows, anule la selección de la opción **Habilitar la seguridad integrada de Windows para los orígenes de datos de informes** .</span><span class="sxs-lookup"><span data-stu-id="98ed9-173">To turn off Windows integrated security, unselect the **Enable Windows Integrated security for report data sources** option.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="98ed9-174">Consulte también</span><span class="sxs-lookup"><span data-stu-id="98ed9-174">See Also</span></span>  
 [<span data-ttu-id="98ed9-175">Administrador de configuración de Reporting Services &#40;modo nativo&#41;</span><span class="sxs-lookup"><span data-stu-id="98ed9-175">Reporting Services Configuration Manager &#40;Native Mode&#41;</span></span>](../../sql-server/install/reporting-services-configuration-manager-native-mode.md)  
  
  
