---
title: Creación de un grupo de recursos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- resource pools [SQL Server], create
- Resource Governor, resource pool create
ms.assetid: 44dd0567-a4c8-4c72-89ff-e76f6ddef344
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5abd2e60f4f9bb5290b47f95349782f8b26ad8bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677523"
---
# <a name="create-a-resource-pool"></a><span data-ttu-id="2cefd-102">Crear un grupo de recursos de servidor</span><span class="sxs-lookup"><span data-stu-id="2cefd-102">Create a Resource Pool</span></span>
  <span data-ttu-id="2cefd-103">Puede crear un grupo de recursos de servidor con [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2cefd-103">You can create a resource pool by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="2cefd-104">**Antes de empezar:**  [Limitaciones y restricciones](#LimitationsRestrictions), [Permisos](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="2cefd-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="2cefd-105">**Para crear un grupo de recursos de servidor con:**  [SQL Server Management Studio](#CreRPProp), [Transact-SQL](#CreRPTSQL)</span><span class="sxs-lookup"><span data-stu-id="2cefd-105">**To create a resource pool, using:**  [SQL Server Management Studio](#CreRPProp), [Transact-SQL](#CreRPTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2cefd-106">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="2cefd-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="2cefd-107">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="2cefd-107">Limitations and Restrictions</span></span>  
 <span data-ttu-id="2cefd-108">El porcentaje máximo de uso de la CPU debe ser igual o superior al porcentaje mínimo de uso de la CPU.</span><span class="sxs-lookup"><span data-stu-id="2cefd-108">The maximum CPU percentage must be equal to or higher than the minimum CPU percentage.</span></span> <span data-ttu-id="2cefd-109">El porcentaje máximo de uso de memoria debe ser igual o superior al porcentaje mínimo de uso de memoria.</span><span class="sxs-lookup"><span data-stu-id="2cefd-109">The maximum memory percentage must be equal to or higher than the minimum memory percentage.</span></span>  
  
 <span data-ttu-id="2cefd-110">Las sumas de los porcentajes mínimos de uso de la CPU y los porcentajes mínimos de uso de memoria de todos los grupos de recursos de servidor no deben superar el 100 por cien.</span><span class="sxs-lookup"><span data-stu-id="2cefd-110">The sums of the minimum CPU percentages and minimum memory percentages for all resource pools must not exceed 100.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2cefd-111">Permisos</span><span class="sxs-lookup"><span data-stu-id="2cefd-111">Permissions</span></span>  
 <span data-ttu-id="2cefd-112">Para crear un grupo de recursos de servidor se requiere un permiso CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="2cefd-112">Creating a resource pool requires CONTROL SERVER permission.</span></span>  
  
##  <a name="create-a-resource-pool-using-sql-server-management-studio"></a><a name="CreRPProp"></a> <span data-ttu-id="2cefd-113">Crear un grupo de recursos de servidor mediante SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2cefd-113">Create a Resource Pool Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="2cefd-114">**Para crear un grupo de recursos de servidor con [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="2cefd-114">**To create a resource pool by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span></span>  
  
1.  <span data-ttu-id="2cefd-115">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], abra el Explorador de objetos y expanda de forma recursiva el nodo **Administración** hasta e incluyendo el nodo **Regulador de recursos**.</span><span class="sxs-lookup"><span data-stu-id="2cefd-115">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to and including **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="2cefd-116">Haga clic con el botón derecho en **Regulador de recursos**y, luego, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2cefd-116">Right-click **Resource Governor**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="2cefd-117">En la cuadrícula **Grupos de recursos de servidor** , haga clic en la primera columna de la fila vacía.</span><span class="sxs-lookup"><span data-stu-id="2cefd-117">In the **Resource pools** grid, click the first column in the empty row.</span></span> <span data-ttu-id="2cefd-118">Esta columna tiene como etiqueta un asterisco (\*).</span><span class="sxs-lookup"><span data-stu-id="2cefd-118">This column is labeled with an asterisk (\*).</span></span>  
  
4.  <span data-ttu-id="2cefd-119">Haga doble clic en la celda vacía de la columna **Nombre** .</span><span class="sxs-lookup"><span data-stu-id="2cefd-119">Double-click the empty cell in the **Name** column.</span></span> <span data-ttu-id="2cefd-120">Escriba el nombre que desee utilizar con el grupo de recursos de servidor.</span><span class="sxs-lookup"><span data-stu-id="2cefd-120">Type in the name that you want to use for the resource pool.</span></span>  
  
5.  <span data-ttu-id="2cefd-121">Haga clic o doble clic en cualquier otra celda de la fila que desea cambiar, y especifique los nuevos valores.</span><span class="sxs-lookup"><span data-stu-id="2cefd-121">Click or double-click any other cells in the row you want to change, and enter the new values.</span></span>  
  
6.  <span data-ttu-id="2cefd-122">Haga clic en **Aceptar**para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="2cefd-122">To save the changes, click **OK**</span></span>  
  
##  <a name="create-a-resource-pool-using-transact-sql"></a><a name="CreRPTSQL"></a> <span data-ttu-id="2cefd-123">Crear un grupo de recursos de servidor mediante Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2cefd-123">Create a Resource Pool Using Transact-SQL</span></span>  
 <span data-ttu-id="2cefd-124">**Para crear un grupo de recursos de servidor con [!INCLUDE[tsql](../../includes/tsql-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="2cefd-124">**To create a resource pool by using [!INCLUDE[tsql](../../includes/tsql-md.md)]**</span></span>  
  
1.  <span data-ttu-id="2cefd-125">Ejecute la instrucción `CREATE RESOURCE POOL` especificando los valores de propiedad que desea establecer.</span><span class="sxs-lookup"><span data-stu-id="2cefd-125">Run the `CREATE RESOURCE POOL` statement specifying the property values to be set.</span></span>  
  
2.  <span data-ttu-id="2cefd-126">Ejecute la instrucción **ALTER RESOURCE GOVERNOR RECONFIGURE** .</span><span class="sxs-lookup"><span data-stu-id="2cefd-126">Run the **ALTER RESOURCE GOVERNOR RECONFIGURE** statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="2cefd-127">Ejemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="2cefd-127">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="2cefd-128">En el ejemplo siguiente se crea un grupo de recursos de servidor denominado `poolAdhoc`.</span><span class="sxs-lookup"><span data-stu-id="2cefd-128">The following example creates a resource pool named `poolAdhoc`.</span></span>  
  
```  
CREATE RESOURCE POOL poolAdhoc  
WITH (MAX_CPU_PERCENT = 20);  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="2cefd-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2cefd-129">See Also</span></span>  
 <span data-ttu-id="2cefd-130">[Regulador de recursos](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="2cefd-130">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="2cefd-131">[Habilitar el regulador de recursos](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="2cefd-131">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="2cefd-132">[Grupo de recursos de servidor del regulador de recursos](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="2cefd-132">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="2cefd-133">[Cambiar la configuración del grupo de recursos de servidor](change-resource-pool-settings.md) </span><span class="sxs-lookup"><span data-stu-id="2cefd-133">[Change Resource Pool Settings](change-resource-pool-settings.md) </span></span>  
 <span data-ttu-id="2cefd-134">[Eliminar un grupo de recursos de servidor](delete-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="2cefd-134">[Delete a Resource Pool](delete-a-resource-pool.md) </span></span>  
 <span data-ttu-id="2cefd-135">[Configurar el regulador de recursos utilizando una plantilla](configure-resource-governor-using-a-template.md) </span><span class="sxs-lookup"><span data-stu-id="2cefd-135">[Configure Resource Governor Using a Template](configure-resource-governor-using-a-template.md) </span></span>  
 <span data-ttu-id="2cefd-136">[Grupos de cargas de trabajo del regulador de recursos](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="2cefd-136">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="2cefd-137">[Función clasificadora del regulador de recursos](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="2cefd-137">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 <span data-ttu-id="2cefd-138">[CREATE RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2cefd-138">[CREATE RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql) </span></span>  
 [<span data-ttu-id="2cefd-139">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2cefd-139">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
