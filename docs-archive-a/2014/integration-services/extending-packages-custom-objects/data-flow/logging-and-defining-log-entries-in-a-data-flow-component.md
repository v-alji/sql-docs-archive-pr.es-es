---
title: Registrar y definir entradas de registro en un componente de flujo de datos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- logs [Integration Services], custom
- custom log entries [Integration Services]
- custom data flow components [Integration Services], logging
- data flow components [Integration Services], logging
ms.assetid: 2190dba9-59b5-480b-b8e9-21d5a54c5917
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 14dfec71679bbe455ae8be5face98b776a80b9e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744778"
---
# <a name="logging-and-defining-log-entries-in-a-data-flow-component"></a><span data-ttu-id="e17e6-102">Registrar y definir entradas de registro en un componente de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="e17e6-102">Logging and Defining Log Entries in a Data Flow Component</span></span>
  <span data-ttu-id="e17e6-103">Los componentes de flujo de datos personalizados pueden publicar mensajes en una entrada de registro existente con el método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.PostLogMessage%2A> de la interfaz <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>.</span><span class="sxs-lookup"><span data-stu-id="e17e6-103">Custom data flow components can post messages to an existing log entry by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.PostLogMessage%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface.</span></span> <span data-ttu-id="e17e6-104">También pueden presentar información al usuario con el método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireInformation%2A> o métodos similares de la interfaz <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>.</span><span class="sxs-lookup"><span data-stu-id="e17e6-104">They can also present information to the user by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireInformation%2A> method or similar methods of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface.</span></span> <span data-ttu-id="e17e6-105">Sin embargo, este enfoque supone la sobrecarga de provocar y controlar eventos adicionales y obliga al usuario a buscar los mensajes que le pueden interesar entre todos los mensajes informativos detallados.</span><span class="sxs-lookup"><span data-stu-id="e17e6-105">However, this approach incurs the overhead of raising and handling additional events, and forces the user to sift through verbose informational messages for the messages that may be of interest to them.</span></span> <span data-ttu-id="e17e6-106">Puede utilizar una entrada de registro personalizada tal como se describe a continuación para proporcionar información de registro personalizada etiquetada de forma diferenciada a los usuarios del componente.</span><span class="sxs-lookup"><span data-stu-id="e17e6-106">You can use a custom log entry as described below to provide distinctly labeled custom log information to users of your component.</span></span>  
  
## <a name="registering-and-using-a-custom-log-entry"></a><span data-ttu-id="e17e6-107">Registrar y utilizar una entrada de registro personalizada</span><span class="sxs-lookup"><span data-stu-id="e17e6-107">Registering and Using a Custom Log Entry</span></span>  
  
### <a name="registering-a-custom-log-entry"></a><span data-ttu-id="e17e6-108">Registrar una entrada de registro personalizada</span><span class="sxs-lookup"><span data-stu-id="e17e6-108">Registering a Custom Log Entry</span></span>  
 <span data-ttu-id="e17e6-109">Para registrar una entrada de registro personalizada y que la utilice el componente, invalide el método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterLogEntries%2A> de la clase base <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent>.</span><span class="sxs-lookup"><span data-stu-id="e17e6-109">To register a custom log entry for use by your component, override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterLogEntries%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class.</span></span> <span data-ttu-id="e17e6-110">En el ejemplo siguiente se registra una entrada de registro personalizada y se proporciona un nombre y una descripción.</span><span class="sxs-lookup"><span data-stu-id="e17e6-110">The following example registers a custom log entry and provides a name and description.</span></span>  
  
```csharp  
using Microsoft.SqlServer.Dts.Runtime;  
...  
private const string MyLogEntryName = "My Custom Component Log Entry";  
private const string MyLogEntryDescription = "Log entry from My Custom Component ";  
...  
    public override void RegisterLogEntries()  
    {  
      this.LogEntryInfos.Add(MyLogEntryName,  
        MyLogEntryDescription,  
        Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_CONSISTENT);  
    }  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
...  
Private Const MyLogEntryName As String = "My Custom Component Log Entry"   
Private Const MyLogEntryDescription As String = "Log entry from My Custom Component "  
...  
Public  Overrides Sub RegisterLogEntries()   
  Me.LogEntryInfos.Add(MyLogEntryName, _  
    MyLogEntryDescription, _  
    Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_CONSISTENT)   
End Sub  
```  
  
 <span data-ttu-id="e17e6-111">La enumeración <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency> proporciona una sugerencia al motor en tiempo de ejecución sobre la frecuencia con que se registrará el evento:</span><span class="sxs-lookup"><span data-stu-id="e17e6-111">The <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency> enumeration provides a hint to the runtime about how frequently the event will be logged:</span></span>  
  
-   <span data-ttu-id="e17e6-112"><xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_OCCASIONAL>: el evento solamente se registra en ocasiones, no durante cada ejecución.</span><span class="sxs-lookup"><span data-stu-id="e17e6-112"><xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_OCCASIONAL>: Event is logged only sometimes, not during every execution.</span></span>  
  
-   <span data-ttu-id="e17e6-113"><xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_CONSISTENT>: el evento se registra un número constante de veces durante cada ejecución.</span><span class="sxs-lookup"><span data-stu-id="e17e6-113"><xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_CONSISTENT>: Event is logged a constant number of times during every execution.</span></span>  
  
-   <span data-ttu-id="e17e6-114"><xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_PROPORTIONAL>: el evento se registra un número de veces proporcional a la cantidad de trabajo completado.</span><span class="sxs-lookup"><span data-stu-id="e17e6-114"><xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_PROPORTIONAL>: Event is logged a number of times proportional to the amount of work completed.</span></span>  
  
 <span data-ttu-id="e17e6-115">En el ejemplo anterior se utiliza <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_CONSISTENT> porque el componente espera registrar una entrada una vez por ejecución.</span><span class="sxs-lookup"><span data-stu-id="e17e6-115">The example above uses <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_CONSISTENT> because the component expects to log an entry once per execution.</span></span>  
  
 <span data-ttu-id="e17e6-116">Después de registrar la entrada de registro personalizada y agregar una instancia del componente personalizado a la superficie del diseñador de flujo de datos, el cuadro de diálogo **Registro** del diseñador muestra una nueva entrada de registro con el nombre "My Custom Component Log Entry" en la lista de entradas de registro disponibles.</span><span class="sxs-lookup"><span data-stu-id="e17e6-116">After registering the custom log entry and adding an instance of your custom component to the data flow designer surface, the **Logging** dialog box in the designer displays a new log entry with the name "My Custom Component Log Entry" in the list of available log entries.</span></span>  
  
### <a name="logging-to-a-custom-log-entry"></a><span data-ttu-id="e17e6-117">Registrar en una entrada de registro personalizada</span><span class="sxs-lookup"><span data-stu-id="e17e6-117">Logging to a Custom Log Entry</span></span>  
 <span data-ttu-id="e17e6-118">Después de registrar la entrada de registro personalizada, el componente puede registrar los mensajes personalizados.</span><span class="sxs-lookup"><span data-stu-id="e17e6-118">After registering the custom log entry, the component can now log custom messages.</span></span> <span data-ttu-id="e17e6-119">En el ejemplo siguiente se escribe una entrada de registro personalizada durante el método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> que contiene el texto de una instrucción SQL que utiliza el componente.</span><span class="sxs-lookup"><span data-stu-id="e17e6-119">The example below writes a custom log entry during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> method that contains the text of a SQL statement used by the component.</span></span>  
  
```csharp  
public override void PreExecute()  
{  
  DateTime now = DateTime.Now;  
  byte[] additionalData = null;  
  this.ComponentMetaData.PostLogMessage(MyLogEntryName,  
    this.ComponentMetaData.Name,  
    "Command Sent was: " + myCommand.CommandText,  
    now, now, 0, ref additionalData);  
}  
```  
  
```vb  
Public  Overrides Sub PreExecute()   
  Dim now As DateTime = DateTime.Now   
  Dim additionalData As Byte() = Nothing   
  Me.ComponentMetaData.PostLogMessage(MyLogEntryName, _  
    Me.ComponentMetaData.Name, _  
    "Command Sent was: " + myCommand.CommandText, _  
    now, now, 0, additionalData)   
End Sub  
```  
  
 <span data-ttu-id="e17e6-120">Cuando el usuario ejecuta el paquete, después de seleccionar "My Custom Component Log Entry" en el cuadro de diálogo **Registro**, el registro contendrá una entrada claramente etiquetada como "User::My Custom Component Log Entry".</span><span class="sxs-lookup"><span data-stu-id="e17e6-120">Now when the user executes the package, after selecting the "My Custom Component Log Entry" in the **Logging** dialog box, the log will contain an entry clearly labeled as "User::My Custom Component Log Entry."</span></span> <span data-ttu-id="e17e6-121">Esta nueva entrada de registro contiene el texto de la instrucción SQL, la marca de tiempo y cualquier dato adicional registrado por el programador.</span><span class="sxs-lookup"><span data-stu-id="e17e6-121">This new log entry contains the text of the SQL statement, the timestamp, and any additional data logged by the developer.</span></span>  
  
<span data-ttu-id="e17e6-122">![Integration Services icono (pequeño)](../../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="e17e6-122">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="e17e6-123">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="e17e6-123">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="e17e6-124">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="e17e6-124">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="e17e6-125">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="e17e6-125">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e17e6-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e17e6-126">See Also</span></span>  
 [<span data-ttu-id="e17e6-127">Registro de Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="e17e6-127">Integration Services &#40;SSIS&#41; Logging</span></span>](../../performance/integration-services-ssis-logging.md)  
  
  
