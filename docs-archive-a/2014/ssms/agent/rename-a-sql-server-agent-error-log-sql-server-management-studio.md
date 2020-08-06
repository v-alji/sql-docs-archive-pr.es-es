---
title: Cambiar el nombre del registro de errores del Agente SQL Server (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], SQL Server Agent
- renaming SQL Server Agent error log
- SQL Server Agent, errors
- errors [SQL Server Agent]
ms.assetid: dee2b199-48af-44cb-9177-d029a5edb169
author: stevestein
ms.author: sstein
ms.openlocfilehash: c1c85550a29bfff316ffc275ba2d4e4df10686d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677342"
---
# <a name="rename-a-sql-server-agent-error-log-sql-server-management-studio"></a><span data-ttu-id="b3b29-102">Rename a SQL Server Agent Error Log (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="b3b29-102">Rename a SQL Server Agent Error Log (SQL Server Management Studio)</span></span>
  <span data-ttu-id="b3b29-103">En este tema se describe cómo cambiar el nombre del archivo donde [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se escriben los errores del agente en mediante [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b3b29-103">This topic describes how to rename the file where [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent errors are written in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="b3b29-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="b3b29-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b3b29-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="b3b29-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b3b29-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="b3b29-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b3b29-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="b3b29-107">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="b3b29-108">Para cambiar el nombre de un registro de errores del Agente SQL Server utilizando SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b3b29-108">To rename a SQL Server Agent error log using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b3b29-109">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="b3b29-109">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b3b29-110">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="b3b29-110">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="b3b29-111">El Explorador de objetos solo muestra el nodo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] si se tiene permiso para usarlo.</span><span class="sxs-lookup"><span data-stu-id="b3b29-111">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b3b29-112">no escribirá nada en el archivo de registro nuevo hasta que se reinicie el servicio del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b3b29-112">Agent will not write to the new log file until the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service is restarted.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b3b29-113">Seguridad</span><span class="sxs-lookup"><span data-stu-id="b3b29-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b3b29-114">Permisos</span><span class="sxs-lookup"><span data-stu-id="b3b29-114">Permissions</span></span>  
 <span data-ttu-id="b3b29-115">Para realizar sus funciones, el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe configurarse de modo que use las credenciales de una cuenta que sea miembro del rol fijo de servidor **sysadmin** en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b3b29-115">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b3b29-116">La cuenta debe tener los siguientes permisos de Windows:</span><span class="sxs-lookup"><span data-stu-id="b3b29-116">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="b3b29-117">Iniciar sesión como servicio (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="b3b29-117">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="b3b29-118">Reemplazar un token de nivel de proceso (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="b3b29-118">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="b3b29-119">Omitir la comprobación transversal (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="b3b29-119">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="b3b29-120">Ajustar las cuotas de memoria de un proceso (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="b3b29-120">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="b3b29-121">Para obtener más información acerca de los permisos de Windows necesarios para la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cuenta de servicio del agente, consulte [seleccionar una cuenta para el servicio de Agente SQL Server](select-an-account-for-the-sql-server-agent-service.md) y [configurar los permisos y las cuentas de servicio de Windows](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="b3b29-121">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b3b29-122">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b3b29-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-a-sql-server-agent-error-log"></a><span data-ttu-id="b3b29-123">Para cambiar el nombre del registro de errores del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="b3b29-123">To rename a SQL Server Agent error log</span></span>  
  
1.  <span data-ttu-id="b3b29-124">En el **Explorador de objetos**, haga clic en el signo más para expandir el servidor que contiene el registro de errores del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cuyo nombre desea cambiar.</span><span class="sxs-lookup"><span data-stu-id="b3b29-124">In **Object Explorer**, click the plus sign to expand the server that contains the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log that you want to rename.</span></span>  
  
2.  <span data-ttu-id="b3b29-125">Haga clic en el signo más para expandir **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="b3b29-125">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="b3b29-126">Haga clic con el botón derecho en la carpeta **Registros de errores** y seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="b3b29-126">Right-click the **Error Logs** folder and select **Configure**.</span></span>  
  
4.  <span data-ttu-id="b3b29-127">En el cuadro de diálogo **Configurar registros de errores del Agente SQL Server** , en el cuadro **Archivo de registro de errores** , escriba la nueva ruta de acceso y nombre de archivo para el registro de errores.</span><span class="sxs-lookup"><span data-stu-id="b3b29-127">In the **Configure SQL Server Agent Error Logs** dialog box, in the **Error log file** box, enter the new file path and file name for the error log.</span></span> <span data-ttu-id="b3b29-128">Como alternativa, haga clic en los puntos suspensivos **(...)** para abrir el cuadro de diálogo **Especificar ubicación de registro de errores de agente** .</span><span class="sxs-lookup"><span data-stu-id="b3b29-128">Alternately, click the ellipsis **(...)** to open the **Specify agent error log location** dialog box.</span></span>  
  
5.  <span data-ttu-id="b3b29-129">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b3b29-129">When finished, click **OK**.</span></span>  
  
  
