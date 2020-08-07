---
title: Provocar eventos en la tarea Script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- events [Integration Services], scripts
- warnings [Integration Services]
- SSIS events, scripts
- errors [Integration Services], events
- SSIS Script task, events
- Events property
- Script task [Integration Services], events
ms.assetid: 21ea07d1-e267-4fb1-a6cc-82c95a39beae
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e20a276b91e434b6915cfb218eba17c07acd6544
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745905"
---
# <a name="raising-events-in-the-script-task"></a><span data-ttu-id="8efc6-102">Provocar eventos en la tarea Script</span><span class="sxs-lookup"><span data-stu-id="8efc6-102">Raising Events in the Script Task</span></span>
  <span data-ttu-id="8efc6-103">Los eventos proporcionan una manera de notificar errores, advertencias y otra información, como el progreso o el estado de una tarea, al paquete contenedor.</span><span class="sxs-lookup"><span data-stu-id="8efc6-103">Events provide a way to report errors, warnings, and other information, such as task progress or status, to the containing package.</span></span> <span data-ttu-id="8efc6-104">El paquete proporciona controladores de eventos para administrar las notificaciones de eventos.</span><span class="sxs-lookup"><span data-stu-id="8efc6-104">The package provides event handlers for managing event notifications.</span></span> <span data-ttu-id="8efc6-105">La tarea Script puede provocar los eventos mediante una llamada a los métodos en la propiedad <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A> del objeto `Dts`.</span><span class="sxs-lookup"><span data-stu-id="8efc6-105">The Script task can raise events by calling methods on the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A> property of the `Dts` object.</span></span> <span data-ttu-id="8efc6-106">Para obtener más información sobre la manera en que los paquetes [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] controlan los eventos, vea [Controladores de eventos de Integration Services &#40;SSIS&#41;](../../integration-services-ssis-event-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="8efc6-106">For more information about how [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] packages handle events, see [Integration Services &#40;SSIS&#41; Event Handlers](../../integration-services-ssis-event-handlers.md).</span></span>  
  
 <span data-ttu-id="8efc6-107">Los eventos se pueden registrar en cualquier proveedor de registro habilitado en el paquete.</span><span class="sxs-lookup"><span data-stu-id="8efc6-107">Events can be logged to any log provider that is enabled in the package.</span></span> <span data-ttu-id="8efc6-108">Los proveedores de registro almacenan información sobre los eventos en un almacén de datos.</span><span class="sxs-lookup"><span data-stu-id="8efc6-108">Log providers store information about events in a data store.</span></span> <span data-ttu-id="8efc6-109">La tarea Script también puede utilizar el método <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A> para registrar información en un proveedor de registro sin provocar un evento.</span><span class="sxs-lookup"><span data-stu-id="8efc6-109">The Script task can also use the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A> method to log information to a log provider without raising an event.</span></span> <span data-ttu-id="8efc6-110">Para obtener más información acerca de cómo usar el método <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A>, vea [Registrar en la tarea Script](logging-in-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="8efc6-110">For more information about how to use the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A> method, see [Logging in the Script Task](logging-in-the-script-task.md).</span></span>  
  
 <span data-ttu-id="8efc6-111">Para provocar un evento, la tarea Script llama a uno de los métodos expuesto por la propiedad <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A>.</span><span class="sxs-lookup"><span data-stu-id="8efc6-111">To raise an event, the Script task calls one of the methods exposed by the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A> property.</span></span> <span data-ttu-id="8efc6-112">En la tabla siguiente se enumeran los métodos que expone la propiedad <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A>.</span><span class="sxs-lookup"><span data-stu-id="8efc6-112">The following table lists the methods exposed by the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A> property.</span></span>  
  
|<span data-ttu-id="8efc6-113">Evento</span><span class="sxs-lookup"><span data-stu-id="8efc6-113">Event</span></span>|<span data-ttu-id="8efc6-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="8efc6-114">Description</span></span>|  
|-----------|-----------------|  
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireCustomEvent%2A>|<span data-ttu-id="8efc6-115">Provoca un evento personalizado definido por el usuario en el paquete.</span><span class="sxs-lookup"><span data-stu-id="8efc6-115">Raises a user-defined custom event in the package.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireError%2A>|<span data-ttu-id="8efc6-116">Informa al paquete de una condición de error.</span><span class="sxs-lookup"><span data-stu-id="8efc6-116">Informs the package of an error condition.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireInformation%2A>|<span data-ttu-id="8efc6-117">Proporciona información al usuario.</span><span class="sxs-lookup"><span data-stu-id="8efc6-117">Provides information to the user.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireProgress%2A>|<span data-ttu-id="8efc6-118">Informa al paquete del progreso de la tarea.</span><span class="sxs-lookup"><span data-stu-id="8efc6-118">Informs the package of the progress of the task.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireQueryCancel%2A>|<span data-ttu-id="8efc6-119">Devuelve un valor que indica si el paquete necesita que la tarea se cierre prematuramente.</span><span class="sxs-lookup"><span data-stu-id="8efc6-119">Returns a value that indicates whether the package needs the task to shut down prematurely.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireWarning%2A>|<span data-ttu-id="8efc6-120">Informa al paquete de que la tarea está en un estado que garantiza la notificación del usuario, pero no es una condición de error.</span><span class="sxs-lookup"><span data-stu-id="8efc6-120">Informs the package that the task is in a state that warrants user notification, but is not an error condition.</span></span>|  
  
## <a name="events-example"></a><span data-ttu-id="8efc6-121">Ejemplo de eventos</span><span class="sxs-lookup"><span data-stu-id="8efc6-121">Events Example</span></span>  
 <span data-ttu-id="8efc6-122">En el ejemplo siguiente se muestra cómo provocar eventos desde la tarea Script.</span><span class="sxs-lookup"><span data-stu-id="8efc6-122">The following example demonstrates how to raise events from within the Script task.</span></span> <span data-ttu-id="8efc6-123">El ejemplo utiliza una función nativa de la API de Windows para determinar si está disponible una conexión a Internet.</span><span class="sxs-lookup"><span data-stu-id="8efc6-123">The example uses a native Windows API function to determine whether an Internet connection is available.</span></span> <span data-ttu-id="8efc6-124">Si no hay ninguna conexión disponible, provoca un error.</span><span class="sxs-lookup"><span data-stu-id="8efc6-124">If no connection is available, it raises an error.</span></span> <span data-ttu-id="8efc6-125">Si se utiliza una conexión de módem potencialmente volátil, el ejemplo provoca una advertencia.</span><span class="sxs-lookup"><span data-stu-id="8efc6-125">If a potentially volatile modem connection is in use, the example raises a warning.</span></span> <span data-ttu-id="8efc6-126">De lo contrario, devuelve un mensaje informativo que indica que se ha detectado una conexión a Internet.</span><span class="sxs-lookup"><span data-stu-id="8efc6-126">Otherwise, it returns an informational message that an Internet connection has been detected.</span></span>  
  
```vb  
Private Declare Function InternetGetConnectedState Lib "wininet" _  
    (ByRef dwFlags As Long, ByVal dwReserved As Long) As Long  
  
Private Enum ConnectedStates  
    LAN = &H2  
    Modem = &H1  
    Proxy = &H4  
    Offline = &H20  
    Configured = &H40  
    RasInstalled = &H10  
End Enum  
  
Public Sub Main()  
  
    Dim dwFlags As Long  
    Dim connectedState As Long  
    Dim fireAgain as Boolean  
  
    connectedState = InternetGetConnectedState(dwFlags, 0)  
  
    If connectedState <> 0 Then  
        If (dwFlags And ConnectedStates.Modem) = ConnectedStates.Modem Then  
            Dts.Events.FireWarning(0, "Script Task Example", _  
                "Volatile Internet connection detected.", String.Empty, 0)  
        Else  
            Dts.Events.FireInformation(0, "Script Task Example", _  
                "Internet connection detected.", String.Empty, 0, fireAgain)  
        End If  
    Else  
        ' If not connected to the Internet, raise an error.  
        Dts.Events.FireError(0, "Script Task Example", _  
            "Internet connection not available.", String.Empty, 0)  
    End If  
  
    Dts.TaskResult = ScriptResults.Success  
  
End Sub  
```  
  
```csharp  
using System;  
using System.Data;  
using Microsoft.SqlServer.Dts.Runtime;  
using System.Windows.Forms;  
using System.Runtime.InteropServices;  
  
public class ScriptMain  
{  
  
[DllImport("wininet")]  
        private extern static long InternetGetConnectedState(ref long dwFlags, long dwReserved);  
  
        private enum ConnectedStates  
        {  
            LAN = 0x2,  
            Modem = 0x1,  
            Proxy = 0x4,  
            Offline = 0x20,  
            Configured = 0x40,  
            RasInstalled = 0x10  
        };  
  
        public void Main()  
        {  
            //  
            long dwFlags = 0;  
            long connectedState;  
            bool fireAgain = true;  
            int state;  
  
            connectedState = InternetGetConnectedState(ref dwFlags, 0);  
            state = (int)ConnectedStates.Modem;  
            if (connectedState != 0)  
            {  
                if ((dwFlags & state) == state)  
                {  
                    Dts.Events.FireWarning(0, "Script Task Example", "Volatile Internet connection detected.", String.Empty, 0);  
                }  
                else  
                {  
                    Dts.Events.FireInformation(0, "Script Task Example", "Internet connection detected.", String.Empty, 0, ref fireAgain);  
                }  
            }  
            else  
            {  
                // If not connected to the Internet, raise an error.  
                Dts.Events.FireError(0, "Script Task Example", "Internet connection not available.", String.Empty, 0);  
            }  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
  
        }  
  
```  
  
<span data-ttu-id="8efc6-127">![Integration Services icono (pequeño)](../../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="8efc6-127">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="8efc6-128">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="8efc6-128">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="8efc6-129">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="8efc6-129">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="8efc6-130">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="8efc6-130">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8efc6-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8efc6-131">See Also</span></span>  
 <span data-ttu-id="8efc6-132">[Controladores de eventos de Integration Services &#40;SSIS&#41;](../../integration-services-ssis-event-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="8efc6-132">[Integration Services &#40;SSIS&#41; Event Handlers](../../integration-services-ssis-event-handlers.md) </span></span>  
 [<span data-ttu-id="8efc6-133">Agregar un controlador de eventos a un paquete</span><span class="sxs-lookup"><span data-stu-id="8efc6-133">Add an Event Handler to a Package</span></span>](../../add-an-event-handler-to-a-package.md)  
  
  
