---
title: Habilitar el regulador de recursos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, enabling
ms.assetid: 4d17af53-cf11-4ce4-aab4-deda94a49836
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7b1b0f780457aa5a4d26cbb463c9f31a94185f0d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745694"
---
# <a name="enable-resource-governor"></a><span data-ttu-id="bd2df-102">Habilitar el regulador de recursos</span><span class="sxs-lookup"><span data-stu-id="bd2df-102">Enable Resource Governor</span></span>
  <span data-ttu-id="bd2df-103">El regulador de recursos está desactivado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="bd2df-103">The Resource Governor is turned off by default.</span></span> <span data-ttu-id="bd2df-104">Puede habilitar el regulador de recursos utilizando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="bd2df-104">You can enable the Resource Governor by using either [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Transact-SQL.</span></span>  
  
-   <span data-ttu-id="bd2df-105">**Antes de empezar:**  [Limitaciones y restricciones](#LimitationsRestrictions), [Permisos](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="bd2df-105">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="bd2df-106">**Para habilitar Resource Governor, mediante:**  [Explorador de objetos](#RGOnObjEx), [Propiedades de Resource Governor](#RGOnProp), [Transact-SQL](#RGOnTSQL)</span><span class="sxs-lookup"><span data-stu-id="bd2df-106">**To enable Resource Governorn, using:**  [Object Explorer](#RGOnObjEx), [Resource Governor Properties](#RGOnProp), [Transact-SQL](#RGOnTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="bd2df-107">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="bd2df-107">Before You Begin</span></span>  
 <span data-ttu-id="bd2df-108">Habilitar el regulador de recursos tiene como consecuencia lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bd2df-108">Enabling the resource governor has the following results:</span></span>  
  
-   <span data-ttu-id="bd2df-109">La función clasificadora se ejecuta para las nuevas conexiones, de forma que se pueden asignar sus cargas de trabajo a los grupos de cargas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bd2df-109">The classifier function is run for new connections so that their workloads can be assigned to workload groups.</span></span>  
  
-   <span data-ttu-id="bd2df-110">Se respetan y se aplican los límites de los recursos especificados en la configuración del regulador de recursos.</span><span class="sxs-lookup"><span data-stu-id="bd2df-110">The resource limits that are specified in the Resource Governor configuration are honored and enforced.</span></span>  
  
-   <span data-ttu-id="bd2df-111">Las solicitudes que existieran antes de habilitar el regulador de recursos resultarán afectadas por cualquier cambio realizado en la configuración en el momento de deshabilitar el regulador de recursos.</span><span class="sxs-lookup"><span data-stu-id="bd2df-111">Requests that existed before enabling Resource Governor are affected by any configuration changes that were made when the Resource Governor was disabled.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="bd2df-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="bd2df-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="bd2df-113">No puede utilizar la instrucción `ALTER RESOURCE GOVERNOR` para habilitar el regulador de recursos durante una transacción del usuario.</span><span class="sxs-lookup"><span data-stu-id="bd2df-113">You cannot use the `ALTER RESOURCE GOVERNOR` statement to enable Resource Governor when in a user transaction.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="bd2df-114">Permisos</span><span class="sxs-lookup"><span data-stu-id="bd2df-114">Permissions</span></span>  
 <span data-ttu-id="bd2df-115">Habilitar el regulador de recursos requiere el permiso CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="bd2df-115">Enabling the Resource Governor requires CONTROL SERVER permission.</span></span>  
  
##  <a name="enable-resource-governor-using-object-explorer"></a><a name="RGOnObjEx"></a> <span data-ttu-id="bd2df-116">Habilitar el regulador de recursos mediante el Explorador de objetos</span><span class="sxs-lookup"><span data-stu-id="bd2df-116">Enable Resource Governor Using Object Explorer</span></span>  
 <span data-ttu-id="bd2df-117">**Para habilitar el regulador de recursos utilizando el Explorador de objetos**</span><span class="sxs-lookup"><span data-stu-id="bd2df-117">**To enable the Resource Governor by using Object Explorer**</span></span>  
  
1.  <span data-ttu-id="bd2df-118">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], abra el Explorador de objetos y expanda de forma recursiva el nodo **Administración** hasta el nodo **Regulador de recursos**.</span><span class="sxs-lookup"><span data-stu-id="bd2df-118">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="bd2df-119">Haga clic con el botón derecho en **Regulador de recursos**y luego haga clic en **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="bd2df-119">Right-click **Resource Governor**, and then click **Enable**.</span></span>  
  
##  <a name="enable-resource-governor-using-resource-governor-properties"></a><a name="RGOnProp"></a> <span data-ttu-id="bd2df-120">Habilitar el regulador de recursos mediante Propiedades del regulador de recursos</span><span class="sxs-lookup"><span data-stu-id="bd2df-120">Enable Resource Governor Using Resource Governor Properties</span></span>  
 <span data-ttu-id="bd2df-121">**Para habilitar el regulador de recursos mediante la página Propiedades del regulador de recursos**</span><span class="sxs-lookup"><span data-stu-id="bd2df-121">**To enable the Resource Governor by using the Resource Governor Properties page**</span></span>  
  
1.  <span data-ttu-id="bd2df-122">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], abra el Explorador de objetos y expanda de forma recursiva el nodo **Administración** hasta el nodo **Regulador de recursos**.</span><span class="sxs-lookup"><span data-stu-id="bd2df-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="bd2df-123">Haga clic con el botón derecho en **Regulador de recursos** y, luego, haga clic en **Propiedades**. De este modo se abre la página **Propiedades del regulador de recursos** .</span><span class="sxs-lookup"><span data-stu-id="bd2df-123">Right-click **Resource Governor** and then click **Properties**, this opens the **Resource Governor Properties** page.</span></span>  
  
3.  <span data-ttu-id="bd2df-124">Haga clic en la casilla **Habilitar regulador de recursos** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bd2df-124">Click the **Enable Resource Governor** check box, and then click **OK**.</span></span>  
  
##  <a name="enable-resource-governor-using-transact-sql"></a><a name="RGOnTSQL"></a> <span data-ttu-id="bd2df-125">Habilitar el regulador de recursos mediante Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bd2df-125">Enable Resource Governor Using Transact-SQL</span></span>  
 <span data-ttu-id="bd2df-126">**Para habilitar el regulador de recursos mediante Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="bd2df-126">**To enable the Resource Governor by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="bd2df-127">Ejecute la instrucción **ALTER RESOURCE GOVERNOR RECONFIGURE** .</span><span class="sxs-lookup"><span data-stu-id="bd2df-127">Run the **ALTER RESOURCE GOVERNOR RECONFIGURE** statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="bd2df-128">Ejemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="bd2df-128">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="bd2df-129">En el ejemplo siguiente se habilita el regulador de recursos.</span><span class="sxs-lookup"><span data-stu-id="bd2df-129">The following example enables the Resource Governor.</span></span>  
  
```  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="bd2df-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bd2df-130">See Also</span></span>  
 <span data-ttu-id="bd2df-131">[Regulador de recursos](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="bd2df-131">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="bd2df-132">[Deshabilitar el regulador de recursos](disable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="bd2df-132">[Disable Resource Governor](disable-resource-governor.md) </span></span>  
 <span data-ttu-id="bd2df-133">[Grupo de recursos de servidor del regulador de recursos](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="bd2df-133">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="bd2df-134">[Grupos de cargas de trabajo del regulador de recursos](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="bd2df-134">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="bd2df-135">[Función clasificadora del regulador de recursos](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="bd2df-135">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 [<span data-ttu-id="bd2df-136">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bd2df-136">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
