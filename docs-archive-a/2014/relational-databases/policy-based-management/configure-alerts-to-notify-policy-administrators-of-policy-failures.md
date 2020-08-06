---
title: Configurar alertas para notificar los errores de directiva a los administradores de directivas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, configure alerts
ms.assetid: e8e60159-d5b0-49d5-91f3-af8e9cb994c1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9eb84ced3bb6313dd5920deaf479925556f08fc4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744066"
---
# <a name="configure-alerts-to-notify-policy-administrators-of-policy-failures"></a><span data-ttu-id="a4bde-102">Configurar alertas para notificar los errores de directiva a los administradores de directivas</span><span class="sxs-lookup"><span data-stu-id="a4bde-102">Configure Alerts to Notify Policy Administrators of Policy Failures</span></span>
  <span data-ttu-id="a4bde-103">Cuando las directivas de administración basada en directivas se ejecutan en uno de los tres modos de evaluación automatizados, si se produce la infracción de una directiva, se escribe un mensaje en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="a4bde-103">When Policy-Based Management policies are executed in one of the three automated evaluation modes, if a policy violation occurs, a message is written to the event log.</span></span> <span data-ttu-id="a4bde-104">Para que se le notifique cuando este mensaje se escribe en el registro de eventos, puede crear una alerta que se active al detectar el mensaje y permita realizar una acción.</span><span class="sxs-lookup"><span data-stu-id="a4bde-104">To be notified when this message is written to the event log, you can create an alert to detect the message and perform an action.</span></span> <span data-ttu-id="a4bde-105">La alerta debería detectar los mensajes que se muestran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="a4bde-105">The alert should detect the messages as shown in the following table.</span></span>  
  
|<span data-ttu-id="a4bde-106">Modo de ejecución</span><span class="sxs-lookup"><span data-stu-id="a4bde-106">Execution mode</span></span>|<span data-ttu-id="a4bde-107">Número de mensaje</span><span class="sxs-lookup"><span data-stu-id="a4bde-107">Message number</span></span>|  
|--------------------|--------------------|  
|<span data-ttu-id="a4bde-108">Al cambiar: impedir</span><span class="sxs-lookup"><span data-stu-id="a4bde-108">On change: prevent</span></span><br /><br /> <span data-ttu-id="a4bde-109">(si es Automático)</span><span class="sxs-lookup"><span data-stu-id="a4bde-109">(if automatic)</span></span>|<span data-ttu-id="a4bde-110">34050</span><span class="sxs-lookup"><span data-stu-id="a4bde-110">34050</span></span>|  
|<span data-ttu-id="a4bde-111">Al cambiar: impedir</span><span class="sxs-lookup"><span data-stu-id="a4bde-111">On change: prevent</span></span><br /><br /> <span data-ttu-id="a4bde-112">(si es A petición)</span><span class="sxs-lookup"><span data-stu-id="a4bde-112">(if On demand)</span></span>|<span data-ttu-id="a4bde-113">34051</span><span class="sxs-lookup"><span data-stu-id="a4bde-113">34051</span></span>|  
|<span data-ttu-id="a4bde-114">Al programar</span><span class="sxs-lookup"><span data-stu-id="a4bde-114">On schedule</span></span>|<span data-ttu-id="a4bde-115">34052</span><span class="sxs-lookup"><span data-stu-id="a4bde-115">34052</span></span>|  
|<span data-ttu-id="a4bde-116">Al cambiar</span><span class="sxs-lookup"><span data-stu-id="a4bde-116">On change</span></span>|<span data-ttu-id="a4bde-117">34053</span><span class="sxs-lookup"><span data-stu-id="a4bde-117">34053</span></span>|  
  
 <span data-ttu-id="a4bde-118">Si desea configurar una alerta para responder a los mensajes de error de administración basada en directivas, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="a4bde-118">To set up an alert to respond to the Policy-Based Management error messages, see the following topics:</span></span>  
  
-   [<span data-ttu-id="a4bde-119">Crear un operador</span><span class="sxs-lookup"><span data-stu-id="a4bde-119">Create an Operator</span></span>](../../ssms/agent/create-an-operator.md)  
  
-   [<span data-ttu-id="a4bde-120">Create an Alert Using an Error Number</span><span class="sxs-lookup"><span data-stu-id="a4bde-120">Create an Alert Using an Error Number</span></span>](../../ssms/agent/create-an-alert-using-an-error-number.md)  
  
-   [<span data-ttu-id="a4bde-121">Asignar alertas a un operador</span><span class="sxs-lookup"><span data-stu-id="a4bde-121">Assign Alerts to an Operator</span></span>](../../ssms/agent/assign-alerts-to-an-operator.md)  
  
## <a name="permissions"></a><span data-ttu-id="a4bde-122">Permisos</span><span class="sxs-lookup"><span data-stu-id="a4bde-122">Permissions</span></span>  
 <span data-ttu-id="a4bde-123">Cuando las directivas se evalúan a petición, se ejecutan en el contexto de seguridad del usuario.</span><span class="sxs-lookup"><span data-stu-id="a4bde-123">When policies are evaluated on demand, they execute in the security context of the user.</span></span> <span data-ttu-id="a4bde-124">Para escribir en el registro de errores, el usuario debe tener los permisos ALTER TRACE o ser miembro del rol fijo de servidor sysadmin.</span><span class="sxs-lookup"><span data-stu-id="a4bde-124">To write to the error log, the user must have ALTER TRACE permissions or be a member of the sysadmin fixed server role.</span></span> <span data-ttu-id="a4bde-125">Las directivas que evalúe un usuario que tenga menos privilegios no escribirán en el registro de eventos y no desencadenarán una alerta.</span><span class="sxs-lookup"><span data-stu-id="a4bde-125">Policies that are evaluated by a user that has less privileges will not write to the event log, and will not fire an alert.</span></span>  
  
 <span data-ttu-id="a4bde-126">Los modos de ejecución automatizados se ejecutan como un miembro del rol sysadmin.</span><span class="sxs-lookup"><span data-stu-id="a4bde-126">The automated execution modes execute as a member of the sysadmin role.</span></span> <span data-ttu-id="a4bde-127">Esto permite que la directiva se escriba en el registro de errores y se genere una alerta.</span><span class="sxs-lookup"><span data-stu-id="a4bde-127">This allows the policy to write to the error log and raise an alert.</span></span>  
  
## <a name="additional-considerations-about-alerts"></a><span data-ttu-id="a4bde-128">Consideraciones adicionales sobre las alertas</span><span class="sxs-lookup"><span data-stu-id="a4bde-128">Additional Considerations About Alerts</span></span>  
 <span data-ttu-id="a4bde-129">Tenga en cuenta las consideraciones adicionales siguientes acerca de las alertas:</span><span class="sxs-lookup"><span data-stu-id="a4bde-129">Be aware of the following additional considerations about alerts:</span></span>  
  
-   <span data-ttu-id="a4bde-130">Las alertas solo se generan para las directivas que están habilitadas.</span><span class="sxs-lookup"><span data-stu-id="a4bde-130">Alerts are raised only for policies that are enabled.</span></span> <span data-ttu-id="a4bde-131">Dado que las directivas **A petición** no pueden estar habilitadas, no se generan alertas para las directivas que se ejecutan a petición.</span><span class="sxs-lookup"><span data-stu-id="a4bde-131">Because **On demand** policies cannot be enabled, alerts are not raised for policies that are executed on demand.</span></span>  
  
-   <span data-ttu-id="a4bde-132">Si la acción que desea tomar incluye enviar un mensaje de correo electrónico, debe configurar una cuenta de correo.</span><span class="sxs-lookup"><span data-stu-id="a4bde-132">If the action you want to take includes sending an e-mail message, you must configure a mail account.</span></span> <span data-ttu-id="a4bde-133">Recomendamos usar Correo electrónico de base de datos.</span><span class="sxs-lookup"><span data-stu-id="a4bde-133">We recommend that you use Database Mail.</span></span> <span data-ttu-id="a4bde-134">Para obtener más información sobre cómo configurar Correo electrónico de base de datos, vea [Crear una nueva cuenta de Correo electrónico de base de datos](../database-mail/create-a-database-mail-account.md).</span><span class="sxs-lookup"><span data-stu-id="a4bde-134">For more information about how to set up Database Mail, see [Create a Database Mail Account](../database-mail/create-a-database-mail-account.md).</span></span>  
  
  
