---
title: Evaluar una directiva de administración basada en directivas según una programación | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, evaluate policy
ms.assetid: bea09522-ff47-4037-ab55-a98ea7c10099
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f1c6b1a7d13d14c02f4b4e537c2dbdb2df39d02c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745715"
---
# <a name="evaluate-a-policy-based-management-policy-on-a-schedule"></a><span data-ttu-id="5b1f4-102">Evaluar una directiva de administración basada en directivas según una programación</span><span class="sxs-lookup"><span data-stu-id="5b1f4-102">Evaluate a Policy-Based Management Policy on a Schedule</span></span>
  <span data-ttu-id="5b1f4-103">En este tema se describe cómo evaluar una directiva de administración basada en directivas según una programación en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b1f4-103">This topic describes how to evaluate a Policy-Based Management policy on a schedule in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="5b1f4-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="5b1f4-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5b1f4-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="5b1f4-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5b1f4-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5b1f4-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5b1f4-107">**Para evaluar una directiva según una programación mediante**</span><span class="sxs-lookup"><span data-stu-id="5b1f4-107">**To evaluate a policy on a schedule, using:**</span></span>  
  
     [<span data-ttu-id="5b1f4-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5b1f4-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5b1f4-109">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="5b1f4-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5b1f4-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5b1f4-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5b1f4-111">Permisos</span><span class="sxs-lookup"><span data-stu-id="5b1f4-111">Permissions</span></span>  
 <span data-ttu-id="5b1f4-112">Requiere la pertenencia al rol PolicyAdministratorRole en la base de datos msdb.</span><span class="sxs-lookup"><span data-stu-id="5b1f4-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5b1f4-113">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5b1f4-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-evaluate-a-policy-on-a-schedule"></a><span data-ttu-id="5b1f4-114">Para evaluar una directiva según una programación</span><span class="sxs-lookup"><span data-stu-id="5b1f4-114">To evaluate a policy on a schedule</span></span>  
  
1.  <span data-ttu-id="5b1f4-115">En el **Explorador de objetos**, haga clic en el signo más para expandir el servidor que contiene la programación de directiva que desea evaluar.</span><span class="sxs-lookup"><span data-stu-id="5b1f4-115">In **Object Explorer**, click the plus sign to expand the server that contains the policy schedule that you want to evaluate.</span></span>  
  
2.  <span data-ttu-id="5b1f4-116">Haga clic en el signo más para expandir la carpeta **Administración** .</span><span class="sxs-lookup"><span data-stu-id="5b1f4-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="5b1f4-117">Haga clic en el signo más para expandir la carpeta **Administración de directivas**.</span><span class="sxs-lookup"><span data-stu-id="5b1f4-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="5b1f4-118">Haga clic en el signo más para expandir la carpeta **Directivas** .</span><span class="sxs-lookup"><span data-stu-id="5b1f4-118">Click the plus sign to expand the **Policies** folder.</span></span>  
  
5.  <span data-ttu-id="5b1f4-119">Haga clic con el botón derecho en la directiva cuya programación quiera evaluar y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5b1f4-119">Right-click the policy whose schedule you what to evaluate and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="5b1f4-120">En el cuadro de diálogo **Abrir directiva -** _nombre_de_directiva_, en la lista **Modo de evaluación**, seleccione **Al programar**.</span><span class="sxs-lookup"><span data-stu-id="5b1f4-120">On the **Open Policy -**_policy_name_ dialog box, in the **Evaluation Mode** list, select **On schedule**.</span></span>  
  
7.  <span data-ttu-id="5b1f4-121">En **Programación**, haga clic en **Elegir** para especificar una programación existente o en **Nuevo** para crear una programación nueva.</span><span class="sxs-lookup"><span data-stu-id="5b1f4-121">Under **Schedule**, click either **Pick** to specify an existing schedule or **New** to create a new schedule.</span></span>  
  
8.  <span data-ttu-id="5b1f4-122">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5b1f4-122">When finished, click **OK**.</span></span>  
  
  
