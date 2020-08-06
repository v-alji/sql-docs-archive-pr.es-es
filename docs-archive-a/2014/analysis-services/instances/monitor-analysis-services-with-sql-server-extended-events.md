---
title: Usar SQL Server Extended Events (XEvents) para supervisar Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b57cc2fe-52dc-4fa9-8554-5a866e25c6d7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9d12d9bc8d6a56702e1b44f8404b25681a1033f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675031"
---
# <a name="use-sql-server-extended-events-xevents-to-monitor-analysis-services"></a><span data-ttu-id="f63b4-102">Usar SQL Server Extended Events (XEvents) para supervisar Analysis Services</span><span class="sxs-lookup"><span data-stu-id="f63b4-102">Use SQL Server Extended Events (XEvents) to Monitor Analysis Services</span></span>
  <span data-ttu-id="f63b4-103">Analysis Services proporciona funciones de seguimiento mediante el uso de [eventos extendidos](../../relational-databases/extended-events/extended-events.md).</span><span class="sxs-lookup"><span data-stu-id="f63b4-103">Analysis Services provides tracing capabilities through the usage of [Extended Events](../../relational-databases/extended-events/extended-events.md).</span></span>  
  
 <span data-ttu-id="f63b4-104">Eventos extendidos es una infraestructura de eventos con un alto nivel de escalabilidad y configurabilidad para sistemas de servidor.</span><span class="sxs-lookup"><span data-stu-id="f63b4-104">Extended Events is an event infrastructure that is highly scalable and configurable for server systems.</span></span> <span data-ttu-id="f63b4-105">Extended Events es un sistema ligero de supervisión de rendimiento que usa muy pocos recursos de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="f63b4-105">Extended Events is a light weight performance monitoring system that uses very few performance resources.</span></span>  
  
 <span data-ttu-id="f63b4-106">Todos los eventos de Analysis Services se pueden capturar y destinar a usuarios específicos, tal como se define en [Extended Events](../../relational-databases/extended-events/extended-events.md), a través de XEvents.</span><span class="sxs-lookup"><span data-stu-id="f63b4-106">All Analysis Services events can be captured and target to specific consumers, as defined in [Extended Events](../../relational-databases/extended-events/extended-events.md), through XEvents.</span></span>  
  
## <a name="initiating-extended-events-in-analysis-services"></a><span data-ttu-id="f63b4-107">Iniciar Eventos extendidos en Analysis Services</span><span class="sxs-lookup"><span data-stu-id="f63b4-107">Initiating Extended Events in Analysis Services</span></span>  
 <span data-ttu-id="f63b4-108">El seguimiento de Eventos extendidos se habilita mediante un comando de script de objeto de creación XMLA similar como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="f63b4-108">Extended Event tracing is enabled using a similar XMLA create object script command as shown below:</span></span>  
  
```  
<Execute ...>  
   <Command>  
      <Batch ...>  
         <Create ...>  
            <ObjectDefinition>  
               <Trace>  
                  <ID>trace_id</ID>  
                  <Name>trace_name</Name>  
                  <ddl300_300:XEvent>  
                     <event_session ...>  
                        <event package="AS" name="AS_event">  
                           <action package="PACKAGE0" .../>  
                        </event>  
                        <target package="PACKAGE0" name="asynchronous_file_target">  
                           <parameter name="filename" value="data_filename.xel"/>  
                           <parameter name="metadatafile" value="metadata_filename.xem"/>  
                        </target>  
                     </event_session>  
                  </ddl300_300:XEvent>  
               </Trace>  
            </ObjectDefinition>  
         </Create>  
      </Batch>  
   </Command>  
   <Properties></Properties>  
</Execute>  
  
```  
  
 <span data-ttu-id="f63b4-109">Donde el usuario definirá los siguientes elementos, según las necesidades del seguimiento:</span><span class="sxs-lookup"><span data-stu-id="f63b4-109">Where the following elements are to be defined by the user, depending on the tracing needs:</span></span>  
  
 <span data-ttu-id="f63b4-110">*trace_id*</span><span class="sxs-lookup"><span data-stu-id="f63b4-110">*trace_id*</span></span>  
 <span data-ttu-id="f63b4-111">Define el identificador único de este seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f63b4-111">Defines the unique identifier for this trace.</span></span>  
  
 <span data-ttu-id="f63b4-112">*trace_name*</span><span class="sxs-lookup"><span data-stu-id="f63b4-112">*trace_name*</span></span>  
 <span data-ttu-id="f63b4-113">El nombre proporcionado a este seguimiento; normalmente una definición legible del mismo.</span><span class="sxs-lookup"><span data-stu-id="f63b4-113">The name given to this trace; usually a human readable definition of the trace.</span></span> <span data-ttu-id="f63b4-114">Es una práctica común usar el valor de *trace_id* como nombre.</span><span class="sxs-lookup"><span data-stu-id="f63b4-114">It is a common practice to use the *trace_id* value as the name.</span></span>  
  
 <span data-ttu-id="f63b4-115">*AS_event*</span><span class="sxs-lookup"><span data-stu-id="f63b4-115">*AS_event*</span></span>  
 <span data-ttu-id="f63b4-116">El evento de Analysis Services que se expondrá.</span><span class="sxs-lookup"><span data-stu-id="f63b4-116">The Analysis Services event to be exposed.</span></span> <span data-ttu-id="f63b4-117">Consulte [Eventos de seguimiento de Analysis Services](https://docs.microsoft.com/bi-reference/trace-events/analysis-services-trace-events) para ver los nombres de los eventos.</span><span class="sxs-lookup"><span data-stu-id="f63b4-117">See [Analysis Services Trace Events](https://docs.microsoft.com/bi-reference/trace-events/analysis-services-trace-events) for names of the events.</span></span>  
  
 <span data-ttu-id="f63b4-118">*data_filename*</span><span class="sxs-lookup"><span data-stu-id="f63b4-118">*data_filename*</span></span>  
 <span data-ttu-id="f63b4-119">El nombre del archivo de datos que contiene los datos de los eventos.</span><span class="sxs-lookup"><span data-stu-id="f63b4-119">The name of the file that contains the events data.</span></span> <span data-ttu-id="f63b4-120">Este nombre se añade como sufijo con una marca de tiempo para evitar sobrescribir los datos si el seguimiento se envía repetidamente.</span><span class="sxs-lookup"><span data-stu-id="f63b4-120">This name is suffixed with a time stamp to avoid data overwriting if the trace is sent over and over.</span></span>  
  
 <span data-ttu-id="f63b4-121">*metadata_filename*</span><span class="sxs-lookup"><span data-stu-id="f63b4-121">*metadata_filename*</span></span>  
 <span data-ttu-id="f63b4-122">El nombre del archivo de datos que contiene los metadatos de los eventos.</span><span class="sxs-lookup"><span data-stu-id="f63b4-122">The name of the file that contains the events metadata.</span></span> <span data-ttu-id="f63b4-123">Este nombre se añade como sufijo con una marca de tiempo para evitar sobrescribir los datos si el seguimiento se envía repetidamente.</span><span class="sxs-lookup"><span data-stu-id="f63b4-123">This name is suffixed with a time stamp to avoid data overwriting if the trace is sent over and over.</span></span>  
  
## <a name="stopping-extended-events-in-analysis-services"></a><span data-ttu-id="f63b4-124">Detener Eventos extendidos en Analysis Services</span><span class="sxs-lookup"><span data-stu-id="f63b4-124">Stopping Extended Events in Analysis Services</span></span>  
 <span data-ttu-id="f63b4-125">Para detener el objeto de seguimiento de Eventos extendidos, debe eliminar el objeto utilizando un comando de script de objeto de eliminación XMLA como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="f63b4-125">To stop the Extended Events tracing object you need to delete that object using a similar XMLA delete object script command as shown below:</span></span>  
  
```  
<Execute xmlns="urn:schemas-microsoft-com:xml-analysis">  
   <Command>  
      <Batch ...>  
         <Delete ...>  
            <Object>  
               <TraceID>trace_id</TraceID>  
            </Object>  
         </Delete>  
      </Batch>  
   </Command>  
   <Properties></Properties>  
</Execute>  
  
```  
  
 <span data-ttu-id="f63b4-126">Donde el usuario definirá los siguientes elementos, según las necesidades del seguimiento:</span><span class="sxs-lookup"><span data-stu-id="f63b4-126">Where the following elements are to be defined by the user, depending on the tracing needs:</span></span>  
  
 <span data-ttu-id="f63b4-127">*trace_id*</span><span class="sxs-lookup"><span data-stu-id="f63b4-127">*trace_id*</span></span>  
 <span data-ttu-id="f63b4-128">Define el identificador único para el seguimiento que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="f63b4-128">Defines the unique identifier for the trace to be deleted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f63b4-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f63b4-129">See Also</span></span>  
 [<span data-ttu-id="f63b4-130">Eventos extendidos</span><span class="sxs-lookup"><span data-stu-id="f63b4-130">Extended Events</span></span>](../../relational-databases/extended-events/extended-events.md)  
  
  
