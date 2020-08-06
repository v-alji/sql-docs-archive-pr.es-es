---
title: Ejecutar un paquete en el servidor SSIS mediante SQL Server Management Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 56dc1bf8-99d4-41dc-bdc4-f64f1ccfd688
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d17009988dea54621d4fd7ef542cf452bfe95c6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744737"
---
# <a name="run-a-package-on-the-ssis-server-using-sql-server-management-studio"></a><span data-ttu-id="f6369-102">Ejecutar un paquete en el servidor SSIS con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f6369-102">Run a Package on the SSIS Server Using SQL Server Management Studio</span></span>
  <span data-ttu-id="f6369-103">Después de implementar el proyecto en el servidor de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , puede ejecutar el paquete en el servidor.</span><span class="sxs-lookup"><span data-stu-id="f6369-103">After you deploy your project to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server, you can run the package on the server.</span></span>  
  
 <span data-ttu-id="f6369-104">Puede utilizar los informes de operaciones para ver información sobre los paquetes que se han ejecutado, o que se están ejecutando actualmente, en el servidor.</span><span class="sxs-lookup"><span data-stu-id="f6369-104">You can use operations reports to view information about packages that have run, or are currently running, on the server.</span></span> <span data-ttu-id="f6369-105">Para obtener más información, consulte [Reports for the Integration Services Server](../../2014/integration-services/reports-for-the-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="f6369-105">For more information, see [Reports for the Integration Services Server](../../2014/integration-services/reports-for-the-integration-services-server.md).</span></span>  
  
### <a name="to-run-a-package-on-the-server-using-sql-server-management-studio"></a><span data-ttu-id="f6369-106">Para ejecutar un paquete en el servidor con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f6369-106">To run a package on the server using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="f6369-107">Abra [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] y conéctese a la instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que contiene el catálogo de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f6369-107">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and connect to the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that contains the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] catalog.</span></span>  
  
2.  <span data-ttu-id="f6369-108">En el Explorador de objetos, expanda el nodo **Catálogos de Integration Services** , expanda el nodo **SSISDB** y vaya al paquete contenido en el proyecto que ha implementado.</span><span class="sxs-lookup"><span data-stu-id="f6369-108">In Object Explorer, expand the **Integration Services Catalogs** node, expand the **SSISDB** node, and navigate to the package contained in the project you deployed.</span></span>  
  
3.  <span data-ttu-id="f6369-109">Haga clic con el botón derecho en el nombre del paquete y seleccione **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="f6369-109">Right-click the package name and select **Execute**.</span></span>  
  
4.  <span data-ttu-id="f6369-110">Configure la ejecución del paquete mediante las opciones de las pestañas **Parámetros**, **Administradores de conexión**y **Avanzadas** del cuadro de diálogo **Ejecutar paquete** .</span><span class="sxs-lookup"><span data-stu-id="f6369-110">Configure the package execution by using the settings on the **Parameters**, **Connection Managers**, and **Advanced** tabs in the **Execute Package** dialog box.</span></span>  
  
5.  <span data-ttu-id="f6369-111">Haga clic en **Aceptar** para ejecutar el paquete.</span><span class="sxs-lookup"><span data-stu-id="f6369-111">Click **OK** to run the package.</span></span>  
  
     <span data-ttu-id="f6369-112">O bien</span><span class="sxs-lookup"><span data-stu-id="f6369-112">-or-</span></span>  
  
     <span data-ttu-id="f6369-113">Utilice procedimientos almacenados para ejecutar el paquete.</span><span class="sxs-lookup"><span data-stu-id="f6369-113">Use stored procedures to run the package.</span></span> <span data-ttu-id="f6369-114">Haga clic en **Script** para generar la instrucción Transact-SQL que crea una instancia de la ejecución y la inicia.</span><span class="sxs-lookup"><span data-stu-id="f6369-114">Click **Script** to generate the Transact-SQL statement that creates an instance of the execution and starts an instance of the execution.</span></span> <span data-ttu-id="f6369-115">La instrucción incluye una llamada a los procedimientos almacenados catalog.create_execution, catalog.set_execution_parameter_value y catalog.start_execution.</span><span class="sxs-lookup"><span data-stu-id="f6369-115">The statement includes a call to the catalog.create_execution, catalog.set_execution_parameter_value, and catalog.start_execution stored procedures.</span></span> <span data-ttu-id="f6369-116">Para obtener más información sobre estos procedimientos almacenados, vea [catalog.create_execution &#40;base de datos de SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-create-execution-ssisdb-database), [catalog.set_execution_parameter_value &#40;base de datos de SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database) y [catalog.start_execution &#40;base de datos de SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="f6369-116">For more information about these stored procedures, see [catalog.create_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-create-execution-ssisdb-database), [catalog.set_execution_parameter_value &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database), and [catalog.start_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database).</span></span>  
  
  
