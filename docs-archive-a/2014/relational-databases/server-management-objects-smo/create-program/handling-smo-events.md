---
title: Controlar eventos SMO | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- events [SMO]
- SQL Server Management Objects, events
- SMO [SQL Server], events
- events [SMO], about events
ms.assetid: b4f120dd-ba78-46ff-99c5-e47effac8544
author: stevestein
ms.author: sstein
ms.openlocfilehash: f7ea438142ac283c5ad19670fa827b5e248e80f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676986"
---
# <a name="handling-smo-events"></a><span data-ttu-id="6376e-102">Controlar eventos SMO</span><span class="sxs-lookup"><span data-stu-id="6376e-102">Handling SMO Events</span></span>
  <span data-ttu-id="6376e-103">Hay tipos de evento de servidor a los que se puede suscribir utilizando un controlador de eventos y el objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.</span><span class="sxs-lookup"><span data-stu-id="6376e-103">There are server event types that can be subscribed to by using an event handler and the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span>  
  
 <span data-ttu-id="6376e-104">Muchas de las clases de instancia en los objetos de administración de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (SMO) pueden activar los eventos cuando se producen ciertas acciones en el servidor.</span><span class="sxs-lookup"><span data-stu-id="6376e-104">Many of the instance classes in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO) can trigger events when certain actions on the server occur.</span></span>  
  
 <span data-ttu-id="6376e-105">Estos eventos se pueden administrar mediante programación preparando un controlador de eventos y suscribiéndose a los eventos asociados.</span><span class="sxs-lookup"><span data-stu-id="6376e-105">These events can be handled programmatically by setting up an event handler and subscribing to the associated events.</span></span> <span data-ttu-id="6376e-106">Este tipo de control de eventos es transitorio porque se quitan todas las suscripciones cuando se sale del programa cliente de SMO.</span><span class="sxs-lookup"><span data-stu-id="6376e-106">This type of event handling is transient because all the subscriptions are removed when the SMO client program exits.</span></span>  
  
## <a name="connectioncontext-event-handling"></a><span data-ttu-id="6376e-107">Controlar eventos ConnectionContext</span><span class="sxs-lookup"><span data-stu-id="6376e-107">ConnectionContext Event Handling</span></span>  
 <span data-ttu-id="6376e-108">Los objetos <xref:Microsoft.SqlServer.Management.Common.ServerConnection> admiten varios tipos de evento.</span><span class="sxs-lookup"><span data-stu-id="6376e-108">The <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object supports several event types.</span></span> <span data-ttu-id="6376e-109">La propiedad del evento debe estar establecida en una instancia de un controlador de eventos adecuado y el objeto de controlador de eventos se debe definir como una función protegida que administra el evento.</span><span class="sxs-lookup"><span data-stu-id="6376e-109">The event property must be set to an instance of an appropriate event handler, and the event handler object must be defined as a protected function that handles the event.</span></span>  
  
## <a name="event-subscription"></a><span data-ttu-id="6376e-110">Suscripción a eventos</span><span class="sxs-lookup"><span data-stu-id="6376e-110">Event Subscription</span></span>  
 <span data-ttu-id="6376e-111">Administra los eventos escribiendo una clase de controlador de eventos, creando una instancia de él, asignando el controlador de eventos al objeto primario y suscribiéndose a continuación al evento.</span><span class="sxs-lookup"><span data-stu-id="6376e-111">You handle events by writing an event handler class, creating an instance of it, assigning the event handler to the parent object, and then subscribing to the event.</span></span>  
  
 <span data-ttu-id="6376e-112">Una clase de controlador de eventos se debe escribir para administrar los eventos.</span><span class="sxs-lookup"><span data-stu-id="6376e-112">An event handler class must be written to handle events.</span></span> <span data-ttu-id="6376e-113">La clase de controlador de eventos puede contener más de una función de controlador de eventos y se debe instalar para los eventos que se van a administrar.</span><span class="sxs-lookup"><span data-stu-id="6376e-113">The event handler class can contain more than one event handler function, and must be installed for the events to be handled.</span></span> <span data-ttu-id="6376e-114">Las funciones de controlador de eventos reciben información sobre el evento del parámetro *ServerEventNotificatificationArgs* que se puede usar para notificar información sobre el evento.</span><span class="sxs-lookup"><span data-stu-id="6376e-114">The event handler functions receive information about the event from the *ServerEventNotificatificationArgs* parameter that can be used to report information about the event.</span></span>  
  
 <span data-ttu-id="6376e-115">Los tipos de eventos de base de datos y de servidor que se pueden controlar se enumeran en la <xref:Microsoft.SqlServer.Management.Smo.DatabaseEventSet> clase y en la <xref:Microsoft.SqlServer.Management.Smo.ServerEventSet> clase.</span><span class="sxs-lookup"><span data-stu-id="6376e-115">The types of database and server events that can be handled are listed in the <xref:Microsoft.SqlServer.Management.Smo.DatabaseEventSet> class and the <xref:Microsoft.SqlServer.Management.Smo.ServerEventSet>class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6376e-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6376e-116">Example</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="registering-event-handlers-and-subscribing-to-event-handling-in-visual-basic"></a><span data-ttu-id="6376e-117">Registrar los controladores de eventos y suscribirse al control de eventos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6376e-117">Registering Event Handlers and Subscribing to Event Handling in Visual Basic</span></span>  
 <span data-ttu-id="6376e-118">En este ejemplo de código se muestra cómo configurar el controlador de eventos y cómo suscribirse a los eventos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="6376e-118">This code example shows how to set up the event handler, and how to subscribe to the database events.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBEvents1](SMO How to#SMO_VBEvents1)]  -->  
  
## <a name="registering-event-handlers-and-subscribing-to-event-handling-in-visual-c"></a><span data-ttu-id="6376e-119">Registrar los controladores de eventos y suscribirse al control de eventos en Visual C#</span><span class="sxs-lookup"><span data-stu-id="6376e-119">Registering Event Handlers and Subscribing to Event Handling in Visual C#</span></span>  
 <span data-ttu-id="6376e-120">En este ejemplo de código se muestra cómo configurar el controlador de eventos y cómo suscribirse a los eventos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="6376e-120">This code example shows how to set up the event handler, and how to subscribe to the database events.</span></span>  
  
```  
//Create an event handler subroutine that runs when a table is created.   
private void MyCreateEventHandler(object sender, ServerEventArgs e)   
{   
Console.WriteLine("A table has just been added to the AdventureWorks2012 database.");   
}   
//Create an event handler subroutine that runs when a table is deleted.   
private void MyDropEventHandler(object sender, ServerEventArgs e)   
{   
Console.WriteLine("A table has just been dropped from the AdventureWorks2012 database.");   
}   
public void Main()   
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Reference the AdventureWorks2012 database.   
Database db;   
db = srv.Databases("AdventureWorks2012");   
//Create a database event set that contains the CreateTable event only.   
DatabaseEventSet databaseCreateEventSet = new DatabaseEventSet();   
databaseCreateEventSet.CreateTable = true;   
//Create a server event handler and set it to the first event handler subroutine.   
ServerEventHandler serverCreateEventHandler;   
serverCreateEventHandler = new ServerEventHandler(MyCreateEventHandler);   
//Subscribe to the first server event handler when a CreateTable event occurs.   
db.Events.SubscribeToEvents(databaseCreateEventSet, serverCreateEventHandler);   
    //Create a database event set that contains the DropTable event only.   
DatabaseEventSet databaseDropEventSet = new DatabaseEventSet();   
databaseDropEventSet.DropTable = true;   
//Create a server event handler and set it to the second event handler subroutine.   
ServerEventHandler serverDropEventHandler;   
serverDropEventHandler = new ServerEventHandler(MyDropEventHandler);   
//Subscribe to the second server event handler when a DropTable event occurs.   
db.Events.SubscribeToEvents(databaseDropEventSet, serverDropEventHandler);   
//Start event handling.   
db.Events.StartEvents();   
//Create a table on the database.   
Table tb;   
tb = new Table(db, "Test_Table");   
Column mycol1;   
mycol1 = new Column(tb, "Name", DataType.NChar(50));   
mycol1.Collation = "Latin1_General_CI_AS";   
mycol1.Nullable = true;   
tb.Columns.Add(mycol1);   
tb.Create();   
//Remove the table.   
tb.Drop();   
//Wait until the events have occured.   
int x;   
int y;   
for (x = 1; x <= 1000000000; x++) {   
    y = x * 2;   
}   
//Stop event handling.   
db.Events.StopEvents();   
}  
```  
  
  
