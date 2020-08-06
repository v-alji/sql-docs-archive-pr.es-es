---
title: Ver actividad de trabajo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- viewing job activity
- jobs [SQL Server Agent], viewing
- SQL Server Agent jobs, viewing
- displaying job activity
ms.assetid: 5c284e5e-7775-435d-ac49-f3f12a27ddc7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 56b159952c83ed243c4c5d8012c76e5a2a248519
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750442"
---
# <a name="view-job-activity"></a><span data-ttu-id="e414e-102">Ver actividad de trabajo</span><span class="sxs-lookup"><span data-stu-id="e414e-102">View Job Activity</span></span>
  <span data-ttu-id="e414e-103">En este tema se describe cómo ver el estado de ejecución de los trabajos del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e414e-103">This topic describes how to view the runtime state of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="e414e-104">Cuando se inicia el servicio del Agente [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], se crea una nueva sesión y la tabla **sysjobactivity** de la base de datos **msdb** se rellena con todos los trabajos definidos que existen.</span><span class="sxs-lookup"><span data-stu-id="e414e-104">When the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service starts, a new session is created and the **sysjobactivity** table in the **msdb** database is populated with all the existing defined jobs.</span></span> <span data-ttu-id="e414e-105">En esta tabla se registra la actividad y el estado actuales de los trabajos.</span><span class="sxs-lookup"><span data-stu-id="e414e-105">This table records current job activity and status.</span></span> <span data-ttu-id="e414e-106">Puede utilizar el Monitor de actividad de trabajo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ver el estado actual de los trabajos.</span><span class="sxs-lookup"><span data-stu-id="e414e-106">You can use the Job Activity Monitor in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to view the current state of jobs.</span></span> <span data-ttu-id="e414e-107">Si el servicio del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] finaliza inesperadamente, puede consultar la tabla **sysjobactivity** para ver qué trabajos se estaban ejecutando cuando finalizó el servicio.</span><span class="sxs-lookup"><span data-stu-id="e414e-107">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service unexpectedly terminates, you can refer to the **sysjobactivity** table to see which jobs were being executed when the service terminated.</span></span>  
  
 <span data-ttu-id="e414e-108">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="e414e-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e414e-109">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="e414e-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e414e-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="e414e-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e414e-111">**Para ver la actividad de los trabajos, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="e414e-111">**To view job activity, using:**</span></span>  
  
     [<span data-ttu-id="e414e-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e414e-112">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="e414e-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e414e-113">Transact-SQL</span></span>](#TSQL)  
  
## <a name="before-you-begin"></a><span data-ttu-id="e414e-114">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="e414e-114">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e414e-115">Seguridad</span><span class="sxs-lookup"><span data-stu-id="e414e-115">Security</span></span>  
 <span data-ttu-id="e414e-116">Para obtener información detallada, vea [Implementar la seguridad del Agente SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="e414e-116">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="e414e-117">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e414e-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-job-activity"></a><span data-ttu-id="e414e-118">Para ver la actividad de los trabajos</span><span class="sxs-lookup"><span data-stu-id="e414e-118">To view job activity</span></span>  
  
1.  <span data-ttu-id="e414e-119">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="e414e-119">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="e414e-120">Expanda **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="e414e-120">Expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="e414e-121">Haga clic con el botón derecho en **Monitor de actividad de trabajo** y, luego, haga clic en **Ver actividad de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="e414e-121">Right-click **Job Activity Monitor** and click **View Job Activity**.</span></span>  
  
4.  <span data-ttu-id="e414e-122">En el **Monitor de actividad de trabajo**, puede ver los detalles de cada trabajo definido para este servidor.</span><span class="sxs-lookup"><span data-stu-id="e414e-122">In the **Job Activity Monitor**, you can view details about each job that is defined for this server.</span></span>  
  
5.  <span data-ttu-id="e414e-123">Haga clic con el botón secundario en un trabajo para iniciarlo, detenerlo, habilitarlo o deshabilitarlo, actualizar el estado que se muestra en el Monitor de actividad de trabajo, eliminarlo o ver su historial o sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="e414e-123">Right-click a job to start it, stop it, enable or disable it, refresh its status as displayed in the Job Activity Monitor, delete it, or view its history or properties.</span></span>  <span data-ttu-id="e414e-124">Para iniciar, detener, habilitar o deshabilitar, o actualizar varios trabajos, seleccione varias filas en el Monitor de actividad de trabajo y haga clic con el botón secundario en la selección.</span><span class="sxs-lookup"><span data-stu-id="e414e-124">To start, stop, enable or disable, or refresh multiple jobs, select multiple rows in the Job Activity Monitor, and right-click your selection.</span></span>  
  
6.  <span data-ttu-id="e414e-125">Para actualizar el Monitor de actividad de trabajo, haga clic en **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="e414e-125">To update the Job Activity Monitor, click **Refresh**.</span></span> <span data-ttu-id="e414e-126">Para ver menos filas, haga clic en **Filtro** y escriba los parámetros del filtro.</span><span class="sxs-lookup"><span data-stu-id="e414e-126">To view fewer rows, click **Filter** and enter filter parameters.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="e414e-127">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e414e-127">Using Transact-SQL</span></span>  
  
#### <a name="to-view-job-activity"></a><span data-ttu-id="e414e-128">Para ver la actividad de los trabajos</span><span class="sxs-lookup"><span data-stu-id="e414e-128">To view job activity</span></span>  
  
1.  <span data-ttu-id="e414e-129">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e414e-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e414e-130">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="e414e-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e414e-131">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="e414e-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- lists activity for all jobs that the current user has permission to view.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_help_jobactivity ;  
    GO  
    ```  
  
 <span data-ttu-id="e414e-132">Para obtener más información, vea [sp_help_jobactivity &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-help-jobactivity-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e414e-132">For more information, see [sp_help_jobactivity &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-jobactivity-transact-sql).</span></span>  
  
  
