---
title: Reporting Services aplicaciones de servicio y servicio de SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 501aa9ee-8c13-458c-bf6f-24e00c82681b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5654764f7913002cdae58d3264848250a292c585
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678054"
---
# <a name="reporting-services-sharepoint-service-and-service-applications"></a><span data-ttu-id="e8cd4-102">Aplicaciones de servicio y servicio de SharePoint de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="e8cd4-102">Reporting Services SharePoint Service and Service Applications</span></span>
  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="e8cd4-103">se ha diseñado como un servicio de SharePoint y utiliza un servicio de SharePoint y una o varias aplicaciones de servicio.</span><span class="sxs-lookup"><span data-stu-id="e8cd4-103">SharePoint mode is architected on the SharePoint service architecture and utilizes a SharePoint service and one to many service applications.</span></span> <span data-ttu-id="e8cd4-104">Al crear una aplicación de servicio, el servicio estará disponible y se generará la base de datos de aplicación del servicio.</span><span class="sxs-lookup"><span data-stu-id="e8cd4-104">Creating a service application makes the service available and generates the service application database.</span></span> <span data-ttu-id="e8cd4-105">Puede crear varias aplicaciones de servicio de Reporting Services pero una aplicación de servicio es suficiente para la mayor parte de los escenarios de implementación.</span><span class="sxs-lookup"><span data-stu-id="e8cd4-105">You can create multiple Reporting Services service applications but one service application is sufficient for most deployment scenarios.</span></span>  
  
 <span data-ttu-id="e8cd4-106">Este tema contiene la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="e8cd4-106">This topic covers the following information:</span></span>  
  
-   [<span data-ttu-id="e8cd4-107">Crear una aplicación de servicio de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="e8cd4-107">Creating a Reporting Services Service Application</span></span>](#bkmk_createapp)  
  
-   [<span data-ttu-id="e8cd4-108">Modificar las asociaciones de la aplicación de servicio con un grupo de servidores proxy</span><span class="sxs-lookup"><span data-stu-id="e8cd4-108">Modify the Associations of the Service Application with a proxy group</span></span>](#bkmk_associations)  
  
-   [<span data-ttu-id="e8cd4-109">Modificar las propiedades de la aplicación de servicio</span><span class="sxs-lookup"><span data-stu-id="e8cd4-109">Edit Service Application Properties</span></span>](#bkmk_editserviceapplication)  
  
-   [<span data-ttu-id="e8cd4-110">Para crear una aplicación de servicio de Reporting Services mediante PowerShell</span><span class="sxs-lookup"><span data-stu-id="e8cd4-110">To create a Reporting Services Service Application using PowerShell</span></span>](#bkmk_powershell_create_ssrs_serviceapp)  
  
-   [<span data-ttu-id="e8cd4-111">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="e8cd4-111">Related Tasks</span></span>](#bkmk_related)  
  
##  <a name="creating-a-reporting-services-service-application"></a><a name="bkmk_createapp"></a><span data-ttu-id="e8cd4-112">Creación de una aplicación de servicio de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="e8cd4-112">Creating a Reporting Services Service Application</span></span>  
 <span data-ttu-id="e8cd4-113">Puede usar los scripts de PowerShell o la Administración central de SharePoint para crear las aplicaciones de servicio de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e8cd4-113">You can use SharePoint Central Administration or PowerShell scripts to create the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] services applications.</span></span> <span data-ttu-id="e8cd4-114">Para obtener más información sobre cómo usar la Administración central de SharePoint, vea la sección "Crear una aplicación de servicio de Reporting Services" en [Instalar el modo de SharePoint de Reporting Services para SharePoint 2010](../../2014/sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2010.md).</span><span class="sxs-lookup"><span data-stu-id="e8cd4-114">For more information on using SharePoint Central Administration, see the "Create a Reporting Services Service Application" section in [Install Reporting Services SharePoint Mode for SharePoint 2010](../../2014/sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2010.md).</span></span> <span data-ttu-id="e8cd4-115">Consulte la sección de PowerShell más adelante en este tema para ver un ejemplo de un script de PowerShell para crear aplicaciones de servicio.</span><span class="sxs-lookup"><span data-stu-id="e8cd4-115">See the PowerShell section later in this topic for a sample PowerShell script for creating service applications.</span></span>  
  
##  <a name="modify-the-associations-of-the-service-application-with-a-proxy-group"></a><a name="bkmk_associations"></a><span data-ttu-id="e8cd4-116">Modificar las asociaciones de la aplicación de servicio con un grupo de servidores proxy</span><span class="sxs-lookup"><span data-stu-id="e8cd4-116">Modify the Associations of the Service Application with a proxy group</span></span>  
 <span data-ttu-id="e8cd4-117">La nueva página para crear aplicaciones de servicio contiene la sección **Asociación de aplicaciones web**.</span><span class="sxs-lookup"><span data-stu-id="e8cd4-117">The New page for creating a services application contains the section **Web Application Association**.</span></span> <span data-ttu-id="e8cd4-118">La sección le permite asociar la aplicación de servicio cuando la cree.</span><span class="sxs-lookup"><span data-stu-id="e8cd4-118">The section allows you to associate your service application as you create it.</span></span> <span data-ttu-id="e8cd4-119">Siga los pasos siguientes para cambiar la asociación y asignar una configuración de cliente a la aplicación de servicio.</span><span class="sxs-lookup"><span data-stu-id="e8cd4-119">Use the following steps to change the association and assign a customer configuration to the service application.</span></span> <span data-ttu-id="e8cd4-120">El mismo proceso general se puede usar también para agregar el proxy al grupo predeterminado en lugar de cambiar la asociación de la aplicación de servicio a un grupo personalizado.</span><span class="sxs-lookup"><span data-stu-id="e8cd4-120">The same general process can also be used to add the proxy to the default group rather than changing the association of the service application to a custom group.</span></span>  
  
1.  <span data-ttu-id="e8cd4-121">En Administración central de SharePoint, en Administración de aplicaciones, haga clic en **Configurar las asociaciones de aplicación de servicio**.</span><span class="sxs-lookup"><span data-stu-id="e8cd4-121">In SharePoint Central Administration, in the Application Management, click **Configure Service Application Associations**.</span></span>  
  
2.  <span data-ttu-id="e8cd4-122">En la página Asociaciones de aplicaciones de servicio, cambie la vista a **Aplicaciones de servicio**.</span><span class="sxs-lookup"><span data-stu-id="e8cd4-122">On the Service application Associations page, change the view to **Service Applications**.</span></span>  
  
3.  <span data-ttu-id="e8cd4-123">Busque el nombre de la nueva aplicación de servicio de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] y haga clic en él.</span><span class="sxs-lookup"><span data-stu-id="e8cd4-123">Find and click the name of your new [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Service application.</span></span> <span data-ttu-id="e8cd4-124">Puede hacer clic en el **valor predeterminado** del nombre del grupo de proxy de aplicación para agregar el proxy al grupo predeterminado en lugar de completar los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="e8cd4-124">You could also click the application proxy group name **default** to add the proxy to default group rather than completing the following steps.</span></span>  
  
4.  <span data-ttu-id="e8cd4-125">Seleccione **Personalizado** en el cuadro de selección **Editar el siguiente grupo de conexiones**.</span><span class="sxs-lookup"><span data-stu-id="e8cd4-125">Select **Custom** in the selection box **Edit the following group of connections**.</span></span>  
  
5.  <span data-ttu-id="e8cd4-126">Active la casilla correspondiente al proxy y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e8cd4-126">Check the box for your proxy and click **Ok**.</span></span>  
  
##  <a name="edit-service-application-properties"></a><a name="bkmk_editserviceapplication"></a><span data-ttu-id="e8cd4-127">Editar propiedades de la aplicación de servicio</span><span class="sxs-lookup"><span data-stu-id="e8cd4-127">Edit Service Application Properties</span></span>  
 <span data-ttu-id="e8cd4-128">Puede volver a abrir la página de propiedades de la aplicación de servicio para modificar las propiedades.</span><span class="sxs-lookup"><span data-stu-id="e8cd4-128">You can reopen the property page of the service application to modify the properties.</span></span>  
  
1.  <span data-ttu-id="e8cd4-129">En administración central de SharePoint, en el Grupo administración de aplicaciones, haga clic en **Administrar aplicaciones de servicio**.</span><span class="sxs-lookup"><span data-stu-id="e8cd4-129">In SharePoint Central Administration, in the Application Management group, click **Manage service applications**.</span></span>  
  
2.  <span data-ttu-id="e8cd4-130">Seleccione la aplicación de servicio haciendo clic en la columna de tipo para seleccionar toda la fila.</span><span class="sxs-lookup"><span data-stu-id="e8cd4-130">Select the service application by clicking the type column to select the entire row.</span></span> <span data-ttu-id="e8cd4-131">Si hace clic en el nombre de la aplicación, se abre la página de opciones de administración del servicio en lugar de las propiedades de la aplicación de servicio.</span><span class="sxs-lookup"><span data-stu-id="e8cd4-131">If you click the name of the application it, the Management options page for the service opens instead of opening the properties of the service application.</span></span>  
  
3.  <span data-ttu-id="e8cd4-132">En la cinta de opciones de Aplicaciones de servicio, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e8cd4-132">In the Service Applications ribbon, click **Properties**.</span></span>  
  
##  <a name="to-create-a-reporting-services-service-application-using-powershell"></a><a name="bkmk_powershell_create_ssrs_serviceapp"></a><span data-ttu-id="e8cd4-133">Para crear una aplicación de servicio de Reporting Services con PowerShell</span><span class="sxs-lookup"><span data-stu-id="e8cd4-133">To create a Reporting Services Service Application using PowerShell</span></span>  
 <span data-ttu-id="e8cd4-134">Puede utilizar PowerShell para crear el proxy y la aplicación de servicio.</span><span class="sxs-lookup"><span data-stu-id="e8cd4-134">You can use PowerShell to create the Service application and proxy.</span></span> <span data-ttu-id="e8cd4-135">En el ejemplo siguiente se supone que ya sabe qué grupo de aplicaciones desea configurar para usar la aplicación de servicio.</span><span class="sxs-lookup"><span data-stu-id="e8cd4-135">The sample below assumes that you know what application pool you want to configure the service application to use.</span></span>  
  
1.  <span data-ttu-id="e8cd4-136">Agregue el objeto de grupo de aplicaciones del nombre del grupo de aplicaciones a una variable que se pasa en la acción Nueva.</span><span class="sxs-lookup"><span data-stu-id="e8cd4-136">Add the application pool object of your application pool name to a variable that is passed into the New action.</span></span>  
  
    ```powershell
    $appPoolName = Get-SPServiceApplicationPool "<application pool name>"  
    ```  
  
2.  <span data-ttu-id="e8cd4-137">Crear la aplicación de servicio con un nombre y un nombre de grupo de aplicaciones que proporcione.</span><span class="sxs-lookup"><span data-stu-id="e8cd4-137">Create the service application with a name and application pool name you provide.</span></span>  
  
    ```powershell
    New-SPRSServiceApplication -Name 'MyServiceApplication' -ApplicationPool $appPoolName -DatabaseName 'MyServiceApplicationDatabase' -DatabaseServer '<Server Name>'  
    ```  
  
3.  <span data-ttu-id="e8cd4-138">Obtenga el nuevo objeto de aplicación de servicio y canalice el objeto en cmdlet para canalizar el nuevo proxy.</span><span class="sxs-lookup"><span data-stu-id="e8cd4-138">Get the new service application object, and pipe the object into the Pipe the new proxy cmdlet.</span></span>  
  
    ```powershell
    Get-SPRSServiceApplication -name MyServiceApplication | New-SPRSServiceApplicationProxy "MyServiceApplicationProxy"  
    ```  
  
##  <a name="related-tasks"></a><a name="bkmk_related"></a> <span data-ttu-id="e8cd4-139">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="e8cd4-139">Related Tasks</span></span>  
  
|<span data-ttu-id="e8cd4-140">Tarea</span><span class="sxs-lookup"><span data-stu-id="e8cd4-140">Task</span></span>|<span data-ttu-id="e8cd4-141">Vínculo</span><span class="sxs-lookup"><span data-stu-id="e8cd4-141">Link</span></span>|  
|----------|----------|  
|<span data-ttu-id="e8cd4-142">Administre la configuración de la aplicación de servicio.</span><span class="sxs-lookup"><span data-stu-id="e8cd4-142">Manage the settings of your Service Application.</span></span>|[<span data-ttu-id="e8cd4-143">Administrar una aplicación de servicio de SharePoint para Reporting Services</span><span class="sxs-lookup"><span data-stu-id="e8cd4-143">Manage a Reporting Services SharePoint Service Application</span></span>](../../2014/reporting-services/manage-a-reporting-services-sharepoint-service-application.md)|  
|<span data-ttu-id="e8cd4-144">Realizar una copia de seguridad y restauración de la aplicación de servicio y de los componentes relacionados como las claves de cifrado y el proxy.</span><span class="sxs-lookup"><span data-stu-id="e8cd4-144">Backup and restore the service application and related components such as encryption keys and proxy.</span></span>|[<span data-ttu-id="e8cd4-145">Copias de seguridad y restauración de aplicaciones de servicio de SharePoint para Reporting Services</span><span class="sxs-lookup"><span data-stu-id="e8cd4-145">Backup and Restore Reporting Services SharePoint Service Applications</span></span>](../../2014/reporting-services/backup-and-restore-reporting-services-sharepoint-service-applications.md)|  
