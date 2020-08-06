---
title: Establecer un tamaño máximo de tabla para una tabla de seguimiento (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- size [SQL Server], trace tables
- maximum table size for traces
ms.assetid: d0ae83e5-1c88-4a2e-be05-2c341280b978
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5f48efbe02e300e06faf857ed0fb36ae340ad979
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743737"
---
# <a name="set-a-maximum-table-size-for-a-trace-table-sql-server-profiler"></a><span data-ttu-id="a6219-102">Establecer un tamaño máximo de tabla para una tabla de seguimiento (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="a6219-102">Set a Maximum Table Size for a Trace Table (SQL Server Profiler)</span></span>
  <span data-ttu-id="a6219-103">En este tema se describe cómo establecer un tamaño máximo de tabla para tablas de seguimiento mediante el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6219-103">This topic describes how to set a maximum table size for trace tables by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-set-a-maximum-table-size-for-a-trace-table"></a><span data-ttu-id="a6219-104">Para establecer un tamaño máximo de tabla para una tabla de seguimiento</span><span class="sxs-lookup"><span data-stu-id="a6219-104">To set a maximum table size for a trace table</span></span>  
  
1.  <span data-ttu-id="a6219-105">En el menú **Archivo** , haga clic en **Nuevo seguimiento**y, a continuación, conéctese a una instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a6219-105">On the **File** menu, click **New Trace**, and then connect to an instance of SQL Server.</span></span>  
  
     <span data-ttu-id="a6219-106">Aparecerá el cuadro de diálogo **Propiedades de seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="a6219-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a6219-107">Si se selecciona **Iniciar el seguimiento inmediatamente tras realizar la conexión**, el cuadro de diálogo **Propiedades de seguimiento**no aparecerá y, en su lugar, se iniciará el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a6219-107">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear and the trace begins instead.</span></span> <span data-ttu-id="a6219-108">Para desactivar esta configuración, en el menú **Herramientas**, haga clic en **Opciones**y desactive la casilla **Iniciar el seguimiento inmediatamente tras realizar la conexión** .</span><span class="sxs-lookup"><span data-stu-id="a6219-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="a6219-109">En el cuadro **Nombre de seguimiento** , escriba un nombre para el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a6219-109">In the **Trace name** box, type a name for the trace.</span></span>  
  
3.  <span data-ttu-id="a6219-110">En el cuadro **Nombre de plantilla**, seleccione una plantilla de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a6219-110">In the **Template name**list, select a trace template.</span></span>  
  
4.  <span data-ttu-id="a6219-111">Active la casilla **Guardar en la tabla**.</span><span class="sxs-lookup"><span data-stu-id="a6219-111">Select the **Save to table**check box.</span></span>  
  
5.  <span data-ttu-id="a6219-112">Conéctese al servidor en el que desee que se almacene el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a6219-112">Connect to the server on which you want the trace to be stored.</span></span>  
  
     <span data-ttu-id="a6219-113">Aparecerá el cuadro de diálogo **Tabla de destino** .</span><span class="sxs-lookup"><span data-stu-id="a6219-113">The **Destination Table** dialog box appears.</span></span>  
  
6.  <span data-ttu-id="a6219-114">En la lista **Base de datos** , seleccione una base de datos para el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a6219-114">Select a database for the trace from the **Database** list.</span></span>  
  
7.  <span data-ttu-id="a6219-115">En el cuadro **Tabla** , escriba o seleccione un nombre de tabla.</span><span class="sxs-lookup"><span data-stu-id="a6219-115">In the **Table** box, type or select a table name.</span></span>  
  
8.  <span data-ttu-id="a6219-116">Active la casilla **Establecer número máximo de filas (en miles)** y especifique un número máximo de filas para la tabla de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a6219-116">Select the **Set maximum rows** check box, and specify a maximum number of rows for the trace table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a6219-117">Cuando el número de filas de la tabla supere el máximo especificado, dejarán de registrarse los eventos de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a6219-117">When the number of rows in the table exceeds the maximum that you have specified, the trace events are no longer recorded.</span></span> <span data-ttu-id="a6219-118">No obstante, la traza continuará.</span><span class="sxs-lookup"><span data-stu-id="a6219-118">However, tracing continues.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6219-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a6219-119">See Also</span></span>  
 <span data-ttu-id="a6219-120">[SQL Server Profiler](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="a6219-120">[SQL Server Profiler](sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="a6219-121">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="a6219-121">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
