---
title: Agregar un visor de datos a un flujo de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- data viewers [Integration Services]
- data flow [Integration Services], data viewers
- adding data viewers
ms.assetid: 5e573274-a170-4132-bfc8-a8ff3a8411e4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7abd76417552ec50da736afe024a5ae36ee6a2ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663058"
---
# <a name="add-a-data-viewer-to-a-data-flow"></a><span data-ttu-id="1ed0a-102">agregar un visor de datos a un flujo de datos</span><span class="sxs-lookup"><span data-stu-id="1ed0a-102">Add a Data Viewer to a Data Flow</span></span>
  <span data-ttu-id="1ed0a-103">En este tema se describe cómo agregar y configurar un visor de datos en un flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="1ed0a-103">This topic describes how to add and configure a data viewer in a data flow.</span></span> <span data-ttu-id="1ed0a-104">Un visor de datos muestra los datos que se mueven entre dos componentes de flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="1ed0a-104">A data viewer displays data that is moving between two data flow components.</span></span> <span data-ttu-id="1ed0a-105">Por ejemplo, un visor de datos puede mostrar los datos que se extraen de un origen de datos antes de que una transformación en el flujo de datos los modifique.</span><span class="sxs-lookup"><span data-stu-id="1ed0a-105">For example, a data viewer can display the data that is extracted from a data source before a transformation in the data flow modifies the data.</span></span>  
  
 <span data-ttu-id="1ed0a-106">Una ruta de acceso conecta componentes de un flujo de datos conectando la salida de un componente de flujo de datos con la entrada de otro componente.</span><span class="sxs-lookup"><span data-stu-id="1ed0a-106">A path connects components in a data flow by connecting the output of one data flow component to the input of another component.</span></span>  
  
 <span data-ttu-id="1ed0a-107">Para poder agregar visores de datos a un paquete, éste debe incluir una tarea Flujo de datos y al menos dos componentes de flujo de datos conectados.</span><span class="sxs-lookup"><span data-stu-id="1ed0a-107">Before you can add data viewers to a package, the package must include a Data Flow task and at least two data flow components that are connected.</span></span>  
  
### <a name="to-add-a-data-viewer-to-a-data-flow"></a><span data-ttu-id="1ed0a-108">Para agregar un visor de datos a un flujo de datos</span><span class="sxs-lookup"><span data-stu-id="1ed0a-108">To add a data viewer to a data flow</span></span>  
  
1.  <span data-ttu-id="1ed0a-109">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="1ed0a-109">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="1ed0a-110">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="1ed0a-110">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="1ed0a-111">Haga clic en la pestaña **Flujo de control** , si aún no está activo.</span><span class="sxs-lookup"><span data-stu-id="1ed0a-111">Click the **Control Flow** tab, if it is not already active.</span></span>  
  
4.  <span data-ttu-id="1ed0a-112">Haga clic en la tarea Flujo de datos que contiene el flujo de datos al que desee adjuntar un visor de datos y, a continuación, haga clic en la pestaña **Flujo de datos** .</span><span class="sxs-lookup"><span data-stu-id="1ed0a-112">Click the Data Flow task to whose data flow you want to attach a data viewer and then click the **Data Flow** tab.</span></span>  
  
5.  <span data-ttu-id="1ed0a-113">Haga clic con el botón derecho en una ruta entre dos componentes de flujo de datos y, después, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="1ed0a-113">Right-click a path between two data flow components, and click **Edit**.</span></span>  
  
6.  <span data-ttu-id="1ed0a-114">En la página **General** puede ver y editar propiedades de ruta.</span><span class="sxs-lookup"><span data-stu-id="1ed0a-114">On the **General** page, you can view and edit path properties.</span></span> <span data-ttu-id="1ed0a-115">Por ejemplo, en la lista desplegable **PathAnnotation** puede seleccionar la anotación que aparece junto a la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="1ed0a-115">For example, from the **PathAnnotation** drop-down list you can select the annotation that appears next to the path.</span></span>  
  
7.  <span data-ttu-id="1ed0a-116">En la página **Metadatos** puede ver los metadatos de columna y copiar los metadatos al Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="1ed0a-116">On the **Metadata** page, you can view the column metadata and copy the metadata to the Clipboard.</span></span>  
  
8.  <span data-ttu-id="1ed0a-117">En la página **Visor de datos** , haga clic en **Habilitar visor de datos**.</span><span class="sxs-lookup"><span data-stu-id="1ed0a-117">On the **Data Viewer** page, click **Enable data viewer**.</span></span>  
  
9. <span data-ttu-id="1ed0a-118">En el área Columnas que se mostrarán, seleccione las columnas que desee mostrar en el visor de datos.</span><span class="sxs-lookup"><span data-stu-id="1ed0a-118">In the Columns to display area, select the columns you want to display in the data viewer.</span></span> <span data-ttu-id="1ed0a-119">De forma predeterminada, todas las columnas disponibles aparecen seleccionadas y en la lista **Columnas mostradas** .</span><span class="sxs-lookup"><span data-stu-id="1ed0a-119">By default, all the available columns are selected and listed in the **Displayed Columns** list.</span></span> <span data-ttu-id="1ed0a-120">Mueva las columnas que no desee utilizar a la lista **Columnas sin usar** , seleccionándolas y haciendo clic en la flecha hacia la izquierda.</span><span class="sxs-lookup"><span data-stu-id="1ed0a-120">Move columns that you do not want to use to the **Unused Column** list by selecting them and then clicking the left arrow.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1ed0a-121">En la cuadrícula, los valores que representan los tipos de datos DT_DATE, DT_DBTIME2, DT_FILETIME, DT_DBTIMESTAMP, DT_DBTIMESTAMP2 y DT_DBTIMESTAMPOFFSET aparecen como cadenas con formato ISO 8601 y un espacio separador reemplaza el separador `T`.</span><span class="sxs-lookup"><span data-stu-id="1ed0a-121">In the grid, values that represent the DT_DATE, DT_DBTIME2, DT_FILETIME, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, and DT_DBTIMESTAMPOFFSET data types appear as ISO 8601 formatted strings and a space separator replaces the `T` separator.</span></span> <span data-ttu-id="1ed0a-122">Los valores que representan los tipos de datos DT_DATE y DT_FILETIME incluyen siete dígitos para las fracciones de segundo.</span><span class="sxs-lookup"><span data-stu-id="1ed0a-122">Values that represent the DT_DATE and DT_FILETIME data types include seven digits for fractional seconds.</span></span> <span data-ttu-id="1ed0a-123">Dado que el tipo de datos DT_FILETIME almacena solamente tres dígitos de fracciones de segundo, la cuadrícula muestra ceros para los cuatro dígitos restantes.</span><span class="sxs-lookup"><span data-stu-id="1ed0a-123">Because the DT_FILETIME data type stores only three digits of fractional seconds, the grid displays zeros for the remaining four digits.</span></span> <span data-ttu-id="1ed0a-124">Los valores que representan el tipo de datos DT_DBTIMESTAMP incluyen tres dígitos para las fracciones de segundo.</span><span class="sxs-lookup"><span data-stu-id="1ed0a-124">Values that represent the DT_DBTIMESTAMP data type include three digits for fractional seconds.</span></span> <span data-ttu-id="1ed0a-125">Para los valores que representan los tipos de datos DT_DBTIME2, DT_DBTIMESTAMP2 y DT_DBTIMESTAMPOFFSET, el número de dígitos de las fracciones de segundo corresponde a la escala especificada para el tipo de datos de la columna.</span><span class="sxs-lookup"><span data-stu-id="1ed0a-125">For values that represent the DT_DBTIME2, DT_DBTIMESTAMP2, and DT_DBTIMESTAMPOFFSET data types, the number of digits for fractional seconds corresponds to the scale specified for the column's data type.</span></span> <span data-ttu-id="1ed0a-126">Para obtener más información acerca de los formatos ISO 8601, vea [Date and Time Formats](../../2014/integration-services/date-and-time-formats.md).</span><span class="sxs-lookup"><span data-stu-id="1ed0a-126">For more information about ISO 8601 formats, see [Date and Time Formats](../../2014/integration-services/date-and-time-formats.md).</span></span> <span data-ttu-id="1ed0a-127">Para obtener más información acerca de los tipos de datos, vea [Integration Services Data Types](data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="1ed0a-127">For more information about data types, see [Integration Services Data Types](data-flow/integration-services-data-types.md).</span></span>  
  
10. <span data-ttu-id="1ed0a-128">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="1ed0a-128">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ed0a-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1ed0a-129">See Also</span></span>  
 <span data-ttu-id="1ed0a-130">[Transformaciones de Integration Services](data-flow/transformations/integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="1ed0a-130">[Integration Services Transformations](data-flow/transformations/integration-services-transformations.md) </span></span>  
 <span data-ttu-id="1ed0a-131">[Rutas de Integration Services](data-flow/integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="1ed0a-131">[Integration Services Paths](data-flow/integration-services-paths.md) </span></span>  
 <span data-ttu-id="1ed0a-132">[Flujo de datos](data-flow/data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="1ed0a-132">[Data Flow](data-flow/data-flow.md) </span></span>  
 [<span data-ttu-id="1ed0a-133">Depurar el flujo de datos</span><span class="sxs-lookup"><span data-stu-id="1ed0a-133">Debugging Data Flow</span></span>](troubleshooting/debugging-data-flow.md)  
  
  
