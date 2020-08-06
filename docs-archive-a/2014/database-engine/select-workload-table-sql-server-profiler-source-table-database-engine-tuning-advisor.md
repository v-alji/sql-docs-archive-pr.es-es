---
title: SQL Server Profiler-Asistente para la optimización de motor de base de datos de tabla de origen-seleccionar tabla de carga de trabajo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.replay.tools.sourcetable.f1
helpviewer_keywords:
- Select Workload Table dialog box
- Source Table dialog box
ms.assetid: 51185be7-7092-480a-a52c-cf7786c4a0a0
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d10899c01df8e7fbc7ee45d108841a18d3248500
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671661"
---
# <a name="sql-server-profiler---source-table-database-engine-tuning-advisor---select-workload-table"></a><span data-ttu-id="f6539-102">Tabla de SQL Server Profiler de origen-Asistente para la optimización de motor de base de datos-seleccionar tabla de carga de trabajo</span><span class="sxs-lookup"><span data-stu-id="f6539-102">SQL Server Profiler - Source Table-Database Engine Tuning Advisor - Select Workload Table</span></span>
  <span data-ttu-id="f6539-103">El Asistente para la optimización de [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] y el [!INCLUDE[ssDE](../includes/ssde-md.md)] de Microsoft utilizan este cuadro de diálogo para seleccionar las tablas.</span><span class="sxs-lookup"><span data-stu-id="f6539-103">Microsoft [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] and [!INCLUDE[ssDE](../includes/ssde-md.md)] Tuning Advisor use this dialog box to select tables.</span></span>  
  
 <span data-ttu-id="f6539-104">En [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], use el cuadro de diálogo **Tabla de origen** a fin de especificar una tabla de origen para una tabla de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f6539-104">In [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], use the **Source Table** dialog box to specify a source table for a trace table.</span></span> <span data-ttu-id="f6539-105">Esta última es una tabla desde la que se carga un seguimiento y su contenido se ve y usa para reproducir el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f6539-105">This is a table from which a trace is loaded, and the contents of which are viewed or used for replaying the trace.</span></span>  
  
 <span data-ttu-id="f6539-106">En el Asistente para la optimización de [!INCLUDE[ssDE](../includes/ssde-md.md)], use el cuadro de diálogo **Seleccionar tabla de carga de trabajo** para seleccionar una tabla de base de datos que contenga información de seguimiento de [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], que puede usarse como carga de trabajo de optimización, o bien para obtener una vista previa del contenido de la tabla antes de iniciar el análisis de optimización.</span><span class="sxs-lookup"><span data-stu-id="f6539-106">In [!INCLUDE[ssDE](../includes/ssde-md.md)] Tuning Advisor, use the **Select Workload Table** dialog box to select a database table that contains [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] trace information to use as a tuning workload, or to preview the table contents before starting tuning analysis.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f6539-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="f6539-107">Options</span></span>  
 <span data-ttu-id="f6539-108">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="f6539-108">**SQL Server**</span></span>  
 <span data-ttu-id="f6539-109">Especifica la instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] conectada actualmente.</span><span class="sxs-lookup"><span data-stu-id="f6539-109">Specifies the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] currently connected.</span></span> <span data-ttu-id="f6539-110">Este campo se llena automáticamente y no puede actualizarse.</span><span class="sxs-lookup"><span data-stu-id="f6539-110">This field is populated automatically and cannot be updated.</span></span>  
  
 <span data-ttu-id="f6539-111">**Base de datos**</span><span class="sxs-lookup"><span data-stu-id="f6539-111">**Database**</span></span>  
 <span data-ttu-id="f6539-112">Especifica la base de datos en la que se ubica la tabla de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f6539-112">Specify the database where the trace table is located.</span></span>  
  
 <span data-ttu-id="f6539-113">**Propietario**</span><span class="sxs-lookup"><span data-stu-id="f6539-113">**Owner**</span></span>  
 <span data-ttu-id="f6539-114">Specifies the owner of the trace table.</span><span class="sxs-lookup"><span data-stu-id="f6539-114">Specifies the owner of the trace table.</span></span> <span data-ttu-id="f6539-115">Este campo se llena automáticamente como **dbo**.</span><span class="sxs-lookup"><span data-stu-id="f6539-115">This field is populated automatically as **dbo**.</span></span>  
  
 <span data-ttu-id="f6539-116">**Tabla**</span><span class="sxs-lookup"><span data-stu-id="f6539-116">**Table**</span></span>  
 <span data-ttu-id="f6539-117">Especifica el nombre de la tabla de seguimiento desde la que debe leerse el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f6539-117">Specify the name of the trace table from which the trace should be read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6539-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f6539-118">See Also</span></span>  
 <span data-ttu-id="f6539-119">[Guardar los resultados de un seguimiento en una tabla &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/save-trace-results-to-a-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="f6539-119">[Save Trace Results to a Table &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/save-trace-results-to-a-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="f6539-120">[Plantillas y permisos de SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="f6539-120">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="f6539-121">Database Engine Tuning Advisor</span><span class="sxs-lookup"><span data-stu-id="f6539-121">Database Engine Tuning Advisor</span></span>](../relational-databases/performance/database-engine-tuning-advisor.md)  
  
  
