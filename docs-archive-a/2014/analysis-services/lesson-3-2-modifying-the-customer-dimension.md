---
title: Modificar la dimensión Customer | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 5b5aed99-1760-4bc7-b248-52ecb0b97ebc
author: minewiskan
ms.author: owend
ms.openlocfilehash: bd5c5c47205a89f8429b0b6f0ba55da266d5e811
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675029"
---
# <a name="modifying-the-customer-dimension"></a><span data-ttu-id="68312-102">Modificar la dimensión Customer</span><span class="sxs-lookup"><span data-stu-id="68312-102">Modifying the Customer Dimension</span></span>
  <span data-ttu-id="68312-103">Existen varios métodos para hacer que las dimensiones de un cubo sean más fáciles de usar y tengan más funciones.</span><span class="sxs-lookup"><span data-stu-id="68312-103">There are many different ways that you can increase the usability and functionality of the dimensions in a cube.</span></span> <span data-ttu-id="68312-104">En las tareas de este tema, debe modificar la dimensión Customer.</span><span class="sxs-lookup"><span data-stu-id="68312-104">In the tasks in this topic, you modify the Customer dimension.</span></span>  
  
## <a name="renaming-attributes"></a><span data-ttu-id="68312-105">Cambiar el nombre de los atributos</span><span class="sxs-lookup"><span data-stu-id="68312-105">Renaming Attributes</span></span>  
 <span data-ttu-id="68312-106">Use la pestaña **Estructura de dimensión** del Diseñador de dimensiones para cambiar los nombres de los atributos.</span><span class="sxs-lookup"><span data-stu-id="68312-106">You can change attribute names with the **Dimension Structure** tab of Dimension Designer.</span></span>  
  
#### <a name="to-rename-an-attribute"></a><span data-ttu-id="68312-107">Para cambiar el nombre de un atributo</span><span class="sxs-lookup"><span data-stu-id="68312-107">To rename an attribute</span></span>  
  
1.  <span data-ttu-id="68312-108">Cambie al **Diseñador de dimensiones** para la dimensión Customer en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="68312-108">Switch to **Dimension Designer** for the Customer dimension in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="68312-109">Para ello, haga doble clic en la dimensión **Customer** del nodo **Dimensiones** del Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="68312-109">To do this, double-click the **Customer** dimension in the **Dimensions** node of Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="68312-110">En el panel **Atributos** , haga clic con el botón derecho en **English Country Region Name**y haga clic en **Cambiar nombre**.</span><span class="sxs-lookup"><span data-stu-id="68312-110">In the **Attributes** pane, right-click **English Country Region Name**, and then click **Rename**.</span></span> <span data-ttu-id="68312-111">Cambie el nombre del atributo a `Country-Region` .</span><span class="sxs-lookup"><span data-stu-id="68312-111">Change the name of the attribute to `Country-Region`.</span></span>  
  
3.  <span data-ttu-id="68312-112">Cambie los nombres de los atributos siguientes del mismo modo:</span><span class="sxs-lookup"><span data-stu-id="68312-112">Change the names of the following attributes in the same manner:</span></span>  
  
    -   <span data-ttu-id="68312-113">Atributo de **educación en inglés** : cambiar a`Education`</span><span class="sxs-lookup"><span data-stu-id="68312-113">**English Education** attribute - change to `Education`</span></span>  
  
    -   <span data-ttu-id="68312-114">Atributo de **ocupación en inglés** : cambiar a`Occupation`</span><span class="sxs-lookup"><span data-stu-id="68312-114">**English Occupation** attribute - change to `Occupation`</span></span>  
  
    -   <span data-ttu-id="68312-115">Atributo de **nombre de provincia de estado** : cambiar a`State-Province`</span><span class="sxs-lookup"><span data-stu-id="68312-115">**State Province Name** attribute - change to `State-Province`</span></span>  
  
4.  <span data-ttu-id="68312-116">En el menú **Archivo**, haga clic en **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="68312-116">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="creating-a-hierarchy"></a><span data-ttu-id="68312-117">Creación de una jerarquía</span><span class="sxs-lookup"><span data-stu-id="68312-117">Creating a Hierarchy</span></span>  
 <span data-ttu-id="68312-118">Puede crear una nueva jerarquía si arrastra un atributo desde el panel **Atributos** hasta el panel **Jerarquías** .</span><span class="sxs-lookup"><span data-stu-id="68312-118">You can create a new hierarchy by dragging an attribute from the **Attributes** pane to the **Hierarchies** pane.</span></span>  
  
#### <a name="to-create-a-hierarchy"></a><span data-ttu-id="68312-119">Para crear una jerarquía</span><span class="sxs-lookup"><span data-stu-id="68312-119">To create a hierarchy</span></span>  
  
1.  <span data-ttu-id="68312-120">Arrastre el `Country-Region` atributo desde el panel **atributos** al panel **jerarquías** .</span><span class="sxs-lookup"><span data-stu-id="68312-120">Drag the `Country-Region` attribute from the **Attributes** pane into the **Hierarchies** pane.</span></span>  
  
2.  <span data-ttu-id="68312-121">Arrastre el `State-Province` atributo desde el panel **atributos** a la **\<new level>** celda del panel **jerarquías** , debajo del `Country-Region` nivel.</span><span class="sxs-lookup"><span data-stu-id="68312-121">Drag the `State-Province` attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the `Country-Region` level.</span></span>  
  
3.  <span data-ttu-id="68312-122">Arrastre el atributo **City** desde el panel **atributos** a la **\<new level>** celda del panel **jerarquías** , debajo del `State-Province` nivel.</span><span class="sxs-lookup"><span data-stu-id="68312-122">Drag the **City** attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the `State-Province` level.</span></span>  
  
4.  <span data-ttu-id="68312-123">En el panel **jerarquías** de la pestaña **estructura de dimensión** , haga clic con el botón secundario en la barra de título de la jerarquía jerarquía, seleccione **cambiar nombre**y, a continuación, escriba **Hierarchy** `Customer Geography` .</span><span class="sxs-lookup"><span data-stu-id="68312-123">In the **Hierarchies** pane of the **Dimension Structure** tab, right-click the title bar of the **Hierarchy** hierarchy, select **Rename**, and then type `Customer Geography`.</span></span>  
  
     <span data-ttu-id="68312-124">El nombre de la jerarquía es ahora `Customer Geography` .</span><span class="sxs-lookup"><span data-stu-id="68312-124">The name of the hierarchy is now `Customer Geography`.</span></span>  
  
5.  <span data-ttu-id="68312-125">En el menú **Archivo**, haga clic en **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="68312-125">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="adding-a-named-calculation"></a><span data-ttu-id="68312-126">Agregar un cálculo con nombre</span><span class="sxs-lookup"><span data-stu-id="68312-126">Adding a Named Calculation</span></span>  
 <span data-ttu-id="68312-127">Puede agregar un cálculo con nombre, que es una expresión SQL representada como columna calculada en una tabla de la vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="68312-127">You can add a named calculation, which is a SQL expression that is represented as a calculated column, to a table in a data source view.</span></span> <span data-ttu-id="68312-128">Aparece la expresión y se comporta como columna en la tabla.</span><span class="sxs-lookup"><span data-stu-id="68312-128">The expression appears and behaves as a column in the table.</span></span> <span data-ttu-id="68312-129">Los cálculos con nombre permiten ampliar el esquema relacional de las tablas existentes de la vista del origen de datos sin modificar la tabla en el origen de datos subyacente.</span><span class="sxs-lookup"><span data-stu-id="68312-129">Named calculations let you extend the relational schema of existing tables in a data source view without modifying the table in the underlying data source.</span></span> <span data-ttu-id="68312-130">Para obtener más información, vea [definir cálculos con nombre en una vista del origen de datos &#40;Analysis Services&#41;](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md)</span><span class="sxs-lookup"><span data-stu-id="68312-130">For more information, see [Define Named Calculations in a Data Source View &#40;Analysis Services&#41;](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md)</span></span>  
  
#### <a name="to-add-a-named-calculation"></a><span data-ttu-id="68312-131">Para agregar un cálculo con nombre</span><span class="sxs-lookup"><span data-stu-id="68312-131">To add a named calculation</span></span>  
  
1.  <span data-ttu-id="68312-132">Abra la vista del origen de datos \*\* [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW 2012\*\* haciendo doble clic en ella en la carpeta **vistas del origen de datos** en explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="68312-132">Open the **[!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW 2012** data source view by double-clicking it in the **Data Source Views** folder in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="68312-133">En el panel **Tablas** , haga clic con el botón derecho en **Customer**y, después, haga clic en **Nuevo cálculo con nombre**.</span><span class="sxs-lookup"><span data-stu-id="68312-133">In the **Tables** pane on the left, right-click **Customer**, and then click **New Named Calculation**.</span></span>  
  
3.  <span data-ttu-id="68312-134">En el cuadro de diálogo **crear cálculo con nombre** , escriba `FullName` en el cuadro **nombre de columna** y, a continuación, escriba o copie y pegue la siguiente `CASE` instrucción en el cuadro **expresión** :</span><span class="sxs-lookup"><span data-stu-id="68312-134">In the **Create Named Calculation** dialog box, type `FullName` in the **Column name** box, and then type or copy and paste the following `CASE` statement in the **Expression** box:</span></span>  
  
    ```  
    CASE  
       WHEN MiddleName IS NULL THEN  
       FirstName + ' ' + LastName  
       ELSE  
       FirstName + ' ' + MiddleName + ' ' + LastName  
    END  
    ```  
  
     <span data-ttu-id="68312-135">La `CASE` instrucción concatena las columnas **FirstName**, **MiddleName**y **LastName** en una única columna que se usará en la dimensión Customer como el nombre mostrado para el atributo **Customer** .</span><span class="sxs-lookup"><span data-stu-id="68312-135">The `CASE` statement concatenates the **FirstName**, **MiddleName**, and **LastName** columns into a single column that you will use in the Customer dimension as the displayed name for the **Customer** attribute.</span></span>  
  
4.  <span data-ttu-id="68312-136">Haga clic en **Aceptar**y expanda **Customer** en el panel **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="68312-136">Click **OK**, and then expand **Customer** in the **Tables** pane.</span></span>  
  
     <span data-ttu-id="68312-137">El `FullName` cálculo con nombre aparece en la lista de columnas de la tabla Customer, con un icono que indica que se trata de un cálculo con nombre.</span><span class="sxs-lookup"><span data-stu-id="68312-137">The `FullName` named calculation appears in the list of columns in the Customer table, with an icon that indicates that it is a named calculation.</span></span>  
  
5.  <span data-ttu-id="68312-138">En el menú **Archivo**, haga clic en **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="68312-138">On the **File** menu, click **Save All**.</span></span>  
  
6.  <span data-ttu-id="68312-139">En el panel **Tablas** , haga clic con el botón derecho en **Customer**y haga clic en **Explorar datos**.</span><span class="sxs-lookup"><span data-stu-id="68312-139">In the **Tables** pane, right-click **Customer**, and then click **Explore Data**.</span></span>  
  
7.  <span data-ttu-id="68312-140">Revise la última columna de la vista **Explorar la tabla Customer** .</span><span class="sxs-lookup"><span data-stu-id="68312-140">Review the last column in the **Explore Customer Table** view.</span></span>  
  
     <span data-ttu-id="68312-141">Observe que la `FullName` columna aparece en la vista del origen de datos, concatenando correctamente los datos de varias columnas del origen de datos subyacente y sin modificar el origen de datos original.</span><span class="sxs-lookup"><span data-stu-id="68312-141">Notice that the `FullName` column appears in the data source view, correctly concatenating data from several columns from the underlying data source and without modifying the original data source.</span></span>  
  
8.  <span data-ttu-id="68312-142">Cierre la pestaña **Explorar la tabla Customer** .</span><span class="sxs-lookup"><span data-stu-id="68312-142">Close the **Explore Customer Table** tab.</span></span>  
  
## <a name="using-the-named-calculation-for-member-names"></a><span data-ttu-id="68312-143">Usar el cálculo con nombre para los nombres de miembro</span><span class="sxs-lookup"><span data-stu-id="68312-143">Using the Named Calculation for Member Names</span></span>  
 <span data-ttu-id="68312-144">Una vez que ha creado un cálculo con nombre en la vista del origen de datos, puede usar ese cálculo como propiedad de un atributo.</span><span class="sxs-lookup"><span data-stu-id="68312-144">After you have created a named calculation in the data source view, you can use the named calculation as a property of an attribute.</span></span>  
  
#### <a name="to-use-the-named-calculation-for-member-names"></a><span data-ttu-id="68312-145">Para utilizar el cálculo con nombre para los nombres de miembro</span><span class="sxs-lookup"><span data-stu-id="68312-145">To use the named calculation for member names</span></span>  
  
1.  <span data-ttu-id="68312-146">Pase al Diseñador de dimensiones para la dimensión Customer.</span><span class="sxs-lookup"><span data-stu-id="68312-146">Switch to Dimension Designer for the Customer dimension.</span></span>  
  
2.  <span data-ttu-id="68312-147">En el panel **Atributos** de la pestaña **Estructura de dimensión** , haga clic en el atributo **Customer Key** .</span><span class="sxs-lookup"><span data-stu-id="68312-147">In the **Attributes** pane of the **Dimension Structure** tab, click the **Customer Key** attribute.</span></span>  
  
3.  <span data-ttu-id="68312-148">Abra la ventana Propiedades y haga clic en el botón **Ocultar automáticamente** de la barra de título para que permanezca abierta.</span><span class="sxs-lookup"><span data-stu-id="68312-148">Open the Properties window and click the **Auto Hide** button on the title bar so that it stays open.</span></span>  
  
4.  <span data-ttu-id="68312-149">En el campo de la propiedad **nombre** , escriba `Full Name` .</span><span class="sxs-lookup"><span data-stu-id="68312-149">In the **Name** property field, type `Full Name`.</span></span>  
  
5.  <span data-ttu-id="68312-150">Haga clic en el campo de la propiedad **NameColumn** situado en la parte inferior y, a continuación, haga clic en el botón Examinar (**...**) para abrir el cuadro de diálogo **columna de nombre** .</span><span class="sxs-lookup"><span data-stu-id="68312-150">Click in the **NameColumn** property field at the bottom, and then click the browse (**...**) button to open the **Name Column** dialog box.</span></span>  
  
6.  <span data-ttu-id="68312-151">Seleccione `FullName` en la parte inferior de la lista **columna de origen** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="68312-151">Select `FullName` at the bottom of the **Source column** list, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="68312-152">En la pestaña estructura de dimensiones, arrastre el `Full Name` atributo desde el panel **atributos** a la **\<new level>** celda del panel **jerarquías** , debajo del nivel **City** .</span><span class="sxs-lookup"><span data-stu-id="68312-152">In the Dimensions Structure tab, drag the `Full Name` attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **City** level.</span></span>  
  
8.  <span data-ttu-id="68312-153">En el menú **Archivo**, haga clic en **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="68312-153">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="defining-display-folders"></a><span data-ttu-id="68312-154">Definir carpetas para mostrar</span><span class="sxs-lookup"><span data-stu-id="68312-154">Defining Display Folders</span></span>  
 <span data-ttu-id="68312-155">Puede utilizar carpetas para mostrar para agrupar jerarquías de usuario y de atributo en estructuras de carpeta con el fin de facilitar el uso de dichas estructuras.</span><span class="sxs-lookup"><span data-stu-id="68312-155">You can use display folders to group user and attribute hierarchies into folder structures to increase usability.</span></span>  
  
#### <a name="to-define-display-folders"></a><span data-ttu-id="68312-156">Para definir carpetas para mostrar</span><span class="sxs-lookup"><span data-stu-id="68312-156">To define display folders</span></span>  
  
1.  <span data-ttu-id="68312-157">Abra la pestaña **Estructura de dimensión** para la dimensión Customer.</span><span class="sxs-lookup"><span data-stu-id="68312-157">Open the **Dimension Structure** tab for the Customer dimension.</span></span>  
  
2.  <span data-ttu-id="68312-158">En el panel **Atributos** , mantenga pulsada la tecla CTRL mientras hace clic en cada uno de los atributos siguientes para seleccionarlos:</span><span class="sxs-lookup"><span data-stu-id="68312-158">In the **Attributes** pane, select the following attributes by holding down the CTRL key while clicking each of them:</span></span>  
  
    -   <span data-ttu-id="68312-159">**Ciudad**</span><span class="sxs-lookup"><span data-stu-id="68312-159">**City**</span></span>  
  
    -   `Country-Region`  
  
    -   <span data-ttu-id="68312-160">**Código postal**</span><span class="sxs-lookup"><span data-stu-id="68312-160">**Postal Code**</span></span>  
  
    -   `State-Province`  
  
3.  <span data-ttu-id="68312-161">En el ventana Propiedades, haga clic en el campo de la propiedad **AttributeHierarchyDisplayFolder** en la parte superior (puede que tenga que apuntar para ver el nombre completo) y, a continuación, escriba `Location` .</span><span class="sxs-lookup"><span data-stu-id="68312-161">In the Properties window, click the **AttributeHierarchyDisplayFolder** property field at the top (you might need to point to it to see the full name), and then type `Location`.</span></span>  
  
4.  <span data-ttu-id="68312-162">En el panel **jerarquías** , haga clic en `Customer Geography` y, en el ventana Propiedades de la derecha, seleccione `Location` como el valor de la propiedad **DisplayFolder** .</span><span class="sxs-lookup"><span data-stu-id="68312-162">In the **Hierarchies** pane, click `Customer Geography`, and then in the Properties window on the right, select `Location` as the value of the **DisplayFolder** property.</span></span>  
  
5.  <span data-ttu-id="68312-163">En el panel **Atributos** , mantenga pulsada la tecla CTRL mientras hace clic en cada uno de los atributos siguientes para seleccionarlos:</span><span class="sxs-lookup"><span data-stu-id="68312-163">In the **Attributes** pane, select the following attributes by holding down the CTRL key while clicking each of them:</span></span>  
  
    -   <span data-ttu-id="68312-164">**Commute Distance**</span><span class="sxs-lookup"><span data-stu-id="68312-164">**Commute Distance**</span></span>  
  
    -   `Education`  
  
    -   <span data-ttu-id="68312-165">**Mujer**</span><span class="sxs-lookup"><span data-stu-id="68312-165">**Gender**</span></span>  
  
    -   <span data-ttu-id="68312-166">**House Owner Flag**</span><span class="sxs-lookup"><span data-stu-id="68312-166">**House Owner Flag**</span></span>  
  
    -   <span data-ttu-id="68312-167">**Marital Status**</span><span class="sxs-lookup"><span data-stu-id="68312-167">**Marital Status**</span></span>  
  
    -   <span data-ttu-id="68312-168">**Number Cars Owned**</span><span class="sxs-lookup"><span data-stu-id="68312-168">**Number Cars Owned**</span></span>  
  
    -   <span data-ttu-id="68312-169">**Number Children At Home**</span><span class="sxs-lookup"><span data-stu-id="68312-169">**Number Children At Home**</span></span>  
  
    -   `Occupation`  
  
    -   <span data-ttu-id="68312-170">**Total Children**</span><span class="sxs-lookup"><span data-stu-id="68312-170">**Total Children**</span></span>  
  
    -   <span data-ttu-id="68312-171">**Yearly Income**</span><span class="sxs-lookup"><span data-stu-id="68312-171">**Yearly Income**</span></span>  
  
6.  <span data-ttu-id="68312-172">En el ventana Propiedades, haga clic en el campo de la propiedad **AttributeHierarchyDisplayFolder** en la parte superior y, a continuación, escriba `Demographic` .</span><span class="sxs-lookup"><span data-stu-id="68312-172">In the Properties window, click the **AttributeHierarchyDisplayFolder** property field at the top, and then type `Demographic`.</span></span>  
  
7.  <span data-ttu-id="68312-173">En el panel **Atributos** , mantenga pulsada la tecla CTRL mientras hace clic en cada uno de los atributos siguientes para seleccionarlos:</span><span class="sxs-lookup"><span data-stu-id="68312-173">In the **Attributes** pane, select the following attributes by holding down the CTRL key while clicking each of them:</span></span>  
  
    -   <span data-ttu-id="68312-174">**Dirección de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="68312-174">**Email Address**</span></span>  
  
    -   <span data-ttu-id="68312-175">**Teléfono**</span><span class="sxs-lookup"><span data-stu-id="68312-175">**Phone**</span></span>  
  
8.  <span data-ttu-id="68312-176">En el ventana Propiedades, haga clic en el campo de la propiedad **AttributeHierarchyDisplayFolder** y escriba `Contacts` .</span><span class="sxs-lookup"><span data-stu-id="68312-176">In the Properties window, click the **AttributeHierarchyDisplayFolder** property field and type `Contacts`.</span></span>  
  
9. <span data-ttu-id="68312-177">En el menú **Archivo**, haga clic en **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="68312-177">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="defining-composite-keycolumns"></a><span data-ttu-id="68312-178">Definir KeyColumns compuestas</span><span class="sxs-lookup"><span data-stu-id="68312-178">Defining Composite KeyColumns</span></span>  
 <span data-ttu-id="68312-179">La propiedad **KeyColumns** contiene la columna o columnas que representan la clave para el atributo.</span><span class="sxs-lookup"><span data-stu-id="68312-179">The **KeyColumns** property contains the column or columns that represent the key for the attribute.</span></span> <span data-ttu-id="68312-180">En esta lección, creará una clave compuesta para la **ciudad** y `State-Province` los atributos.</span><span class="sxs-lookup"><span data-stu-id="68312-180">In this lesson, you create a composite key for the **City** and `State-Province` attributes.</span></span> <span data-ttu-id="68312-181">Las claves compuestas pueden resultar de utilidad cuando necesite identificar un atributo de forma inequívoca.</span><span class="sxs-lookup"><span data-stu-id="68312-181">Composite keys can be helpful when you need to uniquely identify an attribute.</span></span> <span data-ttu-id="68312-182">Por ejemplo, al definir las relaciones de atributo más adelante en este tutorial, un atributo **City** debe identificar de forma única un `State-Province` atributo.</span><span class="sxs-lookup"><span data-stu-id="68312-182">For example, when you define attribute relationships later in this tutorial, a **City** attribute must uniquely identify a `State-Province` attribute.</span></span> <span data-ttu-id="68312-183">Sin embargo, podrían existir varias ciudades con el mismo nombre en estados diferentes.</span><span class="sxs-lookup"><span data-stu-id="68312-183">However, there could be several cities with the same name in different states.</span></span> <span data-ttu-id="68312-184">Por este motivo, deberá crear una clave compuesta formada por las columnas **StateProvinceName** y **City** para el atributo **City** .</span><span class="sxs-lookup"><span data-stu-id="68312-184">For this reason, you will create a composite key that is composed of the **StateProvinceName** and **City** columns for the **City** attribute.</span></span> <span data-ttu-id="68312-185">Para más información, vea [Modificar la propiedad KeyColumns de un atributo](multidimensional-models/attribute-properties-modify-the-keycolumn-property.md).</span><span class="sxs-lookup"><span data-stu-id="68312-185">For more information, see [Modify the KeyColumn Property of an Attribute](multidimensional-models/attribute-properties-modify-the-keycolumn-property.md).</span></span>  
  
#### <a name="to-define-composite-keycolumns-for-the-city-attribute"></a><span data-ttu-id="68312-186">Para definir KeyColumns compuestas para el atributo City</span><span class="sxs-lookup"><span data-stu-id="68312-186">To define composite KeyColumns for the City attribute</span></span>  
  
1.  <span data-ttu-id="68312-187">Abra la pestaña **Estructura de dimensión** para la dimensión Customer.</span><span class="sxs-lookup"><span data-stu-id="68312-187">Open the **Dimension Structure** tab for the Customer dimension.</span></span>  
  
2.  <span data-ttu-id="68312-188">En el panel **Atributos** , haga clic en el atributo **City** .</span><span class="sxs-lookup"><span data-stu-id="68312-188">In the **Attributes** pane, click the **City** attribute.</span></span>  
  
3.  <span data-ttu-id="68312-189">En la ventana **Propiedades** , haga clic en el campo **KeyColumns** junto a la parte final y, después, haga clic en el botón Examinar (**...**).</span><span class="sxs-lookup"><span data-stu-id="68312-189">In the **Properties** window, click in the **KeyColumns** field near the bottom, and then click the browse (**...**) button.</span></span>  
  
4.  <span data-ttu-id="68312-190">En el cuadro de diálogo **Columnas de clave** , en la lista **Columnas disponibles** , seleccione la columna **StateProvinceName**y, después, haga clic en el botón **>** .</span><span class="sxs-lookup"><span data-stu-id="68312-190">In the **Key Columns** dialog box, in the **Available Columns** list, select the column **StateProvinceName**, and then click the **>** button.</span></span>  
  
     <span data-ttu-id="68312-191">Las columnas **City** y **StateProvinceName** se muestran ahora en la lista **Columnas de clave** .</span><span class="sxs-lookup"><span data-stu-id="68312-191">The **City** and **StateProvinceName** columns are now displayed in the **Key Columns** list.</span></span>  
  
5.  <span data-ttu-id="68312-192">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="68312-192">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="68312-193">Para establecer la propiedad **NameColumn** del atributo **City** , haga clic en el campo **NameColumn** en la ventana Propiedades y, después, haga clic en el botón Examinar (**...**).</span><span class="sxs-lookup"><span data-stu-id="68312-193">To set the **NameColumn** property of the **City** attribute, click the **NameColumn** field in the Properties window, and then click the browse (**...**) button.</span></span>  
  
7.  <span data-ttu-id="68312-194">En el cuadro de diálogo **Columna de nombre** , en la lista **Columna de origen** , seleccione **City**y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="68312-194">In the **Name Column** dialog box, in the **Source column** list, select **City**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="68312-195">En el menú **Archivo**, haga clic en **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="68312-195">On the **File** menu, click **Save All**.</span></span>  
  
#### <a name="to-define-composite-keycolumns-for-the-state-province-attribute"></a><span data-ttu-id="68312-196">Para definir KeyColumns compuestas para el atributo State-Province</span><span class="sxs-lookup"><span data-stu-id="68312-196">To define composite KeyColumns for the State-Province attribute</span></span>  
  
1.  <span data-ttu-id="68312-197">Asegúrese de que la pestaña **Estructura de dimensión** para la dimensión Customer está abierta.</span><span class="sxs-lookup"><span data-stu-id="68312-197">Make sure the **Dimension Structure** tab for the Customer dimension is open.</span></span>  
  
2.  <span data-ttu-id="68312-198">En el panel **atributos** , haga clic en el `State-Province` atributo.</span><span class="sxs-lookup"><span data-stu-id="68312-198">In the **Attributes** pane, click the `State-Province` attribute.</span></span>  
  
3.  <span data-ttu-id="68312-199">En la ventana **Propiedades** , haga clic en el campo **KeyColumns** y, después, haga clic en el botón Examinar (**...**).</span><span class="sxs-lookup"><span data-stu-id="68312-199">In the **Properties** window, click in the **KeyColumns** field, and then click the browse (**...**) button.</span></span>  
  
4.  <span data-ttu-id="68312-200">En el cuadro de diálogo **Columnas de clave** , en la lista **Columnas disponibles** , seleccione la columna **EnglishCountryRegionName**y, después, haga clic en el botón **>** .</span><span class="sxs-lookup"><span data-stu-id="68312-200">In the **Key Columns** dialog box, in the **Available Columns** list, select the column **EnglishCountryRegionName**, and then click the **>** button.</span></span>  
  
     <span data-ttu-id="68312-201">Las columnas **EnglishCountryRegionName** y **StateProvinceName** se muestran ahora en la lista **Columnas de clave** .</span><span class="sxs-lookup"><span data-stu-id="68312-201">The **EnglishCountryRegionName** and **StateProvinceName** columns are now displayed in the **Key Columns** list.</span></span>  
  
5.  <span data-ttu-id="68312-202">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="68312-202">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="68312-203">Para establecer la propiedad **NameColumn** del `State-Province` atributo, haga clic en el campo **NameColumn** en el ventana Propiedades y, a continuación, haga clic en el botón Examinar (**...**).</span><span class="sxs-lookup"><span data-stu-id="68312-203">To set the **NameColumn** property of the `State-Province` attribute, click the **NameColumn** field in the Properties window, and then click the browse (**...**) button.</span></span>  
  
7.  <span data-ttu-id="68312-204">En el cuadro de diálogo **Columna de nombre** , en la lista **Columna de origen** , seleccione **StateProvinceName**y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="68312-204">In the **Name Column** dialog box, in the **Source column** list, select **StateProvinceName**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="68312-205">En el menú **Archivo**, haga clic en **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="68312-205">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="defining-attribute-relationships"></a><span data-ttu-id="68312-206">Definición de relaciones de atributo</span><span class="sxs-lookup"><span data-stu-id="68312-206">Defining Attribute Relationships</span></span>  
 <span data-ttu-id="68312-207">Si los datos subyacentes lo permiten, debería definir relaciones de atributo entre atributos.</span><span class="sxs-lookup"><span data-stu-id="68312-207">If the underlying data supports it, you should define attribute relationships between attributes.</span></span> <span data-ttu-id="68312-208">La definición de relaciones de atributo acelera el procesamiento de las dimensiones, las particiones y las consultas.</span><span class="sxs-lookup"><span data-stu-id="68312-208">Defining attribute relationships speeds up dimension, partition, and query processing.</span></span> <span data-ttu-id="68312-209">Para obtener más información, consulte [Definir relaciones de atributo](multidimensional-models/attribute-relationships-define.md) y [Relaciones de atributo](multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="68312-209">For more information, see [Define Attribute Relationships](multidimensional-models/attribute-relationships-define.md) and [Attribute Relationships](multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span></span>  
  
#### <a name="to-define-attribute-relationships"></a><span data-ttu-id="68312-210">Para definir relaciones de atributo</span><span class="sxs-lookup"><span data-stu-id="68312-210">To define attribute relationships</span></span>  
  
1.  <span data-ttu-id="68312-211">En el **Diseñador de dimensiones** para la dimensión Customer, haga clic en la pestaña **relaciones de atributo** . Es posible que tenga que esperar.</span><span class="sxs-lookup"><span data-stu-id="68312-211">In the **Dimension Designer** for the Customer dimension, click the **Attribute Relationships** tab. You might need to wait.</span></span>  
  
2.  <span data-ttu-id="68312-212">En el diagrama, haga clic con el botón derecho en el atributo **City** y haga clic en **Nueva relación de atributo**.</span><span class="sxs-lookup"><span data-stu-id="68312-212">In the diagram, right-click the **City** attribute, and then click **New Attribute Relationship**.</span></span>  
  
3.  <span data-ttu-id="68312-213">En el cuadro de diálogo **Crear relación de atributo** , el **Atributo de origen** es **City**.</span><span class="sxs-lookup"><span data-stu-id="68312-213">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is **City**.</span></span> <span data-ttu-id="68312-214">Establezca el **atributo relacionado** en `State-Province` .</span><span class="sxs-lookup"><span data-stu-id="68312-214">Set the **Related Attribute** to `State-Province`.</span></span>  
  
4.  <span data-ttu-id="68312-215">En la lista **Tipo de relación** , establezca el tipo de relación en **Rígida**.</span><span class="sxs-lookup"><span data-stu-id="68312-215">In the **Relationship type** list, set the relationship type to **Rigid**.</span></span>  
  
     <span data-ttu-id="68312-216">El tipo de relación es **Rígida** porque las relaciones entre los miembros no cambiarán con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="68312-216">The relationship type is **Rigid** because relationships between the members will not change over time.</span></span> <span data-ttu-id="68312-217">Por ejemplo, es poco habitual que una ciudad pase a formar parte de otro estado o provincia.</span><span class="sxs-lookup"><span data-stu-id="68312-217">For example, it would be unusual for a city to become part of a different state or province.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="68312-218">En el diagrama, haga clic con el botón secundario en el `State-Province` atributo y seleccione **nueva relación de atributo**.</span><span class="sxs-lookup"><span data-stu-id="68312-218">In the diagram, right-click the `State-Province` attribute and then select **New Attribute Relationship**.</span></span>  
  
7.  <span data-ttu-id="68312-219">En el cuadro de diálogo **crear relación de atributo** , el **atributo de origen** es `State-Province` .</span><span class="sxs-lookup"><span data-stu-id="68312-219">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is `State-Province`.</span></span> <span data-ttu-id="68312-220">Establezca el **atributo relacionado** en `Country-Region` .</span><span class="sxs-lookup"><span data-stu-id="68312-220">Set the **Related Attribute** to `Country-Region`.</span></span>  
  
8.  <span data-ttu-id="68312-221">En la lista **Tipo de relación** , establezca el tipo de relación en **Rígida**.</span><span class="sxs-lookup"><span data-stu-id="68312-221">In the **Relationship type** list, set the relationship type to **Rigid**.</span></span>  
  
9. <span data-ttu-id="68312-222">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="68312-222">Click **OK**.</span></span>  
  
10. <span data-ttu-id="68312-223">En el menú **Archivo**, haga clic en **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="68312-223">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="deploying-changes-processing-the-objects-and-viewing-the-changes"></a><span data-ttu-id="68312-224">Implementar cambios, procesar los objetos y ver los cambios</span><span class="sxs-lookup"><span data-stu-id="68312-224">Deploying Changes, Processing the Objects, and Viewing the Changes</span></span>  
 <span data-ttu-id="68312-225">Una vez que ha cambiado los atributos y las jerarquías, debe implementar los cambios y procesar de nuevo los objetos relacionados antes de ver los cambios.</span><span class="sxs-lookup"><span data-stu-id="68312-225">After you have changed attributes and hierarchies, you must deploy the changes and reprocess the related objects before you can view the changes.</span></span>  
  
#### <a name="to-deploy-the-changes-process-the-objects-and-view-the-changes"></a><span data-ttu-id="68312-226">Para implementar los cambios, procesar los objetos y ver los cambios</span><span class="sxs-lookup"><span data-stu-id="68312-226">To deploy the changes, process the objects, and view the changes</span></span>  
  
1.  <span data-ttu-id="68312-227">En el menú **Generar** de [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], haga clic en **Implementar Tutorial de Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="68312-227">On the **Build** menu of [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="68312-228">Después de que aparezca el mensaje **La implementación finalizó correctamente** , haga clic en la pestaña **Explorador** del Diseñador de dimensiones para la dimensión Customer y, después, haga clic en el botón Volver a conectar en el lado izquierdo de la barra de herramientas del diseñador.</span><span class="sxs-lookup"><span data-stu-id="68312-228">After you receive the **Deployment Completed Successfully** message, click the **Browser** tab of Dimension Designer for the Customer dimension, and then click the Reconnect button on the left side of the toolbar of the designer.</span></span>  
  
3.  <span data-ttu-id="68312-229">Compruebe que `Customer Geography` está seleccionado en la lista **jerarquía** y, a continuación, en el panel explorador, expanda **todo**, **Australia**, **Nueva Gales del sur**y, a continuación, expanda **Coffs**.</span><span class="sxs-lookup"><span data-stu-id="68312-229">Verify that `Customer Geography` is selected in the **Hierarchy** list, and then in the browser pane, expand **All**, expand **Australia**, expand **New South Wales**, and then expand **Coffs Harbour**.</span></span>  
  
     <span data-ttu-id="68312-230">El explorador muestra los clientes de la ciudad.</span><span class="sxs-lookup"><span data-stu-id="68312-230">The browser displays the customers in the city.</span></span>  
  
4.  <span data-ttu-id="68312-231">Cambie al **Diseñador de cubos** para el cubo Tutorial de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="68312-231">Switch to **Cube Designer** for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span> <span data-ttu-id="68312-232">Para ello, haga doble clic en el cubo **Tutorial de Analysis Services** en el nodo **Cubos** del **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="68312-232">To do this, double-click the **Analysis Services Tutorial** cube in the **Cubes** node of **Solution Explorer**.</span></span>  
  
5.  <span data-ttu-id="68312-233">Haga clic en la pestaña **Explorador** y haga clic en el botón Volver a conectar en la barra de herramientas del diseñador.</span><span class="sxs-lookup"><span data-stu-id="68312-233">Click the **Browser** tab, and then click the Reconnect button on the toolbar of the designer.</span></span>  
  
6.  <span data-ttu-id="68312-234">En el panel **Grupo de medida** , expanda **Customer**.</span><span class="sxs-lookup"><span data-stu-id="68312-234">In the **Measure Group** pane, expand **Customer**.</span></span>  
  
     <span data-ttu-id="68312-235">Observe que, en lugar de una lista larga de atributos, debajo de Customer solamente aparecen las carpetas para mostrar y los atributos que no tienen valores de carpeta para mostrar.</span><span class="sxs-lookup"><span data-stu-id="68312-235">Notice that instead of a long list of attributes, only the display folders and the attributes that do not have display folder values appear underneath Customer.</span></span>  
  
7.  <span data-ttu-id="68312-236">En el menú **Archivo**, haga clic en **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="68312-236">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="68312-237">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="68312-237">Next Task in Lesson</span></span>  
 [<span data-ttu-id="68312-238">Modificar la dimensión Product</span><span class="sxs-lookup"><span data-stu-id="68312-238">Modifying the Product Dimension</span></span>](lesson-3-3-modifying-the-product-dimension.md)  
  
## <a name="see-also"></a><span data-ttu-id="68312-239">Consulte también</span><span class="sxs-lookup"><span data-stu-id="68312-239">See Also</span></span>  
 <span data-ttu-id="68312-240">[Referencia de propiedades de atributo de dimensión](multidimensional-models/dimension-attribute-properties-reference.md) </span><span class="sxs-lookup"><span data-stu-id="68312-240">[Dimension Attribute Properties Reference](multidimensional-models/dimension-attribute-properties-reference.md) </span></span>  
 <span data-ttu-id="68312-241">[Quitar un atributo de una dimensión](multidimensional-models/attribute-properties-remove-an-attribute-from-a-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="68312-241">[Remove an Attribute from a Dimension](multidimensional-models/attribute-properties-remove-an-attribute-from-a-dimension.md) </span></span>  
 <span data-ttu-id="68312-242">[Cambiar el nombre de un atributo](multidimensional-models/attribute-properties-rename-an-attribute.md) </span><span class="sxs-lookup"><span data-stu-id="68312-242">[Rename an Attribute](multidimensional-models/attribute-properties-rename-an-attribute.md) </span></span>  
 [<span data-ttu-id="68312-243">Definir cálculos con nombre en una vista del origen de datos &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="68312-243">Define Named Calculations in a Data Source View &#40;Analysis Services&#41;</span></span>](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md)  
  
  
