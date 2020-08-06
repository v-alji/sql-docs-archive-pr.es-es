---
title: Definir propiedades de atributo primario en una jerarquía de elementos primarios y secundarios | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2d78fa73-a13b-4e12-bbd0-43e5307f760c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1dfa4340bdc161809cf3821e5cb1f0609399e1d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674416"
---
# <a name="defining-parent-attribute-properties-in-a-parent-child-hierarchy"></a><span data-ttu-id="fb3a1-102">Definir propiedades de atributo primario en una jerarquía de elementos primarios y secundarios</span><span class="sxs-lookup"><span data-stu-id="fb3a1-102">Defining Parent Attribute Properties in a Parent-Child Hierarchy</span></span>
  <span data-ttu-id="fb3a1-103">Una jerarquía de elementos primarios y secundarios es una jerarquía de una dimensión que está basada en dos columnas de tabla.</span><span class="sxs-lookup"><span data-stu-id="fb3a1-103">A parent-child hierarchy is a hierarchy in a dimension that is based on two table columns.</span></span> <span data-ttu-id="fb3a1-104">La combinación de estas columnas define las relaciones jerárquicas entre los miembros de dimensión.</span><span class="sxs-lookup"><span data-stu-id="fb3a1-104">Together, these columns define the hierarchical relationships among the members of the dimension.</span></span> <span data-ttu-id="fb3a1-105">La primera columna, denominada *columna de claves de miembro*, identifica a cada miembro de dimensión.</span><span class="sxs-lookup"><span data-stu-id="fb3a1-105">The first column, called the *member key column*, identifies each dimension member.</span></span> <span data-ttu-id="fb3a1-106">La otra columna, denominada *columna principal*, identifica al elemento principal de cada miembro de dimensión.</span><span class="sxs-lookup"><span data-stu-id="fb3a1-106">The other column, called the *parent column*, identifies the parent of each dimension member.</span></span> <span data-ttu-id="fb3a1-107">La propiedad **NamingTemplate** de un atributo primario determina el nombre de cada nivel en la jerarquía de elementos primarios y secundarios, y la propiedad **MembersWithData** determina si deben mostrarse los datos de los miembros primarios.</span><span class="sxs-lookup"><span data-stu-id="fb3a1-107">The **NamingTemplate** property of a parent attribute determines the name of each level in the parent-child hierarchy, and the **MembersWithData** property determines whether data for parent members should be displayed.</span></span>

 <span data-ttu-id="fb3a1-108">Para obtener más información, vea jerarquía de elementos [primarios y secundarios](multidimensional-models/parent-child-dimension.md), [atributos en jerarquías de elementos primarios y secundarios](multidimensional-models/parent-child-dimension-attributes.md) .</span><span class="sxs-lookup"><span data-stu-id="fb3a1-108">For more information, see [Parent-Child Hierarchy](multidimensional-models/parent-child-dimension.md), [Attributes in Parent-Child Hierarchies](multidimensional-models/parent-child-dimension-attributes.md)</span></span>

> [!NOTE]
>  <span data-ttu-id="fb3a1-109">Cuando se utiliza el Asistente para dimensiones con objeto de crear una dimensión, el asistente reconoce las tablas que incluyen relaciones de elementos primarios y secundarios, y define automáticamente la jerarquía de elementos primarios y secundarios.</span><span class="sxs-lookup"><span data-stu-id="fb3a1-109">When you use the Dimension Wizard to create a dimension, the wizard recognizes the tables that have parent-child relationships and automatically defines the parent-child hierarchy for you.</span></span>

 <span data-ttu-id="fb3a1-110">En las tareas de este tema, creará una plantilla de asignación de nombres que define el nombre para cada nivel en la jerarquía de elementos primarios y secundarios de la dimensión **Employee** .</span><span class="sxs-lookup"><span data-stu-id="fb3a1-110">In the tasks in this topic, you will create a naming template that defines the name for each level in the parent-child hierarchy in the **Employee** dimension.</span></span> <span data-ttu-id="fb3a1-111">A continuación, configurará el atributo primario para ocultar todos los datos primarios, de modo que solo se muestren las ventas de los miembros del nivel de hoja.</span><span class="sxs-lookup"><span data-stu-id="fb3a1-111">You will then configure the parent attribute to hide all parent data, so that only the sales for leaf-level members are displayed.</span></span>

## <a name="browsing-the-employee-dimension"></a><span data-ttu-id="fb3a1-112">Examinar la dimensión Employee</span><span class="sxs-lookup"><span data-stu-id="fb3a1-112">Browsing the Employee Dimension</span></span>

1.  <span data-ttu-id="fb3a1-113">En el Explorador de soluciones, haga doble clic en **Employee.dim** en la carpeta **Dimensiones** para abrir el Diseñador de dimensiones para la dimensión Employee.</span><span class="sxs-lookup"><span data-stu-id="fb3a1-113">In Solution Explorer, double-click **Employee.dim** in the **Dimensions** folder to open Dimension Designer for the Employee dimension.</span></span>

2.  <span data-ttu-id="fb3a1-114">Haga clic en la pestaña **Explorador** , compruebe que **Employees** está seleccionado en la lista **Jerarquía** y, después, expanda el miembro **All Employees** .</span><span class="sxs-lookup"><span data-stu-id="fb3a1-114">Click the **Browser** tab, verify that **Employees** is selected in the **Hierarchy** list, and then expand the **All Employees** member.</span></span>

     <span data-ttu-id="fb3a1-115">Observe que **Ken J. Sánchez** es el director de nivel superior de esta jerarquía de elementos primarios y secundarios.</span><span class="sxs-lookup"><span data-stu-id="fb3a1-115">Notice that **Ken J. Sánchez** is the top-level manager in this parent-child hierarchy.</span></span>

3.  <span data-ttu-id="fb3a1-116">Seleccione el miembro **Ken J. Sánchez** .</span><span class="sxs-lookup"><span data-stu-id="fb3a1-116">Select the **Ken J. Sánchez** member.</span></span>

     <span data-ttu-id="fb3a1-117">Observe que el nombre de nivel para este miembro es **Level 02**.</span><span class="sxs-lookup"><span data-stu-id="fb3a1-117">Notice that the level name for this member is **Level 02**.</span></span> <span data-ttu-id="fb3a1-118">(El nombre de nivel aparece después de **Nivel actual:** , justo encima del miembro **All Employees** .) En esta tarea, definirá nombres más descriptivos para cada nivel.</span><span class="sxs-lookup"><span data-stu-id="fb3a1-118">(The level name appears after **Current level:** immediately above the **All Employees** member.) In the next task, you will define more descriptive names for each level.</span></span>

4.  <span data-ttu-id="fb3a1-119">Expanda **Ken J. Sánchez** para ver los nombres de los empleados que informan a este director y, después, seleccione **Brian S. Welcker** para ver el nombre de este nivel.</span><span class="sxs-lookup"><span data-stu-id="fb3a1-119">Expand **Ken J. Sánchez** to view the names of the employees who report to this manager, and then select **Brian S. Welcker** to view the name of this level.</span></span>

     <span data-ttu-id="fb3a1-120">Observe que el nombre de nivel para este miembro es **Level 03**.</span><span class="sxs-lookup"><span data-stu-id="fb3a1-120">Notice that the level name for this member is **Level 03**.</span></span>

5.  <span data-ttu-id="fb3a1-121">En el Explorador de soluciones, haga doble clic en **Analysis Services Tutorial.cube** en la carpeta **Cubos** para abrir el Diseñador de cubos para el cubo Tutorial de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fb3a1-121">In Solution Explorer, double-click **Analysis Services Tutorial.cube** in the **Cubes** folder to open Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span>

6.  <span data-ttu-id="fb3a1-122">Haga clic en la pestaña **Explorador** .</span><span class="sxs-lookup"><span data-stu-id="fb3a1-122">Click the **Browser** tab.</span></span>

7.  <span data-ttu-id="fb3a1-123">Haga clic en el icono de Excel y, después, haga clic en **Habilitar** cuando se le pida que habilite las conexiones.</span><span class="sxs-lookup"><span data-stu-id="fb3a1-123">Click the Excel icon, and then click **Enable** when prompted to enable connections.</span></span>

8.  <span data-ttu-id="fb3a1-124">En la Lista de campos de tabla dinámica, expanda **Reseller Sales**.</span><span class="sxs-lookup"><span data-stu-id="fb3a1-124">In the PivotTable Field List, expand **Reseller Sales**.</span></span> <span data-ttu-id="fb3a1-125">Arrastre **Reseller Sales-Sales Amount** hasta el área Valores.</span><span class="sxs-lookup"><span data-stu-id="fb3a1-125">Drag **Reseller Sales-Sales Amount** to the Values area.</span></span>

9. <span data-ttu-id="fb3a1-126">En la Lista de campos de tabla dinámica, expanda **Employee**, y arrastre la jerarquía **Employees** hasta el área **Filas** .</span><span class="sxs-lookup"><span data-stu-id="fb3a1-126">In the PivotTable Field List, expand **Employee**, and then drag the **Employees** hierarchy to the **Rows** area.</span></span>

     <span data-ttu-id="fb3a1-127">Todos los miembros de la jerarquía Employees se agregarán a la columna A del informe de tabla dinámica.</span><span class="sxs-lookup"><span data-stu-id="fb3a1-127">All the members of the Employees hierarchy are added to column A of the PivotTable report.</span></span>

     <span data-ttu-id="fb3a1-128">En la ilustración siguiente se muestra expandida la jerarquía Employees.</span><span class="sxs-lookup"><span data-stu-id="fb3a1-128">The following image shows the Employees hierarchy expanded.</span></span>

10. <span data-ttu-id="fb3a1-129">![Tabla dinámica que muestra la jerarquía Employees](../../2014/tutorials/media/l4-employee-1.gif "Tabla dinámica que muestra la jerarquía Employees")</span><span class="sxs-lookup"><span data-stu-id="fb3a1-129">![PivotTable showing Employees hierarchy](../../2014/tutorials/media/l4-employee-1.gif "PivotTable showing Employees hierarchy")</span></span>

     <span data-ttu-id="fb3a1-130">Observe que las ventas realizadas por cada director del nivel 03 también se muestran en el nivel 04.</span><span class="sxs-lookup"><span data-stu-id="fb3a1-130">Notice that the sales made by each manager in Level 03 are also displayed in Level 04.</span></span> <span data-ttu-id="fb3a1-131">Esto es así porque cada director también es un empleado de otro director.</span><span class="sxs-lookup"><span data-stu-id="fb3a1-131">This is because each manager is also an employee of another manager.</span></span> <span data-ttu-id="fb3a1-132">En la tarea siguiente, ocultará estos importes de ventas.</span><span class="sxs-lookup"><span data-stu-id="fb3a1-132">In the next task, you will hide these sale amounts.</span></span>

## <a name="modifying-parent-attribute-properties-in-the-employee-dimension"></a><span data-ttu-id="fb3a1-133">Modificar las propiedades de los atributos primarios en la dimensión Employee</span><span class="sxs-lookup"><span data-stu-id="fb3a1-133">Modifying Parent Attribute Properties in the Employee Dimension</span></span>

1.  <span data-ttu-id="fb3a1-134">Cambie al Diseñador de dimensiones para la dimensión **Employee** .</span><span class="sxs-lookup"><span data-stu-id="fb3a1-134">Switch to Dimension Designer for the **Employee** dimension.</span></span>

2.  <span data-ttu-id="fb3a1-135">Haga clic en la pestaña **Estructura de dimensión** , y, después, seleccione la jerarquía de atributo **Employees** en el panel **Atributos** .</span><span class="sxs-lookup"><span data-stu-id="fb3a1-135">Click the **Dimension Structure** tab, and then select the **Employees** attribute hierarchy in the **Attributes** pane.</span></span>

     <span data-ttu-id="fb3a1-136">Observe el icono único de este atributo.</span><span class="sxs-lookup"><span data-stu-id="fb3a1-136">Notice the unique icon for this attribute.</span></span> <span data-ttu-id="fb3a1-137">Este icono significa que el atributo es la clave principal de una jerarquía de elementos primarios y secundarios.</span><span class="sxs-lookup"><span data-stu-id="fb3a1-137">This icon signifies that the attribute is the parent key in a parent-child hierarchy.</span></span> <span data-ttu-id="fb3a1-138">Observe también que, en la ventana Propiedades, la propiedad **Usage** del atributo está definida como **Primaria**.</span><span class="sxs-lookup"><span data-stu-id="fb3a1-138">Notice also, in the Properties window, that the **Usage** property for the attribute is defined as **Parent**.</span></span> <span data-ttu-id="fb3a1-139">Esta propiedad se estableció con el Asistente para dimensiones cuando se diseñó la dimensión.</span><span class="sxs-lookup"><span data-stu-id="fb3a1-139">This property was set by the Dimension Wizard when the dimension was designed.</span></span> <span data-ttu-id="fb3a1-140">El asistente detectó automáticamente la relación de elementos primarios y secundarios.</span><span class="sxs-lookup"><span data-stu-id="fb3a1-140">The wizard automatically detected the parent-child relationship.</span></span>

3.  <span data-ttu-id="fb3a1-141">En la ventana Propiedades, haga clic en el botón de puntos suspensivos (**...**) de la celda de la propiedad **NamingTemplate** .</span><span class="sxs-lookup"><span data-stu-id="fb3a1-141">In the Properties window, click the ellipsis button (**...**) in the **NamingTemplate** property cell.</span></span>

     <span data-ttu-id="fb3a1-142">En el cuadro de diálogo **Plantilla de asignación de nombres de nivel** , debe definir la plantilla de asignación de nombres de nivel que determina los nombres de nivel de la jerarquía de elementos primarios y secundarios que se muestran a los usuarios cuando examinan los cubos.</span><span class="sxs-lookup"><span data-stu-id="fb3a1-142">In the **Level Naming Template** dialog box, you define the level naming template that determines the level names in the parent-child hierarchy that are displayed to users as they browse cubes.</span></span>

4.  <span data-ttu-id="fb3a1-143">En la segunda fila, la **\*** fila, escriba **Employee \* LEVEL** en la columna **nombre** y, a continuación, haga clic en la tercera fila.</span><span class="sxs-lookup"><span data-stu-id="fb3a1-143">In the second row, the **\*** row, type **Employee Level \*** in the **Name** column, and then click the third row.</span></span>

     <span data-ttu-id="fb3a1-144">Observe que, bajo **Resultado** , cada nivel ahora se denominará "Employee Level" seguido por un número que aumenta de forma secuencial.</span><span class="sxs-lookup"><span data-stu-id="fb3a1-144">Notice under **Result** that each level will now be named "Employee Level" followed by a sequentially increasing number.</span></span>

     <span data-ttu-id="fb3a1-145">En la imagen siguiente se muestran los cambios realizados en el cuadro de diálogo **Plantilla de asignación de nombres de nivel** .</span><span class="sxs-lookup"><span data-stu-id="fb3a1-145">The following image shows the changes in the **Level Naming Template** dialog box.</span></span>

     <span data-ttu-id="fb3a1-146">![Cuadro de diálogo plantilla de asignación de nombres de nivel](../../2014/tutorials/media/l4-namingtemplate.gif "Cuadro de diálogo Plantilla de asignación de nombres de nivel")</span><span class="sxs-lookup"><span data-stu-id="fb3a1-146">![Level Naming Template dialog box](../../2014/tutorials/media/l4-namingtemplate.gif "Level Naming Template dialog box")</span></span>

5.  <span data-ttu-id="fb3a1-147">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb3a1-147">Click **OK**.</span></span>

6.  <span data-ttu-id="fb3a1-148">En la ventana Propiedades del atributo **Employees** , en la celda de la propiedad **MembersWithData** , seleccione **NonLeafDataHidden** para cambiar este valor por el atributo **Employees** .</span><span class="sxs-lookup"><span data-stu-id="fb3a1-148">In the Properties window for the **Employees** attribute, in the **MembersWithData** property cell, select **NonLeafDataHidden** to change this value for the **Employees** attribute.</span></span>

     <span data-ttu-id="fb3a1-149">De este modo se ocultarán los datos relacionados con los miembros no hoja de la jerarquía de elementos primarios y secundarios.</span><span class="sxs-lookup"><span data-stu-id="fb3a1-149">This will cause data that is related to non-leaf level members in the parent-child hierarchy to be hidden.</span></span>

## <a name="browsing-the-employee-dimension-with-the-modified-attributes"></a><span data-ttu-id="fb3a1-150">Examinar la dimensión Employee con los atributos modificados</span><span class="sxs-lookup"><span data-stu-id="fb3a1-150">Browsing the Employee Dimension with the Modified Attributes</span></span>

1.  <span data-ttu-id="fb3a1-151">En el menú **Generar** de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], haga clic en **Implementar Tutorial de Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="fb3a1-151">On the **Build** menu of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click **Deploy Analysis Services Tutorial**.</span></span>

2.  <span data-ttu-id="fb3a1-152">Cuando la implementación se haya completado correctamente, cambie al Diseñador de cubos para el cubo Tutorial de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] y haga clic en **Volver a conectar** en la pestaña **Explorador** .</span><span class="sxs-lookup"><span data-stu-id="fb3a1-152">When deployment has successfully completed, switch to Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click **Reconnect** on the toolbar of the **Browser** tab.</span></span>

3.  <span data-ttu-id="fb3a1-153">Haga clic en el icono de Excel y, a continuación, haga clic en **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="fb3a1-153">Click the Excel icon, and then click **Enable**.</span></span>

4.  <span data-ttu-id="fb3a1-154">Arrastre **Reseller Sales-Sales Amount** hasta el área Valores.</span><span class="sxs-lookup"><span data-stu-id="fb3a1-154">Drag **Reseller Sales-Sales Amount** to the Values area.</span></span>

5.  <span data-ttu-id="fb3a1-155">Arrastre la jerarquía **Employees** hasta el área Etiquetas de fila.</span><span class="sxs-lookup"><span data-stu-id="fb3a1-155">Drag the **Employees** hierarchy to the Row Labels area.</span></span>

     <span data-ttu-id="fb3a1-156">En la imagen siguiente se muestran los cambios realizados en la jerarquía Employees.</span><span class="sxs-lookup"><span data-stu-id="fb3a1-156">The following image shows the changes that you made to the Employees hierarchy.</span></span> <span data-ttu-id="fb3a1-157">Observe que Stephen Y. Jiang ya no aparece como empleado de sí mismo.</span><span class="sxs-lookup"><span data-stu-id="fb3a1-157">Notice that Stephen Y. Jiang no longer appears as an employee of himself.</span></span>

     <span data-ttu-id="fb3a1-158">![Jerarquía Employees modificada](../../2014/tutorials/media/l4-employee-2.png "Jerarquía Employees modificada")</span><span class="sxs-lookup"><span data-stu-id="fb3a1-158">![Modified Employees hierarchy](../../2014/tutorials/media/l4-employee-2.png "Modified Employees hierarchy")</span></span>

## <a name="next-task-in-lesson"></a><span data-ttu-id="fb3a1-159">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="fb3a1-159">Next Task in Lesson</span></span>
 [<span data-ttu-id="fb3a1-160">Agrupar miembros de atributo automáticamente</span><span class="sxs-lookup"><span data-stu-id="fb3a1-160">Automatically Grouping Attribute Members</span></span>](lesson-4-3-automatically-grouping-attribute-members.md)

## <a name="see-also"></a><span data-ttu-id="fb3a1-161">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fb3a1-161">See Also</span></span>
 <span data-ttu-id="fb3a1-162">Atributos de [la jerarquía de elementos primarios y secundarios](multidimensional-models/parent-child-dimension.md) [en las jerarquías de elementos primarios y secundarios](multidimensional-models/parent-child-dimension-attributes.md)</span><span class="sxs-lookup"><span data-stu-id="fb3a1-162">[Parent-Child Hierarchy](multidimensional-models/parent-child-dimension.md) [Attributes in Parent-Child Hierarchies](multidimensional-models/parent-child-dimension-attributes.md)</span></span>


