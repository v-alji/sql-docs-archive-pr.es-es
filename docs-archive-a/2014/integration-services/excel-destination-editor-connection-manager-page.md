---
title: Editor de destino de Excel (página Administrador de conexiones) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.exceldestadapter.connection.f1
helpviewer_keywords:
- Excel Destination Editor
ms.assetid: fc13f725-963c-488e-91e2-20627133e842
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1556bf713c49aac31f1cc1cd624336f10dbf832f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673806"
---
# <a name="excel-destination-editor-connection-manager-page"></a><span data-ttu-id="c2619-102">Editor de destino de Excel (página Administrador de conexiones)</span><span class="sxs-lookup"><span data-stu-id="c2619-102">Excel Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="c2619-103">Utilice la página **Administrador de conexiones** del cuadro de diálogo **Editor de destino de Excel** para especificar la información de orígenes de datos y para obtener una vista previa de los resultados.</span><span class="sxs-lookup"><span data-stu-id="c2619-103">Use the **Connection Manager** page of the **Excel Destination Editor** dialog box to specify data source information, and to preview the results.</span></span> <span data-ttu-id="c2619-104">El destino de Excel carga los datos en una hoja de cálculo o en un rango con nombre de un libro de [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c2619-104">The Excel destination loads data into a worksheet or a named range in a [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] workbook.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c2619-105">La `CommandTimeout` propiedad del destino de Excel no está disponible en el **Editor de destino de Excel**, pero se puede establecer mediante el **editor avanzado**.</span><span class="sxs-lookup"><span data-stu-id="c2619-105">The `CommandTimeout` property of the Excel destination is not available in the **Excel Destination Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="c2619-106">Además, ciertas opciones de carga rápida solo están disponibles en el **editor avanzado**.</span><span class="sxs-lookup"><span data-stu-id="c2619-106">In addition, certain Fast Load options are available only in the **Advanced Editor**.</span></span> <span data-ttu-id="c2619-107">Para obtener más información acerca de estas propiedades, vea la sección sobre el destino de Excel en [Excel Custom Properties](data-flow/excel-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="c2619-107">For more information on these properties, see the Excel Destination section of [Excel Custom Properties](data-flow/excel-custom-properties.md).</span></span>  
  
 <span data-ttu-id="c2619-108">Para obtener más información acerca del destino de Excel, vea [Excel Destination](data-flow/excel-destination.md).</span><span class="sxs-lookup"><span data-stu-id="c2619-108">To learn more about the Excel destination, see [Excel Destination](data-flow/excel-destination.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="c2619-109">Opciones estáticas</span><span class="sxs-lookup"><span data-stu-id="c2619-109">Static Options</span></span>  
 <span data-ttu-id="c2619-110">**Administrador de conexiones con Excel**</span><span class="sxs-lookup"><span data-stu-id="c2619-110">**Excel connection manager**</span></span>  
 <span data-ttu-id="c2619-111">Seleccione un Administrador de conexiones con Excel en la lista o cree una conexión haciendo clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="c2619-111">Select an existing Excel connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="c2619-112">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="c2619-112">**New**</span></span>  
 <span data-ttu-id="c2619-113">Cree un administrador de conexiones mediante el cuadro de diálogo **Administrador de conexiones con Excel** .</span><span class="sxs-lookup"><span data-stu-id="c2619-113">Create a new connection manager by using the **Excel Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="c2619-114">**Modo de acceso a datos**</span><span class="sxs-lookup"><span data-stu-id="c2619-114">**Data access mode**</span></span>  
 <span data-ttu-id="c2619-115">Especifique el método para seleccionar datos del origen.</span><span class="sxs-lookup"><span data-stu-id="c2619-115">Specify the method for selecting data from the source.</span></span>  
  
|<span data-ttu-id="c2619-116">Opción</span><span class="sxs-lookup"><span data-stu-id="c2619-116">Option</span></span>|<span data-ttu-id="c2619-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="c2619-117">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c2619-118">Tabla o vista</span><span class="sxs-lookup"><span data-stu-id="c2619-118">Table or view</span></span>|<span data-ttu-id="c2619-119">Carga datos en una hoja de cálculo o en un rango con nombre del origen de datos de Excel.</span><span class="sxs-lookup"><span data-stu-id="c2619-119">Loads data into a worksheet or named range in the Excel data source.</span></span>|  
|<span data-ttu-id="c2619-120">Variable de nombre de tabla o nombre de vista</span><span class="sxs-lookup"><span data-stu-id="c2619-120">Table name or view name variable</span></span>|<span data-ttu-id="c2619-121">Especifique la hoja de calculo o el rango con nombre de una variable.</span><span class="sxs-lookup"><span data-stu-id="c2619-121">Specify the worksheet or range name in a variable.</span></span><br /><br /> <span data-ttu-id="c2619-122">**Información relacionada**: [Usar variables en paquetes](../../2014/integration-services/use-variables-in-packages.md)</span><span class="sxs-lookup"><span data-stu-id="c2619-122">**Related information**: [Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md)</span></span>|  
|<span data-ttu-id="c2619-123">Comando SQL</span><span class="sxs-lookup"><span data-stu-id="c2619-123">SQL command</span></span>|<span data-ttu-id="c2619-124">Cargue datos en el destino de Excel utilizando una consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="c2619-124">Load data into the Excel destination by using an SQL query.</span></span>|  
  
 <span data-ttu-id="c2619-125">**Nombre de la hoja de Excel**</span><span class="sxs-lookup"><span data-stu-id="c2619-125">**Name of the Excel sheet**</span></span>  
 <span data-ttu-id="c2619-126">Seleccione el destino de Excel de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="c2619-126">Select the excel destination from the drop-down list.</span></span> <span data-ttu-id="c2619-127">Si la lista está vacía, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="c2619-127">If the list is empty, click **New**.</span></span>  
  
 <span data-ttu-id="c2619-128">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="c2619-128">**New**</span></span>  
 <span data-ttu-id="c2619-129">Haga clic en **Nuevo** para iniciar el cuadro de diálogo **Crear tabla** .</span><span class="sxs-lookup"><span data-stu-id="c2619-129">Click **New** to launch the **Create Table** dialog box.</span></span> <span data-ttu-id="c2619-130">Al hacer clic en **Aceptar**, el cuadro de diálogo crea el archivo de Excel al que señala el **Administrador de conexiones con Excel** .</span><span class="sxs-lookup"><span data-stu-id="c2619-130">When you click **OK**, the dialog box creates the excel file that the **Excel Connection Manager** points to.</span></span>  
  
 <span data-ttu-id="c2619-131">**Datos existentes de la vista**</span><span class="sxs-lookup"><span data-stu-id="c2619-131">**View Existing Data**</span></span>  
 <span data-ttu-id="c2619-132">Obtenga una vista previa de los resultados mediante el cuadro de diálogo **Vista previa de los resultados de la consulta** .</span><span class="sxs-lookup"><span data-stu-id="c2619-132">Preview results by using the **Preview Query Results** dialog box.</span></span> <span data-ttu-id="c2619-133">La vista previa puede mostrar hasta 200 filas.</span><span class="sxs-lookup"><span data-stu-id="c2619-133">Preview can display up to 200 rows.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="c2619-134"> Si el **Administrador de conexiones con Excel** que ha seleccionado señala a un archivo de Excel que no existe, verá un mensaje de error al hacer clic en este botón.</span><span class="sxs-lookup"><span data-stu-id="c2619-134">If the **Excel connection manager** you selected points to an excel file that does not exist, you will see an error message when you click this button.</span></span>  
  
## <a name="data-access-mode-dynamic-options"></a><span data-ttu-id="c2619-135">Opciones dinámicas del modo de acceso a datos</span><span class="sxs-lookup"><span data-stu-id="c2619-135">Data Access Mode Dynamic Options</span></span>  
  
### <a name="data-access-mode--table-or-view"></a><span data-ttu-id="c2619-136">Modo de acceso a datos = Tabla o vista</span><span class="sxs-lookup"><span data-stu-id="c2619-136">Data access mode = Table or view</span></span>  
 <span data-ttu-id="c2619-137">**Nombre de la hoja de Excel**</span><span class="sxs-lookup"><span data-stu-id="c2619-137">**Name of the Excel sheet**</span></span>  
 <span data-ttu-id="c2619-138">Seleccione el nombre de la hoja de cálculo o el rango con nombre de los disponibles en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="c2619-138">Select the name of the worksheet or named range from a list of those available in the data source.</span></span>  
  
### <a name="data-access-mode--table-name-or-view-name-variable"></a><span data-ttu-id="c2619-139">Modo de acceso a datos = Variable de nombre de tabla o nombre de vista</span><span class="sxs-lookup"><span data-stu-id="c2619-139">Data access mode = Table name or view name variable</span></span>  
 <span data-ttu-id="c2619-140">**Nombre de la variable**</span><span class="sxs-lookup"><span data-stu-id="c2619-140">**Variable name**</span></span>  
 <span data-ttu-id="c2619-141">Seleccione la variable que contiene el nombre de la hoja de cálculo o el rango con nombre.</span><span class="sxs-lookup"><span data-stu-id="c2619-141">Select the variable that contains the name of the worksheet or named range.</span></span>  
  
### <a name="data-access-mode--sql-command"></a><span data-ttu-id="c2619-142">Modo de acceso a datos = Comando SQL</span><span class="sxs-lookup"><span data-stu-id="c2619-142">Data access mode = SQL command</span></span>  
 <span data-ttu-id="c2619-143">**Texto de comando SQL**</span><span class="sxs-lookup"><span data-stu-id="c2619-143">**SQL command text**</span></span>  
 <span data-ttu-id="c2619-144">Escriba el texto de una consulta SQL, genere la consulta haciendo clic en **Generar consulta**, o bien busque el archivo que contiene el texto de la consulta haciendo clic en **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="c2619-144">Enter the text of an SQL query, build the query by clicking **Build Query**, or locate the file that contains the query text by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="c2619-145">**Generar consulta**</span><span class="sxs-lookup"><span data-stu-id="c2619-145">**Build Query**</span></span>  
 <span data-ttu-id="c2619-146">Use el cuadro de diálogo **Generador de consultas** para crear visualmente la consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="c2619-146">Use the **Query Builder** dialog box to construct the SQL query visually.</span></span>  
  
 <span data-ttu-id="c2619-147">**Browse**</span><span class="sxs-lookup"><span data-stu-id="c2619-147">**Browse**</span></span>  
 <span data-ttu-id="c2619-148">Use el cuadro de diálogo **Abrir** para buscar el archivo que contiene el texto de la consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="c2619-148">Use the **Open** dialog box to locate the file that contains the text of the SQL query.</span></span>  
  
 <span data-ttu-id="c2619-149">**Analizar consulta**</span><span class="sxs-lookup"><span data-stu-id="c2619-149">**Parse Query**</span></span>  
 <span data-ttu-id="c2619-150">Comprueba la sintaxis del texto de la consulta.</span><span class="sxs-lookup"><span data-stu-id="c2619-150">Verify the syntax of the query text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2619-151">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c2619-151">See Also</span></span>  
 <span data-ttu-id="c2619-152">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="c2619-152">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="c2619-153">[Editor de destino de Excel &#40;página asignaciones&#41;](../../2014/integration-services/excel-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="c2619-153">[Excel Destination Editor &#40;Mappings Page&#41;](../../2014/integration-services/excel-destination-editor-mappings-page.md) </span></span>  
 <span data-ttu-id="c2619-154">[Editor de destino de Excel &#40;página salida de error&#41;](../../2014/integration-services/excel-destination-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="c2619-154">[Excel Destination Editor &#40;Error Output Page&#41;](../../2014/integration-services/excel-destination-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="c2619-155">Crear bucles entre archivos y tablas de Excel mediante un contenedor de bucles ForEach</span><span class="sxs-lookup"><span data-stu-id="c2619-155">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](control-flow/foreach-loop-container.md)  
  
  
