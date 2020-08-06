---
title: Desencadenadores logon | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- logon triggers
- login triggers
helpviewer_keywords:
- triggers [SQL Server], logon
ms.assetid: 2f0ebb2f-de10-482d-9806-1a5de5b312b8
author: rothja
ms.author: jroth
ms.openlocfilehash: cda0be25f07ed2ee283b9707884041e7c6e4692f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676913"
---
# <a name="logon-triggers"></a><span data-ttu-id="9dae1-102">Desencadenadores logon</span><span class="sxs-lookup"><span data-stu-id="9dae1-102">Logon Triggers</span></span>
  <span data-ttu-id="9dae1-103">Los desencadenadores LOGON activan procedimientos almacenados en respuesta a un evento LOGON.</span><span class="sxs-lookup"><span data-stu-id="9dae1-103">Logon triggers fire stored procedures in response to a LOGON event.</span></span> <span data-ttu-id="9dae1-104">Este evento se genera cuando se establece una sesión de usuario con una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9dae1-104">This event is raised when a user session is established with an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9dae1-105">Los desencadenadores logon se activan después de que termine la fase de autenticación del inicio de sesión, pero antes de que se establezca la sesión de usuario realmente.</span><span class="sxs-lookup"><span data-stu-id="9dae1-105">Logon triggers fire after the authentication phase of logging in finishes, but before the user session is actually established.</span></span> <span data-ttu-id="9dae1-106">Por tanto, todos los mensajes que se originan dentro del desencadenador y que normalmente llegarían hasta el usuario, como los mensajes de error y los mensajes de la instrucción PRINT, se desvían al registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9dae1-106">Therefore, all messages originating inside the trigger that would typically reach the user, such as error messages and messages from the PRINT statement, are diverted to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log.</span></span> <span data-ttu-id="9dae1-107">Los desencadenadores logon no se activan si se produce un error en la autenticación.</span><span class="sxs-lookup"><span data-stu-id="9dae1-107">Logon triggers do not fire if authentication fails.</span></span>  
  
 <span data-ttu-id="9dae1-108">Puede utilizar desencadenadores logon para realizar auditorías y controlar sesiones de servidor, como el seguimiento de la actividad de inicio de sesión, la restricción de inicios de sesión en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]o la limitación del número de sesiones para un inicio de sesión específico.</span><span class="sxs-lookup"><span data-stu-id="9dae1-108">You can use logon triggers to audit and control server sessions, such as by tracking login activity, restricting logins to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or limiting the number of sessions for a specific login.</span></span> <span data-ttu-id="9dae1-109">Por ejemplo, en el siguiente código, el desencadenador LOGON rechaza los intentos de iniciar sesión en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] iniciados por el inicio de sesión *login_test* si ya hay tres sesiones de usuario creadas por dicho inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="9dae1-109">For example, in the following code, the logon trigger denies log in attempts to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] initiated by login *login_test* if there are already three user sessions created by that login.</span></span>  
  
 [!code-sql[TriggerDDL#LogonTrigger1](../../snippets/tsql/SQL14/tsql/triggerddl/transact-sql/snippet_create_alter_drop_trigger.sql#logontrigger1)]  
  
 <span data-ttu-id="9dae1-110">Tenga en cuenta que el evento LOGON se corresponde con el evento de seguimiento de SQL AUDIT_LOGIN, que se puede usar en [notificaciones de eventos](../service-broker/event-notifications.md).</span><span class="sxs-lookup"><span data-stu-id="9dae1-110">Note that the LOGON event corresponds to the AUDIT_LOGIN SQL Trace event, which can be used in [Event Notifications](../service-broker/event-notifications.md).</span></span> <span data-ttu-id="9dae1-111">La diferencia principal entre los desencadenadores y las notificaciones de eventos radica en que los desencadenadores se generan de forma sincrónica con los eventos, mientras que las notificaciones de eventos son asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="9dae1-111">The primary difference between triggers and event notifications is that triggers are raised synchronously with events, whereas event notifications are asynchronous.</span></span> <span data-ttu-id="9dae1-112">Esto significa, por ejemplo, que si desea que no se establezca una sesión, debe utilizar un desencadenador logon.</span><span class="sxs-lookup"><span data-stu-id="9dae1-112">This means, for example, that if you want to stop a session from being established, you must use a logon trigger.</span></span> <span data-ttu-id="9dae1-113">Para este fin, no se puede usar una notificación de eventos en un evento AUDIT_LOGIN.</span><span class="sxs-lookup"><span data-stu-id="9dae1-113">An event notification on an AUDIT_LOGIN event cannot be used for this purpose.</span></span>  
  
## <a name="specifying-first-and-last-trigger"></a><span data-ttu-id="9dae1-114">Especificar el primer y el último desencadenador</span><span class="sxs-lookup"><span data-stu-id="9dae1-114">Specifying First and Last Trigger</span></span>  
 <span data-ttu-id="9dae1-115">Se pueden definir varios desencadenadores en el evento LOGON.</span><span class="sxs-lookup"><span data-stu-id="9dae1-115">Multiple triggers can be defined on the LOGON event.</span></span> <span data-ttu-id="9dae1-116">Cualquiera de estos desencadenadores se puede designar como el primero o el último en activarse en un evento mediante el procedimiento almacenado del sistema [sp_settriggerorder](/sql/relational-databases/system-stored-procedures/sp-settriggerorder-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="9dae1-116">Any one of these triggers can be designated the first or last trigger to be fired on an event by using the [sp_settriggerorder](/sql/relational-databases/system-stored-procedures/sp-settriggerorder-transact-sql) system stored procedure.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="9dae1-117">no garantiza el orden de ejecución del resto de desencadenadores.</span><span class="sxs-lookup"><span data-stu-id="9dae1-117">does not guarantee the execution order of the remaining triggers.</span></span>  
  
## <a name="managing-transactions"></a><span data-ttu-id="9dae1-118">Administrar transacciones</span><span class="sxs-lookup"><span data-stu-id="9dae1-118">Managing Transactions</span></span>  
 <span data-ttu-id="9dae1-119">Antes de que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] active un desencadenador logon, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] crea una transacción implícita que es independiente de cualquier transacción de usuario.</span><span class="sxs-lookup"><span data-stu-id="9dae1-119">Before [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fires a logon trigger, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] creates an implicit transaction that is independent from any user transaction.</span></span> <span data-ttu-id="9dae1-120">Por consiguiente, cuando el primer desencadenador LOGON inicia la activación, el recuento de transacciones es 1.</span><span class="sxs-lookup"><span data-stu-id="9dae1-120">Therefore, when the first logon trigger starts firing, the transaction count is 1.</span></span> <span data-ttu-id="9dae1-121">Una vez que todos los desencadenadores LOGON finalizan su ejecución, se confirma la transacción.</span><span class="sxs-lookup"><span data-stu-id="9dae1-121">After all the logon triggers finish executing, the transaction commits.</span></span> <span data-ttu-id="9dae1-122">Al igual que ocurre con otros tipos de desencadenadores, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] devuelve un error si un desencadenador LOGON termina de ejecutarse con un recuento de transacciones de 0.</span><span class="sxs-lookup"><span data-stu-id="9dae1-122">As with other types of triggers, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] returns an error if a logon trigger finishes execution with a transaction count of 0.</span></span> <span data-ttu-id="9dae1-123">La instrucción ROLLBACK TRANSACTION restablece el recuento de transacciones en 0, incluso si la instrucción se ha emitido desde una transacción anidada.</span><span class="sxs-lookup"><span data-stu-id="9dae1-123">The ROLLBACK TRANSACTION statement resets the transaction count to 0, even if the statement is issued inside a nested transaction.</span></span> <span data-ttu-id="9dae1-124">COMMIT TRANSACTION puede reducir el recuento de transacciones a 0.</span><span class="sxs-lookup"><span data-stu-id="9dae1-124">COMMIT TRANSACTION might decrement the transaction count to 0.</span></span> <span data-ttu-id="9dae1-125">Por tanto, aconsejamos que no se emitan instrucciones COMMIT TRANSACTION desde desencadenadores LOGON.</span><span class="sxs-lookup"><span data-stu-id="9dae1-125">Therefore, we advise against issuing COMMIT TRANSACTION statements inside logon triggers.</span></span>  
  
 <span data-ttu-id="9dae1-126">Piense lo siguiente cuando esté utilizando una instrucción ROLLBACK TRANSACTION dentro de los desencadenadores logon:</span><span class="sxs-lookup"><span data-stu-id="9dae1-126">Consider the following when you are using a ROLLBACK TRANSACTION statement inside logon triggers:</span></span>  
  
-   <span data-ttu-id="9dae1-127">Se revierten todas las modificaciones de datos realizadas antes de emitir la instrucción ROLLBACK TRANSACTION.</span><span class="sxs-lookup"><span data-stu-id="9dae1-127">Any data modifications made up to the point of ROLLBACK TRANSACTION are rolled back.</span></span> <span data-ttu-id="9dae1-128">Estas modificaciones incluyen las realizadas por el desencadenador actual y las realizadas por desencadenadores anteriores ejecutados en el mismo evento.</span><span class="sxs-lookup"><span data-stu-id="9dae1-128">These modifications include those made by the current trigger and those made by previous triggers that executed on the same event.</span></span> <span data-ttu-id="9dae1-129">No se ejecutan los desencadenadores restantes para el evento específico.</span><span class="sxs-lookup"><span data-stu-id="9dae1-129">Any remaining triggers for the specific event are not executed.</span></span>  
  
-   <span data-ttu-id="9dae1-130">El desencadenador actual continúa ejecutando cualquier instrucción restante que aparezca después de la instrucción ROLLBACK.</span><span class="sxs-lookup"><span data-stu-id="9dae1-130">The current trigger continues to execute any remaining statements that appear after the ROLLBACK statement.</span></span> <span data-ttu-id="9dae1-131">Si alguna de estas instrucciones modifica datos, no se revierten las modificaciones.</span><span class="sxs-lookup"><span data-stu-id="9dae1-131">If any of these statements modify data, the modifications are not rolled back.</span></span>  
  
 <span data-ttu-id="9dae1-132">Una sesión de usuario no está establecida si se produce cualquiera de las siguientes condiciones durante la ejecución de un desencadenador en un evento LOGON:</span><span class="sxs-lookup"><span data-stu-id="9dae1-132">A user session is not established if any one of the following conditions occur during execution of a trigger on a LOGON event:</span></span>  
  
-   <span data-ttu-id="9dae1-133">La transacción implícita original se revierte o produce un error.</span><span class="sxs-lookup"><span data-stu-id="9dae1-133">The original implicit transaction is rolled back or fails.</span></span>  
  
-   <span data-ttu-id="9dae1-134">Un error con una gravedad mayor que 20 se genera dentro del cuerpo del desencadenador.</span><span class="sxs-lookup"><span data-stu-id="9dae1-134">An error that has severity greater than 20 is raised inside the trigger body.</span></span>  
  
## <a name="disabling-a-logon-trigger"></a><span data-ttu-id="9dae1-135">Deshabilitar un desencadenador logon</span><span class="sxs-lookup"><span data-stu-id="9dae1-135">Disabling a Logon Trigger</span></span>  
 <span data-ttu-id="9dae1-136">Un desencadenador logon puede impedir la conexión al [!INCLUDE[ssDE](../../../includes/ssde-md.md)] de todos los usuarios, incluidos los miembros del rol fijo de servidor `sysadmin`.</span><span class="sxs-lookup"><span data-stu-id="9dae1-136">A logon trigger can effectively prevent successful connections to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] for all users, including members of the `sysadmin` fixed server role.</span></span> <span data-ttu-id="9dae1-137">Cuando el desencadenador logon impide que se realicen las conexiones, los miembros del rol fijo de servidor `sysadmin` pueden conectarse mediante la conexión de administrador dedicada o iniciando el [!INCLUDE[ssDE](../../../includes/ssde-md.md)] en modo de configuración mínima (-f).</span><span class="sxs-lookup"><span data-stu-id="9dae1-137">When a logon trigger is preventing connections, members of the `sysadmin` fixed server role can connect by using the dedicated administrator connection, or by starting the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] in minimal configuration mode (-f).</span></span> <span data-ttu-id="9dae1-138">Para más información, consulte [Opciones de inicio del servicio de motor de base de datos](../../database-engine/configure-windows/database-engine-service-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="9dae1-138">For more information, see [Database Engine Service Startup Options](../../database-engine/configure-windows/database-engine-service-startup-options.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="9dae1-139">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="9dae1-139">Related Tasks</span></span>  
  
|<span data-ttu-id="9dae1-140">Tarea</span><span class="sxs-lookup"><span data-stu-id="9dae1-140">Task</span></span>|<span data-ttu-id="9dae1-141">Tema</span><span class="sxs-lookup"><span data-stu-id="9dae1-141">Topic</span></span>|  
|----------|-----------|  
|<span data-ttu-id="9dae1-142">Describe cómo crear los desencadenadores logon.</span><span class="sxs-lookup"><span data-stu-id="9dae1-142">Describes how to create logon triggers.</span></span> <span data-ttu-id="9dae1-143">Los desencadenadores logon se pueden crear desde cualquier base de datos, pero se registran en el nivel de servidor y residen en la base de datos **maestra** .</span><span class="sxs-lookup"><span data-stu-id="9dae1-143">Logon triggers can be created from any database, but are registered at the server level and reside in the **master** database.</span></span>|[<span data-ttu-id="9dae1-144">CREATE TRIGGER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9dae1-144">CREATE TRIGGER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-trigger-transact-sql)|  
|<span data-ttu-id="9dae1-145">Describe cómo modificar los desencadenadores logon.</span><span class="sxs-lookup"><span data-stu-id="9dae1-145">Describes how to modify logon triggers.</span></span>|[<span data-ttu-id="9dae1-146">ALTER TRIGGER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9dae1-146">ALTER TRIGGER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-trigger-transact-sql)|  
|<span data-ttu-id="9dae1-147">Describe cómo eliminar los desencadenadores logon.</span><span class="sxs-lookup"><span data-stu-id="9dae1-147">Describes how to delete logon triggers.</span></span>|[<span data-ttu-id="9dae1-148">DROP TRIGGER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9dae1-148">DROP TRIGGER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-trigger-transact-sql)|  
|<span data-ttu-id="9dae1-149">Describe cómo devolver información acerca de los desencadenadores logon.</span><span class="sxs-lookup"><span data-stu-id="9dae1-149">Describes how to return information about logon triggers.</span></span>|[<span data-ttu-id="9dae1-150">sys.server_triggers &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9dae1-150">sys.server_triggers &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql)<br /><br /> [<span data-ttu-id="9dae1-151">sys.server_trigger_events &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9dae1-151">sys.server_trigger_events &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql)|  
|<span data-ttu-id="9dae1-152">Describe cómo capturar los datos de evento de desencadenador logon.</span><span class="sxs-lookup"><span data-stu-id="9dae1-152">Describes how to capture logon trigger event data.</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="9dae1-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9dae1-153">See Also</span></span>  
 [<span data-ttu-id="9dae1-154">Desencadenadores DDL</span><span class="sxs-lookup"><span data-stu-id="9dae1-154">DDL Triggers</span></span>](../triggers/ddl-triggers.md)  
  
  