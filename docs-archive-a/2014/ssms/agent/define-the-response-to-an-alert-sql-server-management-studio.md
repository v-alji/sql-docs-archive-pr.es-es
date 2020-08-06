---
title: Definir la respuesta a una alerta (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, alerts
- alerts [SQL Server], responding to
- responding to alerts
ms.assetid: c86ca6eb-c59f-46e9-bc32-d474e7c3b170
author: stevestein
ms.author: sstein
ms.openlocfilehash: c14e5adf43602b57697483b9ce4c2cdf20ff8e10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745634"
---
# <a name="define-the-response-to-an-alert-sql-server-management-studio"></a><span data-ttu-id="7a05c-102">Define the Response to an Alert (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="7a05c-102">Define the Response to an Alert (SQL Server Management Studio)</span></span>
  <span data-ttu-id="7a05c-103">En este tema se describe cómo definir cómo [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] responde a las [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alertas del agente en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7a05c-103">This topic describes how to define how [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] responds to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="7a05c-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="7a05c-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7a05c-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="7a05c-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7a05c-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="7a05c-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="7a05c-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="7a05c-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7a05c-108">**Para definir la respuesta a una alerta, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="7a05c-108">**To define the response to an alert, using:**</span></span>  
  
     [<span data-ttu-id="7a05c-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7a05c-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7a05c-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7a05c-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7a05c-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="7a05c-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="7a05c-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="7a05c-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="7a05c-113">Las opciones Buscapersonas y **net send** se quitarán del Agente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en una versión futura de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a05c-113">The Pager and **net send** options will be removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in a future version of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7a05c-114">Evite utilizar estas características en los nuevos trabajos de programación y planee modificar las aplicaciones que actualmente las utilizan.</span><span class="sxs-lookup"><span data-stu-id="7a05c-114">Avoid using these features in new development work, and plan to modify applications that currently use these features.</span></span>  
  
-   <span data-ttu-id="7a05c-115">Tenga en cuenta que deberá configurar el Agente SQL Server para que utilice el Correo electrónico de base de datos para enviar a los operadores notificaciones por correo electrónico o buscapersonas.</span><span class="sxs-lookup"><span data-stu-id="7a05c-115">Note that SQL Server Agent must be configured to use Database Mail to send e-mail and pager notifications to operators.</span></span> <span data-ttu-id="7a05c-116">Para obtener más información, vea el tema sobre [asignación de alertas a un operador](assign-alerts-to-an-operator.md).</span><span class="sxs-lookup"><span data-stu-id="7a05c-116">For more information, see [Assign Alerts to an Operator](assign-alerts-to-an-operator.md).</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="7a05c-117">ofrece un método gráfico sencillo para administrar trabajos y es el método recomendado para crear y administrar la infraestructura de trabajo.</span><span class="sxs-lookup"><span data-stu-id="7a05c-117">provides an easy, graphical way to manage jobs, and is the recommended way to create and manage the job infrastructure.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7a05c-118">Seguridad</span><span class="sxs-lookup"><span data-stu-id="7a05c-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7a05c-119">Permisos</span><span class="sxs-lookup"><span data-stu-id="7a05c-119">Permissions</span></span>  
 <span data-ttu-id="7a05c-120">Solo los miembros del rol fijo de servidor **sysadmin** pueden definir la respuesta a una alerta.</span><span class="sxs-lookup"><span data-stu-id="7a05c-120">Only members of the **sysadmin** fixed server role can define the response to an alert.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7a05c-121">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7a05c-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-define-the-response-to-an-alert"></a><span data-ttu-id="7a05c-122">Para definir la respuesta a una alerta</span><span class="sxs-lookup"><span data-stu-id="7a05c-122">To define the response to an alert</span></span>  
  
1.  <span data-ttu-id="7a05c-123">En el **Explorador de objetos**, haga clic en el signo más para expandir el servidor que contiene la alerta en la que desea definir una respuesta.</span><span class="sxs-lookup"><span data-stu-id="7a05c-123">In **Object Explorer**, click the plus sign to expand the server that contains the alert on which you want to define a response.</span></span>  
  
2.  <span data-ttu-id="7a05c-124">Haga clic en el signo más para expandir **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="7a05c-124">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="7a05c-125">Haga clic en el signo más para expandir la carpeta **Alertas** .</span><span class="sxs-lookup"><span data-stu-id="7a05c-125">Click the plus sign to expand the **Alerts** folder.</span></span>  
  
4.  <span data-ttu-id="7a05c-126">Haga clic con el botón derecho en la alerta en la que desea definir una respuesta y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7a05c-126">Right-click the alert on which you want to define a response and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="7a05c-127">En el cuadro de diálogo _alert_name_**propiedades de alerta** , en **seleccionar una página**, seleccione **respuesta**.</span><span class="sxs-lookup"><span data-stu-id="7a05c-127">In the _alert_name_**alert properties** dialog box, under **Select a page**, select **Response**.</span></span>  
  
6.  <span data-ttu-id="7a05c-128">Active la casilla **Ejecutar trabajo** y, en la lista situada debajo de la casilla **Ejecutar trabajo** , seleccione el trabajo que se ejecutará cuando se produzca la alerta.</span><span class="sxs-lookup"><span data-stu-id="7a05c-128">Select the **Execute job** check box and, from the list below the **Execute job** check box, select a job to execute when the alert occurs.</span></span> <span data-ttu-id="7a05c-129">Puede crear un nuevo trabajo haciendo clic en **Nuevo trabajo**.</span><span class="sxs-lookup"><span data-stu-id="7a05c-129">You can create a new job by clicking **New Job**.</span></span> <span data-ttu-id="7a05c-130">Puede ver más información acerca del trabajo haciendo clic en **View Job**.</span><span class="sxs-lookup"><span data-stu-id="7a05c-130">You can view more information about the job by clicking **View Job**.</span></span> <span data-ttu-id="7a05c-131">Para obtener más información sobre las opciones disponibles en los cuadros de diálogo **nuevo trabajo** y **propiedades del trabajo**_Job_name_ , consulte [crear un trabajo](create-a-job.md) y [ver un trabajo](view-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="7a05c-131">For more information about the available options in the **New Job** and **Job Properties**_job_name_ dialog boxes, see [Create a Job](create-a-job.md) and [View a Job](view-a-job.md).</span></span>  
  
7.  <span data-ttu-id="7a05c-132">Active la casilla **Notificar a los operadores** si desea notificar a los operadores cuándo se activará la alerta.</span><span class="sxs-lookup"><span data-stu-id="7a05c-132">Select the **Notify Operators** check box if you want to notify operators when the alert is activated.</span></span> <span data-ttu-id="7a05c-133">En **Lista de operadores**, seleccione uno o más de los métodos siguientes para notificar al operador o a los operadores: **Correo electrónico**, **Buscapersonas**o **Net Send**.</span><span class="sxs-lookup"><span data-stu-id="7a05c-133">In the **Operator list**, select one or more of the following methods for notifying the operator or operators: **E-mail**, **Pager**, or **Net Send**.</span></span> <span data-ttu-id="7a05c-134">Puede crear un nuevo operador haciendo clic en **Nuevo operador**.</span><span class="sxs-lookup"><span data-stu-id="7a05c-134">You can create a new operator by clicking **New Operator**.</span></span> <span data-ttu-id="7a05c-135">Puede ver más información acerca de un operador haciendo clic en **Ver operador**.</span><span class="sxs-lookup"><span data-stu-id="7a05c-135">You can view more information about an operator by clicking **View Operator**.</span></span> <span data-ttu-id="7a05c-136">Para obtener más información acerca de las opciones disponibles en los cuadros de diálogo **Nuevo operador** y **Ver las propiedades del operador** , vea [Create an Operator](create-an-operator.md) y [View Information About an Operator](view-information-about-an-operator.md).</span><span class="sxs-lookup"><span data-stu-id="7a05c-136">For more information about the available options in the **New Operator** and **View Operator Properties** dialog boxes, see [Create an Operator](create-an-operator.md) and [View Information About an Operator](view-information-about-an-operator.md).</span></span>  
  
8.  <span data-ttu-id="7a05c-137">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7a05c-137">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7a05c-138">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7a05c-138">Using Transact-SQL</span></span>  
  
#### <a name="to-define-the-response-to-an-alert"></a><span data-ttu-id="7a05c-139">Para definir la respuesta a una alerta</span><span class="sxs-lookup"><span data-stu-id="7a05c-139">To define the response to an alert</span></span>  
  
1.  <span data-ttu-id="7a05c-140">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a05c-140">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7a05c-141">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="7a05c-141">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7a05c-142">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="7a05c-142">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- adds an e-mail notification for Test Alert.  
    -- assumes that Test Alert already exists and that Fran??ois Ajenstat is a valid operator name   
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_notification  
     @alert_name = N'Test Alert',  
     @operator_name = N'Fran??ois Ajenstat',  
     @notification_method = 1 ;  
    GO  
    ```  
  
 <span data-ttu-id="7a05c-143">Para obtener más información, vea [sp_add_notification &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7a05c-143">For more information, see [sp_add_notification &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql).</span></span>  
  
  
