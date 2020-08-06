---
title: Cuadro de diálogo Crear nueva directiva o Abrir directiva, página General | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.newgroup.f1
- sql12.swb.dmf.policy.f1
- sql12.swb.dmf.policy.filter.f1
ms.assetid: c00bebd0-d04b-4c64-840e-8b7a2c603436
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4b67cb8faf18001b841824b806e7befc0683d457
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671013"
---
# <a name="create-new-policy-or-open-policy-dialog-box-general-page"></a><span data-ttu-id="82e21-102">Cuadro de diálogo Crear nueva directiva o Abrir directiva, página General</span><span class="sxs-lookup"><span data-stu-id="82e21-102">Create New Policy or Open Policy Dialog Box, General Page</span></span>
  <span data-ttu-id="82e21-103">Utilice este cuadro de diálogo para crear una directiva nueva de administración basada en directivas o modificar una directiva existente.</span><span class="sxs-lookup"><span data-stu-id="82e21-103">Use this dialog box to create a new Policy-Based Management policy or modify an existing policy.</span></span> <span data-ttu-id="82e21-104">Utilice las áreas **Para destinos** y **Restricción de servidor** como filtro para limitar las directivas a un subconjunto de todos los destinos posibles.</span><span class="sxs-lookup"><span data-stu-id="82e21-104">Use the **Against targets** and **Server restriction** areas as a filter to limit policies to a subset of all possible targets.</span></span> <span data-ttu-id="82e21-105">Las condiciones que se usan como filtros de destino se deben definir en una faceta física y no deben contener funciones ni el operador LIKE.</span><span class="sxs-lookup"><span data-stu-id="82e21-105">For conditions to be used as target filters, they must be defined on a physical facet, must not contain functions, and must not contain the LIKE operator.</span></span> <span data-ttu-id="82e21-106">Cuando el sistema calcula el conjunto de objetos para una directiva, los objetos del sistema se excluyen de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="82e21-106">When the system computes the object set for a policy, by default the system objects are excluded.</span></span>  <span data-ttu-id="82e21-107">Por ejemplo, si el conjunto de objetos de la directiva hace referencia a todas las tablas, la directiva no se aplicará a las tablas del sistema.</span><span class="sxs-lookup"><span data-stu-id="82e21-107">For example, if the object set of the policy refers to all tables, the policy will not apply to system tables.</span></span> <span data-ttu-id="82e21-108">Si los usuarios desean evaluar una directiva con los objetos del sistema, pueden agregar explícitamente objetos del sistema al conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="82e21-108">If users want to evaluate a policy against system objects, they can explicitly add system objects to the object set.</span></span> <span data-ttu-id="82e21-109">Sin embargo, aunque se admiten todas las directivas para el modo de evaluación **Comprobar en la programación** , por razones de rendimiento, no todas las directivas con conjuntos de objetos arbitrarios se admiten para el modo de evaluación **Comprobar en los cambios** .</span><span class="sxs-lookup"><span data-stu-id="82e21-109">However, though all policies are supported for **check on schedule** evaluation mode, for performance reason, not all policies with arbitrary object sets are supported for **check on change** evaluation mode.</span></span> <span data-ttu-id="82e21-110">Para obtener más información, consulte: [https://blogs.msdn.com/b/sqlpbm/archive/2009/04/13/policy-evaluation-modes.aspx](https://blogs.msdn.com/b/sqlpbm/archive/2009/04/13/policy-evaluation-modes.aspx)</span><span class="sxs-lookup"><span data-stu-id="82e21-110">For more information, see [https://blogs.msdn.com/b/sqlpbm/archive/2009/04/13/policy-evaluation-modes.aspx](https://blogs.msdn.com/b/sqlpbm/archive/2009/04/13/policy-evaluation-modes.aspx)</span></span>  
  
## <a name="options"></a><span data-ttu-id="82e21-111">Opciones</span><span class="sxs-lookup"><span data-stu-id="82e21-111">Options</span></span>  
 <span data-ttu-id="82e21-112">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="82e21-112">**Name**</span></span>  
 <span data-ttu-id="82e21-113">Si la directiva es nueva, escriba un nombre para ella.</span><span class="sxs-lookup"><span data-stu-id="82e21-113">For a new policy, type the new policy name.</span></span> <span data-ttu-id="82e21-114">Si la directiva ya existe, se muestra el nombre.</span><span class="sxs-lookup"><span data-stu-id="82e21-114">For an existing policy, the name is displayed.</span></span>  
  
 <span data-ttu-id="82e21-115">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="82e21-115">**Enabled**</span></span>  
 <span data-ttu-id="82e21-116">Active la casilla **Habilitada** para habilitar la directiva.</span><span class="sxs-lookup"><span data-stu-id="82e21-116">Select the **Enabled** check box to enable the policy.</span></span> <span data-ttu-id="82e21-117">Desactive la casilla **Habilitada** para deshabilitar la directiva.</span><span class="sxs-lookup"><span data-stu-id="82e21-117">Clear the **Enabled** check box to disable the policy.</span></span> <span data-ttu-id="82e21-118">El cuadro **Habilitada** se aplica a la automatización de las directivas.</span><span class="sxs-lookup"><span data-stu-id="82e21-118">The **Enabled** box applies to policy automation.</span></span> <span data-ttu-id="82e21-119">Crea o quita el sistema de automatización para la directiva.</span><span class="sxs-lookup"><span data-stu-id="82e21-119">It creates or removes the automation system for the policy.</span></span> <span data-ttu-id="82e21-120">Automation utiliza los mecanismos siguientes:</span><span class="sxs-lookup"><span data-stu-id="82e21-120">Automation uses the following mechanisms:</span></span>  
  
 <span data-ttu-id="82e21-121">**Al cambiar: impedir**</span><span class="sxs-lookup"><span data-stu-id="82e21-121">**On change: prevent**</span></span>  
 <span data-ttu-id="82e21-122">Un desencadenador de base de datos exige la compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="82e21-122">A database trigger enforces compliance.</span></span>  
  
 <span data-ttu-id="82e21-123">**Al cambiar: solo registro**</span><span class="sxs-lookup"><span data-stu-id="82e21-123">**On change: log only**</span></span>  
 <span data-ttu-id="82e21-124">Un evento de servicios de notificación comprueba la compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="82e21-124">A notification services event checks for compliance.</span></span>  
  
 <span data-ttu-id="82e21-125">**Al programar**</span><span class="sxs-lookup"><span data-stu-id="82e21-125">**On schedule**</span></span>  
 <span data-ttu-id="82e21-126">Se crea un trabajo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para comprobar la compatibilidad según una programación.</span><span class="sxs-lookup"><span data-stu-id="82e21-126">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job is created to check for compliance on a schedule.</span></span>  
  
 <span data-ttu-id="82e21-127">Con las directivas que se ejecutan utilizando el modo de evaluación **A petición** no se usa esta casilla.</span><span class="sxs-lookup"><span data-stu-id="82e21-127">Policies that are run using **On demand** evaluation mode do not use this check box.</span></span>  
  
 <span data-ttu-id="82e21-128">**Condición de comprobación**</span><span class="sxs-lookup"><span data-stu-id="82e21-128">**Check condition**</span></span>  
 <span data-ttu-id="82e21-129">Seleccione la condición de la administración basada en directivas que esta directiva utiliza.</span><span class="sxs-lookup"><span data-stu-id="82e21-129">Select the Policy-Based Management condition that this policy uses.</span></span> <span data-ttu-id="82e21-130">Se enumeran todas las condiciones del servidor para la faceta de administración basada en directivas asociada.</span><span class="sxs-lookup"><span data-stu-id="82e21-130">All conditions on the server for the associated Policy-Based Management facet are listed.</span></span> <span data-ttu-id="82e21-131">Haga clic en **Nueva condición** para crear una condición nueva.</span><span class="sxs-lookup"><span data-stu-id="82e21-131">Click **New condition** to create a new condition.</span></span> <span data-ttu-id="82e21-132">Haga clic en el botón de puntos suspensivos ( **...** ) para modificar la condición.</span><span class="sxs-lookup"><span data-stu-id="82e21-132">Click the ellipsis (**...**) button to modify the condition.</span></span>  
  
 <span data-ttu-id="82e21-133">**Para destinos**</span><span class="sxs-lookup"><span data-stu-id="82e21-133">**Against targets**</span></span>  
 <span data-ttu-id="82e21-134">Seleccione los tipos de destino que están disponibles para que esta faceta complete una expresión de filtro.</span><span class="sxs-lookup"><span data-stu-id="82e21-134">Select the target types that are available for this facet to complete a filter expression.</span></span>  
  
 <span data-ttu-id="82e21-135">**Modo de evaluación**</span><span class="sxs-lookup"><span data-stu-id="82e21-135">**Evaluation Mode**</span></span>  
 <span data-ttu-id="82e21-136">Seleccione el modo de evaluación para la directiva.</span><span class="sxs-lookup"><span data-stu-id="82e21-136">Select the evaluation mode for the policy.</span></span> <span data-ttu-id="82e21-137">Algunas directivas se pueden comprobar pero no exigir.</span><span class="sxs-lookup"><span data-stu-id="82e21-137">Some policies can be checked but not enforced.</span></span> <span data-ttu-id="82e21-138">Los modos de evaluación son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="82e21-138">The evaluation modes are as follows:</span></span>  
  
 <span data-ttu-id="82e21-139">**A petición**</span><span class="sxs-lookup"><span data-stu-id="82e21-139">**On demand**</span></span>  
 <span data-ttu-id="82e21-140">La directiva solo se ejecutará desde el cuadro de diálogo **Evaluar** .</span><span class="sxs-lookup"><span data-stu-id="82e21-140">Policy will only be run when you run it from the **Evaluate** dialog box.</span></span>  
  
 <span data-ttu-id="82e21-141">**Al programar**</span><span class="sxs-lookup"><span data-stu-id="82e21-141">**On schedule**</span></span>  
 <span data-ttu-id="82e21-142">La directiva se evalúa periódicamente, se graba una entrada de registro para las directivas que no se cumplen y se crea un informe.</span><span class="sxs-lookup"><span data-stu-id="82e21-142">Periodically evaluates the policy, records a log entry for policies that have out-of-compliance, and creates a report.</span></span> <span data-ttu-id="82e21-143">Habilita el cuadro **Programación** .</span><span class="sxs-lookup"><span data-stu-id="82e21-143">Enables the **Schedule** box.</span></span>  
  
 <span data-ttu-id="82e21-144">**Al cambiar: solo registro**</span><span class="sxs-lookup"><span data-stu-id="82e21-144">**On change: log only**</span></span>  
 <span data-ttu-id="82e21-145">Cuando se prueban los cambios, esta opción no evita los cambios que no cumplen la directiva, pero registra las infracciones de la directiva.</span><span class="sxs-lookup"><span data-stu-id="82e21-145">When changes are tried, this option does not prevent out-of-compliance changes, but logs policy violations.</span></span>  
  
 <span data-ttu-id="82e21-146">**Al cambiar: impedir**</span><span class="sxs-lookup"><span data-stu-id="82e21-146">**On change: prevent**</span></span>  
 <span data-ttu-id="82e21-147">Cuando se prueban los cambios, esta opción evita los cambios que infringirían la directiva.</span><span class="sxs-lookup"><span data-stu-id="82e21-147">When changes are tried, this option prevents changes that would violate the policy.</span></span>  
  
 <span data-ttu-id="82e21-148">**Programación**</span><span class="sxs-lookup"><span data-stu-id="82e21-148">**Schedule**</span></span>  
 <span data-ttu-id="82e21-149">Esta opción aparece cuando está seleccionado el modo de evaluación **Al programar** .</span><span class="sxs-lookup"><span data-stu-id="82e21-149">This option appears when **On schedule** evaluation mode is selected.</span></span> <span data-ttu-id="82e21-150">Escriba el nombre de la programación, haga clic en **Seleccionar** para seleccionar una programación de una lista o haga clic en **Nueva** para crear una nueva.</span><span class="sxs-lookup"><span data-stu-id="82e21-150">Type the name of the schedule, click **Pick** to select a schedule from a list, or click **New** to create a new schedule.</span></span> <span data-ttu-id="82e21-151">Para habilitar el área de programación, debe seleccionarse **Al programar** .</span><span class="sxs-lookup"><span data-stu-id="82e21-151">To enable the schedule area, **On schedule** must be selected.</span></span>  
  
 <span data-ttu-id="82e21-152">**Restricción de servidor**</span><span class="sxs-lookup"><span data-stu-id="82e21-152">**Server restriction**</span></span>  
 <span data-ttu-id="82e21-153">Seleccione los tipos de servidores que son adecuados para esta directiva.</span><span class="sxs-lookup"><span data-stu-id="82e21-153">Select the types of servers that are appropriate for this policy.</span></span> <span data-ttu-id="82e21-154">Las opciones son **Ninguno** o seleccionar una condición que filtre los servidores posibles.</span><span class="sxs-lookup"><span data-stu-id="82e21-154">Options are **None** or select a condition that filters the possible servers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82e21-155">Consulte también</span><span class="sxs-lookup"><span data-stu-id="82e21-155">See Also</span></span>  
 [<span data-ttu-id="82e21-156">Administrar servidores mediante administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="82e21-156">Administer Servers by Using Policy-Based Management</span></span>](administer-servers-by-using-policy-based-management.md)  
  
  
