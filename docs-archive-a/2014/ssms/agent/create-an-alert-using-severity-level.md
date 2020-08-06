---
title: Crear una alerta con nivel de gravedad | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- alerts [SQL Server], creating
- SQL Server Agent, alerts
- severity levels [SQL Server]
- alerts [SQL Server], severity levels
ms.assetid: a1fd71bf-5bf9-4ce2-9a1d-032576a4a6e9
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6ee353129d60fe7fc8bed0eff279920d8d4ba640
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747412"
---
# <a name="create-an-alert-using-severity-level"></a><span data-ttu-id="af004-102">Create an Alert Using Severity Level</span><span class="sxs-lookup"><span data-stu-id="af004-102">Create an Alert Using Severity Level</span></span>
  <span data-ttu-id="af004-103">En este tema se describe cómo crear una [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alerta del agente que se genera cuando se produce un evento con un nivel de gravedad específico en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="af004-103">This topic describes how to create a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert that is raised when an event of a specific severity level occurs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="af004-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="af004-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="af004-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="af004-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="af004-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="af004-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="af004-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="af004-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="af004-108">**Para crear una alerta con nivel de gravedad, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="af004-108">**To create an alert using severity level, using:**</span></span>  
  
     [<span data-ttu-id="af004-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="af004-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="af004-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="af004-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="af004-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="af004-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="af004-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="af004-112">Limitations and Restrictions</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="af004-113">proporciona una forma gráfica y fácil de administrar todo el sistema de alertas, y constituye el método recomendado para configurar una infraestructura de alertas.</span><span class="sxs-lookup"><span data-stu-id="af004-113">provides an easy, graphical way to manage the entire alerting system and is the recommended way to configure an alert infrastructure.</span></span>  
  
-   <span data-ttu-id="af004-114">Los eventos generados durante **xp_logevent** se producen en la base de datos maestra.</span><span class="sxs-lookup"><span data-stu-id="af004-114">Events generated with **xp_logevent** occur in the master database.</span></span> <span data-ttu-id="af004-115">Por tanto, **xp_logevent** no desencadena una alerta a menos que el valor de **@database_name** de la alerta sea is **'master'** o NULL.</span><span class="sxs-lookup"><span data-stu-id="af004-115">Therefore, **xp_logevent** does not trigger an alert unless the **@database_name** for the alert is **'master'** or NULL.</span></span>  
  
-   <span data-ttu-id="af004-116">Con los niveles de gravedad entre 19 y 25 se envía un mensaje de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] al registro de la aplicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows y se desencadena una alerta.</span><span class="sxs-lookup"><span data-stu-id="af004-116">Severity levels from 19 through 25 send a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] message to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows application log and trigger an alert.</span></span> <span data-ttu-id="af004-117">Los eventos con niveles de gravedad inferiores a 19 solo desencadenarán alertas si ha utilizado **sp_altermessage**, RAISERROR WITH LOG o **xp_logevent** para forzar que se escriban en el registro de la aplicación Windows.</span><span class="sxs-lookup"><span data-stu-id="af004-117">Events with severity levels less than 19 will trigger alerts only if you have used **sp_altermessage**, RAISERROR WITH LOG, or **xp_logevent** to force them to be written to the Windows application log.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="af004-118">Seguridad</span><span class="sxs-lookup"><span data-stu-id="af004-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="af004-119">Permisos</span><span class="sxs-lookup"><span data-stu-id="af004-119">Permissions</span></span>  
 <span data-ttu-id="af004-120">De forma predeterminada, solo los miembros del rol fijo de servidor **sysadmin** pueden ejecutar **sp_add_alert**.</span><span class="sxs-lookup"><span data-stu-id="af004-120">By default, only members of the **sysadmin** fixed server role can execute **sp_add_alert**.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="af004-121">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="af004-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-an-alert-using-severity-level"></a><span data-ttu-id="af004-122">Para crear una alerta con nivel de gravedad</span><span class="sxs-lookup"><span data-stu-id="af004-122">To create an alert using severity level</span></span>  
  
1.  <span data-ttu-id="af004-123">En el **Explorador de objetos** , haga clic en el signo más para expandir el servidor donde desea crear una alerta con nivel de seguridad.</span><span class="sxs-lookup"><span data-stu-id="af004-123">In **Object Explorer,** click the plus sign to expand the server where you want to create an alert using severity level.</span></span>  
  
2.  <span data-ttu-id="af004-124">Haga clic en el signo más para expandir **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="af004-124">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="af004-125">Haga clic con el botón derecho en **Alertas** y seleccione **Nueva alerta**.</span><span class="sxs-lookup"><span data-stu-id="af004-125">Right-click **Alerts** and select **New Alert**.</span></span>  
  
4.  <span data-ttu-id="af004-126">En el cuadro de diálogo **Nueva alerta** , en el cuadro **Nombre** , escriba un nombre para esta alerta.</span><span class="sxs-lookup"><span data-stu-id="af004-126">In the **New Alert** dialog box, in the **Name** box, enter a name for this alert.</span></span>  
  
5.  <span data-ttu-id="af004-127">En la lista **Tipo** , seleccione **Alerta de evento de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="af004-127">In the **Type** list, select **SQL Server event alert**.</span></span>  
  
6.  <span data-ttu-id="af004-128">En **Definición de evento de alerta**, en la lista **Nombre de la base de datos** , seleccione una base de datos para restringir la alerta a una base de datos específica.</span><span class="sxs-lookup"><span data-stu-id="af004-128">Under **Event alert definition**, in the **Database name** list, select a database to restrict the alert to a specific database.</span></span>  
  
7.  <span data-ttu-id="af004-129">En **Las alertas se mostrarán en función de**, haga clic en **Gravedad** y seleccione la gravedad específica que generará la alerta.</span><span class="sxs-lookup"><span data-stu-id="af004-129">Under **Alerts will be raised based on**, click **Severity** and then select the specific severity that will raise the alert.</span></span>  
  
8.  <span data-ttu-id="af004-130">Active la casilla correspondiente a **Mostrar alerta cuando el mensaje contenga** para restringir la alerta a una secuencia de caracteres en particular y, a continuación, escriba una palabra clave o una cadena de caracteres en el **Texto del mensaje**.</span><span class="sxs-lookup"><span data-stu-id="af004-130">Check the box corresponding to **Raise alert when message contains** check box to restrict the alert to a particular character sequence, and then enter a keyword or character string for the **Message text**.</span></span> <span data-ttu-id="af004-131">El número máximo de caracteres es 100.</span><span class="sxs-lookup"><span data-stu-id="af004-131">The maximum number of characters is 100.</span></span>  
  
9. <span data-ttu-id="af004-132">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="af004-132">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="af004-133">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="af004-133">Using Transact-SQL</span></span>  
  
#### <a name="to-create-an-alert-using-severity-level"></a><span data-ttu-id="af004-134">Para crear una alerta con nivel de gravedad</span><span class="sxs-lookup"><span data-stu-id="af004-134">To create an alert using severity level</span></span>  
  
1.  <span data-ttu-id="af004-135">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af004-135">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="af004-136">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="af004-136">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="af004-137">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="af004-137">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- adds an alert (Test Alert) that runs the Back up the AdventureWorks2012 Database job when fired   
    -- assumes that the message 55001 and the Back up the AdventureWorks2012 Database job already exist.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_alert  
        @name = N'Test Alert',  
        @message_id = 55001,   
       @severity = 0,   
       @notification_message = N'Error 55001 has occurred. The database will be backed up...',   
       @job_name = N'Back up the AdventureWorks2012 Database' ;  
    GO  
    ```  
  
 <span data-ttu-id="af004-138">Para obtener más información, vea [sp_add_alert &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="af004-138">For more information, see [sp_add_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql).</span></span>  
  
  
