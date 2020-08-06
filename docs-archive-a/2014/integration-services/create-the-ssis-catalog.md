---
title: Crear el catálogo de SSIS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 6ed56d36-18d9-40c2-b51f-f2a4c71d1e73
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2572cc131f34a21171054a159e3b7968c453a780
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669778"
---
# <a name="create-the-ssis-catalog"></a><span data-ttu-id="df06e-102">Crear el catálogo de SSIS</span><span class="sxs-lookup"><span data-stu-id="df06e-102">Create the SSIS Catalog</span></span>
  <span data-ttu-id="df06e-103">Después de diseñar y probar paquetes en [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], puede implementar los proyectos que contienen los paquetes en un servidor de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="df06e-103">After you design and test packages in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], you can deploy the projects that contain the packages to an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="df06e-104">Para poder implementar los proyectos en el servidor de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], el servidor debe contener el catálogo de `SSISDB`.</span><span class="sxs-lookup"><span data-stu-id="df06e-104">Before you can deploy the projects to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server, the server must contain the `SSISDB` catalog.</span></span> <span data-ttu-id="df06e-105">El programa de instalación de [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] no crea automáticamente el catálogo; es necesario crear manualmente el catálogo usando las instrucciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="df06e-105">The installation program for [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] does not automatically create the catalog; you need to manually create the catalog by using the following instructions.</span></span>  
  
 <span data-ttu-id="df06e-106">Puede crear el catálogo de SSISDB en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df06e-106">You can create the SSISDB catalog in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="df06e-107">También crea el catálogo mediante programación con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="df06e-107">You also create the catalog programmatically by using Windows PowerShell.</span></span>  
  
### <a name="to-create-the-ssisdb-catalog-in-sql-server-management-studio"></a><span data-ttu-id="df06e-108">Para crear un catálogo de SSISDB en SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="df06e-108">To create the SSISDB catalog in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="df06e-109">Abra [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df06e-109">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="df06e-110">Conéctese al motor de base de datos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="df06e-110">Connect to the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Database Engine.</span></span>  
  
3.  <span data-ttu-id="df06e-111">En el Explorador de objetos, expanda el nodo del servidor, haga clic con el botón derecho en el nodo **Catálogos de Integration Services** y, después, haga clic en **Crear catálogo**.</span><span class="sxs-lookup"><span data-stu-id="df06e-111">In Object Explorer, expand the server node, right-click the **Integration Services Catalogs** node, and then click **Create Catalog**.</span></span>  
  
4.  <span data-ttu-id="df06e-112">Haga clic en **Habilitar integración con CLR**.</span><span class="sxs-lookup"><span data-stu-id="df06e-112">Click **Enable CLR Integration**.</span></span>  
  
     <span data-ttu-id="df06e-113">El catálogo usar los procedimientos almacenados de CLR.</span><span class="sxs-lookup"><span data-stu-id="df06e-113">The catalog uses CLR stored procedures.</span></span>  
  
5.  <span data-ttu-id="df06e-114">Haga clic en **Habilitar la ejecución automática del procedimiento almacenado de Integration Services al iniciar SQL Server** para permitir que el procedimiento almacenado [catalog.startup](/sql/integration-services/system-stored-procedures/catalog-startup) se ejecute cada vez que se reinicie la instancia del servidor de [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="df06e-114">Click **Enable automatic execution of Integration Services stored procedure at SQL Server startup** to enable the [catalog.startup](/sql/integration-services/system-stored-procedures/catalog-startup) stored procedure to run each time the [!INCLUDE[ssIS](../includes/ssis-md.md)] server instance is restarted.</span></span>  
  
     <span data-ttu-id="df06e-115">El procedimiento almacenado realiza el mantenimiento del estado de las operaciones del catálogo de SSISDB.</span><span class="sxs-lookup"><span data-stu-id="df06e-115">The stored procedure performs maintenance of the state of operations for the SSISDB catalog.</span></span> <span data-ttu-id="df06e-116">Corrige el estado de los paquetes que estaban en ejecución si y cuando la instancia del servidor de [!INCLUDE[ssIS](../includes/ssis-md.md)] se bloquea.</span><span class="sxs-lookup"><span data-stu-id="df06e-116">It fixes the status of any packages there were running if and when the [!INCLUDE[ssIS](../includes/ssis-md.md)] server instance goes down.</span></span>  
  
6.  <span data-ttu-id="df06e-117">Escriba una contraseña y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="df06e-117">Enter a password, and then click **Ok**.</span></span>  
  
     <span data-ttu-id="df06e-118">La contraseña protege la clave maestra de la base de datos que se usar para cifrar los datos del catálogo.</span><span class="sxs-lookup"><span data-stu-id="df06e-118">The password protects the database master key that is used for encrypting the catalog data.</span></span> <span data-ttu-id="df06e-119">Guarde la contraseña en un lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="df06e-119">Save the password in a secure location.</span></span> <span data-ttu-id="df06e-120">Se recomienda que haga también una copia de seguridad de la clave maestra de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="df06e-120">It is recommended that you also back up the database master key.</span></span> <span data-ttu-id="df06e-121">Para más información, consulte [Back Up a Database Master Key](../relational-databases/security/encryption/back-up-a-database-master-key.md).</span><span class="sxs-lookup"><span data-stu-id="df06e-121">For more information, see [Back Up a Database Master Key](../relational-databases/security/encryption/back-up-a-database-master-key.md).</span></span>  
  
### <a name="to-create-the-ssisdb-catalog-programmatically"></a><span data-ttu-id="df06e-122">Para crear el catálogo de SSISDB mediante programación</span><span class="sxs-lookup"><span data-stu-id="df06e-122">To create the SSISDB catalog programmatically</span></span>  
  
1.  <span data-ttu-id="df06e-123">Ejecute el siguiente script de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="df06e-123">Execute the following PowerShell script:</span></span>  
  
    ```powershell
    # Load the IntegrationServices Assembly  
    [Reflection.Assembly]::LoadWithPartialName("Microsoft.SqlServer.Management.IntegrationServices")  
  
    # Store the IntegrationServices Assembly namespace to avoid typing it every time  
    $ISNamespace = "Microsoft.SqlServer.Management.IntegrationServices"  
  
    Write-Host "Connecting to server ..."  
  
    # Create a connection to the server  
    $sqlConnectionString = "Data Source=localhost;Initial Catalog=master;Integrated Security=SSPI;"  
    $sqlConnection = New-Object System.Data.SqlClient.SqlConnection $sqlConnectionString  
  
    # Create the Integration Services object  
    $integrationServices = New-Object $ISNamespace".IntegrationServices" $sqlConnection  
  
    # Provision a new SSIS Catalog  
    $catalog = New-Object $ISNamespace".Catalog" ($integrationServices, "SSISDB", "P@assword1")  
    $catalog.Create()
    ```  
  
     <span data-ttu-id="df06e-124">Para obtener más ejemplos de cómo usar Windows PowerShell y el espacio de nombres <xref:Microsoft.SqlServer.Management.IntegrationServices>, vea la entrada del blog [SSIS and PowerShell in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=242539) (SSIS y PowerShell en SQL Server 2012), en blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="df06e-124">For more examples of how to use Windows PowerShell and the <xref:Microsoft.SqlServer.Management.IntegrationServices> namespace, see the blog entry, [SSIS and PowerShell in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=242539), on blogs.msdn.com.</span></span> <span data-ttu-id="df06e-125">Para obtener información general sobre el espacio de nombres y ejemplos de código, vea la entrada del blog sobre el [Modelo de objetos administrados del catálogo de SSIS](https://techcommunity.microsoft.com/t5/sql-server-integration-services/a-glimpse-of-the-ssis-catalog-managed-object-model/ba-p/387892)en blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="df06e-125">For an overview of the namespace and code examples, see the blog entry, [A Glimpse of the SSIS Catalog Managed Object Model](https://techcommunity.microsoft.com/t5/sql-server-integration-services/a-glimpse-of-the-ssis-catalog-managed-object-model/ba-p/387892), on blogs.msdn.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df06e-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="df06e-126">See Also</span></span>  
 <span data-ttu-id="df06e-127">[Catálogo de SSIS](catalog/ssis-catalog.md) </span><span class="sxs-lookup"><span data-stu-id="df06e-127">[SSIS Catalog](catalog/ssis-catalog.md) </span></span>  
 [<span data-ttu-id="df06e-128">Copia de seguridad, restauración y traslado del catálogo de SSIS</span><span class="sxs-lookup"><span data-stu-id="df06e-128">Backup, Restore, and Move the SSIS Catalog</span></span>](../../2014/integration-services/backup-restore-and-move-the-ssis-catalog.md)  
