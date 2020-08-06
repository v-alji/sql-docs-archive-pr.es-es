---
title: Extraer datos mediante el origen de ODBC | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 10f25703-49a2-4d45-abab-6b4da2a57ba5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c05efe2b0479047280fc093ee555e037c77d82e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751330"
---
# <a name="extract-data-by-using-the-odbc-source"></a><span data-ttu-id="db80a-102">Extraer datos mediante el origen de ODBC</span><span class="sxs-lookup"><span data-stu-id="db80a-102">Extract Data by Using the ODBC Source</span></span>
  <span data-ttu-id="db80a-103">Este procedimiento describe cómo extraer datos mediante un origen ODBC.</span><span class="sxs-lookup"><span data-stu-id="db80a-103">This procedure describes how to extract data by using an ODBC source.</span></span> <span data-ttu-id="db80a-104">Para agregar y configurar un origen ODBC, el paquete ya debe incluir por lo menos una tarea Flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="db80a-104">To add and configure an ODBC source, the package must already include at least one Data Flow task.</span></span>  
  
### <a name="to-extract-data-using-an-odbc-source"></a><span data-ttu-id="db80a-105">Para extraer datos mediante un origen ODBC</span><span class="sxs-lookup"><span data-stu-id="db80a-105">To extract data using an ODBC source</span></span>  
  
1.  <span data-ttu-id="db80a-106">En [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], abra el paquete de [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] que desee.</span><span class="sxs-lookup"><span data-stu-id="db80a-106">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] package you want.</span></span>  
  
2.  <span data-ttu-id="db80a-107">Haga clic en la pestaña **Flujo de datos** y, a continuación, desde el **cuadro de herramientas**, arrastre el origen ODBC a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="db80a-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the ODBC source to the design surface.</span></span>  
  
3.  <span data-ttu-id="db80a-108">Haga doble clic en el origen ODBC.</span><span class="sxs-lookup"><span data-stu-id="db80a-108">Double-click the ODBC source.</span></span>  
  
4.  <span data-ttu-id="db80a-109">En el cuadro de diálogo **Editor de origen ODBC** , en la página **Administrador de conexiones** , seleccione un administrador de conexiones ODBC o haga clic en **Nuevo** para crear un nuevo administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="db80a-109">In the **ODBC Source Editor** dialog box, on the **Connection Manager** page, select an existing ODBC connection manager or click **New** to create a new connection manager.</span></span>  
  
5.  <span data-ttu-id="db80a-110">Seleccione el método de acceso de datos.</span><span class="sxs-lookup"><span data-stu-id="db80a-110">Select the data access method.</span></span>  
  
    -   <span data-ttu-id="db80a-111">**Nombre de la tabla**: seleccione una tabla o vista en la base de datos o escriba una expresión regular para identificar la tabla con la que el administrador de conexiones ODBC se conecta.</span><span class="sxs-lookup"><span data-stu-id="db80a-111">**Table Name**: Select a table or view in the database or type a regular expression to identify the table to which the ODBC connection manager connects.</span></span>  
  
         <span data-ttu-id="db80a-112">Esta lista contiene solo las 1000 primeras tablas.</span><span class="sxs-lookup"><span data-stu-id="db80a-112">This list contains the first 1000 tables only.</span></span> <span data-ttu-id="db80a-113">Si la base de datos contiene más de 1000 tablas, puede escribir el principio de un nombre de tabla o usar el comodín (\*) para escribir cualquier parte del nombre con el fin de mostrar la tabla o las tablas que desea usar.</span><span class="sxs-lookup"><span data-stu-id="db80a-113">If your database contains more than 1000 tables, you can type the beginning of a table name or use the (\*) wild card to enter any part of the name to display the table or tables you want to use.</span></span>  
  
    -   <span data-ttu-id="db80a-114">**Comando SQL**: escriba un comando SQL o haga clic en **Examinar** para cargar la consulta SQL desde un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="db80a-114">**SQL Command**: Type an SQL Command or click **Browse** to load the SQL query from a text file.</span></span>  
  
6.  <span data-ttu-id="db80a-115">Puede hacer clic en **Vista previa** para ver hasta 200 filas de los datos extraídos por el origen ODBC.</span><span class="sxs-lookup"><span data-stu-id="db80a-115">You can click **Preview** to view up to 200 rows of the data extracted by the ODBC source.</span></span>  
  
7.  <span data-ttu-id="db80a-116">Para actualizar la asignación entre las columnas externas y de salida, haga clic en **Columnas** y seleccione diferentes columnas en la lista **Columna externa** .</span><span class="sxs-lookup"><span data-stu-id="db80a-116">To update the mapping between external and output columns, click **Columns** and select different columns in the **External Column** list.</span></span>  
  
8.  <span data-ttu-id="db80a-117">Si es necesario actualice los nombres de las columnas de salida modificando los valores en la lista **Columna de salida** .</span><span class="sxs-lookup"><span data-stu-id="db80a-117">If necessary, update the names of output columns by editing values in the **Output Column** list.</span></span>  
  
9. <span data-ttu-id="db80a-118">Para configurar la salida de error, haga clic en **Salida de error**.</span><span class="sxs-lookup"><span data-stu-id="db80a-118">To configure the error output, click **Error Output**.</span></span>  
  
10. <span data-ttu-id="db80a-119">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="db80a-119">Click **OK**.</span></span>  
  
11. <span data-ttu-id="db80a-120">Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados**, en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="db80a-120">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db80a-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="db80a-121">See Also</span></span>  
 <span data-ttu-id="db80a-122">[Editor de orígenes ODBC &#40;página Administrador de conexiones&#41;](../odbc-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="db80a-122">[ODBC Source Editor &#40;Connection Manager Page&#41;](../odbc-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="db80a-123">[Editor de orígenes ODBC &#40;página Columnas&#41;](../odbc-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="db80a-123">[ODBC Source Editor &#40;Columns Page&#41;](../odbc-source-editor-columns-page.md) </span></span>  
 [<span data-ttu-id="db80a-124">Editor de orígenes ODBC &#40;página Salida de error&#41;</span><span class="sxs-lookup"><span data-stu-id="db80a-124">ODBC Source Editor &#40;Error Output Page&#41;</span></span>](../odbc-source-editor-error-output-page.md)  
  
  
