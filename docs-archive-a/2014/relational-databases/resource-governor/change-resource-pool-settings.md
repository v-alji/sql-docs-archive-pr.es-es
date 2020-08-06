---
title: Cambio de la configuración del grupo de recursos de servidor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, resource pool alter
- resource pools [SQL Server], alter
ms.assetid: 49438285-a011-4dac-bd4f-f35cd90fda61
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2183cceaaf8a3e183d96c154075f9a922942c2c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745188"
---
# <a name="change-resource-pool-settings"></a><span data-ttu-id="5b9d9-102">Cambiar la configuración del grupo de recursos de servidor</span><span class="sxs-lookup"><span data-stu-id="5b9d9-102">Change Resource Pool Settings</span></span>
  <span data-ttu-id="5b9d9-103">Puede modificar la configuración del grupo de recursos de servidor mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b9d9-103">You can change resource pool settings by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="5b9d9-104">**Antes de empezar:**  [Limitaciones y restricciones](#LimitationsRestrictions), [Permisos](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="5b9d9-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="5b9d9-105">**Para cambiar la configuración para un grupo de recursos mediante:**  [SQL Server Management Studio](#ChgRPProp), [Transact-SQL](#ChgRPTSQL)</span><span class="sxs-lookup"><span data-stu-id="5b9d9-105">**To change the settings for a resource pool, using:**  [SQL Server Management Studio](#ChgRPProp), [Transact-SQL](#ChgRPTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5b9d9-106">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="5b9d9-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="5b9d9-107">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="5b9d9-107">Limitations and Restrictions</span></span>  
 <span data-ttu-id="5b9d9-108">El porcentaje máximo de uso de la CPU debe ser igual o superior al porcentaje mínimo de uso de la CPU.</span><span class="sxs-lookup"><span data-stu-id="5b9d9-108">The maximum CPU percentage must be equal to or higher than the minimum CPU percentage.</span></span> <span data-ttu-id="5b9d9-109">El porcentaje máximo de uso de memoria debe ser igual o superior al porcentaje mínimo de uso de memoria.</span><span class="sxs-lookup"><span data-stu-id="5b9d9-109">The maximum memory percentage must be equal to or higher than the minimum memory percentage.</span></span>  
  
 <span data-ttu-id="5b9d9-110">Las sumas de los porcentajes mínimos de uso de la CPU y los porcentajes mínimos de uso de memoria de todos los grupos de recursos de servidor no deben superar el 100 por cien.</span><span class="sxs-lookup"><span data-stu-id="5b9d9-110">The sums of the minimum CPU percentages and minimum memory percentages for all resource pools must not exceed 100.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5b9d9-111">Permisos</span><span class="sxs-lookup"><span data-stu-id="5b9d9-111">Permissions</span></span>  
 <span data-ttu-id="5b9d9-112">Para cambiar la configuración del grupo de recursos de servidor se requiere el permiso CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="5b9d9-112">Changing resource pool settings requires CONTROL SERVER permission.</span></span>  
  
##  <a name="change-resource-pool-settings-using-sql-server-management-studio"></a><a name="ChgRPProp"></a> <span data-ttu-id="5b9d9-113">Cambiar la configuración del grupo de recursos de servidor mediante SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5b9d9-113">Change Resource Pool Settings Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="5b9d9-114">**Para cambiar la configuración del grupo de recursos de servidor utilizando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="5b9d9-114">**To change resource pool settings by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span></span>  
  
1.  <span data-ttu-id="5b9d9-115">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], abra el Explorador de objetos y expanda de forma recursiva el nodo **Administración** hasta **Grupos de recursos de servidor**, con este último incluido.</span><span class="sxs-lookup"><span data-stu-id="5b9d9-115">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to and including **Resource Pools**.</span></span>  
  
2.  <span data-ttu-id="5b9d9-116">Haga clic con el botón derecho en el grupo de recursos que va a modificar y, luego, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5b9d9-116">Right-click the resource pool to be modified, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="5b9d9-117">En la página **Propiedades del regulador de recursos** , seleccione la fila del grupo de recursos de servidor en la cuadrícula **Grupos de recursos de servidor** si no está seleccionada automáticamente.</span><span class="sxs-lookup"><span data-stu-id="5b9d9-117">In the **Resource Governor Properties** page, select the row for the resource pool in the **Resource pools** grid if it is not automatically selected.</span></span>  
  
4.  <span data-ttu-id="5b9d9-118">Haga clic o doble clic en las celdas de la fila que va a cambiar y especifique los nuevos valores.</span><span class="sxs-lookup"><span data-stu-id="5b9d9-118">Click or double-click the cells in the row to be changed, and enter the new values.</span></span>  
  
5.  <span data-ttu-id="5b9d9-119">Haga clic en **Aceptar**para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="5b9d9-119">To save the changes, click **OK**</span></span>  
  
##  <a name="change-resource-pool-settings-using-transact-sql"></a><a name="ChgRPTSQL"></a> <span data-ttu-id="5b9d9-120">Cambiar la configuración del grupo de recursos de servidor mediante Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5b9d9-120">Change Resource Pool Settings Using Transact-SQL</span></span>  
 <span data-ttu-id="5b9d9-121">**Para cambiar la configuración del grupo de recursos de servidor utilizando [!INCLUDE[tsql](../../includes/tsql-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="5b9d9-121">**To change resource pool settings by using [!INCLUDE[tsql](../../includes/tsql-md.md)]**</span></span>  
  
1.  <span data-ttu-id="5b9d9-122">Ejecute la instrucción `ALTER RESOURCE POOL` especificando los valores de propiedad que desea cambiar.</span><span class="sxs-lookup"><span data-stu-id="5b9d9-122">Run the `ALTER RESOURCE POOL` statement specifying the property values to be changed.</span></span>  
  
2.  <span data-ttu-id="5b9d9-123">Ejecute la instrucción **ALTER RESOURCE GOVERNOR RECONFIGURE** .</span><span class="sxs-lookup"><span data-stu-id="5b9d9-123">Run the **ALTER RESOURCE GOVERNOR RECONFIGURE** statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="5b9d9-124">Ejemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="5b9d9-124">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="5b9d9-125">En el siguiente ejemplo se cambia el valor de porcentaje máximo de uso de la CPU del grupo de recursos de servidor denominado `poolAdhoc`.</span><span class="sxs-lookup"><span data-stu-id="5b9d9-125">The following example changes the max CPU percentage setting for the resource pool named `poolAdhoc`.</span></span>  
  
```  
ALTER RESOURCE POOL poolAdhoc  
WITH (MAX_CPU_PERCENT = 25);  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="5b9d9-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5b9d9-126">See Also</span></span>  
 <span data-ttu-id="5b9d9-127">[Regulador de recursos](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="5b9d9-127">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="5b9d9-128">[Habilitar el regulador de recursos](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="5b9d9-128">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="5b9d9-129">[Crear un grupo de recursos de servidor](create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="5b9d9-129">[Create a Resource Pool](create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="5b9d9-130">[Eliminar un grupo de recursos de servidor](delete-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="5b9d9-130">[Delete a Resource Pool](delete-a-resource-pool.md) </span></span>  
 <span data-ttu-id="5b9d9-131">[Grupos de cargas de trabajo del regulador de recursos](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="5b9d9-131">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="5b9d9-132">[Función clasificadora del regulador de recursos](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="5b9d9-132">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 <span data-ttu-id="5b9d9-133">[ALTER RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5b9d9-133">[ALTER RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-pool-transact-sql) </span></span>  
 [<span data-ttu-id="5b9d9-134">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5b9d9-134">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
