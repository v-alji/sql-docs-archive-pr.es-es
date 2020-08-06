---
title: Ver y detener los paquetes que se ejecutan en el servidor de Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- packages [Integration Services], managing
- managing running packages [Integration Services]
- packages [Integration Services], running
- running package [Integration Services], managing
ms.assetid: 11bf44e6-f6b0-475f-b816-40e914dbac80
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6e63839d4ab5d8d50f7d86eea05c8d58107d6799
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676562"
---
# <a name="viewing-and-stopping-packages-running-on-the-integration-services-server"></a><span data-ttu-id="6030a-102">Ver y detener los paquetes en ejecución en el Servidor de Integration Services</span><span class="sxs-lookup"><span data-stu-id="6030a-102">Viewing and Stopping Packages Running on the Integration Services Server</span></span>
  <span data-ttu-id="6030a-103">La base de datos de `SSISDB` almacena el historial de ejecuciones en tablas internas que no son visibles para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="6030a-103">The `SSISDB` database stores execution history in internal tables that are not visible to users.</span></span> <span data-ttu-id="6030a-104">Sin embargo, expone la información que necesita a través de vistas públicas que puede consultar.</span><span class="sxs-lookup"><span data-stu-id="6030a-104">However it exposes the information that you need through public views that you can query.</span></span> <span data-ttu-id="6030a-105">También proporciona procedimientos almacenados a los que puede llamar para realizar tareas frecuentes relacionadas con los paquetes.</span><span class="sxs-lookup"><span data-stu-id="6030a-105">It also provides stored procedures that you can call to perform common tasks related to packages.</span></span>  
  
 <span data-ttu-id="6030a-106">Normalmente, administra los objetos de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] del servidor en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6030a-106">Typically you manage [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] objects on the server in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="6030a-107">Sin embargo, también puede consultar las vistas de base de datos y llamar a los procedimientos almacenados directamente, o escribir código personalizado que llame a la API administrada.</span><span class="sxs-lookup"><span data-stu-id="6030a-107">However you can also query the database views and call the stored procedures directly, or write custom code that calls the managed API.</span></span> [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="6030a-108">y la API administrada consultan las vistas y llaman a los procedimientos almacenados para realizar muchas de sus tareas.</span><span class="sxs-lookup"><span data-stu-id="6030a-108">and the managed API query the views and call the stored procedures to perform many of their tasks.</span></span> <span data-ttu-id="6030a-109">Por ejemplo, puede ver la lista de paquetes de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que se están ejecutando actualmente en el servidor y solicitar que se detengan si es necesario.</span><span class="sxs-lookup"><span data-stu-id="6030a-109">For example, you can view the list of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages that are currently running on the server, and request packages to stop if you have to.</span></span>  
  
## <a name="viewing-the-list-of-running-packages"></a><span data-ttu-id="6030a-110">Ver la lista de paquetes en ejecución</span><span class="sxs-lookup"><span data-stu-id="6030a-110">Viewing the List of Running Packages</span></span>  
 <span data-ttu-id="6030a-111">Puede ver la lista de paquetes que hay en ejecución actualmente en el servidor en el cuadro de diálogo **Operaciones activas** .</span><span class="sxs-lookup"><span data-stu-id="6030a-111">You can view the list of packages that are currently running on the server in the **Active Operations** dialog box.</span></span> <span data-ttu-id="6030a-112">Para más información, consulte [Active Operations Dialog Box](../../2014/integration-services/active-operations-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="6030a-112">For more information, see [Active Operations Dialog Box](../../2014/integration-services/active-operations-dialog-box.md).</span></span>  
  
 <span data-ttu-id="6030a-113">Para obtener información sobre los demás métodos que puede usar para ver la lista de paquetes en ejecución, vea los siguientes temas.</span><span class="sxs-lookup"><span data-stu-id="6030a-113">For information about the other methods that you can use to view the list of running packages, see the following topics.</span></span>  
  
 [!INCLUDE[tsql](../includes/tsql-md.md)] <span data-ttu-id="6030a-114">access</span><span class="sxs-lookup"><span data-stu-id="6030a-114">access</span></span>  
 <span data-ttu-id="6030a-115">Para ver la lista de los paquetes que se están ejecutando en el servidor, consulte la vista [catalog.executions &#40;base de datos de SSISDB&#41;](/sql/integration-services/system-views/catalog-executions-ssisdb-database) para los paquetes que tengan un estado de 2.</span><span class="sxs-lookup"><span data-stu-id="6030a-115">To view the list of packages that are running on the server, query the view, [catalog.executions &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-executions-ssisdb-database) for packages that have a status of 2.</span></span>  
  
 <span data-ttu-id="6030a-116">Acceso mediante programación a través de la API administrada</span><span class="sxs-lookup"><span data-stu-id="6030a-116">Programmatic access through the managed API</span></span>  
 <span data-ttu-id="6030a-117">Vea el espacio de nombres <xref:Microsoft.SqlServer.Management.IntegrationServices> y sus clases.</span><span class="sxs-lookup"><span data-stu-id="6030a-117">See the <xref:Microsoft.SqlServer.Management.IntegrationServices> namespace and its classes.</span></span>  
  
## <a name="stopping-a-running-package"></a><span data-ttu-id="6030a-118">Detener un paquete en ejecución</span><span class="sxs-lookup"><span data-stu-id="6030a-118">Stopping a Running Package</span></span>  
 <span data-ttu-id="6030a-119">En el cuadro de diálogo **Operaciones activas** , puede solicitar que se detenga un paquete en ejecución.</span><span class="sxs-lookup"><span data-stu-id="6030a-119">You can request a running package to stop in the **Active Operations** dialog box.</span></span> <span data-ttu-id="6030a-120">Para más información, consulte [Active Operations Dialog Box](../../2014/integration-services/active-operations-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="6030a-120">For more information, see [Active Operations Dialog Box](../../2014/integration-services/active-operations-dialog-box.md).</span></span>  
  
 <span data-ttu-id="6030a-121">Para obtener información acerca de los otros métodos que puede usar para detener un paquete en ejecución, vea los temas siguientes.</span><span class="sxs-lookup"><span data-stu-id="6030a-121">For information about the other methods that you can use to stop a running package, see the following topics.</span></span>  
  
 [!INCLUDE[tsql](../includes/tsql-md.md)] <span data-ttu-id="6030a-122">access</span><span class="sxs-lookup"><span data-stu-id="6030a-122">access</span></span>  
 <span data-ttu-id="6030a-123">Para detener un paquete en ejecución en el servidor, llame al procedimiento almacenado [catalog.stop_operation &#40;base de datos de SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-stop-operation-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="6030a-123">To stop a package that is running on the server, call the stored procedure, [catalog.stop_operation &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-stop-operation-ssisdb-database).</span></span>  
  
 <span data-ttu-id="6030a-124">Acceso mediante programación a través de la API administrada</span><span class="sxs-lookup"><span data-stu-id="6030a-124">Programmatic access through the managed API</span></span>  
 <span data-ttu-id="6030a-125">Vea el espacio de nombres <xref:Microsoft.SqlServer.Management.IntegrationServices> y sus clases.</span><span class="sxs-lookup"><span data-stu-id="6030a-125">See the <xref:Microsoft.SqlServer.Management.IntegrationServices> namespace and its classes.</span></span>  
  
## <a name="viewing-the-history-of-packages-that-have-run"></a><span data-ttu-id="6030a-126">Ver el historial de paquetes ejecutados</span><span class="sxs-lookup"><span data-stu-id="6030a-126">Viewing the History of Packages That Have Run</span></span>  
 <span data-ttu-id="6030a-127">Para ver el historial de los paquetes que se han ejecutado en [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], use el informe **Todas las ejecuciones** .</span><span class="sxs-lookup"><span data-stu-id="6030a-127">To view the history of packages that have run in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], use the **All Executions** report.</span></span> <span data-ttu-id="6030a-128">Para obtener más información sobre el informe **Todas las ejecuciones** y otros informes estándar, vea [Informes para el servidor de Integration Services](../../2014/integration-services/reports-for-the-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="6030a-128">For more information on the **All Executions** report and other standard reports, see [Reports for the Integration Services Server](../../2014/integration-services/reports-for-the-integration-services-server.md).</span></span>  
  
 <span data-ttu-id="6030a-129">Para obtener información acerca de los demás métodos que puede usar para ver el historial de paquetes en ejecución, vea los siguientes temas.</span><span class="sxs-lookup"><span data-stu-id="6030a-129">For information about the other methods that you can use to view the history of running packages, see the following topics.</span></span>  
  
 [!INCLUDE[tsql](../includes/tsql-md.md)] <span data-ttu-id="6030a-130">access</span><span class="sxs-lookup"><span data-stu-id="6030a-130">access</span></span>  
 <span data-ttu-id="6030a-131">Para ver información sobre los paquetes que se han ejecutado, consulte la vista [catalog.executions &#40;base de datos de SSISDB&#41;](/sql/integration-services/system-views/catalog-executions-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="6030a-131">To view information about packages that have run, query the view, [catalog.executions &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-executions-ssisdb-database).</span></span>  
  
 <span data-ttu-id="6030a-132">Acceso mediante programación a través de la API administrada</span><span class="sxs-lookup"><span data-stu-id="6030a-132">Programmatic access through the managed API</span></span>  
 <span data-ttu-id="6030a-133">Vea el espacio de nombres <xref:Microsoft.SqlServer.Management.IntegrationServices> y sus clases.</span><span class="sxs-lookup"><span data-stu-id="6030a-133">See the <xref:Microsoft.SqlServer.Management.IntegrationServices> namespace and its classes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6030a-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6030a-134">See Also</span></span>  
 <span data-ttu-id="6030a-135">[Execution of Projects and Packages](packages/run-integration-services-ssis-packages.md)  (Ejecución de proyectos y paquetes)</span><span class="sxs-lookup"><span data-stu-id="6030a-135">[Execution of Projects and Packages](packages/run-integration-services-ssis-packages.md) </span></span>  
 [<span data-ttu-id="6030a-136">Solucionar problemas de informes para la ejecución de paquetes</span><span class="sxs-lookup"><span data-stu-id="6030a-136">Troubleshooting Reports for Package Execution</span></span>](troubleshooting/troubleshooting-reports-for-package-execution.md)  
  
  
