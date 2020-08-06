---
title: Aprovisionar suscripciones y alertas para aplicaciones de servicio SSRS | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services Shared Service
- SharePoint Mode [Reporting Services]
- SharePoint Mode
- Reporting Services Service Application
- SSRS service application
ms.assetid: d0de3f1f-4887-47fb-bacf-46aaad74c4be
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9c09033b6a31295b8fbe42058cba9059f5d05629
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751838"
---
# <a name="provision-subscriptions-and-alerts-for-ssrs-service-applications"></a><span data-ttu-id="e0522-102">Aprovisionar Subscripciones y alertas para aplicaciones de servicio SSRS</span><span class="sxs-lookup"><span data-stu-id="e0522-102">Provision Subscriptions and Alerts for SSRS Service Applications</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="e0522-103">requieren el Agente SQL Server y la configuración de permisos del mismo.</span><span class="sxs-lookup"><span data-stu-id="e0522-103">subscriptions and data alerts require SQL Server Agent and require the configuration of permissions for SQL Server Agent.</span></span> <span data-ttu-id="e0522-104">Si ve mensajes de error que indican que se requiere el Agente SQL Server y ha comprobado que se está ejecutando, actualice o compruebe los permisos.</span><span class="sxs-lookup"><span data-stu-id="e0522-104">If you see error messages that indicate SQL Server Agent is required and you have verified SQL Server Agent is running, then update or verify permissions.</span></span> <span data-ttu-id="e0522-105">El ámbito de este tema es [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en modo de SharePoint y en él se describen tres formas de actualizar los permisos del Agente SQL Server con suscripciones de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e0522-105">The scope of this topic is [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in SharePoint mode and the topic describes three ways you can update the permissions of SQL Server Agent with [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] subscriptions.</span></span> <span data-ttu-id="e0522-106">Las credenciales que use para los pasos de este tema deben disponer de los permisos adecuados para conceder permisos de ejecución a RSExecRole para los objetos de la aplicación de servicio, msdb y las bases de datos maestras.</span><span class="sxs-lookup"><span data-stu-id="e0522-106">The credentials you use for the steps in this topic need to have sufficient permissions to grant execute permissions to the RSExecRole for objects in the service application, msdb, and master databases.</span></span>

||
|-|
|<span data-ttu-id="e0522-107">**[!INCLUDE[applies](../../includes/applies-md.md)]** SharePoint 2013 &#124; SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="e0522-107">**[!INCLUDE[applies](../../includes/applies-md.md)]**  SharePoint 2013 &#124; SharePoint 2010</span></span>|

 <span data-ttu-id="e0522-108">![Permisos de Agente SQL para bases de datos de aplicación de servicio](../../../2014/sql-server/install/media/rs-provisionsqlagent.gif "Permisos de Agente SQL para bases de datos de aplicación de servicio")</span><span class="sxs-lookup"><span data-stu-id="e0522-108">![SQL Agent permissions to Service Application DBs](../../../2014/sql-server/install/media/rs-provisionsqlagent.gif "SQL Agent permissions to Service Application DBs")</span></span>

||<span data-ttu-id="e0522-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="e0522-109">Description</span></span>|
|------|-----------------|
|<span data-ttu-id="e0522-110">**1**</span><span class="sxs-lookup"><span data-stu-id="e0522-110">**1**</span></span>|<span data-ttu-id="e0522-111">Instancia del Motor de base de datos de SQL Server que hospeda las bases de datos de aplicación de servicio de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="e0522-111">The instance of SQL Server Database engine that is hosting the Reporting Services service application databases.</span></span>|
|<span data-ttu-id="e0522-112">**2**</span><span class="sxs-lookup"><span data-stu-id="e0522-112">**2**</span></span>|<span data-ttu-id="e0522-113">Instancia del agente SQL Server para la instancia del motor de base de datos SQL.</span><span class="sxs-lookup"><span data-stu-id="e0522-113">The instance of SQL Server agent for the instance of the SQL database engine.</span></span>|
|<span data-ttu-id="e0522-114">**3**</span><span class="sxs-lookup"><span data-stu-id="e0522-114">**3**</span></span>|<span data-ttu-id="e0522-115">Bases de datos de aplicación de servicio de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="e0522-115">The Reporting Services service application databases.</span></span> <span data-ttu-id="e0522-116">Los nombres se basan en la información utilizada para crear la aplicación de servicio.</span><span class="sxs-lookup"><span data-stu-id="e0522-116">The names are based on the information used for creating the service application.</span></span> <span data-ttu-id="e0522-117">A continuación se muestran los nombres de la base de datos de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e0522-117">The following are example database names:</span></span><br /><br /> <span data-ttu-id="e0522-118">ReportingService_2fbae157295d49df86d0b85760c704b0</span><span class="sxs-lookup"><span data-stu-id="e0522-118">ReportingService_2fbae157295d49df86d0b85760c704b0</span></span><br /><br /> <span data-ttu-id="e0522-119">ReportingService_2fbae157295d49df86d0b85760c704b0_Alerting</span><span class="sxs-lookup"><span data-stu-id="e0522-119">ReportingService_2fbae157295d49df86d0b85760c704b0_Alerting</span></span><br /><br /> <span data-ttu-id="e0522-120">ReportingService_2fbae157295d49df86d0b85760c704b0TempDB</span><span class="sxs-lookup"><span data-stu-id="e0522-120">ReportingService_2fbae157295d49df86d0b85760c704b0TempDB</span></span>|
|<span data-ttu-id="e0522-121">**4**</span><span class="sxs-lookup"><span data-stu-id="e0522-121">**4**</span></span>|<span data-ttu-id="e0522-122">Base de datos maestra y de MSDB de la instancia del motor de base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e0522-122">The master and MSDB database of the instance of the SQL Server Database engine.</span></span>|

 <span data-ttu-id="e0522-123">Use uno de los tres métodos siguientes para actualizar los permisos:</span><span class="sxs-lookup"><span data-stu-id="e0522-123">Use one the following three methods to update the permissions:</span></span>

1.  <span data-ttu-id="e0522-124">En la página **Provisiones y Suscripciones y alertas** , escriba las credenciales y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e0522-124">From the **Provisions and Subscriptions and Alerts** page, type credentials and click **ok**.</span></span>

2.  <span data-ttu-id="e0522-125">En la página Provisiones, suscripciones y alertas, haga clic en el botón **Descargar script** para descargar un script Transact-SQL que se puede usar para configurar los permisos.</span><span class="sxs-lookup"><span data-stu-id="e0522-125">From the Provisions and Subscriptions and Alerts page, click the **Download Script** button to download a transact SQL script that can be used to configure permissions.</span></span>

3.  <span data-ttu-id="e0522-126">Ejecute un cmdlet de PowerShell para compilar un script Transact-SQL que se pueda utilizar para configurar los permisos.</span><span class="sxs-lookup"><span data-stu-id="e0522-126">Run a PowerShell cmdlet to build a transact SQL script that can be used to configure permissions.</span></span>

### <a name="to-update-permissions-using-the-provision-page"></a><span data-ttu-id="e0522-127">Para actualizar los permisos mediante la página de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="e0522-127">To update permissions using the provision page</span></span>

1.  <span data-ttu-id="e0522-128">En Administración central de SharePoint, en el grupo **Administración de aplicaciones** , haga clic en **Administrar aplicaciones de servicio**.</span><span class="sxs-lookup"><span data-stu-id="e0522-128">From SharePoint Central Administration, in the **Application Management** group click **Manage Service Applications**</span></span>

2.  <span data-ttu-id="e0522-129">Busque su aplicación de servicio en la lista y haga clic en el nombre de la aplicación o haga clic en la columna **Tipo** para seleccionar la aplicación de servicio y haga clic en el botón **Administrar** en la cinta de opciones de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e0522-129">Find your service application in the list and click the name of the application or click the **Type** column to select the services application and click the **Manage** button in the SharePoint ribbon.</span></span>

3.  <span data-ttu-id="e0522-130">En la página **Administrar la aplicación de Reporting Services** , haga clic en **Aprovisionar suscripciones y alertas**.</span><span class="sxs-lookup"><span data-stu-id="e0522-130">On the **Manage Reporting Services Application** page, click **Provision Subscriptions and Alerts**.</span></span>

4.  <span data-ttu-id="e0522-131">Si el administrador de SharePoint tiene privilegios suficientes para la base de datos maestra y las bases de datos de aplicación de servicio, escriba esas credenciales.</span><span class="sxs-lookup"><span data-stu-id="e0522-131">If the SharePoint administrator has enough privileges to the Master database and the service application databases, type those credentials.</span></span>

5.  <span data-ttu-id="e0522-132">Haga clic en el botón **Aceptar** .</span><span class="sxs-lookup"><span data-stu-id="e0522-132">Click the **OK** button.</span></span>

##  <a name="to-download-the-transact-sql-script"></a><a name="bkmk_download"></a> <span data-ttu-id="e0522-133">Para descargar el script Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e0522-133">To download the Transact-SQL Script</span></span>

1.  <span data-ttu-id="e0522-134">En Administración central de SharePoint, en el grupo **Administración de aplicaciones** , haga clic en **Administrar aplicaciones de servicio**.</span><span class="sxs-lookup"><span data-stu-id="e0522-134">From SharePoint Central Administration, in the **Application Management** group click **Manage Service Applications**</span></span>

2.  <span data-ttu-id="e0522-135">Busque su aplicación de servicio en la lista y haga clic en el nombre de la aplicación o haga clic en la columna **Tipo** para seleccionar la aplicación de servicio y haga clic en el botón **Administrar** en la cinta de opciones de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e0522-135">Find your service application in the list and click the name of the application or click the **Type** column to select the services application and click the **Manage** button in the SharePoint ribbon.</span></span>

3.  <span data-ttu-id="e0522-136">En la página **Administrar la aplicación de Reporting Services** , haga clic en **Aprovisionar suscripciones y alertas**.</span><span class="sxs-lookup"><span data-stu-id="e0522-136">On the **Manage Reporting Services Application** page, click **Provision Subscriptions and Alerts**.</span></span>

4.  <span data-ttu-id="e0522-137">En el área **Ver estado** , compruebe que el Agente SQL Server se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="e0522-137">In the **View Status** area, verify SQL Server Agent is running.</span></span>

5.  <span data-ttu-id="e0522-138">Haga clic en **Descargar script** para descargar un script de Transact-SQL que puede ejecutar SQL Server Management Studio para conceder los permisos.</span><span class="sxs-lookup"><span data-stu-id="e0522-138">Click **Download Script** to download a transact SQL script you can run in SQL Server Management studio to grant permissions.</span></span> <span data-ttu-id="e0522-139">El nombre del archivo de script que se cree contendrá el nombre de su nombre de aplicación de servicio de Reporting Services, por ejemplo, **[nombre de la aplicación de servicio] -GrantRights.sql**.</span><span class="sxs-lookup"><span data-stu-id="e0522-139">The script file name that is created will contain the name of your Reporting Services service application name, for example **[name of the service application]-GrantRights.sql**.</span></span>

### <a name="to-generate-the-transact-sql-statement-with-powershell"></a><span data-ttu-id="e0522-140">Para generar la instrucción Transact-SQL con PowerShell</span><span class="sxs-lookup"><span data-stu-id="e0522-140">To generate the Transact-SQL statement with PowerShell</span></span>

1.  <span data-ttu-id="e0522-141">También puede utilizar un cmdlet de Windows PowerShel en el SharePoint 2010 Management Shell para crear el script Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="e0522-141">You can also use a Windows PowerShell cmdlet in the SharePoint 2010 Management Shell to create the Transact-SQL script.</span></span>

2.  <span data-ttu-id="e0522-142">En el menú **Iniciar** , haga clic en **Todos los programas**.</span><span class="sxs-lookup"><span data-stu-id="e0522-142">On the **Start** menu, click **All Programs**.</span></span>

3.  <span data-ttu-id="e0522-143">Expanda **Productos Microsoft SharePoint 2010** y haga clic en **SharePoint 2010 Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e0522-143">Expand **Microsoft SharePoint 2010 Products** and click **SharePoint 2010 Management Shell**.</span></span>

4.  <span data-ttu-id="e0522-144">Actualice el siguiente cmdlet de PowerShell reemplazando el nombre de la base de datos del servidor de informes, la cuenta del grupo de aplicaciones y la ruta de acceso de la instrucción.</span><span class="sxs-lookup"><span data-stu-id="e0522-144">Update the following PowerShell cmdlet by replacing the name of the report server database, application pool account, and the path of the statement.</span></span>

     <span data-ttu-id="e0522-145">**Sintaxis de cmdlet:** `Get-SPRSDatabaseRightsScript -DatabaseName <ReportingServices database name> -UserName <app pool account> -IsWindowsUser | Out-File <path of statement>`</span><span class="sxs-lookup"><span data-stu-id="e0522-145">**Syntax of cmdlet:** `Get-SPRSDatabaseRightsScript -DatabaseName <ReportingServices database name> -UserName <app pool account> -IsWindowsUser | Out-File <path of statement>`</span></span>

     <span data-ttu-id="e0522-146">**Cmdlet de ejemplo:** `Get-SPRSDatabaseRightsScript -DatabaseName ReportingService_46fd00359f894b828907b254e3f6257c -UserName "NT AUTHORITY\NETWORK SERVICE" -IsWindowsUser | Out-File c:\SQLServerAgentrights.sql`</span><span class="sxs-lookup"><span data-stu-id="e0522-146">**Sample cmdlet:** `Get-SPRSDatabaseRightsScript -DatabaseName ReportingService_46fd00359f894b828907b254e3f6257c -UserName "NT AUTHORITY\NETWORK SERVICE" -IsWindowsUser | Out-File c:\SQLServerAgentrights.sql`</span></span>

## <a name="using-the-transact-sql-script"></a><span data-ttu-id="e0522-147">Usar el script Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e0522-147">Using the Transact-SQL Script</span></span>
 <span data-ttu-id="e0522-148">Los siguientes procedimientos se pueden utilizar con los scripts descargados de la página de provisiones o con los scripts creados con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e0522-148">The following procedures can be used with scripts download from the provisions page or scripts created using PowerShell.</span></span>

#### <a name="to-load-the-transact-sql-script-in-sql-server-management-studio"></a><span data-ttu-id="e0522-149">Para cargar el script Transact-SQL en SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e0522-149">To load the Transact-SQL script in SQL Server Management Studio</span></span>

1.  <span data-ttu-id="e0522-150">Para abrir SQL Server Management Studio, en el menú **Inicio** , haga clic en **Microsoft SQL Server 2012** y haga clic en **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="e0522-150">To open SQL Server Management Studio, on the **Start** menu, click **Microsoft SQL Server 2012** and click **SQL Server Management Studio**.</span></span>

2.  <span data-ttu-id="e0522-151">En el cuadro de diálogo **Conectar con el servidor** establezca las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="e0522-151">In the **Connect to Server** dialog box set the following options:</span></span>

    -   <span data-ttu-id="e0522-152">En la lista **Tipo de servidor** , seleccione **Motor de base de datos**.</span><span class="sxs-lookup"><span data-stu-id="e0522-152">In the **Server type** list, select **Database Engine**</span></span>

    -   <span data-ttu-id="e0522-153">En **Nombre del servidor**, escriba el nombre de la instancia de SQL Server en la que desea configurar el Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e0522-153">In **Server Name**, type the name of the SQL Server instance on which you want to configure SQL Server Agent.</span></span>

    -   <span data-ttu-id="e0522-154">Seleccione un modo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="e0522-154">Select an authentication mode.</span></span>

    -   <span data-ttu-id="e0522-155">Si se conecta con la Autenticación de SQL Server, proporcione un inicio de sesión y una contraseña.</span><span class="sxs-lookup"><span data-stu-id="e0522-155">If connecting using SQL Server Authentication, provide a login and password.</span></span>

3.  <span data-ttu-id="e0522-156">Haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="e0522-156">Click **Connect**.</span></span>

#### <a name="to-run-the-transact-sql-statement"></a><span data-ttu-id="e0522-157">Para ejecutar la instrucción Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e0522-157">To run the Transact-SQL statement</span></span>

1.  <span data-ttu-id="e0522-158">En la barra de herramientas de SQL Server Management Studio, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="e0522-158">On the toolbar of SQL Server Management Studio, click **New Query**.</span></span>

2.  <span data-ttu-id="e0522-159">En el menú **Archivo** , haga clic en **Abrir**y, a continuación, en **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="e0522-159">On the **File** menu, click **Open**, and then click **File**.</span></span>

3.  <span data-ttu-id="e0522-160">Navegue a la carpeta donde guardó la instrucción Transact-SQL que generó en SharePoint 2010 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e0522-160">Navigate to the folder where you saved the Transact-SQL statement that you generated in SharePoint 2010 Management Shell.</span></span>

4.  <span data-ttu-id="e0522-161">Haga clic en el archivo y, a continuación, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="e0522-161">Click the file and then click **Open**.</span></span>

     <span data-ttu-id="e0522-162">La instrucción se agrega a la ventana de consulta.</span><span class="sxs-lookup"><span data-stu-id="e0522-162">The statement is added to the query window.</span></span>

5.  <span data-ttu-id="e0522-163">Haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="e0522-163">Click **Execute**.</span></span>


