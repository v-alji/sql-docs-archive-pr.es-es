---
title: Configurar la transformación comando de OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- parameters [Integration Services]
- OLE DB Command transformation
ms.assetid: c800f167-3d2e-4c10-8ba3-a02f1872ccea
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d1714a6b798c6d8256052fd3c16bd86182480bcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748874"
---
# <a name="configure-the-ole-db-command-transformation"></a><span data-ttu-id="9e85e-102">Configurar la transformación Comando de OLE DB</span><span class="sxs-lookup"><span data-stu-id="9e85e-102">Configure the OLE DB Command Transformation</span></span>
  <span data-ttu-id="9e85e-103">Para agregar y configurar una transformación Comando de OLE DB, el paquete ya debe incluir por lo menos una tarea Flujo de datos y un origen tal como origen de archivo plano y un origen de OLE DB.</span><span class="sxs-lookup"><span data-stu-id="9e85e-103">To add and configure an OLE DB Command transformation, the package must already include at least one Data Flow task and a source such as a Flat File source or an OLE DB source.</span></span> <span data-ttu-id="9e85e-104">Esta transformación normalmente se usa para ejecutar consultas con parámetros.</span><span class="sxs-lookup"><span data-stu-id="9e85e-104">This transformation is typically used for running parameterized queries.</span></span>  
  
### <a name="to-configure-the-ole-db-command-transformation"></a><span data-ttu-id="9e85e-105">Para configurar la transformación Comando de OLE DB</span><span class="sxs-lookup"><span data-stu-id="9e85e-105">To configure the OLE DB Command transformation</span></span>  
  
1.  <span data-ttu-id="9e85e-106">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="9e85e-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="9e85e-107">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="9e85e-107">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="9e85e-108">Haga clic en la pestaña **Flujo de datos** y, a continuación, desde el **cuadro de herramientas**, arrastre la transformación Comando de OLE DB a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="9e85e-108">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the OLE DB Command transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="9e85e-109">Conecte la transformación Comando de OLE DB al flujo de datos; para hacerlo, arrastre el conector (la flecha verde o roja) desde un origen de datos o una transformación anterior a la transformación Comando de OLE DB.</span><span class="sxs-lookup"><span data-stu-id="9e85e-109">Connect the OLE DB Command transformation to the data flow by dragging a connector-the green or red arrow-from a data source or a previous transformation to the OLE DB Command transformation.</span></span>  
  
5.  <span data-ttu-id="9e85e-110">Haga clic con el botón derecho en el componente y seleccione Editar o Mostrar el **Editor avanzado**.</span><span class="sxs-lookup"><span data-stu-id="9e85e-110">Right-click the component and select Edit or Show **Advanced Editor**.</span></span>  
  
6.  <span data-ttu-id="9e85e-111">En la pestaña **Administradores de conexión** , seleccione un administrador de conexiones OLE DB en la lista **Administrador de conexiones** .</span><span class="sxs-lookup"><span data-stu-id="9e85e-111">On the **Connection Managers** tab, select an OLE DB connection manager in the **Connection Manager** list.</span></span> <span data-ttu-id="9e85e-112">Para más información, consulte [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="9e85e-112">For more information, see [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md).</span></span>  
  
7.  <span data-ttu-id="9e85e-113">Haga clic en la pestaña **Propiedades de componente** y haga clic en el botón de puntos suspensivos **(…)** del cuadro **SqlCommand**.</span><span class="sxs-lookup"><span data-stu-id="9e85e-113">Click the **Component Properties** tab and click the ellipsis button **(...)** in the **SqlCommand** box.</span></span>  
  
8.  <span data-ttu-id="9e85e-114">En el **Editor de valores de cadena**, escriba la instrucción SQL con parámetros mediante un signo de pregunta (?) como marcador de parámetro para cada parámetro.</span><span class="sxs-lookup"><span data-stu-id="9e85e-114">In the **String Value Editor**, type the parameterized SQL statement using a question mark (?) as the parameter marker for each parameter.</span></span>  
  
9. <span data-ttu-id="9e85e-115">Haga clic en **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="9e85e-115">Click **Refresh**.</span></span> <span data-ttu-id="9e85e-116">Cuando hace clic en **Actualizar**, la transformación crea una columna para cada parámetro en la colección de columnas externas y establece la propiedad DBParamInfoFlags.</span><span class="sxs-lookup"><span data-stu-id="9e85e-116">When you click **Refresh**, the transformation creates a column for each parameter in the External Columns collection and sets the DBParamInfoFlags property.</span></span>  
  
10. <span data-ttu-id="9e85e-117">Haga clic en la pestaña **Propiedades de entrada y salida** .</span><span class="sxs-lookup"><span data-stu-id="9e85e-117">Click the **Input and Output Properties** tab.</span></span>  
  
11. <span data-ttu-id="9e85e-118">Expanda **Entrada de comando de OLE DB**y luego expanda **Columnas externas**.</span><span class="sxs-lookup"><span data-stu-id="9e85e-118">Expand **OLE DB Command Input**, and then expand **External Columns**.</span></span>  
  
12. <span data-ttu-id="9e85e-119">Compruebe que **Columnas externas** enumera una columna para cada parámetro en la instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="9e85e-119">Verify that **External Columns** lists a column for each parameter in the SQL statement.</span></span> <span data-ttu-id="9e85e-120">Los nombres de columna son **Param_0**, **Param_1**, etc.</span><span class="sxs-lookup"><span data-stu-id="9e85e-120">The column names are **Param_0**, **Param_1**, and so on.</span></span>  
  
     <span data-ttu-id="9e85e-121">No debe cambiar los nombres de las columnas.</span><span class="sxs-lookup"><span data-stu-id="9e85e-121">You should not change the column names.</span></span> <span data-ttu-id="9e85e-122">Si lo hace, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] generará un error de validación para la transformación Comando de OLE DB.</span><span class="sxs-lookup"><span data-stu-id="9e85e-122">If you change the column names, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] generates a validation error for the OLE DB Command transformation.</span></span>  
  
     <span data-ttu-id="9e85e-123">Además, tampoco debe cambiar el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="9e85e-123">Also, you should not change the data type.</span></span> <span data-ttu-id="9e85e-124">La propiedad DataType de cada columna se establece en el tipo de datos correcto.</span><span class="sxs-lookup"><span data-stu-id="9e85e-124">The DataType property of each column is set to the correct data type.</span></span>  
  
13. <span data-ttu-id="9e85e-125">Si **Columnas externas** no enumera ninguna columna, debe agregarlas manualmente.</span><span class="sxs-lookup"><span data-stu-id="9e85e-125">If **External Columns** lists no columns you must add them manually.</span></span>  
  
    -   <span data-ttu-id="9e85e-126">Haga clic en **Agregar columna** una vez por cada parámetro de la instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="9e85e-126">Click **Add Column** one time for each parameter in the SQL statement.</span></span>  
  
    -   <span data-ttu-id="9e85e-127">Actualice los nombres de columna a **Param_0**, **Param_1**, etc.</span><span class="sxs-lookup"><span data-stu-id="9e85e-127">Update the column names to **Param_0**, **Param_1**, and so on.</span></span>  
  
    -   <span data-ttu-id="9e85e-128">Especifique un valor en la propiedad DBParamInfoFlags.</span><span class="sxs-lookup"><span data-stu-id="9e85e-128">Specify a value in the DBParamInfoFlags property.</span></span> <span data-ttu-id="9e85e-129">El valor debe coincidir con el valor de la enumeración OLE DB DBPARAMFLAGSENUM.</span><span class="sxs-lookup"><span data-stu-id="9e85e-129">The value must match a value in the OLE DB DBPARAMFLAGSENUM enumeration.</span></span> <span data-ttu-id="9e85e-130">Para obtener más información, vea la documentación de referencia de OLE DB.</span><span class="sxs-lookup"><span data-stu-id="9e85e-130">For more information, see the OLE DB reference documentation.</span></span>  
  
    -   <span data-ttu-id="9e85e-131">Especifique el tipo de datos de la columna y, según el tipo de datos, especifique la página de códigos, longitud, precisión y escala de la columna.</span><span class="sxs-lookup"><span data-stu-id="9e85e-131">Specify the data type of the column and, depending on the data type, specify the code page, length, precision, and scale of the column.</span></span>  
  
    -   <span data-ttu-id="9e85e-132">Para eliminar un parámetro sin usar, seleccione el parámetro en **Columnas externas**y luego haga clic en **Quitar columna**.</span><span class="sxs-lookup"><span data-stu-id="9e85e-132">To delete an unused parameter, select the parameter in **External Columns**, and then click **Remove Column**.</span></span>  
  
    -   <span data-ttu-id="9e85e-133">Haga clic en **Asignaciones de columnas** y asigne las columnas de la lista **Columnas de entrada disponibles** a parámetros de la lista **Columnas de destino disponibles** .</span><span class="sxs-lookup"><span data-stu-id="9e85e-133">Click **Column Mappings** and map columns in the **Available Input Columns** list to parameters in the **Available Destination Columns** list.</span></span>  
  
14. <span data-ttu-id="9e85e-134">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="9e85e-134">Click **OK**.</span></span>  
  
15. <span data-ttu-id="9e85e-135">Para guardar el paquete actualizado, haga clic en **Guardar** en el menú **Archivo** .</span><span class="sxs-lookup"><span data-stu-id="9e85e-135">To save the updated package, click **Save** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e85e-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9e85e-136">See Also</span></span>  
 <span data-ttu-id="9e85e-137">[OLE DB la transformación de comandos](data-flow/transformations/ole-db-command-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="9e85e-137">[OLE DB Command Transformation](data-flow/transformations/ole-db-command-transformation.md) </span></span>  
 <span data-ttu-id="9e85e-138">[Transformaciones de Integration Services](data-flow/transformations/integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="9e85e-138">[Integration Services Transformations](data-flow/transformations/integration-services-transformations.md) </span></span>  
 <span data-ttu-id="9e85e-139">[Rutas de Integration Services](data-flow/integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="9e85e-139">[Integration Services Paths](data-flow/integration-services-paths.md) </span></span>  
 [<span data-ttu-id="9e85e-140">Tarea Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="9e85e-140">Data Flow Task</span></span>](control-flow/data-flow-task.md)  
  
  
