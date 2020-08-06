---
title: Crear un script de Transact-SQL para ejecutar un seguimiento (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], running
- scripts [SQL Server], traces
ms.assetid: 6b0e2519-998d-40d5-b8ba-5e6a773f91a6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3d4b4bebb2a3e05e3de12e59c53ccca9c980afd5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743746"
---
# <a name="create-a-transact-sql-script-for-running-a-trace-sql-server-profiler"></a><span data-ttu-id="f24c6-102">Crear un script de Transact-SQL para ejecutar un seguimiento (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="f24c6-102">Create a Transact-SQL Script for Running a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="f24c6-103">En este tema se describe cómo crear un script de Transact-SQL a partir de un archivo o una tabla de seguimiento existente mediante el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f24c6-103">This topic describes how to create a Transact-SQL script from an existing trace file or table by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-create-a-transact-sql-script-to-run-a-trace"></a><span data-ttu-id="f24c6-104">Para crear un script de Transact-SQL para ejecutar un seguimiento</span><span class="sxs-lookup"><span data-stu-id="f24c6-104">To create a Transact-SQL script to run a trace</span></span>  
  
1.  <span data-ttu-id="f24c6-105">Abra un archivo o una tabla de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f24c6-105">Open a trace file or table.</span></span> <span data-ttu-id="f24c6-106">Para obtener más información, vea [Abrir un archivo de seguimiento &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) o el Asistente para la optimización del [Abrir una tabla de seguimiento &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="f24c6-106">For more information, see [Open a Trace File &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) or [Open a Trace Table &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span></span>  
  
2.  <span data-ttu-id="f24c6-107">En el menú**Archivo**seleccione **Exportar**, **Definición de seguimiento de scripts**y, a continuación, haga clic en la versión que corresponda al servidor cuyo seguimiento desee realizar.</span><span class="sxs-lookup"><span data-stu-id="f24c6-107">On the**File**menu, point to **Export**, point to **Script Trace Definition**, and then click the version that corresponds to the server you want to trace.</span></span>  
  
3.  <span data-ttu-id="f24c6-108">En el cuadro de diálogo **Guardar como** , especifique un nombre para el archivo de script y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f24c6-108">In the **Save As** dialog box, enter a name for the script file, and then click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f24c6-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f24c6-109">See Also</span></span>  
 <span data-ttu-id="f24c6-110">[Plantillas y permisos de SQL Server Profiler](sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="f24c6-110">[SQL Server Profiler Templates and Permissions](sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="f24c6-111">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="f24c6-111">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
