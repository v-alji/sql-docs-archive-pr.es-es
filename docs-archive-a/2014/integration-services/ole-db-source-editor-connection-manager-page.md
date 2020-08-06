---
title: Editor de origen de OLE DB (página Administrador de conexiones) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.oledbsourceadapter.connection.f1
helpviewer_keywords:
- OLE DB Source Editor
ms.assetid: 53699902-8699-4547-b56b-a5b2079e98b6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e6b9d841ff902107847a9d85779af41f476315db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676587"
---
# <a name="ole-db-source-editor-connection-manager-page"></a><span data-ttu-id="a58dd-102">Editor de origen de OLE DB (página Administrador de conexiones)</span><span class="sxs-lookup"><span data-stu-id="a58dd-102">OLE DB Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="a58dd-103">Utilice la página **Administrador de conexiones** del cuadro de diálogo **Editor de origen de OLE DB** para seleccionar el administrador de conexiones OLE DB para el origen.</span><span class="sxs-lookup"><span data-stu-id="a58dd-103">Use the **Connection Manager** page of the **OLE DB Source Editor** dialog box to select the OLE DB connection manager for the source.</span></span> <span data-ttu-id="a58dd-104">Esta página también permite seleccionar una tabla o vista de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a58dd-104">This page also lets you select a table or view from the database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a58dd-105">Para cargar datos desde un origen de datos que use [!INCLUDE[msCoName](../includes/msconame-md.md)] Office Excel 2007, use un origen de OLE DB.</span><span class="sxs-lookup"><span data-stu-id="a58dd-105">To load data from a data source that uses [!INCLUDE[msCoName](../includes/msconame-md.md)] Office Excel 2007, use an OLE DB source.</span></span> <span data-ttu-id="a58dd-106">No puede usar un origen de Excel para cargar datos desde un origen de datos de Excel 2007.</span><span class="sxs-lookup"><span data-stu-id="a58dd-106">You cannot use an Excel source to load data from an Excel 2007 data source.</span></span> <span data-ttu-id="a58dd-107">Para más información, consulte [Configure OLE DB Connection Manager](configure-ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="a58dd-107">For more information, see [Configure OLE DB Connection Manager](configure-ole-db-connection-manager.md).</span></span>  
>   
>  <span data-ttu-id="a58dd-108">Para cargar datos desde un origen de datos que use [!INCLUDE[msCoName](../includes/msconame-md.md)] Office Excel 2003 o anterior, use un origen de Excel.</span><span class="sxs-lookup"><span data-stu-id="a58dd-108">To load data from a data source that uses [!INCLUDE[msCoName](../includes/msconame-md.md)] Office Excel 2003 or earlier, use an Excel source.</span></span> <span data-ttu-id="a58dd-109">Para más información, vea [Editor de origen de Excel &#40;página Administrador de conexiones&#41;](../../2014/integration-services/excel-source-editor-connection-manager-page.md).</span><span class="sxs-lookup"><span data-stu-id="a58dd-109">For more information, see [Excel Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/excel-source-editor-connection-manager-page.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a58dd-110">La `CommandTimeout` propiedad del origen de OLE DB no está disponible en el **Editor de origen de OLE DB**, pero se puede establecer mediante el **editor avanzado**.</span><span class="sxs-lookup"><span data-stu-id="a58dd-110">The `CommandTimeout` property of the OLE DB source is not available in the **OLE DB Source Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="a58dd-111">Para obtener más información acerca de esta propiedad, vea la sección Origen de Excel de [OLE DB Custom Properties](data-flow/ole-db-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="a58dd-111">For more information on this property, see the Excel Source section of [OLE DB Custom Properties](data-flow/ole-db-custom-properties.md).</span></span>  
  
 <span data-ttu-id="a58dd-112">Para obtener más información acerca del origen de OLE DB, vea [OLE DB Source](data-flow/ole-db-source.md).</span><span class="sxs-lookup"><span data-stu-id="a58dd-112">To learn more about the OLE DB source, see [OLE DB Source](data-flow/ole-db-source.md).</span></span>  
  
## <a name="open-the-ole-db-source-editor-connection-manager-page"></a><span data-ttu-id="a58dd-113">Abrir el Editor de origen de OLE DB (página Administrador de conexiones)</span><span class="sxs-lookup"><span data-stu-id="a58dd-113">Open the OLE DB Source Editor (Connection Manager Page</span></span>  
  
1.  <span data-ttu-id="a58dd-114">Agregue el origen de OLE DB al paquete [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a58dd-114">Add the OLE DB source to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="a58dd-115">Haga clic con el botón derecho en el componente de origen y, después, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a58dd-115">Right-click the source component and when click **Edit**.</span></span>  
  
3.  <span data-ttu-id="a58dd-116">Haga clic en **Administrador de conexiones**.</span><span class="sxs-lookup"><span data-stu-id="a58dd-116">Click **Connection Manager**.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="a58dd-117">Opciones estáticas</span><span class="sxs-lookup"><span data-stu-id="a58dd-117">Static Options</span></span>  
 <span data-ttu-id="a58dd-118">**Administrador de conexiones OLE DB**</span><span class="sxs-lookup"><span data-stu-id="a58dd-118">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="a58dd-119">Seleccione un administrador de conexiones de la lista o cree una conexión haciendo clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="a58dd-119">Select an existing connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="a58dd-120">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="a58dd-120">**New**</span></span>  
 <span data-ttu-id="a58dd-121">Cree un administrador de conexiones con el cuadro de diálogo **Configurar el administrador de conexiones OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="a58dd-121">Create a new connection manager by using the **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="a58dd-122">**Modo de acceso a datos**</span><span class="sxs-lookup"><span data-stu-id="a58dd-122">**Data access mode**</span></span>  
 <span data-ttu-id="a58dd-123">Especifique el método para seleccionar datos del origen.</span><span class="sxs-lookup"><span data-stu-id="a58dd-123">Specify the method for selecting data from the source.</span></span>  
  
|<span data-ttu-id="a58dd-124">Opción</span><span class="sxs-lookup"><span data-stu-id="a58dd-124">Option</span></span>|<span data-ttu-id="a58dd-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="a58dd-125">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="a58dd-126">Tabla o vista</span><span class="sxs-lookup"><span data-stu-id="a58dd-126">Table or view</span></span>|<span data-ttu-id="a58dd-127">Obtenga datos de una tabla o vista en el origen de datos OLE DB.</span><span class="sxs-lookup"><span data-stu-id="a58dd-127">Retrieve data from a table or view in the OLE DB data source.</span></span>|  
|<span data-ttu-id="a58dd-128">Variable de nombre de tabla o nombre de vista</span><span class="sxs-lookup"><span data-stu-id="a58dd-128">Table name or view name variable</span></span>|<span data-ttu-id="a58dd-129">Especifique el nombre de la tabla o vista de una variable.</span><span class="sxs-lookup"><span data-stu-id="a58dd-129">Specify the table or view name in a variable.</span></span><br /><br /> <span data-ttu-id="a58dd-130">**Información relacionada:** [Usar variables en paquetes](../../2014/integration-services/use-variables-in-packages.md)</span><span class="sxs-lookup"><span data-stu-id="a58dd-130">**Related information:** [Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md)</span></span>|  
|<span data-ttu-id="a58dd-131">Comando SQL</span><span class="sxs-lookup"><span data-stu-id="a58dd-131">SQL command</span></span>|<span data-ttu-id="a58dd-132">Obtenga datos del origen de datos OLE DB mediante una consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="a58dd-132">Retrieve data from the OLE DB data source by using a SQL query.</span></span>|  
|<span data-ttu-id="a58dd-133">Comando SQL de variable</span><span class="sxs-lookup"><span data-stu-id="a58dd-133">SQL command from variable</span></span>|<span data-ttu-id="a58dd-134">Especifique el texto de la consulta SQL de una variable.</span><span class="sxs-lookup"><span data-stu-id="a58dd-134">Specify the SQL query text in a variable.</span></span>|  
  
 <span data-ttu-id="a58dd-135">**Versión preliminar**</span><span class="sxs-lookup"><span data-stu-id="a58dd-135">**Preview**</span></span>  
 <span data-ttu-id="a58dd-136">Muestra una vista previa de los resultados mediante el cuadro de diálogo **Vista de datos** .</span><span class="sxs-lookup"><span data-stu-id="a58dd-136">Preview results by using the **Data View** dialog box.</span></span> <span data-ttu-id="a58dd-137">**Vista previa** puede mostrar hasta 200 filas.</span><span class="sxs-lookup"><span data-stu-id="a58dd-137">**Preview** can display up to 200 rows.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a58dd-138">Cuando genera una vista previa de datos, las columnas con un tipo definido por el usuario CLR no contienen datos.</span><span class="sxs-lookup"><span data-stu-id="a58dd-138">When you preview data, columns with a CLR user-defined type do not contain data.</span></span> <span data-ttu-id="a58dd-139">En su lugar, se muestran los valores \<value too big to display> o System.Byte[].</span><span class="sxs-lookup"><span data-stu-id="a58dd-139">Instead the values \<value too big to display> or System.Byte[] display.</span></span> <span data-ttu-id="a58dd-140">El primero se muestra cuando se tiene acceso al origen de datos mediante el proveedor SQL OLE DB y el último, cuando se utiliza el proveedor Native Client [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a58dd-140">The former displays when the data source is accessed using the SQL OLE DB provider, the latter when using the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Native Client provider.</span></span>  
  
## <a name="data-access-mode-dynamic-options"></a><span data-ttu-id="a58dd-141">Opciones dinámicas del modo de acceso a datos</span><span class="sxs-lookup"><span data-stu-id="a58dd-141">Data Access Mode Dynamic Options</span></span>  
  
### <a name="data-access-mode--table-or-view"></a><span data-ttu-id="a58dd-142">Modo de acceso a datos = Tabla o vista</span><span class="sxs-lookup"><span data-stu-id="a58dd-142">Data access mode = Table or view</span></span>  
 <span data-ttu-id="a58dd-143">**Nombre de la tabla o la vista**</span><span class="sxs-lookup"><span data-stu-id="a58dd-143">**Name of the table or the view**</span></span>  
 <span data-ttu-id="a58dd-144">Seleccione el nombre de la tabla o vista de los disponibles en una lista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="a58dd-144">Select the name of the table or view from a list of those available in the data source.</span></span>  
  
### <a name="data-access-mode--table-name-or-view-name-variable"></a><span data-ttu-id="a58dd-145">Modo de acceso a datos = Variable de nombre de tabla o nombre de vista</span><span class="sxs-lookup"><span data-stu-id="a58dd-145">Data access mode = Table name or view name variable</span></span>  
 <span data-ttu-id="a58dd-146">**Nombre de la variable**</span><span class="sxs-lookup"><span data-stu-id="a58dd-146">**Variable name**</span></span>  
 <span data-ttu-id="a58dd-147">Seleccione la variable que contiene el nombre de la tabla o vista.</span><span class="sxs-lookup"><span data-stu-id="a58dd-147">Select the variable that contains the name of the table or view.</span></span>  
  
### <a name="data-access-mode--sql-command"></a><span data-ttu-id="a58dd-148">Modo de acceso a datos = Comando SQL</span><span class="sxs-lookup"><span data-stu-id="a58dd-148">Data access mode = SQL command</span></span>  
 <span data-ttu-id="a58dd-149">**Texto de comando SQL**</span><span class="sxs-lookup"><span data-stu-id="a58dd-149">**SQL command text**</span></span>  
 <span data-ttu-id="a58dd-150">Escriba el texto de una consulta SQL, genere la consulta haciendo clic en **Generar consulta**, o bien busque el archivo que contiene el texto de la consulta haciendo clic en **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="a58dd-150">Enter the text of a SQL query, build the query by clicking **Build Query**, or locate the file that contains the query text by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="a58dd-151">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="a58dd-151">**Parameters**</span></span>  
 <span data-ttu-id="a58dd-152">Si ha escrito una consulta con parámetros mediante ?</span><span class="sxs-lookup"><span data-stu-id="a58dd-152">If you have entered a parameterized query by using ?</span></span> <span data-ttu-id="a58dd-153">como marcador de posición de parámetro en el texto de la consulta, utilice el cuadro de diálogo **Establecer parámetros de consulta** para asignar los parámetros de entrada de las consultas a las variables del paquete.</span><span class="sxs-lookup"><span data-stu-id="a58dd-153">as a parameter placeholder in the query text, use the **Set Query Parameters** dialog box to map query input parameters to package variables.</span></span>  
  
 <span data-ttu-id="a58dd-154">**Generar consulta**</span><span class="sxs-lookup"><span data-stu-id="a58dd-154">**Build query**</span></span>  
 <span data-ttu-id="a58dd-155">Use el cuadro de diálogo **Generador de consultas** para crear visualmente la consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="a58dd-155">Use the **Query Builder** dialog box to construct the SQL query visually.</span></span>  
  
 <span data-ttu-id="a58dd-156">**Browse**</span><span class="sxs-lookup"><span data-stu-id="a58dd-156">**Browse**</span></span>  
 <span data-ttu-id="a58dd-157">Use el cuadro de diálogo **Abrir** para buscar el archivo que contiene el texto de la consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="a58dd-157">Use the **Open** dialog box to locate the file that contains the text of the SQL query.</span></span>  
  
 <span data-ttu-id="a58dd-158">**Analizar consulta**</span><span class="sxs-lookup"><span data-stu-id="a58dd-158">**Parse query**</span></span>  
 <span data-ttu-id="a58dd-159">Comprueba la sintaxis del texto de la consulta.</span><span class="sxs-lookup"><span data-stu-id="a58dd-159">Verify the syntax of the query text.</span></span>  
  
### <a name="data-access-mode--sql-command-from-variable"></a><span data-ttu-id="a58dd-160">Modo de acceso a datos = Comando SQL de variable</span><span class="sxs-lookup"><span data-stu-id="a58dd-160">Data access mode = SQL command from variable</span></span>  
 <span data-ttu-id="a58dd-161">**Nombre de la variable**</span><span class="sxs-lookup"><span data-stu-id="a58dd-161">**Variable name**</span></span>  
 <span data-ttu-id="a58dd-162">Seleccione la variable que contiene el texto de la consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="a58dd-162">Select the variable that contains the text of the SQL query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a58dd-163">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a58dd-163">See Also</span></span>  
 <span data-ttu-id="a58dd-164">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="a58dd-164">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="a58dd-165">[&#40;página columnas del editor de origen de OLE DB&#41;](../../2014/integration-services/ole-db-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="a58dd-165">[OLE DB Source Editor &#40;Columns Page&#41;](../../2014/integration-services/ole-db-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="a58dd-166">[OLE DB Editor de origen &#40;página salida de error&#41;](../../2014/integration-services/ole-db-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="a58dd-166">[OLE DB Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/ole-db-source-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="a58dd-167">[Extraer datos mediante el origen de OLE DB](data-flow/extract-data-by-using-the-ole-db-source.md) </span><span class="sxs-lookup"><span data-stu-id="a58dd-167">[Extract Data by Using the OLE DB Source](data-flow/extract-data-by-using-the-ole-db-source.md) </span></span>  
 [<span data-ttu-id="a58dd-168">Administrador de conexiones OLE DB</span><span class="sxs-lookup"><span data-stu-id="a58dd-168">OLE DB Connection Manager</span></span>](connection-manager/ole-db-connection-manager.md)  
  
  
