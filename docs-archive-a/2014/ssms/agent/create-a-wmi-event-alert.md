---
title: Crear una alerta de evento WMI | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- WMI event alerts [SQL Server Management Studio]
ms.assetid: b8c46db6-408b-484e-98f0-a8af3e7ec763
author: stevestein
ms.author: sstein
ms.openlocfilehash: 737e7ccac9c92e663040e71339aa120f8db8b80b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674536"
---
# <a name="create-a-wmi-event-alert"></a><span data-ttu-id="7d1f0-102">Create a WMI Event Alert</span><span class="sxs-lookup"><span data-stu-id="7d1f0-102">Create a WMI Event Alert</span></span>
  <span data-ttu-id="7d1f0-103">En este tema se describe cómo crear una alerta del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que se genera cuando se produce un evento de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] específico supervisado por el proveedor WMI para eventos de servidor en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d1f0-103">This topic describes how to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert that is raised when a specific [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] event occurs that is monitored by the WMI Provider for Server Events in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="7d1f0-104">Para obtener información sobre el uso del proveedor WMI para supervisar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eventos, vea [conceptos del proveedor WMI para eventos de servidor](../../relational-databases/wmi-provider-server-events/wmi-provider-for-server-events-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="7d1f0-104">For information about the using the WMI Provider to monitor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] events, see [WMI Provider for Server Events Concepts](../../relational-databases/wmi-provider-server-events/wmi-provider-for-server-events-concepts.md).</span></span> <span data-ttu-id="7d1f0-105">Para más información sobre los permisos necesarios para recibir notificaciones de alertas de eventos de WMI, consulte [Seleccionar una cuenta para el servicio Agente SQL Server](select-an-account-for-the-sql-server-agent-service.md).</span><span class="sxs-lookup"><span data-stu-id="7d1f0-105">For information about the permissions necessary to receive WMI event alert notifications, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md).</span></span> <span data-ttu-id="7d1f0-106">Para más información sobre WQL, consulte [Usar WQL con el proveedor de WMI para eventos de servidor](../../relational-databases/wmi-provider-server-events/using-wql-with-the-wmi-provider-for-server-events.md).</span><span class="sxs-lookup"><span data-stu-id="7d1f0-106">For more information about WQL, see [Using WQL with the WMI Provider for Server Events](../../relational-databases/wmi-provider-server-events/using-wql-with-the-wmi-provider-for-server-events.md).</span></span>  
  
 <span data-ttu-id="7d1f0-107">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="7d1f0-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7d1f0-108">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="7d1f0-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7d1f0-109">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="7d1f0-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="7d1f0-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="7d1f0-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7d1f0-111">**Para crear una alerta de evento WMI, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="7d1f0-111">**To create a WMI event alert, using:**</span></span>  
  
     [<span data-ttu-id="7d1f0-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7d1f0-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7d1f0-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7d1f0-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7d1f0-114">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="7d1f0-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="7d1f0-115">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="7d1f0-115">Limitations and Restrictions</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="7d1f0-116">proporciona una forma gráfica y fácil de administrar todo el sistema de alertas, y constituye el método recomendado para configurar una infraestructura de alertas.</span><span class="sxs-lookup"><span data-stu-id="7d1f0-116">provides an easy, graphical way to manage the entire alerting system and is the recommended way to configure an alert infrastructure.</span></span>  
  
-   <span data-ttu-id="7d1f0-117">Los eventos generados durante **xp_logevent** se producen en la base de datos maestra.</span><span class="sxs-lookup"><span data-stu-id="7d1f0-117">Events generated with **xp_logevent** occur in the master database.</span></span> <span data-ttu-id="7d1f0-118">Por tanto, **xp_logevent** no desencadena una alerta a menos que el valor de **@database_name** de la alerta sea is **'master'** o NULL.</span><span class="sxs-lookup"><span data-stu-id="7d1f0-118">Therefore, **xp_logevent** does not trigger an alert unless the **@database_name** for the alert is **'master'** or NULL.</span></span>  
  
-   <span data-ttu-id="7d1f0-119">Solo se admiten los espacios de nombres WMI del equipo que ejecuta el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7d1f0-119">Only WMI namespaces on the computer that runs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent are supported.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7d1f0-120">Seguridad</span><span class="sxs-lookup"><span data-stu-id="7d1f0-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7d1f0-121">Permisos</span><span class="sxs-lookup"><span data-stu-id="7d1f0-121">Permissions</span></span>  
 <span data-ttu-id="7d1f0-122">De forma predeterminada, solo los miembros del rol fijo de servidor **sysadmin** pueden ejecutar **sp_add_alert**.</span><span class="sxs-lookup"><span data-stu-id="7d1f0-122">By default, only members of the **sysadmin** fixed server role can execute **sp_add_alert**.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7d1f0-123">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7d1f0-123">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-wmi-event-alert"></a><span data-ttu-id="7d1f0-124">Para crear una alerta de evento WMI</span><span class="sxs-lookup"><span data-stu-id="7d1f0-124">To create a WMI event alert</span></span>  
  
1.  <span data-ttu-id="7d1f0-125">En el **Explorador de objetos** , haga clic en el signo más para expandir el servidor donde desea crear una alerta de evento WMI.</span><span class="sxs-lookup"><span data-stu-id="7d1f0-125">In **Object Explorer,** click the plus sign to expand the server where you want to create a WMI event alert.</span></span>  
  
2.  <span data-ttu-id="7d1f0-126">Haga clic en el signo más para expandir **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="7d1f0-126">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="7d1f0-127">Haga clic con el botón derecho en **Alertas** y seleccione **Nueva alerta**.</span><span class="sxs-lookup"><span data-stu-id="7d1f0-127">Right-click **Alerts** and select **New Alert**.</span></span>  
  
4.  <span data-ttu-id="7d1f0-128">En el cuadro de diálogo **Nueva alerta** , en el cuadro **Nombre** , escriba un nombre para esta alerta.</span><span class="sxs-lookup"><span data-stu-id="7d1f0-128">In the **New Alert** dialog box, in the **Name** box, enter a name for this alert.</span></span>  
  
5.  <span data-ttu-id="7d1f0-129">Active la casilla **Habilitar** para que la alerta se pueda ejecutar.</span><span class="sxs-lookup"><span data-stu-id="7d1f0-129">Check the **Enable** check box to enable the alert to run.</span></span> <span data-ttu-id="7d1f0-130">De forma predeterminada, la opción **Habilitar** está activada.</span><span class="sxs-lookup"><span data-stu-id="7d1f0-130">By default, **Enable** is checked.</span></span>  
  
6.  <span data-ttu-id="7d1f0-131">En la lista **Tipo** , seleccione **Alerta de evento WMI**.</span><span class="sxs-lookup"><span data-stu-id="7d1f0-131">In the **Type** list, select **WMI event alert**.</span></span>  
  
7.  <span data-ttu-id="7d1f0-132">En **Definición de evento de alerta de WMI**, en el cuadro **Espacio de nombres** , especifique el espacio de nombres WMI para la instrucción WQL (Lenguaje de consulta de WMI) que identifica qué evento WMI activará esta alerta.</span><span class="sxs-lookup"><span data-stu-id="7d1f0-132">Under **WMI event alert definition**, in the **Namespace** box, specify the WMI namespace for the WMI Query Language (WQL) statement that identifies which WMI event will trigger this alert.</span></span>  
  
8.  <span data-ttu-id="7d1f0-133">En el cuadro **Consulta** , especifique la instrucción WQL que identifica el evento al que responde esta alerta.</span><span class="sxs-lookup"><span data-stu-id="7d1f0-133">In the **Query** box, specify the WQL statement that identifies the event that this alert responds to.</span></span>  
  
9. <span data-ttu-id="7d1f0-134">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="7d1f0-134">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7d1f0-135">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7d1f0-135">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-wmi-event-alert"></a><span data-ttu-id="7d1f0-136">Para crear una alerta de evento WMI</span><span class="sxs-lookup"><span data-stu-id="7d1f0-136">To create a WMI event alert</span></span>  
  
1.  <span data-ttu-id="7d1f0-137">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d1f0-137">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7d1f0-138">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="7d1f0-138">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7d1f0-139">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="7d1f0-139">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- creates a WMI event alert that retrieves all event properties for any ALTER_TABLE event that occurs on table AdventureWorks2012.Sales.SalesOrderDetail  
    -- This example assumes that the message 54001 already exists.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_alert  
        @name = N'Test Alert 2',  
        @message_id = 54001  
        @notification_message = N'Error 54001 has occurred on the Sales.SalesOrderDetail table on the AdventureWorks2012 database. Please see the following information...',  
        @wmi_namespace = '\\.\root\Microsoft\SqlServer\ServerEvents\,  
        @wmi_query = N'SELECT * FROM ALTER_TABLE   
    WHERE DatabaseName = 'AdventureWorks2012' AND SchemaName = 'Sales'   
        AND ObjectType='Table' AND ObjectName = 'SalesOrderDetail'';  
    GO  
    ```  
  
 <span data-ttu-id="7d1f0-140">Para obtener más información, vea [sp_add_alert &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7d1f0-140">For more information, see [sp_add_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql).</span></span>  
  
  
