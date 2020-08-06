---
title: Movimiento de un grupo de cargas de trabajo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
f1_keywords:
- sql12.swb.rg.properties_moveworkloadgroup.f1
helpviewer_keywords:
- workload groups [SQL Server], move
- Resource Governor, workload group move
ms.assetid: f2068636-6e53-486a-a6fc-c12de2a38424
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7f73b48f0ec2255760b4ee55acfaf91dc02af7cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745692"
---
# <a name="move-a-workload-group"></a><span data-ttu-id="2a7cd-102">Mover un grupo de cargas de trabajo</span><span class="sxs-lookup"><span data-stu-id="2a7cd-102">Move a Workload Group</span></span>
  <span data-ttu-id="2a7cd-103">Puede mover un grupo de cargas de trabajo del regulador de recursos a un grupo de recursos de servidor diferente utilizando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="2a7cd-103">You can move a Resource Governor workload group to a different resource pool by using either [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Transact-SQL.</span></span>  
  
-   <span data-ttu-id="2a7cd-104">**Antes de empezar:**  [Limitaciones y restricciones](#LimitationsRestrictions), [Permisos](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="2a7cd-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="2a7cd-105">**Para mover un grupo de cargas de trabajo con:**  [SQL Server Management Studio](#MoveWGSSMS), [Transact-SQL](#MoveWGTSQL)</span><span class="sxs-lookup"><span data-stu-id="2a7cd-105">**To move a workload group, using:**  [SQL Server Management Studio](#MoveWGSSMS), [Transact-SQL](#MoveWGTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2a7cd-106">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="2a7cd-106">Before You Begin</span></span>  
 <span data-ttu-id="2a7cd-107">No puede mover un grupo de cargas de trabajo si hay una operación de configuración del regulador de recursos pendiente.</span><span class="sxs-lookup"><span data-stu-id="2a7cd-107">You cannot move a workload group if there is a pending Resource Governor configuration operation.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="2a7cd-108">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="2a7cd-108">Limitations and Restrictions</span></span>  
 <span data-ttu-id="2a7cd-109">No puede mover un grupo de cargas de trabajo si hay una operación de configuración del regulador de recursos pendiente.</span><span class="sxs-lookup"><span data-stu-id="2a7cd-109">You cannot move a workload group if there is a pending Resource Governor configuration operation.</span></span> <span data-ttu-id="2a7cd-110">Es posible determinar si existe una configuración pendiente consultando la vista de administración dinámica [sys.dm_resource_governor_configuration &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-configuration-transact-sql) para obtener el estado actual de is_configuration_pending.</span><span class="sxs-lookup"><span data-stu-id="2a7cd-110">You can determine whether there is a configuration pending by querying the [sys.dm_resource_governor_configuration &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-configuration-transact-sql) dynamic management view to get the current status of is_configuration_pending.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2a7cd-111">Permisos</span><span class="sxs-lookup"><span data-stu-id="2a7cd-111">Permissions</span></span>  
 <span data-ttu-id="2a7cd-112">Mover un grupo de cargas de trabajo requiere un permiso CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="2a7cd-112">Moving a workload group requires CONTROL SERVER permission.</span></span>  
  
##  <a name="move-a-workload-group-using-sql-server-management-studio"></a><a name="MoveWGSSMS"></a> <span data-ttu-id="2a7cd-113">Mover un grupo de cargas de trabajo mediante SQL Server Management</span><span class="sxs-lookup"><span data-stu-id="2a7cd-113">Move a Workload Group Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="2a7cd-114">**Para mover un grupo de cargas de trabajo utilizando [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="2a7cd-114">**To move a workload group by using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]**</span></span>  
  
1.  <span data-ttu-id="2a7cd-115">En el Explorador de objetos, expanda de forma recursiva el nodo **Administración** hasta el nodo **Regulador de recursos**.</span><span class="sxs-lookup"><span data-stu-id="2a7cd-115">In Object Explorer, recursively expand the **Management** node down to **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="2a7cd-116">Haga clic con el botón derecho en **Regulador de recursos** y, luego, haga clic en **Propiedades**. De este modo se abre la página **Propiedades del regulador de recursos** .</span><span class="sxs-lookup"><span data-stu-id="2a7cd-116">Right-click **Resource Governor** and then click **Properties**, this opens the **Resource Governor Properties** page.</span></span>  
  
3.  <span data-ttu-id="2a7cd-117">En la ventana **Grupos de recursos** , haga clic en el grupo de recursos de servidor que contiene el grupo de cargas de trabajo que se va a mover.</span><span class="sxs-lookup"><span data-stu-id="2a7cd-117">In the **Resource Pools** window, click the resource pool containing the workload group to be moved.</span></span> <span data-ttu-id="2a7cd-118">La ventana **Grupos de cargas de trabajo** enumera ahora los grupos de cargas de trabajo que contiene ese grupo de recursos de servidor.</span><span class="sxs-lookup"><span data-stu-id="2a7cd-118">The **Workload Groups** window now lists the workload groups in that resource pool.</span></span>  
  
4.  <span data-ttu-id="2a7cd-119">En la ventana **Grupos de cargas de trabajo** , haga clic con el botón derecho en la flecha derecha situada a la izquierda del grupo de cargas de trabajo que se va a mover y haga clic en **Mover a**.</span><span class="sxs-lookup"><span data-stu-id="2a7cd-119">In the **Workload Groups** window, right-click the right arrow to the left of the workload group to be moved, and click **Move to**.</span></span> <span data-ttu-id="2a7cd-120">Esto muestra una ventana **Mover grupo de cargas de trabajo** .</span><span class="sxs-lookup"><span data-stu-id="2a7cd-120">This displays a **Move Workload Group** window.</span></span>  
  
5.  <span data-ttu-id="2a7cd-121">Los grupos de recursos de servidor disponibles se muestran en la ventana.</span><span class="sxs-lookup"><span data-stu-id="2a7cd-121">Available resource pools are displayed in the window.</span></span> <span data-ttu-id="2a7cd-122">Haga clic en el nombre del grupo de recursos de servidor al que desea mover el grupo de cargas de trabajo y, a continuación, haga clic en **Aceptar** para llevar a cabo esta acción.</span><span class="sxs-lookup"><span data-stu-id="2a7cd-122">Click the name of the resource pool that you want to move the workload group to, and then click **OK** to carry out this action.</span></span>  
  
6.  <span data-ttu-id="2a7cd-123">Esta acción no se completa hasta que se hace clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2a7cd-123">This action is not completed until after you click **OK**.</span></span> <span data-ttu-id="2a7cd-124">Al hacer clic en **Aceptar**, se ejecutará la instrucción ALTER RESOURCE GOVERNOR RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="2a7cd-124">When you click **OK**, the ALTER RESOURCE GOVERNOR RECONFIGURE statement is executed.</span></span>  
  
7.  <span data-ttu-id="2a7cd-125">Si la operación de creación o cambio de configuración sobre el grupo de recursos de servidor o el grupo de cargas de trabajo produce un error, aparecerá un informe de error debajo del título de la página de propiedades.</span><span class="sxs-lookup"><span data-stu-id="2a7cd-125">If the create or reconfigure operation fails for the resource pool or workload group, a summary error message appears below the title of the property page.</span></span> <span data-ttu-id="2a7cd-126">Para ver un mensaje de error más detallado, haga clic en la flecha abajo que aparece en el mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="2a7cd-126">To see a detailed error message, click the down arrow on the error message.</span></span>  
  
##  <a name="move-a-workload-group-using-transact-sql"></a><a name="MoveWGTSQL"></a> <span data-ttu-id="2a7cd-127">Mover un grupo de cargas de trabajo mediante Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2a7cd-127">Move a Workload Group Using Transact-SQL</span></span>  
 <span data-ttu-id="2a7cd-128">**Para mover un grupo de cargas de trabajo utilizando Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="2a7cd-128">**To move a workload group by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="2a7cd-129">Ejecute la instrucción `ALTER WORKLOAD GROUP` especificando el nombre del grupo de cargas de trabajo que se va a mover y el grupo de recursos de servidor al que se debería mover.</span><span class="sxs-lookup"><span data-stu-id="2a7cd-129">Run the `ALTER WORKLOAD GROUP` statement specifying the name of the workload group to be moved and the resource pool to which it should be moved.</span></span>  
  
2.  <span data-ttu-id="2a7cd-130">Ejecute la instrucción **ALTER RESOURCE GOVERNOR RECONFIGURE** .</span><span class="sxs-lookup"><span data-stu-id="2a7cd-130">Run the **ALTER RESOURCE GOVERNOR RECONFIGURE** statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="2a7cd-131">Ejemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="2a7cd-131">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="2a7cd-132">El siguiente ejemplo mueve un grupo de cargas de trabajo denominado `groupAdhoc` al grupo de recursos de servidor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="2a7cd-132">The following example moves a workload group named `groupAdhoc` to the default resource pool.</span></span>  
  
```  
ALTER WORKLOAD GROUP groupAdhoc  
USING [default];  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="2a7cd-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2a7cd-133">See Also</span></span>  
 <span data-ttu-id="2a7cd-134">[Regulador de recursos](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="2a7cd-134">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="2a7cd-135">[Habilitar el regulador de recursos](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="2a7cd-135">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="2a7cd-136">[Crear un grupo de recursos de servidor](create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="2a7cd-136">[Create a Resource Pool](create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="2a7cd-137">[Crear un grupo de cargas de trabajo](create-a-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="2a7cd-137">[Create a Workload Group](create-a-workload-group.md) </span></span>  
 <span data-ttu-id="2a7cd-138">[ALTER WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2a7cd-138">[ALTER WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-workload-group-transact-sql) </span></span>  
 [<span data-ttu-id="2a7cd-139">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2a7cd-139">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
