---
title: Modificar una sesión de eventos extendidos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
ms.assetid: 114ec05b-7eca-4c87-b276-25e37b84be39
author: rothja
ms.author: jroth
ms.openlocfilehash: 14be41e48262bc7ebc8aeeaf55185f5e35d0c72e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662039"
---
# <a name="alter-an-extended-events-session"></a><span data-ttu-id="27d9b-102">Modificar una sesión de eventos extendidos</span><span class="sxs-lookup"><span data-stu-id="27d9b-102">Alter an Extended Events Session</span></span>
  <span data-ttu-id="27d9b-103">Después de crear una sesión de eventos extendidos, puede modificarla según sus necesidades con el **Asistente para eventos extendidos de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="27d9b-103">After you create an Extended Events session, you can alter it according to your needs using the **SQL Server Extended Events Wizard**.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="27d9b-104">Introducción</span><span class="sxs-lookup"><span data-stu-id="27d9b-104">Before you Begin</span></span>  
 <span data-ttu-id="27d9b-105">No puede modificar un destino para las sesiones activas e inactivas, y no puede cambiar las configuraciones de propiedades avanzadas de una sesión activa.</span><span class="sxs-lookup"><span data-stu-id="27d9b-105">You cannot alter a target for active and inactive sessions, and you cannot change the advanced properties configurations for an active session.</span></span>  
  
 <span data-ttu-id="27d9b-106">Puede realizar las siguientes modificaciones en las sesiones de eventos activas e inactivas:</span><span class="sxs-lookup"><span data-stu-id="27d9b-106">You can make the following alterations to both active and inactive event sessions:</span></span>  
  
-   <span data-ttu-id="27d9b-107">Agregar o quitar eventos de la sesión y modificar las configuraciones de eventos como campos, filtros y acciones de eventos.</span><span class="sxs-lookup"><span data-stu-id="27d9b-107">Add or remove events from the session, and alter the event configurations such as event fields, filters and actions.</span></span>  
  
-   <span data-ttu-id="27d9b-108">Agregar o quitar un destino de la sesión de eventos.</span><span class="sxs-lookup"><span data-stu-id="27d9b-108">Add or remove a target from the event session.</span></span>  
  
-   <span data-ttu-id="27d9b-109">Habilitar la opción **Iniciar la sesión de eventos al iniciar el servidor** .</span><span class="sxs-lookup"><span data-stu-id="27d9b-109">Enable the **Start the event session on server startup** option.</span></span>  
  
 <span data-ttu-id="27d9b-110">Puede realizar las siguientes modificaciones adicionales en una sesión de eventos inactiva:</span><span class="sxs-lookup"><span data-stu-id="27d9b-110">You can make the following additional alterations to an inactive event session:</span></span>  
  
-   <span data-ttu-id="27d9b-111">Habilitar la opción **Realizar el seguimiento de la relación entre eventos** .</span><span class="sxs-lookup"><span data-stu-id="27d9b-111">Enable the **Track the relationship between events** option.</span></span>  
  
-   <span data-ttu-id="27d9b-112">Cambiar la configuración de las propiedades avanzadas.</span><span class="sxs-lookup"><span data-stu-id="27d9b-112">Change the advanced properties configuration.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="27d9b-113">El **Asistente para eventos extendidos de SQL Server** no admite la modificación de la sesión de eventos.</span><span class="sxs-lookup"><span data-stu-id="27d9b-113">The **SQL Server Extended Events Wizard** does not support event session modification.</span></span>  
  
## <a name="how-to-alter-an-extended-events-session-using-the-sql-server-extended-events-wizard"></a><span data-ttu-id="27d9b-114">Cómo modificar una sesión de eventos extendidos con el Asistente para eventos extendidos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="27d9b-114">How to alter an Extended Events session using the SQL Server Extended Events Wizard</span></span>  
  
-   <span data-ttu-id="27d9b-115">En el Explorador de objetos, expanda **Administración**, expanda **Eventos extendidos**y, a continuación, expanda **Sesiones**.</span><span class="sxs-lookup"><span data-stu-id="27d9b-115">In Object Explorer, expand **Management**, expand **Extended Events**, and then expand **Sessions**.</span></span>  
  
-   <span data-ttu-id="27d9b-116">Haga clic con el botón derecho en la sesión que quiera modificar y luego haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="27d9b-116">Right-click the session you want to alter, and then click **Properties**.</span></span>  
  
-   <span data-ttu-id="27d9b-117">En el cuadro de diálogo **Propiedades** , realice los cambios adecuados y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="27d9b-117">In the **Properties** dialog box, make the appropriate changes, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27d9b-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="27d9b-118">See Also</span></span>  
 <span data-ttu-id="27d9b-119">[ALTER EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-event-session-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="27d9b-119">[ALTER EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-event-session-transact-sql) </span></span>  
 [<span data-ttu-id="27d9b-120">Crear una sesión de eventos extendidos mediante el Editor de consultas</span><span class="sxs-lookup"><span data-stu-id="27d9b-120">Create an Extended Events Session Using Query Editor</span></span>](../../database-engine/create-an-extended-events-session-using-query-editor.md)  
  
  
