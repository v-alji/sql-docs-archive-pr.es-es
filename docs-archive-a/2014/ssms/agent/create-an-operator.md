---
title: Crear un operador | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- jobs [SQL Server Agent], notification options
- operators (users) [Database Engine], creating with Management Studio
- SQL Server Agent jobs, notification options
- jobs [SQL Server Agent], operators
- notifications [SQL Server], job status
ms.assetid: 1359d790-5905-4927-a208-e7155e7768a2
author: stevestein
ms.author: sstein
ms.openlocfilehash: dfe07042f9a4b8ac595ada8b86e7bad131032700
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745647"
---
# <a name="create-an-operator"></a><span data-ttu-id="5cdfd-102">Create an Operator</span><span class="sxs-lookup"><span data-stu-id="5cdfd-102">Create an Operator</span></span>
  <span data-ttu-id="5cdfd-103">En este tema se describe cómo configurar un usuario para que reciba notificaciones acerca [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de los trabajos del agente en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5cdfd-103">This topic describes how to configure a user to receive notifications about [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="5cdfd-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="5cdfd-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5cdfd-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="5cdfd-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5cdfd-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="5cdfd-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="5cdfd-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5cdfd-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5cdfd-108">**Para crear un operador, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="5cdfd-108">**To create an operator, using:**</span></span>  
  
     [<span data-ttu-id="5cdfd-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5cdfd-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5cdfd-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5cdfd-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5cdfd-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="5cdfd-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="5cdfd-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="5cdfd-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="5cdfd-113">Las opciones Buscapersonas y **net send** se quitarán del Agente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en una versión futura de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5cdfd-113">The Pager and **net send** options will be removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in a future version of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5cdfd-114">Evite utilizar estas características en los nuevos trabajos de programación y planee modificar las aplicaciones que actualmente las utilizan.</span><span class="sxs-lookup"><span data-stu-id="5cdfd-114">Avoid using these features in new development work, and plan to modify applications that currently use these features.</span></span>  
  
-   <span data-ttu-id="5cdfd-115">Tenga en cuenta que deberá configurar el Agente SQL Server para que utilice el Correo electrónico de base de datos para enviar a los operadores notificaciones por correo electrónico o buscapersonas.</span><span class="sxs-lookup"><span data-stu-id="5cdfd-115">Note that SQL Server Agent must be configured to use Database Mail to send e-mail and pager notifications to operators.</span></span> <span data-ttu-id="5cdfd-116">Para obtener más información, vea el tema sobre [asignación de alertas a un operador](assign-alerts-to-an-operator.md).</span><span class="sxs-lookup"><span data-stu-id="5cdfd-116">For more information, see [Assign Alerts to an Operator](assign-alerts-to-an-operator.md).</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="5cdfd-117">ofrece un método gráfico sencillo para administrar trabajos y es el método recomendado para crear y administrar la infraestructura de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5cdfd-117">provides an easy, graphical way to manage jobs, and is the recommended way to create and manage the job infrastructure.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5cdfd-118">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5cdfd-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5cdfd-119">Permisos</span><span class="sxs-lookup"><span data-stu-id="5cdfd-119">Permissions</span></span>  
 <span data-ttu-id="5cdfd-120">Solo los miembros del rol fijo de servidor **sysadmin** pueden crear operadores.</span><span class="sxs-lookup"><span data-stu-id="5cdfd-120">Only members of the **sysadmin** fixed server role can create operators.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5cdfd-121">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5cdfd-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-an-operator"></a><span data-ttu-id="5cdfd-122">Para crear un operador</span><span class="sxs-lookup"><span data-stu-id="5cdfd-122">To create an operator</span></span>  
  
1.  <span data-ttu-id="5cdfd-123">En el **Explorador de objetos**, haga clic en el signo más para expandir el servidor en el que desea crear un operador del Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5cdfd-123">In **Object Explorer**, click the plus sign to expand the server where you want to create a SQL Server Agent operator.</span></span>  
  
2.  <span data-ttu-id="5cdfd-124">Haga clic en el signo más para expandir **Agente SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="5cdfd-124">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="5cdfd-125">Haga clic con el botón derecho en la carpeta **Operadores** y, luego, seleccione **Nuevo operador**.</span><span class="sxs-lookup"><span data-stu-id="5cdfd-125">Right-click the **Operators** folder and select **New Operator**.</span></span>  
  
     <span data-ttu-id="5cdfd-126">Las siguientes opciones están disponibles en la página **General** del cuadro de diálogo **Nuevo operador** :</span><span class="sxs-lookup"><span data-stu-id="5cdfd-126">The following options are available on the **General** page of the **New Operator** dialog box:</span></span>  
  
     <span data-ttu-id="5cdfd-127">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="5cdfd-127">**Name**</span></span>  
     <span data-ttu-id="5cdfd-128">Cambie el nombre del operador.</span><span class="sxs-lookup"><span data-stu-id="5cdfd-128">Change the name of the operator.</span></span>  
  
     <span data-ttu-id="5cdfd-129">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="5cdfd-129">**Enabled**</span></span>  
     <span data-ttu-id="5cdfd-130">Habilite el operador.</span><span class="sxs-lookup"><span data-stu-id="5cdfd-130">Enable the operator.</span></span> <span data-ttu-id="5cdfd-131">Si no se hablita, no se le envía ninguna notificación.</span><span class="sxs-lookup"><span data-stu-id="5cdfd-131">When not enabled, no notifications are sent to the operator.</span></span>  
  
     <span data-ttu-id="5cdfd-132">**Nombre de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="5cdfd-132">**E-mail name**</span></span>  
     <span data-ttu-id="5cdfd-133">Especifica la dirección de correo electrónico del operador.</span><span class="sxs-lookup"><span data-stu-id="5cdfd-133">Specifies the e-mail address for the operator.</span></span>  
  
     <span data-ttu-id="5cdfd-134">**Dirección de NET SEND**</span><span class="sxs-lookup"><span data-stu-id="5cdfd-134">**Net send address**</span></span>  
     <span data-ttu-id="5cdfd-135">Especifique la dirección que se va a usar para **net send**.</span><span class="sxs-lookup"><span data-stu-id="5cdfd-135">Specify the address to use for **net send**.</span></span>  
  
     <span data-ttu-id="5cdfd-136">**Correo electrónico del buscapersonas**</span><span class="sxs-lookup"><span data-stu-id="5cdfd-136">**Pager e-mail name**</span></span>  
     <span data-ttu-id="5cdfd-137">Especifica la dirección de correo electrónico que debe utilizarse para el buscapersonas del operador.</span><span class="sxs-lookup"><span data-stu-id="5cdfd-137">Specifies the e-mail address to use for the operator's pager.</span></span>  
  
     <span data-ttu-id="5cdfd-138">**Programación de buscapersonas en servicio**</span><span class="sxs-lookup"><span data-stu-id="5cdfd-138">**Pager on duty schedule**</span></span>  
     <span data-ttu-id="5cdfd-139">Establece las horas a las que el buscapersonas está activo.</span><span class="sxs-lookup"><span data-stu-id="5cdfd-139">Sets the times at which the pager is active.</span></span>  
  
     <span data-ttu-id="5cdfd-140">**Lunes - Viernes**</span><span class="sxs-lookup"><span data-stu-id="5cdfd-140">**Monday - Sunday**</span></span>  
     <span data-ttu-id="5cdfd-141">Seleccione los días en los que el buscapersonas está activo.</span><span class="sxs-lookup"><span data-stu-id="5cdfd-141">Select the days that the pager is active.</span></span>  
  
     <span data-ttu-id="5cdfd-142">**Inicio del día laborable**</span><span class="sxs-lookup"><span data-stu-id="5cdfd-142">**Workday begin**</span></span>  
     <span data-ttu-id="5cdfd-143">Seleccione la hora del día a partir de la cual el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] envía mensajes al buscapersonas.</span><span class="sxs-lookup"><span data-stu-id="5cdfd-143">Select the time of day after which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent sends messages to the pager.</span></span>  
  
     <span data-ttu-id="5cdfd-144">**Fin del día laborable**</span><span class="sxs-lookup"><span data-stu-id="5cdfd-144">**Workday end**</span></span>  
     <span data-ttu-id="5cdfd-145">Seleccione la hora del día a partir de la cual el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deja de enviar mensajes al buscapersonas.</span><span class="sxs-lookup"><span data-stu-id="5cdfd-145">Select the time of day after which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent no longer sends messages to the pager.</span></span>  
  
     <span data-ttu-id="5cdfd-146">Las siguientes opciones están disponibles en la página **Notificaciones** del cuadro de diálogo **Nuevo operador** :</span><span class="sxs-lookup"><span data-stu-id="5cdfd-146">The following options are available on the **Notifications** page of the **New Operator** dialog box:</span></span>  
  
     <span data-ttu-id="5cdfd-147">**Alertas**</span><span class="sxs-lookup"><span data-stu-id="5cdfd-147">**Alerts**</span></span>  
     <span data-ttu-id="5cdfd-148">Muestra las alertas de la instancia.</span><span class="sxs-lookup"><span data-stu-id="5cdfd-148">View the alerts in the instance.</span></span>  
  
     <span data-ttu-id="5cdfd-149">**Trabajos**</span><span class="sxs-lookup"><span data-stu-id="5cdfd-149">**Jobs**</span></span>  
     <span data-ttu-id="5cdfd-150">Muestra los trabajos de la instancia.</span><span class="sxs-lookup"><span data-stu-id="5cdfd-150">View the jobs in the instance.</span></span>  
  
     <span data-ttu-id="5cdfd-151">**Lista de alertas**</span><span class="sxs-lookup"><span data-stu-id="5cdfd-151">**Alert list**</span></span>  
     <span data-ttu-id="5cdfd-152">Enumera las alertas de la instancia.</span><span class="sxs-lookup"><span data-stu-id="5cdfd-152">Lists the alerts in the instance.</span></span>  
  
     <span data-ttu-id="5cdfd-153">**Lista de trabajos**</span><span class="sxs-lookup"><span data-stu-id="5cdfd-153">**Job list**</span></span>  
     <span data-ttu-id="5cdfd-154">Enumera los trabajos de la instancia.</span><span class="sxs-lookup"><span data-stu-id="5cdfd-154">Lists the jobs in the instance.</span></span>  
  
     <span data-ttu-id="5cdfd-155">**Por**</span><span class="sxs-lookup"><span data-stu-id="5cdfd-155">**E-mail**</span></span>  
     <span data-ttu-id="5cdfd-156">Envía la notificación al operador por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="5cdfd-156">Notify this operator using e-mail.</span></span>  
  
     <span data-ttu-id="5cdfd-157">**Buscapersonas**</span><span class="sxs-lookup"><span data-stu-id="5cdfd-157">**Pager**</span></span>  
     <span data-ttu-id="5cdfd-158">Envía la notificación al operador mediante un mensaje de correo electrónico a la dirección del buscapersonas.</span><span class="sxs-lookup"><span data-stu-id="5cdfd-158">Notify this operator by sending e-mail to the pager address.</span></span>  
  
     <span data-ttu-id="5cdfd-159">**Net send**</span><span class="sxs-lookup"><span data-stu-id="5cdfd-159">**Net send**</span></span>  
     <span data-ttu-id="5cdfd-160">Notifique a este operador con **net send**.</span><span class="sxs-lookup"><span data-stu-id="5cdfd-160">Notify this operator using **net send**.</span></span>  
  
4.  <span data-ttu-id="5cdfd-161">Cuando termine de crear el nuevo operador, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5cdfd-161">When finished creating the new operator, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5cdfd-162">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5cdfd-162">Using Transact-SQL</span></span>  
  
#### <a name="to-create-an-operator"></a><span data-ttu-id="5cdfd-163">Para crear un operador</span><span class="sxs-lookup"><span data-stu-id="5cdfd-163">To create an operator</span></span>  
  
1.  <span data-ttu-id="5cdfd-164">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5cdfd-164">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5cdfd-165">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="5cdfd-165">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5cdfd-166">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="5cdfd-166">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- sets up the operator information for user 'danwi.' The operator is enabled.   
    -- SQL Server Agent sends notifications by pager from Monday through Friday from 8 A.M. to 5 P.M.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_operator  
        @name = N'Dan Wilson',  
        @enabled = 1,  
        @email_address = N'danwi',  
        @pager_address = N'5551290AW@pager.Adventure-Works.com',  
        @weekday_pager_start_time = 080000,  
        @weekday_pager_end_time = 170000,  
        @pager_days = 62 ;  
    GO  
    ```  
  
 <span data-ttu-id="5cdfd-167">Para obtener más información, vea [sp_add_operator &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-operator-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5cdfd-167">For more information, see [sp_add_operator &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-operator-transact-sql).</span></span>  
  
  
