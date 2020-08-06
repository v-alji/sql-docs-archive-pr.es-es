---
title: Definir cálculos con nombre en una vista del origen de datos (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- modifying named calculations
- data source views [Analysis Services], named calculations
- named calculations [Analysis Services]
ms.assetid: 729e7b12-6185-4b73-8bcb-cfe459b15355
author: minewiskan
ms.author: owend
ms.openlocfilehash: ae901c340fe29c042430d928a4abaea8e8cfe84b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673374"
---
# <a name="define-named-calculations-in-a-data-source-view-analysis-services"></a><span data-ttu-id="e35fc-102">Definir cálculos con nombre en una vista del origen de datos (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="e35fc-102">Define Named Calculations in a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="e35fc-103">Un cálculo con nombre es una expresión SQL representada como una columna calculada.</span><span class="sxs-lookup"><span data-stu-id="e35fc-103">A named calculation is a SQL expression represented as a calculated column.</span></span> <span data-ttu-id="e35fc-104">Esta expresión aparece y se comporta como una columna en la tabla.</span><span class="sxs-lookup"><span data-stu-id="e35fc-104">This expression appears and behaves as a column in the table.</span></span> <span data-ttu-id="e35fc-105">Un cálculo con nombre permite ampliar el esquema relacional de las tablas o vistas existentes en una vista del origen de datos sin modificar las tablas o vistas en el origen de datos subyacente.</span><span class="sxs-lookup"><span data-stu-id="e35fc-105">A named calculation lets you extend the relational schema of existing tables or views in a data source view without modifying the tables or views in the underlying data source.</span></span> <span data-ttu-id="e35fc-106">Considere los ejemplos siguientes:</span><span class="sxs-lookup"><span data-stu-id="e35fc-106">Consider the following examples:</span></span>

-   <span data-ttu-id="e35fc-107">Cree un cálculo con nombre derivado de varias columnas en una tabla de hechos (por ejemplo, cree Tax Amount multiplicando un tipo impositivo por un precio de venta).</span><span class="sxs-lookup"><span data-stu-id="e35fc-107">Create a single named calculation that is derived from multiple columns in a fact table (for example, creating Tax Amount by multiplying a tax rate by a sales price).</span></span>

-   <span data-ttu-id="e35fc-108">Cree un nombre descriptivo para un miembro de dimensión.</span><span class="sxs-lookup"><span data-stu-id="e35fc-108">Construct a user friendly name for a dimension member.</span></span>

-   <span data-ttu-id="e35fc-109">Para mejorar el rendimiento de las consultas, cree un cálculo con nombre en la DSV en lugar de crear un miembro calculado en un cubo.</span><span class="sxs-lookup"><span data-stu-id="e35fc-109">As a query performance enhancement, create a named calculation in the DSV instead of creating a calculated member in a cube.</span></span> <span data-ttu-id="e35fc-110">Los cálculos con nombre se calculan durante el procesamiento, mientras que los miembros calculados se calculan en el tiempo de la consulta.</span><span class="sxs-lookup"><span data-stu-id="e35fc-110">Named calculations are calculated during processing whereas calculated members are calculated at query time.</span></span>

## <a name="creating-named-calculations"></a><span data-ttu-id="e35fc-111">Crear cálculos con nombre</span><span class="sxs-lookup"><span data-stu-id="e35fc-111">Creating Named Calculations</span></span>

> [!NOTE]
>  <span data-ttu-id="e35fc-112">No se puede agregar un cálculo con nombre a una consulta con nombre, ni se puede basar una consulta con nombre en una tabla que contenga un cálculo con nombre.</span><span class="sxs-lookup"><span data-stu-id="e35fc-112">You cannot add a named calculation to a named query, nor can you base a named query on a table that contains a named calculation.</span></span>

 <span data-ttu-id="e35fc-113">Cuando se crea un cálculo con nombre, se especifica un nombre, la expresión SQL y, opcionalmente, una descripción del cálculo.</span><span class="sxs-lookup"><span data-stu-id="e35fc-113">When you create a named calculation, you specify a name, the SQL expression, and, optionally, a description of the calculation.</span></span> <span data-ttu-id="e35fc-114">La expresión SQL puede hacer referencia a otras tablas de la vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="e35fc-114">The SQL expression can refer to other tables in the data source view.</span></span> <span data-ttu-id="e35fc-115">Una vez definido el cálculo con nombre, su expresión se envía al proveedor del origen de datos y se valida como la siguiente instrucción SQL en la que `<Expression>` contiene la expresión que define el cálculo con nombre.</span><span class="sxs-lookup"><span data-stu-id="e35fc-115">After the named calculation is defined, the expression in a named calculation is sent to the provider for the data source and validated as the following SQL statement in which `<Expression>` contains the expression that defines the named calculation.</span></span>

```
SELECT 
   <Table Name in Data Source>.*, 
   <Expression> AS <Column Name> 
FROM 
   <Table Name in Data Source> AS <Table Name in Data Source View>
```

 <span data-ttu-id="e35fc-116">El tipo de datos de la columna se determina por el tipo de datos del valor escalar devuelto por la expresión.</span><span class="sxs-lookup"><span data-stu-id="e35fc-116">The data type of the column is determined by the data type of the scalar value returned by the expression.</span></span> <span data-ttu-id="e35fc-117">Si el proveedor no encuentra ningún error en la expresión, la columna se agrega a la tabla.</span><span class="sxs-lookup"><span data-stu-id="e35fc-117">If the provider does not find any errors in the expression, the column is added to the table.</span></span>

 <span data-ttu-id="e35fc-118">Las columnas a las que hace referencia la expresión no deben estar calificadas o deben estar calificadas solo por el nombre de la tabla.</span><span class="sxs-lookup"><span data-stu-id="e35fc-118">Columns referenced in the expression should not be qualified or should be qualified by the table name only.</span></span> <span data-ttu-id="e35fc-119">Por ejemplo, para hacer referencia a la columna SaleAmount de una tabla, son válidos los valores `SaleAmount` o `Sales.SaleAmount` , pero `dbo.Sales.SaleAmount` genera un error.</span><span class="sxs-lookup"><span data-stu-id="e35fc-119">For example, to refer to the SaleAmount column in a table, `SaleAmount` or `Sales.SaleAmount` is valid, but `dbo.Sales.SaleAmount` generates an error.</span></span>

 <span data-ttu-id="e35fc-120">La expresión no se incluye entre paréntesis automáticamente.</span><span class="sxs-lookup"><span data-stu-id="e35fc-120">The expression is not automatically enclosed between parentheses.</span></span> <span data-ttu-id="e35fc-121">Por lo tanto, si una expresión, como una instrucción SELECT, requiere paréntesis, debe escribirlos en el cuadro **Expresión** .</span><span class="sxs-lookup"><span data-stu-id="e35fc-121">Therefore, if an expression, such as a SELECT statement, requires parentheses, you must type the parentheses in the **Expression** box.</span></span> <span data-ttu-id="e35fc-122">Por ejemplo, la siguiente expresión solo es válida si escribe los paréntesis.</span><span class="sxs-lookup"><span data-stu-id="e35fc-122">For example, the following expression is valid only if you type the parentheses.</span></span>

```
(SELECT Description FROM Categories WHERE Categories.CategoryID = CategoryID)
```

## <a name="add-or-edit-a-named-calculation"></a><span data-ttu-id="e35fc-123">Agregar o editar un cálculo con nombre</span><span class="sxs-lookup"><span data-stu-id="e35fc-123">Add or Edit a Named Calculation</span></span>

1.  <span data-ttu-id="e35fc-124">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el proyecto o conéctese a la base de datos que contiene la vista del origen de datos en que desea definir un cálculo con nombre.</span><span class="sxs-lookup"><span data-stu-id="e35fc-124">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database that contains the data source view in which you wish to define a named calculation.</span></span>

2.  <span data-ttu-id="e35fc-125">En el Explorador de soluciones, expanda la carpeta **Vistas del origen de datos** y, después, haga doble clic en la vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="e35fc-125">In Solution Explorer, expand the **Data Source Views** folder, then double-click the data source view.</span></span>

3.  <span data-ttu-id="e35fc-126">Haga clic con el botón derecho en la tabla en la que quiere definir el cálculo con nombre en el panel **Tablas** o **Diagrama** y luego haga clic en **Nuevo cálculo con nombre**.</span><span class="sxs-lookup"><span data-stu-id="e35fc-126">Right-click the table in which you wish to define the named calculation in either the **Tables** or the **Diagram** pane, and then click **New Named Calculation**.</span></span> <span data-ttu-id="e35fc-127">Asegúrese de hacer clic con el botón secundario en el nombre de tabla, y no en un atributo.</span><span class="sxs-lookup"><span data-stu-id="e35fc-127">Be sure to right-click on the table name, and not on an attribute.</span></span> <span data-ttu-id="e35fc-128">El menú debe ser similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="e35fc-128">The menu should look like the following:</span></span>

     <span data-ttu-id="e35fc-129">![Captura de pantalla del espacio de trabajo de diagrama, menú contextual](../media/ssas-olapdsv-diagram.gif "Captura de pantalla del espacio de trabajo de diagrama, menú contextual")</span><span class="sxs-lookup"><span data-stu-id="e35fc-129">![Screenshot of diagram workspace, right-click menu](../media/ssas-olapdsv-diagram.gif "Screenshot of diagram workspace, right-click menu")</span></span>

    > [!NOTE]
    >  <span data-ttu-id="e35fc-130">Para buscar una tabla o una vista, puede usar la opción **Buscar tabla** haciendo clic en el menú **vista del origen de datos** o haciendo clic con el botón derecho en un área abierta de los paneles **tablas** o **Diagrama** .</span><span class="sxs-lookup"><span data-stu-id="e35fc-130">To locate a table or view, you can use the **Find Table** option by either clicking the **Data Source View** menu or right-clicking in an open area of the **Tables** or **Diagram** panes.</span></span>

4.  <span data-ttu-id="e35fc-131">En el cuadro de diálogo **Crear cálculo con nombre** , realice las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="e35fc-131">In the **Create Named Calculations** dialog box, do the following:</span></span>

    -   <span data-ttu-id="e35fc-132">En el cuadro de texto **Nombre de columna** , escriba el nombre de la nueva columna.</span><span class="sxs-lookup"><span data-stu-id="e35fc-132">In the **Column name** text box, type the name of the new column.</span></span>

    -   <span data-ttu-id="e35fc-133">En el cuadro de texto **Descripción** , escriba una descripción para la nueva columna.</span><span class="sxs-lookup"><span data-stu-id="e35fc-133">In the **Description** text box type a description for the new column.</span></span>

    -   <span data-ttu-id="e35fc-134">En el cuadro de texto **Expresión** , escriba la expresión que produzca el contenido de la nueva columna en el dialecto SQL adecuado para el proveedor de datos.</span><span class="sxs-lookup"><span data-stu-id="e35fc-134">In the **Expression** text box, type the expression that yields the content of the new column in the SQL dialect appropriate for the data provider.</span></span>

5.  <span data-ttu-id="e35fc-135">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="e35fc-135">Click **OK**.</span></span>

     <span data-ttu-id="e35fc-136">La columna de cálculo con nombre aparecerá como la última columna de la tabla de la vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="e35fc-136">The named calculation column appears as the last column in the data source view table.</span></span> <span data-ttu-id="e35fc-137">El símbolo de una calculadora indica que la columna contiene un cálculo con nombre.</span><span class="sxs-lookup"><span data-stu-id="e35fc-137">A calculator symbol indicates that the column contains a named calculation.</span></span>

## <a name="delete-a-named-calculation"></a><span data-ttu-id="e35fc-138">Eliminar un cálculo con nombre</span><span class="sxs-lookup"><span data-stu-id="e35fc-138">Delete a Named Calculation</span></span>
 <span data-ttu-id="e35fc-139">Si trata de eliminar un cálculo con nombre, se le presenta una lista de los objetos definidos en el proyecto o la base de datos que no serán válidos tras la eliminación.</span><span class="sxs-lookup"><span data-stu-id="e35fc-139">When you attempt to delete a named calculation, you are prompted with a list of the objects defined in the project or database that will be invalidated by the deletion.</span></span> <span data-ttu-id="e35fc-140">Revise la lista cuidadosamente antes de eliminar el cálculo.</span><span class="sxs-lookup"><span data-stu-id="e35fc-140">Review the list carefully before deleting the calculation.</span></span>

## <a name="see-also"></a><span data-ttu-id="e35fc-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e35fc-141">See Also</span></span>
 [<span data-ttu-id="e35fc-142">Definir consultas con nombre en una vista del origen de datos &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="e35fc-142">Define Named Queries in a Data Source View &#40;Analysis Services&#41;</span></span>](define-named-queries-in-a-data-source-view-analysis-services.md)


