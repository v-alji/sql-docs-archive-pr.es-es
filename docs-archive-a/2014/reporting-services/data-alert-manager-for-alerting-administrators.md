---
title: Administrador de alertas de datos para administradores de alertas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- managing, alerts
- managing, data alerts
ms.assetid: 32fd968f-1c0c-4ba8-851c-8a3b5e1fbbf2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 050107d07e976b99609a456506eb7bbfbf5e20d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674640"
---
# <a name="data-alert-manager-for-alerting-administrators"></a><span data-ttu-id="2c1c6-102">Administrador de alertas de datos para administradores de alertas</span><span class="sxs-lookup"><span data-stu-id="2c1c6-102">Data Alert Manager for Alerting Administrators</span></span>
  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="2c1c6-103">proporciona el Administrador de alertas de datos para SharePoint, que permite a los administradores de alertas administrar las alertas de datos.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-103">provides Data Alert Manager for SharePoint alerting administrators to manage data alerts.</span></span> <span data-ttu-id="2c1c6-104">Los administradores de alertas pueden ver información sobre todas las alertas guardadas en el sitio y eliminarlas.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-104">Alerting administrators can view information about all alerts saved to the site and delete alerts.</span></span> <span data-ttu-id="2c1c6-105">En la imagen siguiente se muestran las características disponibles en el Administrador de alertas de datos para los administradores de alertas de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-105">The following picture shows the features available to SharePoint alerting managers in Data Alert Manager.</span></span>

 <span data-ttu-id="2c1c6-106">![Administrador de alertas para administradores de sitios de SharePoint](media/rs-alertmanagersite.gif "Administrador de alertas para administradores de sitios de SharePoint")</span><span class="sxs-lookup"><span data-stu-id="2c1c6-106">![Alert Manager for SharePoin tsite administrators](media/rs-alertmanagersite.gif "Alert Manager for SharePoin tsite administrators")</span></span>

 <span data-ttu-id="2c1c6-107">Cuando se habilita el sitio para las alertas de datos, se crean dos páginas de SharePoint, MyDataAlerts.aspx y SiteDataAlerts.aspx, que se agregan al sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-107">When the site is enabled for data alerts, two SharePoint pages, MyDataAlerts.aspx and SiteDataAlerts.aspx are created and added to the SharePoint site.</span></span> <span data-ttu-id="2c1c6-108">SiteDataAlerts.aspx es el Administrador de alertas de datos para los administradores de alertas.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-108">SiteDataAlerts.aspx is Data Alert Manager for alerting administrators.</span></span> <span data-ttu-id="2c1c6-109">Los administradores de alertas pueden abrir el Administrador de alertas de datos desde la página Configuración del sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-109">Alerting administrators can open Data Alert Manager from the Site Settings SharePoint page.</span></span> <span data-ttu-id="2c1c6-110">Los administradores de alertas deben tener el permiso Administrar alertas de SharePoint para abrir el Administrador de alertas de datos.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-110">Alerting administrators must have SharePoint Manage Alerts permission to open Data Alert Manager.</span></span>

 <span data-ttu-id="2c1c6-111">También se puede abrir el Administrador de alertas de datos directamente mediante una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-111">You can also open Data Alert Manager directly by using a URL.</span></span> <span data-ttu-id="2c1c6-112">A continuación se muestra la sintaxis de la dirección URL:</span><span class="sxs-lookup"><span data-stu-id="2c1c6-112">The following shows the syntax of the URL:</span></span>

 `http: //<site name>/_layouts/ReportServer/ SiteDataAlerts.aspx`

> [!NOTE]
>  <span data-ttu-id="2c1c6-113">Como administrador de alertas, puede conceder permiso a los trabajadores de la información para tener acceso a las características de alertas de datos de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2c1c6-113">As an alerting administrator, you can grant permission to information workers to access the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] data alerts features.</span></span> <span data-ttu-id="2c1c6-114">Para obtener más información sobre los permisos necesarios, vea [Alertas de datos de Reporting Services](../ssms/agent/alerts.md).</span><span class="sxs-lookup"><span data-stu-id="2c1c6-114">For more information about the required permissions, see [Reporting Services Data Alerts](../ssms/agent/alerts.md).</span></span>

##  <a name="viewing-data-alert-information"></a><a name="ViewingAlerts"></a> <span data-ttu-id="2c1c6-115">Ver información de alertas de datos</span><span class="sxs-lookup"><span data-stu-id="2c1c6-115">Viewing Data Alert Information</span></span>
 <span data-ttu-id="2c1c6-116">Cuando se instala y se configura Reporting Services en SharePoint, la página Configuración del sitio de SharePoint incluye las opciones de **Reporting Services** .</span><span class="sxs-lookup"><span data-stu-id="2c1c6-116">When Reporting Services is installed and configured in SharePoint, the Site Settings SharePoint page includes the **Reporting Services** options.</span></span> <span data-ttu-id="2c1c6-117">Los administradores de alertas hacen clic en la opción **Administrar alertas de datos** en Reporting Services para abrir el Administrador de alertas de datos.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-117">Alerting administrators click the **Manage Data Alerts** option within Reporting Service to open Data Alert Manager.</span></span> <span data-ttu-id="2c1c6-118">En la imagen siguiente se muestra en qué lugar de la página Configuración del sitio se abre el Administrador de alertas de datos.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-118">The following picture shows from where on the Site Settings page you open Data Alert Manager.</span></span>

 <span data-ttu-id="2c1c6-119">![Sección Reporting Services de la página Configuración del sitio](media/rs-sitesettings.gif "Sección Reporting Services de la página Configuración del sitio")</span><span class="sxs-lookup"><span data-stu-id="2c1c6-119">![Reporting Services section of Site Settings page](media/rs-sitesettings.gif "Reporting Services section of Site Settings page")</span></span>

 <span data-ttu-id="2c1c6-120">El Administrador de alertas de datos incluye una tabla con el nombre de la alerta, el nombre del informe, el nombre del propietario de la alerta, el número de veces que se envió la alerta, la última vez que se ejecutó la alerta, la última vez que se modificó la definición de la alerta y el estado del mensaje de alerta.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-120">Data Alert Manager includes a table that lists the alert name, report name, the name of the alert owner, the number the alert message was sent, the last time the alert was run, the last time the alert definition was modified, and the status of the alert message.</span></span> <span data-ttu-id="2c1c6-121">Si la alerta no se puede generar o enviar, la columna de estado contiene información sobre el error que le ayudará a solucionar los problemas relacionados con la alerta.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-121">If the alert cannot be generated or generated or sent, the status column contains information about the error and helps you troubleshoot the alert.</span></span> <span data-ttu-id="2c1c6-122">Para más información, consulte [Administrar todas las alertas de datos de un sitio de SharePoint en el Administrador de alertas de datos](manage-all-data-alerts-on-a-sharepoint-site-in-data-alert-manager.md).</span><span class="sxs-lookup"><span data-stu-id="2c1c6-122">For more information, see [Manage All Data Alerts on a SharePoint Site in Data Alert Manager](manage-all-data-alerts-on-a-sharepoint-site-in-data-alert-manager.md).</span></span>

 <span data-ttu-id="2c1c6-123">En la tabla siguiente se muestran datos de ejemplo de una tabla del Administrador de alertas de datos.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-123">The following table shows sample data from a table in Data Alert Manager.</span></span> <span data-ttu-id="2c1c6-124">Cuando se produce un error, el mensaje de error y el identificador de la entrada del registro (un GUID) se incluyen en el campo **Estado** de la tabla.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-124">When an error occurs, the error message and the identifier of the entry in the log (a GUID) are included in the **Status** field in the table.</span></span>

|<span data-ttu-id="2c1c6-125">Nombre de la alerta</span><span class="sxs-lookup"><span data-stu-id="2c1c6-125">Alert Name</span></span>|<span data-ttu-id="2c1c6-126">Nombre del informe</span><span class="sxs-lookup"><span data-stu-id="2c1c6-126">Report Name</span></span>|<span data-ttu-id="2c1c6-127">Creado por</span><span class="sxs-lookup"><span data-stu-id="2c1c6-127">Created By</span></span>|<span data-ttu-id="2c1c6-128">Alertas enviadas</span><span class="sxs-lookup"><span data-stu-id="2c1c6-128">Sent Alerts</span></span>|<span data-ttu-id="2c1c6-129">Última ejecución</span><span class="sxs-lookup"><span data-stu-id="2c1c6-129">Last Run</span></span>|<span data-ttu-id="2c1c6-130">Modificado por última vez</span><span class="sxs-lookup"><span data-stu-id="2c1c6-130">Last Modified</span></span>|<span data-ttu-id="2c1c6-131">Estado</span><span class="sxs-lookup"><span data-stu-id="2c1c6-131">Status</span></span>|
|----------------|-----------------|----------------|-----------------|--------------|-------------------|------------|
|<span data-ttu-id="2c1c6-132">SalesQTR</span><span class="sxs-lookup"><span data-stu-id="2c1c6-132">SalesQTR</span></span>|<span data-ttu-id="2c1c6-133">SalesByTerritoryAndQTR</span><span class="sxs-lookup"><span data-stu-id="2c1c6-133">SalesByTerritoryAndQTR</span></span>|<span data-ttu-id="2c1c6-134">Lauren Johnson</span><span class="sxs-lookup"><span data-stu-id="2c1c6-134">Lauren Johnson</span></span>|<span data-ttu-id="2c1c6-135">4</span><span class="sxs-lookup"><span data-stu-id="2c1c6-135">4</span></span>|<span data-ttu-id="2c1c6-136">6/12/2011</span><span class="sxs-lookup"><span data-stu-id="2c1c6-136">6/12/2011</span></span>|<span data-ttu-id="2c1c6-137">6/1/2011</span><span class="sxs-lookup"><span data-stu-id="2c1c6-137">6/1/2011</span></span>|<span data-ttu-id="2c1c6-138">La última alerta se ejecutó correctamente y se envió.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-138">Last alert ran successfully and alert was sent.</span></span>|
|<span data-ttu-id="2c1c6-139">UnitsSold</span><span class="sxs-lookup"><span data-stu-id="2c1c6-139">UnitsSold</span></span>|<span data-ttu-id="2c1c6-140">ProductsSalesByQTR</span><span class="sxs-lookup"><span data-stu-id="2c1c6-140">ProductsSalesByQTR</span></span>|<span data-ttu-id="2c1c6-141">Michael Blythe</span><span class="sxs-lookup"><span data-stu-id="2c1c6-141">Michael Blythe</span></span>|<span data-ttu-id="2c1c6-142">2</span><span class="sxs-lookup"><span data-stu-id="2c1c6-142">2</span></span>|<span data-ttu-id="2c1c6-143">7/1/2011</span><span class="sxs-lookup"><span data-stu-id="2c1c6-143">7/1/2011</span></span>|<span data-ttu-id="2c1c6-144">6/28/2011</span><span class="sxs-lookup"><span data-stu-id="2c1c6-144">6/28/2011</span></span>|<span data-ttu-id="2c1c6-145">La última alerta se ejecutó correctamente, pero los datos no se modificaron y no se envió la alerta.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-145">Last alert ran successfully, but the data was unchanged and no alert was sent.</span></span>|
|<span data-ttu-id="2c1c6-146">InventoryCount</span><span class="sxs-lookup"><span data-stu-id="2c1c6-146">InventoryCount</span></span>|<span data-ttu-id="2c1c6-147">StockStatusByQTR</span><span class="sxs-lookup"><span data-stu-id="2c1c6-147">StockStatusByQTR</span></span>|<span data-ttu-id="2c1c6-148">Lauren Johnson</span><span class="sxs-lookup"><span data-stu-id="2c1c6-148">Lauren Johnson</span></span>|<span data-ttu-id="2c1c6-149">7</span><span class="sxs-lookup"><span data-stu-id="2c1c6-149">7</span></span>|<span data-ttu-id="2c1c6-150">7/10/2011</span><span class="sxs-lookup"><span data-stu-id="2c1c6-150">7/10/2011</span></span>|<span data-ttu-id="2c1c6-151">7/2/2011</span><span class="sxs-lookup"><span data-stu-id="2c1c6-151">7/2/2011</span></span>|<span data-ttu-id="2c1c6-152">\<error message>El archivo de registro contiene información detallada sobre el error.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-152">\<error message>The log file contains detailed information about the error.</span></span> <span data-ttu-id="2c1c6-153">Consulte la entrada de registro con el identificador: \<GUID> .</span><span class="sxs-lookup"><span data-stu-id="2c1c6-153">Refer to the log entry with the identifier: \<GUID>.</span></span>|
|<span data-ttu-id="2c1c6-154">TopPromotion</span><span class="sxs-lookup"><span data-stu-id="2c1c6-154">TopPromotion</span></span>|<span data-ttu-id="2c1c6-155">PromotionTracking</span><span class="sxs-lookup"><span data-stu-id="2c1c6-155">PromotionTracking</span></span>|<span data-ttu-id="2c1c6-156">Cristian Petculescu</span><span class="sxs-lookup"><span data-stu-id="2c1c6-156">Cristian Petculescu</span></span>|<span data-ttu-id="2c1c6-157">0</span><span class="sxs-lookup"><span data-stu-id="2c1c6-157">0</span></span>||<span data-ttu-id="2c1c6-158">5/23/2011</span><span class="sxs-lookup"><span data-stu-id="2c1c6-158">5/23/2011</span></span>|<span data-ttu-id="2c1c6-159">Alerta creada.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-159">Alert created.</span></span>|

 <span data-ttu-id="2c1c6-160">Para obtener más información, vea [administrar todas las alertas de datos en un sitio de SharePoint en el administrador de alertas de datos](manage-all-data-alerts-on-a-sharepoint-site-in-data-alert-manager.md).</span><span class="sxs-lookup"><span data-stu-id="2c1c6-160">For more information see, [Manage All Data Alerts on a SharePoint Site in Data Alert Manager](manage-all-data-alerts-on-a-sharepoint-site-in-data-alert-manager.md).</span></span>

 <span data-ttu-id="2c1c6-161">Puede ver todas las alertas creadas por los usuarios del sitio.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-161">You can view all alerts created by site users.</span></span> <span data-ttu-id="2c1c6-162">Puede seleccionar un usuario y luego elegir si desea ver todas sus alertas o solo las alertas de un informe determinado.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-162">You choose a user and then choose whether to view all their alerts or only alerts for a specific report.</span></span>


##  <a name="delete-data-alerts"></a><a name="DeleteAlerts"></a><span data-ttu-id="2c1c6-163">Eliminar alertas de datos</span><span class="sxs-lookup"><span data-stu-id="2c1c6-163">Delete Data Alerts</span></span>
 <span data-ttu-id="2c1c6-164">Las definiciones de alertas se eliminan desde el Administrador de alertas de datos.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-164">You delete alerts definitions from Data Alert Manager.</span></span> <span data-ttu-id="2c1c6-165">Cada definición de alerta de datos tiene un propietario, que es el usuario de SharePoint que la creó.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-165">Every data alert definition has an owner, the SharePoint user who created it.</span></span> <span data-ttu-id="2c1c6-166">Los propietarios solo pueden eliminar las definiciones de alertas que han creado ellos mismos.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-166">Owners can delete only the alert definitions that they created.</span></span> <span data-ttu-id="2c1c6-167">Para obtener más información, vea [Administrar mis alertas de datos en el Administrador de alertas de datos](manage-my-data-alerts-in-data-alert-manager.md).</span><span class="sxs-lookup"><span data-stu-id="2c1c6-167">For more information, see [Manage My Data Alerts in Data Alert Manager](manage-my-data-alerts-in-data-alert-manager.md).</span></span>

 <span data-ttu-id="2c1c6-168">Los administradores de alertas de SharePoint pueden ver la lista de las definiciones de alertas creadas por todos los usuarios del sitio y eliminarlas.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-168">A SharePoint alerting administrators can list and then delete alert definitions created by all users of the site.</span></span> <span data-ttu-id="2c1c6-169">Para obtener más información, vea [administrar todas las alertas de datos en un sitio de SharePoint en el administrador de alertas de datos](manage-all-data-alerts-on-a-sharepoint-site-in-data-alert-manager.md) .</span><span class="sxs-lookup"><span data-stu-id="2c1c6-169">For more information, see [Manage All Data Alerts on a SharePoint Site in Data Alert Manager](manage-all-data-alerts-on-a-sharepoint-site-in-data-alert-manager.md)</span></span>

 <span data-ttu-id="2c1c6-170">Después de eliminar una definición de alerta, no se envían más alertas.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-170">After you delete the alert definition, no further alerts are sent.</span></span> <span data-ttu-id="2c1c6-171">Sin embargo, si consulta la base de datos de alertas puede que todavía exista la definición de la alerta.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-171">However, if you query the alerting database you might find that the alert definition still exists.</span></span> <span data-ttu-id="2c1c6-172">El servicio de alertas realiza limpiezas según una programación, y la definición de la alerta se eliminará definitivamente durante la limpieza siguiente.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-172">The alerting service performs clean up on a schedule and the alert definition is deleted permanently in the next cleanup.</span></span> <span data-ttu-id="2c1c6-173">El intervalo de limpieza predeterminado es de 20 minutos.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-173">The default cleanup interval is 20 minutes.</span></span> <span data-ttu-id="2c1c6-174">Este y otros intervalos de limpieza son configurables.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-174">This and other cleanup intervals are configurable.</span></span> <span data-ttu-id="2c1c6-175">Para obtener más información, vea [Alertas de datos de Reporting Services](../ssms/agent/alerts.md).</span><span class="sxs-lookup"><span data-stu-id="2c1c6-175">For more information, see [Reporting Services Data Alerts](../ssms/agent/alerts.md).</span></span>


##  <a name="related-tasks"></a><a name="HowTo"></a> <span data-ttu-id="2c1c6-176">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="2c1c6-176">Related Tasks</span></span>
 <span data-ttu-id="2c1c6-177">En esta sección se enumera un procedimiento que muestra cómo administrar las alertas.</span><span class="sxs-lookup"><span data-stu-id="2c1c6-177">This section lists a procedure that shows you how to manage your alerts.</span></span>

-   [<span data-ttu-id="2c1c6-178">Administrar todas las alertas de datos de un sitio de SharePoint en el Administrador de alertas de datos</span><span class="sxs-lookup"><span data-stu-id="2c1c6-178">Manage All Data Alerts on a SharePoint Site in Data Alert Manager</span></span>](manage-all-data-alerts-on-a-sharepoint-site-in-data-alert-manager.md)


## <a name="see-also"></a><span data-ttu-id="2c1c6-179">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2c1c6-179">See Also</span></span>
 [<span data-ttu-id="2c1c6-180">Alertas de datos de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="2c1c6-180">Reporting Services Data Alerts</span></span>](../ssms/agent/alerts.md)

