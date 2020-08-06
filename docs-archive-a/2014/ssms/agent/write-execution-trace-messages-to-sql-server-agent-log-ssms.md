---
title: Escribir mensajes de seguimiento de ejecución en el registro de errores de Agente SQL Server (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], SQL Server Agent
- writing trace messages
- traces [SQL Server], SQL Server Agent logs
- SQL Server Agent, errors
- errors [SQL Server Agent]
ms.assetid: 90e3731e-6fae-43db-833e-9accecdd1c03
author: stevestein
ms.author: sstein
ms.openlocfilehash: 38b08452ef2680b654dd735b901488cb5f5f5f97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747401"
---
# <a name="write-execution-trace-messages-to-the-sql-server-agent-error-log-sql-server-management-studio"></a><span data-ttu-id="9273e-102">Write Execution Trace Messages to the SQL Server Agent Error Log (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="9273e-102">Write Execution Trace Messages to the SQL Server Agent Error Log (SQL Server Management Studio)</span></span>
  <span data-ttu-id="9273e-103">En este tema se describe cómo configurar el [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agente para que incluya mensajes de seguimiento de ejecución en su registro de errores en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9273e-103">This topic describes how to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to include execution trace messages in its error log in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="9273e-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="9273e-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9273e-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="9273e-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9273e-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="9273e-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="9273e-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="9273e-107">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="9273e-108">Para escribir mensajes de seguimiento de ejecución en el registro de errores del Agente SQL Server mediante SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9273e-108">To write execution trace messages to the SQL Server Agent Error Log using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9273e-109">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="9273e-109">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="9273e-110">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="9273e-110">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="9273e-111">El Explorador de objetos solo muestra el nodo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] si se tiene permiso para usarlo.</span><span class="sxs-lookup"><span data-stu-id="9273e-111">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
-   <span data-ttu-id="9273e-112">Dado que esta opción puede hacer que el tamaño del registro de errores sea muy grande, solo se incluyen los mensajes de seguimiento de ejecución en los registros de errores del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cuando se investiga un problema específico del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9273e-112">Because this option can cause the error log to become large, only include execution trace messages in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error logs when investigating a specific [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent problem.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9273e-113">Seguridad</span><span class="sxs-lookup"><span data-stu-id="9273e-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9273e-114">Permisos</span><span class="sxs-lookup"><span data-stu-id="9273e-114">Permissions</span></span>  
 <span data-ttu-id="9273e-115">Para realizar sus funciones, el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe configurarse de modo que use las credenciales de una cuenta que sea miembro del rol fijo de servidor **sysadmin** en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9273e-115">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9273e-116">La cuenta debe tener los siguientes permisos de Windows:</span><span class="sxs-lookup"><span data-stu-id="9273e-116">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="9273e-117">Iniciar sesión como servicio (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="9273e-117">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="9273e-118">Reemplazar un token de nivel de proceso (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="9273e-118">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="9273e-119">Omitir la comprobación transversal (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="9273e-119">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="9273e-120">Ajustar las cuotas de memoria de un proceso (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="9273e-120">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="9273e-121">Para obtener más información acerca de los permisos de Windows necesarios para la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cuenta de servicio del agente, consulte [seleccionar una cuenta para el servicio de Agente SQL Server](select-an-account-for-the-sql-server-agent-service.md) y [configurar los permisos y las cuentas de servicio de Windows](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="9273e-121">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="SSMSProcedure"></a>   
#### <a name="to-write-execution-trace-messages-to-the-sql-server-agent-error-log"></a><span data-ttu-id="9273e-122">Para escribir mensajes de seguimiento de ejecución en el registro de errores del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="9273e-122">To write execution trace messages to the SQL Server Agent error log</span></span>  
  
1.  <span data-ttu-id="9273e-123">En el **Explorador de objetos**, haga clic en el signo más para expandir el servidor que contiene el registro de errores del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en el que desea escribir mensajes de seguimiento de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9273e-123">In **Object Explorer**, click the plus sign to expand the server that contains the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log to which you want to write execution trace messages.</span></span>  
  
2.  <span data-ttu-id="9273e-124">Haga clic con el botón derecho en **Agente SQL Server** y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="9273e-124">Right-click **SQL Server Agent** and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="9273e-125">En el cuadro de diálogo **propiedades de Agente SQL Server-**_SERVER_NAME_ , en **registro de errores** en la página **General** , active la casilla **incluir mensajes de seguimiento de ejecución** .</span><span class="sxs-lookup"><span data-stu-id="9273e-125">In the **SQL Server Agent Properties -**_server_name_ dialog box, under **Error log** on the **General** page, select the **Include execution trace messages** check box.</span></span>  
  
4.  <span data-ttu-id="9273e-126">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="9273e-126">Click **OK**.</span></span>  
  
  
