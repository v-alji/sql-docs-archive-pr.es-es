---
title: Cambio de la configuración del grupo de cargas de trabajo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- workload groups [SQL Server], alter
- Resource Governor, workload group alter
ms.assetid: 73b6109c-2ad0-4915-b11b-d40d5a0fdc25
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 579aad71d32a629d75f1eecd76e7dacfe32d94f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661893"
---
# <a name="change-workload-group-settings"></a><span data-ttu-id="7ac41-102">Cambiar la configuración del grupo de cargas de trabajo</span><span class="sxs-lookup"><span data-stu-id="7ac41-102">Change Workload Group Settings</span></span>
  <span data-ttu-id="7ac41-103">Puede modificar la configuración de un grupo de cargas de trabajo utilizando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7ac41-103">You can change workload group settings by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="7ac41-104">**Antes de empezar:**  [Limitaciones y restricciones](#LimitationsRestrictions), [Permisos](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="7ac41-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="7ac41-105">**Para cambiar la configuración de una carga de trabajo de grupo mediante:**  [SQL Server Management Studio](#ChgWGProp), [Transact-SQL](#ChgWGTSQL)</span><span class="sxs-lookup"><span data-stu-id="7ac41-105">**To change the settings for a workload group, using:**  [SQL Server Management Studio](#ChgWGProp), [Transact-SQL](#ChgWGTSQL)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="7ac41-106">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="7ac41-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="7ac41-107">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="7ac41-107">Limitations and Restrictions</span></span>  
 <span data-ttu-id="7ac41-108">Puede cambiar la configuración del grupo de cargas de trabajo predeterminado y los grupos de cargas de trabajo definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="7ac41-108">You can change the settings of the default workload group and user-defined workload groups.</span></span>  
  
 <span data-ttu-id="7ac41-109">**REQUEST_MAX_MEMORY_GRANT_PERCENT**</span><span class="sxs-lookup"><span data-stu-id="7ac41-109">**REQUEST_MAX_MEMORY_GRANT_PERCENT**</span></span>  
  
 <span data-ttu-id="7ac41-110">La memoria consumida por la creación de índices en una tabla con particiones no alineada es proporcional al número de particiones involucradas.</span><span class="sxs-lookup"><span data-stu-id="7ac41-110">The memory consumed by index creation on a non-aligned partitioned table is proportional to the number of partitions involved.</span></span> <span data-ttu-id="7ac41-111">Si la memoria total necesaria supera el límite por consulta (REQUEST_MAX_MEMORY_GRANT_PERCENT) impuesto por la configuración del grupo de cargas de trabajo, puede que esta creación de índices produzca un error.</span><span class="sxs-lookup"><span data-stu-id="7ac41-111">If the total required memory exceeds the per-query limit, (REQUEST_MAX_MEMORY_GRANT_PERCENT) imposed by the workload group setting, this index creation may fail.</span></span> <span data-ttu-id="7ac41-112">Dado que el grupo de cargas de trabajo predeterminado permite que una consulta supere el límite por consulta con la memoria mínima necesaria para iniciar la compatibilidad con SQL Server 2005, es posible que el usuario pueda ejecutar la misma creación de índices en el grupo de cargas de trabajo predeterminado si el grupo de recursos de servidor predeterminado tiene configurada una memoria total suficiente para ejecutar una consulta.</span><span class="sxs-lookup"><span data-stu-id="7ac41-112">Because the default workload group allows a query to exceed the per-query limit with the minimum required memory to start for SQL Server 2005 compatibility, the user may be able to run the same index creation in the default workload group, if the default resource pool has enough total memory configured to run such a query.</span></span>  
  
 <span data-ttu-id="7ac41-113">Se permite la creación de índices para usar más memoria del área de trabajo que la concedida inicialmente para mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="7ac41-113">Index creation is allowed to use more memory workspace than initially granted for performance.</span></span> <span data-ttu-id="7ac41-114">El regulador de recursos admite este tratamiento especial; sin embargo, la concesión inicial y cualquier concesión de memoria adicional están limitadas por la configuración del grupo de cargas de trabajo y el grupo de recursos de servidor.</span><span class="sxs-lookup"><span data-stu-id="7ac41-114">This special handling is supported by Resource Governor, however, the initial grant and any additional memory grant are limited by the workload group and resource pool settings.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7ac41-115">Permisos</span><span class="sxs-lookup"><span data-stu-id="7ac41-115">Permissions</span></span>  
 <span data-ttu-id="7ac41-116">Cambiar la configuración del grupo de cargas de trabajo requiere el permiso CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="7ac41-116">Changing workload group settings requires CONTROL SERVER permission.</span></span>  
  
##  <a name="change-workload-group-settings-using-sql-server-management-studio"></a><a name="ChgWGProp"></a> <span data-ttu-id="7ac41-117">Cambiar la configuración del grupo de cargas de trabajo mediante SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7ac41-117">Change Workload Group Settings Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="7ac41-118">**Para cambiar la configuración del grupo de cargas de trabajo utilizando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="7ac41-118">**To change workload group settings by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span></span>  
  
1.  <span data-ttu-id="7ac41-119">En el Explorador de objetos, expanda de forma recursiva el nodo **Management** hasta e incluida la carpeta **Grupos de cargas de trabajo** que contiene el grupo de cargas de trabajo que se va a modificar.</span><span class="sxs-lookup"><span data-stu-id="7ac41-119">In Object Explorer, recursively expand the **Management** node down to and including the **Workload Groups** folder that contains the workload group to be modified.</span></span>  
  
2.  <span data-ttu-id="7ac41-120">Haga clic con el botón derecho en el grupo de cargas de trabajo que se va a modificar y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7ac41-120">Right-click the workload group to be modified, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="7ac41-121">En la página **Propiedades del regulador de recursos** , seleccione la fila del grupo de cargas de trabajo en la cuadrícula **Grupos de cargas de trabajo del grupo de recursos de servidor** si no está seleccionada automáticamente.</span><span class="sxs-lookup"><span data-stu-id="7ac41-121">In the **Resource Governor Properties** page, select the row for the workload group in the **Workload groups for resource pool** grid if it is not automatically selected.</span></span>  
  
4.  <span data-ttu-id="7ac41-122">Haga clic o doble clic en las celdas de la fila que va a cambiar y especifique los nuevos valores.</span><span class="sxs-lookup"><span data-stu-id="7ac41-122">Click or double-click the cells in the row to be changed, and enter the new values.</span></span>  
  
5.  <span data-ttu-id="7ac41-123">Haga clic en **Aceptar**para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="7ac41-123">To save the changes, click **OK**</span></span>  
  
##  <a name="change-workload-group-settings-using-transact-sql"></a><a name="ChgWGTSQL"></a> <span data-ttu-id="7ac41-124">Cambiar la configuración del grupo de cargas de trabajo mediante Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7ac41-124">Change Workload Group Settings Using Transact-SQL</span></span>  
 <span data-ttu-id="7ac41-125">**Para cambiar la configuración del grupo de cargas de trabajo utilizando Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="7ac41-125">**To change workload group settings by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="7ac41-126">Ejecute la instrucción ALTER WORKLOAD GROUP especificando los valores de propiedad que desea cambiar.</span><span class="sxs-lookup"><span data-stu-id="7ac41-126">Run the ALTER WORKLOAD GROUP statement specifying the property values to be changed.</span></span>  
  
2.  <span data-ttu-id="7ac41-127">Ejecute la instrucción ALTER RESOURCE GOVERNOR RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="7ac41-127">Run the ALTER RESOURCE GOVERNOR RECONFIGURE statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="7ac41-128">Ejemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7ac41-128">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="7ac41-129">En el siguiente ejemplo se cambia el porcentaje de concesión de memoria máxima del grupo de cargas de trabajo denominado `groupAdhoc`.</span><span class="sxs-lookup"><span data-stu-id="7ac41-129">The following example changes the max memory grant percent setting for the workload group named `groupAdhoc`.</span></span>  
  
```  
ALTER WORKLOAD GROUP groupAdhoc  
WITH (REQUEST_MAX_MEMORY_GRANT_PERCENT = 30);  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="7ac41-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7ac41-130">See Also</span></span>  
 <span data-ttu-id="7ac41-131">[Regulador de recursos](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="7ac41-131">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="7ac41-132">[Crear un grupo de cargas de trabajo](create-a-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="7ac41-132">[Create a Workload Group](create-a-workload-group.md) </span></span>  
 <span data-ttu-id="7ac41-133">[Crear un grupo de recursos de servidor](create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="7ac41-133">[Create a Resource Pool](create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="7ac41-134">[Cambiar la configuración del grupo de recursos de servidor](change-resource-pool-settings.md) </span><span class="sxs-lookup"><span data-stu-id="7ac41-134">[Change Resource Pool Settings](change-resource-pool-settings.md) </span></span>  
 <span data-ttu-id="7ac41-135">[ALTER WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7ac41-135">[ALTER WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-workload-group-transact-sql) </span></span>  
 <span data-ttu-id="7ac41-136">[ALTER RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7ac41-136">[ALTER RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-pool-transact-sql) </span></span>  
 [<span data-ttu-id="7ac41-137">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7ac41-137">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
