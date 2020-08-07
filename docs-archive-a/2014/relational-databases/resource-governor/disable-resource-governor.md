---
title: Deshabilitar el regulador de recursos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, disabling
ms.assetid: 2c2d2db0-34a5-4f50-b783-17693e3ce3f1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 172f01bdde0f792cd9ed72ad371e5811b8de8885
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745696"
---
# <a name="disable-resource-governor"></a><span data-ttu-id="91020-102">Deshabilitar el regulador de recursos</span><span class="sxs-lookup"><span data-stu-id="91020-102">Disable Resource Governor</span></span>
  <span data-ttu-id="91020-103">Puede deshabilitar el regulador de recursos utilizando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="91020-103">You can disable the Resource Governor by using either [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Transact-SQL.</span></span>  
  
-   <span data-ttu-id="91020-104">**Antes de empezar:**  [Limitaciones y restricciones](#LimitationsRestrictions), [Permisos](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="91020-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="91020-105">**Para deshabilitar Resource Governor con:**  [Explorador de objetos](#RGOffObjEx), [Propiedades de Resource Governor](#RGOffProp), [Transact-SQL](#RGOffTSQL)</span><span class="sxs-lookup"><span data-stu-id="91020-105">**To disable Resource Governorn, using:**  [Object Explorer](#RGOffObjEx), [Resource Governor Properties](#RGOffProp), [Transact-SQL](#RGOffTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="91020-106">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="91020-106">Before You Begin</span></span>  
 <span data-ttu-id="91020-107">Deshabilitar el regulador de recursos tiene como consecuencia lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="91020-107">Disabling the Resource Governor has the following results:</span></span>  
  
-   <span data-ttu-id="91020-108">No se ejecuta la función clasificadora.</span><span class="sxs-lookup"><span data-stu-id="91020-108">The classifier function is not run.</span></span>  
  
-   <span data-ttu-id="91020-109">Todas las conexiones nuevas se clasifican automáticamente en el grupo de carga de trabajo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="91020-109">All new connections are automatically classified into the default workload group.</span></span>  
  
-   <span data-ttu-id="91020-110">Las solicitudes iniciadas por el sistema se clasifican en el grupo de cargas de trabajo interno.</span><span class="sxs-lookup"><span data-stu-id="91020-110">System-initiated requests are classified into the internal workload group.</span></span>  
  
-   <span data-ttu-id="91020-111">Se restablecen los valores predeterminados de todas las configuraciones existentes del grupo de cargas de trabajo y el grupo de recursos de servidor.</span><span class="sxs-lookup"><span data-stu-id="91020-111">All existing workload group and resource pool settings are reset to their default values.</span></span> <span data-ttu-id="91020-112">En este caso, no se desencadena ningún evento cuando se alcanzan los límites.</span><span class="sxs-lookup"><span data-stu-id="91020-112">In this case, no events are fired when limits are reached.</span></span>  
  
-   <span data-ttu-id="91020-113">La supervisión normal del sistema no resulta afectada.</span><span class="sxs-lookup"><span data-stu-id="91020-113">Normal system monitoring is not affected.</span></span>  
  
-   <span data-ttu-id="91020-114">Se puede cambiar la configuración, pero los cambios no surtirán efecto hasta que se habilite el regulador de recursos.</span><span class="sxs-lookup"><span data-stu-id="91020-114">Configuration changes can be made, but the changes do not take effect until the Resource Governor is enabled.</span></span>  
  
-   <span data-ttu-id="91020-115">Al reiniciar SQL Server, el regulador de recursos no cargará su configuración, sino que tendrá únicamente los grupos de cargas de trabajo y los grupos de recursos de servidor predeterminados e internos.</span><span class="sxs-lookup"><span data-stu-id="91020-115">Upon restarting SQL Server, the Resource Governor will not load its configuration, but instead will have only the default and internal workload groups and resource pools.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="91020-116">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="91020-116">Limitations and Restrictions</span></span>  
 <span data-ttu-id="91020-117">No puede utilizar la instrucción `ALTER RESOURCE GOVERNOR` para deshabilitar el regulador de recursos durante una transacción del usuario.</span><span class="sxs-lookup"><span data-stu-id="91020-117">You cannot use the `ALTER RESOURCE GOVERNOR` statement to disable Resource Governor when in a user transaction.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="91020-118">Permisos</span><span class="sxs-lookup"><span data-stu-id="91020-118">Permissions</span></span>  
 <span data-ttu-id="91020-119">Deshabilitar el regulador de recursos requiere el permiso CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="91020-119">Disabling the Resource Governor requires CONTROL SERVER permission.</span></span>  
  
##  <a name="disable-resource-governor-using-object-explorer"></a><a name="RGOffObjEx"></a> <span data-ttu-id="91020-120">Deshabilitar el regulador de recursos mediante el Explorador de objetos</span><span class="sxs-lookup"><span data-stu-id="91020-120">Disable Resource Governor Using Object Explorer</span></span>  
 <span data-ttu-id="91020-121">**Para deshabilitar el regulador de recursos utilizando el Explorador de objetos**</span><span class="sxs-lookup"><span data-stu-id="91020-121">**To disable the Resource Governor by using Object Explorer**</span></span>  
  
1.  <span data-ttu-id="91020-122">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], abra el Explorador de objetos y expanda de forma recursiva el nodo **Administración** hasta el nodo **Regulador de recursos**.</span><span class="sxs-lookup"><span data-stu-id="91020-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="91020-123">Haga clic con el botón derecho en **Regulador de recursos**y, luego, haga clic en **Deshabilitar**.</span><span class="sxs-lookup"><span data-stu-id="91020-123">Right-click **Resource Governor**, and then click **Disable**.</span></span>  
  
##  <a name="disable-resource-governor-using-resource-governor-properties"></a><a name="RGOffProp"></a> <span data-ttu-id="91020-124">Deshabilitar el regulador de recursos mediante Propiedades del regulador de recursos</span><span class="sxs-lookup"><span data-stu-id="91020-124">Disable Resource Governor Using Resource Governor Properties</span></span>  
 <span data-ttu-id="91020-125">**Para deshabilitar el regulador de recursos mediante la página Propiedades del regulador de recursos**</span><span class="sxs-lookup"><span data-stu-id="91020-125">**To disable the Resource Governor by using the Resource Governor Properties page**</span></span>  
  
1.  <span data-ttu-id="91020-126">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], abra el Explorador de objetos y expanda de forma recursiva el nodo **Administración** hasta el nodo **Regulador de recursos**.</span><span class="sxs-lookup"><span data-stu-id="91020-126">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="91020-127">Haga clic con el botón derecho en **Regulador de recursos** y, luego, haga clic en **Propiedades**. De este modo se abre la página **Propiedades del regulador de recursos** .</span><span class="sxs-lookup"><span data-stu-id="91020-127">Right-click **Resource Governor** and then click **Properties**, this opens the **Resource Governor Properties** page.</span></span>  
  
3.  <span data-ttu-id="91020-128">Haga clic en la casilla **Habilitar regulador de recursos** , asegúrese de que la casilla no está activada, y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="91020-128">Click the **Enable Resource Governor** check box, ensure that the box is not selected, and then click **OK**.</span></span>  
  
##  <a name="disable-resource-governor-using-transact-sql"></a><a name="RGOffTSQL"></a> <span data-ttu-id="91020-129">Deshabilitar el regulador de recursos mediante Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="91020-129">Disable Resource Governor Using Transact-SQL</span></span>  
 <span data-ttu-id="91020-130">**Para deshabilitar el regulador de recursos mediante Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="91020-130">**To disable the Resource Governor by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="91020-131">Ejecute la instrucción **ALTER RESOURCE GOVERNOR DISABLE** .</span><span class="sxs-lookup"><span data-stu-id="91020-131">Run the **ALTER RESOURCE GOVERNOR DISABLE** statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="91020-132">Ejemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="91020-132">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="91020-133">En el ejemplo siguiente se habilita el regulador de recursos.</span><span class="sxs-lookup"><span data-stu-id="91020-133">The following example enables the Resource Governor.</span></span>  
  
```  
ALTER RESOURCE GOVERNOR DISABLE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="91020-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="91020-134">See Also</span></span>  
 <span data-ttu-id="91020-135">[Regulador de recursos](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="91020-135">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="91020-136">[Habilitar el regulador de recursos](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="91020-136">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="91020-137">[Grupo de recursos de servidor del regulador de recursos](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="91020-137">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="91020-138">[Grupos de cargas de trabajo del regulador de recursos](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="91020-138">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="91020-139">[Función clasificadora del regulador de recursos](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="91020-139">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 [<span data-ttu-id="91020-140">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="91020-140">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
