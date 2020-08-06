---
title: Configurar un contenedor de bucles foreach | Microsoft Docs
ms.custom: ''
ms.date: 08/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Foreach Loop containers
- containers [Integration Services], Foreach Loop
ms.assetid: 519c6f96-5e1f-47d2-b96a-d49946948c25
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 85fb399f51e22e091fac9b1d8d332b9a12e7d77e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663634"
---
# <a name="configure-a-foreach-loop-container"></a><span data-ttu-id="b93c9-102">Configurar un contenedor de bucles Foreach</span><span class="sxs-lookup"><span data-stu-id="b93c9-102">Configure a Foreach Loop Container</span></span>
  <span data-ttu-id="b93c9-103">Este procedimiento describe cómo configurar un contenedor de bucles Foreach, incluyendo expresiones de propiedad en los niveles de enumerador y contenedor.</span><span class="sxs-lookup"><span data-stu-id="b93c9-103">This procedure describes how to configure a Foreach Loop container, including property expressions at the enumerator and container levels.</span></span>  
  
### <a name="to-configure-the-foreach-loop-container"></a><span data-ttu-id="b93c9-104">Para configurar el contenedor de bucles Foreach</span><span class="sxs-lookup"><span data-stu-id="b93c9-104">To configure the Foreach Loop container</span></span>  
  
1.  <span data-ttu-id="b93c9-105">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="b93c9-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="b93c9-106">Haga clic en la pestaña **Flujo de control** y haga doble clic en el bucle Foreach.</span><span class="sxs-lookup"><span data-stu-id="b93c9-106">Click the **Control Flow** tab and double-click the Foreach Loop.</span></span>  
  
3.  <span data-ttu-id="b93c9-107">En el cuadro de diálogo **Editor de bucles Foreach** , haga clic en **General** y, opcionalmente, modifique el nombre y descripción del bucle Foreach.</span><span class="sxs-lookup"><span data-stu-id="b93c9-107">In the **Foreach Loop Editor** dialog box, click **General** and, optionally, modify the name and description of the Foreach Loop.</span></span>  
  
4.  <span data-ttu-id="b93c9-108">Haga clic en **Colección** y seleccione un tipo de enumerador de la lista **Enumerador** .</span><span class="sxs-lookup"><span data-stu-id="b93c9-108">Click **Collection** and select an enumerator type from the **Enumerator** list.</span></span>  
  
5.  <span data-ttu-id="b93c9-109">Especifique un enumerador y establezca las opciones del enumerador de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="b93c9-109">Specify an enumerator and set enumerator options as follows:</span></span>  
  
    -   <span data-ttu-id="b93c9-110">Para usar el enumerador de archivos para Foreach, proporcione la carpeta que contiene los archivos que se deben enumerar, especifique un filtro para el nombre y tipo de archivo, y especifique si es necesario devolver el nombre de archivo completo.</span><span class="sxs-lookup"><span data-stu-id="b93c9-110">To usethe Foreach File enumerator, provide the folder that contains the files to enumerate, specify a filter for the file name and type, and specify whether the fully qualified file name should be returned.</span></span> <span data-ttu-id="b93c9-111">Además, indique si se deben recorrer las subcarpetas para obtener más archivos.</span><span class="sxs-lookup"><span data-stu-id="b93c9-111">Also, indicate whether to recurse through subfolders for more files.</span></span>  
  
    -   <span data-ttu-id="b93c9-112">Para usar el enumerador de elementos para Foreach, haga clic en **Columnas**y, en el cuadro de diálogo **Columnas For Each Item** , haga clic en **Agregar** para agregar columnas.</span><span class="sxs-lookup"><span data-stu-id="b93c9-112">To use the Foreach Item enumerator, click **Columns**, and, in the **For Each Item Columns** dialog box, click **Add** to add columns.</span></span> <span data-ttu-id="b93c9-113">Seleccione un tipo de datos de la lista **Tipo de datos** para cada columna y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b93c9-113">Select a data type in the **Data Type** list for each column, and click **OK**.</span></span>  
  
         <span data-ttu-id="b93c9-114">Escriba valores en las columnas o seleccione valores de las listas.</span><span class="sxs-lookup"><span data-stu-id="b93c9-114">Type values in the columns or select values from lists.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="b93c9-115">Para agregar una nueva fila, haga clic en cualquier punto fuera de la celda en la que escribió.</span><span class="sxs-lookup"><span data-stu-id="b93c9-115">To add a new row, click anywhere outside the cell in which you typed.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="b93c9-116">Si un valor no es compatible con el tipo de datos de la columna, el texto se resalta.</span><span class="sxs-lookup"><span data-stu-id="b93c9-116">If a value is not compatible with the column data type, the text is highlighted.</span></span>  
  
    -   <span data-ttu-id="b93c9-117">Para usar el enumerador Foreach ADO, seleccione una variable existente o haga clic en **Nueva variable** en la lista **Variable de origen de objeto ADO** para especificar la variable que contiene el nombre del objeto ADO que se debe enumerar, y seleccione una opción de modo de enumeración.</span><span class="sxs-lookup"><span data-stu-id="b93c9-117">To use the Foreach ADO enumerator, select an existing variable or click **New variable** in the **ADO object source variable** list to specify the variable that contains the name of the ADO object to enumerate, and select an enumeration mode option.</span></span>  
  
         <span data-ttu-id="b93c9-118">Si se crea una nueva variable, establezca las propiedades de la variable en el cuadro de diálogo **Agregar variable** .</span><span class="sxs-lookup"><span data-stu-id="b93c9-118">If creating a new variable, set the variable properties in the **Add Variable** dialog box.</span></span>  
  
    -   <span data-ttu-id="b93c9-119">Para usar el Enumerador de conjunto de filas del esquema para Foreach de ADO.NET, seleccione una conexión ADO.NET existente o haga clic en **Nueva conexión** en la lista **Conexión** y luego seleccione un esquema.</span><span class="sxs-lookup"><span data-stu-id="b93c9-119">To use the Foreach ADO.NET Schema Rowset enumerator, select an existing ADO.NET connection or click **New connection** in the **Connection** list, and then select a schema.</span></span>  
  
         <span data-ttu-id="b93c9-120">Si lo desea, haga clic en **Establecer restricciones** y seleccione las restricciones de esquemas, seleccione la variable que contenga el valor de restricción o escriba el valor de restricción, y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b93c9-120">Optionally, click **Set Restrictions** and select schema restrictions, select the variable that contains the restriction value or type the restriction value, and click **OK**.</span></span>  
  
    -   <span data-ttu-id="b93c9-121">Para usar el Enumerador de variable para Foreach, seleccione una variable en la lista **Variable** .</span><span class="sxs-lookup"><span data-stu-id="b93c9-121">To use the Foreach From Variable enumerator, select a variable in the **Variable** list.</span></span>  
  
    -   <span data-ttu-id="b93c9-122">Para usar el enumerador NodeList para Foreach, haga clic en DocumentSourceType, seleccione el tipo de origen de la lista y, después, haga clic en DocumentSource.</span><span class="sxs-lookup"><span data-stu-id="b93c9-122">To use the Foreach NodeList enumerator, click DocumentSourceType and select the source type from the list, and then click DocumentSource.</span></span> <span data-ttu-id="b93c9-123">Según el valor seleccionado para DocumentSourceType, seleccione una variable o una conexión de archivo de la lista, cree una variable o una conexión de archivo, o bien escriba el origen XML en el **Editor de origen del documento**.</span><span class="sxs-lookup"><span data-stu-id="b93c9-123">Depending on the value selected for DocumentSourceType, select a variable or a file connection from the list, create a new variable or file connection, or type the XML source in the **Document Source Editor**.</span></span>  
  
         <span data-ttu-id="b93c9-124">Después, haga clic en EnumerationType y seleccione el tipo de enumeración de la lista.</span><span class="sxs-lookup"><span data-stu-id="b93c9-124">Next, click EnumerationType and select an enumeration type from the list.</span></span> <span data-ttu-id="b93c9-125">Si EnumerationType es **Navigator, Node o NodeText**, haga clic en OuterXPathStringSourceType, seleccione el tipo de origen y, después, haga clic en OuterXPathString.</span><span class="sxs-lookup"><span data-stu-id="b93c9-125">If EnumerationType is **Navigator, Node, or NodeText**, click OuterXPathStringSourceType and select the source type, and then click OuterXPathString.</span></span> <span data-ttu-id="b93c9-126">Según el valor establecido para OuterXPathStringSourceType, seleccione una variable o una conexión de archivo de la lista, cree una variable o una conexión de archivo, o bien escriba la cadena de la expresión XPath (lenguaje de rutas XML) externa.</span><span class="sxs-lookup"><span data-stu-id="b93c9-126">Depending on the value set for OuterXPathStringSourceType, select a variable or a file connection from the list, create a new variable or file connection, or type the string for the outer XML Path Language (XPath) expression.</span></span>  
  
         <span data-ttu-id="b93c9-127">Si EnumerationType es **ElementCollection**, establezca OuterXPathStringSourceType y OuterXPathString como se ha descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="b93c9-127">If EnumerationType is **ElementCollection**,set OuterXPathStringSourceType and OuterXPathString as described above.</span></span> <span data-ttu-id="b93c9-128">Después, haga clic en InnerElementType, seleccione un tipo de enumeración para los elementos internos y, después, haga clic en InnerXPathStringSourceType.</span><span class="sxs-lookup"><span data-stu-id="b93c9-128">Then, click InnerElementType and select an enumeration type for the inner elements, and then click InnerXPathStringSourceType.</span></span> <span data-ttu-id="b93c9-129">Según el valor establecido para InnerXPathStringSourceType, seleccione una variable o conexión de archivo, cree una variable o una conexión de archivo, o bien escriba la cadena para la expresión XPath interna.</span><span class="sxs-lookup"><span data-stu-id="b93c9-129">Depending on the value set for InnerXPathStringSourceType, select a variable or a file connection, create a new variable or file connection, or type the string for the inner XPath expression.</span></span>  
  
    -   <span data-ttu-id="b93c9-130">Para usar el Enumerador de SMO para Foreach, seleccione una conexión ADO.NET existente o haga clic en **Nueva conexión** en la lista **Conexión** y luego escriba la cadena que se debe usar o haga clic en **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="b93c9-130">To use the Foreach SMO enumerator, select an existing ADO.NET connection or click **New connection** in the **Connection** list, and then either type the string to use or click **Browse**.</span></span> <span data-ttu-id="b93c9-131">Si hace clic en **Examinar**, en el cuadro de diálogo **Seleccionar enumeración de SMO** , seleccione el tipo de objeto que se debe enumerar y el tipo de enumeración, y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b93c9-131">If you click **Browse**, in the **Select SMO Enumeration** dialog box, select the object type to enumerate and the enumeration type, and click **OK**.</span></span>  
  
6.  <span data-ttu-id="b93c9-132">También puede hacer clic en el botón Examinar ( **…** ) en el cuadro de texto **Expresiones** de la página **Colección** para crear expresiones que actualicen valores de propiedades.</span><span class="sxs-lookup"><span data-stu-id="b93c9-132">Optionally, click the browse button **(...)** in the **Expressions** text box on the **Collection** page to create expressions that update property values.</span></span> <span data-ttu-id="b93c9-133">Para más información, vea [Agregar o cambiar una expresión de propiedad](expressions/add-or-change-a-property-expression.md).</span><span class="sxs-lookup"><span data-stu-id="b93c9-133">For more information, see [Add or Change a Property Expression](expressions/add-or-change-a-property-expression.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b93c9-134">Las propiedades de la lista **Propiedad** varían según el enumerador.</span><span class="sxs-lookup"><span data-stu-id="b93c9-134">The properties listed in the **Property** list varies by enumerator.</span></span>  
  
7.  <span data-ttu-id="b93c9-135">Opcionalmente, haga clic en **Asignaciones de variables** para asignar propiedades de objetos al valor de la colección y luego haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b93c9-135">Optionally, click **Variable Mappings** to map object properties to the collection value, and then do the following:</span></span>  
  
    1.  <span data-ttu-id="b93c9-136">En la lista **Variables**, seleccione una variable o haga clic en **\<New Variable>** para crear una.</span><span class="sxs-lookup"><span data-stu-id="b93c9-136">In the **Variables** list, select a variable or click **\<New Variable>** to create a new variable.</span></span>  
  
    2.  <span data-ttu-id="b93c9-137">Si agrega una nueva variable, establezca las propiedades de la variable en el cuadro de diálogo **Agregar variable** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b93c9-137">If you add a new variable, set the variable properties in the **Add Variable** dialog box and click **OK**.</span></span>  
  
    3.  <span data-ttu-id="b93c9-138">Si usa el enumerador Foreach Item, puede actualizar el valor de índice en la lista **Índice** .</span><span class="sxs-lookup"><span data-stu-id="b93c9-138">If you use the For Each Item enumerator, you can update the index value in the **Index** list.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="b93c9-139">El valor de índice indica cuál es la columna en el elemento que se debe asignar a la variable.</span><span class="sxs-lookup"><span data-stu-id="b93c9-139">The index value indicates which column in the item to map to the variable.</span></span> <span data-ttu-id="b93c9-140">Solo el enumerador Foreach Item puede usar un valor de índice que no sea 0.</span><span class="sxs-lookup"><span data-stu-id="b93c9-140">Only the For Each Item enumerator can use an index value other than 0.</span></span>  
  
8.  <span data-ttu-id="b93c9-141">Opcionalmente, haga clic en **Expresiones** y, en la página **Expresiones** , cree expresiones de propiedades para las propiedades del contenedor de bucles Foreach.</span><span class="sxs-lookup"><span data-stu-id="b93c9-141">Optionally, click **Expressions** and, on the **Expressions** page, create property expressions for the properties of the Foreach Loop container.</span></span> <span data-ttu-id="b93c9-142">Para más información, vea [Agregar o cambiar una expresión de propiedad](expressions/add-or-change-a-property-expression.md).</span><span class="sxs-lookup"><span data-stu-id="b93c9-142">For more information, see [Add or Change a Property Expression](expressions/add-or-change-a-property-expression.md).</span></span>  
  
9. <span data-ttu-id="b93c9-143">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="b93c9-143">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b93c9-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b93c9-144">See Also</span></span>  
 [<span data-ttu-id="b93c9-145">Contenedor Foreach Loop</span><span class="sxs-lookup"><span data-stu-id="b93c9-145">Foreach Loop Container</span></span>](control-flow/foreach-loop-container.md)  
  
  
