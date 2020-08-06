---
title: 'Ejemplo: crear una alerta de Agente SQL Server mediante el proveedor WMI para eventos de servidor | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- SQL Server Agent [WMI]
- WMI Provider for Server Events, samples
- sample applications [WMI]
ms.assetid: d44811c7-cd46-4017-b284-c863ca088e8f
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: f23a3a8738435dc6a27a230f4521300a3ee2470f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746799"
---
# <a name="sample-creating-a-sql-server-agent-alert-by-using-the-wmi-provider-for-server-events"></a><span data-ttu-id="b9939-102">Sample: Creación de una alerta del Agente SQL Server con el proveedor WMI para eventos de servidor</span><span class="sxs-lookup"><span data-stu-id="b9939-102">Sample: Creating a SQL Server Agent Alert by Using the WMI Provider for Server Events</span></span>
  <span data-ttu-id="b9939-103">Una manera común de utilizar el Proveedor de eventos WMI es crear alertas del Agente SQL Server que respondan a eventos concretos.</span><span class="sxs-lookup"><span data-stu-id="b9939-103">One common way to use the WMI Event Provider is to create SQL Server Agent alerts that respond to specific events.</span></span> <span data-ttu-id="b9939-104">En el ejemplo siguiente se presenta una alerta simple que guarda los eventos de grafo de interbloqueo de XML en una tabla para el análisis posterior.</span><span class="sxs-lookup"><span data-stu-id="b9939-104">The following sample presents a simple alert that saves XML deadlock graph events in a table for later analysis.</span></span> <span data-ttu-id="b9939-105">El Agente SQL Server envía una solicitud WQL, recibe los eventos WMI y ejecuta un trabajo en respuesta al evento.</span><span class="sxs-lookup"><span data-stu-id="b9939-105">SQL Server Agent submits a WQL request, receives WMI events, and runs a job in response to the event.</span></span> <span data-ttu-id="b9939-106">Observe que, aunque varios objetos Service Broker están implicados para procesar el mensaje de notificación, el Proveedor de eventos WMI administra los detalles de creación y administración de estos objetos.</span><span class="sxs-lookup"><span data-stu-id="b9939-106">Notice that, although several Service Broker objects are involved in processing the notification message, the WMI Event Provider handles the details of creating and managing these objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9939-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b9939-107">Example</span></span>  
 <span data-ttu-id="b9939-108">Primero, se crea una tabla en la base de datos `AdventureWorks` para contener el evento de grafo de interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="b9939-108">First, a table is created in the `AdventureWorks` database to hold the deadlock graph event.</span></span> <span data-ttu-id="b9939-109">La tabla contiene dos columnas: la columna `AlertTime` contiene la hora a la que se ejecuta la alerta y la columna `DeadlockGraph` contiene el documento XML que contiene el grafo de interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="b9939-109">The table contains two columns: The `AlertTime` column holds the time that the alert runs, and the `DeadlockGraph` column holds the XML document that contains the deadlock graph.</span></span>  
  
 <span data-ttu-id="b9939-110">A continuación, se crea la alerta.</span><span class="sxs-lookup"><span data-stu-id="b9939-110">Then, the alert is created.</span></span> <span data-ttu-id="b9939-111">El script crea primero el trabajo que la alerta ejecutará, agrega un paso de trabajo al trabajo y dirige el trabajo a la instancia actual de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b9939-111">The script first creates the job that the alert will run, adds a job step to the job, and targets the job to the current instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b9939-112">A continuación, el script crea la alerta.</span><span class="sxs-lookup"><span data-stu-id="b9939-112">The script then creates the alert.</span></span>  
  
 <span data-ttu-id="b9939-113">El paso de trabajo recupera la propiedad **TextData** de la instancia de evento WMI e inserta ese valor en la columna **DeadlockGraph** de la tabla **DeadlockEvents** .</span><span class="sxs-lookup"><span data-stu-id="b9939-113">The job step retrieves the **TextData** property of the WMI event instance and inserts that value into the **DeadlockGraph** column of the **DeadlockEvents** table.</span></span> <span data-ttu-id="b9939-114">Observe que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] convierte implícitamente la cadena al formato XML.</span><span class="sxs-lookup"><span data-stu-id="b9939-114">Notice that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] implicitly converts the string into XML format.</span></span> <span data-ttu-id="b9939-115">Dado que el paso de trabajo utiliza el subsistema [!INCLUDE[tsql](../../includes/tsql-md.md)], el paso de trabajo no especifica un proxy.</span><span class="sxs-lookup"><span data-stu-id="b9939-115">Because the job step uses the [!INCLUDE[tsql](../../includes/tsql-md.md)] subsystem, the job step does not specify a proxy.</span></span>  
  
 <span data-ttu-id="b9939-116">La alerta ejecuta el trabajo cada vez que se registraría un evento de seguimiento de grafo de interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="b9939-116">The alert runs the job whenever a deadlock graph trace event would be logged.</span></span> <span data-ttu-id="b9939-117">Para una alerta WMI, el Agente SQL Server crea una consulta de notificación mediante el espacio de nombres y la instrucción WQL especificados.</span><span class="sxs-lookup"><span data-stu-id="b9939-117">For a WMI alert, SQL Server Agent creates a notification query using the namespace and WQL statement specified.</span></span> <span data-ttu-id="b9939-118">Para este alerta, el Agente SQL Server supervisa la instancia predeterminada en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="b9939-118">For this alert, SQL Server Agent monitors the default instance on the local computer.</span></span> <span data-ttu-id="b9939-119">La instrucción WQL solicita cualquier evento `DEADLOCK_GRAPH` en la instancia predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b9939-119">The WQL statement requests any `DEADLOCK_GRAPH` event in the default instance.</span></span> <span data-ttu-id="b9939-120">Para cambiar la instancia que supervisa la alerta, sustituya el nombre de instancia por `MSSQLSERVER` en el `@wmi_namespace` para la alerta.</span><span class="sxs-lookup"><span data-stu-id="b9939-120">To change the instance that the alert monitors, substitute the instance name for `MSSQLSERVER` in the `@wmi_namespace` for the alert.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b9939-121">Para Agente SQL Server recibir eventos de WMI, [!INCLUDE[ssSB](../../includes/sssb-md.md)] debe estar habilitado en **msdb** y [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b9939-121">For SQL Server Agent to receive WMI events, [!INCLUDE[ssSB](../../includes/sssb-md.md)] must be enabled in **msdb** and [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span>  
  
```  
USE AdventureWorks ;  
GO  
  
IF OBJECT_ID('DeadlockEvents', 'U') IS NOT NULL  
BEGIN  
    DROP TABLE DeadlockEvents ;  
END ;  
GO  
  
CREATE TABLE DeadlockEvents  
    (AlertTime DATETIME, DeadlockGraph XML) ;  
GO  
-- Add a job for the alert to run.  
  
EXEC  msdb.dbo.sp_add_job @job_name=N'Capture Deadlock Graph',   
    @enabled=1,   
    @description=N'Job for responding to DEADLOCK_GRAPH events' ;  
GO  
  
-- Add a jobstep that inserts the current time and the deadlock graph into  
-- the DeadlockEvents table.  
  
EXEC msdb.dbo.sp_add_jobstep  
    @job_name = N'Capture Deadlock Graph',  
    @step_name=N'Insert graph into LogEvents',  
    @step_id=1,   
    @on_success_action=1,   
    @on_fail_action=2,   
    @subsystem=N'TSQL',   
    @command= N'INSERT INTO DeadlockEvents  
                (AlertTime, DeadlockGraph)  
                VALUES (getdate(), N''$(ESCAPE_SQUOTE(WMI(TextData)))'')',  
    @database_name=N'AdventureWorks' ;  
GO  
  
-- Set the job server for the job to the current instance of SQL Server.  
  
EXEC msdb.dbo.sp_add_jobserver @job_name = N'Capture Deadlock Graph' ;  
GO  
  
-- Add an alert that responds to all DEADLOCK_GRAPH events for  
-- the default instance. To monitor deadlocks for a different instance,  
-- change MSSQLSERVER to the name of the instance.  
  
EXEC msdb.dbo.sp_add_alert @name=N'Respond to DEADLOCK_GRAPH',   
@wmi_namespace=N'\\.\root\Microsoft\SqlServer\ServerEvents\MSSQLSERVER',   
    @wmi_query=N'SELECT * FROM DEADLOCK_GRAPH',   
    @job_name='Capture Deadlock Graph' ;  
GO  
```  
  
## <a name="testing-the-sample"></a><span data-ttu-id="b9939-122">Probar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="b9939-122">Testing the Sample</span></span>  
 <span data-ttu-id="b9939-123">Para ver cómo se ejecuta el trabajo, provoque un interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="b9939-123">To see the job run, provoke a deadlock.</span></span> <span data-ttu-id="b9939-124">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , abra dos pestañas de **consulta SQL** y conecte ambas consultas a la misma instancia.</span><span class="sxs-lookup"><span data-stu-id="b9939-124">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open two **SQL Query** tabs and connect both queries to the same instance.</span></span> <span data-ttu-id="b9939-125">Ejecute el script siguiente en una de las pestañas de consulta.</span><span class="sxs-lookup"><span data-stu-id="b9939-125">Run the following script in one of the query tabs.</span></span> <span data-ttu-id="b9939-126">Este script genera un conjunto de resultados y finaliza.</span><span class="sxs-lookup"><span data-stu-id="b9939-126">This script produces one result set and finishes.</span></span>  
  
```  
USE AdventureWorks ;  
GO  
  
BEGIN TRANSACTION ;  
GO  
  
SELECT TOP(1) Name FROM Production.Product WITH (XLOCK) ;  
GO  
```  
  
 <span data-ttu-id="b9939-127">Ejecute el siguiente script en la segunda pestaña de consulta. Este script genera un conjunto de resultados y, a continuación, se bloquea, a la espera de adquirir un bloqueo en `Production.Product` .</span><span class="sxs-lookup"><span data-stu-id="b9939-127">Run the following script in the second query tab. This script produces one result set and then blocks, waiting to acquire a lock on `Production.Product`.</span></span>  
  
```  
USE AdventureWorks ;  
GO  
  
BEGIN TRANSACTION ;  
GO  
  
SELECT TOP(1) Name FROM Production.Location WITH (XLOCK) ;  
GO  
  
SELECT TOP(1) Name FROM Production.Product WITH (XLOCK) ;  
GO  
```  
  
 <span data-ttu-id="b9939-128">Ejecute el siguiente script en la primera pestaña de consulta. Este script se bloquea, a la espera de adquirir un bloqueo en `Production.Location` .</span><span class="sxs-lookup"><span data-stu-id="b9939-128">Run the following script in the first query tab. This script blocks, waiting to acquire a lock on `Production.Location`.</span></span> <span data-ttu-id="b9939-129">Después de un tiempo de espera corto, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] elegirá este script o el script del ejemplo como víctima del interbloqueo y finalizará la transacción.</span><span class="sxs-lookup"><span data-stu-id="b9939-129">After a short time-out, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will choose either this script or the script in the sample as the deadlock victim and end the transaction.</span></span>  
  
```  
SELECT TOP(1) Name FROM Production.Location WITH (XLOCK) ;  
GO  
```  
  
 <span data-ttu-id="b9939-130">Después de provocar el interbloqueo, espere unos momentos a que el Agente SQL Server active la alerta y ejecute el trabajo.</span><span class="sxs-lookup"><span data-stu-id="b9939-130">After provoking the deadlock, wait several moments for SQL Server Agent to activate the alert and run the job.</span></span> <span data-ttu-id="b9939-131">Examine el contenido de la tabla `DeadlockEvents` ejecutando el script siguiente:</span><span class="sxs-lookup"><span data-stu-id="b9939-131">Examine the contents of the `DeadlockEvents` table by running the following script:</span></span>  
  
```  
SELECT * FROM DeadlockEvents ;  
GO  
```  
  
 <span data-ttu-id="b9939-132">La columna `DeadlockGraph` debería contener un documento XML que muestra todas las propiedades del evento de grafo de interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="b9939-132">The `DeadlockGraph` column should contain an XML document that shows all the properties of the deadlock graph event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9939-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b9939-133">See Also</span></span>  
 [<span data-ttu-id="b9939-134">Conceptos del proveedor WMI para eventos de servidor</span><span class="sxs-lookup"><span data-stu-id="b9939-134">WMI Provider for Server Events Concepts</span></span>](wmi-provider-for-server-events-concepts.md)  
  
  
