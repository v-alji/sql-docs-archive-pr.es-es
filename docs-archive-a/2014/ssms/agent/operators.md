---
title: Operadores | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- operators (users) [Database Engine]
- fail-safe operator [SQL Server]
- aliases [SQL Server], operators
- SQL Server Agent alerts, operators
- contact information [SQL Server Agent]
- net send [SQL Server]
- e-mail [SQL Server], SQL Server Agent operators
- pager notifications [SQL Server Agent]
- mail [SQL Server], SQL Server Agent operators
- operators (users) [Database Engine], defining
- jobs [SQL Server Agent], operators
- alerts [SQL Server], operators
ms.assetid: 38e8488f-2669-4cea-b9c3-5f394a663678
author: stevestein
ms.author: sstein
ms.openlocfilehash: d141a2db9a69603701200bc50dcac57ef402968a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747876"
---
# <a name="operators"></a><span data-ttu-id="bf0a8-102">Operadores</span><span class="sxs-lookup"><span data-stu-id="bf0a8-102">Operators</span></span>
  <span data-ttu-id="bf0a8-103">Los operadores son alias para personas o grupos que pueden recibir una notificación electrónica cuando los trabajos se completan o se activa una alerta.</span><span class="sxs-lookup"><span data-stu-id="bf0a8-103">Operators are aliases for people or groups that can receive electronic notification when jobs have completed or alerts have been raised.</span></span> <span data-ttu-id="bf0a8-104">El servicio Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] admite la notificación de administradores a través de operadores.</span><span class="sxs-lookup"><span data-stu-id="bf0a8-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service supports the notification of administrators through operators.</span></span> <span data-ttu-id="bf0a8-105">Los operadores habilitan las capacidades de notificación y supervisión del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bf0a8-105">Operators enable notification and monitoring capabilities of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span>  
  
## <a name="operator-attributes-and-concepts"></a><span data-ttu-id="bf0a8-106">Atributos y conceptos de operador</span><span class="sxs-lookup"><span data-stu-id="bf0a8-106">Operator Attributes and Concepts</span></span>  
 <span data-ttu-id="bf0a8-107">Los atributos principales de un operador son:</span><span class="sxs-lookup"><span data-stu-id="bf0a8-107">The primary attributes of an operator are:</span></span>  
  
-   <span data-ttu-id="bf0a8-108">Nombre del operador</span><span class="sxs-lookup"><span data-stu-id="bf0a8-108">Operator name</span></span>  
  
-   <span data-ttu-id="bf0a8-109">Información de contacto</span><span class="sxs-lookup"><span data-stu-id="bf0a8-109">Contact information</span></span>  
  
### <a name="naming-an-operator"></a><span data-ttu-id="bf0a8-110">Asignar nombres a operadores</span><span class="sxs-lookup"><span data-stu-id="bf0a8-110">Naming an Operator</span></span>  
 <span data-ttu-id="bf0a8-111">Cada operador debe tener asignado un nombre.</span><span class="sxs-lookup"><span data-stu-id="bf0a8-111">Every operator must have a name.</span></span> <span data-ttu-id="bf0a8-112">Los nombres de los operadores deben ser únicos en la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y no pueden tener más de **128** caracteres.</span><span class="sxs-lookup"><span data-stu-id="bf0a8-112">Operator names must be unique within the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance and can be no longer than **128** characters.</span></span>  
  
### <a name="contact-information"></a><span data-ttu-id="bf0a8-113">Información de contacto</span><span class="sxs-lookup"><span data-stu-id="bf0a8-113">Contact Information</span></span>  
 <span data-ttu-id="bf0a8-114">La información de contacto de un operador define cómo se va a notificar a dicho operador.</span><span class="sxs-lookup"><span data-stu-id="bf0a8-114">An operator's contact information defines how the operator is notified.</span></span> <span data-ttu-id="bf0a8-115">Se puede notificar a los operadores mediante correo electrónico, buscapersonas o con el comando **net send** :</span><span class="sxs-lookup"><span data-stu-id="bf0a8-115">Operators can be notified by e-mail, pager, or through the **net send** command:</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="bf0a8-116">Las opciones Buscapersonas y **net send** se quitarán del Agente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en una versión futura de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf0a8-116">The Pager and **net send** options will be removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in a future version of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="bf0a8-117">Evite utilizar estas características en los nuevos trabajos de programación y planee modificar las aplicaciones que actualmente las utilizan.</span><span class="sxs-lookup"><span data-stu-id="bf0a8-117">Avoid using these features in new development work, and plan to modify applications that currently use these features.</span></span>  
  
-   <span data-ttu-id="bf0a8-118">**Notificación mediante correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="bf0a8-118">**E-mail notification**</span></span>  
  
     <span data-ttu-id="bf0a8-119">La notificación por correo electrónico envía un mensaje de correo electrónico al operador.</span><span class="sxs-lookup"><span data-stu-id="bf0a8-119">E-mail notification sends an e-mail message to the operator.</span></span> <span data-ttu-id="bf0a8-120">Para la notificación por correo electrónico debe proporcionar una dirección de correo electrónico al operador.</span><span class="sxs-lookup"><span data-stu-id="bf0a8-120">For e-mail notification, you provide the e-mail address for the operator.</span></span>  
  
-   <span data-ttu-id="bf0a8-121">**Notificación mediante buscapersonas**</span><span class="sxs-lookup"><span data-stu-id="bf0a8-121">**Pager notification**</span></span>  
  
     <span data-ttu-id="bf0a8-122">Este tipo de notificación se implementa mediante el correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="bf0a8-122">Paging is implemented by e-mail.</span></span> <span data-ttu-id="bf0a8-123">Para la notificación por buscapersonas debe proporcionar una dirección de correo electrónico en la que el operador recibirá los mensajes del buscapersonas.</span><span class="sxs-lookup"><span data-stu-id="bf0a8-123">For pager notification, you provide the e-mail address where the operator receives pager messages.</span></span> <span data-ttu-id="bf0a8-124">Para establecer la notificación mediante buscapersonas, debe instalar en el servidor de correo un software que procese el correo entrante y lo convierta en mensajes de buscapersonas.</span><span class="sxs-lookup"><span data-stu-id="bf0a8-124">To set up pager notification, you must install software on the mail server that processes inbound mail and converts it to a pager message.</span></span> <span data-ttu-id="bf0a8-125">El software realizar diversas acciones, entre las que se incluyen:</span><span class="sxs-lookup"><span data-stu-id="bf0a8-125">The software can take one of several approaches, including:</span></span>  
  
    -   <span data-ttu-id="bf0a8-126">Reenviar el correo a un servidor de correo remoto en el sitio del proveedor del buscapersonas.</span><span class="sxs-lookup"><span data-stu-id="bf0a8-126">Forwarding the mail to a remote mail server at the site of the pager provider.</span></span>  
  
         <span data-ttu-id="bf0a8-127">El proveedor del buscapersonas debe ofrecer este servicio, aunque el software necesario generalmente está disponible como parte del sistema de correo local.</span><span class="sxs-lookup"><span data-stu-id="bf0a8-127">The pager provider must offer this service, although the software required is generally available as part of the local mail system.</span></span> <span data-ttu-id="bf0a8-128">Para obtener más información, vea la documentación del buscapersonas.</span><span class="sxs-lookup"><span data-stu-id="bf0a8-128">For more information, see your pager documentation.</span></span>  
  
    -   <span data-ttu-id="bf0a8-129">Enrutar el correo electrónico mediante Internet a un servidor de correo electrónico en el sitio del proveedor del buscapersonas.</span><span class="sxs-lookup"><span data-stu-id="bf0a8-129">Routing the e-mail by way of the Internet to an e-mail server at the pager provider's site.</span></span>  
  
         <span data-ttu-id="bf0a8-130">Es una variación del primer planteamiento.</span><span class="sxs-lookup"><span data-stu-id="bf0a8-130">This is a variation on the first approach.</span></span>  
  
    -   <span data-ttu-id="bf0a8-131">Procesar el mensaje de correo electrónico de entrada y llamar al número del buscapersonas mediante un módem conectado.</span><span class="sxs-lookup"><span data-stu-id="bf0a8-131">Processing the inbound e-mail and dialing the pager by using an attached modem.</span></span>  
  
         <span data-ttu-id="bf0a8-132">Este software es propiedad de los proveedores de servicios de localización.</span><span class="sxs-lookup"><span data-stu-id="bf0a8-132">This software is proprietary to pager service providers.</span></span> <span data-ttu-id="bf0a8-133">El software funciona como un cliente de correo electrónico que procesa periódicamente su bandeja de entrada mediante la interpretación de toda o parte de la información de la dirección de correo electrónico como un número de buscapersonas o mediante la correspondencia del nombre de correo electrónico con un número de buscapersonas en una tabla de traducción.</span><span class="sxs-lookup"><span data-stu-id="bf0a8-133">The software acts as a e-mail client that periodically processes its inbox either by interpreting all or part of the e-mail address information as a pager number, or by matching the e-mail name to a pager number in a translation table.</span></span>  
  
         <span data-ttu-id="bf0a8-134">Si todos los operadores comparten el mismo proveedor de buscapersonas, puede utilizar [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para especificar el formato especial de correo electrónico necesario para el sistema de conversión del buscapersonas a correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="bf0a8-134">If all of the operators share a pager provider, you can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to specify any special e-mail formatting that is required by the pager-to-e-mail system.</span></span> <span data-ttu-id="bf0a8-135">El formato especial puede ser un prefijo o un sufijo y puede incluirse en las siguientes líneas del mensaje de correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="bf0a8-135">The special formatting can be a prefix or a suffix and can be included in the following lines of the e-mail:</span></span>  
  
         <span data-ttu-id="bf0a8-136">**Firmante:**</span><span class="sxs-lookup"><span data-stu-id="bf0a8-136">**Subject:**</span></span>  
  
         <span data-ttu-id="bf0a8-137">**CC**:</span><span class="sxs-lookup"><span data-stu-id="bf0a8-137">**Cc**:</span></span>  
  
         <span data-ttu-id="bf0a8-138">**Para**:</span><span class="sxs-lookup"><span data-stu-id="bf0a8-138">**To**:</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bf0a8-139">Si utiliza un sistema de localización alfanumérica de baja capacidad, puede reducir el texto enviado si excluye el texto del error de la notificación del buscapersonas.</span><span class="sxs-lookup"><span data-stu-id="bf0a8-139">If you use a low-capacity alphanumeric paging system, you can shorten the text that is sent by excluding the error text from the pager notification.</span></span> <span data-ttu-id="bf0a8-140">Un sistema de localización alfanumérica de baja capacidad es, por ejemplo, uno que esté limitado a 64 caracteres por página.</span><span class="sxs-lookup"><span data-stu-id="bf0a8-140">An example of a low-capacity alphanumeric paging system is one that is limited to 64 characters per page.</span></span>  
  
-   <span data-ttu-id="bf0a8-141">**net sendnotification**</span><span class="sxs-lookup"><span data-stu-id="bf0a8-141">**net sendnotification**</span></span>  
  
     <span data-ttu-id="bf0a8-142">Envía un mensaje al operador mediante el comando **net send** .</span><span class="sxs-lookup"><span data-stu-id="bf0a8-142">This sends a message to the operator by means of the **net send** command.</span></span> <span data-ttu-id="bf0a8-143">Si usa **net send**, especifique el destinatario (el equipo o el usuario) de un mensaje de red.</span><span class="sxs-lookup"><span data-stu-id="bf0a8-143">For **net send**, specify the recipient (computer or user) of a network message.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bf0a8-144">El comando **net send** usa Microsoft Windows Messenger.</span><span class="sxs-lookup"><span data-stu-id="bf0a8-144">The **net send** command uses Microsoft Windows Messenger.</span></span> <span data-ttu-id="bf0a8-145">Para enviar alertas correctamente, este servicio debe ejecutarse tanto en el equipo en el que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se está ejecutando como en el equipo que usa el operador.</span><span class="sxs-lookup"><span data-stu-id="bf0a8-145">To successfully send alerts, this service must be running on both the computer on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running and the computer that the operator uses.</span></span>  
  
## <a name="alerting-and-fail-safe-operators"></a><span data-ttu-id="bf0a8-146">Alertas y operadores para notificaciones de error</span><span class="sxs-lookup"><span data-stu-id="bf0a8-146">Alerting and Fail-Safe Operators</span></span>  
 <span data-ttu-id="bf0a8-147">Puede elegir a qué operadores notificará en respuesta a una alerta.</span><span class="sxs-lookup"><span data-stu-id="bf0a8-147">You can choose which operators are to be notified in response to an alert.</span></span> <span data-ttu-id="bf0a8-148">Por ejemplo, puede asignar responsabilidades rotativas para notificar a los operadores mediante la programación de alertas.</span><span class="sxs-lookup"><span data-stu-id="bf0a8-148">For example, you can assign rotating responsibilities for operator notification by scheduling alerts.</span></span> <span data-ttu-id="bf0a8-149">Por ejemplo, se notifica a A de las alertas que se producen los lunes, miércoles o viernes, y a B de las que se producen los martes, jueves y sábados.</span><span class="sxs-lookup"><span data-stu-id="bf0a8-149">For example, Individual A is notified of alerts that occur on Monday, Wednesday, or Friday, and Individual B is notified of alerts that occur on Tuesday, Thursday, or Saturday.</span></span>  
  
 <span data-ttu-id="bf0a8-150">El operador para notificaciones de error recibe la notificación de una alerta después de que no se haya recibido respuesta a ninguna de las notificaciones enviadas mediante buscapersonas a los operadores designados.</span><span class="sxs-lookup"><span data-stu-id="bf0a8-150">The fail-safe operator receives an alert notification after all pager notifications to the designated operators have failed.</span></span> <span data-ttu-id="bf0a8-151">Por ejemplo, si ha definido tres operadores para las notificaciones mediante buscapersonas y no se pueden enviar mensajes al buscapersonas de ninguno de ellos, entonces se notificará al operador para notificaciones de error.</span><span class="sxs-lookup"><span data-stu-id="bf0a8-151">For example, if you have defined three operators for pager notifications and none of the designated operators can be paged, the fail-safe operator is notified.</span></span>  
  
 <span data-ttu-id="bf0a8-152">Se notifica al operador para notificaciones de error cuando:</span><span class="sxs-lookup"><span data-stu-id="bf0a8-152">The fail-safe operator is notified when:</span></span>  
  
-   <span data-ttu-id="bf0a8-153">No se pueden enviar mensajes al localizador de ninguno de los operadores responsables de la alerta.</span><span class="sxs-lookup"><span data-stu-id="bf0a8-153">The operators responsible for the alert could not be paged.</span></span>  
  
     <span data-ttu-id="bf0a8-154">Entre los motivos que impiden contactar con los operadores principales se incluyen el uso de direcciones de buscapersonas incorrectas y los operadores fuera de servicio.</span><span class="sxs-lookup"><span data-stu-id="bf0a8-154">Reasons for failure to reach primary operators include incorrect pager addresses and off-duty operators.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="bf0a8-155">El Agente no puede tener acceso a las tablas del sistema en la base de datos **msdb** .</span><span class="sxs-lookup"><span data-stu-id="bf0a8-155">Agent cannot access system tables in the **msdb** database.</span></span>  
  
     <span data-ttu-id="bf0a8-156">La tabla del sistema **sysnotifications** especifica las responsabilidades de los operadores respecto a las alertas.</span><span class="sxs-lookup"><span data-stu-id="bf0a8-156">The **sysnotifications** system table specifies operator responsibilities for alerts.</span></span>  
  
 <span data-ttu-id="bf0a8-157">El operador para notificaciones de error es una característica de seguridad.</span><span class="sxs-lookup"><span data-stu-id="bf0a8-157">The fail-safe operator is a security feature.</span></span> <span data-ttu-id="bf0a8-158">Para eliminar el operador asignado al servicio a prueba de errores debe reasignar el servicio a otro operador o eliminar completamente la asignación a prueba de errores.</span><span class="sxs-lookup"><span data-stu-id="bf0a8-158">You cannot delete the operator assigned to fail-safe duty without reassigning fail-safe duty to another operator, or deleting the fail-safe assignment altogether.</span></span>  
  
## <a name="notifying-an-operator"></a><span data-ttu-id="bf0a8-159">Notificación de un operador</span><span class="sxs-lookup"><span data-stu-id="bf0a8-159">Notifying an Operator</span></span>  
 <span data-ttu-id="bf0a8-160">Debe configurar al menos uno de los elementos siguientes para poder notificar a un operador:</span><span class="sxs-lookup"><span data-stu-id="bf0a8-160">You must set up one or more of the following in order to notify an operator:</span></span>  
  
-   <span data-ttu-id="bf0a8-161">Para enviar un mensaje de correo electrónico mediante la funcionalidad Correo electrónico de base de datos, debe tener acceso a un servidor de correo electrónico que admita SMTP.</span><span class="sxs-lookup"><span data-stu-id="bf0a8-161">To send e-mail with Database Mail functionality, you must have access to an e-mail server that supports SMTP.</span></span>  
  
-   <span data-ttu-id="bf0a8-162">Para notificar mediante un buscapersonas, debe disponer de hardware o software de otros fabricantes para enviar mensajes de buscapersonas a correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="bf0a8-162">For paging, you must have third-party pager-to-e-mail software and/or hardware.</span></span>  
  
-   <span data-ttu-id="bf0a8-163">Para usar **net send**, el operador debe haber iniciado sesión en el equipo especificado y el equipo especificado debe permitir la recepción de mensajes desde Windows Messenger.</span><span class="sxs-lookup"><span data-stu-id="bf0a8-163">To use **net send**, the operator must be logged on to the specified computer, and the specified computer must allow messages from Windows Messenger.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="bf0a8-164">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="bf0a8-164">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bf0a8-165">**Tareas**</span><span class="sxs-lookup"><span data-stu-id="bf0a8-165">**Tasks**</span></span>|<span data-ttu-id="bf0a8-166">**Tema.**</span><span class="sxs-lookup"><span data-stu-id="bf0a8-166">**Topic**</span></span>|  
|<span data-ttu-id="bf0a8-167">Tareas relacionadas con la creación de un operador</span><span class="sxs-lookup"><span data-stu-id="bf0a8-167">Tasks related to creating an operator</span></span>|[<span data-ttu-id="bf0a8-168">Crear un operador</span><span class="sxs-lookup"><span data-stu-id="bf0a8-168">Create an Operator</span></span>](create-an-operator.md)<br /><br /> [<span data-ttu-id="bf0a8-169">Designate a Fail-Safe Operator</span><span class="sxs-lookup"><span data-stu-id="bf0a8-169">Designate a Fail-Safe Operator</span></span>](designate-a-fail-safe-operator.md)|  
|<span data-ttu-id="bf0a8-170">Tareas relacionadas con la asignación de alertas</span><span class="sxs-lookup"><span data-stu-id="bf0a8-170">Tasks related to assigning alerts</span></span>|[<span data-ttu-id="bf0a8-171">Asignar alertas a un operador</span><span class="sxs-lookup"><span data-stu-id="bf0a8-171">Assign Alerts to an Operator</span></span>](assign-alerts-to-an-operator.md)<br /><br /> [<span data-ttu-id="bf0a8-172">Definir la respuesta a una alerta &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="bf0a8-172">Define the Response to an Alert &#40;SQL Server Management Studio&#41;</span></span>](define-the-response-to-an-alert-sql-server-management-studio.md)<br /><br /> [<span data-ttu-id="bf0a8-173">sp_add_notification &#40;&#41;de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bf0a8-173">sp_add_notification &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql)<br /><br /> [<span data-ttu-id="bf0a8-174">Asignar alertas a un operador</span><span class="sxs-lookup"><span data-stu-id="bf0a8-174">Assign Alerts to an Operator</span></span>](assign-alerts-to-an-operator.md)|  
  
## <a name="see-also"></a><span data-ttu-id="bf0a8-175">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bf0a8-175">See Also</span></span>  
 [<span data-ttu-id="bf0a8-176">Correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="bf0a8-176">Database Mail</span></span>](../../relational-databases/database-mail/database-mail.md)  
  
  
