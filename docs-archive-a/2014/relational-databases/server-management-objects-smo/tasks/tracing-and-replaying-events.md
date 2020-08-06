---
title: Seguimiento y reproducción de eventos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- replaying events
- traces [SMO]
- events [SMO], replaying
- events [SMO], tracing
ms.assetid: f41b3f85-2f6c-4c3e-9776-8c73d2cc7a53
author: stevestein
ms.author: sstein
ms.openlocfilehash: f7f0d570c70ef1cba080217e6c3a0f9b6055a4d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746206"
---
# <a name="tracing-and-replaying-events"></a><span data-ttu-id="d8e40-102">Seguimiento y reproducción de eventos</span><span class="sxs-lookup"><span data-stu-id="d8e40-102">Tracing and Replaying Events</span></span>
  <span data-ttu-id="d8e40-103">En SMO, los objetos `Trace` y `Replay` del espacio de nombres <xref:Microsoft.SqlServer.Management.Trace> proporcionan acceso mediante programación a la funcionalidad de [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)], que se utiliza para supervisar una instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] o [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8e40-103">In SMO, the `Trace` and `Replay` objects in the <xref:Microsoft.SqlServer.Management.Trace> namespace provide programmatic access to the [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] functionality, which is used for monitoring an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="d8e40-104">Puede capturar y guardar datos acerca de cada evento en un archivo o en una tabla para analizarlos posteriormente.</span><span class="sxs-lookup"><span data-stu-id="d8e40-104">You can capture and save data about each event to a file or table to analyze later.</span></span> <span data-ttu-id="d8e40-105">Por ejemplo, puede supervisar un entorno de producción para ver qué procedimientos almacenados afectan negativamente al rendimiento al ejecutarse demasiado lentamente.</span><span class="sxs-lookup"><span data-stu-id="d8e40-105">For example, you can monitor a production environment to see which procedures are impeding performance by executing too slowly.</span></span>  
  
 <span data-ttu-id="d8e40-106">Los objetos `Trace` y `Replay` proporcionan un conjunto de objetos que se pueden utilizar para crear seguimientos en una instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8e40-106">The `Trace` and `Replay` objects provide a set of objects that can be used to create traces on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d8e40-107">Puede utilizar estos objetos desde sus propias aplicaciones para crear seguimientos manualmente para [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] o [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8e40-107">These objects can be used from within your own applications to create traces manually for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="d8e40-108">Asimismo, se puede utilizar los objetos `Trace` de SMO para leer los archivos y las tablas de Seguimiento de SQL que se crearon al supervisar el registro de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] o DTS.</span><span class="sxs-lookup"><span data-stu-id="d8e40-108">Additionally, SMO `Trace` objects can be used to read SQL Trace files and tables that were created by monitoring [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], or DTS logging.</span></span>  
  
 <span data-ttu-id="d8e40-109">Los objetos `Trace` de SMO permiten realizar las funciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="d8e40-109">SMO `Trace` objects let you perform the following functions:</span></span>  
  
-   <span data-ttu-id="d8e40-110">Crear un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d8e40-110">Create a trace.</span></span>  
  
-   <span data-ttu-id="d8e40-111">Establecer filtros en el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d8e40-111">Set filters on the trace.</span></span>  
  
-   <span data-ttu-id="d8e40-112">Establecer los eventos de los que se va a realizar un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d8e40-112">Set the events that are being traced.</span></span>  
  
-   <span data-ttu-id="d8e40-113">Detener o iniciar un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d8e40-113">Stop or start a trace.</span></span>  
  
-   <span data-ttu-id="d8e40-114">Leer los archivos y las tablas de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d8e40-114">Read trace files, and trace tables.</span></span>  
  
-   <span data-ttu-id="d8e40-115">Obtener información sobre los eventos en un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d8e40-115">Get information about events on a trace.</span></span>  
  
-   <span data-ttu-id="d8e40-116">Obtener información sobre los filtros en un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d8e40-116">Get information about filters on a trace.</span></span>  
  
-   <span data-ttu-id="d8e40-117">Manipular mediante programación los datos de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d8e40-117">Manipulate trace data programmatically.</span></span>  
  
-   <span data-ttu-id="d8e40-118">Escribir archivos y tablas de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d8e40-118">Write trace tables and trace files.</span></span>  
  
-   <span data-ttu-id="d8e40-119">Reproducir archivos o tablas de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d8e40-119">Replay trace files or trace tables.</span></span>  
  
 <span data-ttu-id="d8e40-120">La aplicación SMO puede utilizar los datos de seguimiento de los `Trace` `Replay` objetos y, o bien se puede examinar manualmente mediante [SQL Server Profiler](../../../tools/sql-server-profiler/sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="d8e40-120">The trace data from the `Trace` and `Replay` objects can be used by the SMO application, or it can be examined manually by using [SQL Server Profiler](../../../tools/sql-server-profiler/sql-server-profiler.md).</span></span> <span data-ttu-id="d8e40-121">Los datos de seguimiento también son compatibles con los procedimientos almacenados de [SQL Trace](../../sql-trace/sql-trace.md) que también proporcionan funciones de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d8e40-121">The trace data is also compatible with the [SQL Trace](../../sql-trace/sql-trace.md) stored procedures that also provide tracing capabilities.</span></span>  
  
 <span data-ttu-id="d8e40-122">Los objetos de seguimiento de SMO residen en el espacio de nombres <xref:Microsoft.SqlServer.Management.Trace>, que requiere una referencia al archivo Microsoft.SQLServer.ConnectionInfo.dll.</span><span class="sxs-lookup"><span data-stu-id="d8e40-122">The SMO trace objects reside in the <xref:Microsoft.SqlServer.Management.Trace> namespace, which requires a reference to the Microsoft.SQLServer.ConnectionInfo.dll file.</span></span>  
  
 <span data-ttu-id="d8e40-123">Los objetos `Trace` y `Replay` requieren un objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection><xref:Microsoft.SqlServer.Management.Smo.Server.%23ctor%2A> que establezca una conexión con la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8e40-123">The `Trace` and `Replay` objects require a <xref:Microsoft.SqlServer.Management.Common.ServerConnection><xref:Microsoft.SqlServer.Management.Smo.Server.%23ctor%2A> object to establish a connection with the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d8e40-124">El objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> reside en el espacio de nombres <xref:Microsoft.SqlServer.Management.Common>, que requiere una referencia al archivo Microsoft.SQLServer.ConnectionInfo.dll.</span><span class="sxs-lookup"><span data-stu-id="d8e40-124">The <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object resides in the <xref:Microsoft.SqlServer.Management.Common> namespace, which requires a reference to the Microsoft.SQLServer.ConnectionInfo.dll file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d8e40-125">Los objetos `Trace` y `Replay` no se pueden utilizar en una plataforma de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="d8e40-125">The `Trace` and `Replay` objects are not supported on a 64-bit platform.</span></span>  
  
  
