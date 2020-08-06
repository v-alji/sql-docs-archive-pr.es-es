---
title: Guardar los resultados de un seguimiento en un archivo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 74f80667-62f3-4e14-bb1a-f0c2b6ef3402
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 644fc812bbb4863c336ff2f53f5b2d67ee0a4d5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663305"
---
# <a name="save-trace-results-to-a-file"></a><span data-ttu-id="a705b-102">Guardar los resultados de un seguimiento en un archivo</span><span class="sxs-lookup"><span data-stu-id="a705b-102">Save Trace Results to a File</span></span>
  <span data-ttu-id="a705b-103">Los resultados de un seguimiento se pueden guardar en un archivo.</span><span class="sxs-lookup"><span data-stu-id="a705b-103">You can save trace results to a file.</span></span> <span data-ttu-id="a705b-104">Un archivo de seguimiento es un archivo donde se escriben los resultados de un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a705b-104">A trace file is a file where the trace results are written.</span></span> <span data-ttu-id="a705b-105">Un archivo de seguimiento puede ubicarse en un directorio local (por ejemplo C:\\*nombreDeCarpeta*\\*nombreDeArchivo.trc*) o un directorio de red (por ejemplo \\\nombreDeEquipo\nombreDeRecursoCompartido\nombreDeArchivo.trc).</span><span class="sxs-lookup"><span data-stu-id="a705b-105">A trace file can be located either in a local directory (such as C:\\*foldername*\\*filename.trc*) or a network directory (such as \\\computername\sharename\filename.trc).</span></span>  
  
 <span data-ttu-id="a705b-106">Puede utilizar los archivos de seguimiento para realizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a705b-106">You can use the trace files to do the following:</span></span>  
  
-   <span data-ttu-id="a705b-107">Reproducir seguimientos</span><span class="sxs-lookup"><span data-stu-id="a705b-107">Replay traces</span></span>  
  
-   <span data-ttu-id="a705b-108">Auditar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a705b-108">Audit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="a705b-109">Realizar análisis de rendimiento</span><span class="sxs-lookup"><span data-stu-id="a705b-109">Conduct performance analysis</span></span>  
  
-   <span data-ttu-id="a705b-110">Correlacionar eventos de seguimiento con contadores de rendimiento para mejorar la detección de problemas</span><span class="sxs-lookup"><span data-stu-id="a705b-110">Correlate trace events with performance counters to enhance problem detection</span></span>  
  
-   <span data-ttu-id="a705b-111">Realizar análisis del Asistente para la optimización de motor de bases de datos</span><span class="sxs-lookup"><span data-stu-id="a705b-111">Perform Database Engine Tuning Advisor analysis</span></span>  
  
-   <span data-ttu-id="a705b-112">Optimizar las consultas</span><span class="sxs-lookup"><span data-stu-id="a705b-112">Carry out query optimization</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="a705b-113">guarda los resultados de un seguimiento en un archivo cuando se especifica una ruta de acceso y un nombre de archivo para el **@tracefile** argumento del procedimiento almacenado **sp_trace_create**.</span><span class="sxs-lookup"><span data-stu-id="a705b-113">saves trace results to a file when a path and file name are specified for the **@tracefile** argument of the stored procedure **sp_trace_create**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a705b-114">Si hay especificada una ruta de acceso al procedimiento almacenado **sp_trace_create** para guardar el archivo de seguimiento, el directorio debe ser accesible para el servidor.</span><span class="sxs-lookup"><span data-stu-id="a705b-114">If a path is specified to the **sp_trace_create** stored procedure for saving the trace file, the directory must be accessible to the server.</span></span> <span data-ttu-id="a705b-115">También debe tener presente que si un directorio local está especificado con **sp_trace_create**, se trata de un directorio local en el equipo servidor.</span><span class="sxs-lookup"><span data-stu-id="a705b-115">Also be aware that if a local directory is specified to **sp_trace_create**, it is a local directory on the server computer.</span></span>  
  
 <span data-ttu-id="a705b-116">Si se utiliza [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] , ello le permite guardar los resultados de un seguimiento en un archivo o una tabla.</span><span class="sxs-lookup"><span data-stu-id="a705b-116">If [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] is used, it allows you to save trace results to a file or to a table.</span></span> <span data-ttu-id="a705b-117">Si guarda los resultados de un seguimiento en una tabla, tendrá el mismo acceso que si guarda el seguimiento en un archivo, además de poder realizar consultas en la tabla para buscar eventos específicos.</span><span class="sxs-lookup"><span data-stu-id="a705b-117">Saving trace results to a table allows the same access as saving the trace to a file plus you can query the table to search for specific events.</span></span>  
  
 <span data-ttu-id="a705b-118">Para obtener más información sobre cómo guardar los resultados de seguimiento, vea [Guardar los resultados de un seguimiento en una tabla &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/save-trace-results-to-a-table-sql-server-profiler.md) y [Guardar los resultados de seguimiento en un archivo &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/save-trace-results-to-a-file-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="a705b-118">For more information about saving trace results, see [Save Trace Results to a Table &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/save-trace-results-to-a-table-sql-server-profiler.md) and [Save Trace Results to a File &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/save-trace-results-to-a-file-sql-server-profiler.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a705b-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a705b-119">See Also</span></span>  
 <span data-ttu-id="a705b-120">[sp_trace_create &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a705b-120">[sp_trace_create &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql) </span></span>  
 <span data-ttu-id="a705b-121">[Crear un seguimiento &#40;Transact-SQL&#41;](../sql-trace/create-a-trace-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="a705b-121">[Create a Trace &#40;Transact-SQL&#41;](../sql-trace/create-a-trace-transact-sql.md) </span></span>  
 [<span data-ttu-id="a705b-122">Crear un seguimiento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a705b-122">Create a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/create-a-trace-sql-server-profiler.md)  
  
  
