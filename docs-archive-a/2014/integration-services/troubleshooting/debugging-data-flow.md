---
title: Depurar el flujo de datos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- progress reporting [Integration Services]
- data viewers [Integration Services]
- data flow [Integration Services], debugging
- debugging [Integration Services], data flow
- counting rows
ms.assetid: 1c574f1b-54f7-4c05-8e42-8620e2c1df0f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ed1d1b7ebb119d452ca3de92fdad47552d1cc36c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747093"
---
# <a name="debugging-data-flow"></a><span data-ttu-id="4247b-102">Depurar el flujo de datos</span><span class="sxs-lookup"><span data-stu-id="4247b-102">Debugging Data Flow</span></span>
  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="4247b-103">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] y el Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] incluyen características y herramientas que puede usar para solucionar los problemas de los flujos de datos en un paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4247b-103">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] and the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer include features and tools that you can use to troubleshoot the data flows in an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package.</span></span>  
  
-   [!INCLUDE[ssIS](../../includes/ssis-md.md)] <span data-ttu-id="4247b-104">proporciona visores de datos.</span><span class="sxs-lookup"><span data-stu-id="4247b-104">Designer provides data viewers.</span></span>  
  
-   [!INCLUDE[ssIS](../../includes/ssis-md.md)] <span data-ttu-id="4247b-105">y las transformaciones de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] proporcionan recuentos de filas.</span><span class="sxs-lookup"><span data-stu-id="4247b-105">Designer and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] transformations provide row counts.</span></span>  
  
-   [!INCLUDE[ssIS](../../includes/ssis-md.md)] <span data-ttu-id="4247b-106">proporciona informes de progreso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4247b-106">Designer provides progress reporting at run time.</span></span>  
  
## <a name="data-viewers"></a><span data-ttu-id="4247b-107">Visores de datos</span><span class="sxs-lookup"><span data-stu-id="4247b-107">Data Viewers</span></span>  
 <span data-ttu-id="4247b-108">Los visores de datos muestran datos entre dos componentes en un flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="4247b-108">Data viewers display data between two components in a data flow.</span></span> <span data-ttu-id="4247b-109">Los visores de datos pueden mostrar datos cuando los datos se extraen de un origen de datos y entran por primera vez en un flujo de datos, antes y después de que una transformación actualice los datos, y antes de que los datos se carguen en su destino.</span><span class="sxs-lookup"><span data-stu-id="4247b-109">Data viewers can display data when the data is extracted from a data source and first enters a data flow, before and after a transformation updates the data, and before the data is loaded into its destination.</span></span>  
  
 <span data-ttu-id="4247b-110">Para ver los datos, se adjuntan visores de datos a la ruta que conecta dos componentes de flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="4247b-110">To view the data, you attach data viewers to the path that connects two data flow components.</span></span> <span data-ttu-id="4247b-111">La capacidad para ver datos entre componentes de flujo de datos hace que sea más fácil identificar valores de datos inesperados, ver la forma en que una transformación cambia los valores de columna y detectar el motivo por el cual una transformación genera errores.</span><span class="sxs-lookup"><span data-stu-id="4247b-111">The ability to view data between data flow components makes it easier to identify unexpected data values, view the way a transformation changes column values, and discover the reason that a transformation fails.</span></span> <span data-ttu-id="4247b-112">Por ejemplo, puede ocurrir que una búsqueda en una tabla de referencia genere un error, y para corregir esto puede ser necesario agregar una transformación que proporcione datos predeterminados para columnas en blanco.</span><span class="sxs-lookup"><span data-stu-id="4247b-112">For example, you may find that a lookup in a reference table fails, and to correct this you may want to add a transformation that provides default data for blank columns.</span></span>  
  
 <span data-ttu-id="4247b-113">Un visor de datos puede mostrar los datos en una cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="4247b-113">A data viewer can display data in a grid.</span></span> <span data-ttu-id="4247b-114">Con una cuadrícula, se seleccionan las columnas que se muestran.</span><span class="sxs-lookup"><span data-stu-id="4247b-114">Using a grid, you select the columns to display.</span></span> <span data-ttu-id="4247b-115">Los valores de las columnas seleccionadas se muestran en formato tabular.</span><span class="sxs-lookup"><span data-stu-id="4247b-115">The values for the selected columns display in a tabular format.</span></span>  
  
 <span data-ttu-id="4247b-116">También puede incluir varios visores de datos en una ruta.</span><span class="sxs-lookup"><span data-stu-id="4247b-116">You can also include multiple data viewers on a path.</span></span> <span data-ttu-id="4247b-117">Puede mostrar los mismos datos en distintos formatos (por ejemplo, crear una vista de gráfico y una vista de cuadrícula de los datos), o bien puede crear varios visores de datos para diferentes columnas de datos.</span><span class="sxs-lookup"><span data-stu-id="4247b-117">You can display the same data in different formats-for example, create a chart view and a grid view of the data-or create different data viewers for different columns of data.</span></span>  
  
 <span data-ttu-id="4247b-118">Cuando se agrega un visor de datos a una ruta, el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] agrega un icono de visor de datos a la superficie de diseño de la pestaña **Flujo de datos** , junto a la ruta.</span><span class="sxs-lookup"><span data-stu-id="4247b-118">When you add a data viewer to a path, [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer adds a data viewer icon to the design surface of the **Data Flow** tab, next to the path.</span></span> <span data-ttu-id="4247b-119">Las transformaciones que pueden tener varias salidas, como la transformación División condicional, pueden incluir un visor de datos en cada ruta.</span><span class="sxs-lookup"><span data-stu-id="4247b-119">Transformations that can have multiple outputs, such as the Conditional Split transformation, can include a data viewer on each path.</span></span>  
  
 <span data-ttu-id="4247b-120">En el tiempo de ejecución, se abre una ventana de **Visor de datos** , que muestra la información especificada por el formato de visor de datos.</span><span class="sxs-lookup"><span data-stu-id="4247b-120">At run time, a **Data Viewer** window opens and displays the information specified by the data viewer format.</span></span> <span data-ttu-id="4247b-121">Por ejemplo, un visor de datos que usa el formato de cuadrícula muestra datos para las columnas seleccionadas, la cantidad de filas de salida que se pasan al componente de flujo de datos y la cantidad de filas que se muestran.</span><span class="sxs-lookup"><span data-stu-id="4247b-121">For example, a data viewer that uses the grid format shows data for the selected columns, the number of output rows passed to the data flow component, and the number of rows displayed.</span></span> <span data-ttu-id="4247b-122">La información muestra cada búfer individualmente y, según el ancho de las filas en el flujo de datos, un búfer puede contener más o menos filas.</span><span class="sxs-lookup"><span data-stu-id="4247b-122">The information displays buffer by buffer and, depending on the width of the rows in the data flow, a buffer may contain more or fewer rows.</span></span>  
  
 <span data-ttu-id="4247b-123">En el cuadro de diálogo **Visor de datos** , puede copiar los datos en el Portapapeles, eliminar todos los datos de la tabla, reconfigurar el visor de datos, reanudar el flujo de datos y separar o adjuntar el visor de datos.</span><span class="sxs-lookup"><span data-stu-id="4247b-123">In the **Data Viewer** dialog box, you can copy the data to the Clipboard, clear all data from the table, reconfigure the data viewer, resume the flow of data, and detach or attach the data viewer.</span></span>  
  
#### <a name="to-add-a-data-viewer"></a><span data-ttu-id="4247b-124">Para agregar un visor de datos</span><span class="sxs-lookup"><span data-stu-id="4247b-124">To add a data viewer</span></span>  
  
-   [<span data-ttu-id="4247b-125">Agregar un visor de datos a un flujo de datos</span><span class="sxs-lookup"><span data-stu-id="4247b-125">Add a Data Viewer to a Data Flow</span></span>](../add-a-data-viewer-to-a-data-flow.md)  
  
## <a name="row-counts"></a><span data-ttu-id="4247b-126">Recuentos de filas</span><span class="sxs-lookup"><span data-stu-id="4247b-126">Row Counts</span></span>  
 <span data-ttu-id="4247b-127">La cantidad de filas que han pasado por una ruta aparece en la superficie de diseño de la pestaña **Flujo de datos** en el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] junto a la ruta.</span><span class="sxs-lookup"><span data-stu-id="4247b-127">The number of rows that have passed through a path is displayed on the design surface of the **Data Flow** tab in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer next to the path.</span></span> <span data-ttu-id="4247b-128">La cantidad se actualiza periódicamente mientras los datos pasan por la ruta.</span><span class="sxs-lookup"><span data-stu-id="4247b-128">The number is updated periodically while the data moves through the path.</span></span>  
  
 <span data-ttu-id="4247b-129">También puede agregar una transformación Recuento de filas al flujo de datos para capturar el recuento de filas final en una variable.</span><span class="sxs-lookup"><span data-stu-id="4247b-129">You can also add a Row Count transformation to the data flow to capture the final row count in a variable.</span></span> <span data-ttu-id="4247b-130">Para más información, consulte [Row Count Transformation](../data-flow/transformations/row-count-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="4247b-130">For more information, see [Row Count Transformation](../data-flow/transformations/row-count-transformation.md).</span></span>  
  
## <a name="progress-reporting"></a><span data-ttu-id="4247b-131">Informes de progreso</span><span class="sxs-lookup"><span data-stu-id="4247b-131">Progress Reporting</span></span>  
 <span data-ttu-id="4247b-132">Al ejecutar un paquete, el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] muestra el progreso en la superficie de diseño en la pestaña **Flujo de datos** , mostrando cada componente de flujo de datos con un color que indica el estado.</span><span class="sxs-lookup"><span data-stu-id="4247b-132">When you run a package, [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer depicts progress on the design surface of the **Data Flow** tab by displaying each data flow component in a color that indicates status.</span></span> <span data-ttu-id="4247b-133">Cuando cada componente empieza a ejecutar su trabajo, cambia de incoloro a amarillo, y cuando termina correctamente, se cambia a verde.</span><span class="sxs-lookup"><span data-stu-id="4247b-133">When each component starts to perform its work, it changes from no color to yellow, and when it finishes successfully, it changes to green.</span></span> <span data-ttu-id="4247b-134">El color rojo indica un error del componente.</span><span class="sxs-lookup"><span data-stu-id="4247b-134">A red color indicates that the component failed.</span></span>  
  
 <span data-ttu-id="4247b-135">En la tabla siguiente se describen los códigos de colores.</span><span class="sxs-lookup"><span data-stu-id="4247b-135">The following table describes the color-coding.</span></span>  
  
|<span data-ttu-id="4247b-136">Color</span><span class="sxs-lookup"><span data-stu-id="4247b-136">Color</span></span>|<span data-ttu-id="4247b-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="4247b-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4247b-138">Sin color</span><span class="sxs-lookup"><span data-stu-id="4247b-138">No color</span></span>|<span data-ttu-id="4247b-139">Espera la llamada del motor de flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="4247b-139">Waiting to be called by the data flow engine.</span></span>|  
|<span data-ttu-id="4247b-140">Amarillo</span><span class="sxs-lookup"><span data-stu-id="4247b-140">Yellow</span></span>|<span data-ttu-id="4247b-141">Ejecución de una transformación, extracción de datos o carga de datos.</span><span class="sxs-lookup"><span data-stu-id="4247b-141">Performing a transformation, extracting data, or loading data.</span></span>|  
|<span data-ttu-id="4247b-142">Verde</span><span class="sxs-lookup"><span data-stu-id="4247b-142">Green</span></span>|<span data-ttu-id="4247b-143">Ejecución correcta.</span><span class="sxs-lookup"><span data-stu-id="4247b-143">Ran successfully.</span></span>|  
|<span data-ttu-id="4247b-144">rojo</span><span class="sxs-lookup"><span data-stu-id="4247b-144">red</span></span>|<span data-ttu-id="4247b-145">Ejecución con errores.</span><span class="sxs-lookup"><span data-stu-id="4247b-145">Ran with errors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4247b-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4247b-146">See Also</span></span>  
 [<span data-ttu-id="4247b-147">Herramientas para solucionar problemas con el desarrollo de paquetes</span><span class="sxs-lookup"><span data-stu-id="4247b-147">Troubleshooting Tools for Package Development</span></span>](troubleshooting-tools-for-package-development.md)  
  
  
