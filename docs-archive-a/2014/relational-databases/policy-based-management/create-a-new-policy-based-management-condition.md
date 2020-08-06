---
title: Creación de una nueva condición de administración basada en directivas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, creating policy conditions
ms.assetid: 8a612f7e-6c70-49db-a4de-48431e097cc5
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e4fe206c9a82b69101508f6f0a760ca9c1bc423d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673669"
---
# <a name="create-a-new-policy-based-management-condition"></a><span data-ttu-id="6b6e5-102">Crear una nueva condición de administración basada en directivas.</span><span class="sxs-lookup"><span data-stu-id="6b6e5-102">Create a New Policy-Based Management Condition</span></span>
  <span data-ttu-id="6b6e5-103">En este tema se describe cómo crear una condición de administración basada en directivas en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6b6e5-103">This topic describes how to create a Policy-based Management condition in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="6b6e5-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="6b6e5-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6b6e5-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="6b6e5-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6b6e5-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="6b6e5-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6b6e5-107">**Para crear una condición mediante:**</span><span class="sxs-lookup"><span data-stu-id="6b6e5-107">**To create a condition, using:**</span></span>  
  
     [<span data-ttu-id="6b6e5-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6b6e5-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6b6e5-109">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="6b6e5-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6b6e5-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="6b6e5-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6b6e5-111">Permisos</span><span class="sxs-lookup"><span data-stu-id="6b6e5-111">Permissions</span></span>  
 <span data-ttu-id="6b6e5-112">Requiere la pertenencia al rol PolicyAdministratorRole en la base de datos msdb.</span><span class="sxs-lookup"><span data-stu-id="6b6e5-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6b6e5-113">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6b6e5-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-condition"></a><span data-ttu-id="6b6e5-114">Para crear una condición</span><span class="sxs-lookup"><span data-stu-id="6b6e5-114">To create a condition</span></span>  
  
1.  <span data-ttu-id="6b6e5-115">En el **Explorador de objetos**, haga clic en el signo más para expandir el servidor en el que quiera crear una condición de administración basada en directivas.</span><span class="sxs-lookup"><span data-stu-id="6b6e5-115">In **Object Explorer**, click the plus sign to expand the server where you want to create a Policy-based Management condition.</span></span>  
  
2.  <span data-ttu-id="6b6e5-116">Haga clic en el signo más para expandir la carpeta **Administración** .</span><span class="sxs-lookup"><span data-stu-id="6b6e5-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="6b6e5-117">Haga clic en el signo más para expandir la carpeta **Administración de directivas**.</span><span class="sxs-lookup"><span data-stu-id="6b6e5-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="6b6e5-118">Haga clic en el signo más para expandir la carpeta **Facetas** .</span><span class="sxs-lookup"><span data-stu-id="6b6e5-118">Click the plus sign to expand the **Facets** folder.</span></span>  
  
5.  <span data-ttu-id="6b6e5-119">Haga clic con el botón derecho en la faceta en la que quiere crear una nueva condición y seleccione **Nueva condición**.</span><span class="sxs-lookup"><span data-stu-id="6b6e5-119">Right-click the facet in which you want to create a new condition and select **New Condition**.</span></span>  
  
6.  <span data-ttu-id="6b6e5-120">En el cuadro de diálogo **Crear nueva condición** , en el cuadro **Nombre** , escriba el nombre de la nueva condición.</span><span class="sxs-lookup"><span data-stu-id="6b6e5-120">In the **Create New Condition** dialog box, in the **Name** box, type the name of the new condition.</span></span>  
  
7.  <span data-ttu-id="6b6e5-121">Confirme que la faceta es correcta en la lista **Faceta** o seleccione una faceta diferente.</span><span class="sxs-lookup"><span data-stu-id="6b6e5-121">Confirm the correct facet in the **Facet** list, or select a different facet.</span></span>  
  
8.  <span data-ttu-id="6b6e5-122">En **Expresión**, construya las expresiones de condiciones seleccionando una propiedad de faceta en el cuadro **Campo** , junto con su operador y valor asociados.</span><span class="sxs-lookup"><span data-stu-id="6b6e5-122">Under **Expression**, construct condition expressions by selecting a facet property in the **Field** box, together with its associated operator and value.</span></span> <span data-ttu-id="6b6e5-123">Si agrega varias expresiones, estas pueden combinarse con **Y** u **O**.</span><span class="sxs-lookup"><span data-stu-id="6b6e5-123">When you add multiple expressions, the expressions can be joined by using **And** or **Or**.</span></span> <span data-ttu-id="6b6e5-124">Para obtener más información sobre las opciones disponibles en este cuadro de diálogo, vea [Cuadro de diálogo Crear nueva condición o Abrir condición, página General](../../integration-services/general-page-of-integration-services-designers-options.md), [Cuadro de diálogo Crear nueva condición o Abrir condición, página Descripción](create-new-condition-or-open-condition-dialog-box-description-page.md) y [Cuadro de diálogo Edición avanzada &#40;condición&#41;](advanced-edit-condition-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="6b6e5-124">For more information on the available options in this dialog box, see [Create New Condition or Open Condition Dialog Box, General Page](../../integration-services/general-page-of-integration-services-designers-options.md), [Create New Condition or Open Condition Dialog Box, Description Page](create-new-condition-or-open-condition-dialog-box-description-page.md), and [Advanced Edit &#40;Condition&#41; Dialog Box](advanced-edit-condition-dialog-box.md).</span></span>  
  
9. <span data-ttu-id="6b6e5-125">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6b6e5-125">When finished, click **OK**.</span></span>  
  
  
