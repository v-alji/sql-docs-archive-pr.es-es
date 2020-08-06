---
title: Cuadro de diálogo operaciones activas | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.isoperations.executions.f1
- sql12.ssis.ssms.isoperations.general.f1
ms.assetid: 5bb0fcd6-0ce9-488a-85b8-25dddaa03cda
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 49861de7be207875c554e02d3f3b1b2f941fff64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669819"
---
# <a name="active-operations-dialog-box"></a><span data-ttu-id="8ad08-102">Operaciones activas, cuadro de diálogo</span><span class="sxs-lookup"><span data-stu-id="8ad08-102">Active Operations Dialog Box</span></span>
  <span data-ttu-id="8ad08-103">Utilice el cuadro de diálogo **Operaciones activas** para ver el estado de las operaciones de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que se están ejecutando actualmente en el servidor de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , como implementación, validación, y ejecución del paquete.</span><span class="sxs-lookup"><span data-stu-id="8ad08-103">Use the **Active Operations** dialog box to view the status of currently running [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] operations on the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server, such as deployment, validation, and package execution.</span></span> <span data-ttu-id="8ad08-104">Estos datos se almacenan en el catálogo de SSISDB.</span><span class="sxs-lookup"><span data-stu-id="8ad08-104">This data is stored in the SSISDB catalog.</span></span>  
  
 <span data-ttu-id="8ad08-105">Para obtener más información sobre las vistas de [!INCLUDE[tsql](../includes/tsql-md.md)] relacionadas, vea [catalog.operations &#40;base de datos de SSISDB&#41;](/sql/integration-services/system-views/catalog-operations-ssisdb-database), [catalog.validations &#40;base de datos de SSISDB&#41;](/sql/integration-services/system-views/catalog-validations-ssisdb-database) y [catalog.executions &#40;base de datos de SSISDB&#41;](/sql/integration-services/system-views/catalog-executions-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="8ad08-105">For more information about related [!INCLUDE[tsql](../includes/tsql-md.md)] views, see [catalog.operations &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-operations-ssisdb-database), [catalog.validations &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-validations-ssisdb-database), and [catalog.executions &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-executions-ssisdb-database)</span></span>  
  
 <span data-ttu-id="8ad08-106">**¿Qué desea hacer?**</span><span class="sxs-lookup"><span data-stu-id="8ad08-106">**What do you want to do?**</span></span>  
  
1.  [<span data-ttu-id="8ad08-107">Abrir el cuadro de diálogo operaciones activas</span><span class="sxs-lookup"><span data-stu-id="8ad08-107">Open the Active Operations Dialog Box</span></span>](#open_dialog)  
  
2.  [<span data-ttu-id="8ad08-108">Configurar las opciones</span><span class="sxs-lookup"><span data-stu-id="8ad08-108">Configure the Options</span></span>](#options)  
  
##  <a name="open-the-active-operations-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="8ad08-109">Abrir el cuadro de diálogo Operaciones activas</span><span class="sxs-lookup"><span data-stu-id="8ad08-109">Open the Active Operations Dialog Box</span></span>  
  
1.  <span data-ttu-id="8ad08-110">Abra [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8ad08-110">Open [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span>  
  
2.  <span data-ttu-id="8ad08-111">Conéctese al motor de base de datos de Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="8ad08-111">Connect Microsoft SQL Server Database Engine</span></span>  
  
3.  <span data-ttu-id="8ad08-112">En el Explorador de objetos, expanda el nodo **Integration Services** , haga clic con el botón derecho en **SSISDB**y, después, haga clic en **Operaciones activas**.</span><span class="sxs-lookup"><span data-stu-id="8ad08-112">In Object Explorer, expand the **Integration Services** node, right-click **SSISDB**, and then click **Active Operations**.</span></span>  
  
##  <a name="configure-the-options"></a><a name="options"></a> <span data-ttu-id="8ad08-113">Configurar las opciones</span><span class="sxs-lookup"><span data-stu-id="8ad08-113">Configure the Options</span></span>  
  
### <a name="options"></a><span data-ttu-id="8ad08-114">Opciones</span><span class="sxs-lookup"><span data-stu-id="8ad08-114">Options</span></span>  
 <span data-ttu-id="8ad08-115">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="8ad08-115">**Type**</span></span>  
 <span data-ttu-id="8ad08-116">Especifica el tipo de operación.</span><span class="sxs-lookup"><span data-stu-id="8ad08-116">Specifies the type of operation.</span></span> <span data-ttu-id="8ad08-117">A continuación se muestran los valores posibles para el campo de **tipo** y los valores correspondientes en la columna operations_type de la vista de TRANSACT-SQL `catalog.operations` .</span><span class="sxs-lookup"><span data-stu-id="8ad08-117">The following are the possible values for the **Type** field and the corresponding values in the operations_type column of the Transact-SQL `catalog.operations` view.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8ad08-118">Inicialización de Integration Services</span><span class="sxs-lookup"><span data-stu-id="8ad08-118">Integration Services initialization</span></span>|<span data-ttu-id="8ad08-119">1</span><span class="sxs-lookup"><span data-stu-id="8ad08-119">1</span></span>|  
|<span data-ttu-id="8ad08-120">Limpieza de operaciones (trabajo del Agente SQL Server)</span><span class="sxs-lookup"><span data-stu-id="8ad08-120">Operations cleanup (SQL Agent job)</span></span>|<span data-ttu-id="8ad08-121">2</span><span class="sxs-lookup"><span data-stu-id="8ad08-121">2</span></span>|  
|<span data-ttu-id="8ad08-122">Limpieza de versiones de proyecto (trabajo del Agente SQL Server)</span><span class="sxs-lookup"><span data-stu-id="8ad08-122">Project versions cleanup (SQL Agent job)</span></span>|<span data-ttu-id="8ad08-123">3</span><span class="sxs-lookup"><span data-stu-id="8ad08-123">3</span></span>|  
|<span data-ttu-id="8ad08-124">Implementar proyecto</span><span class="sxs-lookup"><span data-stu-id="8ad08-124">Deploy project</span></span>|<span data-ttu-id="8ad08-125">101</span><span class="sxs-lookup"><span data-stu-id="8ad08-125">101</span></span>|  
|<span data-ttu-id="8ad08-126">Restaurar proyecto</span><span class="sxs-lookup"><span data-stu-id="8ad08-126">Restore project</span></span>|<span data-ttu-id="8ad08-127">106</span><span class="sxs-lookup"><span data-stu-id="8ad08-127">106</span></span>|  
|<span data-ttu-id="8ad08-128">Crear e iniciar la ejecución del paquete</span><span class="sxs-lookup"><span data-stu-id="8ad08-128">Create and start package execution</span></span>|<span data-ttu-id="8ad08-129">200</span><span class="sxs-lookup"><span data-stu-id="8ad08-129">200</span></span>|  
|<span data-ttu-id="8ad08-130">Detener operación (detención de una validación o una ejecución)</span><span class="sxs-lookup"><span data-stu-id="8ad08-130">Stop operation (stopping a validation or execution</span></span>|<span data-ttu-id="8ad08-131">202</span><span class="sxs-lookup"><span data-stu-id="8ad08-131">202</span></span>|  
|<span data-ttu-id="8ad08-132">Validar proyecto</span><span class="sxs-lookup"><span data-stu-id="8ad08-132">Validate project</span></span>|<span data-ttu-id="8ad08-133">300</span><span class="sxs-lookup"><span data-stu-id="8ad08-133">300</span></span>|  
|<span data-ttu-id="8ad08-134">Validar paquete</span><span class="sxs-lookup"><span data-stu-id="8ad08-134">Validate package</span></span>|<span data-ttu-id="8ad08-135">301</span><span class="sxs-lookup"><span data-stu-id="8ad08-135">301</span></span>|  
|<span data-ttu-id="8ad08-136">Configurar catálogo</span><span class="sxs-lookup"><span data-stu-id="8ad08-136">Configure catalog</span></span>|<span data-ttu-id="8ad08-137">1000</span><span class="sxs-lookup"><span data-stu-id="8ad08-137">1000</span></span>|  
  
 <span data-ttu-id="8ad08-138">**Detención**</span><span class="sxs-lookup"><span data-stu-id="8ad08-138">**Stop**</span></span>  
 <span data-ttu-id="8ad08-139">Haga clic para detener una operación que se esté ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="8ad08-139">Click to stop a currently running operation.</span></span>  
  
  
