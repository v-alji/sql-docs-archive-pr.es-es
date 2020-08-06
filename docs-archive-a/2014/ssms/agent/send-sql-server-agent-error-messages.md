---
title: Enviar mensajes de error del Agente SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- messages [SQL Server], SQL Server Agent
- sending messages
- SQL Server Agent, errors
- errors [SQL Server Agent]
ms.assetid: 2597d0d7-951a-48cf-989f-abb67b9fdb36
author: stevestein
ms.author: sstein
ms.openlocfilehash: 03e38b02188eaced65a86b22ed4f22cb6984ce0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674529"
---
# <a name="send-sql-server-agent-error-messages"></a><span data-ttu-id="9e1b1-102">Send SQL Server Agent Error Messages</span><span class="sxs-lookup"><span data-stu-id="9e1b1-102">Send SQL Server Agent Error Messages</span></span>
  <span data-ttu-id="9e1b1-103">En este tema se describe cómo configurar el [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agente para que envíe sus mensajes de error mediante net send en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9e1b1-103">This topic describes how to how to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to send its error messages by way of net send in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="9e1b1-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="9e1b1-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9e1b1-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="9e1b1-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9e1b1-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="9e1b1-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="9e1b1-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="9e1b1-107">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="9e1b1-108">Para enviar mensajes de error del Agente SQL Server utilizando SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9e1b1-108">To send SQL Server Agent error messages using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9e1b1-109">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="9e1b1-109">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="9e1b1-110">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="9e1b1-110">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="9e1b1-111">El Explorador de objetos solo muestra el nodo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] si se tiene permiso para usarlo.</span><span class="sxs-lookup"><span data-stu-id="9e1b1-111">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
-   <span data-ttu-id="9e1b1-112">Para recibir eventos mediante NET SEND, el servicio [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Messenger debe estar en ejecución.</span><span class="sxs-lookup"><span data-stu-id="9e1b1-112">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Messenger service must be running to receive net send events.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9e1b1-113">Seguridad</span><span class="sxs-lookup"><span data-stu-id="9e1b1-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9e1b1-114">Permisos</span><span class="sxs-lookup"><span data-stu-id="9e1b1-114">Permissions</span></span>  
 <span data-ttu-id="9e1b1-115">Para realizar sus funciones, el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe configurarse de modo que use las credenciales de una cuenta que sea miembro del rol fijo de servidor **sysadmin** en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9e1b1-115">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9e1b1-116">La cuenta debe tener los siguientes permisos de Windows:</span><span class="sxs-lookup"><span data-stu-id="9e1b1-116">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="9e1b1-117">Iniciar sesión como servicio (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="9e1b1-117">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="9e1b1-118">Reemplazar un token de nivel de proceso (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="9e1b1-118">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="9e1b1-119">Omitir la comprobación transversal (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="9e1b1-119">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="9e1b1-120">Ajustar las cuotas de memoria de un proceso (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="9e1b1-120">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="9e1b1-121">Para obtener más información acerca de los permisos de Windows necesarios para la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cuenta de servicio del agente, consulte [seleccionar una cuenta para el servicio de Agente SQL Server](select-an-account-for-the-sql-server-agent-service.md) y [configurar los permisos y las cuentas de servicio de Windows](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="9e1b1-121">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9e1b1-122">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9e1b1-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-send-sql-server-agent-error-messages"></a><span data-ttu-id="9e1b1-123">Para enviar mensajes de error del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="9e1b1-123">To send SQL Server Agent error messages</span></span>  
  
1.  <span data-ttu-id="9e1b1-124">En el **Explorador de objetos**, haga clic en el signo más para expandir el servidor que contiene el registro de errores del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] desde el que desea enviar mensajes de error mediante NET SEND.</span><span class="sxs-lookup"><span data-stu-id="9e1b1-124">In **Object Explorer**, click the plus sign to expand the server that contains the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log from which you want to send error messages via net send.</span></span>  
  
2.  <span data-ttu-id="9e1b1-125">Haga clic con el botón derecho en **Agente SQL Server** y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="9e1b1-125">Right-click **SQL Server Agent** and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="9e1b1-126">En el cuadro de diálogo **propiedades de Agente SQL Server-**_SERVER_NAME_ , en **registro de errores** en la página **General** , escriba el nombre de usuario o el nombre del equipo al que desea enviar mensajes de error en el cuadro **destinatario de net send** .</span><span class="sxs-lookup"><span data-stu-id="9e1b1-126">In the **SQL Server Agent Properties -**_server_name_ dialog box, under **Error log** on the **General** page, , type the user name or computer name to which you want to send error messages in the **Net send recipient** box.</span></span>  
  
4.  <span data-ttu-id="9e1b1-127">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="9e1b1-127">Click **OK**.</span></span>  
  
  
