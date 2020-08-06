---
title: Guardar de forma separada eventos Showplan XML Statistics Profile (SQL Server Profiler) | Microsoft Docs
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
ms.assetid: df393f13-d538-4d94-8155-9c2fdf5f755d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: be0c02f8396df81af803c365b9ede42610353ed3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746261"
---
# <a name="save-showplan-xml-statistics-profile-events-separately-sql-server-profiler"></a><span data-ttu-id="f9394-102">Guardar de forma separada eventos Showplan XML Statistics Profile (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="f9394-102">Save Showplan XML Statistics Profile Events Separately (SQL Server Profiler)</span></span>
  <span data-ttu-id="f9394-103">En este tema se describe el modo de guardar eventos **Showplan XML Statistics Profile** capturados en seguimientos en archivos .SQLPlan diferentes mediante el uso del [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9394-103">This topic describes how to save **Showplan XML Statistics Profile** events that are captured in traces into separate .SQLPlan files by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="f9394-104">Puede abrir los archivos de eventos **Showplan XML Statistics Profile** en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], que le permite ver el plan de ejecución gráfico de cada evento.</span><span class="sxs-lookup"><span data-stu-id="f9394-104">You can open the **Showplan XML Statistics Profile** event files in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], which enables you to view the graphical execution plan for each event.</span></span>  
  
### <a name="to-save-showplan-xml-statistics-events-separately"></a><span data-ttu-id="f9394-105">Para guardar eventos Showplan XML Statistics Profile por separado</span><span class="sxs-lookup"><span data-stu-id="f9394-105">To save Showplan XML statistics events separately</span></span>  
  
1.  <span data-ttu-id="f9394-106">En el menú **Archivo** , haga clic en **Nuevo seguimiento**y conéctese a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9394-106">On the **File** menu, click **New Trace**, and then connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="f9394-107">Aparecerá el cuadro de diálogo **Propiedades de seguimiento** .</span><span class="sxs-lookup"><span data-stu-id="f9394-107">The **Trace Properties** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f9394-108">Si activa **Iniciar el seguimiento inmediatamente tras realizar la conexión**, no aparecerá el cuadro de diálogo **Propiedades de seguimiento**y, en su lugar, comenzará el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f9394-108">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box does not appear and the trace begins instead.</span></span> <span data-ttu-id="f9394-109">Para desactivar esta configuración, en el menú **Herramientas**, haga clic en **Opciones**y desactive la casilla **Iniciar el seguimiento inmediatamente tras realizar la conexión** .</span><span class="sxs-lookup"><span data-stu-id="f9394-109">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="f9394-110">En el cuadro de diálogo **Propiedades de seguimiento** , en el cuadro **Nombre de seguimiento** , escriba un nombre para el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f9394-110">In the **Trace Properties** dialog box, type a name for the trace in the **Trace name** box.</span></span>  
  
3.  <span data-ttu-id="f9394-111">En la lista **Usar la plantilla** , seleccione una plantilla de seguimiento o elija **En blanco** si no desea utilizar ninguna plantilla.</span><span class="sxs-lookup"><span data-stu-id="f9394-111">In the **Use the template** list, select a trace template to base the trace on, or select **Blank** if you do not want to use a template.</span></span>  
  
4.  <span data-ttu-id="f9394-112">Lleve a cabo una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="f9394-112">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="f9394-113">Haga clic en**Guardar en el archivo**para capturar el seguimiento en un archivo.</span><span class="sxs-lookup"><span data-stu-id="f9394-113">Click**Save to file**to capture the trace to a file.</span></span> <span data-ttu-id="f9394-114">Especifique un valor en **Establecer el tamaño máximo de archivo (MB)** .</span><span class="sxs-lookup"><span data-stu-id="f9394-114">Specify a value for **Set maximum file size**.</span></span>  
  
         <span data-ttu-id="f9394-115">Opcionalmente, seleccione **Habilitar sustitución incremental de archivos** y el **servidor procesa los datos de seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="f9394-115">Optionally select **Enable file rollover** and **Server processes trace data**.</span></span>  
  
    -   <span data-ttu-id="f9394-116">Haga clic en**Guardar en la tabla** para capturar el seguimiento en una tabla de base de datos.</span><span class="sxs-lookup"><span data-stu-id="f9394-116">Click**Save to table** to capture the trace to a database table.</span></span>  
  
         <span data-ttu-id="f9394-117">De forma opcional, haga clic en **Establecer número máximo de filas (en miles)** y especifique un valor.</span><span class="sxs-lookup"><span data-stu-id="f9394-117">Optionally click **Set maximum rows**, and specify a value.</span></span>  
  
5.  <span data-ttu-id="f9394-118">Opcionalmente, active la casilla **Habilitar hora de detención de seguimiento** y especifique una fecha y hora de detención.</span><span class="sxs-lookup"><span data-stu-id="f9394-118">Optionally select the **Enable trace stop time** check box, and specify a stop date and time.</span></span>  
  
6.  <span data-ttu-id="f9394-119">Haga clic en la pestaña **Selección de eventos**.</span><span class="sxs-lookup"><span data-stu-id="f9394-119">Click the **Events Selection**tab.</span></span>  
  
7.  <span data-ttu-id="f9394-120">En el cuadro de diálogo **Eventos**, expanda la categoría de evento **Rendimiento**y, a continuación, active la casilla **Showplan XML Statistics Profile**.</span><span class="sxs-lookup"><span data-stu-id="f9394-120">In the **Events**data column, expand the **Performance**event category, and then select the **Showplan XML Statistics Profile**check box.</span></span> <span data-ttu-id="f9394-121">Si la categoría de evento **Rendimiento** no está disponible, active la casilla **Mostrar todos los eventos** para mostrarla.</span><span class="sxs-lookup"><span data-stu-id="f9394-121">If the **Performance** event category is not available, check **Show all events** to display it.</span></span>  
  
     <span data-ttu-id="f9394-122">Aparecerá el cuadro de diálogo **Configuración de extracción de eventos**se agrega al cuadro de diálogo **Propiedades de seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="f9394-122">The **Events Extraction Settings**tab is added to the **Trace Properties**dialog.</span></span>  
  
8.  <span data-ttu-id="f9394-123">En el menú **Configuración de extracción de eventos**, haga clic en **Guardar eventos de plan de presentación XML por separado**.</span><span class="sxs-lookup"><span data-stu-id="f9394-123">On the **Events Extraction Settings**tab, click **Save XML Showplan events separately**.</span></span>  
  
9. <span data-ttu-id="f9394-124">En el cuadro de diálogo **Guardar como** , especifique el nombre de archivo para guardar los eventos **Showplan XML Statistics Profile** .</span><span class="sxs-lookup"><span data-stu-id="f9394-124">In the **Save As** dialog box, enter the file name to store the **Showplan XML Statistics Profile** events.</span></span>  
  
10. <span data-ttu-id="f9394-125">Haga clic en **Todos los lotes de plan de presentación en un solo archivo** para guardar todos los eventos **Showplan XML Statistics Profile** en un único archivo XML, o bien haga clic en **Cada lote de plan de presentación en un archivo independiente**para crear un archivo XML para cada evento **Showplan XML Statistics Profile** .</span><span class="sxs-lookup"><span data-stu-id="f9394-125">Click **All batches in a single file** to save all **Showplan XML Statistics Profile** events in a single XML file, or click **Each XML Showplan batch in a distinct file**to create a new XML file for each **Showplan XML Statistics Profile** event.</span></span>  
  
11. <span data-ttu-id="f9394-126">Para ver el archivo del evento **Showplan XML Statistics Profile** en SQL Server Management Studio, en el menú **Archivo** , seleccione **Abrir**y haga clic en **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="f9394-126">To view the **Showplan XML Statistics Profile** event file in SQL Server Management Studio, on the **File** menu, point to **Open**, and click **File**.</span></span> <span data-ttu-id="f9394-127">Diríjase al directorio en que guardó el archivo o archivos de eventos **Showplan XML Statistics Profile** para seleccionar un archivo y abrirlo.</span><span class="sxs-lookup"><span data-stu-id="f9394-127">Navigate to the directory where you saved the **Showplan XML Statistics Profile** event file or files to select one and open it.</span></span> <span data-ttu-id="f9394-128">Los archivos de eventos**Showplan XML Statistics Profile** tienen una extensión de archivo .SQLPlan.</span><span class="sxs-lookup"><span data-stu-id="f9394-128">**Showplan XML Statistics Profile** event files have a .SQLPlan file extension.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9394-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f9394-129">See Also</span></span>  
 [<span data-ttu-id="f9394-130">Analizar consultas con resultados de SHOWPLAN en SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="f9394-130">Analyze Queries with SHOWPLAN Results in SQL Server Profiler</span></span>](../../tools/sql-server-profiler/analyze-queries-with-showplan-results-in-sql-server-profiler.md)  
  
  
