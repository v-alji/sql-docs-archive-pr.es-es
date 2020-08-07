---
title: Eliminación de un grupo de recursos de servidor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, resource pool delete
- resource pools [SQL Server], delete
ms.assetid: 3bdd348b-6582-4ffa-80ef-d49e50596ce5
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a67b0e2262fa3007597091b6087cc937bb0f3276
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745697"
---
# <a name="delete-a-resource-pool"></a><span data-ttu-id="4cdb8-102">Eliminar un grupo de recursos de servidor</span><span class="sxs-lookup"><span data-stu-id="4cdb8-102">Delete a Resource Pool</span></span>
  <span data-ttu-id="4cdb8-103">Puede eliminar un grupo de recursos de servidor utilizando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="4cdb8-103">You can delete a resource pool by using either [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Transact-SQL.</span></span>  
  
-   <span data-ttu-id="4cdb8-104">**Antes de empezar:**  [Limitaciones y restricciones](#LimitationsRestrictions), [Permisos](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="4cdb8-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="4cdb8-105">**Para eliminar un grupo de recursos de servidor con:** [SQL Server Management Studio](#DelRPSSMS), [Transact-SQL](#DelRPTSQL)</span><span class="sxs-lookup"><span data-stu-id="4cdb8-105">**To delete a resource pool, using:** [SQL Server Management Studio](#DelRPSSMS), [Transact-SQL](#DelRPTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4cdb8-106">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="4cdb8-106">Before You Begin</span></span>  
 <span data-ttu-id="4cdb8-107">No se puede eliminar un grupo de recursos de servidor si contiene grupos de cargas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4cdb8-107">You cannot delete a resource pool if it contains workload groups.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="4cdb8-108">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="4cdb8-108">Limitations and Restrictions</span></span>  
 <span data-ttu-id="4cdb8-109">No se pueden eliminar los grupos de recursos de servidor predeterminados o internos del regulador de recursos.</span><span class="sxs-lookup"><span data-stu-id="4cdb8-109">You cannot delete the Resource Governor default or internal resource pools.</span></span> <span data-ttu-id="4cdb8-110">No se puede eliminar un grupo de recursos de servidor si contiene grupos de cargas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4cdb8-110">You cannot delete a resource pool if it contains workload groups.</span></span> <span data-ttu-id="4cdb8-111">Para obtener más información, consulte [Delete a Workload Group](delete-a-workload-group.md).</span><span class="sxs-lookup"><span data-stu-id="4cdb8-111">For more information, see [Delete a Workload Group](delete-a-workload-group.md).</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4cdb8-112">Permisos</span><span class="sxs-lookup"><span data-stu-id="4cdb8-112">Permissions</span></span>  
 <span data-ttu-id="4cdb8-113">Para eliminar un grupo de recursos de servidor se requiere un permiso CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="4cdb8-113">Deleting a resource pool requires CONTROL SERVER permission.</span></span>  
  
##  <a name="delete-a-resource-pool-using-object-explorer"></a><a name="DelRPSSMS"></a> <span data-ttu-id="4cdb8-114">Eliminar un grupo de recursos de servidor mediante el Explorador de objetos</span><span class="sxs-lookup"><span data-stu-id="4cdb8-114">Delete a Resource Pool Using Object Explorer</span></span>  
 <span data-ttu-id="4cdb8-115">**Para eliminar un grupo de recursos de servidor mediante SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="4cdb8-115">**To delete a resource pool by using SQL Server Management Studio**</span></span>  
  
1.  <span data-ttu-id="4cdb8-116">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], abra el Explorador de objetos y expanda de forma recursiva el nodo **Administración** hasta e incluyendo el nodo **Regulador de recursos**.</span><span class="sxs-lookup"><span data-stu-id="4cdb8-116">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to and including **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="4cdb8-117">Haga clic con el botón derecho en el grupo de recursos que va a eliminar y luego haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="4cdb8-117">Right-click the resource pool to be deleted, and then click **Delete**.</span></span>  
  
3.  <span data-ttu-id="4cdb8-118">En la ventana **Eliminar objeto** aparece el grupo de recursos de servidor en la lista **Objeto que se va a eliminar** .</span><span class="sxs-lookup"><span data-stu-id="4cdb8-118">In the **Delete Object** window, the resource pool is listed in the **Object to be deleted** list.</span></span> <span data-ttu-id="4cdb8-119">Para eliminar el grupo de recursos de servidor, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4cdb8-119">To delete the resource pool, click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4cdb8-120">Si el grupo de recursos de servidor que intenta eliminar contiene un grupo de cargas de trabajo, esta acción provocará un error.</span><span class="sxs-lookup"><span data-stu-id="4cdb8-120">If the resource pool that you are trying to delete contains a workload group, this action will fail.</span></span>  
  
##  <a name="delete-a-resource-pool-using-transact-sql"></a><a name="DelRPTSQL"></a> <span data-ttu-id="4cdb8-121">Eliminar un grupo de recursos de servidor mediante Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4cdb8-121">Delete a Resource Pool Using Transact-SQL</span></span>  
 <span data-ttu-id="4cdb8-122">**Para eliminar un grupo de recursos de servidor mediante Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="4cdb8-122">**To delete a resource pool by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="4cdb8-123">Ejecute la instrucción `DROP RESOURCE POOL` especificando el nombre del grupo de recursos de servidor que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="4cdb8-123">Run the `DROP RESOURCE POOL` statement specifying the name of the resource pool to delete.</span></span>  
  
2.  <span data-ttu-id="4cdb8-124">Ejecute la instrucción **ALTER RESOURCE GOVERNOR RECONFIGURE** .</span><span class="sxs-lookup"><span data-stu-id="4cdb8-124">Run the **ALTER RESOURCE GOVERNOR RECONFIGURE** statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="4cdb8-125">Ejemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4cdb8-125">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="4cdb8-126">En el ejemplo siguiente se quita un grupo de cargas de trabajo denominado `poolAdhoc`.</span><span class="sxs-lookup"><span data-stu-id="4cdb8-126">The following example drops a workload group named `poolAdhoc`.</span></span>  
  
```  
DROP RESOURCE POOL poolAdhoc;  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="4cdb8-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4cdb8-127">See Also</span></span>  
 <span data-ttu-id="4cdb8-128">[Regulador de recursos](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="4cdb8-128">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="4cdb8-129">[Grupo de recursos de servidor del regulador de recursos](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="4cdb8-129">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="4cdb8-130">[Crear un grupo de recursos de servidor](create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="4cdb8-130">[Create a Resource Pool](create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="4cdb8-131">[Cambiar la configuración del grupo de recursos de servidor](change-resource-pool-settings.md) </span><span class="sxs-lookup"><span data-stu-id="4cdb8-131">[Change Resource Pool Settings](change-resource-pool-settings.md) </span></span>  
 <span data-ttu-id="4cdb8-132">[Grupos de cargas de trabajo del regulador de recursos](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="4cdb8-132">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="4cdb8-133">[Función clasificadora del regulador de recursos](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="4cdb8-133">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 <span data-ttu-id="4cdb8-134">[DROP WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4cdb8-134">[DROP WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-workload-group-transact-sql) </span></span>  
 <span data-ttu-id="4cdb8-135">[DROP RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4cdb8-135">[DROP RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-resource-pool-transact-sql) </span></span>  
 [<span data-ttu-id="4cdb8-136">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4cdb8-136">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
