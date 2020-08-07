---
title: Enviar a una cola de mensajes privada remota con la tarea Script | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script task [Integration Services], remote private message queues
- Message Queue task [Integration Services]
- Script task [Integration Services], examples
ms.assetid: 636314fd-d099-45cd-8bb4-f730d0a06739
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 308815293dfc41f0a0ac60c21ce7f561a5e7f660
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746326"
---
# <a name="sending-to-a-remote-private-message-queue-with-the-script-task"></a><span data-ttu-id="15dac-102">Enviar a una cola de mensajes privada remota con la tarea Script</span><span class="sxs-lookup"><span data-stu-id="15dac-102">Sending to a Remote Private Message Queue with the Script Task</span></span>
  <span data-ttu-id="15dac-103">Message Queue Server (también conocido como MSMQ) facilita a los desarrolladores la comunicación rápida y confiable con los programas de aplicación mediante el envío y la recepción de mensajes.</span><span class="sxs-lookup"><span data-stu-id="15dac-103">Message Queuing (also known as MSMQ) makes it easy for developers to communicate with application programs quickly and reliably by sending and receiving messages.</span></span> <span data-ttu-id="15dac-104">Una cola de mensajes se puede encontrar en el equipo local o en un equipo remoto y puede ser pública o privada.</span><span class="sxs-lookup"><span data-stu-id="15dac-104">A message queue may be located on the local computer or a remote computer, and may be public or private.</span></span> <span data-ttu-id="15dac-105">En [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], el administrador de conexiones MSMQ y la tarea Cola de mensajes no admiten el envío a una cola privada en un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="15dac-105">In [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], the MSMQ connection manager and Message Queue task do not support sending to a private queue on a remote computer.</span></span> <span data-ttu-id="15dac-106">Sin embargo, si se utiliza la tarea Script, resulta sencillo enviar un mensaje a una cola privada remota.</span><span class="sxs-lookup"><span data-stu-id="15dac-106">However, by using the Script task, it is easy to send a message to a remote private queue.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="15dac-107">Si desea crear una tarea que pueda reutilizar más fácilmente en varios paquetes, considere la posibilidad de utilizar el código de este ejemplo de tarea Script como punto inicial de una tarea personalizada.</span><span class="sxs-lookup"><span data-stu-id="15dac-107">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="15dac-108">Para más información, vea [Desarrollar una tarea personalizada](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="15dac-108">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="description"></a><span data-ttu-id="15dac-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="15dac-109">Description</span></span>  
 <span data-ttu-id="15dac-110">En el ejemplo siguiente se utiliza un administrador de conexiones MSMQ existente, junto con objetos y métodos del espacio de nombres System.Messaging, para enviar el texto contenido en una variable de paquete a una cola de mensajes privada remota.</span><span class="sxs-lookup"><span data-stu-id="15dac-110">The following example uses an existing MSMQ connection manager, together with objects and methods from the System.Messaging namespace, to send the text contained in a package variable to a remote private message queue.</span></span> <span data-ttu-id="15dac-111">La llamada al método M:Microsoft.SqlServer.Dts.ManagedConnections.MSMQConn.AcquireConnection (System. Object) del administrador de conexiones MSMQ devuelve un objeto **MessageQueue** cuyo `Send` método lleva a cabo esta tarea.</span><span class="sxs-lookup"><span data-stu-id="15dac-111">The call to the M:Microsoft.SqlServer.Dts.ManagedConnections.MSMQConn.AcquireConnection(System.Object) method of the MSMQ connection manager returns a **MessageQueue** object whose `Send` method accomplishes this task.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="15dac-112">Para configurar este ejemplo de tarea Script</span><span class="sxs-lookup"><span data-stu-id="15dac-112">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="15dac-113">Cree un administrador de conexiones MSMQ con el nombre predeterminado.</span><span class="sxs-lookup"><span data-stu-id="15dac-113">Create an MSMQ connection manager with the default name.</span></span> <span data-ttu-id="15dac-114">Establezca la ruta de acceso de una cola privada remota válida, con el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="15dac-114">Set the path of a valid remote private queue, in the following format:</span></span>  
  
    ```  
    FORMATNAME:DIRECT=OS:<computername>\private$\<queuename>  
    ```  
  
2.  <span data-ttu-id="15dac-115">Cree una [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] variable denominada **MessageText** de tipo `String` para pasar el texto del mensaje al script.</span><span class="sxs-lookup"><span data-stu-id="15dac-115">Create an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] variable named **MessageText** of type `String` to pass the message text into the script.</span></span> <span data-ttu-id="15dac-116">Escriba un mensaje predeterminado como valor de la variable.</span><span class="sxs-lookup"><span data-stu-id="15dac-116">Enter a default message as the value of the variable.</span></span>  
  
3.  <span data-ttu-id="15dac-117">Agregue una tarea Script a la superficie de diseño y modifíquela.</span><span class="sxs-lookup"><span data-stu-id="15dac-117">Add a Script Task to the design surface and edit it.</span></span> <span data-ttu-id="15dac-118">En la pestaña **Script** del **Editor de la tarea Script**, agregue la variable `MessageText` a la propiedad **ReadOnlyVariables** para que la variable esté disponible dentro del script.</span><span class="sxs-lookup"><span data-stu-id="15dac-118">On the **Script** tab of the **Script Task Editor**, add the `MessageText` variable to the **ReadOnlyVariables** property to make the variable available inside the script.</span></span>  
  
4.  <span data-ttu-id="15dac-119">Haga clic en **Editar script** para abrir el editor de script de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span><span class="sxs-lookup"><span data-stu-id="15dac-119">Click **Edit Script** to open the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) script editor.</span></span>  
  
5.  <span data-ttu-id="15dac-120">En el proyecto de script, agregue una referencia al espacio de nombres `System.Messaging`.</span><span class="sxs-lookup"><span data-stu-id="15dac-120">Add a reference in the script project to the `System.Messaging` namespace.</span></span>  
  
6.  <span data-ttu-id="15dac-121">Reemplace el contenido de la ventana de script con el código de la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="15dac-121">Replace the contents of the script window with the code in the following section.</span></span>  
  
## <a name="code"></a><span data-ttu-id="15dac-122">Código</span><span class="sxs-lookup"><span data-stu-id="15dac-122">Code</span></span>  
  
```vb  
Imports System  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports System.Messaging  
  
Public Class ScriptMain  
  
    Public Sub Main()  
  
        Dim remotePrivateQueue As MessageQueue  
        Dim messageText As String  
  
        remotePrivateQueue = _  
            DirectCast(Dts.Connections("Message Queue Connection Manager").AcquireConnection(Dts.Transaction), _  
            MessageQueue)  
        messageText = DirectCast(Dts.Variables("MessageText").Value, String)  
        remotePrivateQueue.Send(messageText)  
  
        Dts.TaskResult = ScriptResults.Success  
  
    End Sub  
  
End Class  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
using System.Messaging;  
  
public class ScriptMain  
{  
  
    public void Main()  
        {  
  
            MessageQueue remotePrivateQueue = new MessageQueue();  
            string messageText;  
  
            remotePrivateQueue = (MessageQueue)(Dts.Connections["Message Queue Connection Manager"].AcquireConnection(Dts.Transaction) as MessageQueue);  
            messageText = (string)(Dts.Variables["MessageText"].Value);  
            remotePrivateQueue.Send(messageText);  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
  
        }  
  
}  
```  
  
<span data-ttu-id="15dac-123">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="15dac-123">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="15dac-124">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="15dac-124">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="15dac-125">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="15dac-125">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="15dac-126">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="15dac-126">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15dac-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="15dac-127">See Also</span></span>  
 [<span data-ttu-id="15dac-128">Tarea Cola de mensajes</span><span class="sxs-lookup"><span data-stu-id="15dac-128">Message Queue Task</span></span>](../control-flow/message-queue-task.md)  
  
  
