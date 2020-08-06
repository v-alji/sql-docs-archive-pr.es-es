---
title: Eliminación de una directiva de administración basada en directivas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, delete policies
ms.assetid: 488f0305-190c-4223-aa5c-e9bd43b520eb
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7c43bc3cdf4a7a5b5d9268bbd7e68506616d1f0f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744063"
---
# <a name="delete-a-policy-based-management-policy"></a><span data-ttu-id="92ebe-102">Eliminar una directiva de administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="92ebe-102">Delete a Policy-Based Management Policy</span></span>
  <span data-ttu-id="92ebe-103">En este tema se describe cómo eliminar una directiva de administración basada en directivas en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92ebe-103">This topic describes how to delete a Policy-Based Management policy in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="92ebe-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="92ebe-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="92ebe-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="92ebe-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="92ebe-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="92ebe-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="92ebe-107">**Para eliminar una directiva mediante:**</span><span class="sxs-lookup"><span data-stu-id="92ebe-107">**To delete a policy, using:**</span></span>  
  
     [<span data-ttu-id="92ebe-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="92ebe-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="92ebe-109">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="92ebe-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="92ebe-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="92ebe-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="92ebe-111">Permisos</span><span class="sxs-lookup"><span data-stu-id="92ebe-111">Permissions</span></span>  
 <span data-ttu-id="92ebe-112">Requiere la pertenencia al rol PolicyAdministratorRole en la base de datos msdb.</span><span class="sxs-lookup"><span data-stu-id="92ebe-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="92ebe-113">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="92ebe-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-policy"></a><span data-ttu-id="92ebe-114">Para eliminar una directiva</span><span class="sxs-lookup"><span data-stu-id="92ebe-114">To delete a policy</span></span>  
  
1.  <span data-ttu-id="92ebe-115">En el Explorador de objetos, haga clic en el signo más para expandir el servidor que contiene la directiva de administración basada en directivas que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="92ebe-115">In Object Explorer, click the plus sign to expand the server that contains the Policy-Based Management policy that you want to delete.</span></span>  
  
2.  <span data-ttu-id="92ebe-116">Haga clic en el signo más para expandir la carpeta **Administración** .</span><span class="sxs-lookup"><span data-stu-id="92ebe-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="92ebe-117">Haga clic en el signo más para expandir la carpeta **Administración de directivas**.</span><span class="sxs-lookup"><span data-stu-id="92ebe-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="92ebe-118">Haga clic en el signo más para expandir la carpeta **Directivas** .</span><span class="sxs-lookup"><span data-stu-id="92ebe-118">Click the plus sign to expand the **Policies** folder.</span></span>  
  
5.  <span data-ttu-id="92ebe-119">Haga clic con el botón derecho en la directiva que quiere eliminar y seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="92ebe-119">Right-click the policy that you want to delete and select **Delete**.</span></span>  
  
6.  <span data-ttu-id="92ebe-120">En el cuadro de diálogo **Eliminar objeto** , asegúrese de que está seleccionada la condición correcta y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="92ebe-120">In the **Delete Object** dialog box, ensure that the correct condition is selected and then click **OK**.</span></span>  
  
  
