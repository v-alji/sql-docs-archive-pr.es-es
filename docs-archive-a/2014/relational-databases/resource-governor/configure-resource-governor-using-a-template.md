---
title: Configuración del regulador de recursos utilizando una plantilla | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, templates
ms.assetid: f342dec2-d1d6-483e-b44e-98eb7d168b5e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 62edb23cf55a953cb0fef54f002f8eaaa16f58ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676461"
---
# <a name="configure-resource-governor-using-a-template"></a><span data-ttu-id="b2e0f-102">Configurar el regulador de recursos utilizando una plantilla</span><span class="sxs-lookup"><span data-stu-id="b2e0f-102">Configure Resource Governor Using a Template</span></span>
  <span data-ttu-id="b2e0f-103">Puede configurar el regulador de recursos utilizando una plantilla que se proporciona en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2e0f-103">You can configure Resource Governor by using a template that is provided in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="b2e0f-104">**Antes de empezar:**  [Permisos](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="b2e0f-104">**Before you begin:**  [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="b2e0f-105">**Para crear un grupo de cargas de trabajo mediante:** [una plantilla](#ConfRGTemplate)</span><span class="sxs-lookup"><span data-stu-id="b2e0f-105">**To create a workload group, using:**  [a template](#ConfRGTemplate)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b2e0f-106">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="b2e0f-106">Before You Begin</span></span>  
 <span data-ttu-id="b2e0f-107">Siga los pasos que se detallan a continuación para abrir y modificar una plantilla que crea un grupo de recursos de servidor y un grupo de cargas de trabajo para el grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="b2e0f-107">Use the following steps to open and modify a template that creates a resource pool and a workload group for the pool.</span></span> <span data-ttu-id="b2e0f-108">Además, esta plantilla le permite crear una función clasificadora definida por el usuario que enruta las nuevas conexiones al grupo predeterminado o al grupo de cargas de trabajo que está creando.</span><span class="sxs-lookup"><span data-stu-id="b2e0f-108">In addition, this template enables you to create a classifier user-defined function that routes new connections to either the default group or the workload group that you create.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b2e0f-109">Permisos</span><span class="sxs-lookup"><span data-stu-id="b2e0f-109">Permissions</span></span>  
 <span data-ttu-id="b2e0f-110">Las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] del regulador de recursos de la plantilla requieren el permiso CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="b2e0f-110">The resource governor [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the template require CONTROL SERVER permission.</span></span>  
  
##  <a name="configure-resource-governor-using-a-template"></a><a name="ConfRGTemplate"></a> <span data-ttu-id="b2e0f-111">Configurar el regulador de recursos utilizando una plantilla</span><span class="sxs-lookup"><span data-stu-id="b2e0f-111">Configure Resource Governor Using a Template</span></span>  
 <span data-ttu-id="b2e0f-112">**Para configurar el regulador de recursos utilizando una plantilla en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="b2e0f-112">**To configure resource governor by using a template in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span></span>  
  
1.  <span data-ttu-id="b2e0f-113">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], en el menú **Ver** , haga clic en el **Explorador de plantillas**.</span><span class="sxs-lookup"><span data-stu-id="b2e0f-113">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="b2e0f-114">En **Explorador de plantillas**, expanda **Regulador de recursos**y, luego, haga doble clic en **Configurar regulador de recursos**.</span><span class="sxs-lookup"><span data-stu-id="b2e0f-114">In **Template Explorer**, expand **Resource Governor**, and then double-click **Configure Resource Governor**.</span></span>  
  
3.  <span data-ttu-id="b2e0f-115">En **Conectar al motor de base de datos**, escriba la información necesaria y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b2e0f-115">In **Connect to Database Engine**, enter the required information, and then click **OK**.</span></span> <span data-ttu-id="b2e0f-116">La plantilla Configure Resource Governor.sql se proporciona junto con el Editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="b2e0f-116">The template Configure Resource Governor.sql is provided in the Query Editor.</span></span> <span data-ttu-id="b2e0f-117">Utilice esta plantilla para crear y configurar un grupo de recursos de servidor, un grupo de cargas de trabajo y una función clasificadora.</span><span class="sxs-lookup"><span data-stu-id="b2e0f-117">Use this template to create and configure a resource pool, a workload group, and a classifier function.</span></span>  
  
4.  <span data-ttu-id="b2e0f-118">Para modificar los valores de la plantilla, pulse CTRL+MAYÚS+M.</span><span class="sxs-lookup"><span data-stu-id="b2e0f-118">To change the values in the template, press CTRL+SHIFT+M.</span></span> <span data-ttu-id="b2e0f-119">En el cuadro de diálogo **Especificar valores para parámetros de plantilla** , escriba los valores que desea utilizar.</span><span class="sxs-lookup"><span data-stu-id="b2e0f-119">In the **Specify Values for Template Parameters** window, enter the values that you want to use.</span></span>  
  
5.  <span data-ttu-id="b2e0f-120">Para guardar los cambios que realice en la plantilla, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b2e0f-120">To save the changes that you make to the template, click **OK**.</span></span>  
  
6.  <span data-ttu-id="b2e0f-121">Para ejecutar la consulta, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="b2e0f-121">To run the query, click **Execute**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2e0f-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b2e0f-122">See Also</span></span>  
 <span data-ttu-id="b2e0f-123">[Regulador de recursos](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="b2e0f-123">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="b2e0f-124">[Habilitar el regulador de recursos](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="b2e0f-124">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="b2e0f-125">[Grupo de recursos de servidor del regulador de recursos](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="b2e0f-125">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="b2e0f-126">[Grupos de cargas de trabajo del regulador de recursos](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="b2e0f-126">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="b2e0f-127">[Función clasificadora del regulador de recursos](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="b2e0f-127">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 <span data-ttu-id="b2e0f-128">[Ver las propiedades del regulador de recursos](view-resource-governor-properties.md) </span><span class="sxs-lookup"><span data-stu-id="b2e0f-128">[View Resource Governor Properties](view-resource-governor-properties.md) </span></span>  
 <span data-ttu-id="b2e0f-129">[CREATE RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b2e0f-129">[CREATE RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql) </span></span>  
 <span data-ttu-id="b2e0f-130">[CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b2e0f-130">[CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql) </span></span>  
 <span data-ttu-id="b2e0f-131">[CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b2e0f-131">[CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) </span></span>  
 [<span data-ttu-id="b2e0f-132">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b2e0f-132">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
