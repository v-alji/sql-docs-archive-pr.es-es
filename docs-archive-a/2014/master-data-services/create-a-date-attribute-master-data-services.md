---
title: Crear un atributo de fecha (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- creating date attributes [Master Data Services]
- attributes [Master Data Services], creating date attributes
ms.assetid: 22a8f1a3-b4f2-4cfa-8495-7daad5ce9d12
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 93797b90ff03c6a2b60ce8e015897a46a7448aad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662146"
---
# <a name="create-a-date-attribute-master-data-services"></a><span data-ttu-id="7592b-102">Crear un atributo de fecha (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="7592b-102">Create a Date Attribute (Master Data Services)</span></span>
  <span data-ttu-id="7592b-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], cree un atributo de fecha cuando desee que los usuarios escriban una fecha como un valor de atributo.</span><span class="sxs-lookup"><span data-stu-id="7592b-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a date attribute when you want users to enter a date as an attribute value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7592b-104">El atributo se denomina DateTime, pero los valores de hora no se admiten.</span><span class="sxs-lookup"><span data-stu-id="7592b-104">The attribute is called DateTime, but time values are not supported.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7592b-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="7592b-105">Prerequisites</span></span>  
 <span data-ttu-id="7592b-106">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="7592b-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="7592b-107">Debe disponer de permiso para tener acceso al área funcional de **Administración del sistema** .</span><span class="sxs-lookup"><span data-stu-id="7592b-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="7592b-108">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="7592b-108">You must be a model administrator.</span></span> <span data-ttu-id="7592b-109">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="7592b-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="7592b-110">Debe tener una entidad para la que crear el atributo.</span><span class="sxs-lookup"><span data-stu-id="7592b-110">You must have an entity to create the attribute for.</span></span> <span data-ttu-id="7592b-111">Para obtener más información, vea [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="7592b-111">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-create-a-date-attribute"></a><span data-ttu-id="7592b-112">Crear un atributo de fecha</span><span class="sxs-lookup"><span data-stu-id="7592b-112">To create a date attribute</span></span>  
  
1.  <span data-ttu-id="7592b-113">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="7592b-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="7592b-114">En la página **Vista de modelo** , en la barra de menús, seleccione **Administrar** y haga clic en **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="7592b-114">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="7592b-115">En la página **Mantenimiento de entidades** , en la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="7592b-115">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="7592b-116">Seleccione la fila para la entidad para la que desea crear un atributo.</span><span class="sxs-lookup"><span data-stu-id="7592b-116">Select the row for the entity that you want to create an attribute for.</span></span>  
  
5.  <span data-ttu-id="7592b-117">Haga clic en **Editar entidad seleccionada**.</span><span class="sxs-lookup"><span data-stu-id="7592b-117">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="7592b-118">En la página **Editar entidad** :</span><span class="sxs-lookup"><span data-stu-id="7592b-118">On the **Edit Entity** page:</span></span>  
  
    -   <span data-ttu-id="7592b-119">Si el atributo es para miembros hoja, en el panel **Atributos de miembro hoja** , haga clic en **Agregar atributo hoja**.</span><span class="sxs-lookup"><span data-stu-id="7592b-119">If the attribute is for leaf members, in the **Leaf member attributes** pane, click **Add leaf attribute**.</span></span>  
  
    -   <span data-ttu-id="7592b-120">Si el atributo es para miembros consolidados, en el panel **Atributos de miembro consolidados** , haga clic en **Agregar atributo consolidado**.</span><span class="sxs-lookup"><span data-stu-id="7592b-120">If the attribute is for consolidated members, in the **Consolidated member attributes** pane, click **Add consolidated attribute**.</span></span>  
  
    -   <span data-ttu-id="7592b-121">Si el atributo es para colecciones, en el panel **Atributos de colección** , haga clic en **Agregar atributo de colección**.</span><span class="sxs-lookup"><span data-stu-id="7592b-121">If the attribute is for collections, in the **Collection attributes** pane, click **Add collection attribute**.</span></span>  
  
7.  <span data-ttu-id="7592b-122">En la página **Agregar atributo** , seleccione la opción **Forma libre** .</span><span class="sxs-lookup"><span data-stu-id="7592b-122">On the **Add Attribute** page, select the **Free-form** option.</span></span>  
  
8.  <span data-ttu-id="7592b-123">En el cuadro **Nombre** , escriba un nombre para el atributo.</span><span class="sxs-lookup"><span data-stu-id="7592b-123">In the **Name** box, type a name for the attribute.</span></span> <span data-ttu-id="7592b-124">Para obtener una lista de palabras que no se deben usar como nombres de atributo, consulte [palabras reservadas &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="7592b-124">For a list of words that should not be used as attribute names, see [Reserved Words &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span></span>  
  
9. <span data-ttu-id="7592b-125">En el cuadro **Ancho de píxel de la pantalla** , escriba el ancho de la columna de atributo que se va a mostrar en la cuadrícula del **Explorador** .</span><span class="sxs-lookup"><span data-stu-id="7592b-125">In the **Display pixel width** box, type the width of the attribute column to be displayed in the **Explorer** grid.</span></span>  
  
10. <span data-ttu-id="7592b-126">En la lista **Tipo de datos** , seleccione **DateTime**.</span><span class="sxs-lookup"><span data-stu-id="7592b-126">From the **Data type** list, select **DateTime**.</span></span>  
  
11. <span data-ttu-id="7592b-127">En la lista **Máscara de entrada** , seleccione un formato para las fechas.</span><span class="sxs-lookup"><span data-stu-id="7592b-127">From the **Input mask** list, select a format for dates.</span></span>  
  
12. <span data-ttu-id="7592b-128">Si lo desea, seleccione **Habilitar seguimiento de cambios** para realizar el seguimiento de los cambios en los grupos de atributos.</span><span class="sxs-lookup"><span data-stu-id="7592b-128">Optionally, select **Enable change tracking** to track changes to groups of attributes.</span></span> <span data-ttu-id="7592b-129">Para obtener más información, consulte [Agregar atributos a un grupo de seguimiento de cambios &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="7592b-129">For more information, see [Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span></span>  
  
13. <span data-ttu-id="7592b-130">Haga clic en **Guardar atributo**.</span><span class="sxs-lookup"><span data-stu-id="7592b-130">Click **Save attribute**.</span></span>  
  
14. <span data-ttu-id="7592b-131">En la página **Mantenimiento de entidades** , haga clic en **Guardar entidad**.</span><span class="sxs-lookup"><span data-stu-id="7592b-131">On the **Entity Maintenance** page, click **Save entity**.</span></span>  
  
## <a name="to-display-the-time-portion-of-a-datetime-value"></a><span data-ttu-id="7592b-132">Para mostrar la parte de hora de un valor datetime</span><span class="sxs-lookup"><span data-stu-id="7592b-132">To display the time portion of a datetime value</span></span>  
 <span data-ttu-id="7592b-133">Para hacer que la interfaz de usuario muestre la parte de hora de un valor datetime, debe seleccionar una máscara de entrada apropiada para el atributo.</span><span class="sxs-lookup"><span data-stu-id="7592b-133">To have the user interface display the time portion of a datetime value, you must select an appropriate input mask for the attribute.</span></span> <span data-ttu-id="7592b-134">Ninguna de las máscaras integradas para los atributos Datetime hacen esto, pero puede agregar una nueva máscara que permitirá mostrar la hora.</span><span class="sxs-lookup"><span data-stu-id="7592b-134">None of the built-in masks for Datetime attributes do this, but you can add a new mask that will allow you to display time.</span></span> <span data-ttu-id="7592b-135">Para ello, agregue una fila a la tabla mdm.tblList de la base de datos MDS, donde se almacenan las máscaras integradas.</span><span class="sxs-lookup"><span data-stu-id="7592b-135">To do so, add a row in the mdm.tblList table of the MDS database, where the built-in masks are stored.</span></span> <span data-ttu-id="7592b-136">La fila debe tener los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="7592b-136">The row should have the following values:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7592b-137">ListCode</span><span class="sxs-lookup"><span data-stu-id="7592b-137">ListCode</span></span>|<span data-ttu-id="7592b-138">lstInputMask</span><span class="sxs-lookup"><span data-stu-id="7592b-138">lstInputMask</span></span>|  
|<span data-ttu-id="7592b-139">ListName</span><span class="sxs-lookup"><span data-stu-id="7592b-139">ListName</span></span>|<span data-ttu-id="7592b-140">Máscara de entrada</span><span class="sxs-lookup"><span data-stu-id="7592b-140">Input Mask</span></span>|  
|<span data-ttu-id="7592b-141">Seq</span><span class="sxs-lookup"><span data-stu-id="7592b-141">Seq</span></span>|<span data-ttu-id="7592b-142">19</span><span class="sxs-lookup"><span data-stu-id="7592b-142">19</span></span>|  
|<span data-ttu-id="7592b-143">Opción de lista</span><span class="sxs-lookup"><span data-stu-id="7592b-143">List Option</span></span>|<span data-ttu-id="7592b-144">dd/MM/yyyy hh:mm:ss tt</span><span class="sxs-lookup"><span data-stu-id="7592b-144">dd/MM/yyyy hh:mm:ss tt</span></span>|  
|<span data-ttu-id="7592b-145">Option ID</span><span class="sxs-lookup"><span data-stu-id="7592b-145">Option ID</span></span>|<span data-ttu-id="7592b-146">19</span><span class="sxs-lookup"><span data-stu-id="7592b-146">19</span></span>|  
|<span data-ttu-id="7592b-147">IsVisible</span><span class="sxs-lookup"><span data-stu-id="7592b-147">IsVisible</span></span>|<span data-ttu-id="7592b-148">1</span><span class="sxs-lookup"><span data-stu-id="7592b-148">1</span></span>|  
|<span data-ttu-id="7592b-149">Group_ID</span><span class="sxs-lookup"><span data-stu-id="7592b-149">Group_ID</span></span>|<span data-ttu-id="7592b-150">3</span><span class="sxs-lookup"><span data-stu-id="7592b-150">3</span></span>|  
  
 <span data-ttu-id="7592b-151">Después de escribir una fila con los valores anteriores en la tabla mdm.tblList, la máscara "dd/MMM/yyyy hh:mm:ss tt" estará disponible en el cuadro de lista Máscara de entrada.</span><span class="sxs-lookup"><span data-stu-id="7592b-151">After you enter a row with the above values in the mdm.tblList table, the "dd/MM/yyyy hh:mm:ss tt" mask will be available in the Input mask list box.</span></span> <span data-ttu-id="7592b-152">Entonces puede seleccionar esa máscara para mostrar la fecha y la hora de una columna de atributos datetime de una entidad en el Explorador MDS.</span><span class="sxs-lookup"><span data-stu-id="7592b-152">You can then select that mask to display the date and time in a datetime attribute column of an entity in the MDS Explorer.</span></span>  
  
 <span data-ttu-id="7592b-153">La Máscara de entrada es una cadena con formato de fecha y hora de .NET personalizado.</span><span class="sxs-lookup"><span data-stu-id="7592b-153">The Input Mask is a custom .NET DateTime format string.</span></span> <span data-ttu-id="7592b-154">Para más información, consulte [Cadenas con formato de fecha y hora personalizado](https://msdn.microsoft.com/library/8kb3ddd4\(v=vs.110\).aspx)</span><span class="sxs-lookup"><span data-stu-id="7592b-154">For more information, see [Custom Date and Time Format Strings](https://msdn.microsoft.com/library/8kb3ddd4\(v=vs.110\).aspx)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7592b-155">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7592b-155">See Also</span></span>  
 <span data-ttu-id="7592b-156">[Atributos &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="7592b-156">[Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="7592b-157">[Cambiar el nombre de un atributo &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="7592b-157">[Change an Attribute Name &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span></span>  
 <span data-ttu-id="7592b-158">[Cree un atributo basado en dominio &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="7592b-158">[Create a Domain-Based Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="7592b-159">Crear un atributo de archivo &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7592b-159">Create a File Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-file-attribute-master-data-services.md)  
  
  
