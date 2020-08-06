---
title: Extraer datos mediante el origen de OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- extracting data [Integration Services]
- sources [Integration Services], OLE DB
- OLE DB source [Integration Services]
ms.assetid: 4ca6eeb5-b60e-4b81-86dd-0674be8ae8d8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 352d62cc66e3f17fb10839086e7ee9c5307f1a17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751329"
---
# <a name="extract-data-by-using-the-ole-db-source"></a><span data-ttu-id="d3685-102">Extraer datos mediante el origen de OLE DB</span><span class="sxs-lookup"><span data-stu-id="d3685-102">Extract Data by Using the OLE DB Source</span></span>
  <span data-ttu-id="d3685-103">Para agregar y configurar un origen de OLE DB, el paquete ya debe incluir por lo menos una tarea Flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="d3685-103">To add and configure an OLE DB source, the package must already include at least one Data Flow task.</span></span>  
  
### <a name="to-extract-data-using-an-ole-db-source"></a><span data-ttu-id="d3685-104">Para extraer datos mediante un Origen de OLE DB</span><span class="sxs-lookup"><span data-stu-id="d3685-104">To extract data using an OLE DB Source</span></span>  
  
1.  <span data-ttu-id="d3685-105">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="d3685-105">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="d3685-106">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="d3685-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="d3685-107">Haga clic en la pestaña **Flujo de datos** y, a continuación, desde el **cuadro de herramientas**, arrastre el origen de OLE DB hasta la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="d3685-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the OLE DB source to the design surface.</span></span>  
  
4.  <span data-ttu-id="d3685-108">Haga doble clic en el origen de OLE DB.</span><span class="sxs-lookup"><span data-stu-id="d3685-108">Double-click the OLE DB source.</span></span>  
  
5.  <span data-ttu-id="d3685-109">En el **Editor de origen de OLE DB** , en la página **Administrador de conexiones** , seleccione un administrador de conexiones OLE DB o haga clic en **Nuevo** para crear un nuevo administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="d3685-109">In the **OLE DB Source Editor** dialog box, on the **Connection Manager** page, select an existing OLE DB connection manager or click **New** to create a new connection manager.</span></span> <span data-ttu-id="d3685-110">Para más información, consulte [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="d3685-110">For more information, see [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span></span>  
  
6.  <span data-ttu-id="d3685-111">Seleccione el método de acceso de datos:</span><span class="sxs-lookup"><span data-stu-id="d3685-111">Select the data access method:</span></span>  
  
    -   <span data-ttu-id="d3685-112">**Tabla o vista** Seleccione una tabla o vista en la base de datos a la que se conecta el administrador de conexiones OLE DB.</span><span class="sxs-lookup"><span data-stu-id="d3685-112">**Table or view** Select a table or view in the database to which the OLE DB connection manager connects.</span></span>  
  
    -   <span data-ttu-id="d3685-113">**Variable de nombre de tabla o nombre de vista** Seleccione la variable definida por el usuario que contiene el nombre de una tabla o vista en la base de datos a la que se conecta el administrador de conexiones OLE DB.</span><span class="sxs-lookup"><span data-stu-id="d3685-113">**Table name or view name variable** Select the user-defined variable that contains the name of a table or view in the database to which the OLE DB connection manager connects.</span></span>  
  
    -   <span data-ttu-id="d3685-114">**Comando SQL** Escriba un comando SQL o haga clic en **Generar consulta** para escribir un comando SQL mediante el **Generador de consultas**.</span><span class="sxs-lookup"><span data-stu-id="d3685-114">**SQL command** Type an SQL command or click **Build Query** to write an SQL command using the **Query Builder**.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="d3685-115">El comando puede incluir parámetros.</span><span class="sxs-lookup"><span data-stu-id="d3685-115">The command can include parameters.</span></span> <span data-ttu-id="d3685-116">Para obtener más información, vea [Asignar parámetros de consulta a variables en un componente de flujo de datos](map-query-parameters-to-variables-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="d3685-116">For more information, see [Map Query Parameters to Variables in a Data Flow Component](map-query-parameters-to-variables-in-a-data-flow-component.md).</span></span>  
  
    -   <span data-ttu-id="d3685-117">**Comando SQL de variable** Seleccione la variable definida por el usuario que contiene el comando SQL.</span><span class="sxs-lookup"><span data-stu-id="d3685-117">**SQL command from variable** Select the user-defined variable that contains the SQL command.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="d3685-118">Las variables se deben definir en el ámbito de la misma tarea Flujo de datos que contiene el origen OLE DB, o en el ámbito del mismo paquete. Además, la variable debe tener un tipo de datos de cadena.</span><span class="sxs-lookup"><span data-stu-id="d3685-118">The variables must be defined in the scope of the same Data Flow task that contains the OLE DB source, or in the scope of the same package; additionally, the variable must have a string data type.</span></span>  
  
7.  <span data-ttu-id="d3685-119">Para actualizar la asignación entre las columnas externas y de salida, haga clic en **Columnas** y seleccione diferentes columnas en la lista **Columna externa** .</span><span class="sxs-lookup"><span data-stu-id="d3685-119">To update the mapping between external and output columns, click **Columns** and select different columns in the **External Column** list.</span></span>  
  
8.  <span data-ttu-id="d3685-120">Opcionalmente, actualice los nombres de las columnas de salida modificando los valores en la lista **Columna de salida** .</span><span class="sxs-lookup"><span data-stu-id="d3685-120">Optionally, update the names of output columns by editing values in the **Output Column** list.</span></span>  
  
9. <span data-ttu-id="d3685-121">Para configurar la salida de error, haga clic en **Salida de error**.</span><span class="sxs-lookup"><span data-stu-id="d3685-121">To configure the error output, click **Error Output**.</span></span> <span data-ttu-id="d3685-122">Para más información, vea [Configurar una salida de error en un componente de flujo de datos](../configure-an-error-output-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="d3685-122">For more information, see [Configure an Error Output in a Data Flow Component](../configure-an-error-output-in-a-data-flow-component.md).</span></span>  
  
10. <span data-ttu-id="d3685-123">Puede hacer clic en **Vista previa** para ver hasta 200 filas de los datos extraídos por el origen de OLE DB.</span><span class="sxs-lookup"><span data-stu-id="d3685-123">You can click **Preview** to view up to 200 rows of the data extracted by the OLE DB source.</span></span>  
  
11. <span data-ttu-id="d3685-124">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3685-124">Click **OK**.</span></span>  
  
12. <span data-ttu-id="d3685-125">Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados**, en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="d3685-125">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3685-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d3685-126">See Also</span></span>  
 <span data-ttu-id="d3685-127">[Origen de OLE DB](ole-db-source.md) </span><span class="sxs-lookup"><span data-stu-id="d3685-127">[OLE DB Source](ole-db-source.md) </span></span>  
 <span data-ttu-id="d3685-128">[Transformaciones de Integration Services](transformations/integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="d3685-128">[Integration Services Transformations](transformations/integration-services-transformations.md) </span></span>  
 <span data-ttu-id="d3685-129">[Rutas de Integration Services](integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="d3685-129">[Integration Services Paths](integration-services-paths.md) </span></span>  
 [<span data-ttu-id="d3685-130">Tarea Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="d3685-130">Data Flow Task</span></span>](../control-flow/data-flow-task.md)  
  
  
