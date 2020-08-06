---
title: Ejemplo de configuración con privilegios mínimos para PowerPivot para SharePoint 2013 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: c1e09e6c-52d3-48ab-8c70-818d5d775087
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0188f314e4c354b33d03e6e7948aed1ba4cf8be2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744916"
---
# <a name="example-of-a-minimum-privilege-configuration-for-powerpivot-for-sharepoint-2013"></a><span data-ttu-id="bf3ab-102">Ejemplo de configuración con privilegios mínimos de PowerPivot para SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="bf3ab-102">Example of a Minimum-Privilege Configuration for PowerPivot for SharePoint 2013</span></span>
  <span data-ttu-id="bf3ab-103">En este tema se describe una configuración de ejemplo de PowerPivot para SharePoint 2013 con privilegios mínimos.</span><span class="sxs-lookup"><span data-stu-id="bf3ab-103">This topic describes an example PowerPivot for SharePoint 2013 configuration with minimum privileges.</span></span> <span data-ttu-id="bf3ab-104">La configuración emplea una cuenta diferente para cada uno de los tres componentes y cada cuenta tiene el nivel mínimo de privilegios.</span><span class="sxs-lookup"><span data-stu-id="bf3ab-104">The configuration utilizes a different account for each of the three components and each account has the minimum level of privileges.</span></span>  
  
## <a name="summary-of-accounts"></a><span data-ttu-id="bf3ab-105">Resumen de cuentas</span><span class="sxs-lookup"><span data-stu-id="bf3ab-105">Summary of Accounts</span></span>  
 <span data-ttu-id="bf3ab-106">PowerPivot para SharePoint 2013 admite el uso de la cuenta de servicio de red para la cuenta de servicio de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="bf3ab-106">PowerPivot for SharePoint 2013 supports the use of the Network Service account for the Analysis Services service account.</span></span> <span data-ttu-id="bf3ab-107">La cuenta de servicio de red no es un escenario admitido con SharePoint 2010.</span><span class="sxs-lookup"><span data-stu-id="bf3ab-107">The Network Service account is not a supported scenario with SharePoint 2010.</span></span> <span data-ttu-id="bf3ab-108">Para obtener más información sobre las cuentas de servicio, vea [configurar los permisos y las cuentas de servicio de Windows](../../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md) ( https://msdn.microsoft.com/library/ms143504.aspx) .</span><span class="sxs-lookup"><span data-stu-id="bf3ab-108">For more information on Service accounts, see [Configure Windows Service Accounts and Permissions](../../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md) (https://msdn.microsoft.com/library/ms143504.aspx).</span></span>  
  
 <span data-ttu-id="bf3ab-109">En la tabla siguiente se resumen las tres cuentas usadas en este ejemplo de configuración con privilegios mínimos.</span><span class="sxs-lookup"><span data-stu-id="bf3ab-109">The following table summarizes the three accounts used in this example of a minimum privileged configuration.</span></span>  
  
|<span data-ttu-id="bf3ab-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="bf3ab-110">Scope</span></span>|<span data-ttu-id="bf3ab-111">Nombre</span><span class="sxs-lookup"><span data-stu-id="bf3ab-111">Name</span></span>|  
|-----------|----------|  
|<span data-ttu-id="bf3ab-112">Cuenta de administrador de SharePoint</span><span class="sxs-lookup"><span data-stu-id="bf3ab-112">SharePoint Administrator account</span></span>|<span data-ttu-id="bf3ab-113">**SPAdmin**</span><span class="sxs-lookup"><span data-stu-id="bf3ab-113">**SPAdmin**</span></span>|  
|<span data-ttu-id="bf3ab-114">Cuenta de granja de SharePoint</span><span class="sxs-lookup"><span data-stu-id="bf3ab-114">SharePoint Farm account</span></span>|<span data-ttu-id="bf3ab-115">**SPFarm**</span><span class="sxs-lookup"><span data-stu-id="bf3ab-115">**SPFarm**</span></span>|  
|<span data-ttu-id="bf3ab-116">Cuenta de servicio de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="bf3ab-116">Analysis Services service account</span></span>|<span data-ttu-id="bf3ab-117">**SPsvc**</span><span class="sxs-lookup"><span data-stu-id="bf3ab-117">**SPsvc**</span></span>|  
  
### <a name="the-sharepoint-administrator-account-spadmin"></a><span data-ttu-id="bf3ab-118">La cuenta de administrador de SharePoint (SpAdmin)</span><span class="sxs-lookup"><span data-stu-id="bf3ab-118">The SharePoint Administrator account (SpAdmin)</span></span>  
 <span data-ttu-id="bf3ab-119">**SPAdmin** es una cuenta de dominio que se emplea para instalar y configurar la granja de servidores.</span><span class="sxs-lookup"><span data-stu-id="bf3ab-119">**SPAdmin** is a domain account you use to install and configure the farm.</span></span> <span data-ttu-id="bf3ab-120">Es la cuenta que se usa para ejecutar el Asistente para la configuración de SharePoint y la herramienta de configuración de PowerPivot para SharePoint 2013. la cuenta **SPAdmin** es la única cuenta que requiere derechos de administrador local.</span><span class="sxs-lookup"><span data-stu-id="bf3ab-120">It is the account used to run the SharePoint Configuration Wizard and the PowerPivot Configuration Tool for SharePoint 2013.The **SPAdmin** account is the only account that requires local Administrator rights.</span></span> <span data-ttu-id="bf3ab-121">Antes de ejecutar la herramienta de configuración de PowerPivot, conceda a la cuenta de **SPAdmin** privilegios para la SQL Server instancia de base de datos donde SharePoint crea contenido y bases de datos de configuración.</span><span class="sxs-lookup"><span data-stu-id="bf3ab-121">Before running the PowerPivot Configuration tool, grant the **SPAdmin** account privileges to the SQL Server database instance where SharePoint creates content and configuration databases.</span></span> <span data-ttu-id="bf3ab-122">Para configurar la cuenta SPAdmin en un escenario de privilegios mínimos, debe ser miembro de los roles **securityadmin** y **dbcreator**.</span><span class="sxs-lookup"><span data-stu-id="bf3ab-122">To configure the SPAdmin account in a minimum privilege scenario, it should be a member of the roles **securityadmin** and **dbcreator**.</span></span>  
  
### <a name="the-farm-account-spfarm"></a><span data-ttu-id="bf3ab-123">La cuenta de granja (SPFarm)</span><span class="sxs-lookup"><span data-stu-id="bf3ab-123">The Farm account (SPFarm)</span></span>  
 <span data-ttu-id="bf3ab-124">**SPFarm** es una cuenta de dominio que el servicio Temporizador de extensiones de SharePoint y la aplicación web de Administración central usan para acceder a la base de datos de contenido de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bf3ab-124">**SPFarm** is a domain account that the SharePoint Timer service and the web application for Central Administration use to access the SharePoint content database.</span></span> <span data-ttu-id="bf3ab-125">No es necesario que esta cuenta sea administrador local.</span><span class="sxs-lookup"><span data-stu-id="bf3ab-125">This account does not need to be a local administrator.</span></span> <span data-ttu-id="bf3ab-126">El Asistente para la configuración de SharePoint concede el privilegio mínimo adecuado en la base de datos back-end de SQL Server. La configuración de privilegios mínimos de SQL Server es la pertenencia a los roles **securityadmin** y **dbcreator**.</span><span class="sxs-lookup"><span data-stu-id="bf3ab-126">The SharePoint configuration wizard grants the proper minimal privilege in the back-end SQL Server database.The minimum SQL Server privilege configuration is membership in the roles **securityadmin** and **dbcreator**.</span></span>  
  
### <a name="the-service-account-for-powerpivot-service-spsvc"></a><span data-ttu-id="bf3ab-127">La cuenta de servicio para el servicio PowerPivot (SPsvc)</span><span class="sxs-lookup"><span data-stu-id="bf3ab-127">The Service Account for PowerPivot Service (SPsvc)</span></span>  
 <span data-ttu-id="bf3ab-128">Si no se configura una nueva granja de SharePoint antes de ejecutar la herramienta de configuración de PowerPivot, esta herramienta creará lo siguiente de forma predeterminada:</span><span class="sxs-lookup"><span data-stu-id="bf3ab-128">If a new SharePoint farm is not configured before you run the PowerPivot Configuration tool, then by default the PowerPivot Configuration tool will create the following:</span></span>  
  
-   <span data-ttu-id="bf3ab-129">Aplicación de servicio PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="bf3ab-129">PowerPivot Service application.</span></span>  
  
-   <span data-ttu-id="bf3ab-130">Aplicación de servicio de Excel.</span><span class="sxs-lookup"><span data-stu-id="bf3ab-130">Excel Services application.</span></span>  
  
-   <span data-ttu-id="bf3ab-131">Aplicación de almacenamiento seguro.</span><span class="sxs-lookup"><span data-stu-id="bf3ab-131">Secure Store application.</span></span>  
  
 <span data-ttu-id="bf3ab-132">La herramienta de configuración de PowerPivot configura las tres aplicaciones de servicio en el grupo de aplicaciones predeterminado.</span><span class="sxs-lookup"><span data-stu-id="bf3ab-132">The PowerPivot configuration tool configures all three of the service applications in the default application pool.</span></span> <span data-ttu-id="bf3ab-133">Ese grupo de aplicaciones se suele configurar para que se ejecute como la cuenta SPFarm, que tiene acceso a muchos recursos que una cuenta de servicio no necesita. Para hacer que el entorno sea un entorno con privilegios mínimos, configure una nueva cuenta de dominio para que la usen el grupo de aplicaciones y la aplicación web adecuados.</span><span class="sxs-lookup"><span data-stu-id="bf3ab-133">That application pool is typically configured to run as the SPFarm account, which has access to many resources that a service account does not require.To make the environment a minimum-privileged environment, configure a new domain account to be use by the appropriate application pool and web application.</span></span>  
  
 <span data-ttu-id="bf3ab-134">**Para crear una nueva cuenta de dominio SPsvc que se usará como cuenta de servicio de SharePoint:**</span><span class="sxs-lookup"><span data-stu-id="bf3ab-134">**To create a new domain account SPsvc to be used as a SharePoint Service account:**</span></span>  
  
1.  <span data-ttu-id="bf3ab-135">En administración central de SharePoint, haga clic en **seguridad**.</span><span class="sxs-lookup"><span data-stu-id="bf3ab-135">In SharePoint Central Administration, click **Security**.</span></span>  
  
2.  <span data-ttu-id="bf3ab-136">Haga clic en **configurar cuentas de servicio**</span><span class="sxs-lookup"><span data-stu-id="bf3ab-136">Click **Configure Service Accounts**</span></span>  
  
3.  <span data-ttu-id="bf3ab-137">Haga clic en **registrar nueva cuenta administrada**.</span><span class="sxs-lookup"><span data-stu-id="bf3ab-137">Click **Register new managed account**.</span></span>  
  
 <span data-ttu-id="bf3ab-138">La cuenta **SPSvc** no tiene privilegios de administrador local y SPsvc no tendrá ningún privilegio en la base de datos de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bf3ab-138">The **SPSvc** account has no local administrator privileges and SPsvc will not have any privileges in the SharePoint database.</span></span> <span data-ttu-id="bf3ab-139">Los únicos privilegios que SPsvc necesita son derechos administrativos en la instancia de PowerPivot de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="bf3ab-139">The only privileges SPsvc requires is administrative rights to the PowerPivot Instance of the Analysis Services.</span></span>  
  
 <span data-ttu-id="bf3ab-140">**Para configurar el grupo de aplicaciones adecuado de manera que use la cuenta SPsvc:**</span><span class="sxs-lookup"><span data-stu-id="bf3ab-140">**To configure the appropriate application pool to use the SPsvc account :**</span></span>  
  
1.  <span data-ttu-id="bf3ab-141">En administración central de SharePoint, haga clic en **seguridad**.</span><span class="sxs-lookup"><span data-stu-id="bf3ab-141">In SharePoint Central Administration, click **Security**.</span></span>  
  
2.  <span data-ttu-id="bf3ab-142">Haga clic en **configurar cuentas de servicio**.</span><span class="sxs-lookup"><span data-stu-id="bf3ab-142">Click **Configure Service Accounts**.</span></span>  
  
3.  <span data-ttu-id="bf3ab-143">Seleccione el grupo de aplicaciones de servicio usado por la aplicación de servicio PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="bf3ab-143">Select the service application pool used by the PowerPivot Service application.</span></span> <span data-ttu-id="bf3ab-144">Seleccione después la cuenta SPSvc.</span><span class="sxs-lookup"><span data-stu-id="bf3ab-144">Then select the SPSvc account.</span></span>  
  
 <span data-ttu-id="bf3ab-145">**Para conceder acceso a la aplicación web con PowerShell:**</span><span class="sxs-lookup"><span data-stu-id="bf3ab-145">**To Grant access to the web application with PowerShell:**</span></span>  
  
1.  <span data-ttu-id="bf3ab-146">Ejecute el shell de administración de SharePoint 2013 con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="bf3ab-146">Run the SharePoint 2013 Management Shell with administrator privileges.</span></span>  
  
2.  <span data-ttu-id="bf3ab-147">Ejecute el siguiente código de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bf3ab-147">Run the following PowerShell code:</span></span>  
  
    ```powershell
    $webApp = Get-SPWebApplication "http://<servername>"  
    $webApp.GrantAccessToProcessIdentity("DOMAIN\<ServiceAccountName>")
    ```  
