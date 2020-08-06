---
title: Editor de orígenes de ADO NET (página Administrador de conexiones) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.adonetsource.connection.f1
ms.assetid: 7de3f438-bdd6-49b5-937a-47369e754943
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 19dd9c256f15bc9022f7267cb38b6f91bd4d8a5c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748224"
---
# <a name="ado-net-source-editor-connection-manager-page"></a><span data-ttu-id="a3909-102">Editor de orígenes de ADO NET (página Administrador de conexiones)</span><span class="sxs-lookup"><span data-stu-id="a3909-102">ADO NET Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="a3909-103">Utilice la página **Administrador de conexiones** del cuadro de diálogo **Editor de orígenes de ADO NET** para seleccionar el administrador de conexiones [!INCLUDE[vstecado](../includes/vstecado-md.md)] para el origen.</span><span class="sxs-lookup"><span data-stu-id="a3909-103">Use the **Connection Manager** page of the **ADO NET Source Editor** dialog box to select the [!INCLUDE[vstecado](../includes/vstecado-md.md)] connection manager for the source.</span></span> <span data-ttu-id="a3909-104">Esta página también permite seleccionar una tabla o vista de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a3909-104">This page also lets you select a table or view from the database.</span></span>  
  
 <span data-ttu-id="a3909-105">Para obtener más información acerca del origen de ADO NET, vea [ADO NET Source](data-flow/ado-net-source.md).</span><span class="sxs-lookup"><span data-stu-id="a3909-105">To learn more about the ADO NET source, see [ADO NET Source](data-flow/ado-net-source.md).</span></span>  
  
 <span data-ttu-id="a3909-106">**Para abrir la página Administrador de conexiones**</span><span class="sxs-lookup"><span data-stu-id="a3909-106">**To open the Connection Manager page**</span></span>  
  
1.  <span data-ttu-id="a3909-107">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el paquete [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que tiene el origen de ADO NET.</span><span class="sxs-lookup"><span data-stu-id="a3909-107">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that has the ADO NET source.</span></span>  
  
2.  <span data-ttu-id="a3909-108">En la pestaña **Flujo de datos** , haga doble clic en el origen de ADO NET.</span><span class="sxs-lookup"><span data-stu-id="a3909-108">On the **Data Flow** tab, double-click the ADO NET source.</span></span>  
  
3.  <span data-ttu-id="a3909-109">En el **Editor de orígenes de ADO NET**, haga clic en **Administrador de conexiones**.</span><span class="sxs-lookup"><span data-stu-id="a3909-109">In the **ADO NET Source Editor**, click **Connection Manager**.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="a3909-110">Opciones estáticas</span><span class="sxs-lookup"><span data-stu-id="a3909-110">Static Options</span></span>  
 <span data-ttu-id="a3909-111">**Administrador de conexiones de ADO.NET**</span><span class="sxs-lookup"><span data-stu-id="a3909-111">**ADO.NET connection manager**</span></span>  
 <span data-ttu-id="a3909-112">Seleccione un administrador de conexiones de la lista o cree una conexión haciendo clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="a3909-112">Select an existing connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="a3909-113">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="a3909-113">**New**</span></span>  
 <span data-ttu-id="a3909-114">Cree un administrador de conexiones mediante el cuadro de diálogo **Configurar el administrador de conexiones ADO.NET** .</span><span class="sxs-lookup"><span data-stu-id="a3909-114">Create a new connection manager by using the **Configure ADO.NET Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="a3909-115">**Modo de acceso a datos**</span><span class="sxs-lookup"><span data-stu-id="a3909-115">**Data access mode**</span></span>  
 <span data-ttu-id="a3909-116">Especifique el método para seleccionar datos del origen.</span><span class="sxs-lookup"><span data-stu-id="a3909-116">Specify the method for selecting data from the source.</span></span>  
  
|<span data-ttu-id="a3909-117">Opción</span><span class="sxs-lookup"><span data-stu-id="a3909-117">Option</span></span>|<span data-ttu-id="a3909-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="a3909-118">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="a3909-119">Tabla o vista</span><span class="sxs-lookup"><span data-stu-id="a3909-119">Table or view</span></span>|<span data-ttu-id="a3909-120">Recupera datos de una tabla o vista del origen de datos [!INCLUDE[vstecado](../includes/vstecado-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a3909-120">Retrieve data from a table or view in the [!INCLUDE[vstecado](../includes/vstecado-md.md)] data source.</span></span>|  
|<span data-ttu-id="a3909-121">Comando SQL</span><span class="sxs-lookup"><span data-stu-id="a3909-121">SQL command</span></span>|<span data-ttu-id="a3909-122">Recupera datos del origen de datos [!INCLUDE[vstecado](../includes/vstecado-md.md)] mediante una consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="a3909-122">Retrieve data from the [!INCLUDE[vstecado](../includes/vstecado-md.md)] data source by using a SQL query.</span></span>|  
  
 <span data-ttu-id="a3909-123">**Versión preliminar**</span><span class="sxs-lookup"><span data-stu-id="a3909-123">**Preview**</span></span>  
 <span data-ttu-id="a3909-124">Muestra una vista previa de los resultados mediante el cuadro de diálogo **Vista de datos** .</span><span class="sxs-lookup"><span data-stu-id="a3909-124">Preview results by using the **Data View** dialog box.</span></span> <span data-ttu-id="a3909-125">**Vista previa** puede mostrar hasta 200 filas.</span><span class="sxs-lookup"><span data-stu-id="a3909-125">**Preview** can display up to 200 rows.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a3909-126">Cuando genera una vista previa de datos, las columnas con un tipo definido por el usuario CLR no contienen datos.</span><span class="sxs-lookup"><span data-stu-id="a3909-126">When you preview data, columns with a CLR user-defined type do not contain data.</span></span> <span data-ttu-id="a3909-127">En su lugar, se muestran los valores \<value too big to display> o System.Byte[].</span><span class="sxs-lookup"><span data-stu-id="a3909-127">Instead the values \<value too big to display> or System.Byte[] display.</span></span> <span data-ttu-id="a3909-128">El primero se muestra cuando se tiene acceso al origen de datos mediante el proveedor [!INCLUDE[vstecado](../includes/vstecado-md.md)] y el último, cuando se utiliza el proveedor [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="a3909-128">The former displays when the data source is accessed by using the [!INCLUDE[vstecado](../includes/vstecado-md.md)] provider, the latter when using the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Native Client provider.</span></span>  
  
## <a name="data-access-mode-dynamic-options"></a><span data-ttu-id="a3909-129">Opciones dinámicas del modo de acceso a datos</span><span class="sxs-lookup"><span data-stu-id="a3909-129">Data Access Mode Dynamic Options</span></span>  
  
### <a name="data-access-mode--table-or-view"></a><span data-ttu-id="a3909-130">Modo de acceso a datos = Tabla o vista</span><span class="sxs-lookup"><span data-stu-id="a3909-130">Data access mode = Table or view</span></span>  
 <span data-ttu-id="a3909-131">**Nombre de la tabla o la vista**</span><span class="sxs-lookup"><span data-stu-id="a3909-131">**Name of the table or the view**</span></span>  
 <span data-ttu-id="a3909-132">Seleccione el nombre de la tabla o vista de los disponibles en una lista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="a3909-132">Select the name of the table or view from a list of those available in the data source.</span></span>  
  
### <a name="data-access-mode--sql-command"></a><span data-ttu-id="a3909-133">Modo de acceso a datos = Comando SQL</span><span class="sxs-lookup"><span data-stu-id="a3909-133">Data access mode = SQL command</span></span>  
 <span data-ttu-id="a3909-134">**Texto de comando SQL**</span><span class="sxs-lookup"><span data-stu-id="a3909-134">**SQL command text**</span></span>  
 <span data-ttu-id="a3909-135">Escriba el texto de una consulta SQL, genere la consulta haciendo clic en **Generar consulta**, o bien busque el archivo que contiene el texto de la consulta haciendo clic en **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="a3909-135">Enter the text of a SQL query, build the query by clicking **Build Query**, or locate the file that contains the query text by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="a3909-136">**Generar consulta**</span><span class="sxs-lookup"><span data-stu-id="a3909-136">**Build query**</span></span>  
 <span data-ttu-id="a3909-137">Use el cuadro de diálogo **Generador de consultas** para crear visualmente la consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="a3909-137">Use the **Query Builder** dialog box to construct the SQL query visually.</span></span>  
  
 <span data-ttu-id="a3909-138">**Browse**</span><span class="sxs-lookup"><span data-stu-id="a3909-138">**Browse**</span></span>  
 <span data-ttu-id="a3909-139">Use el cuadro de diálogo **Abrir** para buscar el archivo que contiene el texto de la consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="a3909-139">Use the **Open** dialog box to locate the file that contains the text of the SQL query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3909-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a3909-140">See Also</span></span>  
 <span data-ttu-id="a3909-141">[Editor de orígenes de ADO NET &#40;página columnas&#41;](../../2014/integration-services/ado-net-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="a3909-141">[ADO NET Source Editor &#40;Columns Page&#41;](../../2014/integration-services/ado-net-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="a3909-142">[Editor de orígenes de ADO NET &#40;página salida de error&#41;](../../2014/integration-services/ado-net-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="a3909-142">[ADO NET Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/ado-net-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="a3909-143">Administrador de conexiones ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a3909-143">ADO.NET Connection Manager</span></span>](connection-manager/ado-net-connection-manager.md)  
  
  
