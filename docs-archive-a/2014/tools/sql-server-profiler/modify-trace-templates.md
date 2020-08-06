---
title: Modificar plantillas de seguimiento | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- templates [SQL Server], SQL Server Profiler
- Profiler [SQL Server Profiler], templates
- trace templates [SQL Server]
- modifying trace templates
- SQL Server Profiler, templates
ms.assetid: 75b62a54-8d16-4599-bd2d-c42cfcc209f4
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4a26d0a70f65b6ff60dcf42ffb98e67dc0d2b52d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663246"
---
# <a name="modify-trace-templates"></a><span data-ttu-id="f9eed-102">Modificar plantillas de seguimiento</span><span class="sxs-lookup"><span data-stu-id="f9eed-102">Modify Trace Templates</span></span>
  <span data-ttu-id="f9eed-103">Puede modificar las plantillas que están guardadas en un archivo en el equipo local en el que se ejecuta el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f9eed-103">You can modify templates that are saved in a file on the local computer on which [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] is running.</span></span> <span data-ttu-id="f9eed-104">También puede modificar plantillas derivadas de esos archivos.</span><span class="sxs-lookup"><span data-stu-id="f9eed-104">You can also modify templates derived from those files.</span></span> <span data-ttu-id="f9eed-105">Al modificar plantillas existentes, edite las propiedades de la plantilla, como clases de evento y columnas de datos, en el mismo orden en que se definieron originalmente, en la pestaña **Selección de eventos** del cuadro de diálogo **Propiedades de seguimiento** .</span><span class="sxs-lookup"><span data-stu-id="f9eed-105">When you modify existing templates, you edit template properties such as event classes and data columns, in the same order that the properties were set originally, on the **Events Selection** tab of the **Trace Properties** dialog box.</span></span> <span data-ttu-id="f9eed-106">Puede agregar o quitar clases de eventos y columnas de datos, así como cambiar filtros.</span><span class="sxs-lookup"><span data-stu-id="f9eed-106">Event classes and data columns can be added or removed, and filters can be changed.</span></span> <span data-ttu-id="f9eed-107">Después de modificar la plantilla, se crea una plantilla específica del usuario y la original se deja intacta.</span><span class="sxs-lookup"><span data-stu-id="f9eed-107">After the template is modified, a user-specific template is created and the original system template is left intact.</span></span> <span data-ttu-id="f9eed-108">Para obtener más información, vea [Guardar seguimientos y plantillas de seguimiento](save-traces-and-trace-templates.md).</span><span class="sxs-lookup"><span data-stu-id="f9eed-108">For more information, see [Save Traces and Trace Templates](save-traces-and-trace-templates.md).</span></span>  
  
 <span data-ttu-id="f9eed-109">Es posible que tenga que derivar una plantilla de un archivo de seguimiento existente si no puede recordar (o no ha guardado) la plantilla original que se utilizó para crear el seguimiento o si desea volver a ejecutar el mismo seguimiento posteriormente.</span><span class="sxs-lookup"><span data-stu-id="f9eed-109">You may need to derive a template from an existing trace file if you cannot remember (or have not saved) the original template that was used to create the trace, or if you want to run the same trace at a later date.</span></span> <span data-ttu-id="f9eed-110">Si trabaja con seguimientos existentes, puede ver las propiedades, pero no modificarlas.</span><span class="sxs-lookup"><span data-stu-id="f9eed-110">When working with existing traces, you can view the properties, but you cannot modify the properties.</span></span> <span data-ttu-id="f9eed-111">Para modificar las propiedades, detenga o pause el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f9eed-111">To modify the properties, stop or pause the trace.</span></span> <span data-ttu-id="f9eed-112">Para obtener más información, vea [Derivar una plantilla a partir de un archivo o tabla de seguimiento &#40;SQL Server Profiler&#41;](sql-server-profiler.md) y [Derivar una plantilla a partir de un seguimiento en ejecución &#40;SQL Server Profiler&#41;](derive-a-template-from-a-running-trace-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="f9eed-112">For more information, see [Derive a Template from a Trace File or Trace Table &#40;SQL Server Profiler&#41;](sql-server-profiler.md) and [Derive a Template from a Running Trace &#40;SQL Server Profiler&#41;](derive-a-template-from-a-running-trace-sql-server-profiler.md).</span></span>  
  
 <span data-ttu-id="f9eed-113">**Para crear una plantilla de seguimiento**</span><span class="sxs-lookup"><span data-stu-id="f9eed-113">**To create a trace template**</span></span>  
  
 [<span data-ttu-id="f9eed-114">Crear una plantilla de seguimiento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="f9eed-114">Create a Trace Template &#40;SQL Server Profiler&#41;</span></span>](create-a-trace-template-sql-server-profiler.md)  
  
 <span data-ttu-id="f9eed-115">**Para ejecutar un seguimiento desde una plantilla de seguimiento**</span><span class="sxs-lookup"><span data-stu-id="f9eed-115">**To run a trace from a trace template**</span></span>  
  
 [<span data-ttu-id="f9eed-116">Crear un seguimiento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="f9eed-116">Create a Trace &#40;SQL Server Profiler&#41;</span></span>](create-a-trace-sql-server-profiler.md)  
  
 <span data-ttu-id="f9eed-117">**Para modificar una plantilla de seguimiento**</span><span class="sxs-lookup"><span data-stu-id="f9eed-117">**To modify a trace template**</span></span>  
  
 [<span data-ttu-id="f9eed-118">Usar SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="f9eed-118">Using SQL Server Profiler</span></span>](../../database-engine/modify-a-trace-template-sql-server-profiler.md)  
  
 [<span data-ttu-id="f9eed-119">Uso de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f9eed-119">Using Transact-SQL</span></span>](../../relational-databases/sql-trace/modify-an-existing-trace-transact-sql.md)  
  
 <span data-ttu-id="f9eed-120">**Para agregar o quitar eventos de una plantilla de seguimiento o de un archivo de seguimiento**</span><span class="sxs-lookup"><span data-stu-id="f9eed-120">**To add or remove events from a trace template or trace file**</span></span>  
  
 [<span data-ttu-id="f9eed-121">Usar SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="f9eed-121">Using SQL Server Profiler</span></span>](specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md)  
  
 [<span data-ttu-id="f9eed-122">Uso de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f9eed-122">Using Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="f9eed-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f9eed-123">See Also</span></span>  
 [<span data-ttu-id="f9eed-124">Iniciar un seguimiento</span><span class="sxs-lookup"><span data-stu-id="f9eed-124">Start a Trace</span></span>](start-a-trace.md)  
  
  
