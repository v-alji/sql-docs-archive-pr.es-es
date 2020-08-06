---
title: Establecer el intervalo de sondeo de los servidores de destino | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- interval for polling [SQL Server]
- target servers [SQL Server], polling interval
- polling interval [SQL Server]
ms.assetid: 4ffbbefa-77fb-442e-a77c-cb8c6cab9f3c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 36517f60a99a1a844f6d14d489587eef1de9cb13
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751630"
---
# <a name="set-the-polling-interval-for-target-servers"></a><span data-ttu-id="59fa8-102">Set the Polling Interval for Target Servers</span><span class="sxs-lookup"><span data-stu-id="59fa8-102">Set the Polling Interval for Target Servers</span></span>
  <span data-ttu-id="59fa8-103">En este tema se describe cómo establecer la frecuencia con la que el [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agente actualiza la información del servidor maestro en los servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="59fa8-103">This topic describes how to set the frequency that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent refreshes information from the master to the target servers.</span></span> <span data-ttu-id="59fa8-104">Un trabajo es una serie especificada de acciones que realiza el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="59fa8-104">A job is a specified series of actions that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent performs.</span></span> <span data-ttu-id="59fa8-105">Un trabajo multiservidor es un trabajo que ejecuta un servidor maestro en uno o más servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="59fa8-105">A multiserver job is a job that a master server runs on one or more target servers.</span></span>  
  
-   <span data-ttu-id="59fa8-106">**Antes de empezar:**  [Seguridad](#Security)</span><span class="sxs-lookup"><span data-stu-id="59fa8-106">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="59fa8-107">**Para establecer el intervalo de sondeo para servidores de destino, con:**  [SQL Server Management Studio](#SSMS), [Transact-SQL](#TSQL)</span><span class="sxs-lookup"><span data-stu-id="59fa8-107">**To set the polling interval for target servers, using:**  [SQL Server Management Studio](#SSMS), [Transact-SQL](#TSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="59fa8-108">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="59fa8-108">Before You Begin</span></span>  
 <span data-ttu-id="59fa8-109">Cada servidor de destino puede ejecutar una instancia del mismo trabajo al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="59fa8-109">Each target server can run one instance of the same job at the same time.</span></span> <span data-ttu-id="59fa8-110">Cada servidor de destino sondea periódicamente al servidor maestro, descarga una copia de cualquier nuevo trabajo asignado al servidor de destino y, a continuación, se desconecta.</span><span class="sxs-lookup"><span data-stu-id="59fa8-110">Each target server periodically polls the master server, downloads a copy of any new jobs assigned to the target server, and then disconnects.</span></span> <span data-ttu-id="59fa8-111">El servidor de destino ejecuta el trabajo de manera local y, a continuación, se vuelve a conectar al servidor maestro para cargar el estado del resultado del trabajo.</span><span class="sxs-lookup"><span data-stu-id="59fa8-111">The target server runs the job locally and then reconnects to the master server to upload the job outcome status.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="59fa8-112">Si no es posible el acceso al servidor maestro cuando el servidor de destino intenta cargar el estado del trabajo, dicho estado de trabajo se coloca en la cola hasta que se pueda obtener acceso al servidor principal.</span><span class="sxs-lookup"><span data-stu-id="59fa8-112">If the master server is inaccessible when the target server tries to upload job status, the job status is spooled until the master server can be accessed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="59fa8-113">Seguridad</span><span class="sxs-lookup"><span data-stu-id="59fa8-113">Security</span></span>  
 <span data-ttu-id="59fa8-114">Para obtener información detallada, vea [Implement SQL Server Agent Security](implement-sql-server-agent-security.md) y [Choose the Right SQL Server Agent Service Account for Multiserver Environments](choose-the-right-sql-server-agent-service-account-for-multiserver-environments.md).</span><span class="sxs-lookup"><span data-stu-id="59fa8-114">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md) and [Choose the Right SQL Server Agent Service Account for Multiserver Environments](choose-the-right-sql-server-agent-service-account-for-multiserver-environments.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="59fa8-115">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="59fa8-115">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="59fa8-116">**Para establecer el intervalo de sondeo para servidores de destino**</span><span class="sxs-lookup"><span data-stu-id="59fa8-116">**To set the polling interval for target servers**</span></span>  
  
1.  <span data-ttu-id="59fa8-117">En **Explorador de objetos,** Conéctese a una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="59fa8-117">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="59fa8-118">Haga clic con el botón derecho en **Agente SQL Server**, seleccione **Administración multiservidor**y, luego, haga clic en **Administrar servidores de destino**.</span><span class="sxs-lookup"><span data-stu-id="59fa8-118">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Manage Target Servers**.</span></span>  
  
3.  <span data-ttu-id="59fa8-119">En la pestaña **Estado de servidor de destino** , haga clic en **Exponer instrucciones**.</span><span class="sxs-lookup"><span data-stu-id="59fa8-119">On the **Target Server Status** tab, click **Post Instructions**.</span></span>  
  
4.  <span data-ttu-id="59fa8-120">En la lista **Tipo de instrucción** , seleccione **Establecer intervalo de sondeo**.</span><span class="sxs-lookup"><span data-stu-id="59fa8-120">In the **Instruction type** list, select **Set polling interval**.</span></span>  
  
5.  <span data-ttu-id="59fa8-121">En la casilla **Intervalo de sondeo** , escriba el número de segundos (entre 10 y 28.800) que deben transcurrir antes de que el servidor de destino sondee al servidor maestro.</span><span class="sxs-lookup"><span data-stu-id="59fa8-121">In the **Polling interval** box, enter the number of seconds from 10 through 28,800 that must pass before the target server polls the master server.</span></span>  
  
6.  <span data-ttu-id="59fa8-122">En **Destinatarios**, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="59fa8-122">Under **Recipients**, do one of the following:</span></span>  
  
    1.  <span data-ttu-id="59fa8-123">Haga clic en **Todos los servidores de destino** si todos los servidores de destino comparten el mismo intervalo de sondeo.</span><span class="sxs-lookup"><span data-stu-id="59fa8-123">Click **All target servers** if all target servers share the same polling interval.</span></span>  
  
    2.  <span data-ttu-id="59fa8-124">Haga clic en **Estos servidores de destino** si no todos los servidores de destino comparten el mismo intervalo de sondeo y, a continuación, seleccione cada servidor de destino que usará este intervalo de sondeo.</span><span class="sxs-lookup"><span data-stu-id="59fa8-124">Click **These target servers** if not all target servers share the same polling interval, and then select each target server that will use this polling interval.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="59fa8-125">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="59fa8-125">Using Transact-SQL</span></span>  
 <span data-ttu-id="59fa8-126">**Para establecer el intervalo de sondeo para servidores de destino**</span><span class="sxs-lookup"><span data-stu-id="59fa8-126">**To set the polling interval for target servers**</span></span>  
  
1.  <span data-ttu-id="59fa8-127">En el Explorador de objetos, conéctese a una instancia del Motor de base de datos y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="59fa8-127">In Object Explorer, connect to an instance of the Database Engine, and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="59fa8-128">En la barra de herramientas, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="59fa8-128">On the toolbar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="59fa8-129">En la ventana de consulta, use el sp_post_msx_operation &#40;procedimiento almacenado del sistema [&#41;de Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-post-msx-operation-transact-sql) para establecer el intervalo de sondeo para los servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="59fa8-129">In the query window, use the [sp_post_msx_operation &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-post-msx-operation-transact-sql) system stored procedure to set the polling interval for target servers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59fa8-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="59fa8-130">See Also</span></span>  
 [<span data-ttu-id="59fa8-131">dbo.sysdownloadlist &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="59fa8-131">dbo.sysdownloadlist &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-tables/dbo-sysdownloadlist-transact-sql)  
  
  
