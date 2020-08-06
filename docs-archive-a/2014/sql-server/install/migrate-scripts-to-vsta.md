---
title: Migrar scripts a VSTA | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- SSIS Script task, converting scripts
- Script component [Integration Services], converting scripts
- Script task [Integration Services], converting scripts
- SSIS Script component, converting scripts
ms.assetid: d685098b-86a1-46bf-939a-63d56951e009
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: afbc19c35f99a5abc5a6ebd92024e42baa6a9237
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749598"
---
# <a name="migrate-scripts-to-vsta"></a><span data-ttu-id="228f0-102">Migrar scripts a VSTA</span><span class="sxs-lookup"><span data-stu-id="228f0-102">Migrate Scripts to VSTA</span></span>
  <span data-ttu-id="228f0-103">Al actualizar [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] paquetes a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] migra los scripts de las tareas script o los componentes script a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span><span class="sxs-lookup"><span data-stu-id="228f0-103">When you upgrade [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] packages to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] migrates the scripts in any Script tasks or Script components to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span></span> <span data-ttu-id="228f0-104">VSTA es el entorno de script que [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usa.</span><span class="sxs-lookup"><span data-stu-id="228f0-104">VSTA is the scripting environment that [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] uses.</span></span> <span data-ttu-id="228f0-105">En [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , el entorno de scripting para [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] es [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] para aplicaciones (VSA).</span><span class="sxs-lookup"><span data-stu-id="228f0-105">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], the scripting environment for [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] is [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] for Applications (VSA).</span></span>  
  
 <span data-ttu-id="228f0-106">Si los scripts en las tareas Script o los componentes Script hacen referencia a las interfaces, podría tener que modificar esas referencias antes de actualizar el paquete.</span><span class="sxs-lookup"><span data-stu-id="228f0-106">If the scripts in either the Script tasks or Script components reference interfaces, you might have to modify those references before you upgrade the package.</span></span> <span data-ttu-id="228f0-107">De lo contrario, el paquete no se podrá actualizar o los scripts no se podrán validar, dependiendo del método de actualización que use.</span><span class="sxs-lookup"><span data-stu-id="228f0-107">Otherwise, the package will not be upgraded or the scripts will not be validated, depending on the upgrade method that you use.</span></span> <span data-ttu-id="228f0-108">Para modificar estas referencias, reemplace las referencias a las interfaces IDTS*xxx*90 por referencias a las interfaces IDTS*XXX*100 correspondientes.</span><span class="sxs-lookup"><span data-stu-id="228f0-108">To modify these references, replace references to IDTS*xxx*90 interfaces with references to the corresponding IDTS*xxx*100 interfaces.</span></span>  
  
 <span data-ttu-id="228f0-109">Para obtener más información sobre cómo migrar scripts y actualizar paquetes, vea [actualizar paquetes de Integration Services](../../integration-services/install-windows/upgrade-integration-services-packages.md).</span><span class="sxs-lookup"><span data-stu-id="228f0-109">For more information about how to migrate scripts and upgrade packages, see [Upgrade Integration Services Packages](../../integration-services/install-windows/upgrade-integration-services-packages.md).</span></span>  
  
## <a name="understanding-migration-failures"></a><span data-ttu-id="228f0-110">Descripción de los errores de migración</span><span class="sxs-lookup"><span data-stu-id="228f0-110">Understanding Migration Failures</span></span>  
 <span data-ttu-id="228f0-111">Al migrar los scripts, se puede producir un error en la migración debido a una de las razones siguientes:</span><span class="sxs-lookup"><span data-stu-id="228f0-111">When you migrate the scripts, the migration can fail because of one of the following reasons:</span></span>  
  
-   <span data-ttu-id="228f0-112">Se cambió el nombre del punto de entrada para el script de VSA.</span><span class="sxs-lookup"><span data-stu-id="228f0-112">The entry point for the VSA script was renamed.</span></span>  
  
     <span data-ttu-id="228f0-113">El punto de entrada especifica el método en la clase `ScriptMain` en el proyecto de VSTA que el tiempo de ejecución de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] llama como punto de entrada al código de la tarea Script.</span><span class="sxs-lookup"><span data-stu-id="228f0-113">The entry point specifies the method in the `ScriptMain` class in the VSTA project that the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] runtime calls as the entry point into the Script task code.</span></span> <span data-ttu-id="228f0-114">La clase `ScriptMain` es la clase predeterminada que las plantillas de script generan.</span><span class="sxs-lookup"><span data-stu-id="228f0-114">The `ScriptMain` class is the default class that the script templates generate.</span></span>  
  
-   <span data-ttu-id="228f0-115">No hay ningún punto de entrada o hay varios en el script de VSA.</span><span class="sxs-lookup"><span data-stu-id="228f0-115">There is no entry point or there are multiple entry points in the VSA script.</span></span>  
  
-   <span data-ttu-id="228f0-116">No se pudieron agregar referencias de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="228f0-116">Assembly references could not be added.</span></span>  
  
-   <span data-ttu-id="228f0-117">Se modificó la clase `ScriptMain` para heredar de otras clases además de la clase `ScriptObjectModelSSIS`.</span><span class="sxs-lookup"><span data-stu-id="228f0-117">The `ScriptMain` class was modified to inherit from other classes in addition to the `ScriptObjectModelSSIS` class.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="228f0-118">no [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] admite la herencia múltiple.</span><span class="sxs-lookup"><span data-stu-id="228f0-118">[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] does not support multiple inheritance.</span></span>  
  
 <span data-ttu-id="228f0-119">No se puede convertir un script de VSA que use [!INCLUDE[vbprvblong](../../includes/vbprvblong-md.md)] en un script de VSTA que use [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csharp_orcas_long](../../includes/csharp-orcas-long-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="228f0-119">You cannot convert a VSA script that uses [!INCLUDE[vbprvblong](../../includes/vbprvblong-md.md)] to a VSTA script that uses [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csharp_orcas_long](../../includes/csharp-orcas-long-md.md)].</span></span> <span data-ttu-id="228f0-120">Sin embargo, puede crear un nuevo script de VSTA que use [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csharp_orcas_long](../../includes/csharp-orcas-long-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="228f0-120">However, you can create a new VSTA script that uses [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csharp_orcas_long](../../includes/csharp-orcas-long-md.md)].</span></span> <span data-ttu-id="228f0-121">Para obtener más información, consulte [Codificar y depurar la tarea Script](../../integration-services/control-flow/script-task.md) y [Codificar y depurar el componente de script](../../integration-services/data-flow/transformations/script-component.md).</span><span class="sxs-lookup"><span data-stu-id="228f0-121">For more information, see [Coding and Debugging the Script Task](../../integration-services/control-flow/script-task.md) and [Coding and Debugging the Script Component](../../integration-services/data-flow/transformations/script-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="228f0-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="228f0-122">See Also</span></span>  
 [<span data-ttu-id="228f0-123">Ampliar paquetes con scripting</span><span class="sxs-lookup"><span data-stu-id="228f0-123">Extending Packages with Scripting</span></span>](../../relational-databases/server-management-objects-smo/tasks/scripting.md)  
  
  
