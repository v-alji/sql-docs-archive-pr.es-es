---
title: Ocultar y deshabilitar jerarquías de atributos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 095039c2-7104-414c-a9a6-327b03ce79df
author: minewiskan
ms.author: owend
ms.openlocfilehash: cc043c68d2a83424a14707799fd90bf893abc12d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751530"
---
# <a name="hiding-and-disabling-attribute-hierarchies"></a><span data-ttu-id="807ab-102">Ocultar y deshabilitar jerarquías de atributo</span><span class="sxs-lookup"><span data-stu-id="807ab-102">Hiding and Disabling Attribute Hierarchies</span></span>
  <span data-ttu-id="807ab-103">De forma predeterminada, se crea una jerarquía de atributo para cada uno de los atributos de una dimensión, y cada jerarquía está disponible para los datos de hechos de dimensionamiento.</span><span class="sxs-lookup"><span data-stu-id="807ab-103">By default, an attribute hierarchy is created for every attribute in a dimension, and each hierarchy is available for dimensioning fact data.</span></span> <span data-ttu-id="807ab-104">Esta jerarquía consta de un nivel "Todos" y un nivel de detalle que contiene todos los miembros de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="807ab-104">This hierarchy consists of an "All" level and a detail level containing all members of the hierarchy.</span></span> <span data-ttu-id="807ab-105">Como ha aprendido, puede organizar los atributos en jerarquías definidas por el usuario para proporcionar rutas de navegación en un cubo.</span><span class="sxs-lookup"><span data-stu-id="807ab-105">As you have already learned, you can organize attributes into user-defined hierarchies to provide navigation paths in a cube.</span></span> <span data-ttu-id="807ab-106">En determinadas circunstancias, le interesará deshabilitar u ocultar algunos atributos y sus jerarquías.</span><span class="sxs-lookup"><span data-stu-id="807ab-106">Under certain circumstances, you may want to disable or hide some attributes and their hierarchies.</span></span> <span data-ttu-id="807ab-107">Por ejemplo, determinados atributos, como los números de seguridad social o números de identificación nacional, sueldos, las fechas de nacimiento e información sobre el inicio de sesión, no son atributos que los usuarios vayan a utilizar para dimensionar la información del cubo.</span><span class="sxs-lookup"><span data-stu-id="807ab-107">For example, certain attributes such as social security numbers or national identification numbers, pay rates, birth dates, and login information are not attributes by which users will dimension cube information.</span></span> <span data-ttu-id="807ab-108">En lugar de ello, generalmente esta información solo se visualiza como detalles de un miembro de atributo en concreto.</span><span class="sxs-lookup"><span data-stu-id="807ab-108">Instead, this information is generally only viewed as details of a particular attribute member.</span></span> <span data-ttu-id="807ab-109">Puede ocultar estas jerarquías de atributo, dejando los atributos visibles solo como propiedades de miembro de un atributo específico.</span><span class="sxs-lookup"><span data-stu-id="807ab-109">You may want to hide these attribute hierarchies, leaving the attributes visible only as member properties of a specific attribute.</span></span> <span data-ttu-id="807ab-110">También puede hacer que los miembros de otros atributos, como los nombres de cliente o los códigos postales, solo estén visibles cuando se visualizan a través de una jerarquía de usuario en lugar de visualizarse de forma independiente a través de una jerarquía de atributo.</span><span class="sxs-lookup"><span data-stu-id="807ab-110">You may also want to make members of other attributes, such as customer names or postal codes, visible only when they are viewed through a user hierarchy instead of independently through an attribute hierarchy.</span></span> <span data-ttu-id="807ab-111">Un motivo para hacerlo puede ser el número total de miembros distintos de la jerarquía de atributo.</span><span class="sxs-lookup"><span data-stu-id="807ab-111">One reason to do so may be the sheer number of distinct members in the attribute hierarchy.</span></span> <span data-ttu-id="807ab-112">Por último, para mejorar el rendimiento del procesamiento, debe deshabilitar las jerarquías de atributos que los usuarios no utilizarán para examinar.</span><span class="sxs-lookup"><span data-stu-id="807ab-112">Finally, to improve processing performance, you should disable attribute hierarchies that users will not use for browsing.</span></span>

 <span data-ttu-id="807ab-113">El valor de la propiedad **AttributeHierarchyEnabled** determina si se ha creado una jerarquía de atributo.</span><span class="sxs-lookup"><span data-stu-id="807ab-113">The value of the **AttributeHierarchyEnabled** property determines whether an attribute hierarchy is created.</span></span> <span data-ttu-id="807ab-114">Si esta propiedad se establece en **False**, la jerarquía de atributo no se crea y el atributo no puede utilizarse como nivel en una jerarquía de usuario; la jerarquía de atributo solo existe como propiedad de miembro.</span><span class="sxs-lookup"><span data-stu-id="807ab-114">If this property is set to **False**, the attribute hierarchy is not created and the attribute cannot be used as a level in a user hierarchy; the attribute hierarchy exists as a member property only.</span></span> <span data-ttu-id="807ab-115">No obstante, una jerarquía de atributo deshabilitada puede utilizarse para ordenar los miembros de otro atributo.</span><span class="sxs-lookup"><span data-stu-id="807ab-115">However, a disabled attribute hierarchy can still be used to order the members of another attribute.</span></span> <span data-ttu-id="807ab-116">Si el valor de la propiedad **AttributeHierarchyEnabled** se establece en **True**, el valor de la propiedad **AttributeHierarchyVisible** determina si la jerarquía de atributo es visible independientemente de su uso en una jerarquía definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="807ab-116">If the value of the **AttributeHierarchyEnabled** property is set to **True**, the value of the **AttributeHierarchyVisible** property determines whether the attribute hierarchy is visible independent of its use in a user-defined hierarchy.</span></span>

 <span data-ttu-id="807ab-117">Cuando una jerarquía de atributo está habilitada, puede especificar valores para las tres propiedades adicionales siguientes:</span><span class="sxs-lookup"><span data-stu-id="807ab-117">When an attribute hierarchy is enabled, you may want to specify values for the following three additional properties:</span></span>

-   <span data-ttu-id="807ab-118">**IsAggregatable**</span><span class="sxs-lookup"><span data-stu-id="807ab-118">**IsAggregatable**</span></span>

     <span data-ttu-id="807ab-119">De forma predeterminada se define un nivel (Todos) para todas las jerarquías de atributo.</span><span class="sxs-lookup"><span data-stu-id="807ab-119">By default, an (All) level is defined for all attribute hierarchies.</span></span> <span data-ttu-id="807ab-120">Para deshabilitar el nivel (Todos) de una jerarquía de atributo habilitada, establezca el valor de esta propiedad en **False**.</span><span class="sxs-lookup"><span data-stu-id="807ab-120">To disable the (All) level for an enabled attribute hierarchy, set the value for this property to **False**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="807ab-121">Un atributo que tiene su propiedad **IsAggregatable** establecida en False solamente puede usarse como la raíz de una jerarquía definida por el usuario y debe tener un miembro predeterminado especificado (en caso contrario, el motor de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] elegirá uno).</span><span class="sxs-lookup"><span data-stu-id="807ab-121">An attribute that has its **IsAggregatable** property set to false can only be used as the root of a user-defined hierarchy and must have a default member specified (otherwise, one will be chosen for you by the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] engine).</span></span>

-   <span data-ttu-id="807ab-122">**AttributeHierarchyOrdered**</span><span class="sxs-lookup"><span data-stu-id="807ab-122">**AttributeHierarchyOrdered**</span></span>

     <span data-ttu-id="807ab-123">De forma predeterminada, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ordena los miembros de las jerarquías de atributo habilitadas durante el procesamiento y luego almacena los miembros según el valor de la propiedad **OrderBy** , como Nombre o Clave.</span><span class="sxs-lookup"><span data-stu-id="807ab-123">By default, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] orders the members of enabled attribute hierarchies during processing, and then stores the members by the value of the **OrderBy** property, such as by Name or Key.</span></span> <span data-ttu-id="807ab-124">Si el orden no le importa, puede incrementar el rendimiento del procesamiento estableciendo el valor de esta propiedad en **False**.</span><span class="sxs-lookup"><span data-stu-id="807ab-124">If you do not care about ordering, you can increase processing performance by setting the value of this property to **False**.</span></span>

-   <span data-ttu-id="807ab-125">**AttributeHierarchyOptimizedState**</span><span class="sxs-lookup"><span data-stu-id="807ab-125">**AttributeHierarchyOptimizedState**</span></span>

     <span data-ttu-id="807ab-126">De forma predeterminada, y con el objeto de mejorar el rendimiento de las consultas, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] crea durante el procesamiento un índice para cada jerarquía de atributo habilitada.</span><span class="sxs-lookup"><span data-stu-id="807ab-126">By default, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] creates an index for each enabled attribute hierarchy during processing, to improve query performance.</span></span> <span data-ttu-id="807ab-127">Si no tiene previsto utilizar una jerarquía de atributo para explorar, puede incrementar el rendimiento del procesamiento estableciendo el valor de esta propiedad en **NotOptimized**.</span><span class="sxs-lookup"><span data-stu-id="807ab-127">If you do not plan to use an attribute hierarchy for browsing, you can increase processing performance by setting the value of this property to **NotOptimized**.</span></span> <span data-ttu-id="807ab-128">No obstante, si utiliza una jerarquía oculta como atributo clave para la dimensión, el rendimiento también mejorará si crea un índice de los miembros del atributo.</span><span class="sxs-lookup"><span data-stu-id="807ab-128">However, if you use a hidden hierarchy as the key attribute for the dimension, creating an index of the attribute members will still improve performance.</span></span>

 <span data-ttu-id="807ab-129">Estas propiedades no se aplican si la jerarquía de atributo está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="807ab-129">These properties do not apply if an attribute hierarchy is disabled.</span></span>

 <span data-ttu-id="807ab-130">En las tareas de este tema, deshabilitará los números de seguridad social y otros atributos en la dimensión Employee que no se utilizarán para examinar.</span><span class="sxs-lookup"><span data-stu-id="807ab-130">In the tasks in this topic, you will disable social security numbers and other attributes in the Employee dimension that will not be used for browsing.</span></span> <span data-ttu-id="807ab-131">Luego ocultará las jerarquías de atributo de nombre de cliente y código postal en la dimensión Customer.</span><span class="sxs-lookup"><span data-stu-id="807ab-131">You will then hide the customer name and postal code attribute hierarchies in the Customer dimension.</span></span> <span data-ttu-id="807ab-132">Debido al elevado número de miembros de atributo de estas jerarquías, examinarlas será un proceso muy lento, independientemente de la jerarquía de usuario que utilice.</span><span class="sxs-lookup"><span data-stu-id="807ab-132">The large number of attribute members in these hierarchies will make browsing these hierarchies very slow independent of a user hierarchy.</span></span>

## <a name="setting-attribute-hierarchy-properties-in-the-employee-dimension"></a><span data-ttu-id="807ab-133">Establecer las propiedades de la jerarquía de atributo en la dimensión Employee</span><span class="sxs-lookup"><span data-stu-id="807ab-133">Setting Attribute Hierarchy Properties in the Employee Dimension</span></span>

1.  <span data-ttu-id="807ab-134">Cambie al Diseñador de dimensiones para la dimensión Employee y haga clic en la pestaña **Explorador** .</span><span class="sxs-lookup"><span data-stu-id="807ab-134">Switch to Dimension Designer for the Employee dimension, and then click the **Browser** tab.</span></span>

2.  <span data-ttu-id="807ab-135">Compruebe que las jerarquías de atributo siguientes aparecen en la lista **Jerarquía** :</span><span class="sxs-lookup"><span data-stu-id="807ab-135">Verify that the following attribute hierarchies appear in the **Hierarchy** list:</span></span>

    -   <span data-ttu-id="807ab-136">**Base Rate**</span><span class="sxs-lookup"><span data-stu-id="807ab-136">**Base Rate**</span></span>

    -   <span data-ttu-id="807ab-137">**Fecha de nacimiento**</span><span class="sxs-lookup"><span data-stu-id="807ab-137">**Birth Date**</span></span>

    -   <span data-ttu-id="807ab-138">**Id. de inicio de sesión**</span><span class="sxs-lookup"><span data-stu-id="807ab-138">**Login ID**</span></span>

    -   <span data-ttu-id="807ab-139">**Número de seguridad social del director**</span><span class="sxs-lookup"><span data-stu-id="807ab-139">**Manager SSN**</span></span>

    -   <span data-ttu-id="807ab-140">**S.S.**</span><span class="sxs-lookup"><span data-stu-id="807ab-140">**SSN**</span></span>

3.  <span data-ttu-id="807ab-141">Vaya a la pestaña **Estructura de dimensión** y seleccione los atributos siguientes en el panel **Atributos** .</span><span class="sxs-lookup"><span data-stu-id="807ab-141">Switch to the **Dimension Structure** tab, and then select the following attributes in the **Attributes** pane.</span></span> <span data-ttu-id="807ab-142">Para seleccionar varias medidas, haga clic en cada una de ellas mientras mantiene presionada la tecla CTRL:</span><span class="sxs-lookup"><span data-stu-id="807ab-142">You can select multiple measures by clicking each while holding down the CTRL key:</span></span>

    -   <span data-ttu-id="807ab-143">**Base Rate**</span><span class="sxs-lookup"><span data-stu-id="807ab-143">**Base Rate**</span></span>

    -   <span data-ttu-id="807ab-144">**Fecha de nacimiento**</span><span class="sxs-lookup"><span data-stu-id="807ab-144">**Birth Date**</span></span>

    -   <span data-ttu-id="807ab-145">**Id. de inicio de sesión**</span><span class="sxs-lookup"><span data-stu-id="807ab-145">**Login ID**</span></span>

    -   <span data-ttu-id="807ab-146">**Número de seguridad social del director**</span><span class="sxs-lookup"><span data-stu-id="807ab-146">**Manager SSN**</span></span>

    -   <span data-ttu-id="807ab-147">**S.S.**</span><span class="sxs-lookup"><span data-stu-id="807ab-147">**SSN**</span></span>

4.  <span data-ttu-id="807ab-148">En la ventana Propiedades, establezca el valor de la propiedad **AttributeHierarchyEnabled** en **False** para los atributos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="807ab-148">In the Properties window, set the value of the **AttributeHierarchyEnabled** property to **False** for the selected attributes.</span></span>

     <span data-ttu-id="807ab-149">Observe que, en el panel **Atributos** , el icono de cada atributo ha cambiado para indicar que el atributo no está habilitado.</span><span class="sxs-lookup"><span data-stu-id="807ab-149">Notice in the **Attributes** pane that the icon for each attribute has changed to indicate that the attribute is not enabled.</span></span>

     <span data-ttu-id="807ab-150">En la imagen siguiente se muestra la propiedad **AttributeHierarchyEnabled** establecida en False para los atributos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="807ab-150">The following image shows the **AttributeHierarchyEnabled** property set to False for the selected attributes.</span></span>

     <span data-ttu-id="807ab-151">![Propiedad AttributeHierarchyEnabled establecida en False](../../2014/tutorials/media/l4-hierarchyenabled-1.gif "Propiedad AttributeHierarchyEnabled establecida en False")</span><span class="sxs-lookup"><span data-stu-id="807ab-151">![AttributeHierarchyEnabled property set to False](../../2014/tutorials/media/l4-hierarchyenabled-1.gif "AttributeHierarchyEnabled property set to False")</span></span>

5.  <span data-ttu-id="807ab-152">En el menú **Compilar** , haga clic en **Tutorial de Implementar Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="807ab-152">On the **Build** menu, click **Deploy Analysis Services Tutorial**.</span></span>

6.  <span data-ttu-id="807ab-153">Cuando el proceso haya finalizado correctamente, diríjase a la pestaña **Explorador** , haga clic en **Volver a conectar**y, a continuación, intente examinar las jerarquías de atributo modificadas.</span><span class="sxs-lookup"><span data-stu-id="807ab-153">When processing has successfully completed, switch to the **Browser** tab, click **Reconnect**, and then try to browse the modified attribute hierarchies.</span></span>

     <span data-ttu-id="807ab-154">Observe que los miembros de los atributos modificados no están disponibles para examinar como jerarquías de atributo en la lista **Jerarquía** .</span><span class="sxs-lookup"><span data-stu-id="807ab-154">Notice that the members of the modified attributes are not available for browsing as attribute hierarchies in the **Hierarchy** list.</span></span> <span data-ttu-id="807ab-155">Si intenta agregar una de las jerarquías de atributo deshabilitadas como nivel en una jerarquía de usuario, recibirá un error en el que se le notificará que debe habilitar la jerarquía de atributo para que ésta pueda participar en una jerarquía definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="807ab-155">If you try to add one of the disabled attribute hierarchies as a level in a user hierarchy, you will receive an error notifying you that the attribute hierarchy must be enabled to participate in a user-defined hierarchy.</span></span>

## <a name="setting-attribute-hierarchy-properties-in-the-customer-dimension"></a><span data-ttu-id="807ab-156">Establecer las propiedades de la jerarquía de atributo en la dimensión Customer</span><span class="sxs-lookup"><span data-stu-id="807ab-156">Setting Attribute Hierarchy Properties in the Customer Dimension</span></span>

1.  <span data-ttu-id="807ab-157">Cambie al Diseñador de dimensiones para la dimensión Customer y haga clic en la pestaña **Explorador** .</span><span class="sxs-lookup"><span data-stu-id="807ab-157">Switch to Dimension Designer for the Customer dimension, and then click the **Browser** tab.</span></span>

2.  <span data-ttu-id="807ab-158">Compruebe que las jerarquías de atributo siguientes aparecen en la lista **Jerarquía** :</span><span class="sxs-lookup"><span data-stu-id="807ab-158">Verify that the following attribute hierarchies appear in the **Hierarchy** list:</span></span>

    -   <span data-ttu-id="807ab-159">**Nombre completo**</span><span class="sxs-lookup"><span data-stu-id="807ab-159">**Full Name**</span></span>

    -   <span data-ttu-id="807ab-160">**Código postal**</span><span class="sxs-lookup"><span data-stu-id="807ab-160">**Postal Code**</span></span>

3.  <span data-ttu-id="807ab-161">Cambie a la pestaña **Estructura de dimensión** y seleccione los atributos siguientes en el panel **Atributos** (utilice la tecla CTRL si desea seleccionar varios atributos al mismo tiempo):</span><span class="sxs-lookup"><span data-stu-id="807ab-161">Switch to the **Dimension Structure** tab, and then select the following attributes in the **Attributes** pane by using the CTRL key to select multiple attributes at the same time:</span></span>

    -   <span data-ttu-id="807ab-162">**Nombre completo**</span><span class="sxs-lookup"><span data-stu-id="807ab-162">**Full Name**</span></span>

    -   <span data-ttu-id="807ab-163">**Código postal**</span><span class="sxs-lookup"><span data-stu-id="807ab-163">**Postal Code**</span></span>

4.  <span data-ttu-id="807ab-164">En la ventana Propiedades, establezca el valor de la propiedad **AttributeHierarchyVisible** en **False** para los atributos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="807ab-164">In the Properties window, set the value of the **AttributeHierarchyVisible** property to **False** for the selected attributes.</span></span>

     <span data-ttu-id="807ab-165">Puesto que los miembros de estas jerarquías de atributo se utilizarán para dimensionar datos de hechos, si ordena y optimiza dichos miembros, mejorará el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="807ab-165">Because the members of these attribute hierarchies will be used for dimensioning fact data, ordering and optimizing the members of these attribute hierarchies will improve performance.</span></span> <span data-ttu-id="807ab-166">Por consiguiente, las propiedades de estos atributos no deben cambiarse.</span><span class="sxs-lookup"><span data-stu-id="807ab-166">Therefore, the properties of these attributes should not be changed.</span></span>

     <span data-ttu-id="807ab-167">En la imagen siguiente se muestra la propiedad **AttributeHierarchyVisible** establecida en False.</span><span class="sxs-lookup"><span data-stu-id="807ab-167">The following image shows the **AttributeHierarchyVisible** property set to False.</span></span>

     <span data-ttu-id="807ab-168">![Propiedad AttributeHierarchyVisible establecida en False](../../2014/tutorials/media/l4-hierarchyvisible-1.gif "Propiedad AttributeHierarchyVisible establecida en False")</span><span class="sxs-lookup"><span data-stu-id="807ab-168">![AttributeHierarchyVisible property set to False](../../2014/tutorials/media/l4-hierarchyvisible-1.gif "AttributeHierarchyVisible property set to False")</span></span>

5.  <span data-ttu-id="807ab-169">Arrastre el atributo **Postal Code** del panel **Atributos** a la jerarquía de usuario **Customer Geography** en el panel **Jerarquías y niveles** que se encuentra justo en el nivel **City** .</span><span class="sxs-lookup"><span data-stu-id="807ab-169">Drag the **Postal Code** attribute from the **Attributes** pane into the **Customer Geography** user hierarchy in the **Hierarchies and Levels** pane, immediately under the **City** level.</span></span>

     <span data-ttu-id="807ab-170">Observe que el atributo oculto puede seguir convirtiéndose en un nivel de una jerarquía de usuario.</span><span class="sxs-lookup"><span data-stu-id="807ab-170">Notice that a hidden attribute can still become a level in a user hierarchy.</span></span>

6.  <span data-ttu-id="807ab-171">En el menú **Compilar** , haga clic en **Tutorial de Implementar Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="807ab-171">On the **Build** menu, click **Deploy Analysis Services Tutorial**.</span></span>

7.  <span data-ttu-id="807ab-172">Cuando la implementación haya finalizado correctamente, vaya a la pestaña **Explorador** de la dimensión Customer y haga clic en **Volver a conectar**.</span><span class="sxs-lookup"><span data-stu-id="807ab-172">When deployment has successfully completed, switch to the **Browser** tab for the Customer dimension, and then click **Reconnect**.</span></span>

8.  <span data-ttu-id="807ab-173">Intente seleccionar cualquiera de las jerarquías de atributo modificadas en la lista **Jerarquía** .</span><span class="sxs-lookup"><span data-stu-id="807ab-173">Try to select either of the modified attribute hierarchies from the **Hierarchy** list.</span></span>

     <span data-ttu-id="807ab-174">Observe que ninguna de las jerarquías de atributo modificadas aparece en la lista **Jerarquía** .</span><span class="sxs-lookup"><span data-stu-id="807ab-174">Notice that neither of the modified attribute hierarchies appears in the **Hierarchy** list.</span></span>

9. <span data-ttu-id="807ab-175">En la lista **Jerarquía** , seleccione **Customer Geography**y examine cada nivel del panel del explorador.</span><span class="sxs-lookup"><span data-stu-id="807ab-175">In the **Hierarchy** list, select **Customer Geography**, and then browse each level in the browser pane.</span></span>

     <span data-ttu-id="807ab-176">Observe que los niveles ocultos, **Código postal** y **Nombre completo**, están visibles en la jerarquía definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="807ab-176">Notice that the hidden levels, **Postal Code** and **Full Name**, are visible in the user-defined hierarchy.</span></span>

## <a name="next-task-in-lesson"></a><span data-ttu-id="807ab-177">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="807ab-177">Next Task in Lesson</span></span>
 [<span data-ttu-id="807ab-178">Ordenar los miembros de atributo en función de un atributo secundario</span><span class="sxs-lookup"><span data-stu-id="807ab-178">Sorting Attribute Members Based on a Secondary Attribute</span></span>](lesson-4-5-sorting-attribute-members-based-on-a-secondary-attribute.md)


