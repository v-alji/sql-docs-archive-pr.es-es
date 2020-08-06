---
title: Filtrar eventos basándose en la hora de finalización del evento (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- event end times [SQL Server]
- filters [SQL Server], traces
- traces [SQL Server], filters
- traces [SQL Server], events
ms.assetid: 74628f9e-2d39-496a-a443-0a3887db223d
author: stevestein
ms.author: sstein
ms.openlocfilehash: d25d8e1adbd95f48d88fd1516c48dcc0f8374a7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750389"
---
# <a name="filter-events-based-on-the-event-end-time-sql-server-profiler"></a><span data-ttu-id="b74e1-102">Filtrar eventos basándose en la hora de finalización del evento (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="b74e1-102">Filter Events Based on the Event End Time (SQL Server Profiler)</span></span>
  <span data-ttu-id="b74e1-103">En este tema se describe el modo de filtrar eventos de seguimiento basándose en la hora de finalización del evento mediante el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b74e1-103">This topic describes how to filter trace events based on the event ending time by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-filter-events-based-on-the-event-end-time"></a><span data-ttu-id="b74e1-104">Para filtrar eventos basándose en la hora de finalización del evento</span><span class="sxs-lookup"><span data-stu-id="b74e1-104">To filter events based on the event end time</span></span>  
  
1.  <span data-ttu-id="b74e1-105">En el menú **Archivo** , haga clic en **Nuevo seguimiento**y conéctese a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b74e1-105">On the **File** menu, click **New Trace**, and then connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="b74e1-106">Aparecerá el cuadro de diálogo **Propiedades de seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="b74e1-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b74e1-107">Si se selecciona **Iniciar el seguimiento inmediatamente tras realizar la conexión**, el cuadro de diálogo **Propiedades de seguimiento**no aparecerá y, en su lugar, se iniciará el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b74e1-107">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear and the trace begins instead.</span></span> <span data-ttu-id="b74e1-108">Para desactivar esta configuración, en el menú **Herramientas**, haga clic en **Opciones**y desactive la casilla **Iniciar el seguimiento inmediatamente tras realizar la conexión** .</span><span class="sxs-lookup"><span data-stu-id="b74e1-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="b74e1-109">En el cuadro de diálogo **Propiedades de seguimiento** , asegúrese de que la pestaña **General** está seleccionada y especifique un nombre en el cuadro de texto **Nombre de seguimiento** .</span><span class="sxs-lookup"><span data-stu-id="b74e1-109">In the **Trace Properties** dialog box, make sure the **General** tab is selected, and enter a name in the **TraceName** text box.</span></span>  
  
3.  <span data-ttu-id="b74e1-110">En la lista **Usar la plantilla**, seleccione una plantilla de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b74e1-110">From the **Use the template**list, select a trace template.</span></span>  
  
4.  <span data-ttu-id="b74e1-111">Opcionalmente, especifique una tabla o un archivo de destino donde guardar los resultados del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b74e1-111">Optionally, specify a destination file or table in which to save the trace results.</span></span>  
  
5.  <span data-ttu-id="b74e1-112">En el menú **Selección de eventos**, haga clic en la columna de datos **Hora de finalización** para iniciar el cuadro de diálogo **Editar filtro** .</span><span class="sxs-lookup"><span data-stu-id="b74e1-112">On the **Events Selection**tab, click the **EndTime** data column to launch the **Edit Filter** dialog box.</span></span> <span data-ttu-id="b74e1-113">También puede hacer clic con el botón derecho en el encabezado de la columna y seleccionar **Editar filtro de columna**.</span><span class="sxs-lookup"><span data-stu-id="b74e1-113">You can also right-click the column heading, and select **Edit Column Filter**.</span></span>  
  
6.  <span data-ttu-id="b74e1-114">Expanda **mayor que** o **menor que**y escriba un `datetime` valor en el campo que aparece debajo del operador de comparación.</span><span class="sxs-lookup"><span data-stu-id="b74e1-114">Expand **Greater than** or **Less than**, and enter a `datetime`value in the field that appears beneath the comparison operator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b74e1-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b74e1-115">See Also</span></span>  
 <span data-ttu-id="b74e1-116">[SQL Server Profiler](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="b74e1-116">[SQL Server Profiler](sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="b74e1-117">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="b74e1-117">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
