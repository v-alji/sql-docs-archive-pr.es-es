---
title: Guardar eventos Showplan XML por separado (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Showplan XML events
- saving Showplan XML events
- events [SQL Server], Showplan XML
ms.assetid: 33320a7a-36e8-401c-876d-5b82c49abd85
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 240fb408bb3ed8585ecc915ba4829ac21285d241
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677032"
---
# <a name="save-showplan-xml-events-separately-sql-server-profiler"></a><span data-ttu-id="3e043-102">Guardar eventos Showplan XML por separado (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="3e043-102">Save Showplan XML Events Separately (SQL Server Profiler)</span></span>
  <span data-ttu-id="3e043-103">En este tema se describe cómo guardar eventos **Showplan XML** capturados en seguimientos en archivos .SQLPlan distintos mediante el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e043-103">This topic describes how to save **Showplan XML** events that are captured in traces into separate .SQLPlan files by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="3e043-104">Puede abrir los archivos de evento **Showplan XML** en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]para poder ver el plan de ejecución gráfico de cada evento.</span><span class="sxs-lookup"><span data-stu-id="3e043-104">You can open the **Showplan XML** event files in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], which enables you to view the graphical execution plan for each event.</span></span>  
  
### <a name="to-save-showplan-xml-events-separately"></a><span data-ttu-id="3e043-105">Para guardar eventos Showplan XML por separado</span><span class="sxs-lookup"><span data-stu-id="3e043-105">To save Showplan XML events separately</span></span>  
  
1.  <span data-ttu-id="3e043-106">En el menú **Archivo** , haga clic en **Nuevo seguimiento**y, a continuación, conéctese a una instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3e043-106">On the **File** menu, click **New Trace**, and then connect to an instance of SQL Server.</span></span>  
  
     <span data-ttu-id="3e043-107">Aparecerá el cuadro de diálogo **Propiedades de seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="3e043-107">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3e043-108">Si se selecciona **Iniciar el seguimiento inmediatamente tras realizar la conexión**, el cuadro de diálogo **Propiedades de seguimiento**no aparecerá y, en su lugar, se iniciará el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="3e043-108">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear and the trace begins instead.</span></span> <span data-ttu-id="3e043-109">Para desactivar esta configuración, en el menú **Herramientas**, haga clic en **Opciones**y desactive la casilla **Iniciar el seguimiento inmediatamente tras realizar la conexión** .</span><span class="sxs-lookup"><span data-stu-id="3e043-109">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="3e043-110">En el cuadro de diálogo **Propiedades de seguimiento** , en el cuadro **Nombre de seguimiento** , escriba un nombre para el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="3e043-110">In the **Trace Properties** dialog box, type a name for the trace in the **Trace name** box.</span></span>  
  
3.  <span data-ttu-id="3e043-111">En la lista **Usar la plantilla** , seleccione la plantilla de seguimiento que desea utilizar para el seguimiento o seleccione la opción **En blanco** si no desea utilizar ninguna plantilla.</span><span class="sxs-lookup"><span data-stu-id="3e043-111">In the **Use the template** list, select a trace template on which to base the trace, or select **Blank** if you do not want to use a template.</span></span>  
  
4.  <span data-ttu-id="3e043-112">Lleve a cabo una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="3e043-112">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="3e043-113">Active la casilla**Guardar en archivo** para capturar el seguimiento en un archivo.</span><span class="sxs-lookup"><span data-stu-id="3e043-113">Select the**Save to file** check box to capture the trace to a file.</span></span> <span data-ttu-id="3e043-114">Especifique un valor en **Establecer el tamaño máximo de archivo (MB)** .</span><span class="sxs-lookup"><span data-stu-id="3e043-114">Specify a value for **Set maximum file size**.</span></span> <span data-ttu-id="3e043-115">Opcionalmente, active las casillas **Habilitar sustitución incremental de archivos** y **El servidor procesa los datos de seguimiento** .</span><span class="sxs-lookup"><span data-stu-id="3e043-115">Optionally, select the **Enable file rollover** and **Server processes trace data** check boxes.</span></span>  
  
    -   <span data-ttu-id="3e043-116">Active la casilla**Guardar en tabla** para capturar el seguimiento en una tabla de base de datos.</span><span class="sxs-lookup"><span data-stu-id="3e043-116">Select the**Save to table** check box to capture the trace to a database table.</span></span> <span data-ttu-id="3e043-117">De forma opcional, haga clic en **Establecer número máximo de filas (en miles)** y especifique un valor.</span><span class="sxs-lookup"><span data-stu-id="3e043-117">Optionally click **Set maximum rows**, and specify a value.</span></span>  
  
5.  <span data-ttu-id="3e043-118">Opcionalmente, active la casilla **Habilitar hora de detención de seguimiento** para especificar una fecha y hora de detención.</span><span class="sxs-lookup"><span data-stu-id="3e043-118">Optionally, select the **Enable trace stop time** check box, and specify a stop date and time.</span></span>  
  
6.  <span data-ttu-id="3e043-119">Haga clic en la pestaña **Selección de eventos**.</span><span class="sxs-lookup"><span data-stu-id="3e043-119">Click the **Events Selection**tab.</span></span>  
  
7.  <span data-ttu-id="3e043-120">En el cuadro de diálogo **Eventos**, expanda la categoría de evento **Rendimiento**y luego active la casilla **Showplan XML**.</span><span class="sxs-lookup"><span data-stu-id="3e043-120">In the **Events**data column, expand the **Performance**event category, and then select the **Showplan XML**check box.</span></span> <span data-ttu-id="3e043-121">Si la categoría de evento **Rendimiento** no está disponible, active la casilla **Mostrar todos los eventos** para mostrarla.</span><span class="sxs-lookup"><span data-stu-id="3e043-121">If the **Performance** event category is not available, check **Show all events** to display it.</span></span>  
  
     <span data-ttu-id="3e043-122">Aparecerá el cuadro de diálogo **Configuración de extracción de eventos**se agrega al cuadro de diálogo **Propiedades de seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="3e043-122">The **Events Extraction Settings**tab is added to the **Trace Properties**dialog box.</span></span>  
  
8.  <span data-ttu-id="3e043-123">En el menú **Configuración de extracción de eventos**, haga clic en **Guardar eventos de plan de presentación XML por separado**.</span><span class="sxs-lookup"><span data-stu-id="3e043-123">On the **Events Extraction Settings**tab, click **Save XML Showplan events separately**.</span></span>  
  
9. <span data-ttu-id="3e043-124">En el cuadro de diálogo **Guardar como** , especifique el nombre de archivo para guardar los eventos **Showplan XML** .</span><span class="sxs-lookup"><span data-stu-id="3e043-124">In the **Save As** dialog box, enter the name of the file in which to store the **Showplan XML** events.</span></span>  
  
10. <span data-ttu-id="3e043-125">Haga clic en **Todos los lotes de plan de presentación en un solo archivo** para guardar todos los eventos **Showplan XML** en un solo archivo XML, o haga clic en **Cada lote de plan de presentación en un archivo independiente**para crear un archivo XML nuevo para cada evento **Showplan XML** .</span><span class="sxs-lookup"><span data-stu-id="3e043-125">Click **All XML Showplan batches in a single file** to save all **Showplan XML** events in a single XML file, or click **Each XML Showplan batch in a distinct file**to create a new XML file for each **Showplan XML** event.</span></span>  
  
11. <span data-ttu-id="3e043-126">Para ver el archivo del evento **Showplan XML** en SQL Server Management Studio, en el menú **Archivo** , seleccione **Abrir**y haga clic en **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="3e043-126">To view the **Showplan XML** event file in SQL Server Management Studio, on the **File** menu, point to **Open**, and click **File**.</span></span> <span data-ttu-id="3e043-127">Navegue al directorio donde ha guardado el archivo o archivos del evento **Showplan XML** para seleccionar uno y abrirlo.</span><span class="sxs-lookup"><span data-stu-id="3e043-127">Navigate to the directory where you saved the **Showplan XML** event file or files to select one and open it.</span></span> <span data-ttu-id="3e043-128">Los archivos de evento**Showplan XML** tienen la extensión de archivo .SQLPlan.</span><span class="sxs-lookup"><span data-stu-id="3e043-128">**Showplan XML** event files have a .SQLPlan file extension.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e043-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3e043-129">See Also</span></span>  
 [<span data-ttu-id="3e043-130">Analizar consultas con resultados de SHOWPLAN en SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="3e043-130">Analyze Queries with SHOWPLAN Results in SQL Server Profiler</span></span>](../../tools/sql-server-profiler/analyze-queries-with-showplan-results-in-sql-server-profiler.md)  
  
  
