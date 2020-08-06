---
title: Agregar compatibilidad con la depuración de una tarea personalizada | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- BreakpointManager class
- breakpoints [Integration Services]
- custom tasks [Integration Services], debugging
- IDTSSuspend interface
- IDTSBreakpointSite interface
- SSIS custom tasks, debugging
- debugging [Integration Services], custom tasks
ms.assetid: 7f06e49b-0b60-4e81-97da-d32dc248264a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fcc1d0c18cd559b547eadb9c1fa77e8f143389d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674222"
---
# <a name="adding-support-for-debugging-in-a-custom-task"></a><span data-ttu-id="c51c2-102">Agregar compatibilidad con la depuración de una tarea personalizada</span><span class="sxs-lookup"><span data-stu-id="c51c2-102">Adding Support for Debugging in a Custom Task</span></span>
  <span data-ttu-id="c51c2-103">El motor de ejecución de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] permite suspender paquetes, tareas y otros tipos de contenedores durante la ejecución mediante puntos de interrupción.</span><span class="sxs-lookup"><span data-stu-id="c51c2-103">The [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] run-time engine enables packages, tasks, and other types of containers to be suspended during execution by using breakpoints.</span></span> <span data-ttu-id="c51c2-104">El uso de puntos de interrupción le permite revisar y corregir los errores que impiden que la aplicación o tareas se ejecuten correctamente.</span><span class="sxs-lookup"><span data-stu-id="c51c2-104">The use of breakpoints lets you review and correct errors that prevent your application or tasks from running correctly.</span></span> <span data-ttu-id="c51c2-105">La arquitectura de punto de interrupción permite al cliente evaluar el valor en tiempo de ejecución de los objetos del paquete en los puntos definidos de ejecución mientras se suspende el procesamiento de la tarea.</span><span class="sxs-lookup"><span data-stu-id="c51c2-105">The breakpoint architecture enables the client to evaluate the run-time value of objects in the package at defined points of execution while task processing is suspended.</span></span>  
  
 <span data-ttu-id="c51c2-106">Los programadores de tareas personalizadas pueden utilizar esta arquitectura para crear destinos de punto de interrupción personalizados mediante la interfaz <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> y su interfaz primaria, <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend>.</span><span class="sxs-lookup"><span data-stu-id="c51c2-106">Custom task developers can use this architecture to create custom breakpoint targets by using the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> interface, and its parent interface, <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend>.</span></span> <span data-ttu-id="c51c2-107">La interfaz <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> define la interacción entre el motor de ejecución y la tarea para crear y administrar sitios o destinos de puntos de interrupción personalizados.</span><span class="sxs-lookup"><span data-stu-id="c51c2-107">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> interface defines the interaction between the run-time engine and the task for creating and managing custom breakpoint sites or targets.</span></span> <span data-ttu-id="c51c2-108">La interfaz <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend> proporciona los métodos y propiedades a los que llama el motor de ejecución para notificar a la tarea que suspenda o reanude la ejecución.</span><span class="sxs-lookup"><span data-stu-id="c51c2-108">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend> interface provides methods and properties that are called by the run-time engine to notify the task to suspend or resume its execution.</span></span>  
  
 <span data-ttu-id="c51c2-109">Un sitio o destino de punto de interrupción es un punto en la ejecución de la tarea donde se puede suspender el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="c51c2-109">A breakpoint site or target is a point in the execution of the task where processing can be suspended.</span></span> <span data-ttu-id="c51c2-110">Los usuarios seleccionan entre los sitios de punto de interrupción disponibles en el cuadro de diálogo **Establecer puntos de interrupción**.</span><span class="sxs-lookup"><span data-stu-id="c51c2-110">Users select from available breakpoint sites in the **Set Breakpoints** dialog box.</span></span> <span data-ttu-id="c51c2-111">Por ejemplo, además de las opciones de punto de interrupción predeterminadas, el contenedor de bucles Foreach proporciona la opción "Interrumpir al principio de cada iteración del bucle".</span><span class="sxs-lookup"><span data-stu-id="c51c2-111">For example, in addition to the default breakpoint options, the Foreach Loop Container offers the "Break at the beginning of every iteration of the loop" option.</span></span>  
  
 <span data-ttu-id="c51c2-112">Cuando una tarea alcanza un destino de punto de interrupción durante la ejecución, evalúa dicho destino para determinar si está habilitado un punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="c51c2-112">When a task reaches a breakpoint target during execution, it evaluates the breakpoint target to determine whether a breakpoint is enabled.</span></span> <span data-ttu-id="c51c2-113">Esto indica que el usuario desea que la ejecución se detenga en ese punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="c51c2-113">This indicates that the user wants execution to stop at that breakpoint.</span></span> <span data-ttu-id="c51c2-114">Si el punto de interrupción está habilitado, la tarea provoca el evento <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A> en el motor de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c51c2-114">If the breakpoint is enabled, the task raises the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A> event to the run-time engine.</span></span> <span data-ttu-id="c51c2-115">El motor de ejecución responde al evento llamando al método `Suspend` de cada tarea que se está ejecutando actualmente en el paquete.</span><span class="sxs-lookup"><span data-stu-id="c51c2-115">The run-time engine responds to the event by calling the `Suspend` method of each task that is currently running in the package.</span></span> <span data-ttu-id="c51c2-116">La ejecución de la tarea se reanuda cuando el módulo ejecutable llama al método `ResumeExecution` de la tarea suspendida.</span><span class="sxs-lookup"><span data-stu-id="c51c2-116">Execution of the task resumes when the runtime calls the `ResumeExecution` method of the suspended task.</span></span>  
  
 <span data-ttu-id="c51c2-117">Las tareas que no utilizan los puntos de interrupción deberían implementar todavía las interfaces <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> y <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend>.</span><span class="sxs-lookup"><span data-stu-id="c51c2-117">Tasks that do not use breakpoints should still implement the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> and <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend> interfaces.</span></span> <span data-ttu-id="c51c2-118">Esto asegura que la tarea se suspende correctamente cuando otros objetos del paquete provocan eventos <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A>.</span><span class="sxs-lookup"><span data-stu-id="c51c2-118">This ensures that the task is suspended correctly when other objects in the package raise <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A> events.</span></span>  
  
## <a name="idtsbreakpointsite-interface-and-breakpointmanager"></a><span data-ttu-id="c51c2-119">Interfaz IDTSBreakpointSite y BreakpointManager</span><span class="sxs-lookup"><span data-stu-id="c51c2-119">IDTSBreakpointSite Interface and BreakpointManager</span></span>  
 <span data-ttu-id="c51c2-120">Las tareas crean los destinos de punto de interrupción llamando al método <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager.CreateBreakpointTarget%2A> de <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager>, proporcionando un identificador entero y una descripción de cadena como parámetros.</span><span class="sxs-lookup"><span data-stu-id="c51c2-120">Tasks create breakpoint targets by calling the <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager.CreateBreakpointTarget%2A> method of the <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager>, providing an integer ID and string description as parameters.</span></span> <span data-ttu-id="c51c2-121">Cuando la tarea alcanza el punto en el código que contiene un destino de punto de interrupción, evalúa dicho destino mediante el método <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager.IsBreakpointTargetEnabled%2A> para determinar si ese punto de interrupción está habilitado.</span><span class="sxs-lookup"><span data-stu-id="c51c2-121">When the task reaches the point in its code that contains a breakpoint target, it evaluates the breakpoint target by using the <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager.IsBreakpointTargetEnabled%2A> method to determine whether that breakpoint is enabled.</span></span> <span data-ttu-id="c51c2-122">Si es `true`, la tarea se lo notifica al motor de ejecución provocando el evento <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A>.</span><span class="sxs-lookup"><span data-stu-id="c51c2-122">If `true`, the task notifies the run-time engine by raising the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A> event.</span></span>  
  
 <span data-ttu-id="c51c2-123">La interfaz <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> define un método único, <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite.AcceptBreakpointManager%2A>, al que el motor de ejecución llama durante la creación de la tarea.</span><span class="sxs-lookup"><span data-stu-id="c51c2-123">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> interface defines a single method, <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite.AcceptBreakpointManager%2A>, which is called by the run-time engine during task creation.</span></span> <span data-ttu-id="c51c2-124">Este método proporciona el objeto <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager> como un parámetro, que a continuación lo utiliza la tarea para crear y administrar los puntos de interrupción.</span><span class="sxs-lookup"><span data-stu-id="c51c2-124">This method provides as a parameter the <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager> object, which is then used by the task to create and manage its breakpoints.</span></span> <span data-ttu-id="c51c2-125">Las tareas deben almacenar <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager> localmente para su uso durante los métodos `Validate` y `Execute`.</span><span class="sxs-lookup"><span data-stu-id="c51c2-125">Tasks should store the <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager> locally for use during the `Validate` and `Execute` methods.</span></span>  
  
 <span data-ttu-id="c51c2-126">En el código de ejemplo siguiente se muestra cómo crear un destino de punto de interrupción mediante <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager>.</span><span class="sxs-lookup"><span data-stu-id="c51c2-126">The following sample code demonstrates how to create a breakpoint target by using the <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager>.</span></span> <span data-ttu-id="c51c2-127">El ejemplo llama al método <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A> para provocar el evento.</span><span class="sxs-lookup"><span data-stu-id="c51c2-127">The sample calls the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A> method to raise the event.</span></span>  
  
```csharp  
public void AcceptBreakpointManager( BreakpointManager breakPointManager )  
{  
   //   Store the breakpoint manager locally.  
   this.bpm  = breakPointManager;  
}  
public override DTSExecResult Execute( Connections connections,  
  Variables variables, IDTSComponentEvents events,  
  IDTSLogging log, DtsTransaction txn)  
{  
   //   Create a breakpoint.  
   this.bpm.CreateBreakPointTarget( 1 , "A sample breakpoint target." );  
...  
   if( this.bpm.IsBreakpointTargetEnabled( 1 ) == true )  
      events.OnBreakpointHit( this.bpm.GetBreakpointTarget( 1 ) );  
}  
```  
  
```vb  
Public Sub AcceptBreakpointManager(ByVal breakPointManager As BreakpointManager)  
  
   ' Store the breakpoint manager locally.  
   Me.bpm  = breakPointManager  
  
End Sub  
  
Public Overrides Function Execute(ByVal connections As Connections, _  
  ByVal variables As Variables, ByVal events As IDTSComponentEvents, _  
  ByVal log As IDTSLogging, ByVal txn As DtsTransaction) As DTSExecResult  
  
   ' Create a breakpoint.  
   Me.bpm.CreateBreakPointTarget(1 , "A sample breakpoint target.")  
  
   If Me.bpm.IsBreakpointTargetEnabled(1) = True Then  
      events.OnBreakpointHit(Me.bpm.GetBreakpointTarget(1))  
   End If  
  
End Function  
```  
  
## <a name="idtssuspend-interface"></a><span data-ttu-id="c51c2-128">Interfaz IDTSSuspend</span><span class="sxs-lookup"><span data-stu-id="c51c2-128">IDTSSuspend Interface</span></span>  
 <span data-ttu-id="c51c2-129">La interfaz <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend> define los métodos a los que llama el motor de ejecución cuando pone en pausa o reanuda la ejecución de una tarea.</span><span class="sxs-lookup"><span data-stu-id="c51c2-129">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend> interface defines the methods that are called by the run-time engine when it pauses or resumes execution of a task.</span></span> <span data-ttu-id="c51c2-130">La interfaz <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend> implementa la interfaz <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> y la tarea personalizada invalida normalmente los métodos `Suspend` y `ResumeExecution`.</span><span class="sxs-lookup"><span data-stu-id="c51c2-130">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend> interface is implemented by the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> interface, and its `Suspend` and `ResumeExecution` methods are usually overridden by the custom task.</span></span> <span data-ttu-id="c51c2-131">Cuando el motor de ejecución recibe un evento `OnBreakpointHit` de una tarea, llama al método `Suspend` de cada tarea en ejecución, notificando a las tareas que se pongan en pausa.</span><span class="sxs-lookup"><span data-stu-id="c51c2-131">When the run-time engine receives an `OnBreakpointHit` event from a task, it calls the `Suspend` method of each running task, notifying the tasks to pause.</span></span> <span data-ttu-id="c51c2-132">Cuando el cliente reanuda la ejecución, el motor de ejecución llama al método `ResumeExecution` de las tareas que están suspendidas.</span><span class="sxs-lookup"><span data-stu-id="c51c2-132">When the client resumes execution, the run-time engine calls the `ResumeExecution` method of the tasks that are suspended.</span></span>  
  
 <span data-ttu-id="c51c2-133">La suspensión y reanudación de la ejecución de la tarea implica poner en pausa y reanudar el subproceso de ejecución de la tarea.</span><span class="sxs-lookup"><span data-stu-id="c51c2-133">Suspending and resuming task execution involves pausing and resuming the task's execution thread.</span></span> <span data-ttu-id="c51c2-134">En código administrado, para hacer esto se utiliza la clase `ManualResetEvent` en el espacio de nombres `System.Threading` de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c51c2-134">In managed code, you do this using the `ManualResetEvent` class in `System.Threading` namespace of the .NET Framework.</span></span>  
  
 <span data-ttu-id="c51c2-135">En el ejemplo de código siguiente se muestra la suspensión y reanudación de la ejecución de una tarea.</span><span class="sxs-lookup"><span data-stu-id="c51c2-135">The following code sample demonstrates suspension and resumption of task execution.</span></span> <span data-ttu-id="c51c2-136">Observe que el método `Execute` ha cambiado respecto al ejemplo de código anterior y el subproceso de ejecución se pone en pausa al activar el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="c51c2-136">Notice that the `Execute` method has changed from the previous code sample, and the execution thread is paused when firing the breakpoint.</span></span>  
  
```csharp  
private ManualResetEvent m_suspended = new ManualResetEvent( true );  
private ManualResetEvent m_canExecute = new ManualResetEvent( true );  
private int   m_suspendRequired = 0;  
private int   m_debugMode = 0;  
  
public override DTSExecResult Execute( Connections connections, Variables variables, IDTSComponentEvents events, IDTSLogging log, DtsTransaction txn)  
{  
   // While a task is not executing, it is suspended.    
   // Now that we are executing,  
   // change to not suspended.  
   ChangeEvent(m_suspended, false);  
  
   // Check for a suspend before doing any work,   
   // in case the suspend and execute calls  
   // were initiated at virtually the same time.  
   CheckAndSuspend();  
   CheckAndFireBreakpoint( componentEvents, 1);  
}  
private void CheckAndSuspend()  
{  
   // Loop until we can execute.    
   // The loop is required rather than a simple If  
   // because there is a time between the return from WaitOne and the  
   // reset that we might receive another Suspend call.    
   // Suspend() will see that we are suspended  
   // and return.  So we need to rewait.  
   while (!m_canExecute.WaitOne(0, false))  
   {  
      ChangeEvent(m_suspended, true);  
      m_canExecute.WaitOne();  
      ChangeEvent(m_suspended, false);  
   }  
}  
private void CheckAndFireBreakpoint(IDTSComponentEvents events, int breakpointID)  
{  
   // If the breakpoint is enabled, fire it.  
   if (m_debugMode != 0 &&    this.bpm.IsBreakpointTargetEnabled(breakpointID))  
   {  
      //   Enter a suspend mode before firing the breakpoint.    
      //   Firing the breakpoint will cause the runtime   
      //   to call Suspend on this task.    
      //   Because we are blocked on the breakpoint,   
      //   we are suspended.  
      ChangeEvent(m_suspended, true);  
      events.OnBreakpointHit(this.bpm.GetBreakpointTarget(breakpointID));  
      ChangeEvent(m_suspended, false);  
   }  
   // Check for a suspension for two reasons:   
   //   1. If we are at a point where we could fire a breakpoint,   
   //      we are at a valid suspend point.  Even if we didn't hit a  
   //      breakpoint, the runtime may have called suspend,   
   //      so check for it.       
   //   2. Between the return from OnBreakpointHit   
   //      and the reset of the event, it is possible to have  
   //      received a suspend call from which we returned because   
   //      we were already suspended.  We need to be sure it is okay  
   //      to continue executing now.  
   CheckAndSuspend();  
}  
static void ChangeEvent(ManualResetEvent e, bool shouldSet)  
{  
   bool succeeded;  
   if (shouldSet)  
      succeeded = e.Set();  
   else  
      succeeded = e.Reset();  
  
   if (!succeeded)  
      throw new Exception("Synchronization object failed.");  
  
}  
public bool SuspendRequired  
{  
   get   {return m_suspendRequired != 0;}  
   set  
   {  
      // This lock is also taken by Suspend().    
      // Because it is possible for the package to be  
      // suspended and resumed in quick succession,   
      // this property might be set before  
      // the actual Suspend() call.    
      // Without the lock, the Suspend() might reset the canExecute  
      // event after we set it to abort the suspension.  
      lock (this)  
      {  
         Interlocked.Exchange(ref m_suspendRequired, value ? 1 : 0);  
         if (!value)  
            ResumeExecution();  
      }  
   }  
}  
public void ResumeExecution()  
{  
   ChangeEvent( m_canExecute,true );  
}  
public void Suspend()  
{  
   // This lock is also taken by the set SuspendRequired method.    
   // It prevents this call from overriding an   
   // aborted suspension.  See comments in set SuspendRequired.  
   lock (this)  
   {  
      // If a Suspend is required, do it.  
      if (m_suspendRequired != 0)  
         ChangeEvent(m_canExecute, false);  
   }  
   // We can't return from Suspend until the task is "suspended".  
   // This can happen one of two ways:   
   // the m_suspended event occurs, indicating that the execute thread  
   // has suspended, or the canExecute flag is set,   
   // indicating that a suspend is no longer required.  
   WaitHandle [] suspendOperationComplete = {m_suspended, m_canExecute};  
   WaitHandle.WaitAny(suspendOperationComplete);  
}  
```  
  
```vb  
Private m_suspended As ManualResetEvent = New ManualResetEvent(True)  
Private m_canExecute As ManualResetEvent = New ManualResetEvent(True)  
Private m_suspendRequired As Integer = 0  
Private m_debugMode As Integer = 0  
  
Public Overrides Function Execute(ByVal connections As Connections, _  
ByVal variables As Variables, ByVal events As IDTSComponentEvents, _  
ByVal log As IDTSLogging, ByVal txn As DtsTransaction) As DTSExecResult  
  
   ' While a task is not executing it is suspended.    
   ' Now that we are executing,  
   ' change to not suspended.  
   ChangeEvent(m_suspended, False)  
  
   ' Check for a suspend before doing any work,   
   ' in case the suspend and execute calls  
   ' were initiated at virtually the same time.  
   CheckAndSuspend()  
   CheckAndFireBreakpoint(componentEvents, 1)  
  
End Function  
  
Private Sub CheckAndSuspend()  
  
   ' Loop until we can execute.    
   ' The loop is required rather than a simple if  
   ' because there is a time between the return from WaitOne and the  
   ' reset that we might receive another Suspend call.    
   ' Suspend() will see that we are suspended  
   ' and return.  So we need to rewait.  
   Do While Not m_canExecute.WaitOne(0, False)  
              ChangeEvent(m_suspended, True)  
              m_canExecute.WaitOne()  
              ChangeEvent(m_suspended, False)  
   Loop  
  
End Sub  
  
Private Sub CheckAndFireBreakpoint(ByVal events As IDTSComponentEvents, _  
ByVal breakpointID As Integer)  
  
   ' If the breakpoint is enabled, fire it.  
   If m_debugMode <> 0 AndAlso Me.bpm.IsBreakpointTargetEnabled(breakpointID) Then  
              '   Enter a suspend mode before firing the breakpoint.    
              '   Firing the breakpoint will cause the runtime   
              '   to call Suspend on this task.    
              '   Because we are blocked on the breakpoint,   
              '   we are suspended.  
              ChangeEvent(m_suspended, True)  
              events.OnBreakpointHit(Me.bpm.GetBreakpointTarget(breakpointID))  
              ChangeEvent(m_suspended, False)  
   End If  
  
   ' Check for a suspension for two reasons:   
   '   1. If we are at a point where we could fire a breakpoint,   
   '         we are at a valid suspend point.  Even if we didn't hit a  
   '         breakpoint, the runtime may have called suspend,   
   '         so check for it.     
   '   2. Between the return from OnBreakpointHit   
   '         and the reset of the event, it is possible to have  
   '         received a suspend call from which we returned because   
   '         we were already suspended.  We need to be sure it is okay  
   '         to continue executing now.  
   CheckAndSuspend()  
  
End Sub  
  
Shared Sub ChangeEvent(ByVal e As ManualResetEvent, ByVal shouldSet As Boolean)  
  
   Dim succeeded As Boolean  
   If shouldSet Then  
              succeeded = e.Set()  
   Else  
              succeeded = e.Reset()  
   End If  
  
   If (Not succeeded) Then  
              Throw New Exception("Synchronization object failed.")  
   End If  
  
End Sub  
  
Public Property SuspendRequired() As Boolean  
   Get  
               Return m_suspendRequired <> 0  
  End Get  
  Set  
    ' This lock is also taken by Suspend().    
     '   Because it is possible for the package to be  
     '   suspended and resumed in quick succession,   
     '   this property might be set before  
     '   the actual Suspend() call.    
     '   Without the lock, the Suspend() might reset the canExecute  
     '   event after we set it to abort the suspension.  
              SyncLock Me  
                         Interlocked.Exchange(m_suspendRequired,IIf(Value, 1, 0))  
                         If (Not Value) Then  
                                    ResumeExecution()  
                         End If  
              End SyncLock  
   End Set  
End Property  
  
Public Sub ResumeExecution()  
   ChangeEvent(m_canExecute,True)  
End Sub  
  
Public Sub Suspend()  
  
   ' This lock is also taken by the set SuspendRequired method.    
   ' It prevents this call from overriding an   
   ' aborted suspension.  See comments in set SuspendRequired.  
   SyncLock Me  
   ' If a Suspend is required, do it.  
              If m_suspendRequired <> 0 Then  
                         ChangeEvent(m_canExecute, False)  
              End If  
   End SyncLock  
   ' We can't return from Suspend until the task is "suspended".  
   ' This can happen one of two ways:   
   ' the m_suspended event occurs, indicating that the execute thread  
   ' has suspended, or the canExecute flag is set,   
   ' indicating that a suspend is no longer required.  
   Dim suspendOperationComplete As WaitHandle() = {m_suspended, m_canExecute}  
   WaitHandle.WaitAny(suspendOperationComplete)  
  
End Sub  
```  
  
<span data-ttu-id="c51c2-137">![Integration Services icono (pequeño)](../../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="c51c2-137">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="c51c2-138">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="c51c2-138">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="c51c2-139">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="c51c2-139">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="c51c2-140">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="c51c2-140">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c51c2-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c51c2-141">See Also</span></span>  
 [<span data-ttu-id="c51c2-142">Depurar el flujo de control</span><span class="sxs-lookup"><span data-stu-id="c51c2-142">Debugging Control Flow</span></span>](../../troubleshooting/debugging-control-flow.md)  
  
  
