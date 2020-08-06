---
title: Crear una alerta con un número de error | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- alerts [SQL Server], creating
- SQL Server Agent, alerts
- alerts [SQL Server], error numbers
ms.assetid: 03dd7fac-5073-4f86-babd-37e45a86023c
author: stevestein
ms.author: sstein
ms.openlocfilehash: a98f64bc5b9dffc3e2494a0c36c8fc04cdfb6fa2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673999"
---
# <a name="create-an-alert-using-an-error-number"></a><span data-ttu-id="a16ae-102">Create an Alert Using an Error Number</span><span class="sxs-lookup"><span data-stu-id="a16ae-102">Create an Alert Using an Error Number</span></span>
  <span data-ttu-id="a16ae-103">En este tema se describe cómo crear una [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alerta del agente en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] que se generará cuando se produzca un error de un número específico mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a16ae-103">This topic describes how to create a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert occurs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] that will be raised when an error of a specific number occurs by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="a16ae-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="a16ae-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a16ae-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="a16ae-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a16ae-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="a16ae-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="a16ae-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="a16ae-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a16ae-108">**Para crear una alerta con un número de error, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="a16ae-108">**To create an alert using an error number, using:**</span></span>  
  
     [<span data-ttu-id="a16ae-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a16ae-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a16ae-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a16ae-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a16ae-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="a16ae-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="a16ae-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="a16ae-112">Limitations and Restrictions</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="a16ae-113">proporciona una forma gráfica y fácil de administrar todo el sistema de alertas, y constituye el método recomendado para configurar una infraestructura de alertas.</span><span class="sxs-lookup"><span data-stu-id="a16ae-113">provides an easy, graphical way to manage the entire alerting system and is the recommended way to configure an alert infrastructure.</span></span>  
  
-   <span data-ttu-id="a16ae-114">Los eventos generados durante **xp_logevent** se producen en la base de datos maestra.</span><span class="sxs-lookup"><span data-stu-id="a16ae-114">Events generated with **xp_logevent** occur in the master database.</span></span> <span data-ttu-id="a16ae-115">Por tanto, **xp_logevent** no desencadena una alerta a menos que el valor de **@database_name** de la alerta sea is **'master'** o NULL.</span><span class="sxs-lookup"><span data-stu-id="a16ae-115">Therefore, **xp_logevent** does not trigger an alert unless the **@database_name** for the alert is **'master'** or NULL.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a16ae-116">Seguridad</span><span class="sxs-lookup"><span data-stu-id="a16ae-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a16ae-117">Permisos</span><span class="sxs-lookup"><span data-stu-id="a16ae-117">Permissions</span></span>  
 <span data-ttu-id="a16ae-118">De forma predeterminada, solo los miembros del rol fijo de servidor **sysadmin** pueden ejecutar **sp_add_alert**.</span><span class="sxs-lookup"><span data-stu-id="a16ae-118">By default, only members of the **sysadmin** fixed server role can execute **sp_add_alert**.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a16ae-119">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a16ae-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-an-alert-using-an-error-number"></a><span data-ttu-id="a16ae-120">Para crear una alerta mediante un número de error</span><span class="sxs-lookup"><span data-stu-id="a16ae-120">To create an alert using an error number</span></span>  
  
1.  <span data-ttu-id="a16ae-121">En el **Explorador de objetos** , haga clic en el signo más para expandir el servidor donde desea crear una alerta con un número de error.</span><span class="sxs-lookup"><span data-stu-id="a16ae-121">In **Object Explorer,** click the plus sign to expand the server where you want to create an alert using an error number.</span></span>  
  
2.  <span data-ttu-id="a16ae-122">Haga clic en el signo más para expandir **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="a16ae-122">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="a16ae-123">Haga clic con el botón derecho en **Alertas** y seleccione **Nueva alerta**.</span><span class="sxs-lookup"><span data-stu-id="a16ae-123">Right-click **Alerts** and select **New Alert**.</span></span>  
  
4.  <span data-ttu-id="a16ae-124">En el cuadro de diálogo **Nueva alerta** , en el cuadro **Nombre** , escriba un nombre para esta alerta.</span><span class="sxs-lookup"><span data-stu-id="a16ae-124">In the **New Alert** dialog box, in the **Name** box, enter a name for this alert.</span></span>  
  
5.  <span data-ttu-id="a16ae-125">Active la casilla **Habilitar** para que la alerta se pueda ejecutar.</span><span class="sxs-lookup"><span data-stu-id="a16ae-125">Check the **Enable** check box to enable the alert to run.</span></span> <span data-ttu-id="a16ae-126">De forma predeterminada, la opción **Habilitar** está activada.</span><span class="sxs-lookup"><span data-stu-id="a16ae-126">By default, **Enable** is checked.</span></span>  
  
6.  <span data-ttu-id="a16ae-127">En la lista **Tipo** , seleccione **Alerta de evento de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="a16ae-127">In the **Type** list, select **SQL Server event alert**.</span></span>  
  
7.  <span data-ttu-id="a16ae-128">En **Definición de evento de alerta**, en la lista **Nombre de la base de datos** , seleccione una base de datos para restringir la alerta a una base de datos específica.</span><span class="sxs-lookup"><span data-stu-id="a16ae-128">Under **Event alert definition**, in the **Database name** list, select a database to restrict the alert to a specific database.</span></span>  
  
8.  <span data-ttu-id="a16ae-129">En **Las alertas se mostrarán en función de**, haga clic en **Número de error**y escriba un número de error válido para la alerta.</span><span class="sxs-lookup"><span data-stu-id="a16ae-129">Under **Alerts will be raised based on**, click **Error number**, and then type a valid error number for the alert.</span></span> <span data-ttu-id="a16ae-130">También puede hacer clic en **Gravedad** y seleccionar la gravedad específica que producirá la alerta.</span><span class="sxs-lookup"><span data-stu-id="a16ae-130">Alternately, click **Severity** and then select the specific severity that will raise the alert.</span></span>  
  
9. <span data-ttu-id="a16ae-131">Active la casilla correspondiente a **Mostrar alerta cuando el mensaje contenga** para restringir la alerta a una secuencia de caracteres en particular y, a continuación, escriba una palabra clave o una cadena de caracteres en el **Texto del mensaje**.</span><span class="sxs-lookup"><span data-stu-id="a16ae-131">Check the box corresponding to **Raise alert when message contains** check box to restrict the alert to a particular character sequence, and then enter a keyword or character string for the **Message text**.</span></span> <span data-ttu-id="a16ae-132">El número máximo de caracteres es 100.</span><span class="sxs-lookup"><span data-stu-id="a16ae-132">The maximum number of characters is 100.</span></span>  
  
10. <span data-ttu-id="a16ae-133">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="a16ae-133">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a16ae-134">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a16ae-134">Using Transact-SQL</span></span>  
  
#### <a name="to-create-an-alert-using-an-error-number"></a><span data-ttu-id="a16ae-135">Para crear una alerta mediante un número de error</span><span class="sxs-lookup"><span data-stu-id="a16ae-135">To create an alert using an error number</span></span>  
  
1.  <span data-ttu-id="a16ae-136">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a16ae-136">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a16ae-137">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="a16ae-137">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a16ae-138">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="a16ae-138">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
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
  
 <span data-ttu-id="a16ae-139">Para obtener más información, vea [sp_add_alert &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a16ae-139">For more information, see [sp_add_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql).</span></span>  
  
  
