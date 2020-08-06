---
title: Iniciar automáticamente el Agente SQL Server (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, starting
- autostart SQL Server Agent
ms.assetid: 2ea332da-0ede-4d2b-b122-c4c10eaca191
author: stevestein
ms.author: sstein
ms.openlocfilehash: a39c7c7a112370797a965cfa601bc07f983a7a37
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674537"
---
# <a name="autostart-sql-server-agent-sql-server-management-studio"></a><span data-ttu-id="d18a1-102">Autostart SQL Server Agent (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="d18a1-102">Autostart SQL Server Agent (SQL Server Management Studio)</span></span>
  <span data-ttu-id="d18a1-103">En este tema se describe cómo configurar el [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agente para que se reinicie automáticamente si debe detenerse de forma inesperada en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d18a1-103">This topic describes how to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to automatically restart if it should stop unexpectedly in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="d18a1-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="d18a1-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d18a1-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="d18a1-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d18a1-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="d18a1-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="d18a1-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="d18a1-107">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="d18a1-108">Para configurar el Agente SQL Server de modo que se reinicie automáticamente, utilizando SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d18a1-108">To configure SQL Server Agent to automatically restart, using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d18a1-109">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="d18a1-109">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="d18a1-110">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="d18a1-110">Limitations and Restrictions</span></span>  
 <span data-ttu-id="d18a1-111">El Explorador de objetos solo muestra el nodo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] si se tiene permiso para usarlo.</span><span class="sxs-lookup"><span data-stu-id="d18a1-111">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d18a1-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="d18a1-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d18a1-113">Permisos</span><span class="sxs-lookup"><span data-stu-id="d18a1-113">Permissions</span></span>  
 <span data-ttu-id="d18a1-114">Para realizar sus funciones, el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe configurarse de modo que use las credenciales de una cuenta que sea miembro del rol fijo de servidor **sysadmin** en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d18a1-114">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d18a1-115">La cuenta debe tener los siguientes permisos de Windows:</span><span class="sxs-lookup"><span data-stu-id="d18a1-115">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="d18a1-116">Iniciar sesión como servicio (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="d18a1-116">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="d18a1-117">Reemplazar un token de nivel de proceso (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="d18a1-117">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="d18a1-118">Omitir la comprobación transversal (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="d18a1-118">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="d18a1-119">Ajustar las cuotas de memoria de un proceso (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="d18a1-119">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="d18a1-120">Para obtener más información acerca de los permisos de Windows necesarios para la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cuenta de servicio del agente, consulte [seleccionar una cuenta para el servicio de Agente SQL Server](select-an-account-for-the-sql-server-agent-service.md) y [configurar los permisos y las cuentas de servicio de Windows](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="d18a1-120">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d18a1-121">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d18a1-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-sql-server-agent-to-automatically-restart"></a><span data-ttu-id="d18a1-122">Para configurar el Agente SQL Server de modo que se reinicie automáticamente</span><span class="sxs-lookup"><span data-stu-id="d18a1-122">To configure SQL Server Agent to automatically restart</span></span>  
  
1.  <span data-ttu-id="d18a1-123">En el **Explorador de objetos**, haga clic en el signo más para expandir el servidor en el que desea configura el Agente SQL Server para que se reinicie automáticamente.</span><span class="sxs-lookup"><span data-stu-id="d18a1-123">In **Object Explorer**, click the plus sign to expand the server where you want to configure SQL Server Agent to automatically restart.</span></span>  
  
2.  <span data-ttu-id="d18a1-124">Haga clic con el botón derecho en **Agente SQL Server**y, luego, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="d18a1-124">Right-click **SQL Server Agent**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="d18a1-125">En la página **General** , seleccione **Reiniciar el Agente SQL Server automáticamente si se detiene inesperadamente**.</span><span class="sxs-lookup"><span data-stu-id="d18a1-125">On the **General** page, check **Auto restart SQL Server Agent if it stops unexpectedly**.</span></span>  
  
  
