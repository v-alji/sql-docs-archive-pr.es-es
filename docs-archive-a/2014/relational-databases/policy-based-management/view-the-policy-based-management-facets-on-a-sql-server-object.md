---
title: Ver las facetas de administración basada en directivas en un objeto de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, view facets
ms.assetid: 5f423b9f-a6c4-41a7-9d8d-8f4926ce1fb4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9137971a79e9e5a18e0ef5d901184133a4c3eff3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670973"
---
# <a name="view-the-policy-based-management-facets-on-a-sql-server-object"></a><span data-ttu-id="707cf-102">Ver las facetas de administración basada en directivas en un objeto de SQL Server</span><span class="sxs-lookup"><span data-stu-id="707cf-102">View the Policy-Based Management Facets on a SQL Server Object</span></span>
  <span data-ttu-id="707cf-103">En este tema se describe cómo ver todas las facetas de administración basada en directivas aplicadas a un objeto específico de SQL Server en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="707cf-103">This topic describes how to view all of the Policy-Based Management facets applied to a specific SQL Server object in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="707cf-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="707cf-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="707cf-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="707cf-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="707cf-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="707cf-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="707cf-107">**Para ver todas las facetas de un objeto mediante:**</span><span class="sxs-lookup"><span data-stu-id="707cf-107">**To view all of the facets in an object, using:**</span></span>  
  
     [<span data-ttu-id="707cf-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="707cf-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="707cf-109">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="707cf-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="707cf-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="707cf-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="707cf-111">Permisos</span><span class="sxs-lookup"><span data-stu-id="707cf-111">Permissions</span></span>  
 <span data-ttu-id="707cf-112">Requiere la pertenencia al rol PolicyAdministratorRole en la base de datos msdb.</span><span class="sxs-lookup"><span data-stu-id="707cf-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="707cf-113">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="707cf-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-all-of-the-facets-in-an-object"></a><span data-ttu-id="707cf-114">Para ver todas las facetas de un objeto</span><span class="sxs-lookup"><span data-stu-id="707cf-114">To view all of the facets in an object</span></span>  
  
1.  <span data-ttu-id="707cf-115">En el Explorador de objetos, haga clic con el botón derecho en una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], objeto de instancia, base de datos u objeto de base de datos y, después, haga clic en **Facetas**.</span><span class="sxs-lookup"><span data-stu-id="707cf-115">In Object Explorer, right-click an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], instance object, database, or database object, and then click **Facets**.</span></span>  
  
2.  <span data-ttu-id="707cf-116">En el cuadro de diálogo **Ver facetas -**_nombre_de_objeto_, en la lista **Faceta**, seleccione una faceta para ver sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="707cf-116">In the **View Facets -**_object_name_ dialog box, in the **Facet** list, select a facet to view its properties.</span></span> <span data-ttu-id="707cf-117">Para obtener más información acerca de las opciones disponibles en este cuadro de diálogo, vea [View Facets Dialog Box](view-facets-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="707cf-117">For more information on the available options in this dialog box, see [View Facets Dialog Box](view-facets-dialog-box.md).</span></span>  
  
3.  <span data-ttu-id="707cf-118">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="707cf-118">When finished, click **OK**.</span></span>  
  
  
