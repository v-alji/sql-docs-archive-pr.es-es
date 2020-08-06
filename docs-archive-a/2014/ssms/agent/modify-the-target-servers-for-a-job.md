---
title: Modificar los servidores de destino para un trabajo | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- modifying target servers
- SQL Server Agent jobs, target servers
- target servers [SQL Server], modifying
ms.assetid: 9dbe24f2-acec-4aa2-920c-e8e96efa18e4
author: stevestein
ms.author: sstein
ms.openlocfilehash: 246a5bb59a681a70734cc8cabef4f724cda1b52e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671331"
---
# <a name="modify-the-target-servers-for-a-job"></a><span data-ttu-id="60923-102">Modify the Target Servers for a Job</span><span class="sxs-lookup"><span data-stu-id="60923-102">Modify the Target Servers for a Job</span></span>
  <span data-ttu-id="60923-103">En este tema se describe cómo cambiar los servidores de destino para los [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trabajos del agente en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="60923-103">This topic describes how to change the target servers for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="60923-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="60923-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="60923-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="60923-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="60923-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="60923-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="60923-107">**Para modificar los servidores de destino para un trabajo, usando:**</span><span class="sxs-lookup"><span data-stu-id="60923-107">**To modify the target servers for a job, using:**</span></span>  
  
     [<span data-ttu-id="60923-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="60923-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="60923-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="60923-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="60923-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="60923-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="60923-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="60923-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="60923-112">Permisos</span><span class="sxs-lookup"><span data-stu-id="60923-112">Permissions</span></span>  
 <span data-ttu-id="60923-113">De forma predeterminada, los miembros del rol de servidor fijo sysadmin pueden ejecutar este procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="60923-113">By default, members of the sysadmin fixed server role can execute this stored procedure.</span></span> <span data-ttu-id="60923-114">Al resto de usuarios se les debe conceder uno de los siguientes roles fijos de base de datos del Agente SQL Server en la base de datos msdb:</span><span class="sxs-lookup"><span data-stu-id="60923-114">Other users must be granted one of the following SQL Server Agent fixed database roles in the msdb database:</span></span>  
  
1.  `SQLAgentUserRole`  
  
2.  `SQLAgentReaderRole`  
  
3.  <span data-ttu-id="60923-115">SQLAgentOperatorRole</span><span class="sxs-lookup"><span data-stu-id="60923-115">SQLAgentOperatorRole</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="60923-116">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="60923-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-the-target-servers-for-a-job"></a><span data-ttu-id="60923-117">Para modificar los servidores de destino para un trabajo</span><span class="sxs-lookup"><span data-stu-id="60923-117">To modify the target servers for a job</span></span>  
  
1.  <span data-ttu-id="60923-118">En **Explorador de objetos,** Conéctese a una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="60923-118">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="60923-119">Expanda **Agente SQL Server**, expanda **Trabajos**, haga clic con el botón derecho en un trabajo y, luego, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="60923-119">Expand **SQL Server Agent**, expand **Jobs**, right-click a job, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="60923-120">En el cuadro de diálogo **Propiedades del trabajo** , seleccione la página **Destinos**y haga clic en **Destino en servidor local**o **Destino en varios servidores**.</span><span class="sxs-lookup"><span data-stu-id="60923-120">In the **Job Properties** dialog, select the **Targets**page, and click **Target local server**, or **Target multiple servers**.</span></span>  
  
     <span data-ttu-id="60923-121">Si elige **Destino en varios servidores**, designe los servidores que serán destinos para el trabajo activando la casilla situada a la izquierda del nombre del servidor.</span><span class="sxs-lookup"><span data-stu-id="60923-121">If you choose **Target multiple servers**, designate the servers that will be targets for the job by checking the box to the left of the server name.</span></span> <span data-ttu-id="60923-122">Compruebe que las casillas de los servidores que no serán destinos del trabajo están desactivadas.</span><span class="sxs-lookup"><span data-stu-id="60923-122">Verify that the check boxes for servers that will not be targets of the job are unchecked.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="60923-123">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="60923-123">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-the-target-servers-for-a-job"></a><span data-ttu-id="60923-124">Para modificar los servidores de destino para un trabajo</span><span class="sxs-lookup"><span data-stu-id="60923-124">To modify the target servers for a job</span></span>  
  
1.  <span data-ttu-id="60923-125">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60923-125">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="60923-126">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="60923-126">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="60923-127">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="60923-127">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="60923-128">En este ejemplo se asigna el trabajo multiservidor Weekly Sales Backups al servidor SEATTLE2.</span><span class="sxs-lookup"><span data-stu-id="60923-128">This example assigns the multiserver job Weekly Sales Backups to the server SEATTLE2.</span></span>  
  
```  
USE msdb ;  
GO  
  
EXEC dbo.sp_add_jobserver  
    @job_name = N'Weekly Sales Backups',   
    @server_name = N'SEATTLE2' ;   
GO  
  
```  
  
 <span data-ttu-id="60923-129">Para obtener más información, vea [sp_add_jobserver &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="60923-129">For more information, see [sp_add_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60923-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="60923-130">See Also</span></span>  
 [<span data-ttu-id="60923-131">Administración automatizada en una empresa</span><span class="sxs-lookup"><span data-stu-id="60923-131">Automated Administration Across an Enterprise</span></span>](automated-administration-across-an-enterprise.md)  
  
  
