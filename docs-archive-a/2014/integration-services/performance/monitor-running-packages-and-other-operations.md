---
title: Supervisión de ejecuciones de paquetes y otras operaciones | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: cbbcd79f-ab9b-46ec-84cb-4821c1d16b99
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 628b62d9c8e01d0dc0bf641551de67c3838a4504
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677770"
---
# <a name="monitoring-for-package-executions-and-other-operations"></a><span data-ttu-id="c03f9-102">Supervisar las ejecuciones de paquetes y otras operaciones</span><span class="sxs-lookup"><span data-stu-id="c03f9-102">Monitoring for Package Executions and Other Operations</span></span>
  <span data-ttu-id="c03f9-103">Puede supervisar las ejecuciones de paquetes [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , validaciones de proyectos y otras operaciones mediante una o varias de las herramientas siguientes.</span><span class="sxs-lookup"><span data-stu-id="c03f9-103">You can monitor [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package executions, project validations, and other operations by using one of more of the following tools.</span></span> <span data-ttu-id="c03f9-104">Algunas herramientas como las derivaciones de datos solo están disponibles para los proyectos que se implementan en el servidor [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c03f9-104">Certain tools such as data taps are available only for projects that are deployed to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
-   <span data-ttu-id="c03f9-105">Registros</span><span class="sxs-lookup"><span data-stu-id="c03f9-105">Logs</span></span>  
  
     <span data-ttu-id="c03f9-106">Para obtener más información, vea [Registro de Integration Services &#40;SSIS&#41;](integration-services-ssis-logging.md).</span><span class="sxs-lookup"><span data-stu-id="c03f9-106">For more information, see [Integration Services &#40;SSIS&#41; Logging](integration-services-ssis-logging.md).</span></span>  
  
-   <span data-ttu-id="c03f9-107">Informes</span><span class="sxs-lookup"><span data-stu-id="c03f9-107">Reports</span></span>  
  
     <span data-ttu-id="c03f9-108">Para obtener más información, consulte [Reports for the Integration Services Server](../reports-for-the-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="c03f9-108">For more information, see [Reports for the Integration Services Server](../reports-for-the-integration-services-server.md).</span></span>  
  
-   <span data-ttu-id="c03f9-109">Vistas</span><span class="sxs-lookup"><span data-stu-id="c03f9-109">Views</span></span>  
  
     <span data-ttu-id="c03f9-110">Para obtener más información, vea [Vistas &#40;catálogo de Integration Services&#41;](/sql/integration-services/system-views/views-integration-services-catalog).</span><span class="sxs-lookup"><span data-stu-id="c03f9-110">For more information, see [Views &#40;Integration Services Catalog&#41;](/sql/integration-services/system-views/views-integration-services-catalog).</span></span>  
  
-   <span data-ttu-id="c03f9-111">Contadores de rendimiento</span><span class="sxs-lookup"><span data-stu-id="c03f9-111">Performance counters</span></span>  
  
     <span data-ttu-id="c03f9-112">Para más información, consulte [Performance Counters](performance-counters.md).</span><span class="sxs-lookup"><span data-stu-id="c03f9-112">For more information, see [Performance Counters](performance-counters.md).</span></span>  
  
-   <span data-ttu-id="c03f9-113">Derivaciones de datos</span><span class="sxs-lookup"><span data-stu-id="c03f9-113">Data taps</span></span>  
  
## <a name="operation-types"></a><span data-ttu-id="c03f9-114">Tipos de operación</span><span class="sxs-lookup"><span data-stu-id="c03f9-114">Operation Types</span></span>  
 <span data-ttu-id="c03f9-115">En el catálogo de `SSISDB` se supervisan varios tipos diferentes de operaciones, en el servidor [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c03f9-115">Several different types of operations are monitored in the `SSISDB` catalog, on the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="c03f9-116">Cada operación puede tener varios mensajes asociados.</span><span class="sxs-lookup"><span data-stu-id="c03f9-116">Each operation can have multiple messages associated with it.</span></span> <span data-ttu-id="c03f9-117">Cada mensaje se puede clasificar en uno de varios tipos.</span><span class="sxs-lookup"><span data-stu-id="c03f9-117">Each message can be classified into one of several different types.</span></span> <span data-ttu-id="c03f9-118">Por ejemplo, un mensaje puede ser de información, de advertencia o de error.</span><span class="sxs-lookup"><span data-stu-id="c03f9-118">For example, a message can be of type Information, Warning, or Error.</span></span> <span data-ttu-id="c03f9-119">Para obtener la lista completa de tipos de mensaje, vea la documentación de la vista [catalog.operation_messages &#40;base de datos de SSISDB&#41;](/sql/integration-services/system-views/catalog-operation-messages-ssisdb-database) de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="c03f9-119">For the full list of message types, see the documentation for the Transact-SQL [catalog.operation_messages &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-operation-messages-ssisdb-database) view.</span></span> <span data-ttu-id="c03f9-120">Para obtener una lista completa de los tipos de operaciones, vea [catalog.operations &#40;base de datos de SSISDB&#41;](/sql/integration-services/system-views/catalog-operations-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="c03f9-120">For a full list of the operations types, see [catalog.operations &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-operations-ssisdb-database).</span></span>  
  
 <span data-ttu-id="c03f9-121">Se usan nueve tipos de estado diferentes para indicar el estado de una operación.</span><span class="sxs-lookup"><span data-stu-id="c03f9-121">Nine different status types are used to indicate the status of an operation.</span></span> <span data-ttu-id="c03f9-122">Para obtener una lista completa de los tipos de estado, vea la vista [catalog.operations &#40;base de datos de SSISDB&#41;](/sql/integration-services/system-views/catalog-operations-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="c03f9-122">For a full list of the status types, see the [catalog.operations &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-operations-ssisdb-database) view.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="c03f9-123">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="c03f9-123">Related Content</span></span>  
 <span data-ttu-id="c03f9-124">Entrada de blog con una [introducción a la API T-SQL de SSIS](https://go.microsoft.com/fwlink/?LinkId=249051), en blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="c03f9-124">Blog entry, [SSIS T-SQL API Overview](https://go.microsoft.com/fwlink/?LinkId=249051), on blogs.msdn.com.</span></span>  
  
  
