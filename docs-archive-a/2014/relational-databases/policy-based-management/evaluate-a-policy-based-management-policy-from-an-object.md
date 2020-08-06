---
title: Evaluar una directiva de administración basada en directivas desde un objeto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, evaluate policy
ms.assetid: b9e9d646-4894-4dee-a02a-0c71a8dc020e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f0de02092c87a727b723a5940805f34a75052e5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674768"
---
# <a name="evaluate-a-policy-based-management-policy-from-an-object"></a><span data-ttu-id="f6670-102">Evaluar una directiva de administración basada en directivas desde un objeto</span><span class="sxs-lookup"><span data-stu-id="f6670-102">Evaluate a Policy-Based Management Policy from an Object</span></span>
  <span data-ttu-id="f6670-103">En este tema se describe cómo evaluar una directiva de una instancia de servidor, una base de datos o un objeto de base de datos en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f6670-103">This topic describes how to evaluate a policy from a server instance, database, or database object in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="f6670-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="f6670-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f6670-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="f6670-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f6670-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="f6670-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f6670-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f6670-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f6670-108">**Para evaluar una directiva de un objeto mediante:**</span><span class="sxs-lookup"><span data-stu-id="f6670-108">**To evaluate a policy from an object, using:**</span></span>  
  
     [<span data-ttu-id="f6670-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f6670-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f6670-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="f6670-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f6670-111">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="f6670-111">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="f6670-112">El modo de ejecución se define como parte de la directiva y no se puede cambiar en el cuadro de diálogo **Evaluar directivas** .</span><span class="sxs-lookup"><span data-stu-id="f6670-112">The execution mode is defined as part of the policy and cannot be changed in the **Evaluate Policies** dialog box.</span></span>  
  
-   <span data-ttu-id="f6670-113">El cuadro de diálogo **Evaluar directivas** solo muestra las directivas apropiadas para el objeto de base de datos.</span><span class="sxs-lookup"><span data-stu-id="f6670-113">The **Evaluate Policies** dialog box only shows policies appropriate for the database object.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f6670-114">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f6670-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f6670-115">Permisos</span><span class="sxs-lookup"><span data-stu-id="f6670-115">Permissions</span></span>  
 <span data-ttu-id="f6670-116">Requiere la pertenencia al rol PolicyAdministratorRole en la base de datos msdb.</span><span class="sxs-lookup"><span data-stu-id="f6670-116">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f6670-117">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f6670-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-evaluate-a-policy-from-an-object"></a><span data-ttu-id="f6670-118">Para evaluar una directiva de un objeto</span><span class="sxs-lookup"><span data-stu-id="f6670-118">To evaluate a policy from an object</span></span>  
  
1.  <span data-ttu-id="f6670-119">En el Explorador de objetos, haga clic con el botón derecho en una instancia de servidor, base de datos u objeto de base de datos, elija **Directivas**y, después, seleccione **Evaluar**.</span><span class="sxs-lookup"><span data-stu-id="f6670-119">In Object Explorer, right-click a server instance, a database, or a database object, point to **Policies**, and select **Evaluate**.</span></span>  
  
2.  <span data-ttu-id="f6670-120">En el cuadro de diálogo **Evaluar directivas** , seleccione una o varias directivas y haga clic en **Evaluar** para ejecutar la directiva en modo de evaluación.</span><span class="sxs-lookup"><span data-stu-id="f6670-120">In the **Evaluate Policies** dialog box, select one or more policies and click **Evaluate** to run the policy in evaluation mode.</span></span> <span data-ttu-id="f6670-121">De esta forma se genera un informe de compatibilidad para el conjunto de destino, pero no se vuelve a configurar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ni se exige la compatibilidad en el futuro.</span><span class="sxs-lookup"><span data-stu-id="f6670-121">This generates a compliance report for the target set but does not reconfigure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or enforce future compliance.</span></span> <span data-ttu-id="f6670-122">En los destinos que no obedecen las directivas seleccionadas y que tienen propiedades que pueden estar reconfiguradas por la administración basada en directivas, puede exigir la compatibilidad de la directiva haciendo clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="f6670-122">For targets that do not comply with the selected policies and have properties that can be reconfigured by Policy-Based Management, you can enforce policy compliance by clicking **Apply**.</span></span> <span data-ttu-id="f6670-123">Para obtener más información acerca de las opciones disponibles en el cuadro de diálogo **Evaluar directivas** , vea [Evaluate Policies Dialog Box, Policy Selection Page](evaluate-policies-dialog-box-policy-selection-page.md), [Evaluate Policies Dialog Box, Evaluation Results Page](evaluate-policies-dialog-box-evaluation-results-page.md)y [Results Detailed View Dialog Box](results-detailed-view-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="f6670-123">For more information on the available options in the **Evaluate Policies** dialog box, see [Evaluate Policies Dialog Box, Policy Selection Page](evaluate-policies-dialog-box-policy-selection-page.md), [Evaluate Policies Dialog Box, Evaluation Results Page](evaluate-policies-dialog-box-evaluation-results-page.md), and [Results Detailed View Dialog Box](results-detailed-view-dialog-box.md).</span></span>  
  
3.  <span data-ttu-id="f6670-124">Cuando termine, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="f6670-124">When finished, click **Close**.</span></span>  
  
  
