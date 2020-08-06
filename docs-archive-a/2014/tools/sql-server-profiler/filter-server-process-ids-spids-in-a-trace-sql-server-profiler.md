---
title: Filtrar los Id. de proceso de servidor (SPID) en un seguimiento (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- filters [SQL Server], traces
- filters [SQL Server], SPIDs
- traces [SQL Server], filters
ms.assetid: f5945c39-be6b-4632-91cb-92066c80e188
author: stevestein
ms.author: sstein
ms.openlocfilehash: 99ae7eac6f19bd942a04f97b0a7da580eadc9dbf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749003"
---
# <a name="filter-server-process-ids-spids-in-a-trace-sql-server-profiler"></a><span data-ttu-id="fd797-102">Filtrar los Id. de proceso de servidor (SPID) en un seguimiento (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="fd797-102">Filter Server Process IDs (SPIDs) in a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="fd797-103">En este tema se describe cómo filtrar identificadores de proceso de servidor (SPID) en un seguimiento mediante el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fd797-103">This topic describes how to filter server process identifiers (SPIDs) in a trace by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-filter-system-ids-in-a-trace"></a><span data-ttu-id="fd797-104">Para filtrar identificadores de sistema en un seguimiento</span><span class="sxs-lookup"><span data-stu-id="fd797-104">To filter system IDs in a trace</span></span>  
  
1.  <span data-ttu-id="fd797-105">En el menú **Archivo** , haga clic en **Nuevo seguimiento**y, a continuación, conéctese a una instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fd797-105">On the **File** menu, click **New Trace**, and then connect to an instance of SQL Server.</span></span>  
  
     <span data-ttu-id="fd797-106">Aparecerá el cuadro de diálogo **Propiedades de seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="fd797-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fd797-107">Si está seleccionada la opción **iniciar el seguimiento inmediatamente después de establecer la conexión**, el cuadro de diálogo Propiedades de **seguimiento**no aparecerá y, en su lugar, se iniciará el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="fd797-107">if **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear, and the trace begins instead.</span></span> <span data-ttu-id="fd797-108">Para desactivar esta configuración, en el menú **Herramientas**, haga clic en **Opciones**y desactive la casilla **Iniciar el seguimiento inmediatamente tras realizar la conexión** .</span><span class="sxs-lookup"><span data-stu-id="fd797-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="fd797-109">En el cuadro **Nombre de seguimiento** , escriba un nombre para el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="fd797-109">In the **Trace name** box, type a name for the trace.</span></span>  
  
3.  <span data-ttu-id="fd797-110">En el cuadro **Use the template**(Usar la plantilla), seleccione una plantilla de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="fd797-110">In the **Use the template**name list, select a trace template.</span></span>  
  
4.  <span data-ttu-id="fd797-111">Opcionalmente, especifique una tabla o un archivo de destino donde guardar los resultados del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="fd797-111">Optionally, specify a destination file or table in which to save the trace results.</span></span>  
  
5.  <span data-ttu-id="fd797-112">En el menú **Selección de eventos**, haga clic en el encabezado de la columna **SPID**para mostrar el cuadro de diálogo **Editar filtro** .</span><span class="sxs-lookup"><span data-stu-id="fd797-112">On the **Events Selection**tab, click the **SPID**column heading to launch the **Edit Filter** dialog box.</span></span> <span data-ttu-id="fd797-113">También puede hacer clic con el botón derecho en el encabezado de la columna y seleccionar **Editar filtro de columna**.</span><span class="sxs-lookup"><span data-stu-id="fd797-113">You can also right-click the column heading and choose **Edit Column Filter**.</span></span> <span data-ttu-id="fd797-114">Si no aparece la columna **SPID** , active la casilla **Mostrar todas las columnas** .</span><span class="sxs-lookup"><span data-stu-id="fd797-114">If the **SPID** column does not appear, check the **Show all columns** box.</span></span>  
  
6.  <span data-ttu-id="fd797-115">En el cuadro de diálogo **Editar filtro** , expanda el operador de comparación adecuado y especifique un SPID como valor para la comparación.</span><span class="sxs-lookup"><span data-stu-id="fd797-115">In the **Edit Filter** dialog box, expand the appropriate comparison operator, and enter a SPID as a value for the comparison.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd797-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fd797-116">See Also</span></span>  
 [<span data-ttu-id="fd797-117">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="fd797-117">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
