---
title: Eliminación de una condición de administración basada en directivas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, delete policy conditions
ms.assetid: e04148b8-f6dd-4c50-a5ef-c650b71dbf4d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f02a5294ecb53db4d8baa4f3dae0a232d9551a13
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662858"
---
# <a name="delete-a-policy-based-management-condition"></a><span data-ttu-id="eb7f5-102">Eliminar una condición de administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="eb7f5-102">Delete a Policy-Based Management Condition</span></span>
  <span data-ttu-id="eb7f5-103">En este tema se describe cómo eliminar una condición de administración basada en directivas en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eb7f5-103">This topic describes how to delete a Policy-based Management condition in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="eb7f5-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="eb7f5-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="eb7f5-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="eb7f5-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="eb7f5-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="eb7f5-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="eb7f5-107">**Para eliminar una condición mediante:**</span><span class="sxs-lookup"><span data-stu-id="eb7f5-107">**To delete a condition, using:**</span></span>  
  
     [<span data-ttu-id="eb7f5-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="eb7f5-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="eb7f5-109">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="eb7f5-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="eb7f5-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="eb7f5-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="eb7f5-111">Permisos</span><span class="sxs-lookup"><span data-stu-id="eb7f5-111">Permissions</span></span>  
 <span data-ttu-id="eb7f5-112">Requiere la pertenencia al rol PolicyAdministratorRole en la base de datos msdb.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="eb7f5-113">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="eb7f5-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-condition"></a><span data-ttu-id="eb7f5-114">Para eliminar una condición</span><span class="sxs-lookup"><span data-stu-id="eb7f5-114">To delete a condition</span></span>  
  
1.  <span data-ttu-id="eb7f5-115">En el **Explorador de objetos**, haga clic en el signo más para expandir el servidor que contiene la condición que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-115">In **Object Explorer**, click the plus sign to expand the server that contains the condition that you want to delete.</span></span>  
  
2.  <span data-ttu-id="eb7f5-116">Haga clic en el signo más para expandir la carpeta **Administración** .</span><span class="sxs-lookup"><span data-stu-id="eb7f5-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="eb7f5-117">Haga clic en el signo más para expandir la carpeta **Administración de directivas**.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="eb7f5-118">Haga clic en el signo más para expandir la carpeta **Condiciones** .</span><span class="sxs-lookup"><span data-stu-id="eb7f5-118">Click the plus sign to expand the **Conditions** folder.</span></span>  
  
5.  <span data-ttu-id="eb7f5-119">Haga clic con el botón derecho en la condición que quiera eliminar y, después, seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-119">Right-click the condition that you want to delete and select **Delete**.</span></span>  
  
6.  <span data-ttu-id="eb7f5-120">En el cuadro de diálogo **Eliminar objeto** , asegúrese de que está seleccionada la condición correcta y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="eb7f5-120">In the **Delete Object** dialog box, ensure that the correct condition is selected and then click **OK**.</span></span>  
  
  
