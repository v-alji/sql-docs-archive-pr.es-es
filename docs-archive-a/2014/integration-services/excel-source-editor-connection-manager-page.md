---
title: Editor de origen de Excel (página Administrador de conexiones) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.excelsourceadapter.connection.f1
helpviewer_keywords:
- Excel Source Editor
ms.assetid: 428e04e0-ad98-45d0-8345-12ec1b67b2eb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3285b5c8b14016b91005af79542e3e2f9b6559b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673790"
---
# <a name="excel-source-editor-connection-manager-page"></a><span data-ttu-id="0bcf5-102">Editor de origen de Excel (página Administrador de conexiones)</span><span class="sxs-lookup"><span data-stu-id="0bcf5-102">Excel Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="0bcf5-103">Utilice el nodo **Administrador de conexiones** del cuadro de diálogo **Editor de origen de Excel** para seleccionar el libro de [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] que utilizará el origen.</span><span class="sxs-lookup"><span data-stu-id="0bcf5-103">Use the **Connection Manager** node of the **Excel Source Editor** dialog box to select the [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] workbook for the source to use.</span></span> <span data-ttu-id="0bcf5-104">El origen de Excel lee los datos de una hoja de cálculo o un rango con nombre de un libro existente.</span><span class="sxs-lookup"><span data-stu-id="0bcf5-104">The Excel source reads data from a worksheet or named range in an existing workbook.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0bcf5-105">La `CommandTimeout` propiedad del origen de Excel no está disponible en el **Editor de origen de Excel**, pero se puede establecer mediante el **editor avanzado**.</span><span class="sxs-lookup"><span data-stu-id="0bcf5-105">The `CommandTimeout` property of the Excel source is not available in the **Excel Source Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="0bcf5-106">Para obtener más información acerca de esta propiedad, vea la sección Origen de Excel de [Excel Custom Properties](data-flow/excel-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="0bcf5-106">For more information on this property, see the Excel Source section of [Excel Custom Properties](data-flow/excel-custom-properties.md).</span></span>  
  
 <span data-ttu-id="0bcf5-107">Para obtener más información acerca del origen de Excel, vea [Excel Source](data-flow/excel-source.md).</span><span class="sxs-lookup"><span data-stu-id="0bcf5-107">To learn more about the Excel source, see [Excel Source](data-flow/excel-source.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="0bcf5-108">Opciones estáticas</span><span class="sxs-lookup"><span data-stu-id="0bcf5-108">Static Options</span></span>  
 <span data-ttu-id="0bcf5-109">**Administrador de conexiones OLE DB**</span><span class="sxs-lookup"><span data-stu-id="0bcf5-109">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="0bcf5-110">Seleccione un Administrador de conexiones con Excel en la lista o cree una conexión haciendo clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="0bcf5-110">Select an existing Excel connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="0bcf5-111">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="0bcf5-111">**New**</span></span>  
 <span data-ttu-id="0bcf5-112">Cree un administrador de conexiones mediante el cuadro de diálogo **Administrador de conexiones con Excel** .</span><span class="sxs-lookup"><span data-stu-id="0bcf5-112">Create a new connection manager by using the **Excel Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="0bcf5-113">**Modo de acceso a datos**</span><span class="sxs-lookup"><span data-stu-id="0bcf5-113">**Data access mode**</span></span>  
 <span data-ttu-id="0bcf5-114">Especifique el método para seleccionar datos del origen.</span><span class="sxs-lookup"><span data-stu-id="0bcf5-114">Specify the method for selecting data from the source.</span></span>  
  
|<span data-ttu-id="0bcf5-115">Value</span><span class="sxs-lookup"><span data-stu-id="0bcf5-115">Value</span></span>|<span data-ttu-id="0bcf5-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="0bcf5-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0bcf5-117">Tabla o vista</span><span class="sxs-lookup"><span data-stu-id="0bcf5-117">Table or view</span></span>|<span data-ttu-id="0bcf5-118">Recupera los datos de una hoja de cálculo o un rango con nombre del archivo Excel.</span><span class="sxs-lookup"><span data-stu-id="0bcf5-118">Retrieve data from a worksheet or named range in the Excel file.</span></span>|  
|<span data-ttu-id="0bcf5-119">Variable de nombre de tabla o nombre de vista</span><span class="sxs-lookup"><span data-stu-id="0bcf5-119">Table name or view name variable</span></span>|<span data-ttu-id="0bcf5-120">Especifique la hoja de calculo o el rango con nombre de una variable.</span><span class="sxs-lookup"><span data-stu-id="0bcf5-120">Specify the worksheet or range name in a variable.</span></span><br /><br /> <span data-ttu-id="0bcf5-121">**Información relacionada:** [Usar variables en paquetes](../../2014/integration-services/use-variables-in-packages.md)</span><span class="sxs-lookup"><span data-stu-id="0bcf5-121">**Related information:** [Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md)</span></span>|  
|<span data-ttu-id="0bcf5-122">Comando SQL</span><span class="sxs-lookup"><span data-stu-id="0bcf5-122">SQL command</span></span>|<span data-ttu-id="0bcf5-123">Recupera datos del archivo Excel mediante una consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="0bcf5-123">Retrieve data from the Excel file by using a SQL query.</span></span> <span data-ttu-id="0bcf5-124">Para obtener información acerca de la sintaxis de consultas, vea [Excel Source](data-flow/excel-source.md).</span><span class="sxs-lookup"><span data-stu-id="0bcf5-124">For information about query syntax, see [Excel Source](data-flow/excel-source.md).</span></span>|  
|<span data-ttu-id="0bcf5-125">Comando SQL de variable</span><span class="sxs-lookup"><span data-stu-id="0bcf5-125">SQL command from variable</span></span>|<span data-ttu-id="0bcf5-126">Especifique el texto de la consulta SQL de una variable.</span><span class="sxs-lookup"><span data-stu-id="0bcf5-126">Specify the SQL query text in a variable.</span></span>|  
  
 <span data-ttu-id="0bcf5-127">**Versión preliminar**</span><span class="sxs-lookup"><span data-stu-id="0bcf5-127">**Preview**</span></span>  
 <span data-ttu-id="0bcf5-128">Muestra una vista previa de los resultados mediante el cuadro de diálogo **Vista de datos** .</span><span class="sxs-lookup"><span data-stu-id="0bcf5-128">Preview results by using the **Data View** dialog box.</span></span> <span data-ttu-id="0bcf5-129">La vista previa puede mostrar hasta 200 filas.</span><span class="sxs-lookup"><span data-stu-id="0bcf5-129">Preview can display up to 200 rows.</span></span>  
  
## <a name="data-access-mode-dynamic-options"></a><span data-ttu-id="0bcf5-130">Opciones dinámicas del modo de acceso a datos</span><span class="sxs-lookup"><span data-stu-id="0bcf5-130">Data Access Mode Dynamic Options</span></span>  
  
### <a name="data-access-mode--table-or-view"></a><span data-ttu-id="0bcf5-131">Modo de acceso a datos = Tabla o vista</span><span class="sxs-lookup"><span data-stu-id="0bcf5-131">Data access mode = Table or view</span></span>  
 <span data-ttu-id="0bcf5-132">**Nombre de la hoja de Excel**</span><span class="sxs-lookup"><span data-stu-id="0bcf5-132">**Name of the Excel sheet**</span></span>  
 <span data-ttu-id="0bcf5-133">Seleccione el nombre de la hoja de cálculo o el rango con nombre de los disponibles en el libro de Excel.</span><span class="sxs-lookup"><span data-stu-id="0bcf5-133">Select the name of the worksheet or named range from a list of those available in the Excel workbook.</span></span>  
  
### <a name="data-access-mode--table-name-or-view-name-variable"></a><span data-ttu-id="0bcf5-134">Modo de acceso a datos = Variable de nombre de tabla o nombre de vista</span><span class="sxs-lookup"><span data-stu-id="0bcf5-134">Data access mode = Table name or view name variable</span></span>  
 <span data-ttu-id="0bcf5-135">**Nombre de la variable**</span><span class="sxs-lookup"><span data-stu-id="0bcf5-135">**Variable name**</span></span>  
 <span data-ttu-id="0bcf5-136">Seleccione la variable que contiene el nombre de la hoja de cálculo o el rango con nombre.</span><span class="sxs-lookup"><span data-stu-id="0bcf5-136">Select the variable that contains the name of the worksheet or named range.</span></span>  
  
### <a name="data-access-mode--sql-command"></a><span data-ttu-id="0bcf5-137">Modo de acceso a datos = Comando SQL</span><span class="sxs-lookup"><span data-stu-id="0bcf5-137">Data access mode = SQL command</span></span>  
 <span data-ttu-id="0bcf5-138">**Texto de comando SQL**</span><span class="sxs-lookup"><span data-stu-id="0bcf5-138">**SQL command text**</span></span>  
 <span data-ttu-id="0bcf5-139">Escriba el texto de una consulta SQL, genere la consulta haciendo clic en **Generar consulta**, o bien examine el archivo que contiene el texto de la consulta haciendo clic en **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="0bcf5-139">Enter the text of a SQL query, build the query by clicking **Build Query**, or browse to the file that contains the query text by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="0bcf5-140">**Parámetros**</span><span class="sxs-lookup"><span data-stu-id="0bcf5-140">**Parameters**</span></span>  
 <span data-ttu-id="0bcf5-141">Si ha escrito una consulta con parámetros mediante ?</span><span class="sxs-lookup"><span data-stu-id="0bcf5-141">If you have entered a parameterized query by using ?</span></span> <span data-ttu-id="0bcf5-142">como marcador de posición de parámetro en el texto de la consulta, utilice el cuadro de diálogo **Establecer parámetros de consulta** para asignar los parámetros de entrada de las consultas a las variables del paquete.</span><span class="sxs-lookup"><span data-stu-id="0bcf5-142">as a parameter placeholder in the query text, use the **Set Query Parameters** dialog box to map query input parameters to package variables.</span></span>  
  
 <span data-ttu-id="0bcf5-143">**Generar consulta**</span><span class="sxs-lookup"><span data-stu-id="0bcf5-143">**Build query**</span></span>  
 <span data-ttu-id="0bcf5-144">Use el cuadro de diálogo **Generador de consultas** para crear visualmente la consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="0bcf5-144">Use the **Query Builder** dialog box to construct the SQL query visually.</span></span>  
  
 <span data-ttu-id="0bcf5-145">**Browse**</span><span class="sxs-lookup"><span data-stu-id="0bcf5-145">**Browse**</span></span>  
 <span data-ttu-id="0bcf5-146">Use el cuadro de diálogo **Abrir** para buscar el archivo que contiene el texto de la consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="0bcf5-146">Use the **Open** dialog box to locate the file that contains the text of the SQL query.</span></span>  
  
 <span data-ttu-id="0bcf5-147">**Analizar consulta**</span><span class="sxs-lookup"><span data-stu-id="0bcf5-147">**Parse query**</span></span>  
 <span data-ttu-id="0bcf5-148">Comprueba la sintaxis del texto de la consulta.</span><span class="sxs-lookup"><span data-stu-id="0bcf5-148">Verify the syntax of the query text.</span></span>  
  
### <a name="data-access-mode--sql-command-from-variable"></a><span data-ttu-id="0bcf5-149">Modo de acceso a datos = Comando SQL de variable</span><span class="sxs-lookup"><span data-stu-id="0bcf5-149">Data access mode = SQL command from variable</span></span>  
 <span data-ttu-id="0bcf5-150">**Nombre de la variable**</span><span class="sxs-lookup"><span data-stu-id="0bcf5-150">**Variable name**</span></span>  
 <span data-ttu-id="0bcf5-151">Seleccione la variable que contiene el texto de la consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="0bcf5-151">Select the variable that contains the text of the SQL query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bcf5-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0bcf5-152">See Also</span></span>  
 <span data-ttu-id="0bcf5-153">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="0bcf5-153">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="0bcf5-154">[Editor de origen de Excel &#40;página columnas&#41;](../../2014/integration-services/excel-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="0bcf5-154">[Excel Source Editor &#40;Columns Page&#41;](../../2014/integration-services/excel-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="0bcf5-155">[Editor de origen de Excel &#40;página salida de error&#41;](../../2014/integration-services/excel-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="0bcf5-155">[Excel Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/excel-source-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="0bcf5-156">[Administrador de conexiones con Excel](connection-manager/excel-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="0bcf5-156">[Excel Connection Manager](connection-manager/excel-connection-manager.md) </span></span>  
 [<span data-ttu-id="0bcf5-157">Crear bucles entre archivos y tablas de Excel mediante un contenedor de bucles ForEach</span><span class="sxs-lookup"><span data-stu-id="0bcf5-157">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](control-flow/foreach-loop-container.md)  
  
  
