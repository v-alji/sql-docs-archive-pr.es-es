---
title: Notificar a un operador el estado de un trabajo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- status information [SQL Server], jobs
- jobs [SQL Server Agent], notification options
- SQL Server Agent jobs, status
- jobs [SQL Server Agent], status
- SQL Server Agent jobs, notification options
- notifications [SQL Server], job status
ms.assetid: e7399505-27ac-48d9-a637-73bf92b9df49
author: stevestein
ms.author: sstein
ms.openlocfilehash: a202327ad63cf7ef8f51d3572b257816ee6d9419
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671326"
---
# <a name="notify-an-operator-of-job-status"></a><span data-ttu-id="6866a-102">Notify an Operator of Job Status</span><span class="sxs-lookup"><span data-stu-id="6866a-102">Notify an Operator of Job Status</span></span>
  <span data-ttu-id="6866a-103">En este tema se describe cómo establecer opciones de notificación en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] o objetos de administración de SQL Server, por lo que el [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agente puede enviar notificaciones a los operadores acerca de los trabajos.</span><span class="sxs-lookup"><span data-stu-id="6866a-103">This topic describes how to set notification options in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects, so [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent can send notifications to operators about jobs.</span></span>  
  
 <span data-ttu-id="6866a-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="6866a-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6866a-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="6866a-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6866a-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="6866a-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6866a-107">**Para notificar a un operador el estado de un trabajo, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="6866a-107">**To notify an operator of job status, using:**</span></span>  
  
     [<span data-ttu-id="6866a-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6866a-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="6866a-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6866a-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="6866a-110">objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="6866a-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6866a-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="6866a-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6866a-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="6866a-112">Security</span></span>  
 <span data-ttu-id="6866a-113">Para obtener información detallada, vea [Implementar la seguridad del Agente SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="6866a-113">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="6866a-114">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6866a-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-notify-an-operator-of-job-status"></a><span data-ttu-id="6866a-115">Para notificar a un operador el estado de un trabajo</span><span class="sxs-lookup"><span data-stu-id="6866a-115">To notify an operator of job status</span></span>  
  
1.  <span data-ttu-id="6866a-116">En **Explorador de objetos,** Conéctese a una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="6866a-116">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="6866a-117">Expanda **Agente SQL Server**, **Trabajos**, haga clic con el botón derecho en el trabajo que desea editar y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6866a-117">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to edit, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="6866a-118">En el cuadro de diálogo **Propiedades del trabajo** , seleccione la página **Notificaciones** .</span><span class="sxs-lookup"><span data-stu-id="6866a-118">In the **Job Properties** dialog box, select the **Notifications** page.</span></span>  
  
4.  <span data-ttu-id="6866a-119">Si desea enviar una notificación a un operador por **correo electrónico**, seleccione un operador en la lista y elija alguna de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="6866a-119">If you want to notify an operator by e-mail, check **E-mail**, select an operator from the list, and then select one of the following:</span></span>  
  
    -   <span data-ttu-id="6866a-120">**Si el trabajo tiene éxito** para notificar al operador cuando el trabajo concluye correctamente.</span><span class="sxs-lookup"><span data-stu-id="6866a-120">**When the job succeeds** to notify the operator when the job completes successfully.</span></span>  
  
    -   <span data-ttu-id="6866a-121">**Si el trabajo no tiene éxito** para notificar al operador cuando el trabajo se completa de manera incorrecta.</span><span class="sxs-lookup"><span data-stu-id="6866a-121">**When the job fails** to notify the operator when the job completes unsuccessfully.</span></span>  
  
    -   <span data-ttu-id="6866a-122">**Si el trabajo termina** para notificar al operador independientemente del estado de la finalización.</span><span class="sxs-lookup"><span data-stu-id="6866a-122">**When the job completes** to notify the operator regardless of completion status.</span></span>  
  
5.  <span data-ttu-id="6866a-123">Si desea enviar una notificación a un operador por buscapersonas, active la opción **Buscapersonas**, seleccione un operador en la lista y elija alguna de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="6866a-123">If you want to notify an operator by pager, check **Page**, select an operator from the list, and then select one of the following:</span></span>  
  
    -   <span data-ttu-id="6866a-124">**Si el trabajo tiene éxito** para notificar al operador cuando el trabajo concluye correctamente.</span><span class="sxs-lookup"><span data-stu-id="6866a-124">**When the job succeeds** to notify the operator when the job completes successfully.</span></span>  
  
    -   <span data-ttu-id="6866a-125">**Si el trabajo no tiene éxito** para notificar al operador cuando el trabajo se completa de manera incorrecta.</span><span class="sxs-lookup"><span data-stu-id="6866a-125">**When the job fails** to notify the operator when the job completes unsuccessfully.</span></span>  
  
    -   <span data-ttu-id="6866a-126">**Si el trabajo termina** para notificar al operador independientemente del estado de la finalización.</span><span class="sxs-lookup"><span data-stu-id="6866a-126">**When the job completes** to notify the operator regardless of completion status.</span></span>  
  
6.  <span data-ttu-id="6866a-127">Si desea enviar una notificación a un operador por envío de red, active la opción **Envío de red**, seleccione un operador en la lista y elija alguna de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="6866a-127">If you want to notify an operator by net send, check **Net send**, select an operator from the list, and then select one of the following:</span></span>  
  
    -   <span data-ttu-id="6866a-128">**Si el trabajo tiene éxito** para notificar al operador cuando el trabajo concluye correctamente.</span><span class="sxs-lookup"><span data-stu-id="6866a-128">**When the job succeeds** to notify the operator when the job completes successfully.</span></span>  
  
    -   <span data-ttu-id="6866a-129">**Si el trabajo no tiene éxito** para notificar al operador cuando el trabajo se completa de manera incorrecta.</span><span class="sxs-lookup"><span data-stu-id="6866a-129">**When the job fails** to notify the operator when the job completes unsuccessfully.</span></span>  
  
    -   <span data-ttu-id="6866a-130">**Si el trabajo termina** para notificar al operador independientemente del estado de la finalización.</span><span class="sxs-lookup"><span data-stu-id="6866a-130">**When the job completes** to notify the operator regardless of completion status.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="6866a-131">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6866a-131">Using Transact-SQL</span></span>  
  
#### <a name="to-notify-an-operator-of-job-status"></a><span data-ttu-id="6866a-132">Para notificar a un operador el estado de un trabajo</span><span class="sxs-lookup"><span data-stu-id="6866a-132">To notify an operator of job status</span></span>  
  
1.  <span data-ttu-id="6866a-133">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6866a-133">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6866a-134">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="6866a-134">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6866a-135">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="6866a-135">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- adds an e-mail notification for the specified alert (Test Alert).  
    -- This example assumes that Test Alert already exists and that Fran??ois Ajenstat is a valid operator name.  
    USE msdb ;  
    GO  
    EXEC dbo.sp_add_notification   
    @alert_name = N'Test Alert',   
    @operator_name = N'Fran??ois Ajenstat',   
    @notification_method = 1 ;  
    GO  
    ```  
  
 <span data-ttu-id="6866a-136">Para obtener más información, vea [sp_add_notification &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6866a-136">For more information, see [sp_add_notification &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="6866a-137">Usar Objetos de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="6866a-137">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="6866a-138">**Para notificar a un operador el estado de un trabajo**</span><span class="sxs-lookup"><span data-stu-id="6866a-138">**To notify an operator of job status**</span></span>  
  
 <span data-ttu-id="6866a-139">Utilice la clase `Job` mediante un lenguaje de programación que elija, como Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6866a-139">Use the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="6866a-140">Para más información, consulte [Objetos de administración de SQL Server (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="6866a-140">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
