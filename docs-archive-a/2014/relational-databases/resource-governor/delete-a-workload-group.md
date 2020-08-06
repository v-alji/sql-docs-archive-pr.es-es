---
title: Eliminación de un grupo de cargas de trabajo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- workload groups [SQL Server], delete
- Resource Governor, workload group delete
ms.assetid: d5902c46-5c28-4ac1-8b56-cb4ca2b072d0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 801a731db6c5b31bc479d1a3f6079c45ad9a7c04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745701"
---
# <a name="delete-a-workload-group"></a><span data-ttu-id="67e13-102">Eliminar un grupo de cargas de trabajo</span><span class="sxs-lookup"><span data-stu-id="67e13-102">Delete a Workload Group</span></span>
  <span data-ttu-id="67e13-103">Puede eliminar un grupo de cargas de trabajo o grupo de recursos de servidor mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="67e13-103">You can delete a workload group or resource pool by using either [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Transact-SQL.</span></span>  
  
-   <span data-ttu-id="67e13-104">**Antes de empezar:**  [Limitaciones y restricciones](#LimitationsRestrictions), [Permisos](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="67e13-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="67e13-105">**Para eliminar un grupo de cargas de trabajo con:**  [Explorador de objetos](#DelWGObjEx), [Propiedades de Resource Governor](#DelWGRGProp), [Transact-SQL](#DelWGTSQL)</span><span class="sxs-lookup"><span data-stu-id="67e13-105">**To delete a workload group, using:**  [Object Explorer](#DelWGObjEx), [Resource Governor Properties](#DelWGRGProp), [Transact-SQL](#DelWGTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="67e13-106">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="67e13-106">Before You Begin</span></span>  
 <span data-ttu-id="67e13-107">No puede eliminar un grupo de cargas de trabajo si contiene sesiones activas.</span><span class="sxs-lookup"><span data-stu-id="67e13-107">You cannot delete a workload group if it contains active sessions.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="67e13-108">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="67e13-108">Limitations and Restrictions</span></span>  
 <span data-ttu-id="67e13-109">Si un grupo de cargas de trabajo contiene sesiones activas, no se podrá eliminar ni mover el grupo de cargas de trabajo a otro grupo de recursos de servidor si se llama a la instrucción ALTER RESOURCE GOVERNOR RECONFIGURE para aplicar el cambio.</span><span class="sxs-lookup"><span data-stu-id="67e13-109">If a workload group contains active sessions, deleting or moving the workload group to a different resource pool will fail when the ALTER RESOURCE GOVERNOR RECONFIGURE statement is called to apply the change.</span></span> <span data-ttu-id="67e13-110">Para evitar este problema, puede realizar una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="67e13-110">To avoid this problem, you can take one of the following actions:</span></span>  
  
-   <span data-ttu-id="67e13-111">Espere hasta que se hayan desconectado todas las sesiones en el grupo afectado y, a continuación, vuelve a ejecutar la instrucción ALTER RESOURCE GOVERNOR RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="67e13-111">Wait until all the sessions from the affected group have disconnected, and then rerun the ALTER RESOURCE GOVERNOR RECONFIGURE statement.</span></span>  
  
-   <span data-ttu-id="67e13-112">Detenga explícitamente las sesiones en el grupo afectado mediante el comando KILL y, a continuación, vuelva a ejecutar la instrucción ALTER RESOURCE GOVERNOR RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="67e13-112">Explicitly stop sessions in the affected group by using the KILL command, and then rerun the ALTER RESOURCE GOVERNOR RECONFIGURE statement.</span></span> <span data-ttu-id="67e13-113">Si decide que no quiere detener explícitamente las sesiones después de usar **Eliminar** pero antes de detener las sesiones activas, vuelva a crear el grupo usando el nombre original y mueva el grupo al grupo de recursos de servidor original.</span><span class="sxs-lookup"><span data-stu-id="67e13-113">If you decide that you do not want to explicitly stop sessions after you use **Delete** but before you stop active sessions, re-create the group by using the original name and move the group to the original resource pool.</span></span>  
  
-   <span data-ttu-id="67e13-114">Reinicie el servidor.</span><span class="sxs-lookup"><span data-stu-id="67e13-114">Restart the server.</span></span> <span data-ttu-id="67e13-115">Una vez completado el proceso del reinicio, no se creará el grupo eliminado y un grupo movido utilizará la nueva asignación del grupo de recursos de servidor.</span><span class="sxs-lookup"><span data-stu-id="67e13-115">After the restart process is completed, the deleted group will not be created, and a moved group will use the new resource pool assignment.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="67e13-116">Permisos</span><span class="sxs-lookup"><span data-stu-id="67e13-116">Permissions</span></span>  
 <span data-ttu-id="67e13-117">Eliminar un grupo de cargas de trabajo requiere un permiso CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="67e13-117">Deleting a workload group requires CONTROL SERVER permission.</span></span>  
  
##  <a name="delete-a-workload-group-using-object-explorer"></a><a name="DelWGObjEx"></a> <span data-ttu-id="67e13-118">Eliminar un grupo de carga de trabajo mediante el Explorador de objetos</span><span class="sxs-lookup"><span data-stu-id="67e13-118">Delete a Workload Group Using Object Explorer</span></span>  
 <span data-ttu-id="67e13-119">**Para eliminar un grupo de cargas de trabajo mediante el Explorador de objetos**</span><span class="sxs-lookup"><span data-stu-id="67e13-119">**To delete a workload group by using Object Explorer**</span></span>  
  
1.  <span data-ttu-id="67e13-120">En[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], abra el Explorador de objetos y expanda de forma recursiva el nodo **Administración** hasta **Grupos de recursos de servidor**incluido.</span><span class="sxs-lookup"><span data-stu-id="67e13-120">In[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to and including **Resource Pools**.</span></span>  
  
2.  <span data-ttu-id="67e13-121">Expanda de forma recursiva **Grupos de recursos** hasta e incluido el nodo **Grupos de carga de trabajo** en el grupo de recursos de servidor que contiene el grupo de cargas de trabajo que va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="67e13-121">Recursively expand **Resource Pools** down to and including the **Workload Groups** node in the resource pool that contains the workload group to be deleted.</span></span>  
  
3.  <span data-ttu-id="67e13-122">Haga clic con el botón derecho en el grupo de cargas de trabajo y, después, seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="67e13-122">Right-click the workload group, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="67e13-123">En la ventana **Eliminar objeto** aparece el grupo de cargas de trabajo en la lista **Objeto que se va a eliminar** .</span><span class="sxs-lookup"><span data-stu-id="67e13-123">In the **Delete Object** window, the workload group is listed in the **Object to be deleted** list.</span></span> <span data-ttu-id="67e13-124">Para eliminar el grupo de cargas de trabajo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="67e13-124">To delete the workload group, click **OK**.</span></span>  
  
##  <a name="delete-a-workload-group-using-resource-governor-properties"></a><a name="DelWGRGProp"></a> <span data-ttu-id="67e13-125">Eliminar un grupo de cargas de trabajo mediante Propiedades del regulador de recursos</span><span class="sxs-lookup"><span data-stu-id="67e13-125">Delete a Workload Group Using Resource Governor Properties</span></span>  
 <span data-ttu-id="67e13-126">**Para eliminar un grupo de cargas de trabajo mediante la página Propiedades del regulador de recursos**</span><span class="sxs-lookup"><span data-stu-id="67e13-126">**To delete a workload group by using the Resource Governor Properties page**</span></span>  
  
1.  <span data-ttu-id="67e13-127">En el Explorador de objetos, expanda de forma recursiva el nodo **Administración** hasta el nodo **Grupos de recursos de servidor**, éste incluido.</span><span class="sxs-lookup"><span data-stu-id="67e13-127">In Object Explorer, recursively expand the **Management** node down to and including **Resource Pools**.</span></span>  
  
2.  <span data-ttu-id="67e13-128">Haga clic con el botón derecho en el grupo de recursos de servidor que contiene el grupo de cargas de trabajo que va a eliminar y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="67e13-128">Right-click the resource pool that contains the workload group to be deleted, and then click **Properties**.</span></span> <span data-ttu-id="67e13-129">Se abre la página **Propiedades del regulador de recursos** .</span><span class="sxs-lookup"><span data-stu-id="67e13-129">This opens the **Resource Governor Properties** page.</span></span>  
  
3.  <span data-ttu-id="67e13-130">En la ventana **Grupos de cargas de trabajo para grupos de recursos** , haga clic en la línea del grupo de cargas de trabajo que va a eliminar, haga clic con el botón derecho en la flecha derecha situada en el lado izquierdo de la línea y, después, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="67e13-130">In the **Workload groups for resource pool** window, click the line for the workload group to be deleted, then right-click the right arrow on the left side of the line, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="67e13-131">Para eliminar el grupo de cargas de trabajo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="67e13-131">To delete the workload group, click **OK**.</span></span>  
  
##  <a name="delete-a-workload-group-using-transact-sql"></a><a name="DelWGTSQL"></a> <span data-ttu-id="67e13-132">Eliminar un grupo de cargas de trabajo mediante Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="67e13-132">Delete a Workload Group Using Transact-SQL</span></span>  
 <span data-ttu-id="67e13-133">**Para eliminar un grupo de cargas de trabajo utilizando Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="67e13-133">**To delete a workload group by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="67e13-134">Ejecute la instrucción `DROP WORKLOAD GROUP` especificando el nombre del grupo de cargas de trabajo que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="67e13-134">Run the `DROP WORKLOAD GROUP` statement specifying the name of the workload group to delete.</span></span>  
  
2.  <span data-ttu-id="67e13-135">Antes de emitir la instrucción `ALTER RESOURCE GOVERNOR RECONFIGURE`, compruebe que no hay ninguna solicitud activa en el grupo de cargas de trabajo que va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="67e13-135">Before you issue the `ALTER RESOURCE GOVERNOR RECONFIGURE` statement, verify that there are no active requests in the workload group being deleted.</span></span> <span data-ttu-id="67e13-136">Si hay solicitudes activas, `ALTER RESOURCE GOVERNOR` producirá un error.</span><span class="sxs-lookup"><span data-stu-id="67e13-136">If there are active requests, `ALTER RESOURCE GOVERNOR` will fail.</span></span> <span data-ttu-id="67e13-137">Para evitar este problema, puede realizar una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="67e13-137">To avoid this issue, you can take one of the following actions:</span></span>  
  
    -   <span data-ttu-id="67e13-138">Espere hasta todas las sesiones del grupo de cargas de trabajo se hayan desconectado.</span><span class="sxs-lookup"><span data-stu-id="67e13-138">Wait until all the sessions from the workload group have disconnected.</span></span>  
  
    -   <span data-ttu-id="67e13-139">Detenga explícitamente las sesiones del grupo de cargas de trabajo mediante el comando `KILL`.</span><span class="sxs-lookup"><span data-stu-id="67e13-139">Explicitly stop sessions in the workload group by using the `KILL` command.</span></span>  
  
    -   <span data-ttu-id="67e13-140">Reinicie el servidor.</span><span class="sxs-lookup"><span data-stu-id="67e13-140">Restart the server.</span></span> <span data-ttu-id="67e13-141">No se volverá a crear el grupo de cargas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="67e13-141">The workload group will not be re-created.</span></span>  
  
    -   <span data-ttu-id="67e13-142">En un escenario en el que ha emitido la instrucción `DROP WORKLOAD GROUP` pero no desea detener explícitamente las sesiones para aplicar el cambio, puede volver a crear el grupo si utiliza el mismo nombre que tenía antes de emitir la instrucción DROP y, a continuación, mueve el grupo al grupo de recursos de servidor original.</span><span class="sxs-lookup"><span data-stu-id="67e13-142">In a scenario in which you have issued the `DROP WORKLOAD GROUP` statement but decide that you do not want to explicitly stop sessions to apply the change, you can re-create the group by using the same name that it had before you issued the DROP statement, and then move the group to the original resource pool.</span></span>  
  
3.  <span data-ttu-id="67e13-143">Ejecute la `ALTER RESOURCE GOVERNOR RECONFIGURE` instrucción.</span><span class="sxs-lookup"><span data-stu-id="67e13-143">Run the `ALTER RESOURCE GOVERNOR RECONFIGURE` statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="67e13-144">Ejemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="67e13-144">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="67e13-145">En el ejemplo siguiente se quita un grupo de cargas de trabajo denominado `groupAdhoc`.</span><span class="sxs-lookup"><span data-stu-id="67e13-145">The following example drops a workload group named `groupAdhoc`.</span></span>  
  
```  
DROP WORKLOAD GROUP groupAdhoc;  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="67e13-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="67e13-146">See Also</span></span>  
 <span data-ttu-id="67e13-147">[Regulador de recursos](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="67e13-147">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="67e13-148">[Crear un grupo de recursos de servidor](create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="67e13-148">[Create a Resource Pool](create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="67e13-149">[Crear un grupo de cargas de trabajo](create-a-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="67e13-149">[Create a Workload Group](create-a-workload-group.md) </span></span>  
 <span data-ttu-id="67e13-150">[Eliminar un grupo de recursos de servidor](delete-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="67e13-150">[Delete a Resource Pool](delete-a-resource-pool.md) </span></span>  
 <span data-ttu-id="67e13-151">[DROP WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="67e13-151">[DROP WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-workload-group-transact-sql) </span></span>  
 <span data-ttu-id="67e13-152">[DROP RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="67e13-152">[DROP RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-resource-pool-transact-sql) </span></span>  
 [<span data-ttu-id="67e13-153">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="67e13-153">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
