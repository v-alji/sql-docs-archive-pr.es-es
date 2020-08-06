---
title: Guardar gráficos de interbloqueo (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- deadlocks [SQL Server], saving deadlock graphs
- graphs [SQL Server]
- saving deadlock graphs
ms.assetid: bf1fc906-abd6-4a89-842e-da0d66b2defe
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: cdd0bd808ba4b934e5b2d91c9079909acf6e3997
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674769"
---
# <a name="save-deadlock-graphs-sql-server-profiler"></a><span data-ttu-id="915a1-102">Guardar gráficos de interbloqueo (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="915a1-102">Save Deadlock Graphs (SQL Server Profiler)</span></span>
  <span data-ttu-id="915a1-103">En este tema se explica cómo guardar un gráfico de interbloqueo mediante el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="915a1-103">This topic describes how to save a deadlock graph by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="915a1-104">Los gráficos de interbloqueo se guardan como archivos XML.</span><span class="sxs-lookup"><span data-stu-id="915a1-104">Deadlock graphs are saved as XML files.</span></span>  
  
### <a name="to-save-deadlock-graph-events-separately"></a><span data-ttu-id="915a1-105">Para guardar eventos deadlock graph por separado</span><span class="sxs-lookup"><span data-stu-id="915a1-105">To save deadlock graph events separately</span></span>  
  
1.  <span data-ttu-id="915a1-106">En el menú **Archivo** , haga clic en **Nuevo seguimiento**y, a continuación, conéctese a una instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="915a1-106">On the **File** menu, click **New Trace**, and then connect to an instance of SQL Server.</span></span>  
  
     <span data-ttu-id="915a1-107">Aparecerá el cuadro de diálogo **Propiedades de seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="915a1-107">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="915a1-108">Si se selecciona **Iniciar el seguimiento inmediatamente tras realizar la conexión** , el cuadro de diálogo **Propiedades de seguimiento**no aparecerá y, en su lugar, se iniciará el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="915a1-108">If **Start tracing immediately after making connection** is selected, the **Trace Properties**dialog box fails to appear, and the trace begins instead.</span></span> <span data-ttu-id="915a1-109">Para desactivar esta configuración, en el menú **Herramientas**, haga clic en **Opciones**y desactive la casilla **Iniciar el seguimiento inmediatamente tras realizar la conexión** .</span><span class="sxs-lookup"><span data-stu-id="915a1-109">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="915a1-110">En el cuadro de diálogo Propiedades de seguimiento, en el cuadro**Nombre de seguimiento** , escriba un nombre para el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="915a1-110">In the Trace Properties dialog box, type a name for the trace in the**Trace name** box.</span></span>  
  
3.  <span data-ttu-id="915a1-111">En la lista **Usar la plantilla** , seleccione la plantilla de seguimiento que desea utilizar para el seguimiento o seleccione la opción **En blanco** si no desea utilizar ninguna plantilla.</span><span class="sxs-lookup"><span data-stu-id="915a1-111">In the **Use the template** list, select a trace template on which to base the trace, or select **Blank** if you do not want to use a template.</span></span>  
  
4.  <span data-ttu-id="915a1-112">Lleve a cabo una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="915a1-112">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="915a1-113">Active la casilla**Guardar en archivo** para capturar el seguimiento en un archivo.</span><span class="sxs-lookup"><span data-stu-id="915a1-113">Select the**Save to file** check box to capture the trace to a file.</span></span> <span data-ttu-id="915a1-114">Especifique un valor en **Establecer el tamaño máximo de archivo (MB)** .</span><span class="sxs-lookup"><span data-stu-id="915a1-114">Specify a value for **Set maximum file size**.</span></span>  
  
         <span data-ttu-id="915a1-115">Si lo desea, seleccione **Habilitar sustitución incremental de archivos** y **El servidor procesa los datos de seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="915a1-115">Optionally, select **Enable file rollover** and **Server processes trace data**.</span></span>  
  
    -   <span data-ttu-id="915a1-116">Active la casilla **Guardar en tabla** para capturar el seguimiento en una tabla de base de datos.</span><span class="sxs-lookup"><span data-stu-id="915a1-116">Select the **Save to table** check box to capture the trace to a database table.</span></span>  
  
         <span data-ttu-id="915a1-117">Opcionalmente, haga clic en **establecer número máximo de filas**y especifique un valor.</span><span class="sxs-lookup"><span data-stu-id="915a1-117">Optionally, click **Set maximum rows**, and specify a value.</span></span>  
  
5.  <span data-ttu-id="915a1-118">Opcionalmente, active la casilla **Habilitar hora de detención de seguimiento** para especificar una fecha y hora de detención.</span><span class="sxs-lookup"><span data-stu-id="915a1-118">Optionally, select the **Enable trace stop time** check box, and specify a stop date and time.</span></span>  
  
6.  <span data-ttu-id="915a1-119">Haga clic en la pestaña **Selección de eventos**.</span><span class="sxs-lookup"><span data-stu-id="915a1-119">Click the **Events Selection**tab.</span></span>  
  
7.  <span data-ttu-id="915a1-120">En el cuadro de diálogo **Eventos**, expanda la categoría de evento **Bloqueos**y, luego, active la casilla **Deadlock graph**.</span><span class="sxs-lookup"><span data-stu-id="915a1-120">In the **Events**data column, expand the **Locks**event category, and then select the **Deadlock graph**check box.</span></span> <span data-ttu-id="915a1-121">Si la categoría de eventos Bloqueos no está disponible, seleccione la opción **Mostrar todos los eventos** para mostrarla.</span><span class="sxs-lookup"><span data-stu-id="915a1-121">If the Locks event category is not available, check **Show all events** to display it.</span></span>  
  
     <span data-ttu-id="915a1-122">Aparecerá el cuadro de diálogo **Configuración de extracción de eventos**se agrega al cuadro de diálogo **Propiedades de seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="915a1-122">The **Events Extraction Settings**tab is added to the **Trace Properties**dialog box.</span></span>  
  
8.  <span data-ttu-id="915a1-123">En el menú **Configuración de extracción de eventos**, haga clic en **Guardar eventos XML de interbloqueo por separado**.</span><span class="sxs-lookup"><span data-stu-id="915a1-123">On the **Events Extraction Settings**tab, click **Save Deadlock XML Events Separately**.</span></span>  
  
9. <span data-ttu-id="915a1-124">En el cuadro de diálogo **Guardar como** , escriba el nombre del archivo donde desee almacenar los eventos deadlock graph.</span><span class="sxs-lookup"><span data-stu-id="915a1-124">In the **Save As** dialog box, enter the name of the file in which to store the deadlock graph events.</span></span>  
  
10. <span data-ttu-id="915a1-125">Haga clic en **Todos los lotes XML de interbloqueo en un solo archivo** para guardar todos los eventos deadlock graph en un solo archivo XML, o bien haga clic en **Cada lote XML de interbloqueo en un archivo independiente**para crear un nuevo archivo XML para cada evento deadlock graph.</span><span class="sxs-lookup"><span data-stu-id="915a1-125">Click **All Deadlock XML batches in a single file** to save all deadlock graph events in a single XML file, or click **Each Deadlock XML batch in a distinct file**to create a new XML file for each deadlock graph.</span></span>  
  
 <span data-ttu-id="915a1-126">Una vez guardado el archivo de interbloqueo, puede abrir el archivo en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="915a1-126">After you have saved the deadlock file, you can open the file in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="915a1-127">Para obtener más información, vea [abrir, ver e imprimir un archivo de Interbloqueo &#40;SQL Server Management Studio&#41;](open-view-and-print-a-deadlock-file-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="915a1-127">For more information, see [Open, View, and Print a Deadlock File &#40;SQL Server Management Studio&#41;](open-view-and-print-a-deadlock-file-sql-server-management-studio.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="915a1-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="915a1-128">See Also</span></span>  
 [<span data-ttu-id="915a1-129">Analizar interbloqueos con SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="915a1-129">Analyze Deadlocks with SQL Server Profiler</span></span>](../../tools/sql-server-profiler/analyze-deadlocks-with-sql-server-profiler.md)  
  
  
