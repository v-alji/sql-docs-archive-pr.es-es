---
title: Cargar datos mediante el destino de ODBC | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 339ec0a8-922e-48c0-97b3-fc5ee34f95e3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e8bf0b30619c2886df6ddb28858cf98bad858421
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745927"
---
# <a name="load-data-by-using-the-odbc-destination"></a><span data-ttu-id="ae1d1-102">Cargar datos mediante el destino de ODBC</span><span class="sxs-lookup"><span data-stu-id="ae1d1-102">Load Data by Using the ODBC Destination</span></span>
  <span data-ttu-id="ae1d1-103">Este procedimiento muestra cómo cargar datos mediante el destino ODBC.</span><span class="sxs-lookup"><span data-stu-id="ae1d1-103">This procedure shows how to load data by using the ODBC destination.</span></span> <span data-ttu-id="ae1d1-104">Para agregar y configurar un destino ODBC el paquete ya debe incluir al menos una tarea Flujo de datos y un origen.</span><span class="sxs-lookup"><span data-stu-id="ae1d1-104">To add and configure an ODBC destination, the package must already include at least one Data Flow task and source.</span></span>  
  
### <a name="to-load-data-using-an-odbc-destination"></a><span data-ttu-id="ae1d1-105">Para cargar datos mediante un destino ODBC</span><span class="sxs-lookup"><span data-stu-id="ae1d1-105">To load data using an ODBC destination</span></span>  
  
1.  <span data-ttu-id="ae1d1-106">En [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], abra el paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que desee.</span><span class="sxs-lookup"><span data-stu-id="ae1d1-106">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package you want.</span></span>  
  
2.  <span data-ttu-id="ae1d1-107">Haga clic en la pestaña **Flujo de datos** y, a continuación, desde el **cuadro de herramientas**, arrastre el destino ODBC a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="ae1d1-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the ODBC destination to the design surface.</span></span>  
  
3.  <span data-ttu-id="ae1d1-108">Arrastre una salida disponible de un componente de flujo de datos a la entrada del destino ODBC.</span><span class="sxs-lookup"><span data-stu-id="ae1d1-108">Drag an available output of a data flow component to the input of the ODBC destination.</span></span>  
  
4.  <span data-ttu-id="ae1d1-109">Haga doble clic en el destino ODBC.</span><span class="sxs-lookup"><span data-stu-id="ae1d1-109">Double-click the ODBC destination.</span></span>  
  
5.  <span data-ttu-id="ae1d1-110">En el **Editor de destino ODBC** , en la página **Administrador de conexiones** , seleccione un administrador de conexiones ODBC o haga clic en **Nuevo** para crear un nuevo administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="ae1d1-110">In the **ODBC Destination Editor** dialog box, on the **Connection Manager** page, select an existing ODBC connection manager or click **New** to create a new connection manager.</span></span>  
  
6.  <span data-ttu-id="ae1d1-111">Seleccione el método de acceso de datos.</span><span class="sxs-lookup"><span data-stu-id="ae1d1-111">Select the data access method.</span></span>  
  
    -   <span data-ttu-id="ae1d1-112">**Nombre de tabla - lote**: seleccione esta opción para configurar el destino ODBC para trabajar en modo de lote.</span><span class="sxs-lookup"><span data-stu-id="ae1d1-112">**Table Name - Batch**: Select this option to configure the ODBC destination to work in batch mode.</span></span> <span data-ttu-id="ae1d1-113">Al seleccionar esta opción, puede establecer el **Tamaño de lote**.</span><span class="sxs-lookup"><span data-stu-id="ae1d1-113">When you select this option, you can set the **Batch size**.</span></span>  
  
    -   <span data-ttu-id="ae1d1-114">**Nombre de tabla - fila a fila**: seleccione esta opción para configurar el destino ODBC para que cada una de las filas se inserte en la tabla de destino una por una.</span><span class="sxs-lookup"><span data-stu-id="ae1d1-114">**Table Name - Row by Row**: Select this option to configure the ODBC destination to insert each of the rows into the destination table one at a time.</span></span> <span data-ttu-id="ae1d1-115">Al seleccionar esta opción, los datos se cargan en la tabla una fila cada vez.</span><span class="sxs-lookup"><span data-stu-id="ae1d1-115">When you select this option, the data is loaded into the table one row at a time.</span></span>  
  
7.  <span data-ttu-id="ae1d1-116">En el campo **Nombre de la tabla o la vista** , seleccione una tabla o vista disponible desde la base de datos de la lista o escriba una expresión regular para identificar la tabla. Esta lista contiene solo las 1000 primeras tablas.</span><span class="sxs-lookup"><span data-stu-id="ae1d1-116">In the **Name of the table or the view** field, select an available table or view from the database from the list or type in a regular expression to identify the table.This list contains the first 1000 tables only.</span></span> <span data-ttu-id="ae1d1-117">Si la base de datos contiene más de 1000 tablas, puede escribir el principio de un nombre de tabla o usar el comodín (\*) para escribir cualquier parte del nombre con el fin de mostrar la tabla o las tablas que desea usar.</span><span class="sxs-lookup"><span data-stu-id="ae1d1-117">If your database contains more than 1000 tables, you can type the beginning of a table name or use the (\*) wild card to enter any part of the name to display the table or tables you want to use.</span></span>  
  
8.  <span data-ttu-id="ae1d1-118">Puede hacer clic en **Vista previa** para ver hasta 200 filas de datos de la tabla seleccionada en el destino ODBC.</span><span class="sxs-lookup"><span data-stu-id="ae1d1-118">You can click **Preview** to view up to 200 rows of the data from the table selected in the ODBC destination.</span></span>  
  
9. <span data-ttu-id="ae1d1-119">Haga clic en **Asignaciones** y asigne columnas de la lista **Columnas de entrada disponibles** a columnas en la lista **Columnas de destino disponibles** arrastrando columnas de una lista a otra.</span><span class="sxs-lookup"><span data-stu-id="ae1d1-119">Click **Mappings** and then map columns from the **Available Input Columns** list to columns in the **Available Destination Columns** list by dragging columns from one list to another.</span></span>  
  
10. <span data-ttu-id="ae1d1-120">Para configurar la salida de error, haga clic en **Salida de error**.</span><span class="sxs-lookup"><span data-stu-id="ae1d1-120">To configure the error output, click **Error Output**.</span></span>  
  
11. <span data-ttu-id="ae1d1-121">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae1d1-121">Click **OK**.</span></span>  
  
12. <span data-ttu-id="ae1d1-122">Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados**, en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="ae1d1-122">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae1d1-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ae1d1-123">See Also</span></span>  
 <span data-ttu-id="ae1d1-124">[Editor de destino de ODBC &#40;página Administrador de conexiones&#41;](../odbc-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="ae1d1-124">[ODBC Destination Editor &#40;Connection Manager Page&#41;](../odbc-destination-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="ae1d1-125">[Editor de destino de ODBC &#40;página Asignaciones&#41;](../odbc-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="ae1d1-125">[ODBC Destination Editor &#40;Mappings Page&#41;](../odbc-destination-editor-mappings-page.md) </span></span>  
 [<span data-ttu-id="ae1d1-126">Editor de orígenes ODBC &#40;página Salida de error&#41;</span><span class="sxs-lookup"><span data-stu-id="ae1d1-126">ODBC Source Editor &#40;Error Output Page&#41;</span></span>](../odbc-source-editor-error-output-page.md)  
  
  
