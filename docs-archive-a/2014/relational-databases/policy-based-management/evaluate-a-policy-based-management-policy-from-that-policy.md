---
title: Evaluar una directiva de administración basada en directivas desde dicha directiva | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, evaluate policy
ms.assetid: 0b3214bd-d0ab-45ab-9281-3d95507abe54
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 207c86f1465c49238fc9b50ee75489b43d956caf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674770"
---
# <a name="evaluate-a-policy-based-management-policy-from-that-policy"></a><span data-ttu-id="0d875-102">Evaluar una directiva de administración basada en directivas desde dicha directiva</span><span class="sxs-lookup"><span data-stu-id="0d875-102">Evaluate a Policy-Based Management Policy from That Policy</span></span>
  <span data-ttu-id="0d875-103">En este tema se describe cómo evaluar una directiva utilizando esa directiva en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d875-103">This topic describes how to evaluate a policy using that policy in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="0d875-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="0d875-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0d875-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="0d875-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0d875-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="0d875-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="0d875-107">**Para evaluar una directiva mediante:**</span><span class="sxs-lookup"><span data-stu-id="0d875-107">**To evaluate a policy, using:**</span></span>  
  
     [<span data-ttu-id="0d875-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0d875-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0d875-109">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="0d875-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0d875-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="0d875-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0d875-111">Permisos</span><span class="sxs-lookup"><span data-stu-id="0d875-111">Permissions</span></span>  
 <span data-ttu-id="0d875-112">Requiere la pertenencia al rol PolicyAdministratorRole en la base de datos msdb.</span><span class="sxs-lookup"><span data-stu-id="0d875-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0d875-113">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0d875-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-evaluate-a-policy"></a><span data-ttu-id="0d875-114">Para evaluar una directiva</span><span class="sxs-lookup"><span data-stu-id="0d875-114">To evaluate a policy</span></span>  
  
1.  <span data-ttu-id="0d875-115">En el **Explorador de objetos**, haga clic en el signo más para expandir el servidor que contiene la directiva que desea evaluar.</span><span class="sxs-lookup"><span data-stu-id="0d875-115">In **Object Explorer**, click the plus sign to expand the server that contains the policy that you want to evaluate.</span></span>  
  
2.  <span data-ttu-id="0d875-116">Haga clic en el signo más para expandir la carpeta **Administración** .</span><span class="sxs-lookup"><span data-stu-id="0d875-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="0d875-117">Haga clic en el signo más para expandir la carpeta **Administración de directivas**.</span><span class="sxs-lookup"><span data-stu-id="0d875-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="0d875-118">Haga clic en el signo más para expandir la carpeta **Directivas** .</span><span class="sxs-lookup"><span data-stu-id="0d875-118">Click the plus sign to expand the **Policies** folder.</span></span>  
  
5.  <span data-ttu-id="0d875-119">Haga clic con el botón derecho en la directiva que quiere evaluar y seleccione **Evaluar**.</span><span class="sxs-lookup"><span data-stu-id="0d875-119">Right-click the policy that you want to evaluate and select **Evaluate**.</span></span>  
  
6.  <span data-ttu-id="0d875-120">En el cuadro de diálogo **Evaluar resultados**  se muestran los resultados de la evaluación de la directiva.</span><span class="sxs-lookup"><span data-stu-id="0d875-120">In the **Evaluate Results**  dialog box, you see the results of the policy evaluation.</span></span> <span data-ttu-id="0d875-121">En los destinos que no cumplen la directiva y que tienen propiedades que pueden estar reconfiguradas por la administración basada en directivas, puede exigir el cumplimiento de la directiva haciendo clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="0d875-121">For targets that do not comply with the policy and have properties that can be reconfigured by Policy-Based Management, you can enforce compliance by clicking **Apply**.</span></span> <span data-ttu-id="0d875-122">Para obtener más información acerca de las opciones disponibles en el cuadro de diálogo **Evaluar directivas** , vea [Evaluate Policies Dialog Box, Policy Selection Page](evaluate-policies-dialog-box-policy-selection-page.md) y [Evaluate Policies Dialog Box, Evaluation Results Page](evaluate-policies-dialog-box-evaluation-results-page.md).</span><span class="sxs-lookup"><span data-stu-id="0d875-122">For more information on the available options in the **Evaluate Policies** dialog box, see [Evaluate Policies Dialog Box, Policy Selection Page](evaluate-policies-dialog-box-policy-selection-page.md) and [Evaluate Policies Dialog Box, Evaluation Results Page](evaluate-policies-dialog-box-evaluation-results-page.md).</span></span>  
  
7.  <span data-ttu-id="0d875-123">Cuando termine, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="0d875-123">When finished, click **Close**.</span></span>  
  
  
