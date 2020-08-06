---
title: Filtrar eventos basándose en la hora de inicio del evento (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- event start times [SQL Server]
- filters [SQL Server], traces
- traces [SQL Server], filters
- traces [SQL Server], events
ms.assetid: e965579e-d006-41a3-89ec-cfd5398c67d2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7f652952ec6706580b876e3e9a20f96e62598f81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749005"
---
# <a name="filter-events-based-on-the-event-start-time-sql-server-profiler"></a><span data-ttu-id="9b509-102">Filtrar eventos basándose en la hora de inicio del evento (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="9b509-102">Filter Events Based on the Event Start Time (SQL Server Profiler)</span></span>
  <span data-ttu-id="9b509-103">En este tema se describe el modo de filtrar eventos de seguimiento basándose en la hora de inicio del evento mediante el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b509-103">This topic describes how to filter trace events based on the event start time by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-filter-an-event-based-on-the-event-start-time"></a><span data-ttu-id="9b509-104">Para filtrar un evento en función de la hora de inicio del evento</span><span class="sxs-lookup"><span data-stu-id="9b509-104">To filter an event based on the event start time</span></span>  
  
1.  <span data-ttu-id="9b509-105">En el menú **Archivo** , haga clic en **Nuevo seguimiento**y conéctese a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b509-105">On the **File** menu, click **New Trace**, and then connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="9b509-106">Aparecerá el cuadro de diálogo **Propiedades de seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="9b509-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9b509-107">Si se selecciona **Iniciar el seguimiento inmediatamente tras realizar la conexión**, el cuadro de diálogo **Propiedades de seguimiento**no aparecerá y, en su lugar, se iniciará el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9b509-107">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear, and the trace begins instead.</span></span> <span data-ttu-id="9b509-108">Para desactivar esta configuración, en el menú **Herramientas**, haga clic en **Opciones**y desactive la casilla **Iniciar el seguimiento inmediatamente tras realizar la conexión** .</span><span class="sxs-lookup"><span data-stu-id="9b509-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="9b509-109">En el cuadro **Nombre de seguimiento** , escriba un nombre para el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9b509-109">In the **Trace name** box, type a name for the trace.</span></span>  
  
3.  <span data-ttu-id="9b509-110">En el cuadro **Use the template**(Usar la plantilla), seleccione una plantilla de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9b509-110">In the **Use the template**name list, select a trace template.</span></span>  
  
4.  <span data-ttu-id="9b509-111">Opcionalmente, especifique un destino para los resultados del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9b509-111">Optionally specify a destination for the trace results.</span></span>  
  
5.  <span data-ttu-id="9b509-112">En el menú **Selección de eventos**, haga clic en el encabezado de columna **StartTime** .</span><span class="sxs-lookup"><span data-stu-id="9b509-112">On the **Events Selection**tab, click the **StartTime** column heading.</span></span> <span data-ttu-id="9b509-113">También puede hacer clic con el botón derecho en el encabezado de la columna y hacer clic en **Editar filtro de columna** para abrir el cuadro de diálogo **Editar filtro** .</span><span class="sxs-lookup"><span data-stu-id="9b509-113">You can also right-click the column heading, and then click **Edit Column Filter** to launch the **Edit Filter** dialog box.</span></span>  
  
6.  <span data-ttu-id="9b509-114">Expanda **mayor que** o **menor que**y, a continuación, escriba un `datetime` valor en el campo que aparece debajo del operador de comparación.</span><span class="sxs-lookup"><span data-stu-id="9b509-114">Expand **Greater than** or **Less than**, and then enter a `datetime` value in the field that appears beneath the comparison operator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b509-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9b509-115">See Also</span></span>  
 [<span data-ttu-id="9b509-116">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="9b509-116">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
