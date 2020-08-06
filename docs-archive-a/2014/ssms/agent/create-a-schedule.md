---
title: Crear una programación | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- scheduling jobs [SQL Server]
- SQL Server Agent jobs, scheduling
- jobs [SQL Server Agent], scheduling
- schedules [SQL Server], jobs
ms.assetid: 8c7ef3b3-c06d-4a27-802d-ed329dc86ef3
author: stevestein
ms.author: sstein
ms.openlocfilehash: ac71a61163dceb06697b61ef24fce2117d57cf2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676316"
---
# <a name="create-a-schedule"></a><span data-ttu-id="a3e7d-102">Create a Schedule</span><span class="sxs-lookup"><span data-stu-id="a3e7d-102">Create a Schedule</span></span>
  <span data-ttu-id="a3e7d-103">Puede crear una programación para los trabajos del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]u Objetos de administración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a3e7d-103">You can create a schedule for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
-   <span data-ttu-id="a3e7d-104">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="a3e7d-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a3e7d-105">Seguridad</span><span class="sxs-lookup"><span data-stu-id="a3e7d-105">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a3e7d-106">**Para crear una programación, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="a3e7d-106">**To create a schedule, using:**</span></span>  
  
     [<span data-ttu-id="a3e7d-107">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a3e7d-107">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="a3e7d-108">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a3e7d-108">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="a3e7d-109">objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="a3e7d-109">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a3e7d-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="a3e7d-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a3e7d-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="a3e7d-111">Security</span></span>  
 <span data-ttu-id="a3e7d-112">Para obtener información detallada, vea [Implementar la seguridad del Agente SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="a3e7d-112">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="a3e7d-113">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a3e7d-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-schedule"></a><span data-ttu-id="a3e7d-114">Para crear una programación</span><span class="sxs-lookup"><span data-stu-id="a3e7d-114">To create a schedule</span></span>  
  
1.  <span data-ttu-id="a3e7d-115">En **Explorador de objetos,** Conéctese a una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="a3e7d-115">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="a3e7d-116">Expanda el **Agente SQL Server**, haga clic con el botón derecho en **Trabajos**y seleccione **Administrar programaciones**.</span><span class="sxs-lookup"><span data-stu-id="a3e7d-116">Expand **SQL Server Agent**, right-click **Jobs**, and select **Manage Schedules**.</span></span>  
  
3.  <span data-ttu-id="a3e7d-117">En el cuadro de diálogo **Administrar programaciones** , haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="a3e7d-117">In the **Manage Schedules** dialog box, click **New**.</span></span>  
  
4.  <span data-ttu-id="a3e7d-118">En el cuadro **Nombre** , escriba el nombre de la nueva programación.</span><span class="sxs-lookup"><span data-stu-id="a3e7d-118">In the **Name** box, type a name for the new schedule.</span></span>  
  
5.  <span data-ttu-id="a3e7d-119">Si no desea que la programación tenga efecto inmediatamente después de su creación, desactive la casilla **Habilitada** .</span><span class="sxs-lookup"><span data-stu-id="a3e7d-119">If you do not want the schedule to take effect immediately after it has been created, clear the **Enabled** check box.</span></span>  
  
6.  <span data-ttu-id="a3e7d-120">En **Tipo de programación**, seleccione una de las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="a3e7d-120">For **Schedule Type**, select one of the following:</span></span>  
  
    -   <span data-ttu-id="a3e7d-121">Para iniciar el trabajo cuando las CPU alcancen la condición de inactivas, haga clic en **Iniciar al quedar inactivas las CPU**.</span><span class="sxs-lookup"><span data-stu-id="a3e7d-121">To start the job when the CPUs reach an idle condition, click **Start whenever the CPUs become idle**.</span></span>  
  
    -   <span data-ttu-id="a3e7d-122">Si desea que una programación se ejecute varias veces, haga clic en **Periódica**.</span><span class="sxs-lookup"><span data-stu-id="a3e7d-122">If you want a schedule to run repeatedly, click **Recurring**.</span></span> <span data-ttu-id="a3e7d-123">Para establecer la programación periódica, rellene los grupos **Frecuencia**, **Frecuencia diaria**y **Duración** en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a3e7d-123">To set the recurring schedule, complete the **Frequency**, **Daily Frequency**, and **Duration** groups on the dialog.</span></span>  
  
    -   <span data-ttu-id="a3e7d-124">Si desea que la programación se ejecute solo una vez, haga clic en **Una vez**.</span><span class="sxs-lookup"><span data-stu-id="a3e7d-124">If you want the schedule to run only one time, click **One time**.</span></span> <span data-ttu-id="a3e7d-125">Para establecer la programación en **Una vez** , rellene el grupo **Única repetición** del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a3e7d-125">To set the **One time** schedule, complete the **One-time occurrence** group on the dialog box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="a3e7d-126">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a3e7d-126">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-schedule"></a><span data-ttu-id="a3e7d-127">Para crear una programación</span><span class="sxs-lookup"><span data-stu-id="a3e7d-127">To create a schedule</span></span>  
  
1.  <span data-ttu-id="a3e7d-128">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a3e7d-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a3e7d-129">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="a3e7d-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a3e7d-130">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="a3e7d-130">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- creates a schedule named RunOnce.   
    -- The schedule runs one time, at 23:30 on the day that the schedule is created.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_schedule  
        @schedule_name = N'RunOnce',  
        @freq_type = 1,  
        @active_start_time = 233000 ;  
  
    GO  
    ```  
  
 <span data-ttu-id="a3e7d-131">Para obtener más información, vea [sp_add_schedule &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a3e7d-131">For more information, see [sp_add_schedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="a3e7d-132">Usar Objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="a3e7d-132">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="a3e7d-133">**Para crear una programación**</span><span class="sxs-lookup"><span data-stu-id="a3e7d-133">**To create a schedule**</span></span>  
  
 <span data-ttu-id="a3e7d-134">Utilice la clase `JobSchedule` mediante un lenguaje de programación que elija, como Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a3e7d-134">Use the `JobSchedule` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="a3e7d-135">Para más información, consulte [Objetos de administración de SQL Server (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="a3e7d-135">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
