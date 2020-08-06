---
title: Proveedor WMI para las clases y propiedades de eventos de servidor | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- event classes [WMI]
- WMI Provider for Server Events, events listed
- classes [WMI]
ms.assetid: e2916cd7-a3ed-41e6-97b4-2ee060754cbe
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 471e77cb7afa4e6aed441dcbbc8b3b70064f6737
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749201"
---
# <a name="wmi-provider-for-server-events-classes-and-properties"></a><span data-ttu-id="dc307-102">Proveedor WMI de clases y propiedades de eventos de servidor</span><span class="sxs-lookup"><span data-stu-id="dc307-102">WMI Provider for Server Events Classes and Properties</span></span>
  <span data-ttu-id="dc307-103">Los eventos de servidor siguientes componen el modelo de programación del proveedor WMI de eventos de servidor.</span><span class="sxs-lookup"><span data-stu-id="dc307-103">The following server events make up the programming model for the WMI Provider for Server Events.</span></span> <span data-ttu-id="dc307-104">Hay dos categorías principales de eventos que se pueden consultar emitiendo las consultas WQL contra el proveedor.</span><span class="sxs-lookup"><span data-stu-id="dc307-104">There are two main categories of events that can be queried by issuing WQL queries against the provider.</span></span> <span data-ttu-id="dc307-105">Son eventos del lenguaje de definición de datos (DDL) y eventos de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="dc307-105">These are data definition language (DDL) events and trace events.</span></span> <span data-ttu-id="dc307-106">También se puede consultar los eventos de Service Broker BROKER_QUEUE_DISABLED y QUEUE_ACTIVATION.</span><span class="sxs-lookup"><span data-stu-id="dc307-106">The QUEUE_ACTIVATION and BROKER_QUEUE_DISABLED service broker events can also be queried.</span></span> <span data-ttu-id="dc307-107">Tenga en cuenta la naturaleza inclusiva de los diagramas del árbol siguientes.</span><span class="sxs-lookup"><span data-stu-id="dc307-107">Note the inclusive nature of the following tree diagrams.</span></span> <span data-ttu-id="dc307-108">El evento DDL_ASSEMBLY_EVENTS, por ejemplo, incluye los eventos ALTER_ASSEMBLY, DROP_ASSEMBLY y CREATE_ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="dc307-108">The DDL_ASSEMBLY_EVENTS event, for example, includes any ALTER_ASSEMBLY, CREATE_ASSEMBLY, and DROP_ASSEMBLY event.</span></span> <span data-ttu-id="dc307-109">De igual forma, el evento TRC_FULL_TEXT incluye los eventos FT_CRAWL_ABORTED, FT_CRAWL_STOPPED y FT_CRAWL_STARTED.</span><span class="sxs-lookup"><span data-stu-id="dc307-109">Similarly, the TRC_FULL_TEXT event includes any FT_CRAWL_ABORTED, FT_CRAWL_STARTED, and FT_CRAWL_STOPPED event.</span></span> <span data-ttu-id="dc307-110">ALL_EVENTS cubre todos los eventos DDL, eventos de seguimiento, QUEUE_ACTIVATION y BROKER_QUEUE_DISABLED.</span><span class="sxs-lookup"><span data-stu-id="dc307-110">ALL_EVENTS covers all DDL events, trace events, QUEUE_ACTIVATION, and BROKER_QUEUE_DISABLED.</span></span>  
  
 <span data-ttu-id="dc307-111">Para saber qué propiedades se puede consultar desde un evento o grupo de eventos, consulte el esquema de eventos.</span><span class="sxs-lookup"><span data-stu-id="dc307-111">To learn which properties can be queried from an event or event group, refer to the event schema.</span></span> <span data-ttu-id="dc307-112">De forma predeterminada, el esquema de eventos se instala en el directorio siguiente: [!INCLUDE[ssInstallPath](../../includes/ssinstallpath-md.md)]Tools\Binn\schemas\sqlserver\2006\11\events\events.xsd.</span><span class="sxs-lookup"><span data-stu-id="dc307-112">By default, the event schema is installed in the following directory: [!INCLUDE[ssInstallPath](../../includes/ssinstallpath-md.md)]Tools\Binn\schemas\sqlserver\2006\11\events\events.xsd.</span></span>  
  
 <span data-ttu-id="dc307-113">Como alternativa, puede hacer referencia al esquema de eventos publicado en [https://schemas.microsoft.com/sqlserver](https://go.microsoft.com/fwlink/?linkid=43100) .</span><span class="sxs-lookup"><span data-stu-id="dc307-113">Alternatively, you can refer to the event schema published at [https://schemas.microsoft.com/sqlserver](https://go.microsoft.com/fwlink/?linkid=43100).</span></span>  
  
 <span data-ttu-id="dc307-114">Por ejemplo, haciendo referencia al evento ALTER_DATABASE, sabrá que su evento primario es DDL_SERVER_LEVEL_EVENTS y que sus propiedades son `TSQLCommand` y `DatabaseName`.</span><span class="sxs-lookup"><span data-stu-id="dc307-114">For example, by referring to the ALTER_DATABASE event, you will learn that its parent event is DDL_SERVER_LEVEL_EVENTS and its properties are `TSQLCommand` and `DatabaseName`.</span></span> <span data-ttu-id="dc307-115">El evento también hereda las propiedades `SQLInstance`, `PostTime`, `ComputerName`, `SPID` y `LoginName`.</span><span class="sxs-lookup"><span data-stu-id="dc307-115">The event also inherits the properties `SQLInstance`, `PostTime`, `ComputerName`, `SPID`, and `LoginName`.</span></span> <span data-ttu-id="dc307-116">El evento no tiene ningún evento secundario.</span><span class="sxs-lookup"><span data-stu-id="dc307-116">The event has no children events.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dc307-117">Los procedimientos almacenados del sistema que realizan operaciones similares a DDL también pueden activar notificaciones de eventos.</span><span class="sxs-lookup"><span data-stu-id="dc307-117">System stored procedures that perform DDL-like operations can also fire event notifications.</span></span> <span data-ttu-id="dc307-118">Pruebe las notificaciones de eventos para determinar su respuesta a los procedimientos almacenados del sistema que se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="dc307-118">Test your event notifications to determine their responses to system stored procedures that are run.</span></span> <span data-ttu-id="dc307-119">Por ejemplo, la instrucción CREATE TYPE y **sp_addtype** procedimiento almacenado activarán una notificación de eventos que se crea en un evento de CREATE_TYPE.</span><span class="sxs-lookup"><span data-stu-id="dc307-119">For example, the CREATE TYPE statement and **sp_addtype** stored procedure will both fire an event notification that is created on a CREATE_TYPE event.</span></span> <span data-ttu-id="dc307-120">Para obtener más información, vea[eventos DDL](../../relational-databases/triggers/ddl-events.md).</span><span class="sxs-lookup"><span data-stu-id="dc307-120">For more information, see[DDL Events](../../relational-databases/triggers/ddl-events.md).</span></span>  
  
 <span data-ttu-id="dc307-121">**Eventos y grupos de eventos del Lenguaje de definición de datos**</span><span class="sxs-lookup"><span data-stu-id="dc307-121">**Data Definition Language Events and Event Groups**</span></span>  
  
 <span data-ttu-id="dc307-122">![Árbol de eventos del proveedor WMI de eventos de servidor](../../../2014/database-engine/dev-guide/media/sql-wmi-ddl-events-ktm.gif "Árbol de eventos del proveedor WMI de eventos de servidor")</span><span class="sxs-lookup"><span data-stu-id="dc307-122">![WMI Provider for Server Events Event Tree](../../../2014/database-engine/dev-guide/media/sql-wmi-ddl-events-ktm.gif "WMI Provider for Server Events Event Tree")</span></span>  
  
 <span data-ttu-id="dc307-123">**Eventos y grupos de eventos de seguimiento**</span><span class="sxs-lookup"><span data-stu-id="dc307-123">**Trace Events and Event Groups**</span></span>  
  
 <span data-ttu-id="dc307-124">![Eventos y grupos de eventos de seguimiento](../../../2014/database-engine/dev-guide/media/sql-wmi-trc-all-events.gif "Eventos y grupos de eventos de seguimiento")</span><span class="sxs-lookup"><span data-stu-id="dc307-124">![Trace events and event groups](../../../2014/database-engine/dev-guide/media/sql-wmi-trc-all-events.gif "Trace events and event groups")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc307-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dc307-125">See Also</span></span>  
 <span data-ttu-id="dc307-126">[Conceptos del proveedor WMI para eventos de servidor](../../relational-databases/wmi-provider-server-events/wmi-provider-for-server-events-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="dc307-126">[WMI Provider for Server Events Concepts](../../relational-databases/wmi-provider-server-events/wmi-provider-for-server-events-concepts.md) </span></span>  
 [<span data-ttu-id="dc307-127">Usar WQL con el proveedor WMI para eventos de servidor</span><span class="sxs-lookup"><span data-stu-id="dc307-127">Using WQL with the WMI Provider for Server Events</span></span>](../../relational-databases/wmi-provider-server-events/using-wql-with-the-wmi-provider-for-server-events.md)  
  
  
