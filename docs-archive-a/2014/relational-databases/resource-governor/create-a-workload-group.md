---
title: Creación de un grupo de cargas de trabajo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, workload group create
- workload groups [SQL Server], create
ms.assetid: 072868ec-ceff-4db6-941b-281af731a067
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 144bcef57b3d6e191b03b1539e9e7382a9085c93
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671467"
---
# <a name="create-a-workload-group"></a><span data-ttu-id="5a78a-102">Crear un grupo de cargas de trabajo</span><span class="sxs-lookup"><span data-stu-id="5a78a-102">Create a Workload Group</span></span>
  <span data-ttu-id="5a78a-103">Puede crear un grupo de cargas de trabajo utilizando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a78a-103">You can create a workload group by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="5a78a-104">**Antes de empezar:**  [Limitaciones y restricciones](#LimitationsRestrictions), [Permisos](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="5a78a-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="5a78a-105">**Para crear un grupo de cargas de trabajo mediante:**  [SQL Server Management Studio](#CreWGProp), [Transact-SQL](#CreWGTSQL)</span><span class="sxs-lookup"><span data-stu-id="5a78a-105">**To create a workload group, using:**  [SQL Server Management Studio](#CreWGProp), [Transact-SQL](#CreWGTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5a78a-106">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="5a78a-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="5a78a-107">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="5a78a-107">Limitations and Restrictions</span></span>  
 <span data-ttu-id="5a78a-108">**REQUEST_MAX_MEMORY_GRANT_PERCENT**</span><span class="sxs-lookup"><span data-stu-id="5a78a-108">**REQUEST_MAX_MEMORY_GRANT_PERCENT**</span></span>  
  
 <span data-ttu-id="5a78a-109">La memoria consumida por la creación de índices en una tabla con particiones no alineada es proporcional al número de particiones involucradas.</span><span class="sxs-lookup"><span data-stu-id="5a78a-109">The memory consumed by index creation on a non-aligned partitioned table is proportional to the number of partitions involved.</span></span> <span data-ttu-id="5a78a-110">Si la memoria total necesaria supera el límite por consulta (REQUEST_MAX_MEMORY_GRANT_PERCENT) impuesto por la configuración del grupo de cargas de trabajo, puede que esta creación de índices produzca un error.</span><span class="sxs-lookup"><span data-stu-id="5a78a-110">If the total required memory exceeds the per-query limit, (REQUEST_MAX_MEMORY_GRANT_PERCENT) imposed by the workload group setting, this index creation may fail.</span></span> <span data-ttu-id="5a78a-111">Dado que el grupo de cargas de trabajo predeterminado permite que una consulta supere el límite por consulta con la memoria mínima necesaria para iniciar la compatibilidad con SQL Server 2005, es posible que el usuario pueda ejecutar la misma creación de índices en el grupo de cargas de trabajo predeterminado si el grupo de recursos de servidor predeterminado tiene configurada una memoria total suficiente para ejecutar una consulta.</span><span class="sxs-lookup"><span data-stu-id="5a78a-111">Because the default workload group allows a query to exceed the per-query limit with the minimum required memory to start for SQL Server 2005 compatibility, the user may be able to run the same index creation in the default workload group, if the default resource pool has enough total memory configured to run such a query.</span></span>  
  
 <span data-ttu-id="5a78a-112">Se permite la creación de índices para usar más memoria del área de trabajo que la concedida inicialmente para mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="5a78a-112">Index creation is allowed to use more memory workspace than initially granted for performance.</span></span> <span data-ttu-id="5a78a-113">El regulador de recursos admite este tratamiento especial; sin embargo, la concesión inicial y cualquier concesión de memoria adicional están limitadas por la configuración del grupo de cargas de trabajo y el grupo de recursos de servidor.</span><span class="sxs-lookup"><span data-stu-id="5a78a-113">This special handling is supported by Resource Governor, however, the initial grant and any additional memory grant are limited by the workload group and resource pool settings.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5a78a-114">Permisos</span><span class="sxs-lookup"><span data-stu-id="5a78a-114">Permissions</span></span>  
 <span data-ttu-id="5a78a-115">Crear un grupo de cargas de trabajo requiere un permiso CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="5a78a-115">Creating a workload group requires CONTROL SERVER permission.</span></span>  
  
##  <a name="create-a-workload-group-using-sql-server-management-studio"></a><a name="CreWGProp"></a> <span data-ttu-id="5a78a-116">Crear un grupo de cargas de trabajo mediante SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5a78a-116">Create a Workload Group Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="5a78a-117">**Para crear un grupo de cargas de trabajo utilizando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="5a78a-117">**To create a workload group by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span></span>  
  
1.  <span data-ttu-id="5a78a-118">En el Explorador de objetos, expanda de forma recursiva el nodo **Administración** hasta e incluyendo el grupo de recursos de servidor que contiene el grupo de cargas de trabajo que va a modificar.</span><span class="sxs-lookup"><span data-stu-id="5a78a-118">In Object Explorer, recursively expand the **Management** node down to and including the resource pool that contains the workload group to be modified.</span></span>  
  
2.  <span data-ttu-id="5a78a-119">Haga clic con el botón derecho en la carpeta **Grupos de cargas de trabajo** y luego haga clic en **Nuevo grupo de cargas de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="5a78a-119">Right-click the **Workload Groups** folder, and then click **New Workload Group**.</span></span>  
  
3.  <span data-ttu-id="5a78a-120">En la cuadrícula **Grupos de recursos** , asegúrese de que está resaltado el grupo de recursos de servidor al que desea agregar el grupo de carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5a78a-120">In the **Resource pools** grid, ensure the resource pool where you want to add the workload group is highlighted.</span></span>  
  
4.  <span data-ttu-id="5a78a-121">La cuadrícula **Grupos de cargas de trabajo de grupo de recursos de servidor** tendrá una nueva línea con un nombre en blanco y los valores predeterminados en las otras columnas.</span><span class="sxs-lookup"><span data-stu-id="5a78a-121">The **Workload groups for resource pool** grid will have a new line with a blank name and default values in the other columns.</span></span>  
  
5.  <span data-ttu-id="5a78a-122">Haga clic en la celda **Nombre** y escriba un nombre para el grupo de cargas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5a78a-122">Click the **Name** cell and enter a name for the workload group.</span></span>  
  
6.  <span data-ttu-id="5a78a-123">Haga clic o doble clic en cualquier otra celda de la fila cuya configuración predeterminada desee cambiar, y especifique los nuevos valores.</span><span class="sxs-lookup"><span data-stu-id="5a78a-123">Click or double-click any other cells in the row you want to change from their default settings, and enter the new values.</span></span>  
  
7.  <span data-ttu-id="5a78a-124">Haga clic en **Aceptar**para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="5a78a-124">To save the changes, click **OK**</span></span>  
  
##  <a name="create-a-workload-group-using-transact-sql"></a><a name="CreWGTSQL"></a> <span data-ttu-id="5a78a-125">Crear un grupo de cargas de trabajo mediante Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5a78a-125">Create a Workload Group Using Transact-SQL</span></span>  
 <span data-ttu-id="5a78a-126">**Para crear un grupo de cargas de trabajo utilizando [!INCLUDE[tsql](../../includes/tsql-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="5a78a-126">**To create a workload group by using [!INCLUDE[tsql](../../includes/tsql-md.md)]**</span></span>  
  
1.  <span data-ttu-id="5a78a-127">Ejecute la instrucción CREATE WORKLOAD GROUP especificando los valores de propiedad que desea establecer.</span><span class="sxs-lookup"><span data-stu-id="5a78a-127">Run the CREATE WORKLOAD GROUP statement specifying the property values to be set.</span></span>  
  
2.  <span data-ttu-id="5a78a-128">Ejecute la instrucción ALTER RESOURCE GOVERNOR RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="5a78a-128">Run the ALTER RESOURCE GOVERNOR RECONFIGURE statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="5a78a-129">Ejemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="5a78a-129">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="5a78a-130">El siguiente ejemplo crea un grupo de cargas de trabajo denominado `groupAdhoc` en el grupo de recursos de servidor denominado `poolAdhoc`.</span><span class="sxs-lookup"><span data-stu-id="5a78a-130">The following example creates a workload group named `groupAdhoc` in the resource pool named `poolAdhoc`.</span></span>  
  
```  
CREATE WORKLOAD GROUP groupAdhoc  
USING poolAdhoc;  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="5a78a-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5a78a-131">See Also</span></span>  
 <span data-ttu-id="5a78a-132">[Regulador de recursos](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="5a78a-132">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="5a78a-133">[Habilitar el regulador de recursos](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="5a78a-133">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="5a78a-134">[Crear un grupo de recursos de servidor](create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="5a78a-134">[Create a Resource Pool](create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="5a78a-135">[Cambiar la configuración del grupo de cargas de trabajo](change-workload-group-settings.md) </span><span class="sxs-lookup"><span data-stu-id="5a78a-135">[Change Workload Group Settings](change-workload-group-settings.md) </span></span>  
 <span data-ttu-id="5a78a-136">[Crear y probar una función clasificadora definida por el usuario](create-and-test-a-classifier-user-defined-function.md) </span><span class="sxs-lookup"><span data-stu-id="5a78a-136">[Create and Test a Classifier User-Defined Function](create-and-test-a-classifier-user-defined-function.md) </span></span>  
 <span data-ttu-id="5a78a-137">[CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5a78a-137">[CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql) </span></span>  
 [<span data-ttu-id="5a78a-138">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5a78a-138">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
