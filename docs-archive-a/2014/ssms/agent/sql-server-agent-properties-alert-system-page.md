---
title: Propiedades de Agente SQL Server (página Sistema de alerta) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.alert.f1
ms.assetid: 3e6d3bfd-20ee-4593-86cc-f65b1c08c69d
author: stevestein
ms.author: sstein
ms.openlocfilehash: ff203be21efbd99b90f02261cfe94dd49bd0d849
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676305"
---
# <a name="sql-server-agent-properties-alert-system-page"></a><span data-ttu-id="fa085-102">Propiedades de Agente SQL Server (página Sistema de alerta)</span><span class="sxs-lookup"><span data-stu-id="fa085-102">SQL Server Agent Properties (Alert System Page)</span></span>
  <span data-ttu-id="fa085-103">Use esta página para ver y modificar la configuración de los mensajes enviados por alertas del Agente [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fa085-103">Use this page to view and modify the settings for messages sent by [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts.</span></span>  
  
## <a name="options"></a><span data-ttu-id="fa085-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="fa085-104">Options</span></span>  
 <span data-ttu-id="fa085-105">**Sesión de correo**</span><span class="sxs-lookup"><span data-stu-id="fa085-105">**Mail session**</span></span>  
 <span data-ttu-id="fa085-106">Las opciones de esta sección configuran el correo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fa085-106">The options in this section configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Mail.</span></span>  
  
 <span data-ttu-id="fa085-107">**Habilitar perfil de correo**</span><span class="sxs-lookup"><span data-stu-id="fa085-107">**Enable mail profile**</span></span>  
 <span data-ttu-id="fa085-108">Habilita el correo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fa085-108">Enables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Mail.</span></span> <span data-ttu-id="fa085-109">De forma predeterminada, el correo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no está habilitado.</span><span class="sxs-lookup"><span data-stu-id="fa085-109">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Mail is not enabled.</span></span>  
  
 <span data-ttu-id="fa085-110">**Sistema de correo**</span><span class="sxs-lookup"><span data-stu-id="fa085-110">**Mail System**</span></span>  
 <span data-ttu-id="fa085-111">Establece el sistema de correo que debe utilizar el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fa085-111">Sets the mail system for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to use.</span></span> <span data-ttu-id="fa085-112">Correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="fa085-112">Database Mail</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fa085-113">Después de cambiar el sistema de correo electrónico, debe reiniciar el servicio del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para que el cambio entre en vigor.</span><span class="sxs-lookup"><span data-stu-id="fa085-113">After changing the e-mail system, you must restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service for the change to take effect.</span></span>  
  
 <span data-ttu-id="fa085-114">**Perfil de correo**</span><span class="sxs-lookup"><span data-stu-id="fa085-114">**Mail Profile**</span></span>  
 <span data-ttu-id="fa085-115">Establece el perfil que debe utilizar el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fa085-115">Sets the profile for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to use.</span></span> <span data-ttu-id="fa085-116">También puede seleccionar **\<new Database Mail profile...>** para crear un nuevo perfil.</span><span class="sxs-lookup"><span data-stu-id="fa085-116">You may also select **\<new Database Mail profile...>** to create a new profile.</span></span>  
  
 <span data-ttu-id="fa085-117">**Correo electrónico de buscapersonas**</span><span class="sxs-lookup"><span data-stu-id="fa085-117">**Pager e-mails**</span></span>  
 <span data-ttu-id="fa085-118">Las opciones de esta sección le permiten configurar los mensajes de correo electrónico enviados a direcciones de buscapersonas para que funcionen con su sistema de buscapersonas.</span><span class="sxs-lookup"><span data-stu-id="fa085-118">The options in this section allow you to configure e-mail messages sent to pager addresses to work with your paging system.</span></span>  
  
 <span data-ttu-id="fa085-119">**Formato de dirección para correo electrónico de buscapersonas**</span><span class="sxs-lookup"><span data-stu-id="fa085-119">**Address formatting for pager e-mails**</span></span>  
 <span data-ttu-id="fa085-120">Esta sección le permite especificar el formato de las direcciones y la línea de asunto que se incluyen en los mensajes de correo electrónico de buscapersonas.</span><span class="sxs-lookup"><span data-stu-id="fa085-120">This section allows you to specify the format of the addresses and the subject line included in pager e-mails.</span></span>  
  
 <span data-ttu-id="fa085-121">**Línea Para**</span><span class="sxs-lookup"><span data-stu-id="fa085-121">**To line**</span></span>  
 <span data-ttu-id="fa085-122">Especifica las opciones de la línea **Para** del mensaje</span><span class="sxs-lookup"><span data-stu-id="fa085-122">Specifies the options for the **To** line of the message</span></span>  
  
 <span data-ttu-id="fa085-123">**Prefijo**</span><span class="sxs-lookup"><span data-stu-id="fa085-123">**Prefix**</span></span>  
 <span data-ttu-id="fa085-124">Escriba cualquier tipo de texto fijo que su sistema exija al principio de la línea **Para** de los mensajes que se envían a un buscapersonas.</span><span class="sxs-lookup"><span data-stu-id="fa085-124">Type any fixed text that your system requires at the beginning of the **To** line of messages sent to a pager.</span></span>  
  
 <span data-ttu-id="fa085-125">**Buscapersonas**</span><span class="sxs-lookup"><span data-stu-id="fa085-125">**Pager**</span></span>  
 <span data-ttu-id="fa085-126">Incluye la dirección de correo electrónico del mensaje entre el prefijo y el sufijo.</span><span class="sxs-lookup"><span data-stu-id="fa085-126">Includes the e-mail address for the message between the prefix and the suffix.</span></span>  
  
 <span data-ttu-id="fa085-127">**Sufijo**</span><span class="sxs-lookup"><span data-stu-id="fa085-127">**Suffix**</span></span>  
 <span data-ttu-id="fa085-128">Escriba cualquier tipo de texto fijo que su sistema de localización exija al final de la línea **Para** de los mensajes que se envían a un buscapersonas.</span><span class="sxs-lookup"><span data-stu-id="fa085-128">Type any fixed text that your paging system requires at the end of the **To** line of messages sent to a pager.</span></span>  
  
 <span data-ttu-id="fa085-129">**Línea CC**</span><span class="sxs-lookup"><span data-stu-id="fa085-129">**Cc line**</span></span>  
 <span data-ttu-id="fa085-130">Especifica las opciones de la línea **CC** del mensaje.</span><span class="sxs-lookup"><span data-stu-id="fa085-130">Specifies options for the **Cc** line of the message.</span></span>  
  
 <span data-ttu-id="fa085-131">**Prefijo**</span><span class="sxs-lookup"><span data-stu-id="fa085-131">**Prefix**</span></span>  
 <span data-ttu-id="fa085-132">Escriba cualquier tipo de texto fijo que su sistema exija al principio de la línea **CC** de los mensajes que se envían a un buscapersonas.</span><span class="sxs-lookup"><span data-stu-id="fa085-132">Type any fixed text that your system requires at the beginning of the **Cc** line of messages sent to a pager.</span></span>  
  
 <span data-ttu-id="fa085-133">**Buscapersonas**</span><span class="sxs-lookup"><span data-stu-id="fa085-133">**Pager**</span></span>  
 <span data-ttu-id="fa085-134">Incluye la dirección de correo electrónico del mensaje entre el prefijo y el sufijo.</span><span class="sxs-lookup"><span data-stu-id="fa085-134">Includes the e-mail address for the message between the prefix and the suffix.</span></span>  
  
 <span data-ttu-id="fa085-135">**Sufijo**</span><span class="sxs-lookup"><span data-stu-id="fa085-135">**Suffix**</span></span>  
 <span data-ttu-id="fa085-136">Escriba cualquier tipo de texto fijo que su sistema de localización exija al final de la línea **CC** de los mensajes que se envían a un buscapersonas.</span><span class="sxs-lookup"><span data-stu-id="fa085-136">Type any fixed text that your paging system requires at the end of the **Cc** line of messages sent to a pager.</span></span>  
  
 <span data-ttu-id="fa085-137">**Subject**</span><span class="sxs-lookup"><span data-stu-id="fa085-137">**Subject**</span></span>  
 <span data-ttu-id="fa085-138">Especifica las opciones del asunto del mensaje</span><span class="sxs-lookup"><span data-stu-id="fa085-138">Specifies the options for the subject of the message.</span></span>  
  
 <span data-ttu-id="fa085-139">**Prefijo**</span><span class="sxs-lookup"><span data-stu-id="fa085-139">**Prefix**</span></span>  
 <span data-ttu-id="fa085-140">Escriba cualquier tipo de texto fijo que su sistema de localización exija al principio de la línea **Asunto** de los mensajes que se envían a un buscapersonas.</span><span class="sxs-lookup"><span data-stu-id="fa085-140">Type any fixed text that your paging system requires at the beginning of the **Subject** line of messages sent to a pager.</span></span>  
  
 <span data-ttu-id="fa085-141">**Sufijo**</span><span class="sxs-lookup"><span data-stu-id="fa085-141">**Suffix**</span></span>  
 <span data-ttu-id="fa085-142">Escriba cualquier tipo de texto fijo que su sistema de localización exija al final de la línea **Asunto** de los mensajes que se envían a un buscapersonas.</span><span class="sxs-lookup"><span data-stu-id="fa085-142">Type any fixed text that your paging system requires at the end of the **Subject** line of messages sent to a pager.</span></span>  
  
 <span data-ttu-id="fa085-143">**Incluir cuerpo del mensaje en la notificación**</span><span class="sxs-lookup"><span data-stu-id="fa085-143">**Include body of e-mail in notification message**</span></span>  
 <span data-ttu-id="fa085-144">Incluye el cuerpo de un mensaje de correo electrónico en el mensaje que se envía al buscapersonas.</span><span class="sxs-lookup"><span data-stu-id="fa085-144">Includes the body of the e-mail message in the message sent to the pager.</span></span>  
  
 <span data-ttu-id="fa085-145">**Operador para notificaciones de error**</span><span class="sxs-lookup"><span data-stu-id="fa085-145">**Fail-safe operator**</span></span>  
 <span data-ttu-id="fa085-146">Esta sección le permite especificar las opciones del operador para notificaciones de error.</span><span class="sxs-lookup"><span data-stu-id="fa085-146">This section allows you to specify the options for the fail-safe operator.</span></span>  
  
 <span data-ttu-id="fa085-147">**Habilitar operador para notificaciones de error**</span><span class="sxs-lookup"><span data-stu-id="fa085-147">**Enable fail-safe operator**</span></span>  
 <span data-ttu-id="fa085-148">Especifica un operador para notificaciones de error.</span><span class="sxs-lookup"><span data-stu-id="fa085-148">Specifies a fail safe operator.</span></span>  
  
 <span data-ttu-id="fa085-149">**Operador**</span><span class="sxs-lookup"><span data-stu-id="fa085-149">**Operator**</span></span>  
 <span data-ttu-id="fa085-150">Establece el nombre del operador para recibir notificaciones de error.</span><span class="sxs-lookup"><span data-stu-id="fa085-150">Sets the name of the operator to receive fail-safe notifications.</span></span>  
  
 <span data-ttu-id="fa085-151">**Notificar mediante**</span><span class="sxs-lookup"><span data-stu-id="fa085-151">**Notify using**</span></span>  
 <span data-ttu-id="fa085-152">Establece el método que se va a utilizar para las notificaciones al operador para notificaciones de error.</span><span class="sxs-lookup"><span data-stu-id="fa085-152">Sets the method to use for notifying the fail-safe operator.</span></span>  
  
 <span data-ttu-id="fa085-153">**Reemplazo de tokens**</span><span class="sxs-lookup"><span data-stu-id="fa085-153">**Token Replacement**</span></span>  
 <span data-ttu-id="fa085-154">Esta sección le permite habilitar tokens de paso de trabajo que pueden utilizarse en trabajos ejecutados por alertas del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fa085-154">This section allows you to enable job step tokens that can be used in jobs run by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts.</span></span> <span data-ttu-id="fa085-155">Para más información sobre los tokens de paso de trabajo, consulte [Usar tokens en pasos de trabajo](use-tokens-in-job-steps.md).</span><span class="sxs-lookup"><span data-stu-id="fa085-155">For more information about job step tokens, see [Use Tokens in Job Steps](use-tokens-in-job-steps.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fa085-156">Todos los usuarios de Windows con permisos de escritura en el Registro de eventos de Windows pueden tener acceso a pasos de trabajo activados por alertas del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fa085-156">Any Windows user with write permissions on the Windows Event Log may be able to access job steps that are activated by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts.</span></span> <span data-ttu-id="fa085-157">Para evitar este riesgo de seguridad, se deshabilitan de manera predeterminada los tokens del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que pueden utilizarse en trabajos activados por alertas.</span><span class="sxs-lookup"><span data-stu-id="fa085-157">To avoid this security risk, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent tokens that can be used in jobs activated by alerts are disabled by default.</span></span> <span data-ttu-id="fa085-158">Los tokens son: **$(A-DBN)** , **$(A-SVR)** , **$(A-ERR)** , **$(A-SEV)** y **$(A-MSG)** .</span><span class="sxs-lookup"><span data-stu-id="fa085-158">These tokens are: **$(A-DBN)**, **$(A-SVR)**, **$(A-ERR)**, **$(A-SEV)**, and **$(A-MSG)**.</span></span>  
>   
>  <span data-ttu-id="fa085-159">Si necesita utilizar estos tokens, asegúrese de que solo los miembros de grupos de seguridad confiables de Windows, tales como el grupo de administradores, tengan permisos de escritura en el Registro de eventos del equipo en el que reside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , antes de habilitarlos.</span><span class="sxs-lookup"><span data-stu-id="fa085-159">If you need to use these tokens, ensure that only members of trusted Windows security groups, such as the Administrators group, have write permissions on the Event Log of the computer where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resides before enabling them.</span></span>  
  
 <span data-ttu-id="fa085-160">**Reemplazar tokens para todas las respuestas de trabajos a alertas**</span><span class="sxs-lookup"><span data-stu-id="fa085-160">**Replace tokens for all job responses to alerts**</span></span>  
 <span data-ttu-id="fa085-161">Seleccione esta casilla para habilitar el reemplazo de tokens en trabajos activados por alertas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fa085-161">Select this check box to enable token replacement for jobs that are activated by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alerts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa085-162">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fa085-162">See Also</span></span>  
 <span data-ttu-id="fa085-163">[Operadores](operators.md) </span><span class="sxs-lookup"><span data-stu-id="fa085-163">[Operators](operators.md) </span></span>  
 <span data-ttu-id="fa085-164">[Configurar Agente SQL Server mail para usar Correo electrónico de base de datos](../../relational-databases/database-mail/configure-sql-server-agent-mail-to-use-database-mail.md) </span><span class="sxs-lookup"><span data-stu-id="fa085-164">[Configure SQL Server Agent Mail to Use Database Mail](../../relational-databases/database-mail/configure-sql-server-agent-mail-to-use-database-mail.md) </span></span>  
 [<span data-ttu-id="fa085-165">Correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="fa085-165">Database Mail</span></span>](../../relational-databases/database-mail/database-mail.md)  
  
  
