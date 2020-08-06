---
title: Crear un evento definido por el usuario | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent alerts, user-defined events
- user-defined events [SQL Server]
- multiple language support [SQL Server], alerts
- languages [SQL Server], alerts
- severity levels [SQL Server]
- global considerations [SQL Server], alerts
- events [SQL Server], user-defined
- SQL Server Agent alerts, multiple-language environments
- alerts [SQL Server], user-defined events
- alerts [SQL Server], multiple-language environments
- custom events [SQL Server Agent]
- international considerations [SQL Server], alerts
ms.assetid: 03d71a35-97fa-4bba-aa9a-23ac9c9cf879
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2323dc4da3d1a8a67dad41ea189877ade25eff0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751642"
---
# <a name="create-a-user-defined-event"></a><span data-ttu-id="edf71-102">Crear un evento definido por el usuario</span><span class="sxs-lookup"><span data-stu-id="edf71-102">Create a User-Defined Event</span></span>
  <span data-ttu-id="edf71-103">Puede crear eventos definidos por el usuario si desea supervisar los eventos distintos de otros predefinidos por [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="edf71-103">You can create user-defined events if you want to monitor events other than events that are predefined by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="edf71-104">También puede asignar un nivel de gravedad a cada evento definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="edf71-104">You can also assign a severity level to each user-defined event.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="edf71-105">Cuando use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], seleccione la opción **Escribir en el registro de eventos de aplicación Windows** para cada mensaje de evento definido por el usuario, y garantizar así que se registran los mensajes.</span><span class="sxs-lookup"><span data-stu-id="edf71-105">When using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], select the **Write to Windows application event log** option for each user-defined event message, to ensure that the messages are logged.</span></span> <span data-ttu-id="edf71-106">De manera predeterminada, los mensajes definidos por el usuario con niveles de gravedad inferiores a 19 no se envían al registro de aplicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows cuando se producen.</span><span class="sxs-lookup"><span data-stu-id="edf71-106">By default, user-defined messages of severity lower than 19 are not sent to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows application log when they occur.</span></span> <span data-ttu-id="edf71-107">Por tanto, no desencadenan alertas del Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="edf71-107">User-defined messages of severity lower than 19 therefore do not trigger SQL Server Agent alerts.</span></span>  
  
 <span data-ttu-id="edf71-108">Los mensajes de eventos definidos por el usuario deben tener un número de mensaje exclusivo.</span><span class="sxs-lookup"><span data-stu-id="edf71-108">User-defined events must have a unique message number.</span></span> <span data-ttu-id="edf71-109">Los números de los mensajes de eventos definidos por el usuario deben ser mayores de 50.000.</span><span class="sxs-lookup"><span data-stu-id="edf71-109">Message numbers for a user-defined event must be greater than 50,000.</span></span> <span data-ttu-id="edf71-110">Se pueden definir mensajes para el evento en varios idiomas.</span><span class="sxs-lookup"><span data-stu-id="edf71-110">You can define messages for the event in multiple languages.</span></span> <span data-ttu-id="edf71-111">No obstante, debe existir un mensaje de error en **En-US** para que se puedan agregar mensajes en otros idiomas.</span><span class="sxs-lookup"><span data-stu-id="edf71-111">However, an **En-US** error message must exist before messages in other languages can be added.</span></span>  
  
 <span data-ttu-id="edf71-112">Si administra un entorno [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en varios idiomas, cree mensajes definidos por el usuario en cada uno de los idiomas admitidos.</span><span class="sxs-lookup"><span data-stu-id="edf71-112">If you administer a multiple-language [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] environment, create user-defined messages in each of the languages that are supported.</span></span> <span data-ttu-id="edf71-113">Por ejemplo, si crea un nuevo mensaje de evento que se va a utilizar en un servidor en inglés y en alemán, utilice el mismo número de mensaje para ambos, pero asigne un idioma distinto a cada uno.</span><span class="sxs-lookup"><span data-stu-id="edf71-113">For example, if you are creating a new event message to be used on both an English and a German server, use the same message number and severity for both, but assign a different language to each.</span></span>  
  
 <span data-ttu-id="edf71-114">Las tareas siguientes ofrecen información acerca de cómo crear eventos definidos por el usuario y alertas que respondan a los eventos:</span><span class="sxs-lookup"><span data-stu-id="edf71-114">The following tasks provide information about how to create user-defined events and alerts that respond to them:</span></span>  
  
 <span data-ttu-id="edf71-115">**Para crear una alerta basada en un número de mensaje**</span><span class="sxs-lookup"><span data-stu-id="edf71-115">**To create an alert based on a message number**</span></span>  
  
-   [<span data-ttu-id="edf71-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="edf71-116">SQL Server Management Studio</span></span>](create-an-alert-using-an-error-number.md)  
  
-   [<span data-ttu-id="edf71-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="edf71-117">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql)  
  
 <span data-ttu-id="edf71-118">**Para crear una alerta basada en niveles de gravedad**</span><span class="sxs-lookup"><span data-stu-id="edf71-118">**To create an alert based on severity levels**</span></span>  
  
-   [<span data-ttu-id="edf71-119">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="edf71-119">SQL Server Management Studio</span></span>](create-an-alert-using-severity-level.md)  
  
-   [<span data-ttu-id="edf71-120">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="edf71-120">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql)  
  
 <span data-ttu-id="edf71-121">**Para definir la respuesta a una alerta**</span><span class="sxs-lookup"><span data-stu-id="edf71-121">**To define the response to an alert**</span></span>  
  
-   [<span data-ttu-id="edf71-122">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="edf71-122">SQL Server Management Studio</span></span>](../sql-server-management-studio-ssms.md)  
  
-   [<span data-ttu-id="edf71-123">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="edf71-123">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql)  
  
 <span data-ttu-id="edf71-124">**Para crear el mensaje de error de un evento definido por el usuario**</span><span class="sxs-lookup"><span data-stu-id="edf71-124">**To create a user-defined event error message**</span></span>  
  
-   [<span data-ttu-id="edf71-125">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="edf71-125">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-addmessage-transact-sql)  
  
 <span data-ttu-id="edf71-126">**Para modificar el mensaje de error de un evento definido por el usuario**</span><span class="sxs-lookup"><span data-stu-id="edf71-126">**To modify a user-defined event error message**</span></span>  
  
-   [<span data-ttu-id="edf71-127">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="edf71-127">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-altermessage-transact-sql)  
  
 <span data-ttu-id="edf71-128">**Para eliminar el mensaje de error de un evento definido por el usuario**</span><span class="sxs-lookup"><span data-stu-id="edf71-128">**To delete a user-defined event error message**</span></span>  
  
-   [<span data-ttu-id="edf71-129">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="edf71-129">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-dropmessage-transact-sql)  
  
 <span data-ttu-id="edf71-130">**Para deshabilitar o volver a activar una alerta**</span><span class="sxs-lookup"><span data-stu-id="edf71-130">**To disable or reactivate an alert**</span></span>  
  
-   [<span data-ttu-id="edf71-131">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="edf71-131">SQL Server Management Studio</span></span>](disable-or-reactivate-an-alert.md)  
  
-   [<span data-ttu-id="edf71-132">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="edf71-132">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="edf71-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="edf71-133">See Also</span></span>  
 [<span data-ttu-id="edf71-134">sp_update_alert &#40;&#41;de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="edf71-134">sp_update_alert &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql)  
  
  
