---
title: Asignar alertas a un operador | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- assigning alerts to operator
- SQL Server Agent, alerts
- alerts [SQL Server], assigning to operator
- jobs [SQL Server Agent], operators
- notifications [SQL Server], job status
ms.assetid: aa818155-6fa2-4565-a09f-5c7e31c89754
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3cc238b952c03595035856f377b6fdbb9eaf5e2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672364"
---
# <a name="assign-alerts-to-an-operator"></a><span data-ttu-id="a7608-102">Assign Alerts to an Operator</span><span class="sxs-lookup"><span data-stu-id="a7608-102">Assign Alerts to an Operator</span></span>
  <span data-ttu-id="a7608-103">En este tema se describe cómo asignar [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alertas del agente a los operadores para que puedan recibir notificaciones sobre los trabajos en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a7608-103">This topic describes how to assign [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts to operators so they can receive notifications about jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="a7608-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="a7608-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a7608-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="a7608-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a7608-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="a7608-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="a7608-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="a7608-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a7608-108">**Para asignar alertas a un operador, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="a7608-108">**To assign alerts to an operator, using:**</span></span>  
  
     [<span data-ttu-id="a7608-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a7608-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a7608-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a7608-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a7608-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="a7608-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="a7608-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="a7608-112">Limitations and Restrictions</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="a7608-113">proporciona una sencilla forma gráfica de administrar todo el sistema de alertas.</span><span class="sxs-lookup"><span data-stu-id="a7608-113">provides an easy, graphical way to manage the entire alerting system.</span></span> <span data-ttu-id="a7608-114">Se recomienda utilizar [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] para configurar la infraestructura de alertas.</span><span class="sxs-lookup"><span data-stu-id="a7608-114">Using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] is the recommended way to configure your alert infrastructure.</span></span>  
  
-   <span data-ttu-id="a7608-115">Para enviar una notificación como respuesta a una alerta, primero debe configurar el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para el envío de correo.</span><span class="sxs-lookup"><span data-stu-id="a7608-115">To send a notification in response to an alert, you must first configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to send mail.</span></span> <span data-ttu-id="a7608-116">Para más información, consulte [Configurar el Agente SQL Server para que use el Correo electrónico de base de datos](../../relational-databases/database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="a7608-116">For more information, see [Configure SQL Server Agent Mail to Use Database Mail](../../relational-databases/database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span></span>  
  
-   <span data-ttu-id="a7608-117">Si se produce algún error al enviar un mensaje de correo electrónico o una notificación por buscapersonas, el error se comunica en el registro de errores de servicio del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a7608-117">If a failure occurs when sending an e-mail message or pager notification, the failure is reported in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service error log.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a7608-118">Seguridad</span><span class="sxs-lookup"><span data-stu-id="a7608-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a7608-119">Permisos</span><span class="sxs-lookup"><span data-stu-id="a7608-119">Permissions</span></span>  
 <span data-ttu-id="a7608-120">Solo los miembros del rol fijo de servidor **sysadmin** pueden asignar alertas a operadores.</span><span class="sxs-lookup"><span data-stu-id="a7608-120">Only members of the **sysadmin** fixed server role can assign alerts to operators.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a7608-121">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a7608-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-assign-alerts-to-an-operator"></a><span data-ttu-id="a7608-122">Para asignar alertas a un operador</span><span class="sxs-lookup"><span data-stu-id="a7608-122">To assign alerts to an operator</span></span>  
  
1.  <span data-ttu-id="a7608-123">En el **Explorador de objetos**, haga clic en el signo más para expandir el servidor que contiene el operador al que desea asignar una alerta.</span><span class="sxs-lookup"><span data-stu-id="a7608-123">In **Object Explorer**, click the plus sign to expand the server that contains the operator to which you want to assign an alert.</span></span>  
  
2.  <span data-ttu-id="a7608-124">Haga clic en el signo más para expandir **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="a7608-124">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="a7608-125">Haga clic en el signo más para expandir la carpeta **Operadores** .</span><span class="sxs-lookup"><span data-stu-id="a7608-125">Click the plus sign to expand the **Operators** folder.</span></span>  
  
4.  <span data-ttu-id="a7608-126">Haga clic con el botón derecho en el operador al que desea asignar una alerta y seleccione **Propiedades**y, luego, la página **Notificaciones** .</span><span class="sxs-lookup"><span data-stu-id="a7608-126">Right-click the operator to which you want to assign an alert and select **Properties**, and select the **Notifications** page.</span></span>  
  
5.  <span data-ttu-id="a7608-127">En el cuadro de diálogo**Propiedades** de _nombre_operador_, en **Seleccionar una página**,seleccione **Notificaciones**.</span><span class="sxs-lookup"><span data-stu-id="a7608-127">In the _operator_name_**Properties** dialog box, under **Select a page**, select **Notifications**.</span></span>  
  
6.  <span data-ttu-id="a7608-128">En **Ver las notificaciones enviadas a este usuario por**, seleccione **Alertas** para ver una lista de las alertas enviadas a este operador o seleccione **Trabajos** para ver una lista de los trabajos que envían notificaciones a este operador.</span><span class="sxs-lookup"><span data-stu-id="a7608-128">Under **View notifications sent to this user by**, select **Alerts** to view a list of alerts sent to this operator or select **Jobs** to view a list of jobs that send notifications to this operator.</span></span> <span data-ttu-id="a7608-129">Active una o varias de las siguientes casillas para definir el método de notificación de cada notificación según corresponda: **Correo electrónico**, **Buscapersonas**o **Net send**.</span><span class="sxs-lookup"><span data-stu-id="a7608-129">Select one or more of the following checkboxes to define the notification method for each notification as necessary: **E-mail**, **Pager**, or **Net send**.</span></span>  
  
7.  <span data-ttu-id="a7608-130">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a7608-130">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a7608-131">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a7608-131">Using Transact-SQL</span></span>  
  
#### <a name="to-assign-alerts-to-an-operator"></a><span data-ttu-id="a7608-132">Para asignar alertas a un operador</span><span class="sxs-lookup"><span data-stu-id="a7608-132">To assign alerts to an operator</span></span>  
  
1.  <span data-ttu-id="a7608-133">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7608-133">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a7608-134">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="a7608-134">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a7608-135">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="a7608-135">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- adds an e-mail notification for the specified alert (Test Alert)  
    -- This example assumes that Test Alert already exists and that Fran??ois Ajenstat is a valid operator name.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_notification  
     @alert_name = N'Test Alert',  
     @operator_name = N'Fran??ois Ajenstat',  
     @notification_method = 1 ;  
    GO  
    ```  
  
 <span data-ttu-id="a7608-136">Para obtener más información, vea [sp_add_notification &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a7608-136">For more information, see [sp_add_notification &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql).</span></span>  
  
  
