---
title: Editor de transformación búsqueda (página conexión) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.lookuptransformation.referencetable.f1
helpviewer_keywords:
- Lookup Transformation Editor
ms.assetid: e90d6b69-5a26-43c5-8433-5c3c9588e08c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 381378ac1aca85c6bca825033bc439ebc39fb063
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673098"
---
# <a name="lookup-transformation-editor-connection-page"></a><span data-ttu-id="c657a-102">Editor de transformación Búsqueda (página Conexión)</span><span class="sxs-lookup"><span data-stu-id="c657a-102">Lookup Transformation Editor (Connection Page)</span></span>
  <span data-ttu-id="c657a-103">Utilice la página **Conexión** del cuadro de diálogo **Editor de transformación Búsqueda** para seleccionar un administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="c657a-103">Use the **Connection** page of the **Lookup Transformation Editor** dialog box to select a connection manager.</span></span> <span data-ttu-id="c657a-104">Si selecciona un administrador de conexiones OLE DB, también selecciona una consulta, tabla o vista para generar el conjunto de datos de referencia.</span><span class="sxs-lookup"><span data-stu-id="c657a-104">If you select an OLE DB connection manager, you also select a query, table, or view to generate the reference dataset.</span></span>  
  
 <span data-ttu-id="c657a-105">Para obtener más información acerca de la transformación Búsqueda, vea [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="c657a-105">To learn more about the Lookup transformation, see [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="c657a-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="c657a-106">Options</span></span>  
 <span data-ttu-id="c657a-107">Las opciones siguientes están disponibles al seleccionar **Caché completa** y **Administrador de conexiones de caché** en la página General del cuadro de diálogo **Editor de transformación Búsqueda** .</span><span class="sxs-lookup"><span data-stu-id="c657a-107">The following options are available when you select **Full cache** and **Cache connection manager** on the General page of the **Lookup Transformation Editor** dialog box.</span></span>  
  
 <span data-ttu-id="c657a-108">**Administrador de conexiones de caché**</span><span class="sxs-lookup"><span data-stu-id="c657a-108">**Cache connection manager**</span></span>  
 <span data-ttu-id="c657a-109">Seleccione un administrador de conexiones de caché de la lista o cree una conexión haciendo clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="c657a-109">Select an existing Cache connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="c657a-110">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="c657a-110">**New**</span></span>  
 <span data-ttu-id="c657a-111">Cree una conexión mediante el cuadro de diálogo **Editor del administrador de conexiones de caché** .</span><span class="sxs-lookup"><span data-stu-id="c657a-111">Create a new connection by using the **Cache Connection Manager Editor** dialog box.</span></span>  
  
 <span data-ttu-id="c657a-112">Las opciones siguientes están disponibles al seleccionar **Caché completa**, **Caché parcial**o **Sin caché**, y **Administrador de conexiones OLE DB**en la página General del cuadro de diálogo **Editor de transformación Búsqueda** .</span><span class="sxs-lookup"><span data-stu-id="c657a-112">The following options are available when you select **Full cache**, **Partial cache**, or **No cache**, and **OLE DB connection manager**, on the General page of the **Lookup Transformation Editor** dialog box.</span></span>  
  
 <span data-ttu-id="c657a-113">**Administrador de conexiones OLE DB**</span><span class="sxs-lookup"><span data-stu-id="c657a-113">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="c657a-114">Seleccione un administrador de conexiones OLE DB de la lista o cree una conexión haciendo clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="c657a-114">Select an existing OLE DB connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="c657a-115">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="c657a-115">**New**</span></span>  
 <span data-ttu-id="c657a-116">Cree una conexión mediante el cuadro de diálogo **Configurar el administrador de conexiones OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="c657a-116">Create a new connection by using the **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="c657a-117">**Usar una tabla o una vista**</span><span class="sxs-lookup"><span data-stu-id="c657a-117">**Use a table or view**</span></span>  
 <span data-ttu-id="c657a-118">Seleccione una tabla o vista existente de la lista o cree una nueva tabla haciendo clic en **nueva**.</span><span class="sxs-lookup"><span data-stu-id="c657a-118">Select an existing table or view from the list, or create a new table by clicking **New**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c657a-119">Si especifica una instrucción SQL en la página **Avanzadas** del **Editor de transformación Búsqueda**, esa instrucción SQL invalida y reemplaza el nombre de tabla seleccionado aquí.</span><span class="sxs-lookup"><span data-stu-id="c657a-119">If you specify a SQL statement on the **Advanced** page of the **Lookup Transformation Editor**, that SQL statement overrides and replaces the table name selected here.</span></span> <span data-ttu-id="c657a-120">Para obtener más información, vea [Editor de transformación Búsqueda &#40;página Avanzadas&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md).</span><span class="sxs-lookup"><span data-stu-id="c657a-120">For more information, see [Lookup Transformation Editor &#40;Advanced Page&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md).</span></span>  
  
 <span data-ttu-id="c657a-121">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="c657a-121">**New**</span></span>  
 <span data-ttu-id="c657a-122">Permite crear una tabla con el cuadro de diálogo **Crear tabla** .</span><span class="sxs-lookup"><span data-stu-id="c657a-122">Create a new table by using the **Create Table** dialog box.</span></span>  
  
 <span data-ttu-id="c657a-123">**Usar los resultados de una consulta SQL**</span><span class="sxs-lookup"><span data-stu-id="c657a-123">**Use results of an SQL query**</span></span>  
 <span data-ttu-id="c657a-124">Elija esta opción para buscar una consulta preexistente, generar una consulta nueva, comprobar la sintaxis de consulta y obtener una vista previa de los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="c657a-124">Choose this option to browse to a preexisting query, build a new query, check query syntax, and preview query results.</span></span>  
  
 <span data-ttu-id="c657a-125">**Generar consulta**</span><span class="sxs-lookup"><span data-stu-id="c657a-125">**Build query**</span></span>  
 <span data-ttu-id="c657a-126">Cree la instrucción Transact-SQL para ejecutarla mediante el **Generador de consultas**, herramienta gráfica que se usa para crear consultas examinando datos.</span><span class="sxs-lookup"><span data-stu-id="c657a-126">Create the Transact-SQL statement to run by using **Query Builder**, a graphical tool that is used to create queries by browsing through data.</span></span>  
  
 <span data-ttu-id="c657a-127">**Browse**</span><span class="sxs-lookup"><span data-stu-id="c657a-127">**Browse**</span></span>  
 <span data-ttu-id="c657a-128">Utilice esta opción para examinar una consulta preexistente guardada como un archivo.</span><span class="sxs-lookup"><span data-stu-id="c657a-128">Use this option to browse to a preexisting query saved as a file.</span></span>  
  
 <span data-ttu-id="c657a-129">**Analizar consulta**</span><span class="sxs-lookup"><span data-stu-id="c657a-129">**Parse Query**</span></span>  
 <span data-ttu-id="c657a-130">Compruebe la sintaxis de la consulta.</span><span class="sxs-lookup"><span data-stu-id="c657a-130">Check the syntax of the query.</span></span>  
  
 <span data-ttu-id="c657a-131">**Versión preliminar**</span><span class="sxs-lookup"><span data-stu-id="c657a-131">**Preview**</span></span>  
 <span data-ttu-id="c657a-132">Obtenga una vista previa de los resultados mediante el cuadro de diálogo **Vista previa de los resultados de la consulta** .</span><span class="sxs-lookup"><span data-stu-id="c657a-132">Preview results by using the **Preview Query Results** dialog box.</span></span> <span data-ttu-id="c657a-133">Esta opción muestra hasta 200 filas.</span><span class="sxs-lookup"><span data-stu-id="c657a-133">This option displays up to 200 rows.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="c657a-134">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="c657a-134">External Resources</span></span>  
 <span data-ttu-id="c657a-135">Entrada del blog, [Lookup cache modes](https://go.microsoft.com/fwlink/?LinkId=219518) en blogs.msdn.com</span><span class="sxs-lookup"><span data-stu-id="c657a-135">Blog entry, [Lookup cache modes](https://go.microsoft.com/fwlink/?LinkId=219518) on blogs.msdn.com</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c657a-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c657a-136">See Also</span></span>  
 <span data-ttu-id="c657a-137">[Editor de transformación búsqueda &#40;página general&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="c657a-137">[Lookup Transformation Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="c657a-138">[Editor de transformación búsqueda &#40;página columnas&#41;](../../2014/integration-services/lookup-transformation-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="c657a-138">[Lookup Transformation Editor &#40;Columns Page&#41;](../../2014/integration-services/lookup-transformation-editor-columns-page.md) </span></span>  
 <span data-ttu-id="c657a-139">[Editor de transformación búsqueda &#40;página avanzadas&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="c657a-139">[Lookup Transformation Editor &#40;Advanced Page&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md) </span></span>  
 <span data-ttu-id="c657a-140">[Editor de transformación búsqueda &#40;página salida de error&#41;](../../2014/integration-services/lookup-transformation-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="c657a-140">[Lookup Transformation Editor &#40;Error Output Page&#41;](../../2014/integration-services/lookup-transformation-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="c657a-141">Búsqueda aproximada, transformación</span><span class="sxs-lookup"><span data-stu-id="c657a-141">Fuzzy Lookup Transformation</span></span>](data-flow/transformations/fuzzy-lookup-transformation.md)  
  
  
