---
title: Supervisar los contadores de rendimiento con la tarea Script | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- performance counters [Integration Services]
- SSIS Script task, performance counters
- custom performance counters [Integration Services]
- Script task [Integration Services], examples
- Script task [Integration Services], performance counters
- counters [Integration Services]
ms.assetid: 86609bf1-cae6-435e-a58d-41bdfc521e94
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 143e11ff966eb11961aa15073a503522c4b9c86b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748187"
---
# <a name="monitoring-performance-counters-with-the-script-task"></a><span data-ttu-id="7839b-102">Supervisar los contadores de rendimiento con la tarea Script</span><span class="sxs-lookup"><span data-stu-id="7839b-102">Monitoring Performance Counters with the Script Task</span></span>
  <span data-ttu-id="7839b-103">Los administradores quizá tengan que supervisar el rendimiento de los paquetes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que realizan transformaciones complejas en grandes volúmenes de datos.</span><span class="sxs-lookup"><span data-stu-id="7839b-103">Administrators may need to monitor the performance of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages that perform complex transformations on large amounts of data.</span></span> <span data-ttu-id="7839b-104">El espacio de nombres **System.Diagnostics** de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] proporciona las clases para utilizar los contadores de rendimiento existentes y para crear sus propios contadores de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="7839b-104">The **System.Diagnostics** namespace of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] provides classes for using existing performance counters and for creating your own performance counters.</span></span>  
  
 <span data-ttu-id="7839b-105">Los contadores de rendimiento almacenan información sobre el rendimiento de la aplicación que puede utilizar para analizar el rendimiento del software a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="7839b-105">Performance counters store application performance information that you can use to analyze the performance of software over time.</span></span> <span data-ttu-id="7839b-106">Los contadores de rendimiento se pueden supervisar de forma local o remota mediante la herramienta **Monitor de rendimiento**.</span><span class="sxs-lookup"><span data-stu-id="7839b-106">Performance counters can be monitored locally or remotely by using the **Performance Monitor** tool.</span></span> <span data-ttu-id="7839b-107">Puede almacenar los valores de los contadores de rendimiento en variables para la bifurcación del flujo de control posterior en el paquete.</span><span class="sxs-lookup"><span data-stu-id="7839b-107">You can store the values of performance counters in variables for later control flow branching in the package.</span></span>  
  
 <span data-ttu-id="7839b-108">Como una alternativa a utilizar los contadores de rendimiento, puede provocar el evento <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireProgress%2A> a través de la propiedad <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A> del objeto `Dts`.</span><span class="sxs-lookup"><span data-stu-id="7839b-108">As an alternative to using performance counters, you can raise the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireProgress%2A> event through the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A> property of the `Dts` object.</span></span> <span data-ttu-id="7839b-109">El evento <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireProgress%2A> devuelve el progreso incremental e información del porcentaje completado al módulo ejecutable de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7839b-109">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireProgress%2A> event returns both incremental progress and percentage complete information to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] runtime.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7839b-110">Si desea crear una tarea que pueda reutilizar más fácilmente en varios paquetes, considere la posibilidad de utilizar el código de este ejemplo de tarea Script como punto inicial de una tarea personalizada.</span><span class="sxs-lookup"><span data-stu-id="7839b-110">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="7839b-111">Para más información, vea [Desarrollar una tarea personalizada](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="7839b-111">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="description"></a><span data-ttu-id="7839b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="7839b-112">Description</span></span>  
 <span data-ttu-id="7839b-113">En el ejemplo siguiente se crea un contador de rendimiento personalizado y se incrementa el contador.</span><span class="sxs-lookup"><span data-stu-id="7839b-113">The following example creates a custom performance counter and increments the counter.</span></span> <span data-ttu-id="7839b-114">Primero, el ejemplo determina si el contador de rendimiento ya existe.</span><span class="sxs-lookup"><span data-stu-id="7839b-114">First, the example determines whether the performance counter already exists.</span></span> <span data-ttu-id="7839b-115">Si no se ha creado el contador de rendimiento, el script llama al método `Create` del objeto `PerformanceCounterCategory` para crearlo.</span><span class="sxs-lookup"><span data-stu-id="7839b-115">If the performance counter has not been created, the script calls the `Create` method of the `PerformanceCounterCategory` object to create it.</span></span> <span data-ttu-id="7839b-116">Una vez creado el contador de rendimiento, el script incrementa el contador.</span><span class="sxs-lookup"><span data-stu-id="7839b-116">After the performance counter has been created, the script increments the counter.</span></span> <span data-ttu-id="7839b-117">Finalmente, el ejemplo sigue la práctica recomendada de llamar al método `Close` en el contador de rendimiento cuando ya no se necesita.</span><span class="sxs-lookup"><span data-stu-id="7839b-117">Finally, the example follows the best practice of calling the `Close` method on the performance counter when it is no longer needed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7839b-118">Crear una nueva categoría de contador de rendimiento y el contador de rendimiento requiere derechos administrativos.</span><span class="sxs-lookup"><span data-stu-id="7839b-118">Creating a new performance counter category and performance counter requires administrative rights.</span></span> <span data-ttu-id="7839b-119">Además, la nueva categoría y el contador se conservan en el equipo después de la creación.</span><span class="sxs-lookup"><span data-stu-id="7839b-119">Also, the new category and counter persist on the computer after creation.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="7839b-120">Para configurar este ejemplo de tarea Script</span><span class="sxs-lookup"><span data-stu-id="7839b-120">To configure this Script Task example</span></span>  
  
-   <span data-ttu-id="7839b-121">Use una `Imports` instrucción en el código para importar el espacio de nombres **System. Diagnostics** .</span><span class="sxs-lookup"><span data-stu-id="7839b-121">Use an `Imports` statement in your code to import the **System.Diagnostics** namespace.</span></span>  
  
### <a name="example-code"></a><span data-ttu-id="7839b-122">Código de ejemplo</span><span class="sxs-lookup"><span data-stu-id="7839b-122">Example Code</span></span>  
  
```vb  
Public Sub Main()  
  
    Dim myCounter As PerformanceCounter  
  
    Try  
        'Create the performance counter if it does not already exist.  
        If Not _  
        PerformanceCounterCategory.Exists("TaskExample") Then  
            PerformanceCounterCategory.Create("TaskExample", _  
                "Task Performance Counter Example", "Iterations", _  
                "Number of times this task has been called.")  
        End If  
  
        'Initialize the performance counter.  
        myCounter = New PerformanceCounter("TaskExample", _  
            "Iterations", String.Empty, False)  
  
        'Increment the performance counter.  
        myCounter.Increment()  
  
         myCounter.Close()  
        Dts.TaskResult = ScriptResults.Success  
    Catch ex As Exception  
        Dts.Events.FireError(0, _  
            "Task Performance Counter Example", _  
            ex.Message & ControlChars.CrLf & ex.StackTrace, _  
            String.Empty, 0)  
        Dts.TaskResult = ScriptResults.Failure  
    End Try  
  
End Sub  
```  
  
```csharp  
  
public class ScriptMain  
{  
  
public void Main()  
        {  
  
            PerformanceCounter myCounter;  
  
            try  
            {  
                //Create the performance counter if it does not already exist.  
                if (!PerformanceCounterCategory.Exists("TaskExample"))  
                {  
                    PerformanceCounterCategory.Create("TaskExample", "Task Performance Counter Example", "Iterations", "Number of times this task has been called.");  
                }  
  
                //Initialize the performance counter.  
                myCounter = new PerformanceCounter("TaskExample", "Iterations", String.Empty, false);  
  
                //Increment the performance counter.  
                myCounter.Increment();  
  
                myCounter.Close();  
                Dts.TaskResult = (int)ScriptResults.Success;  
            }  
            catch (Exception ex)  
            {  
                Dts.Events.FireError(0, "Task Performance Counter Example", ex.Message + "\r" + ex.StackTrace, String.Empty, 0);  
                Dts.TaskResult = (int)ScriptResults.Failure;  
            }  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
        }  
  
```  
  
<span data-ttu-id="7839b-123">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="7839b-123">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="7839b-124">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="7839b-124">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="7839b-125">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="7839b-125">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="7839b-126">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="7839b-126">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
