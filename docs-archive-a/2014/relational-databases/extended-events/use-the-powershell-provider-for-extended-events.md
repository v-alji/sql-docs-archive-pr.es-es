---
title: Usar el proveedor de PowerShell para eventos extendidos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- PowerShell [SQL Server], xevent
- extended events [SQL Server], PowerShell
- PowerShell [SQL Server], extended events
ms.assetid: 0b10016f-a479-4444-a484-46cb4677cf64
author: rothja
ms.author: jroth
ms.openlocfilehash: a9efbd389545dcde8285a38b06f41580fb65de6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674115"
---
# <a name="use-the-powershell-provider-for-extended-events"></a><span data-ttu-id="22230-102">Usar el proveedor de PowerShell para eventos extendidos</span><span class="sxs-lookup"><span data-stu-id="22230-102">Use the PowerShell Provider for Extended Events</span></span>
  <span data-ttu-id="22230-103">Puede administrar los eventos extendidos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando el proveedor de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="22230-103">You can manage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Extended Events by using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell provider.</span></span> <span data-ttu-id="22230-104">La subcarpeta XEvent está disponible en la unidad SQLSERVER.</span><span class="sxs-lookup"><span data-stu-id="22230-104">The XEvent subfolder is available under the SQLSERVER drive.</span></span> <span data-ttu-id="22230-105">Para acceder a la carpeta, puede usar cualquiera de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="22230-105">You can access the folder by using either of the following methods:</span></span>  
  
-   <span data-ttu-id="22230-106">En el símbolo del sistema, escriba `sqlps` y luego presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="22230-106">At a command prompt, type `sqlps`, and then press ENTER.</span></span> <span data-ttu-id="22230-107">Escriba `cd xevent` y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="22230-107">Type `cd xevent`, and then press ENTER.</span></span> <span data-ttu-id="22230-108">Desde allí, puede usar el **CD** y los `dir` comandos (o los cmdlets **set-Location** y **Get-childitem** ) para desplazarse hasta el nombre del servidor y el nombre de la instancia.</span><span class="sxs-lookup"><span data-stu-id="22230-108">From there, you can use the **cd** and `dir` commands (or **Set-Location** and **Get-Childitem** cmdlets) to navigate to the server name and instance name.</span></span>  
  
-   <span data-ttu-id="22230-109">En el Explorador de objetos, expanda el nombre de la instancia, expanda **Administración**, haga clic con el botón derecho en **Eventos extendidos**y haga clic en **Iniciar PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="22230-109">In Object Explorer, expand the instance name, expand **Management**, right-click **Extended Events**, and then click **Start PowerShell**.</span></span> <span data-ttu-id="22230-110">De esta forma, se inicia PowerShell en la siguiente ruta de acceso:</span><span class="sxs-lookup"><span data-stu-id="22230-110">This starts PowerShell in the following path:</span></span>  
  
     <span data-ttu-id="22230-111">PS SQLServer: \ XEvent \\ *ServerName* \\ *nombreDeInstancia*></span><span class="sxs-lookup"><span data-stu-id="22230-111">PS SQLSERVER:\XEvent\\*ServerName*\\*InstanceName*></span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="22230-112">Puede iniciar PowerShell en cualquier nodo situado debajo de **Eventos extendidos**.</span><span class="sxs-lookup"><span data-stu-id="22230-112">You can start PowerShell from any node under **Extended Events**.</span></span> <span data-ttu-id="22230-113">Por ejemplo, puede hacer clic con el botón derecho en **Sesiones**y, después, hacer clic en **Iniciar PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="22230-113">For example, you can right-click **Sessions**, and then click **Start PowerShell**.</span></span> <span data-ttu-id="22230-114">De esta forma, se inicia PowerShell en un nivel más profundo de la carpeta Sessions.</span><span class="sxs-lookup"><span data-stu-id="22230-114">This starts PowerShell one level deeper, at the Sessions folder.</span></span>  
  
 <span data-ttu-id="22230-115">Puede examinar el árbol de carpetas XEvent para ver las sesiones de eventos extendidos, así como sus eventos, destinos y predicados asociados.</span><span class="sxs-lookup"><span data-stu-id="22230-115">You can browse the XEvent folder tree to view existing Extended Events sessions and their associated events, targets and predicates.</span></span> <span data-ttu-id="22230-116">Por ejemplo, desde la ruta de acceso PS SQLServer: \ XEvent \\ *ServerName* \\ *nombreDeInstancia*>, si escribe `cd sessions` , presiona entrar, escribe `dir` y presiona entrar, puede ver la lista de sesiones almacenadas en esa instancia.</span><span class="sxs-lookup"><span data-stu-id="22230-116">For example, from the PS SQLSERVER:\XEvent\\*ServerName*\\*InstanceName*> path, if you type `cd sessions`, press ENTER, type `dir`, and then press ENTER, you can see the list of sessions that are stored on that instance.</span></span> <span data-ttu-id="22230-117">Asimismo, puede ver si la sesión se está ejecutando (y si este es el caso, durante cuánto tiempo), así como si la sesión está configurada para iniciarse cuando se inicie la instancia.</span><span class="sxs-lookup"><span data-stu-id="22230-117">You can also view whether the session is running (and if this is the case, for how long), and whether the session is configured to start when the instance starts.</span></span>  
  
 <span data-ttu-id="22230-118">Para ver los eventos, sus predicados y los destinos asociados con una sesión, puede cambiar los directorios al nombre de la sesión y, a continuación, ver la carpeta de eventos o de destino.</span><span class="sxs-lookup"><span data-stu-id="22230-118">To view the events, their predictates, and the targets that are associated with a session, you can change directories to the session name, and then view either the events or targets folder.</span></span> <span data-ttu-id="22230-119">Por ejemplo, para ver los eventos y sus predicados asociados a la sesión de mantenimiento del sistema predeterminada, en la ruta de acceso de PS SQLServer: \ XEvent \\ *ServerName* \\ *nombreDeInstancia*\Sessions>, escriba `cd system_health\events,` Presione entrar, escriba `dir` y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="22230-119">For example, to view the events and their predicates that are associated with the default system health session, from the PS SQLSERVER:\XEvent\\*ServerName*\\*InstanceName*\Sessions> path, type `cd system_health\events,` press ENTER, type `dir`, and then press ENTER.</span></span>  
  
 <span data-ttu-id="22230-120">El proveedor de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell es una herramienta eficaz que puede usar para crear, modificar y administrar sesiones de eventos extendidos.</span><span class="sxs-lookup"><span data-stu-id="22230-120">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell provider is a powerful tool that you can use to create, alter, and manage Extended Events sessions.</span></span> <span data-ttu-id="22230-121">En la siguiente sección se proporcionan algunos ejemplos básicos del uso de los scripts de PowerShell con eventos extendidos.</span><span class="sxs-lookup"><span data-stu-id="22230-121">The following section provides some basic examples of using PowerShell scripts with Extended Events.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="22230-122">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="22230-122">Examples</span></span>  
 <span data-ttu-id="22230-123">En los siguientes ejemplos, observe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="22230-123">In the following examples, note the following:</span></span>  
  
-   <span data-ttu-id="22230-124">Los scripts se deben ejecutar desde el símbolo del sistema PS SQLSERVER: \\> (disponible escribiendo `sqlps` en un símbolo del sistema).</span><span class="sxs-lookup"><span data-stu-id="22230-124">The scripts must be run from the PS SQLSERVER:\\> prompt (available by typing `sqlps` at a command prompt).</span></span>  
  
-   <span data-ttu-id="22230-125">Los scripts usan la instancia predeterminada de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="22230-125">The scripts use the default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="22230-126">Los scripts se deben guardar con una extensión .ps1.</span><span class="sxs-lookup"><span data-stu-id="22230-126">The scripts must be saved with a .ps1 extension.</span></span>  
  
-   <span data-ttu-id="22230-127">La directiva de ejecución de PowerShell debe permitir que se ejecute el script.</span><span class="sxs-lookup"><span data-stu-id="22230-127">The PowerShell execution policy must allow the script to run.</span></span> <span data-ttu-id="22230-128">Para establecer la directiva de ejecución, use el cmdlet **Set-Executionpolicy** .</span><span class="sxs-lookup"><span data-stu-id="22230-128">To set the execution policy, use the **Set-Executionpolicy** cmdlet.</span></span> <span data-ttu-id="22230-129">(Para más información, escriba `get-help set-executionpolicy -detailed` y luego presione ENTRAR).</span><span class="sxs-lookup"><span data-stu-id="22230-129">(For more information, type `get-help set-executionpolicy -detailed`, and then press ENTER.)</span></span>  
  
 <span data-ttu-id="22230-130">En el siguiente script se crea una nueva sesión denominada 'TestSession'.</span><span class="sxs-lookup"><span data-stu-id="22230-130">The following script creates a new session that is named 'TestSession'.</span></span>  
  
```powershell
#Script for creating a session.  
cd XEvent  
$h = hostname  
cd $h  
  
#Use the default instance.  
$store = dir | where {$_.DisplayName -ieq 'default'}  
$session = New-Object Microsoft.SqlServer.Management.XEvent.Session -ArgumentList $store, "TestSession"  
$event = $session.AddEvent("sqlserver.file_written")  
$event.AddAction("package0.callstack")  
$session.Create()  
```  
  
 <span data-ttu-id="22230-131">En el siguiente script se agrega el destino de búfer de anillo a la sesión creada en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="22230-131">The following script adds the ring buffer target to the session that was created in the previous example.</span></span> <span data-ttu-id="22230-132">(En este ejemplo se muestra el uso del método `Alter`.</span><span class="sxs-lookup"><span data-stu-id="22230-132">(This example shows the use of the `Alter` method.</span></span> <span data-ttu-id="22230-133">Tenga en cuenta que puede agregar el destino cuando cree la sesión por primera vez).</span><span class="sxs-lookup"><span data-stu-id="22230-133">Be aware that you can add the target when you first create the session.)</span></span>  
  
```powershell
#Script to alter a session.  
cd XEvent  
$h = hostname  
cd $h  
cd DEFAULT\Sessions  
  
#Used to find the specified session.  
$session = dir | where {$_.Name -eq 'TestSession'}  
  
#Add the ring buffer target and call the Alter method.  
$session.AddTarget("package0.ring_buffer")  
$session.Alter()  
```  
  
 <span data-ttu-id="22230-134">En el siguiente script se crea una nueva sesión que usa una expresión de predicado.</span><span class="sxs-lookup"><span data-stu-id="22230-134">The following script creates a new session that uses a predicate expression.</span></span> <span data-ttu-id="22230-135">En este caso, la sesión recopila información para cuando se escriba el archivo c:\temp.log (mediante el evento sqlserver.file_written).</span><span class="sxs-lookup"><span data-stu-id="22230-135">In this case, the session collects information for when the c:\temp.log file is written to (through the sqlserver.file_written event).</span></span>  
  
```powershell
#Script for creating a session.  
cd XEvent  
$h = hostname  
cd $h  
  
#Use the default instance.  
$store = dir | where {$_.DisplayName -ieq 'default'}  
$session = New-Object Microsoft.SqlServer.Management.XEvent.Session -ArgumentList $store, "TestSession2"  
$event = $session.AddEvent("sqlserver.file_written")  
  
#Construct a predicate "equal_i_unicode_string(path, N'c:\temp.log')".  
$column = $store.SqlServerPackage.EventInfoSet["file_written"].DataEventColumnInfoSet["path"]  
$operand = new-object Microsoft.SqlServer.Management.XEvent.PredOperand -argumentlist $column  
$value = new-object Microsoft.SqlServer.Management.XEvent.PredValue -argumentlist "c:\temp.log"  
$compare = $store.Package0Package.PredCompareInfoSet["equal_i_unicode_string"]  
$predicate = new-object Microsoft.SqlServer.Management.XEvent.PredFunctionExpr -ArgumentList $compare, $operand, $value  
$event.SetPredicate($predicate)  
$session.Create()  
```  
  
## <a name="security"></a><span data-ttu-id="22230-136">Seguridad</span><span class="sxs-lookup"><span data-stu-id="22230-136">Security</span></span>  
 <span data-ttu-id="22230-137">Para crear, modificar o quitar una sesión de eventos extendidos, debe disponer del permiso ALTER ANY EVENT SESSION.</span><span class="sxs-lookup"><span data-stu-id="22230-137">To create, alter, or drop an Extended Events session, you must have the ALTER ANY EVENT SESSION permission.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22230-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="22230-138">See Also</span></span>  
 <span data-ttu-id="22230-139">[SQL Server PowerShell](../../powershell/sql-server-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="22230-139">[SQL Server PowerShell](../../powershell/sql-server-powershell.md) </span></span>  
 <span data-ttu-id="22230-140">[Usar la sesión de system_health](use-the-ssms-xe-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="22230-140">[Use the system_health Session](use-the-ssms-xe-profiler.md) </span></span>  
 [<span data-ttu-id="22230-141">Herramientas de eventos extendidos</span><span class="sxs-lookup"><span data-stu-id="22230-141">Extended Events Tools</span></span>](extended-events-tools.md)  
