---
title: Programar tareas administrativas automáticas en Agente SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- scheduling administrative tasks [SMO]
- SQL Server Agent [SMO]
- automatic administrative SMO tasks
ms.assetid: 900242ad-d6a2-48e9-8a1b-f0eea4413c16
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4a7620935a257a4200999cce27ba901588839b16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676435"
---
# <a name="scheduling-automatic-administrative-tasks-in-sql-server-agent"></a><span data-ttu-id="ad316-102">Programar tareas administrativas automáticas en el Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="ad316-102">Scheduling Automatic Administrative Tasks in SQL Server Agent</span></span>
  <span data-ttu-id="ad316-103">Los objetos siguientes representan al Agente de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en SMO:</span><span class="sxs-lookup"><span data-stu-id="ad316-103">In SMO, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent is represented by the following objects:</span></span>  
  
-   <span data-ttu-id="ad316-104">El objeto <xref:Microsoft.SqlServer.Management.Smo.Agent.JobServer> tiene tres colecciones de trabajos, alertas y operadores.</span><span class="sxs-lookup"><span data-stu-id="ad316-104">The <xref:Microsoft.SqlServer.Management.Smo.Agent.JobServer> object has three collections of jobs, alerts and operators.</span></span>  
  
-   <span data-ttu-id="ad316-105">El objeto <xref:Microsoft.SqlServer.Management.Smo.Agent.OperatorCollection> representa una lista de buscapersonas, direcciones de correo electrónico y operadores de net send a los que se puede notificar automáticamente los eventos mediante el Agente de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ad316-105">The <xref:Microsoft.SqlServer.Management.Smo.Agent.OperatorCollection> object represents a list of pager, e-mail addresses and net send operators that can be notified of events automatically by the Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent.</span></span>  
  
-   <span data-ttu-id="ad316-106">El objeto <xref:Microsoft.SqlServer.Management.Smo.Agent.AlertCollection> representa una lista de circunstancias como eventos del sistema o condiciones de rendimiento supervisadas por [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad316-106">The <xref:Microsoft.SqlServer.Management.Smo.Agent.AlertCollection> object represents a list of circumstances such as system events or performance conditions that are monitored by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="ad316-107">El objeto <xref:Microsoft.SqlServer.Management.Smo.Agent.JobCollection> es ligeramente más complejo.</span><span class="sxs-lookup"><span data-stu-id="ad316-107">The <xref:Microsoft.SqlServer.Management.Smo.Agent.JobCollection> object is slightly more complex.</span></span> <span data-ttu-id="ad316-108">Representa una lista de tareas de varios pasos que se ejecutan en programaciones especificadas.</span><span class="sxs-lookup"><span data-stu-id="ad316-108">It represents a list of multi-step tasks that run at specified schedules.</span></span> <span data-ttu-id="ad316-109">Los pasos e información de programación están almacenados en los objetos <xref:Microsoft.SqlServer.Management.Smo.Agent.JobStep> y <xref:Microsoft.SqlServer.Management.Smo.Agent.JobSchedule>.</span><span class="sxs-lookup"><span data-stu-id="ad316-109">The steps and schedule information are stored in the <xref:Microsoft.SqlServer.Management.Smo.Agent.JobStep> and <xref:Microsoft.SqlServer.Management.Smo.Agent.JobSchedule> objects.</span></span>  
  
 <span data-ttu-id="ad316-110">Los objetos del Agente de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] se encuentran en el espacio de nombres <xref:Microsoft.SqlServer.Management.Smo.Agent>.</span><span class="sxs-lookup"><span data-stu-id="ad316-110">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent objects are in the <xref:Microsoft.SqlServer.Management.Smo.Agent> namespace.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="ad316-111">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="ad316-111">Examples</span></span>  
 <span data-ttu-id="ad316-112">Para utilizar cualquier ejemplo de código que se proporcione, deberá elegir el entorno de programación, la plantilla de programación y el lenguaje de programación con los que crear su aplicación.</span><span class="sxs-lookup"><span data-stu-id="ad316-112">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="ad316-113">Para obtener más información, vea [crear un proyecto de Visual Basic SMO en Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) o [crear un proyecto de Visual C&#35; SMO en Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="ad316-113">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
1.  <span data-ttu-id="ad316-114">Para los programas que utilizan el Agente [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], debe incluir la instrucción `Imports` para certificar el espacio de nombres del Agente.</span><span class="sxs-lookup"><span data-stu-id="ad316-114">For programs that use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent, you must include the `Imports` statement to qualify the Agent namespace.</span></span> <span data-ttu-id="ad316-115">Inserte la instrucción después de las demás instrucciones `Imports`, antes de cualquier declaración de la aplicación, como:</span><span class="sxs-lookup"><span data-stu-id="ad316-115">Insert the statement after the other `Imports` statements, before any declarations in the application, such as:</span></span>  
  
 `Imports Microsoft.SqlServer.Management.Smo`  
  
 `Imports Microsoft.SqlServer.Management.Common`  
  
 `Imports Microsoft.SqlServer.Management.Smo.Agent`  
  
## <a name="creating-a-job-with-steps-and-a-schedule-in-visual-basic"></a><span data-ttu-id="ad316-116">Crear un trabajo con pasos y una programación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ad316-116">Creating a Job with Steps and a Schedule in Visual Basic</span></span>  
 <span data-ttu-id="ad316-117">En este ejemplo de código se crea un trabajo con pasos y una programación y, a continuación, se informa a un operador.</span><span class="sxs-lookup"><span data-stu-id="ad316-117">This code example creates a job with steps and a schedule, and then informs an operator.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBAgent1](SMO How to#SMO_VBAgent1)]  -->  
  
## <a name="creating-a-job-with-steps-and-a-schedule-in-visual-c"></a><span data-ttu-id="ad316-118">Crear un trabajo con pasos y una programación en Visual C#</span><span class="sxs-lookup"><span data-stu-id="ad316-118">Creating a Job with Steps and a Schedule in Visual C#</span></span>  
 <span data-ttu-id="ad316-119">En este ejemplo de código se crea un trabajo con pasos y una programación y, a continuación, se informa a un operador.</span><span class="sxs-lookup"><span data-stu-id="ad316-119">This code example creates a job with steps and a schedule, and then informs an operator.</span></span>  
  
```csharp
{  
            //Connect to the local, default instance of SQL Server.  
            Server srv = new Server();  
  
            //Define an Operator object variable by supplying the Agent (parent JobServer object) and the name in the constructor.   
            Operator op = new Operator(srv.JobServer, "Test_Operator");  
  
            //Set the Net send address.   
            op.NetSendAddress = "Network1_PC";  
  
            //Create the operator on the instance of SQL Server Agent.   
            op.Create();  
  
            //Define a Job object variable by supplying the Agent and the name arguments in the constructor and setting properties.   
            Job jb = new Job(srv.JobServer, "Test_Job");  
  
            //Specify which operator to inform and the completion action.   
            jb.OperatorToNetSend = "Test_Operator";  
            jb.NetSendLevel = CompletionAction.Always;  
  
            //Create the job on the instance of SQL Server Agent.   
            jb.Create();  
  
            //Define a JobStep object variable by supplying the parent job and name arguments in the constructor.   
            JobStep jbstp = new JobStep(jb, "Test_Job_Step");  
            jbstp.Command = "Test_StoredProc";  
            jbstp.OnSuccessAction = StepCompletionAction.QuitWithSuccess;  
            jbstp.OnFailAction = StepCompletionAction.QuitWithFailure;  
  
            //Create the job step on the instance of SQL Agent.   
            jbstp.Create();  
  
            //Define a JobSchedule object variable by supplying the parent job and name arguments in the constructor.   
  
            JobSchedule jbsch = new JobSchedule(jb, "Test_Job_Schedule");  
  
            //Set properties to define the schedule frequency, and duration.   
            jbsch.FrequencyTypes = FrequencyTypes.Daily;  
            jbsch.FrequencySubDayTypes = FrequencySubDayTypes.Minute;  
            jbsch.FrequencySubDayInterval = 30;  
            TimeSpan ts1 = new TimeSpan(9, 0, 0);  
            jbsch.ActiveStartTimeOfDay = ts1;  
  
            TimeSpan ts2 = new TimeSpan(17, 0, 0);  
            jbsch.ActiveEndTimeOfDay = ts2;  
            jbsch.FrequencyInterval = 1;  
  
            System.DateTime d = new System.DateTime(2003, 1, 1);  
            jbsch.ActiveStartDate = d;  
  
            //Create the job schedule on the instance of SQL Agent.   
            jbsch.Create();  
        }  
```  
  
## <a name="creating-a-job-with-steps-and-a-schedule-in-powershell"></a><span data-ttu-id="ad316-120">Crear un trabajo con pasos y una programación en PowerShell</span><span class="sxs-lookup"><span data-stu-id="ad316-120">Creating a Job with Steps and a Schedule in PowerShell</span></span>  
 <span data-ttu-id="ad316-121">En este ejemplo de código se crea un trabajo con pasos y una programación y, a continuación, se informa a un operador.</span><span class="sxs-lookup"><span data-stu-id="ad316-121">This code example creates a job with steps and a schedule, and then informs an operator.</span></span>  
  
```powershell
#Get a server object which corresponds to the default instance  
$srv = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Server  
  
#Define an Operator object variable by supplying the Agent (parent JobServer object) and the name in the constructor.  
$op = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Agent.Operator -argumentlist $srv.JobServer, "Test_Operator"  
  
#Set the Net send address.  
$op.NetSendAddress = "Network1_PC"  
  
#Create the operator on the instance of SQL Agent.  
$op.Create()  
  
#Define a Job object variable by supplying the Agent and the name arguments in the constructor and setting properties.   
$jb = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Agent.Job -argumentlist $srv.JobServer, "Test_Job"   
  
#Specify which operator to inform and the completion action.   
$jb.OperatorToNetSend = "Test_Operator";   
$jb.NetSendLevel = [Microsoft.SqlServer.Management.SMO.Agent.CompletionAction]::Always  
  
#Create the job on the instance of SQL Server Agent.   
$jb.Create()  
  
#Define a JobStep object variable by supplying the parent job and name arguments in the constructor.   
$jbstp = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Agent.JobStep -argumentlist $jb, "Test_Job_Step"   
$jbstp.Command = "Test_StoredProc";   
$jbstp.OnSuccessAction = [Microsoft.SqlServer.Management.SMO.Agent.StepCompletionAction]::QuitWithSuccess;   
$jbstp.OnFailAction =[Microsoft.SqlServer.Management.SMO.Agent.StepCompletionAction]::QuitWithFailure;   
  
#Create the job step on the instance of SQL Agent.   
$jbstp.Create();   
  
#Define a JobSchedule object variable by supplying the parent job and name arguments in the constructor.   
$jbsch = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Agent.JobSchedule -argumentlist $jb, "Test_Job_Schedule"   
  
#Set properties to define the schedule frequency, and duration.   
$jbsch.FrequencyTypes =  [Microsoft.SqlServer.Management.SMO.Agent.FrequencyTypes]::Daily  
  
$jbsch.FrequencySubDayTypes = [Microsoft.SqlServer.Management.SMO.Agent.FrequencySubDayTypes]::Minute  
$jbsch.FrequencySubDayInterval = 30  
$ts1 =  New-Object -TypeName TimeSpan -argumentlist 9, 0, 0  
$jbsch.ActiveStartTimeOfDay = $ts1  
$ts2 = New-Object -TypeName TimeSpan -argumentlist 17, 0, 0  
$jbsch.ActiveEndTimeOfDay = $ts2  
$jbsch.FrequencyInterval = 1  
$jbsch.ActiveStartDate = "01/01/2003"  
  
#Create the job schedule on the instance of SQL Agent.   
$jbsch.Create();  
```  
  
## <a name="creating-an-alert-in-visual-basic"></a><span data-ttu-id="ad316-122">Crear una alerta en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ad316-122">Creating an Alert in Visual Basic</span></span>  
 <span data-ttu-id="ad316-123">En este ejemplo de código se crea una alerta que se desencadena mediante una condición de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="ad316-123">This code example creates an alert that is triggered by a performance condition.</span></span> <span data-ttu-id="ad316-124">La condición se debe proporcionar en un formato concreto:</span><span class="sxs-lookup"><span data-stu-id="ad316-124">The condition must be provided in a specific format:</span></span>  
  
 <span data-ttu-id="ad316-125">**ObjectName | Nombre de | Instancia de | ComparisionOp | CompValue**</span><span class="sxs-lookup"><span data-stu-id="ad316-125">**ObjectName|CounterName|Instance|ComparisionOp|CompValue**</span></span>  
  
 <span data-ttu-id="ad316-126">Se requiere un operador para la notificación de alerta.</span><span class="sxs-lookup"><span data-stu-id="ad316-126">An operator is required for the alert notification.</span></span> <span data-ttu-id="ad316-127">El tipo <xref:Microsoft.SqlServer.Management.Smo.Agent.Operator> requiere los corchetes porque `operator` es una palabra clave de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ad316-127">The <xref:Microsoft.SqlServer.Management.Smo.Agent.Operator> type requires square parentheses because `operator` is a Visual Basic keyword.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBAgent3](SMO How to#SMO_VBAgent3)]  -->  
  
## <a name="creating-an-alert-in-visual-c"></a><span data-ttu-id="ad316-128">Crear una alerta en Visual C#</span><span class="sxs-lookup"><span data-stu-id="ad316-128">Creating an Alert in Visual C#</span></span>  
 <span data-ttu-id="ad316-129">En este ejemplo de código se crea una alerta que se desencadena mediante una condición de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="ad316-129">This code example creates an alert that is triggered by a performance condition.</span></span> <span data-ttu-id="ad316-130">La condición se debe proporcionar en un formato concreto:</span><span class="sxs-lookup"><span data-stu-id="ad316-130">The condition must be provided in a specific format:</span></span>  
  
 <span data-ttu-id="ad316-131">**ObjectName | Nombre de | Instancia de | ComparisionOp | CompValue**</span><span class="sxs-lookup"><span data-stu-id="ad316-131">**ObjectName|CounterName|Instance|ComparisionOp|CompValue**</span></span>  
  
 <span data-ttu-id="ad316-132">Se requiere un operador para la notificación de alerta.</span><span class="sxs-lookup"><span data-stu-id="ad316-132">An operator is required for the alert notification.</span></span> <span data-ttu-id="ad316-133">El tipo <xref:Microsoft.SqlServer.Management.Smo.Agent.Operator> requiere los corchetes porque `operator` es una palabra clave de [!INCLUDE[csprcs](../../../includes/csprcs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad316-133">The <xref:Microsoft.SqlServer.Management.Smo.Agent.Operator> type requires square parentheses because `operator` is a [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] keyword.</span></span>  
  
```csharp
{  
             //Connect to the local, default instance of SQL Server.   
            Server srv = new Server();  
  
            //Define an Alert object variable by supplying the SQL Server Agent and the name arguments in the constructor.   
            Alert al = new Alert(srv.JobServer, "Test_Alert");  
  
            //Specify the performance condition string to define the alert.   
            al.PerformanceCondition = "SQLServer:General Statistics|User Connections||>|3";  
  
            //Create the alert on the SQL Agent.   
            al.Create();  
  
            //Define an Operator object variable by supplying the SQL Server Agent and the name arguments in the constructor.   
  
            Operator op = new Operator(srv.JobServer, "Test_Operator");  
            //Set the net send address.   
            op.NetSendAddress = "NetworkPC";  
            //Create the operator on the SQL Agent.   
            op.Create();  
            //Run the AddNotification method to specify the operator is notified when the alert is raised.   
            al.AddNotification("Test_Operator", NotifyMethods.NetSend);  
        }  
```  
  
## <a name="creating-an-alert-in-powershell"></a><span data-ttu-id="ad316-134">Crear una alerta en PowerShell</span><span class="sxs-lookup"><span data-stu-id="ad316-134">Creating an Alert in PowerShell</span></span>  
 <span data-ttu-id="ad316-135">En este ejemplo de código se crea una alerta que se desencadena mediante una condición de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="ad316-135">This code example creates an alert that is triggered by a performance condition.</span></span> <span data-ttu-id="ad316-136">La condición se debe proporcionar en un formato concreto:</span><span class="sxs-lookup"><span data-stu-id="ad316-136">The condition must be provided in a specific format:</span></span>  
  
 <span data-ttu-id="ad316-137">**ObjectName | Nombre de | Instancia de | ComparisionOp | CompValue**</span><span class="sxs-lookup"><span data-stu-id="ad316-137">**ObjectName|CounterName|Instance|ComparisionOp|CompValue**</span></span>  
  
 <span data-ttu-id="ad316-138">Se requiere un operador para la notificación de alerta.</span><span class="sxs-lookup"><span data-stu-id="ad316-138">An operator is required for the alert notification.</span></span> <span data-ttu-id="ad316-139">El tipo <xref:Microsoft.SqlServer.Management.Smo.Agent.Operator> requiere los corchetes porque `operator` es una palabra clave de [!INCLUDE[csprcs](../../../includes/csprcs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad316-139">The <xref:Microsoft.SqlServer.Management.Smo.Agent.Operator> type requires square parentheses because `operator` is a [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] keyword.</span></span>  
  
```powershell
#Get a server object which corresponds to the default instance  
$srv = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Server  
  
#Define an Alert object variable by supplying the SQL Agent and the name arguments in the constructor.  
$al = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Agent.Alert -argumentlist $srv.JobServer, "Test_Alert"  
  
#Specify the performance condition string to define the alert.  
$al.PerformanceCondition = "SQLServer:General Statistics|User Connections||>|3"  
  
#Create the alert on the SQL Agent.  
$al.Create()  
  
#Define an Operator object variable by supplying the Agent (parent JobServer object) and the name in the constructor.  
$op = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Agent.Operator -argumentlist $srv.JobServer, "Test_Operator"  
  
#Set the Net send address.  
$op.NetSendAddress = "Network1_PC"  
  
#Create the operator on the instance of SQL Agent.  
$op.Create()  
  
#Run the AddNotification method to specify the operator is notified when the alert is raised.  
$ns = [Microsoft.SqlServer.Management.SMO.Agent.NotifyMethods]::NetSend  
$al.AddNotification("Test_Operator", $ns)  
  
#Drop the alert and the operator  
$al.Drop()  
$op.Drop()  
```  
  
## <a name="allowing-user-access-to-subsystem-by-using-a-proxy-account-in-visual-basic"></a><span data-ttu-id="ad316-140">Permite el acceso del usuario al subsistema mediante una cuenta de proxy en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ad316-140">Allowing User Access to Subsystem by Using a Proxy Account in Visual Basic</span></span>  
 <span data-ttu-id="ad316-141">En este ejemplo de código se muestra cómo permitir el acceso de un usuario a un subsistema especificado utilizando el método <xref:Microsoft.SqlServer.Management.Smo.Agent.ProxyAccount.AddSubSystem%2A> del objeto <xref:Microsoft.SqlServer.Management.Smo.Agent.ProxyAccount>.</span><span class="sxs-lookup"><span data-stu-id="ad316-141">This code example shows how to allow a user access to a specified subsystem by using the <xref:Microsoft.SqlServer.Management.Smo.Agent.ProxyAccount.AddSubSystem%2A> method of the <xref:Microsoft.SqlServer.Management.Smo.Agent.ProxyAccount> object.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBAgent2](SMO How to#SMO_VBAgent2)]  -->  
  
## <a name="allowing-user-access-to-subsystem-by-using-a-proxy-account-in-visual-c"></a><span data-ttu-id="ad316-142">Permite el acceso del usuario al subsistema mediante una cuenta de proxy en Visual C#</span><span class="sxs-lookup"><span data-stu-id="ad316-142">Allowing User Access to Subsystem by Using a Proxy Account in Visual C#</span></span>  
 <span data-ttu-id="ad316-143">En este ejemplo de código se muestra cómo permitir el acceso de un usuario a un subsistema especificado utilizando el método <xref:Microsoft.SqlServer.Management.Smo.Agent.ProxyAccount.AddSubSystem%2A> del objeto <xref:Microsoft.SqlServer.Management.Smo.Agent.ProxyAccount>.</span><span class="sxs-lookup"><span data-stu-id="ad316-143">This code example shows how to allow a user access to a specified subsystem by using the <xref:Microsoft.SqlServer.Management.Smo.Agent.ProxyAccount.AddSubSystem%2A> method of the <xref:Microsoft.SqlServer.Management.Smo.Agent.ProxyAccount> object.</span></span>  
  
```csharp
//Connect to the local, default instance of SQL Server.   
{   
Server srv = default(Server);   
srv = new Server();   
//Declare a JobServer object variable and reference the SQL Server Agent.   
JobServer js = default(JobServer);   
js = srv.JobServer;   
//Define a Credential object variable by supplying the parent server and name arguments in the constructor.   
Credential c = default(Credential);   
c = new Credential(srv, "Proxy_accnt");   
//Set the identity to a valid login represented by the vIdentity string variable.   
//The sub system will run under this login.   
c.Identity = vIdentity;   
//Create the credential on the instance of SQL Server.   
c.Create();   
//Define a ProxyAccount object variable by supplying the SQL Server Agent, the name, the credential, the description arguments in the constructor.   
ProxyAccount pa = default(ProxyAccount);   
pa = new ProxyAccount(js, "Test_proxy", "Proxy_accnt", true, "Proxy account for users to run job steps in command shell.");   
//Create the proxy account on the SQL Agent.   
pa.Create();   
//Add the login, represented by the vLogin string variable, to the proxy account.   
pa.AddLogin(vLogin);   
//Add the CmdExec subsytem to the proxy account.   
pa.AddSubSystem(AgentSubSystem.CmdExec);   
}   
//Now users logged on as vLogin can run CmdExec job steps with the specified credentials.   
```  
  
## <a name="see-also"></a><span data-ttu-id="ad316-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ad316-144">See Also</span></span>  
 <span data-ttu-id="ad316-145">[Agente SQL Server](../../../ssms/agent/sql-server-agent.md) </span><span class="sxs-lookup"><span data-stu-id="ad316-145">[SQL Server Agent](../../../ssms/agent/sql-server-agent.md) </span></span>  
 [<span data-ttu-id="ad316-146">Implementar trabajos</span><span class="sxs-lookup"><span data-stu-id="ad316-146">Implement Jobs</span></span>](../../../ssms/agent/implement-jobs.md)  
