---
title: Editor de consultas avanzadas de minería de datos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 27e7fc46-689d-43a4-9647-1c27d182bdd6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2aadf4df75b1ccf6001ad8e97d589ce5666f56ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670234"
---
# <a name="advanced-data-mining-query-editor"></a><span data-ttu-id="ee82d-102">Editor de consultas avanzadas de minería de datos</span><span class="sxs-lookup"><span data-stu-id="ee82d-102">Advanced Data Mining Query Editor</span></span>
  <span data-ttu-id="ee82d-103">La **consulta de minería de datos editor avanzado** es una herramienta que le ayudará a crear modelos y consultas personalizados.</span><span class="sxs-lookup"><span data-stu-id="ee82d-103">The **Data Mining Query Advanced Editor** is a tool to help you build custom models and queries.</span></span>  
  
 <span data-ttu-id="ee82d-104">El editor proporciona un conjunto de plantillas con los vínculos en los que se puede hacer clic.</span><span class="sxs-lookup"><span data-stu-id="ee82d-104">The editor provides a set of templates with clickable links.</span></span> <span data-ttu-id="ee82d-105">Basta con hacer clic en cada vínculo y usar los cuadros de diálogo para seleccionar objetos o valores y crear instrucciones complejas de Extensiones de minería de datos (DMX).</span><span class="sxs-lookup"><span data-stu-id="ee82d-105">Just click each link, and use the dialog boxes to select objects or values and build complex Data Mining Extensions (DMX) statements.</span></span> <span data-ttu-id="ee82d-106">Puede cambiar la vista al modelo de edición de texto para modificar la instrucción DMX manualmente.</span><span class="sxs-lookup"><span data-stu-id="ee82d-106">You can switch the view to text editing model to modify the DMX statement manually.</span></span>  
  
 <span data-ttu-id="ee82d-107">Para ir al **editor avanzado consulta de minería de datos**, haga clic en **consulta** y, a continuación, haga clic en **avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="ee82d-107">To get to the **Data Mining Query Advanced Editor**, click **Query** and then click **Advanced**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="ee82d-108">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="ee82d-108">UI element list</span></span>  
 <span data-ttu-id="ee82d-109">**Consulta DMX**</span><span class="sxs-lookup"><span data-stu-id="ee82d-109">**DMX Query pane**</span></span>  
 <span data-ttu-id="ee82d-110">Aquí puede ver la instrucción DMX actual.</span><span class="sxs-lookup"><span data-stu-id="ee82d-110">Here you can see the current DMX statement.</span></span>  
  
 <span data-ttu-id="ee82d-111">Haga clic con el botón secundario en este panel para copiar la instrucción DMX actual.</span><span class="sxs-lookup"><span data-stu-id="ee82d-111">Right-click in the pane to copy the current DMX statement.</span></span>  
  
 <span data-ttu-id="ee82d-112">También puede hacer clic en cualquier parte resaltada de la instrucción para ver las opciones específicas de esa cláusula.</span><span class="sxs-lookup"><span data-stu-id="ee82d-112">You can click any highlighted part of the statement to get options specific to that clause.</span></span> <span data-ttu-id="ee82d-113">Por ejemplo, para eliminar, agregar o editar una salida, haga clic con el botón secundario en el **\<Output>** vínculo.</span><span class="sxs-lookup"><span data-stu-id="ee82d-113">For example, to delete, add, or edit an output, right-click the **\<Output>** link.</span></span>  
  
 <span data-ttu-id="ee82d-114">**Editar consulta/Generador de consultas**</span><span class="sxs-lookup"><span data-stu-id="ee82d-114">**Edit Query/Query Builder**</span></span>  
 <span data-ttu-id="ee82d-115">Use este botón para cambiar el editor entre un editor de texto, donde puede escribir instrucciones DMX directamente. y el **generador de consultas**, que le ayuda a crear una instrucción DMX.</span><span class="sxs-lookup"><span data-stu-id="ee82d-115">Use this button to switch the editor between a text editor, where you can write DMX statements directly; and the **Query Builder**, which helps you build a DMX statement.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ee82d-116">**ADVERTENCIA:** Si cambia de vista antes de que se haya ejecutado la consulta, aparece un mensaje que indica que podría perder algunos cambios.</span><span class="sxs-lookup"><span data-stu-id="ee82d-116">**Warning:** If you switch views before the query has been run, a message appears stating that you might lose some changes.</span></span> <span data-ttu-id="ee82d-117">Si la instrucción DMX es válida, en muchos casos el **generador de consultas** podría convertir correctamente estos cambios.</span><span class="sxs-lookup"><span data-stu-id="ee82d-117">If the DMX statement is valid, in many cases the **Query Builder** might successfully convert these changes.</span></span> <span data-ttu-id="ee82d-118">Sin embargo, si ha creado una instrucción DMX muy compleja, debe guardar el trabajo antes de cambiar de vista.</span><span class="sxs-lookup"><span data-stu-id="ee82d-118">However, if you have built a particularly complex DMX statement, you should definitely save your work before switching views.</span></span>  
  
 <span data-ttu-id="ee82d-119">**Plantillas DMX**</span><span class="sxs-lookup"><span data-stu-id="ee82d-119">**DMX Templates**</span></span>  
 <span data-ttu-id="ee82d-120">Haga clic en esta opción y seleccione en la lista una de las plantillas que contienen los ejemplos DMX.</span><span class="sxs-lookup"><span data-stu-id="ee82d-120">Click and select from a list of templates that contain DMX examples.</span></span> <span data-ttu-id="ee82d-121">Las plantillas proporcionan información solo sobre cada tipo de consulta de modelo o de predicción que puede necesitar, incluidas las consultas que usan tablas anidadas, e instrucciones DMX para administrar los modelos.</span><span class="sxs-lookup"><span data-stu-id="ee82d-121">The templates provide just about every type of model or prediction query that you might need, including queries that use nested tables, and DMX statements to manage models.</span></span> <span data-ttu-id="ee82d-122">Aunque tenga conocimientos de DMX, las plantillas pueden ahorrarle tiempo al mostrar la sintaxis correcta.</span><span class="sxs-lookup"><span data-stu-id="ee82d-122">Even if you know some DMX, the templates can save you time by getting the syntax right.</span></span>  
  
 <span data-ttu-id="ee82d-123">**Elegir modelo**</span><span class="sxs-lookup"><span data-stu-id="ee82d-123">**Choose Model**</span></span>  
 <span data-ttu-id="ee82d-124">Haga clic aquí para ver una lista de los modelos de minería de datos disponibles en la conexión actual.</span><span class="sxs-lookup"><span data-stu-id="ee82d-124">Click to view a list of data mining models available on the current connection.</span></span>  
  
 <span data-ttu-id="ee82d-125">También puede mostrar una lista de modelos disponibles haciendo clic en el nombre del modelo en la instrucción DMX en el panel **consulta DMX** .</span><span class="sxs-lookup"><span data-stu-id="ee82d-125">You can also display a list of available models by clicking on the model name in the DMX statement in the **DMX Query** pane.</span></span> <span data-ttu-id="ee82d-126">El nombre del modelo suele aparecer resaltado en rojo.</span><span class="sxs-lookup"><span data-stu-id="ee82d-126">The model name is typically highlighted in red.</span></span>  
  
 <span data-ttu-id="ee82d-127">**Selección de entradas**</span><span class="sxs-lookup"><span data-stu-id="ee82d-127">**Select Input**</span></span>  
 <span data-ttu-id="ee82d-128">Haga clic en esta opción para elegir los datos que se usarán como entrada para el modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="ee82d-128">Click to choose the data to use as input to the mining model.</span></span> <span data-ttu-id="ee82d-129">Si no se ha especificado ningún origen de datos, también puede hacer clic en el **\<Input>** vínculo, que aparece resaltado en rojo en el panel **consulta DMX** .</span><span class="sxs-lookup"><span data-stu-id="ee82d-129">If no data source has been specified, you can also click the **\<Input>** link, which is highlighted in red in the **DMX Query** pane.</span></span>  
  
 <span data-ttu-id="ee82d-130">Seleccione \*\* \@ InputRowset\*\* en la lista desplegable para abrir el cuadro de diálogo **reemplazar InputRowset** y modificar una entrada existente.</span><span class="sxs-lookup"><span data-stu-id="ee82d-130">Select **\@InputRowset** from the dropdown list to open the **Replace InputRowset** dialog box and modify an existing input.</span></span>  
  
 <span data-ttu-id="ee82d-131">Seleccione **Agregar entrada** para abrir el cuadro de diálogo **Agregar entrada** y especifique un nuevo origen de datos.</span><span class="sxs-lookup"><span data-stu-id="ee82d-131">Select **Add Input** to open the **Add Input** dialog box and specify a new data source.</span></span>  
  
 <span data-ttu-id="ee82d-132">También puede modificar una entrada existente si hace clic en el vínculo \*\* \@ InputRowset\*\* , que aparece resaltado en rojo en el panel consulta DMX.</span><span class="sxs-lookup"><span data-stu-id="ee82d-132">You can also modify an existing input by clicking the **\@InputRowset** link, which is highlighted in red in the DMX Query pane.</span></span>  
  
 <span data-ttu-id="ee82d-133">**Asignar columnas**</span><span class="sxs-lookup"><span data-stu-id="ee82d-133">**Map Columns**</span></span>  
 <span data-ttu-id="ee82d-134">Seleccione columnas del modelo de minería de datos y asígnelas a columnas del origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="ee82d-134">Select columns from the mining model and then map them to columns in the external data source.</span></span>  
  
 <span data-ttu-id="ee82d-135">También puede hacer clic en el vínculo resaltado **\<Mapping>** en el panel consulta DMX.</span><span class="sxs-lookup"><span data-stu-id="ee82d-135">You can also click the highlighted **\<Mapping>** link in the DMX Query pane.</span></span>  
  
 <span data-ttu-id="ee82d-136">**Agregar salida**</span><span class="sxs-lookup"><span data-stu-id="ee82d-136">**Add Output**</span></span>  
 <span data-ttu-id="ee82d-137">Haga clic en esta opción para elegir las columnas que deben incluirse en la salida como parte de una consulta de predicción.</span><span class="sxs-lookup"><span data-stu-id="ee82d-137">Click to choose the columns that should be output as part of a prediction query.</span></span>  
  
 <span data-ttu-id="ee82d-138">También puede hacer clic en el vínculo resaltado **\<Add Output>** en el panel consulta DMX.</span><span class="sxs-lookup"><span data-stu-id="ee82d-138">You can also click the highlighted **\<Add Output>** link in the DMX Query pane.</span></span>  
  
 <span data-ttu-id="ee82d-139">**Columnas del modelo**</span><span class="sxs-lookup"><span data-stu-id="ee82d-139">**Model Columns**</span></span>  
 <span data-ttu-id="ee82d-140">Muestra una lista de las columnas del modelo de minería de datos seleccionado.</span><span class="sxs-lookup"><span data-stu-id="ee82d-140">Lists the columns in the selected mining model.</span></span> <span data-ttu-id="ee82d-141">Si aparece un símbolo en forma de rombo al lado del nombre de la columna, significa que se trata de una columna de predicción.</span><span class="sxs-lookup"><span data-stu-id="ee82d-141">A diamond mark next to the column name indicates that the column is a predictable column.</span></span>  
  
 <span data-ttu-id="ee82d-142">**Columnas de entrada**</span><span class="sxs-lookup"><span data-stu-id="ee82d-142">**Input Columns**</span></span>  
 <span data-ttu-id="ee82d-143">Muestra una lista de las columnas del origen de datos externo que se han agregado como entradas.</span><span class="sxs-lookup"><span data-stu-id="ee82d-143">Lists the columns from the external data source that have been added as inputs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee82d-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ee82d-144">See Also</span></span>  
 [<span data-ttu-id="ee82d-145">&#40;de consultas SQL Server complementos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="ee82d-145">Query &#40;SQL Server Data Mining Add-ins&#41;</span></span>](query-sql-server-data-mining-add-ins.md)  
  
  
