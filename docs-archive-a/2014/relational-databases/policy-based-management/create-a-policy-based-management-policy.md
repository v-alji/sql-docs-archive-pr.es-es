---
title: Creación de una directiva de administración basada en directivas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, creating policies
ms.assetid: b28bf963-89f9-4941-b6c1-6004fec347f1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e76b4dce17e00bae5e8ca4fcf071868c0641c786
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673664"
---
# <a name="create-a-policy-based-management-policy"></a><span data-ttu-id="04125-102">Crear una directiva de administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="04125-102">Create a Policy-Based Management Policy</span></span>
  <span data-ttu-id="04125-103">En este tema se describe cómo crear una directiva de administración basada en directivas en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="04125-103">This topic describes how to create a Policy-Based Management policy in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="04125-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="04125-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="04125-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="04125-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="04125-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="04125-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="04125-107">**Para crear una directiva mediante:**</span><span class="sxs-lookup"><span data-stu-id="04125-107">**To create a policy, using:**</span></span>  
  
     [<span data-ttu-id="04125-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="04125-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="04125-109">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="04125-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="04125-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="04125-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="04125-111">Permisos</span><span class="sxs-lookup"><span data-stu-id="04125-111">Permissions</span></span>  
 <span data-ttu-id="04125-112">Requiere la pertenencia al rol PolicyAdministratorRole en la base de datos msdb.</span><span class="sxs-lookup"><span data-stu-id="04125-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="04125-113">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="04125-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-policy"></a><span data-ttu-id="04125-114">Para crear una directiva</span><span class="sxs-lookup"><span data-stu-id="04125-114">To create a policy</span></span>  
  
1.  <span data-ttu-id="04125-115">En el **Explorador de objetos**, haga clic en el signo más para expandir el servidor en el que quiere crear una directiva de administración basada en directivas.</span><span class="sxs-lookup"><span data-stu-id="04125-115">In **Object Explorer**, click the plus sign to expand the server where you want to create a new a Policy-Based Management policy.</span></span>  
  
2.  <span data-ttu-id="04125-116">Haga clic en el signo más para expandir la carpeta **Administración** .</span><span class="sxs-lookup"><span data-stu-id="04125-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="04125-117">Haga clic en el signo más para expandir la carpeta **Administración de directivas**.</span><span class="sxs-lookup"><span data-stu-id="04125-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="04125-118">Haga clic con el botón derecho en la carpeta **Directivas** y, después, seleccione **Nueva directiva**.</span><span class="sxs-lookup"><span data-stu-id="04125-118">Right-click the **Policies** folder and select **New Policy**.</span></span>  
  
5.  <span data-ttu-id="04125-119">En el cuadro de diálogo **Crear nueva directiva** , en el cuadro **Nombre** , escriba el nombre de la nueva directiva.</span><span class="sxs-lookup"><span data-stu-id="04125-119">In the **Create New Policy** dialog box, in the **Name** box, type the name of the new policy.</span></span>  
  
6.  <span data-ttu-id="04125-120">Si desea que la directiva se habilite en cuanto se cree, active la casilla **Habilitado** .</span><span class="sxs-lookup"><span data-stu-id="04125-120">If you want the policy to be enabled as soon as it is created, select the **Enabled** check box.</span></span> <span data-ttu-id="04125-121">Si el modo de evaluación es **A petición**, la casilla **Habilitado** no está disponible.</span><span class="sxs-lookup"><span data-stu-id="04125-121">If the evaluation mode is **On demand**, the **Enabled** check box is not available.</span></span>  
  
7.  <span data-ttu-id="04125-122">En la lista **Condición de comprobación** , seleccione una de las condiciones existentes o seleccione **Nueva condición**.</span><span class="sxs-lookup"><span data-stu-id="04125-122">In the **Check condition** list, select one of the existing conditions, or select **New Condition**.</span></span> <span data-ttu-id="04125-123">Para modificar una condición, selecciónela y, después, haga clic en los puntos suspensivos ( **...** ). Para obtener más información, vea [Crear una nueva condición de administración basada en directivas.](create-a-new-policy-based-management-condition.md) o [Ver o modificar las propiedades de una condición de administración basada en directivas](view-or-modify-the-properties-of-a-policy-based-management-condition.md).</span><span class="sxs-lookup"><span data-stu-id="04125-123">To edit a condition, select the condition and then click the ellipsis (**...**). For more information, see [Create a New Policy-Based Management Condition](create-a-new-policy-based-management-condition.md) or [View or Modify the Properties of a Policy-Based Management Condition](view-or-modify-the-properties-of-a-policy-based-management-condition.md).</span></span>  
  
8.  <span data-ttu-id="04125-124">En el cuadro **Para destinos** , seleccione uno o varios tipos de destino para esta directiva.</span><span class="sxs-lookup"><span data-stu-id="04125-124">In the **Against targets** box, select one or more target types for this policy.</span></span> <span data-ttu-id="04125-125">Algunas condiciones y facetas solo se pueden aplicar a ciertos tipos de destinos.</span><span class="sxs-lookup"><span data-stu-id="04125-125">Some conditions and facets can only be applied to certain types of targets.</span></span> <span data-ttu-id="04125-126">Los conjuntos de destinos disponibles aparecen en el cuadro asociado.</span><span class="sxs-lookup"><span data-stu-id="04125-126">The available target sets appear in the associated box.</span></span> <span data-ttu-id="04125-127">Expanda **Cada** para seleccionar una condición de filtrado para algunos tipos de destinos.</span><span class="sxs-lookup"><span data-stu-id="04125-127">Expand **Every** to select a filtering condition for some types of the targets.</span></span> <span data-ttu-id="04125-128">Si en este cuadro no aparece ningún destino, la condición de comprobación se investiga en el nivel de servidor.</span><span class="sxs-lookup"><span data-stu-id="04125-128">If no targets appear in this box, the check condition is scoped at the server level.</span></span>  
  
9. <span data-ttu-id="04125-129">En el cuadro **Modo de evaluación** , seleccione cómo se comportará esta directiva.</span><span class="sxs-lookup"><span data-stu-id="04125-129">In the **Evaluation Mode** box, select how this policy will behave.</span></span> <span data-ttu-id="04125-130">Condiciones diferentes pueden tener distintos modos de evaluación válidos.</span><span class="sxs-lookup"><span data-stu-id="04125-130">Different conditions can have different valid evaluation modes.</span></span> <span data-ttu-id="04125-131">Para obtener más información sobre los modos de evaluación válidos, vea [Administrar servidores mediante administración basada en directivas](administer-servers-by-using-policy-based-management.md).</span><span class="sxs-lookup"><span data-stu-id="04125-131">For more information about which evaluation modes are valid, see [Administer Servers by Using Policy-Based Management](administer-servers-by-using-policy-based-management.md).</span></span>  
  
10. <span data-ttu-id="04125-132">Si la directiva se va a evaluar según una programación, establezca el modo de evaluación en **Al programar**y, a continuación, haga clic en **Seleccionar** para seleccionar una programación o haga clic en **Nuevo** para crear una nueva programación.</span><span class="sxs-lookup"><span data-stu-id="04125-132">If the policy will be evaluated on a schedule, set the evaluation mode to **On schedule**, and then click **Pick** to select a schedule, or click **New** to create a new schedule.</span></span>  
  
11. <span data-ttu-id="04125-133">Para limitar la directiva al subconjunto de los tipos de destino, en el cuadro **Restricción de servidor** , seleccione las condiciones de limitación o cree una condición nueva.</span><span class="sxs-lookup"><span data-stu-id="04125-133">To limit the policy to subset of the target types, in the **Server restriction** box, select from limiting conditions or create a new condition.</span></span>  
  
     <span data-ttu-id="04125-134">Para obtener más información acerca de las opciones disponibles en el cuadro de diálogo **Crear nueva directiva** , vea [Cuadro de diálogo Crear nueva directiva o Abrir directiva, página General](../../integration-services/general-page-of-integration-services-designers-options.md) o [Cuadro de diálogo Crear nueva directiva o Abrir directiva, página Descripción](create-new-policy-or-open-policy-dialog-box-description-page.md).</span><span class="sxs-lookup"><span data-stu-id="04125-134">For more information on the available options in the **Create New Policy** dialog box, see [Create New Policy or Open Policy Dialog Box, General Page](../../integration-services/general-page-of-integration-services-designers-options.md) or [Create New Policy or Open Policy Dialog Box, Description Page](create-new-policy-or-open-policy-dialog-box-description-page.md).</span></span>  
  
12. <span data-ttu-id="04125-135">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="04125-135">When finished click **OK**.</span></span>  
  
  
