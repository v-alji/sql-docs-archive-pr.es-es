---
title: Ver información de filtro (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- displaying filter information
- filters [SQL Server], viewing
- filters [SQL Server], traces
- traces [SQL Server], filters
- viewing filter information
ms.assetid: 8d002dea-376a-452c-b3ca-3e93656ed75f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 931b83f8087d446cfc7b08d9582cbad5b02cf671
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670731"
---
# <a name="view-filter-information-sql-server-profiler"></a><span data-ttu-id="09c58-102">Ver información de un filtro (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="09c58-102">View Filter Information (SQL Server Profiler)</span></span>
  <span data-ttu-id="09c58-103">En este tema se describe cómo ver filtros de columnas de datos para clases de eventos mediante el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="09c58-103">This topic describes how to view filters on data columns for event classes by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-view-filter-information"></a><span data-ttu-id="09c58-104">Para ver la información del filtro</span><span class="sxs-lookup"><span data-stu-id="09c58-104">To view filter information</span></span>  
  
1.  <span data-ttu-id="09c58-105">Abra un archivo de seguimiento, tabla de seguimiento o script SQL y, en el menú **Archivo** , haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="09c58-105">Open a trace file, trace table, or SQL script, and on the **File** menu, click **Properties**.</span></span> <span data-ttu-id="09c58-106">Si edita una plantilla de seguimiento o crea un seguimiento nuevo, omita este paso.</span><span class="sxs-lookup"><span data-stu-id="09c58-106">If you are editing a trace template or creating a new trace, skip this step.</span></span>  
  
2.  <span data-ttu-id="09c58-107">En la pestaña **Selección de eventos** , haga clic con el botón derecho en el nombre de la columna de datos del filtro que quiere ver y haga clic en **Editar filtro de columna**.</span><span class="sxs-lookup"><span data-stu-id="09c58-107">On the **Events Selection** tab, right-click the data column name for the filter you want to view, and click **Edit Column Filter**.</span></span>  
  
3.  <span data-ttu-id="09c58-108">En el cuadro de diálogo **Editar filtro** , expanda los operadores de comparación de filtros para ver el valor asignado al criterio especificado.</span><span class="sxs-lookup"><span data-stu-id="09c58-108">In the **Edit Filter** dialog box, expand the filter comparison operators to see the assigned value for the specified criterion.</span></span> <span data-ttu-id="09c58-109">Repita los pasos 2 y 3 para todas las columnas para las que desee ver información del filtro.</span><span class="sxs-lookup"><span data-stu-id="09c58-109">Repeat Steps 2 and 3 for all columns for which you want to view filter information.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="09c58-110">Los operadores de comparación con valores asignados se muestran en negrita.</span><span class="sxs-lookup"><span data-stu-id="09c58-110">Comparison operators with assigned values are formatted bold.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09c58-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="09c58-111">See Also</span></span>  
 [<span data-ttu-id="09c58-112">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="09c58-112">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
