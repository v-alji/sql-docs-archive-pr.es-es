---
title: Modificar la dimensión Date | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 4689d780-4bf6-4cf8-8fde-eb3f15dd668a
author: minewiskan
ms.author: owend
ms.openlocfilehash: b4978e9fe3acd93ddfdca707d2c2353bf171ba12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674430"
---
# <a name="modifying-the-date-dimension"></a><span data-ttu-id="a8ac5-102">Modificar la dimensión Date</span><span class="sxs-lookup"><span data-stu-id="a8ac5-102">Modifying the Date Dimension</span></span>
  <span data-ttu-id="a8ac5-103">En las tareas de este tema, debe crear una jerarquía definida por el usuario y cambiar los nombres de miembro que se muestran para los atributos Date, Month, Calendar Quarter y Calendar Semester.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-103">In the tasks in this topic, you create a user-defined hierarchy and change the member names that are displayed for the Date, Month, Calendar Quarter, and Calendar Semester attributes.</span></span> <span data-ttu-id="a8ac5-104">También definirá claves compuestas para los atributos, controlará el criterio de ordenación de los miembros de dimensión y definirá las relaciones de atributo.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-104">You also define composite keys for attributes, control the sort order of dimension members, and define attribute relationships.</span></span>  
  
## <a name="adding-a-named-calculation"></a><span data-ttu-id="a8ac5-105">Agregar un cálculo con nombre</span><span class="sxs-lookup"><span data-stu-id="a8ac5-105">Adding a Named Calculation</span></span>  
 <span data-ttu-id="a8ac5-106">Puede agregar un cálculo con nombre, que es una expresión SQL representada como columna calculada en una tabla de la vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-106">You can add a named calculation, which is a SQL expression that is represented as a calculated column, to a table in a data source view.</span></span> <span data-ttu-id="a8ac5-107">Aparece la expresión y se comporta como columna en la tabla.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-107">The expression appears and behaves as a column in the table.</span></span> <span data-ttu-id="a8ac5-108">Los cálculos con nombre permiten ampliar el esquema relacional de las tablas existentes de la vista del origen de datos sin modificar la tabla en el origen de datos subyacente.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-108">Named calculations enable you to extend the relational schema of existing tables in a data source view without modifying the table in the underlying data source.</span></span> <span data-ttu-id="a8ac5-109">Para obtener más información, vea [definir cálculos con nombre en una vista del origen de datos &#40;Analysis Services&#41;](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md)</span><span class="sxs-lookup"><span data-stu-id="a8ac5-109">For more information, see [Define Named Calculations in a Data Source View &#40;Analysis Services&#41;](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md)</span></span>  
  
#### <a name="to-add-a-named-calculation"></a><span data-ttu-id="a8ac5-110">Para agregar un cálculo con nombre</span><span class="sxs-lookup"><span data-stu-id="a8ac5-110">To add a named calculation</span></span>  
  
1.  <span data-ttu-id="a8ac5-111">Para abrir la vista del origen de datos **Adventure Works DW 2012** , haga doble clic en ella en la carpeta **Vistas del origen de datos** del Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-111">To open the **Adventure Works DW 2012** data source view, double-click it in the **Data Source Views** folder in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="a8ac5-112">Cerca de la parte inferior del panel **tablas** , haga clic con el botón secundario `Date` y, a continuación, haga clic en **nuevo cálculo con nombre**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-112">Near the bottom of the **Tables** pane, right-click `Date`, and then click **New Named Calculation**.</span></span>  
  
3.  <span data-ttu-id="a8ac5-113">En el cuadro de diálogo **crear cálculo con nombre** , escriba `SimpleDate` en el cuadro **nombre de columna** y, a continuación, escriba o copie y pegue la siguiente `DATENAME` instrucción en el cuadro **expresión** :</span><span class="sxs-lookup"><span data-stu-id="a8ac5-113">In the **Create Named Calculation** dialog box, type `SimpleDate` in the **Column name** box, and then type or copy and paste the following `DATENAME` statement in the **Expression** box:</span></span>  
  
    ```  
    DATENAME(mm, FullDateAlternateKey) + ' ' +  
    DATENAME(dd, FullDateAlternateKey) + ', ' +  
    DATENAME(yy, FullDateAlternateKey)  
    ```  
  
     <span data-ttu-id="a8ac5-114">La instrucción `DATENAME` extrae los valores de año, mes y día de la columna FullDateAlternateKey.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-114">The `DATENAME` statement extracts the year, month, and day values from the FullDateAlternateKey column.</span></span> <span data-ttu-id="a8ac5-115">Usará esta nueva columna como el nombre mostrado para el atributo FullDateAlternateKey.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-115">You will use this new column as the displayed name for the FullDateAlternateKey attribute.</span></span>  
  
4.  <span data-ttu-id="a8ac5-116">Haga clic en **Aceptar**y, a continuación, expanda `Date` en el panel **tablas** .</span><span class="sxs-lookup"><span data-stu-id="a8ac5-116">Click **OK**, and then expand `Date` in the **Tables** pane.</span></span>  
  
     <span data-ttu-id="a8ac5-117">El `SimpleDate` cálculo con nombre aparece en la lista de columnas de la tabla Date, con un icono que indica que se trata de un cálculo con nombre.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-117">The `SimpleDate` named calculation appears in the list of columns in the Date table, with an icon that indicates that it is a named calculation.</span></span>  
  
5.  <span data-ttu-id="a8ac5-118">En el menú **Archivo**, haga clic en **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-118">On the **File** menu, click **Save All**.</span></span>  
  
6.  <span data-ttu-id="a8ac5-119">En el panel **tablas** , haga clic con el botón secundario `Date` y, a continuación, haga clic en **explorar datos**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-119">In the **Tables** pane, right-click `Date`, and then click **Explore Data**.</span></span>  
  
7.  <span data-ttu-id="a8ac5-120">Desplácese hacia la derecha para revisar la última columna de la vista **Explorar la tabla Date** .</span><span class="sxs-lookup"><span data-stu-id="a8ac5-120">Scroll to the right to review the last column in the **Explore Date Table** view.</span></span>  
  
     <span data-ttu-id="a8ac5-121">Observe que la `SimpleDate` columna aparece en la vista del origen de datos, concatenando correctamente los datos de varias columnas del origen de datos subyacente, sin modificar el origen de datos original.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-121">Notice that the `SimpleDate` column appears in the data source view, correctly concatenating data from several columns from the underlying data source, without modifying the original data source.</span></span>  
  
8.  <span data-ttu-id="a8ac5-122">Cierre la vista **Explorar la tabla Date** .</span><span class="sxs-lookup"><span data-stu-id="a8ac5-122">Close the **Explore Date Table** view.</span></span>  
  
## <a name="using-the-named-calculation-for-member-names"></a><span data-ttu-id="a8ac5-123">Usar el cálculo con nombre para los nombres de miembro</span><span class="sxs-lookup"><span data-stu-id="a8ac5-123">Using the Named Calculation for Member Names</span></span>  
 <span data-ttu-id="a8ac5-124">Una vez que ha creado un cálculo con nombre en la vista del origen de datos, puede utilizar dicho cálculo como propiedad de un atributo.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-124">After you create a named calculation in the data source view, you can use the named calculation as a property of an attribute.</span></span>  
  
#### <a name="to-use-the-named-calculation-for-member-names"></a><span data-ttu-id="a8ac5-125">Para utilizar el cálculo con nombre para los nombres de miembro</span><span class="sxs-lookup"><span data-stu-id="a8ac5-125">To use the named calculation for member names</span></span>  
  
1.  <span data-ttu-id="a8ac5-126">Abra el **Diseñador de dimensiones** para la dimensión Date en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8ac5-126">Open **Dimension Designer** for the Date dimension in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="a8ac5-127">Para ello, haga doble clic en la `Date` dimensión en el nodo **dimensiones** de **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-127">To do this, double-click the `Date` dimension in the **Dimensions** node of **Solution Explorer**.</span></span>  
  
2.  <span data-ttu-id="a8ac5-128">En el panel **Atributos** de la pestaña **Estructura de dimensión** , haga clic en el atributo **Date Key** .</span><span class="sxs-lookup"><span data-stu-id="a8ac5-128">In the **Attributes** pane of the **Dimension Structure** tab, click the **Date Key** attribute.</span></span>  
  
3.  <span data-ttu-id="a8ac5-129">Si la ventana Propiedades no está abierta, ábrala y, después, haga clic en el botón **Ocultar automáticamente** en la barra de título para que permanezca abierta.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-129">If the Properties window is not open, open the Properties window, and then click the **Auto Hide** button on the title bar so that it stays open.</span></span>  
  
4.  <span data-ttu-id="a8ac5-130">Haga clic en el campo de la propiedad **NameColumn** situado en la parte inferior de la ventana y, a continuación, haga clic en el botón de puntos suspensivos (**...**) para abrir el cuadro de diálogo **columna de nombre** .</span><span class="sxs-lookup"><span data-stu-id="a8ac5-130">Click the **NameColumn** property field near the bottom of the window, and then click the ellipsis browse (**...**) button to open the **Name Column** dialog box.</span></span>  
  
5.  <span data-ttu-id="a8ac5-131">Seleccione `SimpleDate` en la parte inferior de la lista **columna de origen** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-131">Select `SimpleDate` at the bottom of the **Source column** list, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="a8ac5-132">En el menú **Archivo**, haga clic en **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-132">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="creating-a-hierarchy"></a><span data-ttu-id="a8ac5-133">Creación de una jerarquía</span><span class="sxs-lookup"><span data-stu-id="a8ac5-133">Creating a Hierarchy</span></span>  
 <span data-ttu-id="a8ac5-134">Puede crear una nueva jerarquía si arrastra un atributo desde el panel **Atributos** hasta el panel **Jerarquías** .</span><span class="sxs-lookup"><span data-stu-id="a8ac5-134">You can create a new hierarchy by dragging an attribute from the **Attributes** pane to the **Hierarchies** pane.</span></span>  
  
#### <a name="to-create-a-hierarchy"></a><span data-ttu-id="a8ac5-135">Para crear una jerarquía</span><span class="sxs-lookup"><span data-stu-id="a8ac5-135">To create a hierarchy</span></span>  
  
1.  <span data-ttu-id="a8ac5-136">En la pestaña **estructura de dimensión** del diseñador de dimensiones para la `Date` dimensión, arrastre el atributo **Calendar Year** desde el panel **atributos** al panel **jerarquías** .</span><span class="sxs-lookup"><span data-stu-id="a8ac5-136">In **Dimension Structure** tab of the Dimension Designer for the `Date` dimension, drag the **Calendar Year** attribute from the **Attributes** pane into the **Hierarchies** pane.</span></span>  
  
2.  <span data-ttu-id="a8ac5-137">Arrastre el atributo **Calendar Semester** desde el panel **Atributos** a la celda **\<new level>** del panel **Jerarquías** , debajo del nivel **Calendar Year** .</span><span class="sxs-lookup"><span data-stu-id="a8ac5-137">Drag the **Calendar Semester** attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **Calendar Year** level.</span></span>  
  
3.  <span data-ttu-id="a8ac5-138">Arrastre el atributo **Calendar Quarter** desde el panel **Atributos** a la celda **\<new level>** del panel **Jerarquías** , debajo del nivel **Calendar Semester** .</span><span class="sxs-lookup"><span data-stu-id="a8ac5-138">Drag the **Calendar Quarter** attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **Calendar Semester** level.</span></span>  
  
4.  <span data-ttu-id="a8ac5-139">Arrastre el atributo **English Month Name** desde el panel **Atributos** a la celda **\<new level>** del panel **Jerarquías** , debajo del nivel **Calendar Quarter** .</span><span class="sxs-lookup"><span data-stu-id="a8ac5-139">Drag the **English Month Name** attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **Calendar Quarter** level.</span></span>  
  
5.  <span data-ttu-id="a8ac5-140">Arrastre el atributo **Date Key** desde el panel **Atributos** a la celda **\<new level>** del panel **Jerarquías** , debajo del nivel **English Month Name** .</span><span class="sxs-lookup"><span data-stu-id="a8ac5-140">Drag the **Date Key** attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **English Month Name** level.</span></span>  
  
6.  <span data-ttu-id="a8ac5-141">En el panel **jerarquías** , haga clic con el botón secundario en la barra de título de la jerarquía **jerarquía** , haga clic en **cambiar nombre**y, a continuación, escriba `Calendar Date` .</span><span class="sxs-lookup"><span data-stu-id="a8ac5-141">In the **Hierarchies** pane, right-click the title bar of the **Hierarchy** hierarchy, click **Rename**, and then type `Calendar Date`.</span></span>  
  
7.  <span data-ttu-id="a8ac5-142">Mediante el menú contextual, en la `Calendar Date` jerarquía, cambie el nombre del nivel **English month Name** a y, `Calendar Month` a continuación, cambie el nombre del nivel **Date Key** a `Date` .</span><span class="sxs-lookup"><span data-stu-id="a8ac5-142">By using the right-click context menu, in the `Calendar Date` hierarchy, rename the **English Month Name** level to `Calendar Month`, and then rename the **Date Key** level to `Date`.</span></span>  
  
8.  <span data-ttu-id="a8ac5-143">Elimine el atributo **Full Date Alternate Key** del panel **Atributos** , ya que no lo va a usar.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-143">Delete the **Full Date Alternate Key** attribute from the **Attributes** pane because you will not be using it.</span></span> <span data-ttu-id="a8ac5-144">Haga clic en **Aceptar** en la ventana de confirmación **Eliminar objetos** .</span><span class="sxs-lookup"><span data-stu-id="a8ac5-144">Click **OK** in the **Delete Objects** confirmation window.</span></span>  
  
9. <span data-ttu-id="a8ac5-145">En el menú **Archivo**, haga clic en **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-145">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="defining-attribute-relationships"></a><span data-ttu-id="a8ac5-146">Definición de relaciones de atributo</span><span class="sxs-lookup"><span data-stu-id="a8ac5-146">Defining Attribute Relationships</span></span>  
 <span data-ttu-id="a8ac5-147">Si los datos subyacentes lo permiten, debería definir relaciones de atributo entre atributos.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-147">If the underlying data supports it, you should define attribute relationships between attributes.</span></span> <span data-ttu-id="a8ac5-148">La definición de relaciones de atributo acelera el procesamiento de las dimensiones, las particiones y las consultas.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-148">Defining attribute relationships speeds up dimension, partition, and query processing.</span></span>  
  
#### <a name="to-define-attribute-relationships"></a><span data-ttu-id="a8ac5-149">Para definir relaciones de atributo</span><span class="sxs-lookup"><span data-stu-id="a8ac5-149">To define attribute relationships</span></span>  
  
1.  <span data-ttu-id="a8ac5-150">En el **Diseñador de dimensiones** para la `Date` dimensión, haga clic en la pestaña **relaciones de atributo** .</span><span class="sxs-lookup"><span data-stu-id="a8ac5-150">In the **Dimension Designer** for the `Date` dimension, click the **Attribute Relationships** tab.</span></span>  
  
2.  <span data-ttu-id="a8ac5-151">En el diagrama, haga clic con el botón derecho en el atributo **English Month Name** y haga clic en **Nueva relación de atributo**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-151">In the diagram, right-click the **English Month Name** attribute, and then click **New Attribute Relationship**.</span></span>  
  
3.  <span data-ttu-id="a8ac5-152">En el cuadro de diálogo **Crear relación de atributo** , el **Atributo de origen** es **English Month Name**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-152">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is **English Month Name**.</span></span> <span data-ttu-id="a8ac5-153">Establezca el **Atributo relacionado** en **Calendar Quarter**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-153">Set the **Related Attribute** to **Calendar Quarter**.</span></span>  
  
4.  <span data-ttu-id="a8ac5-154">En la lista **Tipo de relación** , establezca el tipo de relación en **Rígida**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-154">In the **Relationship type** list, set the relationship type to **Rigid**.</span></span>  
  
     <span data-ttu-id="a8ac5-155">El tipo de relación es **Rígida** porque las relaciones entre los miembros no cambiarán con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-155">The relationship type is **Rigid** because relationships between the members will not change over time.</span></span>  
  
5.  <span data-ttu-id="a8ac5-156">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-156">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="a8ac5-157">En el diagrama, haga clic con el botón derecho en el atributo **Calendar Quarter** y, después, haga clic en **Nueva relación de atributo**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-157">In the diagram, right-click the **Calendar Quarter** attribute, and then click **New Attribute Relationship**.</span></span>  
  
7.  <span data-ttu-id="a8ac5-158">En el cuadro de diálogo **Crear relación de atributo** , el **Atributo de origen** es **Calendar Quarter**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-158">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is **Calendar Quarter**.</span></span> <span data-ttu-id="a8ac5-159">Establezca el **Atributo relacionado** en **Calendar Semester**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-159">Set the **Related Attribute** to **Calendar Semester**.</span></span>  
  
8.  <span data-ttu-id="a8ac5-160">En la lista **Tipo de relación** , establezca el tipo de relación en **Rígida**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-160">In the **Relationship type** list, set the relationship type to **Rigid**.</span></span>  
  
9. <span data-ttu-id="a8ac5-161">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-161">Click **OK**.</span></span>  
  
10. <span data-ttu-id="a8ac5-162">En el diagrama, haga clic con el botón derecho en el atributo **Calendar Semester** y, después, haga clic en **Nueva relación de atributo**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-162">In the diagram, right-click the **Calendar Semester** attribute, and then click **New Attribute Relationship**.</span></span>  
  
11. <span data-ttu-id="a8ac5-163">En el cuadro de diálogo **Crear relación de atributo** , el **Atributo de origen** es **Calendar Semester**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-163">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is **Calendar Semester**.</span></span> <span data-ttu-id="a8ac5-164">Establezca el **Atributo relacionado** en **Calendar Year**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-164">Set the **Related Attribute** to **Calendar Year**.</span></span>  
  
12. <span data-ttu-id="a8ac5-165">En la lista **Tipo de relación** , establezca el tipo de relación en **Rígida**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-165">In the **Relationship type** list, set the relationship type to **Rigid**.</span></span>  
  
13. <span data-ttu-id="a8ac5-166">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-166">Click **OK**.</span></span>  
  
14. <span data-ttu-id="a8ac5-167">En el menú **Archivo**, haga clic en **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-167">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="providing-unique-dimension-member-names"></a><span data-ttu-id="a8ac5-168">Proporcionar nombres de miembros de dimensión únicos</span><span class="sxs-lookup"><span data-stu-id="a8ac5-168">Providing Unique Dimension Member Names</span></span>  
 <span data-ttu-id="a8ac5-169">En esta tarea, creará columnas con nombres descriptivos que usarán los atributos **EnglishMonthName**, **CalendarQuarter**y **CalendarSemester** .</span><span class="sxs-lookup"><span data-stu-id="a8ac5-169">In this task, you will create user-friendly name columns that will be used by the **EnglishMonthName**, **CalendarQuarter**, and **CalendarSemester** attributes.</span></span>  
  
#### <a name="to-provide-unique-dimension-member-names"></a><span data-ttu-id="a8ac5-170">Para proporcionar nombres de miembros de dimensión únicos</span><span class="sxs-lookup"><span data-stu-id="a8ac5-170">To provide unique dimension member names</span></span>  
  
1.  <span data-ttu-id="a8ac5-171">Para cambiar a la vista del origen de datos \*\* [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW 2012\*\* , haga doble clic en ella en la carpeta **vistas del origen de datos** en explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-171">To switch to the **[!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW 2012** data source view, double-click it in the **Data Source Views** folder in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="a8ac5-172">En el panel **tablas** , haga clic con el botón secundario `Date` y, a continuación, haga clic en **nuevo cálculo con nombre**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-172">In the **Tables** pane, right-click `Date`, and then click **New Named Calculation**.</span></span>  
  
3.  <span data-ttu-id="a8ac5-173">En el cuadro de diálogo **crear cálculo con nombre** , escriba `MonthName` en el cuadro **nombre de columna** y, a continuación, escriba o copie y pegue la siguiente instrucción en el cuadro **expresión** :</span><span class="sxs-lookup"><span data-stu-id="a8ac5-173">In the **Create Named Calculation** dialog box, type `MonthName` in the **Column name** box, and then type or copy and paste the following statement in the **Expression** box:</span></span>  
  
    ```  
    EnglishMonthName+' '+ CONVERT(CHAR (4), CalendarYear)  
    ```  
  
     <span data-ttu-id="a8ac5-174">Esta instrucción concatena el mes y el año de cada mes de la tabla una nueva columna.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-174">The statement concatenates the month and year for each month in the table into a new column.</span></span>  
  
4.  <span data-ttu-id="a8ac5-175">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-175">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="a8ac5-176">En el panel **tablas** , haga clic con el botón secundario `Date` y, a continuación, haga clic en **nuevo cálculo con nombre**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-176">In the **Tables** pane, right-click `Date`, and then click **New Named Calculation**.</span></span>  
  
6.  <span data-ttu-id="a8ac5-177">En el cuadro de diálogo **crear cálculo con nombre** , escriba `CalendarQuarterDesc` en el cuadro **nombre de columna** y, a continuación, escriba o copie y pegue el siguiente script SQL en el cuadro **expresión** :</span><span class="sxs-lookup"><span data-stu-id="a8ac5-177">In the **Create Named Calculation** dialog box, type `CalendarQuarterDesc` in the **Column name** box, and then type or copy and paste the following SQL script in the **Expression** box:</span></span>  
  
    ```  
    'Q' + CONVERT(CHAR (1), CalendarQuarter) +' '+ 'CY ' +  
    CONVERT(CHAR (4), CalendarYear)  
    ```  
  
     <span data-ttu-id="a8ac5-178">Este script SQL concatena el trimestre natural y el año de cada trimestre de la tabla en una nueva columna.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-178">This SQL script concatenates the calendar quarter and year for each quarter in the table into a new column.</span></span>  
  
7.  <span data-ttu-id="a8ac5-179">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-179">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="a8ac5-180">En el panel **tablas** , haga clic con el botón secundario `Date` y, a continuación, haga clic en **nuevo cálculo con nombre**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-180">In the **Tables** pane, right-click `Date`, and then click **New Named Calculation**.</span></span>  
  
9. <span data-ttu-id="a8ac5-181">En el cuadro de diálogo **crear cálculo con nombre** , escriba `CalendarSemesterDesc` en el cuadro **nombre de columna** y, a continuación, escriba o copie y pegue el siguiente script SQL en el cuadro **expresión** :</span><span class="sxs-lookup"><span data-stu-id="a8ac5-181">In the **Create Named Calculation** dialog box, type `CalendarSemesterDesc` in the **Column name** box, and then type or copy and paste the following SQL script in the **Expression** box:</span></span>  
  
    ```  
    CASE  
    WHEN CalendarSemester = 1 THEN 'H1' + ' ' + 'CY' + ' '   
           + CONVERT(CHAR(4), CalendarYear)  
    ELSE  
    'H2' + ' ' + 'CY' + ' ' + CONVERT(CHAR(4), CalendarYear)  
    END  
    ```  
  
     <span data-ttu-id="a8ac5-182">Este script SQL concatena el semestre natural y el año de cada semestre de la tabla en una nueva columna.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-182">This SQL script concatenates the calendar semester and year for each semester in the table into a new column.</span></span>  
  
10. <span data-ttu-id="a8ac5-183">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-183">Click **OK.**</span></span>  
  
11. <span data-ttu-id="a8ac5-184">En el menú **Archivo**, haga clic en **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-184">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="defining-composite-keycolumns-and-setting-the-name-column"></a><span data-ttu-id="a8ac5-185">Definir KeyColumns compuestas y establecer la columna de nombre</span><span class="sxs-lookup"><span data-stu-id="a8ac5-185">Defining Composite KeyColumns and Setting the Name Column</span></span>  
 <span data-ttu-id="a8ac5-186">La propiedad **KeyColumns** contiene la columna o columnas que representan la clave para el atributo.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-186">The **KeyColumns** property contains the column or columns that represent the key for the attribute.</span></span> <span data-ttu-id="a8ac5-187">En esta tarea, definirá propiedades **KeyColumns**compuestas.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-187">In this task, you will define composite **KeyColumns**.</span></span>  
  
#### <a name="to-define-composite-keycolumns-for-the-english-month-name-attribute"></a><span data-ttu-id="a8ac5-188">Para definir KeyColumns compuestas para el atributo Spanish Month Name</span><span class="sxs-lookup"><span data-stu-id="a8ac5-188">To define composite KeyColumns for the English Month Name attribute</span></span>  
  
1.  <span data-ttu-id="a8ac5-189">Abra la pestaña **Estructura de dimensión** para la dimensión Date.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-189">Open the **Dimension Structure** tab for the Date dimension.</span></span>  
  
2.  <span data-ttu-id="a8ac5-190">En el panel **Atributos** , haga clic en el atributo **English Month Name** .</span><span class="sxs-lookup"><span data-stu-id="a8ac5-190">In the **Attributes** pane, click the **English Month Name** attribute.</span></span>  
  
3.  <span data-ttu-id="a8ac5-191">En la ventana **Propiedades** , haga clic en el campo **KeyColumns** y, después, haga clic en el botón Examinar (**...**).</span><span class="sxs-lookup"><span data-stu-id="a8ac5-191">In the **Properties** window, click the **KeyColumns** field, and then click the browse (**...**) button.</span></span>  
  
4.  <span data-ttu-id="a8ac5-192">En el cuadro de diálogo **columnas de clave** , en la lista **columnas disponibles** , seleccione la columna **CalendarYear**y, a continuación, haga clic en el **>** botón.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-192">In the **Key Columns** dialog box, in the **Available Columns** list, select the column **CalendarYear**, and then click the **>** button.</span></span>  
  
5.  <span data-ttu-id="a8ac5-193">Las columnas **EnglishMonthName** y **CalendarYear** se muestran ahora en la lista **Columnas de clave** .</span><span class="sxs-lookup"><span data-stu-id="a8ac5-193">The **EnglishMonthName** and **CalendarYear** columns are now displayed in the **Key Columns** list.</span></span>  
  
6.  <span data-ttu-id="a8ac5-194">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-194">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="a8ac5-195">Para establecer la propiedad **NameColumn** del atributo **EnglishMonthName** , haga clic en el campo **NameColumn** en la ventana Propiedades y, después, haga clic en el botón Examinar (**...**).</span><span class="sxs-lookup"><span data-stu-id="a8ac5-195">To set the **NameColumn** property of the **EnglishMonthName** attribute, click the **NameColumn** field in the Properties window, and then click the browse (**...**) button.</span></span>  
  
8.  <span data-ttu-id="a8ac5-196">En el cuadro de diálogo **columna de nombre** , en la lista **columna de origen** , seleccione `MonthName` y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-196">In the **Name Column** dialog box, in the **Source Column** list, select `MonthName`, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="a8ac5-197">En el menú **Archivo**, haga clic en **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-197">On the **File** menu, click **Save All**.</span></span>  
  
#### <a name="to-define-composite-keycolumns-for-the-calendar-quarter-attribute"></a><span data-ttu-id="a8ac5-198">Para definir KeyColumns compuestas para el atributo Calendar Quarter</span><span class="sxs-lookup"><span data-stu-id="a8ac5-198">To define composite KeyColumns for the Calendar Quarter attribute</span></span>  
  
1.  <span data-ttu-id="a8ac5-199">En el panel **Atributos** , haga clic en el atributo **Calendar Quarter** .</span><span class="sxs-lookup"><span data-stu-id="a8ac5-199">In the **Attributes** pane, click the **Calendar Quarter** attribute.</span></span>  
  
2.  <span data-ttu-id="a8ac5-200">En la ventana **Propiedades** , haga clic en el campo **KeyColumns** y, después, haga clic en el botón Examinar (**...**).</span><span class="sxs-lookup"><span data-stu-id="a8ac5-200">In the **Properties** window, click the **KeyColumns** field, and then click the browse (**...**) button.</span></span>  
  
3.  <span data-ttu-id="a8ac5-201">En el cuadro de diálogo **columnas de clave** , en la lista **columnas disponibles** , seleccione la columna **CalendarYear**y, a continuación, haga clic en el **>** botón.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-201">In the **Key Columns** dialog box, in the **Available Columns** list, select the column **CalendarYear**, and then click the **>** button.</span></span>  
  
     <span data-ttu-id="a8ac5-202">Las columnas **CalendarQuarter** y **CalendarYear** se muestran ahora en la lista **Columnas de clave** .</span><span class="sxs-lookup"><span data-stu-id="a8ac5-202">The **CalendarQuarter** and **CalendarYear** columns are now displayed in the **Key Columns** list.</span></span>  
  
4.  <span data-ttu-id="a8ac5-203">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-203">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="a8ac5-204">Para establecer la propiedad **NameColumn** del atributo **Calendar Quarter** , haga clic en el campo **NameColumn** en la ventana Propiedades y, después, haga clic en el botón Examinar (**...**).</span><span class="sxs-lookup"><span data-stu-id="a8ac5-204">To set the **NameColumn** property of the **Calendar Quarter** attribute, click the **NameColumn** field in the Properties window, and then click the browse (**...**) button.</span></span>  
  
6.  <span data-ttu-id="a8ac5-205">En el cuadro de diálogo **columna de nombre** , en la lista **columna de origen** , seleccione `CalendarQuarterDesc` y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-205">In the **Name Column** dialog box, in the **Source Column** list, select `CalendarQuarterDesc`, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="a8ac5-206">En el menú **Archivo**, haga clic en **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-206">On the **File** menu, click **Save All**.</span></span>  
  
#### <a name="to-define-composite-keycolumns-for-the-calendar-semester-attribute"></a><span data-ttu-id="a8ac5-207">Para definir KeyColumns compuestas para el atributo Calendar Semester</span><span class="sxs-lookup"><span data-stu-id="a8ac5-207">To define composite KeyColumns for the Calendar Semester attribute</span></span>  
  
1.  <span data-ttu-id="a8ac5-208">En el panel **Atributos** , haga clic en el atributo **Calendar Semester** .</span><span class="sxs-lookup"><span data-stu-id="a8ac5-208">In the **Attributes** pane, click the **Calendar Semester** attribute.</span></span>  
  
2.  <span data-ttu-id="a8ac5-209">En la ventana **Propiedades** , haga clic en el campo **KeyColumns** y, después, haga clic en el botón Examinar (**...**).</span><span class="sxs-lookup"><span data-stu-id="a8ac5-209">In the **Properties** window, click the **KeyColumns** field, and then click the browse (**...**) button.</span></span>  
  
3.  <span data-ttu-id="a8ac5-210">En el cuadro de diálogo **Columnas de clave** , en la lista **Columnas disponibles** , seleccione la columna **CalendarYear**y, después, haga clic en el botón **>** .</span><span class="sxs-lookup"><span data-stu-id="a8ac5-210">In the **Key Columns** dialog box, in the **Available Columns** list, select the column, **CalendarYear**, and then click the **>** button.</span></span>  
  
     <span data-ttu-id="a8ac5-211">Las columnas **CalendarSemester** y **CalendarYear** se muestran ahora en la lista **Columnas de clave** .</span><span class="sxs-lookup"><span data-stu-id="a8ac5-211">The **CalendarSemester** and **CalendarYear** columns are now displayed in the **Key Columns** list.</span></span>  
  
4.  <span data-ttu-id="a8ac5-212">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-212">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="a8ac5-213">Para establecer la propiedad **NameColumn** del atributo **Calendar Semester** , haga clic en el campo **NameColumn** en la ventana Propiedades y, después, haga clic en el botón Examinar (**...**).</span><span class="sxs-lookup"><span data-stu-id="a8ac5-213">To set the **NameColumn** property of the **Calendar Semester** attribute, click the **NameColumn** field in the property window, and then click the browse (**...**) button.</span></span>  
  
6.  <span data-ttu-id="a8ac5-214">En el cuadro de diálogo **columna de nombre** , en la lista **columna de origen** , seleccione `CalendarSemesterDesc` y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-214">In the **Name Column** dialog box, in the **Source Column** list, select `CalendarSemesterDesc`, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="a8ac5-215">En el menú **Archivo**, haga clic en **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-215">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="deploying-and-viewing-the-changes"></a><span data-ttu-id="a8ac5-216">Implementar y ver los cambios</span><span class="sxs-lookup"><span data-stu-id="a8ac5-216">Deploying and Viewing the Changes</span></span>  
 <span data-ttu-id="a8ac5-217">Una vez que ha cambiado los atributos y las jerarquías, debe implementar los cambios y procesar de nuevo los objetos relacionados antes de ver los cambios.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-217">After you have changed attributes and hierarchies, you must deploy the changes and reprocess the related objects before you can view the changes.</span></span>  
  
#### <a name="to-deploy-and-view-the-changes"></a><span data-ttu-id="a8ac5-218">Para implementar y ver los cambios</span><span class="sxs-lookup"><span data-stu-id="a8ac5-218">To deploy and view the changes</span></span>  
  
1.  <span data-ttu-id="a8ac5-219">En el menú **Generar** de [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], haga clic en **Implementar Tutorial de Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-219">On the **Build** menu of [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="a8ac5-220">Tras recibir el mensaje la **implementación finalizó correctamente** , haga clic en la pestaña **Explorador** del **Diseñador de dimensiones** para la `Date` dimensión y, a continuación, haga clic en el botón volver a conectar en la barra de herramientas del diseñador.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-220">After you have received the **Deployment Completed Successfully** message, click the **Browser** tab of **Dimension Designer** for the `Date` dimension, and then click the Reconnect button on the toolbar of the designer.</span></span>  
  
3.  <span data-ttu-id="a8ac5-221">Seleccione **Calendar Quarter** en la lista **Jerarquía** .</span><span class="sxs-lookup"><span data-stu-id="a8ac5-221">Select **Calendar Quarter** from the **Hierarchy** list.</span></span> <span data-ttu-id="a8ac5-222">Revise los miembros de la jerarquía de atributo **Calendar Quarter** .</span><span class="sxs-lookup"><span data-stu-id="a8ac5-222">Review the members in the **Calendar Quarter** attribute hierarchy.</span></span>  
  
     <span data-ttu-id="a8ac5-223">Observe que los nombres de los miembros de la jerarquía del atributo **Calendar Quarter** son más descriptivos y fáciles de usar porque creó un cálculo con nombre que se usa como nombre.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-223">Notice that the names of the members of the **Calendar Quarter** attribute hierarchy are clearer and easier to use because you created a named calculation to use as the name.</span></span> <span data-ttu-id="a8ac5-224">Ahora hay miembros en la jerarquía del atributo **Calendar Quarter** para cada trimestre de cada año.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-224">Members now exist in the **Calendar Quarter** attribute hierarchy for each quarter in each year.</span></span> <span data-ttu-id="a8ac5-225">Los miembros no están ordenados cronológicamente.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-225">The members are not sorted in chronological order.</span></span> <span data-ttu-id="a8ac5-226">En lugar de ello, están ordenados por trimestre y luego por año.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-226">Instead they are sorted by quarter and then by year.</span></span> <span data-ttu-id="a8ac5-227">En la siguiente tarea de este tema, modificará este comportamiento para ordenar los miembros de la jerarquía de este atributo por año y luego por trimestre.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-227">In the next task in this topic, you will modify this behavior to sort the members of this attribute hierarchy by year and then by quarter.</span></span>  
  
4.  <span data-ttu-id="a8ac5-228">Revise los miembros de las jerarquías de los atributos **English Month Name** y **Calendar Semester** .</span><span class="sxs-lookup"><span data-stu-id="a8ac5-228">Review the members of the **English Month Name** and **Calendar Semester** attribute hierarchies.</span></span>  
  
     <span data-ttu-id="a8ac5-229">Observe que los miembros de estas jerarquías tampoco están ordenados cronológicamente.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-229">Notice that the members of these hierarchies are also not sorted in chronological order.</span></span> <span data-ttu-id="a8ac5-230">En lugar de ello, están ordenados por mes o semestre, respectivamente, y luego por año.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-230">Instead, they are sorted by month or semester, respectively, and then by year.</span></span> <span data-ttu-id="a8ac5-231">En la tarea siguiente de este tema, modificará este comportamiento para cambiar el criterio de ordenación.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-231">In the next task in this topic, you will modify this behavior to change this sort order.</span></span>  
  
## <a name="changing-the-sort-order-by-modifying-composite-key-member-order"></a><span data-ttu-id="a8ac5-232">Cambiar el criterio de ordenación modificando el orden de los miembros de clave compuesta</span><span class="sxs-lookup"><span data-stu-id="a8ac5-232">Changing the Sort Order by Modifying Composite Key Member Order</span></span>  
 <span data-ttu-id="a8ac5-233">En esta tarea, modificará el criterio de ordenación cambiando el orden de las claves que forman la clave compuesta.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-233">In this task, you will change the sort order by changing the order of the keys that make up the composite key.</span></span>  
  
#### <a name="to-modify-the-composite-key-member-order"></a><span data-ttu-id="a8ac5-234">Para modificar el orden de los miembros de clave compuesta</span><span class="sxs-lookup"><span data-stu-id="a8ac5-234">To modify the composite key member order</span></span>  
  
1.  <span data-ttu-id="a8ac5-235">Abra la pestaña **estructura de dimensión** del diseñador de dimensiones para la `Date` dimensión y, a continuación, seleccione el **semestre natural** en el panel **atributos** .</span><span class="sxs-lookup"><span data-stu-id="a8ac5-235">Open the **Dimension Structure** tab of Dimension Designer for the `Date` dimension, and then select **Calendar Semester** in the **Attributes** pane.</span></span>  
  
2.  <span data-ttu-id="a8ac5-236">En la ventana Propiedades, revise el valor de la propiedad **OrderBy** .</span><span class="sxs-lookup"><span data-stu-id="a8ac5-236">In the Properties window, review the value for the **OrderBy** property.</span></span> <span data-ttu-id="a8ac5-237">Dicho valor se establece en **Key**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-237">It is set to **Key**.</span></span>  
  
     <span data-ttu-id="a8ac5-238">Los miembros de la jerarquía del atributo **Calendar Semester** están ordenados por su valor de clave.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-238">The members of the **Calendar Semester** attribute hierarchy are sorted by their key value.</span></span> <span data-ttu-id="a8ac5-239">Con una clave compuesta, el orden de las claves de los miembros se basa en el primer valor de la primera clave del miembro y luego en el valor de la segunda clave del miembro.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-239">With a composite key, the ordering of the member keys is based first on the value of the first member key, and then on the value of the second member key.</span></span> <span data-ttu-id="a8ac5-240">Dicho de otro modo, los miembros de la jerarquía del atributo **Calendar Semester** están ordenados primero por semestre y luego por año.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-240">In other words, the members of the **Calendar Semester** attribute hierarchy are sorted first by semester and then by year.</span></span>  
  
3.  <span data-ttu-id="a8ac5-241">En la ventana Propiedades, haga clic en el botón Examinar (**...**) para cambiar el valor de la propiedad **KeyColumns** .</span><span class="sxs-lookup"><span data-stu-id="a8ac5-241">In the Properties window, click the ellipsis browse button (**...**) to change the **KeyColumns** property value.</span></span>  
  
4.  <span data-ttu-id="a8ac5-242">En la lista **Columnas de clave** del cuadro de diálogo **Columnas de clave** , compruebe que **CalendarSemester** está seleccionado, y, después, haga clic en la flecha abajo para invertir el orden de los miembros de esta clave compuesta.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-242">In the **Key Columns** list of the **Key Columns** dialog box, verify that **CalendarSemester** is selected, and then click the down arrow to reverse the order of the members of this composite key.</span></span> <span data-ttu-id="a8ac5-243">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-243">Click **OK**.</span></span>  
  
     <span data-ttu-id="a8ac5-244">Los miembros de la jerarquía de atributo ahora aparecen ordenados primero por año y luego por semestre.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-244">The members of the attribute hierarchy are now sorted first by year and then by semester.</span></span>  
  
5.  <span data-ttu-id="a8ac5-245">Seleccione **Calendar Quarter** en el panel **Atributos** y, después, haga clic en el botón Examinar (**...**) de la propiedad **KeyColumns** de la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-245">Select **Calendar Quarter** in the **Attributes** pane, and then click the ellipsis browse button (**...**) for the **KeyColumns** property in the Properties window.</span></span>  
  
6.  <span data-ttu-id="a8ac5-246">En la lista **Columnas de clave** del cuadro de diálogo **Columnas de clave** , compruebe que **CalendarQuarter** está seleccionado, y, después, haga clic en la flecha abajo para invertir el orden de los miembros de esta clave compuesta.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-246">In the **Key Columns** list of the **Key Columns** dialog box, verify that **CalendarQuarter** is selected, and then click the down arrow to reverse the order of the members of this composite key.</span></span> <span data-ttu-id="a8ac5-247">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-247">Click **OK**.</span></span>  
  
     <span data-ttu-id="a8ac5-248">Los miembros de la jerarquía de atributo ahora aparecen ordenados primero por año y luego por trimestre.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-248">The members of the attribute hierarchy are now sorted first by year and then by quarter.</span></span>  
  
7.  <span data-ttu-id="a8ac5-249">Seleccione **English Month Name** en el panel **Atributos** y, después, haga clic en el botón Examinar (**...**) de la propiedad **KeyColumns** de la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-249">Select **English Month Name** in the **Attributes** pane, and then click the ellipsis button (**...**) for the **KeyColumns** property in the Properties window.</span></span>  
  
8.  <span data-ttu-id="a8ac5-250">En la lista **Columnas de clave** del cuadro de diálogo **Columnas de clave** , compruebe que **EnglishMonthName** está seleccionado, y, después, haga clic en la flecha abajo para invertir el orden de los miembros de esta clave compuesta.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-250">In the **Key Columns** list of the **Key Columns** dialog box, verify that **EnglishMonthName** is selected, and then click the down arrow to reverse the order of the members of this composite key.</span></span> <span data-ttu-id="a8ac5-251">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-251">Click **OK**.</span></span>  
  
     <span data-ttu-id="a8ac5-252">Los miembros de la jerarquía de atributo ahora aparecen ordenados primero por año y luego por mes.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-252">The members of the attribute hierarchy are now sorted first by year and then by month.</span></span>  
  
9. <span data-ttu-id="a8ac5-253">En el menú **Generar** de [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], haga clic en **Implementar Tutorial de Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-253">On the **Build** menu of [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click **Deploy Analysis Services Tutorial**.</span></span> <span data-ttu-id="a8ac5-254">Cuando la implementación se haya completado correctamente, haga clic en la pestaña **Explorador** del diseñador de dimensiones para la `Date` dimensión.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-254">When deployment has successfully completed, click the **Browser** tab in Dimension Designer for the `Date` dimension.</span></span>  
  
10. <span data-ttu-id="a8ac5-255">En la barra de herramientas de la pestaña **Explorador** , haga clic en el botón Volver a conectar.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-255">On the toolbar of the **Browser** tab, click the Reconnect button.</span></span>  
  
11. <span data-ttu-id="a8ac5-256">Revise los miembros de las jerarquías de los atributos **Calendar Quarter** y **Calendar Semester** .</span><span class="sxs-lookup"><span data-stu-id="a8ac5-256">Review the members of the **Calendar Quarter** and **Calendar Semester** attribute hierarchies.</span></span>  
  
     <span data-ttu-id="a8ac5-257">Observe que los miembros de estas jerarquías ahora están clasificados por orden cronológico, por año y luego por trimestre o semestre, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-257">Notice that the members of these hierarchies are now sorted in chronological order, by year and then by quarter or semester, respectively.</span></span>  
  
12. <span data-ttu-id="a8ac5-258">Revise los miembros de la jerarquía del atributo **English Month Name** .</span><span class="sxs-lookup"><span data-stu-id="a8ac5-258">Review the members of the **English Month Name** attribute hierarchy.</span></span>  
  
     <span data-ttu-id="a8ac5-259">Observe que los miembros de la jerarquía de atributo ahora aparecen ordenados primero por año y luego alfabéticamente por mes.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-259">Notice that the members of the hierarchy are now sorted first by year and then alphabetically by month.</span></span> <span data-ttu-id="a8ac5-260">Esto se debe a que el tipo de datos de la columna EnglishCalendarMonth de la vista del origen de datos es una columna de cadena, basada en el tipo de datos nvarchar de la base de datos relacional subyacente.</span><span class="sxs-lookup"><span data-stu-id="a8ac5-260">This is because the data type for the EnglishCalendarMonth column in the data source view is a string column, based on the nvarchar data type in the underlying relational database.</span></span> <span data-ttu-id="a8ac5-261">Para obtener información sobre cómo habilitar la ordenación cronológica de los meses dentro de cada año, consulte [Ordenar los miembros de atributo en función de un atributo derecho](lesson-4-5-sorting-attribute-members-based-on-a-secondary-attribute.md).</span><span class="sxs-lookup"><span data-stu-id="a8ac5-261">For information about how to enable the months to be sorted chronologically within each year, see [Sorting Attribute Members Based on a Secondary Attribute](lesson-4-5-sorting-attribute-members-based-on-a-secondary-attribute.md).</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="a8ac5-262">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="a8ac5-262">Next Task in Lesson</span></span>  
 [<span data-ttu-id="a8ac5-263">Examinar el cubo implementado</span><span class="sxs-lookup"><span data-stu-id="a8ac5-263">Browsing the Deployed Cube</span></span>](lesson-3-5-browsing-the-deployed-cube.md)  
  
## <a name="see-also"></a><span data-ttu-id="a8ac5-264">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a8ac5-264">See Also</span></span>  
 [<span data-ttu-id="a8ac5-265">Dimensiones en modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="a8ac5-265">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
