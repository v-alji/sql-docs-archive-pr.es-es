---
title: Habilitar el registro mediante programación | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SQL Server Integration Services packages, logs
- SSIS packages, logs
- Integration Services packages, logs
- SSIS logging
- log providers [Integration Services]
- logs [Integration Services], enabling
- LoggingMode property
- LogProvider object
- packages [Integration Services], logs
ms.assetid: 3222a1ed-83eb-421c-b299-a53b67bba740
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ff7f81aca330960e4e94b0343080a37ded8c1273
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745946"
---
# <a name="enabling-logging-programmatically"></a><span data-ttu-id="8931a-102">Habilitar el registro mediante programación</span><span class="sxs-lookup"><span data-stu-id="8931a-102">Enabling Logging Programmatically</span></span>
  <span data-ttu-id="8931a-103">El motor en tiempo de ejecución proporciona una colección de objetos <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider> que permiten capturar información específica del evento durante la validación y ejecución de paquetes.</span><span class="sxs-lookup"><span data-stu-id="8931a-103">The run-time engine provides a collection of <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider> objects that enable event-specific information to be captured during package validation and execution.</span></span> <span data-ttu-id="8931a-104">Los objetos <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider> están disponibles para los objetos <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer>, incluidos los objetos <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, <xref:Microsoft.SqlServer.Dts.Runtime.Package>, <xref:Microsoft.SqlServer.Dts.Runtime.ForLoop> y <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop>.</span><span class="sxs-lookup"><span data-stu-id="8931a-104"><xref:Microsoft.SqlServer.Dts.Runtime.LogProvider> objects are available to <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer> objects, including the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, <xref:Microsoft.SqlServer.Dts.Runtime.Package>, <xref:Microsoft.SqlServer.Dts.Runtime.ForLoop>, and <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> objects.</span></span> <span data-ttu-id="8931a-105">El registro se habilita en contenedores individuales o en el paquete completo.</span><span class="sxs-lookup"><span data-stu-id="8931a-105">Logging is enabled on individual containers, or on the whole package.</span></span>

 <span data-ttu-id="8931a-106">Existen diferentes tipos de proveedores de registro disponibles para que los utilice un contenedor.</span><span class="sxs-lookup"><span data-stu-id="8931a-106">There are several types of log providers that are available for a container to use.</span></span> <span data-ttu-id="8931a-107">Esto proporciona la flexibilidad necesaria para crear y almacenar información del registro en distintos formatos.</span><span class="sxs-lookup"><span data-stu-id="8931a-107">This provides the flexibility to create and store log information in many formats.</span></span> <span data-ttu-id="8931a-108">Dar de alta un objeto contenedor en el registro es un proceso de dos pasos: en primer lugar se habilita el registro y, a continuación, se selecciona un proveedor de registro.</span><span class="sxs-lookup"><span data-stu-id="8931a-108">Enlisting a container object in logging is a two-step process: first logging is enabled, and then a log provider is selected.</span></span> <span data-ttu-id="8931a-109">Las propiedades <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingOptions%2A> y <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingMode%2A> del contenedor se utilizan para especificar los eventos registrados y seleccionar el proveedor de registro.</span><span class="sxs-lookup"><span data-stu-id="8931a-109">The <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingOptions%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingMode%2A> properties of the container are used to specify the logged events and to select the log provider.</span></span>

## <a name="enabling-logging"></a><span data-ttu-id="8931a-110">Habilitar el registro</span><span class="sxs-lookup"><span data-stu-id="8931a-110">Enabling Logging</span></span>
 <span data-ttu-id="8931a-111">La propiedad <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingMode%2A>, incluida en cada contenedor que puede realizar el registro, determina si la información de evento del contenedor se registra en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="8931a-111">The <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingMode%2A> property, found in each container that can perform logging, determines whether the container's event information is recorded to the event log.</span></span> <span data-ttu-id="8931a-112">El valor de esta propiedad se asigna desde la estructura <xref:Microsoft.SqlServer.Dts.Runtime.DTSLoggingMode> y se hereda de forma predeterminada del elemento primario del contenedor.</span><span class="sxs-lookup"><span data-stu-id="8931a-112">This property is assigned a value from the <xref:Microsoft.SqlServer.Dts.Runtime.DTSLoggingMode> structure, and is inherited from the container's parent by default.</span></span> <span data-ttu-id="8931a-113">Si el contenedor es un paquete, y por tanto no dispone de elemento primario, la propiedad utiliza <xref:Microsoft.SqlServer.Dts.Runtime.DTSLoggingMode.UseParentSetting>, que tiene como valor predeterminado `Disabled`.</span><span class="sxs-lookup"><span data-stu-id="8931a-113">If the container is a package, and therefore has no parent, the property uses the <xref:Microsoft.SqlServer.Dts.Runtime.DTSLoggingMode.UseParentSetting>, which defaults to `Disabled`.</span></span>

### <a name="selecting-a-log-provider"></a><span data-ttu-id="8931a-114">Seleccionar un proveedor de registro</span><span class="sxs-lookup"><span data-stu-id="8931a-114">Selecting a Log Provider</span></span>
 <span data-ttu-id="8931a-115">Una vez establecida la propiedad <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingMode%2A> en `Enabled`, se agrega un proveedor de registro a la colección <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders> del contenedor para completar el proceso.</span><span class="sxs-lookup"><span data-stu-id="8931a-115">After the <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingMode%2A> property is set to `Enabled`, a log provider is added to the <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders> collection of the container to complete the process.</span></span> <span data-ttu-id="8931a-116">La colección <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders> está disponible en el objeto <xref:Microsoft.SqlServer.Dts.Runtime.LoggingOptions> y contiene los proveedores de registro seleccionados para el contenedor.</span><span class="sxs-lookup"><span data-stu-id="8931a-116">The <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders> collection is available on the <xref:Microsoft.SqlServer.Dts.Runtime.LoggingOptions> object, and contains the log providers selected for the container.</span></span> <span data-ttu-id="8931a-117">Se llama al método <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders.Add%2A> para crear un proveedor y agregarlo a la colección.</span><span class="sxs-lookup"><span data-stu-id="8931a-117">The <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders.Add%2A> method is called to create a provider and add it to the collection.</span></span> <span data-ttu-id="8931a-118">El método devuelve el proveedor de registro que se agregó a la colección.</span><span class="sxs-lookup"><span data-stu-id="8931a-118">The method then returns the log provider that was added to the collection.</span></span> <span data-ttu-id="8931a-119">Cada proveedor incluye configuración única para dicho proveedor; estas propiedades se establecen mediante la propiedad <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider.ConfigString%2A>.</span><span class="sxs-lookup"><span data-stu-id="8931a-119">Each provider has configuration settings that are unique to that provider, and these properties are set using the <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider.ConfigString%2A> property.</span></span>

 <span data-ttu-id="8931a-120">En la tabla siguiente se enumeran los proveedores de registro disponibles, su descripción y su información <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider.ConfigString%2A>.</span><span class="sxs-lookup"><span data-stu-id="8931a-120">The following table lists the available log providers, their description, and their <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider.ConfigString%2A> information.</span></span>

|<span data-ttu-id="8931a-121">Proveedor</span><span class="sxs-lookup"><span data-stu-id="8931a-121">Provider</span></span>|<span data-ttu-id="8931a-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="8931a-122">Description</span></span>|<span data-ttu-id="8931a-123">Propiedad ConfigString</span><span class="sxs-lookup"><span data-stu-id="8931a-123">ConfigString property</span></span>|
|--------------|-----------------|---------------------------|
|<span data-ttu-id="8931a-124">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="8931a-124">SQL Server Profiler</span></span>|<span data-ttu-id="8931a-125">Genera archivos de Seguimiento de SQL que se pueden capturar y ver en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Profiler.</span><span class="sxs-lookup"><span data-stu-id="8931a-125">Generates SQL traces that may be captured and viewed in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Profiler.</span></span> <span data-ttu-id="8931a-126">La extensión predeterminada de los nombres de archivo de este proveedor es .trc.</span><span class="sxs-lookup"><span data-stu-id="8931a-126">The default file name extension for this provider is .trc.</span></span>|<span data-ttu-id="8931a-127">No se requiere ninguna configuración.</span><span class="sxs-lookup"><span data-stu-id="8931a-127">No configuration is required.</span></span>|
|<span data-ttu-id="8931a-128">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8931a-128">SQL Server</span></span>|<span data-ttu-id="8931a-129">Escribe las entradas del registro de eventos en la tabla **sysssislog** de cualquier base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8931a-129">Writes event log entries to the **sysssislog** table in any [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>|<span data-ttu-id="8931a-130">El proveedor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] requiere que se especifique la conexión a la base de datos y el nombre de la base de datos de destino.</span><span class="sxs-lookup"><span data-stu-id="8931a-130">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider requires that the connection to the database be specified, and also the target database name.</span></span>|
|<span data-ttu-id="8931a-131">Archivo de texto</span><span class="sxs-lookup"><span data-stu-id="8931a-131">Text File</span></span>|<span data-ttu-id="8931a-132">Escribe las entradas de registro de eventos en archivos de texto ASCII con un formato de valores separados por comas (CSV).</span><span class="sxs-lookup"><span data-stu-id="8931a-132">Writes event log entries to ASCII text files in a comma-separated value (CSV) format.</span></span> <span data-ttu-id="8931a-133">La extensión predeterminada de los nombres de archivo de este proveedor es .log.</span><span class="sxs-lookup"><span data-stu-id="8931a-133">The default file name extension for this provider is .log.</span></span>|<span data-ttu-id="8931a-134">El nombre de un administrador de conexión de archivos.</span><span class="sxs-lookup"><span data-stu-id="8931a-134">The name of a file connection manager.</span></span>|
|<span data-ttu-id="8931a-135">Registro de eventos de Windows</span><span class="sxs-lookup"><span data-stu-id="8931a-135">Windows Event Log</span></span>|<span data-ttu-id="8931a-136">Escribe las entradas en el registro de eventos estándar de Windows en el equipo local, en el registro de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="8931a-136">Logs to standard Windows Event Log on the local computer in the Application log.</span></span>|<span data-ttu-id="8931a-137">No se requiere ninguna configuración.</span><span class="sxs-lookup"><span data-stu-id="8931a-137">No configuration is required.</span></span>|
|<span data-ttu-id="8931a-138">Archivo XML</span><span class="sxs-lookup"><span data-stu-id="8931a-138">XML File</span></span>|<span data-ttu-id="8931a-139">Escribe las entradas del registro de eventos en archivos con formato XML.</span><span class="sxs-lookup"><span data-stu-id="8931a-139">Writes event log entries to XML formatted file.</span></span> <span data-ttu-id="8931a-140">La extensión predeterminada de los nombres de archivo de este proveedor es .xml.</span><span class="sxs-lookup"><span data-stu-id="8931a-140">The default file name extension for this provider is .xml</span></span>|<span data-ttu-id="8931a-141">El nombre de un administrador de conexión de archivos.</span><span class="sxs-lookup"><span data-stu-id="8931a-141">The name of a file connection manager.</span></span>|

 <span data-ttu-id="8931a-142">Los eventos se incluyen en o excluyen del registro de eventos mediante las propiedades `EventFilterKind` y `EventFilter` del contenedor.</span><span class="sxs-lookup"><span data-stu-id="8931a-142">Events are included in or excluded from the event log by setting the `EventFilterKind` and the `EventFilter` properties of the container.</span></span> <span data-ttu-id="8931a-143">La estructura `EventFilterKind` contiene dos valores, `ExclusionFilter` e `InclusionFilter`, que indican si los eventos que se agregan a `EventFilter` se incluyen en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="8931a-143">The `EventFilterKind` structure contains two values, `ExclusionFilter` and `InclusionFilter`, that indicate whether the events that are added to the `EventFilter` are included in the event log.</span></span> <span data-ttu-id="8931a-144">A continuación se asigna una matriz de cadenas que contiene los nombres de los eventos sujetos del filtrado a la propiedad `EventFilter`.</span><span class="sxs-lookup"><span data-stu-id="8931a-144">The `EventFilter` property is then assigned a string array that contains the names of the events that are the subject of the filtering.</span></span>

 <span data-ttu-id="8931a-145">El código siguiente habilita el registro en un paquete, agrega el proveedor de registro para archivos de texto a la colección <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders> y especifica una lista de eventos para incluir en la salida del registro.</span><span class="sxs-lookup"><span data-stu-id="8931a-145">The following code enables logging on a package, adds the log provider for Text files to the <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders> collection, and specifies a list of events to include in the logging output.</span></span>

## <a name="sample"></a><span data-ttu-id="8931a-146">Muestra</span><span class="sxs-lookup"><span data-stu-id="8931a-146">Sample</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Runtime;

namespace Microsoft.SqlServer.Dts.Samples
{
  class Program
  {
    static void Main(string[] args)
    {
      Package p = new Package();

      ConnectionManager loggingConnection = p.Connections.Add("FILE");
      loggingConnection.ConnectionString = @"C:\SSISPackageLog.txt";

      LogProvider provider = p.LogProviders.Add("DTS.LogProviderTextFile.2");
      provider.ConfigString = loggingConnection.Name;
      p.LoggingOptions.SelectedLogProviders.Add(provider);
      p.LoggingOptions.EventFilterKind = DTSEventFilterKind.Inclusion;
      p.LoggingOptions.EventFilter = new String[] { "OnPreExecute", 
         "OnPostExecute", "OnError", "OnWarning", "OnInformation" };
      p.LoggingMode = DTSLoggingMode.Enabled;

      // Add tasks and other objects to the package.

    }
  }
}
```

```vb
Imports Microsoft.SqlServer.Dts.Runtime

Module Module1

  Sub Main()

    Dim p As Package = New Package()

    Dim loggingConnection As ConnectionManager = p.Connections.Add("FILE")
    loggingConnection.ConnectionString = "C:\SSISPackageLog.txt"

    Dim provider As LogProvider = p.LogProviders.Add("DTS.LogProviderTextFile.2")
    provider.ConfigString = loggingConnection.Name
    p.LoggingOptions.SelectedLogProviders.Add(provider)
    p.LoggingOptions.EventFilterKind = DTSEventFilterKind.Inclusion
    p.LoggingOptions.EventFilter = New String() {"OnPreExecute", _
       "OnPostExecute", "OnError", "OnWarning", "OnInformation"}
    p.LoggingMode = DTSLoggingMode.Enabled

    ' Add tasks and other objects to the package.

  End Sub

End Module
```

<span data-ttu-id="8931a-147">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="8931a-147">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="8931a-148">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="8931a-148">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="8931a-149">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="8931a-149">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="8931a-150">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="8931a-150">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="8931a-151">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8931a-151">See Also</span></span>
 [<span data-ttu-id="8931a-152">Registro de Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="8931a-152">Integration Services &#40;SSIS&#41; Logging</span></span>](../performance/integration-services-ssis-logging.md)


