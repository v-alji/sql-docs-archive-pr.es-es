---
title: Propiedades de alerta-nueva alerta (página general) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.alert.general.f1
ms.assetid: f5c11610-62e3-44df-9800-a5dc35be4a09
author: stevestein
ms.author: sstein
ms.openlocfilehash: 471b0062ecc805e83020495e422f8914baec5f71
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748496"
---
# <a name="alert-properties-new-alert-general-page"></a><span data-ttu-id="cb336-102">Propiedades de alerta-nueva alerta (página general)</span><span class="sxs-lookup"><span data-stu-id="cb336-102">Alert Properties-New Alert (General Page)</span></span>
  <span data-ttu-id="cb336-103">Utilice esta página para ver y modificar las propiedades generales de las [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alertas del agente.</span><span class="sxs-lookup"><span data-stu-id="cb336-103">Use this page to view and modify the general properties of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts.</span></span>  
  
## <a name="options"></a><span data-ttu-id="cb336-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="cb336-104">Options</span></span>  
 <span data-ttu-id="cb336-105">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="cb336-105">**Name**</span></span>  
 <span data-ttu-id="cb336-106">Cambie el nombre de la alerta.</span><span class="sxs-lookup"><span data-stu-id="cb336-106">Change the name of the alert.</span></span>  
  
 <span data-ttu-id="cb336-107">**Habilitar**</span><span class="sxs-lookup"><span data-stu-id="cb336-107">**Enable**</span></span>  
 <span data-ttu-id="cb336-108">Habilita la alerta.</span><span class="sxs-lookup"><span data-stu-id="cb336-108">Enable the alert.</span></span> <span data-ttu-id="cb336-109">Si la alerta no está habilitada, no se producirán acciones especificadas en la alerta.</span><span class="sxs-lookup"><span data-stu-id="cb336-109">When the alert is not enabled, the actions specified in the alert do not occur.</span></span>  
  
 <span data-ttu-id="cb336-110">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="cb336-110">**Type**</span></span>  
 <span data-ttu-id="cb336-111">Seleccione el tipo de alerta:</span><span class="sxs-lookup"><span data-stu-id="cb336-111">Select the type of alert:</span></span>  
  
-   <span data-ttu-id="cb336-112">**Alerta de evento de SQL Server** responde a los mensajes del registro de eventos de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="cb336-112">**SQL Server event alert** responds to messages in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows event log.</span></span>  
  
-   <span data-ttu-id="cb336-113">**Alerta de condición de rendimiento de SQL Server** responde a una condición específica del contador de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="cb336-113">**SQL Server performance condition alert** responds to a specific condition in a performance counter.</span></span>  
  
-   <span data-ttu-id="cb336-114">**Alerta de evento WMI** responde a un evento Instrumental de administración de Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="cb336-114">**WMI event alert** responds to a Windows Management Instrumentation (WMI) event.</span></span>  
  
## <a name="sql-server-event-alert-options"></a><span data-ttu-id="cb336-115">Opciones de Alerta de evento de SQL Server</span><span class="sxs-lookup"><span data-stu-id="cb336-115">SQL Server Event Alert Options</span></span>  
 <span data-ttu-id="cb336-116">**Nombre de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="cb336-116">**Database name**</span></span>  
 <span data-ttu-id="cb336-117">Especifica una base de datos para el evento o **todas las bases de datos** para responder a un mensaje independientemente de la base de datos en la que se produzca el evento.</span><span class="sxs-lookup"><span data-stu-id="cb336-117">Specify a database for the event, or **all databases** to respond to a message regardless of the database where the event occurs.</span></span>  
  
 <span data-ttu-id="cb336-118">**Número de error**</span><span class="sxs-lookup"><span data-stu-id="cb336-118">**Error number**</span></span>  
 <span data-ttu-id="cb336-119">Especifica que este evento responde a un error e indica el número de error.</span><span class="sxs-lookup"><span data-stu-id="cb336-119">Specify that this event responds to an error, and specify the error number.</span></span>  
  
 <span data-ttu-id="cb336-120">**Gravedad**</span><span class="sxs-lookup"><span data-stu-id="cb336-120">**Severity**</span></span>  
 <span data-ttu-id="cb336-121">Especifica que este evento responde a mensajes con un nivel de gravedad específico e indica dicho nivel.</span><span class="sxs-lookup"><span data-stu-id="cb336-121">Specify that this event responds to any message with a specific severity level, and specify the severity level.</span></span>  
  
 <span data-ttu-id="cb336-122">**Mostrar alerta cuando el mensaje contenga**</span><span class="sxs-lookup"><span data-stu-id="cb336-122">**Raise alert when message contains**</span></span>  
 <span data-ttu-id="cb336-123">Filtra los eventos mediante una cadena específica.</span><span class="sxs-lookup"><span data-stu-id="cb336-123">Filter events by a specific string.</span></span> <span data-ttu-id="cb336-124">Cuando esta opción está seleccionada, la alerta solo responde a los eventos que contengan una cadena específica.</span><span class="sxs-lookup"><span data-stu-id="cb336-124">When this option is selected, the alert only responds to events that contain a specific string.</span></span>  
  
 <span data-ttu-id="cb336-125">**Texto del mensaje**</span><span class="sxs-lookup"><span data-stu-id="cb336-125">**Message text**</span></span>  
 <span data-ttu-id="cb336-126">Especifica la cadena que se va a utilizar para filtrar eventos.</span><span class="sxs-lookup"><span data-stu-id="cb336-126">Specify the string to use to filter events.</span></span>  
  
## <a name="sql-server-performance-condition-alerts"></a><span data-ttu-id="cb336-127">Alertas de condición de rendimiento de SQL Server</span><span class="sxs-lookup"><span data-stu-id="cb336-127">SQL Server Performance Condition Alerts</span></span>  
 <span data-ttu-id="cb336-128">**Object**</span><span class="sxs-lookup"><span data-stu-id="cb336-128">**Object**</span></span>  
 <span data-ttu-id="cb336-129">Especifica el objeto de rendimiento que se supervisará.</span><span class="sxs-lookup"><span data-stu-id="cb336-129">Specify the performance object to monitor.</span></span>  
  
 <span data-ttu-id="cb336-130">**Contador**</span><span class="sxs-lookup"><span data-stu-id="cb336-130">**Counter**</span></span>  
 <span data-ttu-id="cb336-131">Especifica el contador del objeto de rendimiento que se supervisará.</span><span class="sxs-lookup"><span data-stu-id="cb336-131">Specify the counter within the performance object to monitor.</span></span>  
  
 <span data-ttu-id="cb336-132">**Instancia**</span><span class="sxs-lookup"><span data-stu-id="cb336-132">**Instance**</span></span>  
 <span data-ttu-id="cb336-133">Especifica la instancia del contador que se supervisará.</span><span class="sxs-lookup"><span data-stu-id="cb336-133">Specify the instance of the counter to monitor.</span></span>  
  
 <span data-ttu-id="cb336-134">**Alertar si contador**</span><span class="sxs-lookup"><span data-stu-id="cb336-134">**Alert if counter**</span></span>  
 <span data-ttu-id="cb336-135">Especifica el comportamiento del contador al que la alerta responde.</span><span class="sxs-lookup"><span data-stu-id="cb336-135">Specify the behavior of the counter that the alert responds to.</span></span> <span data-ttu-id="cb336-136">Por ejemplo, si desea que la alerta responda a una condición en la que el valor del contador **Espacio disponible en tempdb (KB)** esté por debajo de un determinado valor, o bien que la alerta responda a una condición en la que las **Compilaciones SQL/seg.** estén por encima de un determinado valor.</span><span class="sxs-lookup"><span data-stu-id="cb336-136">For example, you may want the alert to respond to a condition where the value of the **Free space in tempdb (KB)** counter falls below a certain value, or you may want the alert to respond to a condition where the **SQL Compilations/sec** rises above a certain value.</span></span>  
  
 <span data-ttu-id="cb336-137">**Valor**</span><span class="sxs-lookup"><span data-stu-id="cb336-137">**Value**</span></span>  
 <span data-ttu-id="cb336-138">Especifica un valor para el contador.</span><span class="sxs-lookup"><span data-stu-id="cb336-138">Specify a value for the counter.</span></span>  
  
## <a name="wmi-event-alert-options"></a><span data-ttu-id="cb336-139">Opciones de Alerta de evento WMI</span><span class="sxs-lookup"><span data-stu-id="cb336-139">WMI Event Alert Options</span></span>  
 <span data-ttu-id="cb336-140">**Espacio de nombres**</span><span class="sxs-lookup"><span data-stu-id="cb336-140">**Namespace**</span></span>  
 <span data-ttu-id="cb336-141">Especifica el espacio de nombres que se utilizará para la instrucción WQL (Lenguaje de consulta WMI).</span><span class="sxs-lookup"><span data-stu-id="cb336-141">Specify the namespace to use for the WMI Query Language (WQL) statement.</span></span> <span data-ttu-id="cb336-142">Solo se admite el espacio de nombres del equipo que ejecuta el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cb336-142">Only namespaces on the computer that runs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent are supported.</span></span>  
  
 <span data-ttu-id="cb336-143">**Consultar**</span><span class="sxs-lookup"><span data-stu-id="cb336-143">**Query**</span></span>  
 <span data-ttu-id="cb336-144">Especifica la instrucción WQL que identifica el evento al que responde la alerta.</span><span class="sxs-lookup"><span data-stu-id="cb336-144">Specify the WQL statement that identifies the event that the alert responds to.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb336-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cb336-145">See Also</span></span>  
 <span data-ttu-id="cb336-146">[Alerts](alerts.md) </span><span class="sxs-lookup"><span data-stu-id="cb336-146">[Alerts](alerts.md) </span></span>  
 <span data-ttu-id="cb336-147">[Usar WQL con el proveedor WMI para eventos de servidor](../../relational-databases/wmi-provider-server-events/using-wql-with-the-wmi-provider-for-server-events.md) </span><span class="sxs-lookup"><span data-stu-id="cb336-147">[Using WQL with the WMI Provider for Server Events](../../relational-databases/wmi-provider-server-events/using-wql-with-the-wmi-provider-for-server-events.md) </span></span>  
 <span data-ttu-id="cb336-148">[Crear una alerta con un número de error](create-an-alert-using-an-error-number.md) </span><span class="sxs-lookup"><span data-stu-id="cb336-148">[Create an Alert Using an Error Number](create-an-alert-using-an-error-number.md) </span></span>  
 [<span data-ttu-id="cb336-149">Create an Alert Using Severity Level</span><span class="sxs-lookup"><span data-stu-id="cb336-149">Create an Alert Using Severity Level</span></span>](create-an-alert-using-severity-level.md)  
  
  
