---
title: Modificar la dimensión Product | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 8e3ffecd-7f40-41a8-8735-bc9858a310cb
author: minewiskan
ms.author: owend
ms.openlocfilehash: 04c0a778a73371dada92c9ff207a17366a2fbc7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674429"
---
# <a name="modifying-the-product-dimension"></a><span data-ttu-id="53c3f-102">Modificar la dimensión Product</span><span class="sxs-lookup"><span data-stu-id="53c3f-102">Modifying the Product Dimension</span></span>
  <span data-ttu-id="53c3f-103">En las tareas de este tema, usará un cálculo con nombre para proporcionar nombres más descriptivos a las líneas de producto, definir una jerarquía en la dimensión Product y especificar el nombre de miembro (Todos) para dicha jerarquía.</span><span class="sxs-lookup"><span data-stu-id="53c3f-103">In the tasks in this topic, you use a named calculation to provide more descriptive names for the product lines, define a hierarchy in the Product dimension, and specify the (All) member name for the hierarchy.</span></span> <span data-ttu-id="53c3f-104">También agrupará los atributos en carpetas para mostrar.</span><span class="sxs-lookup"><span data-stu-id="53c3f-104">You also group attributes into display folders.</span></span>  
  
## <a name="adding-a-named-calculation"></a><span data-ttu-id="53c3f-105">Agregar un cálculo con nombre</span><span class="sxs-lookup"><span data-stu-id="53c3f-105">Adding a Named Calculation</span></span>  
 <span data-ttu-id="53c3f-106">Puede agregar un cálculo con nombre a una tabla de una vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="53c3f-106">You can add a named calculation to a table in a data source view.</span></span> <span data-ttu-id="53c3f-107">En la tarea siguiente, creará un cálculo con nombre que mostrará el nombre completo de la línea de producto.</span><span class="sxs-lookup"><span data-stu-id="53c3f-107">In the following task, you create a named calculation that displays the full product line name.</span></span>  
  
#### <a name="to-add-a-named-calculation"></a><span data-ttu-id="53c3f-108">Para agregar un cálculo con nombre</span><span class="sxs-lookup"><span data-stu-id="53c3f-108">To add a named calculation</span></span>  
  
1.  <span data-ttu-id="53c3f-109">Para abrir la vista del origen de datos **Adventure Works DW 2012** , haga doble clic en **Adventure Works DW 2012** en la carpeta **Vistas del origen de datos** del Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="53c3f-109">To open the **Adventure Works DW 2012** data source view, double-click **Adventure Works DW 2012** in the **Data Source Views** folder in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="53c3f-110">Al final de panel de diagrama, haga clic con el botón derecho en el encabezado de tabla **Product** y, después, haga clic en **Nuevo cálculo con nombre**.</span><span class="sxs-lookup"><span data-stu-id="53c3f-110">In the bottom of the diagram pane, right-click the **Product** table header, and then click **New Named Calculation**.</span></span>  
  
3.  <span data-ttu-id="53c3f-111">En el cuadro de diálogo **crear cálculo con nombre** , escriba `ProductLineName` en el cuadro **nombre de columna** .</span><span class="sxs-lookup"><span data-stu-id="53c3f-111">In the **Create Named Calculation** dialog box, type `ProductLineName` in the **Column name** box.</span></span>  
  
4.  <span data-ttu-id="53c3f-112">En el cuadro **Expresión** , escriba o copie y pegue la siguiente instrucción **CASE** :</span><span class="sxs-lookup"><span data-stu-id="53c3f-112">In the **Expression** box, type or copy and paste the following **CASE** statement:</span></span>  
  
    ```  
    CASE ProductLine  
       WHEN 'M' THEN 'Mountain'  
       WHEN 'R' THEN 'Road'  
       WHEN 'S' THEN 'Accessory'  
       WHEN 'T' THEN 'Touring'  
       ELSE 'Components'  
    END  
    ```  
  
     <span data-ttu-id="53c3f-113">Esta instrucción **CASE** crea nombres descriptivos para cada línea de producto del cubo.</span><span class="sxs-lookup"><span data-stu-id="53c3f-113">This **CASE** statement creates user-friendly names for each product line in the cube.</span></span>  
  
5.  <span data-ttu-id="53c3f-114">Haga clic en **Aceptar** para crear el `ProductLineName` cálculo con nombre.</span><span class="sxs-lookup"><span data-stu-id="53c3f-114">Click **OK** to create the `ProductLineName` named calculation.</span></span> <span data-ttu-id="53c3f-115">Es posible que tenga que esperar.</span><span class="sxs-lookup"><span data-stu-id="53c3f-115">You might need to wait.</span></span>  
  
6.  <span data-ttu-id="53c3f-116">En el menú **Archivo**, haga clic en **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="53c3f-116">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="modifying-the-namecolumn-property-of-an-attribute"></a><span data-ttu-id="53c3f-117">Modificar la propiedad NameColumn de un atributo</span><span class="sxs-lookup"><span data-stu-id="53c3f-117">Modifying the NameColumn Property of an Attribute</span></span>  
  
#### <a name="to-modify-the-namecolumn-property-value-of-an-attribute"></a><span data-ttu-id="53c3f-118">Para modificar el valor de la propiedad NameColumn de un atributo</span><span class="sxs-lookup"><span data-stu-id="53c3f-118">To modify the NameColumn property value of an attribute</span></span>  
  
1.  <span data-ttu-id="53c3f-119">Cambie a la dimensión Product en el Diseñador de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="53c3f-119">Switch to Dimension Designer for the Product dimension.</span></span> <span data-ttu-id="53c3f-120">Para ello, haga doble clic en la dimensión **Product** del nodo **Dimensiones** del Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="53c3f-120">To do this, double-click the **Product** dimension in the **Dimensions** node of Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="53c3f-121">En el panel **Atributos** de la pestaña **Estructura de dimensión** , seleccione **Product Line**.</span><span class="sxs-lookup"><span data-stu-id="53c3f-121">In the **Attributes** pane of the **Dimension Structure** tab, select **Product Line**.</span></span>  
  
3.  <span data-ttu-id="53c3f-122">En el ventana Propiedades en el lado derecho de la pantalla, haga clic en el campo de la propiedad **NameColumn** situado en la parte inferior de la ventana y, a continuación, haga clic en el botón Examinar (**...**) para abrir el cuadro de diálogo **columna de nombre** .</span><span class="sxs-lookup"><span data-stu-id="53c3f-122">In the Properties window on the right side of the screen, click the **NameColumn** property field at the bottom of the window, and then click the browse (**...**) button to open the **Name Column** dialog box.</span></span> <span data-ttu-id="53c3f-123">(Es posible que tenga que hacer clic en la pestaña **Propiedades** a la derecha de la pantalla para abrir la ventana Propiedades).</span><span class="sxs-lookup"><span data-stu-id="53c3f-123">(You might need to click the **Properties** tab on the right side of the screen to open the Properties window.</span></span>  
  
4.  <span data-ttu-id="53c3f-124">Seleccione `ProductLineName` en la parte inferior de la lista **columna de origen** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="53c3f-124">Select `ProductLineName` at the bottom of the **Source column** list, and then click **OK**.</span></span>  
  
     <span data-ttu-id="53c3f-125">El campo NameColumn contiene ahora el texto **Product.ProductLineName (WChar)**.</span><span class="sxs-lookup"><span data-stu-id="53c3f-125">The NameColumn field now contains the text, **Product.ProductLineName (WChar)**.</span></span> <span data-ttu-id="53c3f-126">Los miembros de la jerarquía de atributo **Product Line** mostrarán el nombre completo de la línea de producto en lugar de un nombre abreviado de la misma.</span><span class="sxs-lookup"><span data-stu-id="53c3f-126">The members of the **Product Line** attribute hierarchy now display the full name of the product line instead of an abbreviated product line name.</span></span>  
  
5.  <span data-ttu-id="53c3f-127">En el panel **Atributos** de la pestaña **Estructura de dimensión** , seleccione **Product Key**.</span><span class="sxs-lookup"><span data-stu-id="53c3f-127">In the **Attributes** pane of the **Dimension Structure** tab, select **Product Key**.</span></span>  
  
6.  <span data-ttu-id="53c3f-128">En el ventana Propiedades, haga clic en el campo de la propiedad **NameColumn** y, a continuación, haga clic en el botón de puntos suspensivos (**...**) para abrir el cuadro de diálogo **columna de nombre** .</span><span class="sxs-lookup"><span data-stu-id="53c3f-128">In the Properties window, click the **NameColumn** property field, and then click the ellipsis browse (**...**) button to open the **Name Column** dialog box.</span></span>  
  
7.  <span data-ttu-id="53c3f-129">Seleccione **EnglishProductName** en la lista **Columna de origen** y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="53c3f-129">Select **EnglishProductName** in the **Source column** list, and then click **OK**.</span></span>  
  
     <span data-ttu-id="53c3f-130">El campo NameColumn contiene ahora el texto **Product.EnglishProductName (WChar)**.</span><span class="sxs-lookup"><span data-stu-id="53c3f-130">The NameColumn field now contains the text, **Product.EnglishProductName (WChar)**.</span></span>  
  
8.  <span data-ttu-id="53c3f-131">En el ventana Propiedades, desplácese hacia arriba, haga clic en el campo de la propiedad **nombre** y, a continuación, escriba `Product Name` .</span><span class="sxs-lookup"><span data-stu-id="53c3f-131">In the Properties window, scroll up, click the **Name** property field, and then type `Product Name`.</span></span>  
  
## <a name="creating-a-hierarchy"></a><span data-ttu-id="53c3f-132">Creación de una jerarquía</span><span class="sxs-lookup"><span data-stu-id="53c3f-132">Creating a Hierarchy</span></span>  
  
#### <a name="to-create-a-hierarchy"></a><span data-ttu-id="53c3f-133">Para crear una jerarquía</span><span class="sxs-lookup"><span data-stu-id="53c3f-133">To create a hierarchy</span></span>  
  
1.  <span data-ttu-id="53c3f-134">Arrastre el atributo **Product Line** del panel **Atributos** al panel **Jerarquías** .</span><span class="sxs-lookup"><span data-stu-id="53c3f-134">Drag the **Product Line** attribute from the **Attributes** pane into the **Hierarchies** pane.</span></span>  
  
2.  <span data-ttu-id="53c3f-135">Arrastre el atributo **Model Name** desde el panel **Atributos** a la celda **\<new level>** del panel **Jerarquías** , debajo del nivel **Product Line** .</span><span class="sxs-lookup"><span data-stu-id="53c3f-135">Drag the **Model Name** attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **Product Line** level.</span></span>  
  
3.  <span data-ttu-id="53c3f-136">Arrastre el `Product Name` atributo desde el panel **atributos** a la **\<new level>** celda del panel **jerarquías** , debajo del nivel de **nombre del modelo** .</span><span class="sxs-lookup"><span data-stu-id="53c3f-136">Drag the `Product Name` attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **Model Name** level.</span></span> <span data-ttu-id="53c3f-137">(Cambió el nombre Product Key a Nombre del producto en la sección anterior).</span><span class="sxs-lookup"><span data-stu-id="53c3f-137">(You renamed Product Key to Product Name in the previous section.)</span></span>  
  
4.  <span data-ttu-id="53c3f-138">En el panel **jerarquías** de la pestaña **estructura de dimensión** , haga clic con el botón secundario en la barra de título de la jerarquía jerarquía, haga clic en **cambiar nombre**y, a continuación, escriba **Hierarchy** `Product Model Lines` .</span><span class="sxs-lookup"><span data-stu-id="53c3f-138">In the **Hierarchies** pane of the **Dimension Structure** tab, right-click the title bar of the **Hierarchy** hierarchy, click **Rename**, and then type `Product Model Lines`.</span></span>  
  
     <span data-ttu-id="53c3f-139">El nombre de la jerarquía es ahora `Product Model Lines` .</span><span class="sxs-lookup"><span data-stu-id="53c3f-139">The name of the hierarchy is now `Product Model Lines`.</span></span>  
  
5.  <span data-ttu-id="53c3f-140">En el menú **Archivo**, haga clic en **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="53c3f-140">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="specifying-folder-names-and-all-member-names"></a><span data-ttu-id="53c3f-141">Especificar los nombres de carpeta y el nombre de todos los miembros</span><span class="sxs-lookup"><span data-stu-id="53c3f-141">Specifying Folder Names and All Member Names</span></span>  
  
#### <a name="to-specify-the-folder-and-member-names"></a><span data-ttu-id="53c3f-142">Para especificar los nombres de carpeta y de los miembros</span><span class="sxs-lookup"><span data-stu-id="53c3f-142">To specify the folder and member names</span></span>  
  
1.  <span data-ttu-id="53c3f-143">En el panel **Atributos** , mantenga pulsada la tecla CTRL mientras hace clic en cada uno de los atributos siguientes para seleccionarlos:</span><span class="sxs-lookup"><span data-stu-id="53c3f-143">In the **Attributes** pane, select the following attributes by holding down the CTRL key while clicking each of them:</span></span>  
  
    -   <span data-ttu-id="53c3f-144">**Clase**</span><span class="sxs-lookup"><span data-stu-id="53c3f-144">**Class**</span></span>  
  
    -   <span data-ttu-id="53c3f-145">**Color**</span><span class="sxs-lookup"><span data-stu-id="53c3f-145">**Color**</span></span>  
  
    -   <span data-ttu-id="53c3f-146">**Días de fabricación**</span><span class="sxs-lookup"><span data-stu-id="53c3f-146">**Days To Manufacture**</span></span>  
  
    -   <span data-ttu-id="53c3f-147">**Reorder Point**</span><span class="sxs-lookup"><span data-stu-id="53c3f-147">**Reorder Point**</span></span>  
  
    -   <span data-ttu-id="53c3f-148">**Safety Stock Level**</span><span class="sxs-lookup"><span data-stu-id="53c3f-148">**Safety Stock Level**</span></span>  
  
    -   <span data-ttu-id="53c3f-149">**Tamaño**</span><span class="sxs-lookup"><span data-stu-id="53c3f-149">**Size**</span></span>  
  
    -   <span data-ttu-id="53c3f-150">**Size Range**</span><span class="sxs-lookup"><span data-stu-id="53c3f-150">**Size Range**</span></span>  
  
    -   <span data-ttu-id="53c3f-151">**Estilo**</span><span class="sxs-lookup"><span data-stu-id="53c3f-151">**Style**</span></span>  
  
    -   <span data-ttu-id="53c3f-152">**Peso**</span><span class="sxs-lookup"><span data-stu-id="53c3f-152">**Weight**</span></span>  
  
2.  <span data-ttu-id="53c3f-153">En el campo de la propiedad **AttributeHierarchyDisplayFolder** en el ventana Propiedades, escriba `Stocking` .</span><span class="sxs-lookup"><span data-stu-id="53c3f-153">In the **AttributeHierarchyDisplayFolder** property field in the Properties window, type `Stocking`.</span></span>  
  
     <span data-ttu-id="53c3f-154">Ahora ha agrupado estos atributos en una única carpeta para mostrar.</span><span class="sxs-lookup"><span data-stu-id="53c3f-154">You have now grouped these attributes into a single display folder.</span></span>  
  
3.  <span data-ttu-id="53c3f-155">En el panel **Atributos** , seleccione los atributos siguientes:</span><span class="sxs-lookup"><span data-stu-id="53c3f-155">In the **Attributes** pane, select the following attributes:</span></span>  
  
    -   <span data-ttu-id="53c3f-156">**Dealer Price**</span><span class="sxs-lookup"><span data-stu-id="53c3f-156">**Dealer Price**</span></span>  
  
    -   <span data-ttu-id="53c3f-157">**List Price**</span><span class="sxs-lookup"><span data-stu-id="53c3f-157">**List Price**</span></span>  
  
    -   <span data-ttu-id="53c3f-158">**Standard Cost**</span><span class="sxs-lookup"><span data-stu-id="53c3f-158">**Standard Cost**</span></span>  
  
4.  <span data-ttu-id="53c3f-159">En la celda de la propiedad **AttributeHierarchyDisplayFolder** del ventana Propiedades, escriba `Financial` .</span><span class="sxs-lookup"><span data-stu-id="53c3f-159">In the **AttributeHierarchyDisplayFolder** property cell in the Properties window, type `Financial`.</span></span>  
  
     <span data-ttu-id="53c3f-160">Ahora ha agrupado estos atributos en una segunda carpeta para mostrar.</span><span class="sxs-lookup"><span data-stu-id="53c3f-160">You have now grouped these attributes into a second display folder.</span></span>  
  
5.  <span data-ttu-id="53c3f-161">En el panel **Atributos** , seleccione los atributos siguientes:</span><span class="sxs-lookup"><span data-stu-id="53c3f-161">In the **Attributes** pane, select the following attributes:</span></span>  
  
    -   <span data-ttu-id="53c3f-162">**Fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="53c3f-162">**End Date**</span></span>  
  
    -   <span data-ttu-id="53c3f-163">**Fecha de inicio**</span><span class="sxs-lookup"><span data-stu-id="53c3f-163">**Start Date**</span></span>  
  
    -   <span data-ttu-id="53c3f-164">**Estado**</span><span class="sxs-lookup"><span data-stu-id="53c3f-164">**Status**</span></span>  
  
6.  <span data-ttu-id="53c3f-165">En la celda de la propiedad **AttributeHierarchyDisplayFolder** del ventana Propiedades, escriba `History` .</span><span class="sxs-lookup"><span data-stu-id="53c3f-165">In the **AttributeHierarchyDisplayFolder** property cell in the Properties window, type `History`.</span></span>  
  
     <span data-ttu-id="53c3f-166">Ahora ha agrupado estos atributos en una tercera carpeta para mostrar.</span><span class="sxs-lookup"><span data-stu-id="53c3f-166">You have now grouped these attributes into a third display folder.</span></span>  
  
7.  <span data-ttu-id="53c3f-167">Seleccione la `Product Model Lines` jerarquía en el panel **jerarquías** y, a continuación, cambie la propiedad **AllMemberName** de la ventana Propiedades a `All Products` .</span><span class="sxs-lookup"><span data-stu-id="53c3f-167">Select the `Product Model Lines` hierarchy in the **Hierarchies** pane, and then change the **AllMemberName** property in the Properties window to `All Products`.</span></span>  
  
8.  <span data-ttu-id="53c3f-168">Haga clic en un área abierta del panel **jerarquías** y, a continuación, cambie la propiedad **AttributeAllMemberName** en la parte superior de la ventana Propiedades a `All Products` .</span><span class="sxs-lookup"><span data-stu-id="53c3f-168">Click an open area of the **Hierarchies** pane, and then change the **AttributeAllMemberName** property at the top of the Properties window to `All Products`.</span></span>  
  
     <span data-ttu-id="53c3f-169">Hacer clic en un área abierta permite modificar las propiedades de la dimensión Product propiamente dicha.</span><span class="sxs-lookup"><span data-stu-id="53c3f-169">Clicking an open area lets you modify properties of the Product dimension itself.</span></span> <span data-ttu-id="53c3f-170">También puede hacer clic en **Product** en la parte superior de la lista de atributos del panel **Atributos** .</span><span class="sxs-lookup"><span data-stu-id="53c3f-170">You could also click **Product** at the top of the attributes list in the **Attributes** pane.</span></span>  
  
9. <span data-ttu-id="53c3f-171">En el menú **Archivo**, haga clic en **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="53c3f-171">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="defining-attribute-relationships"></a><span data-ttu-id="53c3f-172">Definición de relaciones de atributo</span><span class="sxs-lookup"><span data-stu-id="53c3f-172">Defining Attribute Relationships</span></span>  
 <span data-ttu-id="53c3f-173">Si los datos subyacentes lo permiten, debería definir relaciones de atributo entre atributos.</span><span class="sxs-lookup"><span data-stu-id="53c3f-173">If the underlying data supports it, you should define attribute relationships between attributes.</span></span> <span data-ttu-id="53c3f-174">La definición de relaciones de atributo acelera el procesamiento de las dimensiones, las particiones y las consultas.</span><span class="sxs-lookup"><span data-stu-id="53c3f-174">Defining attribute relationships speeds up dimension, partition, and query processing.</span></span> <span data-ttu-id="53c3f-175">Para obtener más información, consulte [Definir relaciones de atributo](multidimensional-models/attribute-relationships-define.md) y [Relaciones de atributo](multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="53c3f-175">For more information, see [Define Attribute Relationships](multidimensional-models/attribute-relationships-define.md) and [Attribute Relationships](multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span></span>  
  
#### <a name="to-define-attribute-relationships"></a><span data-ttu-id="53c3f-176">Para definir relaciones de atributo</span><span class="sxs-lookup"><span data-stu-id="53c3f-176">To define attribute relationships</span></span>  
  
1.  <span data-ttu-id="53c3f-177">En el **Diseñador de dimensiones** , para la dimensión Product, haga clic en la pestaña **Relaciones de atributo** .</span><span class="sxs-lookup"><span data-stu-id="53c3f-177">In the **Dimension Designer** for the Product dimension, click the **Attribute Relationships** tab.</span></span>  
  
2.  <span data-ttu-id="53c3f-178">En el diagrama, haga clic con el botón derecho en el atributo **Model Name** y haga clic en **Nueva relación de atributo**.</span><span class="sxs-lookup"><span data-stu-id="53c3f-178">In the diagram, right-click the **Model Name** attribute, and then click **New Attribute Relationship**.</span></span>  
  
3.  <span data-ttu-id="53c3f-179">En el cuadro de diálogo **Crear relación de atributo** , el **Atributo de origen** es **Model Name**.</span><span class="sxs-lookup"><span data-stu-id="53c3f-179">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is **Model Name**.</span></span> <span data-ttu-id="53c3f-180">Establezca el **Atributo relacionado** en **Product Line**.</span><span class="sxs-lookup"><span data-stu-id="53c3f-180">Set the **Related Attribute** to **Product Line**.</span></span>  
  
     <span data-ttu-id="53c3f-181">En la lista **Tipo de relación** , deje establecido el tipo de relación en **Flexible** , ya que las relaciones entre los miembros pueden cambiar con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="53c3f-181">In the **Relationship type** list, leave the relationship type set to **Flexible** because relationships between the members might change over time.</span></span> <span data-ttu-id="53c3f-182">Por ejemplo, un modelo de producto podría moverse a otra línea de producto.</span><span class="sxs-lookup"><span data-stu-id="53c3f-182">For example, a product model might eventually be moved to a different product line.</span></span>  
  
4.  <span data-ttu-id="53c3f-183">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="53c3f-183">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="53c3f-184">En el menú **Archivo**, haga clic en **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="53c3f-184">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="reviewing-product-dimension-changes"></a><span data-ttu-id="53c3f-185">Revisar los cambios de la dimensión Product</span><span class="sxs-lookup"><span data-stu-id="53c3f-185">Reviewing Product Dimension Changes</span></span>  
  
#### <a name="to-review-the-product-dimension-changes"></a><span data-ttu-id="53c3f-186">Para revisar los cambios de la dimensión Product</span><span class="sxs-lookup"><span data-stu-id="53c3f-186">To review the Product dimension changes</span></span>  
  
1.  <span data-ttu-id="53c3f-187">En el menú **Generar** de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], haga clic en **Implementar Tutorial de Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="53c3f-187">On the **Build** menu of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="53c3f-188">Después de que aparezca el mensaje **La implementación finalizó correctamente** , haga clic en la pestaña **Explorador** del **Diseñador de dimensiones** para la dimensión **Product** y, luego, haga clic en el botón Volver a conectar de la barra de herramientas del diseñador.</span><span class="sxs-lookup"><span data-stu-id="53c3f-188">After you have received the **Deployment Completed Successfully** message, click the **Browser** tab of **Dimension Designer** for the **Product** dimension, and then click the Reconnect button on the toolbar of the designer.</span></span>  
  
3.  <span data-ttu-id="53c3f-189">Compruebe que `Product Model Lines` está seleccionado en la lista **jerarquía** y, a continuación, expanda `All Products` .</span><span class="sxs-lookup"><span data-stu-id="53c3f-189">Verify that `Product Model Lines` is selected in the **Hierarchy** list, and then expand `All Products`.</span></span>  
  
     <span data-ttu-id="53c3f-190">Observe que el nombre del miembro **todos** aparece como `All Products` .</span><span class="sxs-lookup"><span data-stu-id="53c3f-190">Notice that the name of the **All** member appears as `All Products`.</span></span> <span data-ttu-id="53c3f-191">Esto se debe a que ha cambiado la propiedad **AllMemberName** de la jerarquía a `All Products` anteriormente en la lección.</span><span class="sxs-lookup"><span data-stu-id="53c3f-191">This is because you changed the **AllMemberName** property for the hierarchy to `All Products` earlier in the lesson.</span></span> <span data-ttu-id="53c3f-192">Además, los miembros del nivel **Product Line** ahora tienen nombres descriptivos, en lugar de abreviaturas de una sola letra.</span><span class="sxs-lookup"><span data-stu-id="53c3f-192">Also, the members of the **Product Line** level now have user-friendly names, instead of single-letter abbreviations.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="53c3f-193">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="53c3f-193">Next Task in Lesson</span></span>  
 [<span data-ttu-id="53c3f-194">Modificar la dimensión Date</span><span class="sxs-lookup"><span data-stu-id="53c3f-194">Modifying the Date Dimension</span></span>](lesson-3-4-modifying-the-date-dimension.md)  
  
## <a name="see-also"></a><span data-ttu-id="53c3f-195">Consulte también</span><span class="sxs-lookup"><span data-stu-id="53c3f-195">See Also</span></span>  
 <span data-ttu-id="53c3f-196">[Definir cálculos con nombre en una vista del origen de datos &#40;Analysis Services&#41;](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="53c3f-196">[Define Named Calculations in a Data Source View &#40;Analysis Services&#41;](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md) </span></span>  
 <span data-ttu-id="53c3f-197">[Crear jerarquías definidas por el usuario](multidimensional-models/user-defined-hierarchies-create.md) </span><span class="sxs-lookup"><span data-stu-id="53c3f-197">[Create User-Defined Hierarchies](multidimensional-models/user-defined-hierarchies-create.md) </span></span>  
 [<span data-ttu-id="53c3f-198">Configurar el nivel &#40;All&#41; para las jerarquías de atributo</span><span class="sxs-lookup"><span data-stu-id="53c3f-198">Configure the &#40;All&#41; Level for Attribute Hierarchies</span></span>](multidimensional-models/database-dimensions-configure-the-all-level-for-attribute-hierarchies.md)  
  
  
