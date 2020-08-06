---
title: Ver las propiedades de una faceta de administración basada en directivas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, view facet properties
ms.assetid: 022a244c-c2e7-4467-b9a2-c7a27859be22
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ea24ff2768ecaeec426a8689455912d848b54813
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670972"
---
# <a name="view-the-properties-of-a-policy-based-management-facet"></a><span data-ttu-id="6c7c3-102">Ver las propiedades de una faceta de administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="6c7c3-102">View the Properties of a Policy-Based Management Facet</span></span>
  <span data-ttu-id="6c7c3-103">En este tema se describe cómo ver las propiedades de una faceta de administración basada en directivas en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6c7c3-103">This topic describes how to view the properties of a Policy-Based Management facet in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="6c7c3-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="6c7c3-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6c7c3-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="6c7c3-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6c7c3-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="6c7c3-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6c7c3-107">**Para ver propiedades de una faceta mediante:**</span><span class="sxs-lookup"><span data-stu-id="6c7c3-107">**To view the properties of a facet, using:**</span></span>  
  
     [<span data-ttu-id="6c7c3-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6c7c3-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6c7c3-109">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="6c7c3-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6c7c3-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="6c7c3-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6c7c3-111">Permisos</span><span class="sxs-lookup"><span data-stu-id="6c7c3-111">Permissions</span></span>  
 <span data-ttu-id="6c7c3-112">Requiere la pertenencia al rol PolicyAdministratorRole en la base de datos msdb.</span><span class="sxs-lookup"><span data-stu-id="6c7c3-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6c7c3-113">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6c7c3-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-properties-of-a-facet"></a><span data-ttu-id="6c7c3-114">Para ver las propiedades de una faceta</span><span class="sxs-lookup"><span data-stu-id="6c7c3-114">To view the properties of a facet</span></span>  
  
1.  <span data-ttu-id="6c7c3-115">En el **Explorador de objetos**, haga clic en el signo más para expandir el servidor que contiene la faceta cuyas propiedades desea ver.</span><span class="sxs-lookup"><span data-stu-id="6c7c3-115">In **Object Explorer**, click the plus sign to expand the server that contains the facet whose properties you want to view.</span></span>  
  
2.  <span data-ttu-id="6c7c3-116">Haga clic en el signo más para expandir la carpeta **Administración** .</span><span class="sxs-lookup"><span data-stu-id="6c7c3-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="6c7c3-117">Haga clic en el signo más para expandir la carpeta **Administración de directivas**.</span><span class="sxs-lookup"><span data-stu-id="6c7c3-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="6c7c3-118">Haga clic en el signo más para expandir la carpeta **Facetas** .</span><span class="sxs-lookup"><span data-stu-id="6c7c3-118">Click the plus sign to expand the **Facets** folder.</span></span>  
  
5.  <span data-ttu-id="6c7c3-119">Haga clic con el botón derecho en la faceta cuyas propiedades quiere ver y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6c7c3-119">Right-click the facet whose properties you want to view and select **Properties**.</span></span> <span data-ttu-id="6c7c3-120">Para más información sobre las opciones disponibles en el cuadro de diálogo **Propiedades de faceta -**_nombre_de_faceta_, vea [Cuadro de diálogo Propiedades de faceta, página General](../../integration-services/general-page-of-integration-services-designers-options.md), [Cuadro de diálogo Propiedades de faceta, página Directivas dependientes](facet-properties-dialog-box-dependent-policies-page.md) y [Cuadro de diálogo Propiedades de faceta, página Condiciones dependientes](facet-properties-dialog-box-dependent-conditions-page.md).</span><span class="sxs-lookup"><span data-stu-id="6c7c3-120">For more information on the available options in the **Facet Properties -**_facet_name_ dialog box, see [Facet Properties Dialog Box, General Page](../../integration-services/general-page-of-integration-services-designers-options.md), [Facet Properties Dialog Box, Dependent Policies Page](facet-properties-dialog-box-dependent-policies-page.md), and [Facet Properties Dialog Box, Dependent Conditions Page](facet-properties-dialog-box-dependent-conditions-page.md).</span></span>  
  
6.  <span data-ttu-id="6c7c3-121">Cuando termine, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="6c7c3-121">When finished, click **Close**.</span></span>  
  
  