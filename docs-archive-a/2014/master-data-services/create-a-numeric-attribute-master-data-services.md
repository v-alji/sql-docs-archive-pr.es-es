---
title: Crear un atributo numérico (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attributes [Master Data Services], creating number attributes
- creating number attributes [Master Data Services]
ms.assetid: c0dbb6d8-ba78-485a-a40d-6d5cb7e75d0a
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: bb9302c0b585c21410a6a764dc2e6dac845c6299
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662143"
---
# <a name="create-a-numeric-attribute-master-data-services"></a><span data-ttu-id="efabe-102">Crear un atributo numérico (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="efabe-102">Create a Numeric Attribute (Master Data Services)</span></span>
  <span data-ttu-id="efabe-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], cree un atributo numérico cuando desee que los usuarios escriban un número como valor de un atributo.</span><span class="sxs-lookup"><span data-stu-id="efabe-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a numeric attribute when you want users to enter a number as an attribute value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="efabe-104">Los atributos numéricos tienen limitaciones.</span><span class="sxs-lookup"><span data-stu-id="efabe-104">Numeric attributes have limitations.</span></span> <span data-ttu-id="efabe-105">Para obtener más información, consulte [Atributos &#40;Master Data Services&#41;](attributes-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="efabe-105">For more information, see [Attributes &#40;Master Data Services&#41;](attributes-master-data-services.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="efabe-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="efabe-106">Prerequisites</span></span>  
 <span data-ttu-id="efabe-107">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="efabe-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="efabe-108">Debe disponer de permiso para tener acceso al área funcional de **Administración del sistema** .</span><span class="sxs-lookup"><span data-stu-id="efabe-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="efabe-109">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="efabe-109">You must be a model administrator.</span></span> <span data-ttu-id="efabe-110">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="efabe-110">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="efabe-111">Debe existir una entidad para la que crear el atributo.</span><span class="sxs-lookup"><span data-stu-id="efabe-111">An entity must exist to create the attribute for.</span></span> <span data-ttu-id="efabe-112">Para obtener más información, vea [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="efabe-112">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-create-a-numeric-attribute"></a><span data-ttu-id="efabe-113">Para crear un atributo numérico</span><span class="sxs-lookup"><span data-stu-id="efabe-113">To create a numeric attribute</span></span>  
  
1.  <span data-ttu-id="efabe-114">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="efabe-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="efabe-115">En la página **Vista de modelo** , en la barra de menús, seleccione **Administrar** y haga clic en **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="efabe-115">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="efabe-116">En la página **Mantenimiento de entidades** , en la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="efabe-116">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="efabe-117">Seleccione la fila para la entidad para la que desea crear un atributo.</span><span class="sxs-lookup"><span data-stu-id="efabe-117">Select the row for the entity that you want to create an attribute for.</span></span>  
  
5.  <span data-ttu-id="efabe-118">Haga clic en **Editar entidad seleccionada**.</span><span class="sxs-lookup"><span data-stu-id="efabe-118">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="efabe-119">En la página **Editar entidad** :</span><span class="sxs-lookup"><span data-stu-id="efabe-119">On the **Edit Entity** page:</span></span>  
  
    -   <span data-ttu-id="efabe-120">Si el atributo es para miembros hoja, en el panel **Atributos de miembro hoja** , haga clic en **Agregar atributo hoja**.</span><span class="sxs-lookup"><span data-stu-id="efabe-120">If the attribute is for leaf members, in the **Leaf member attributes** pane, click **Add leaf attribute**.</span></span>  
  
    -   <span data-ttu-id="efabe-121">Si el atributo es para miembros consolidados, en el panel **Atributos de miembro consolidados** , haga clic en **Agregar atributo consolidado**.</span><span class="sxs-lookup"><span data-stu-id="efabe-121">If the attribute is for consolidated members, in the **Consolidated member attributes** pane, click **Add consolidated attribute**.</span></span>  
  
    -   <span data-ttu-id="efabe-122">Si el atributo es para colecciones, en el panel **Atributos de colección** , haga clic en **Agregar atributo de colección**.</span><span class="sxs-lookup"><span data-stu-id="efabe-122">If the attribute is for collections, in the **Collection attributes** pane, click **Add collection attribute**.</span></span>  
  
7.  <span data-ttu-id="efabe-123">En la página **Agregar atributo** , seleccione la opción **Forma libre** .</span><span class="sxs-lookup"><span data-stu-id="efabe-123">On the **Add Attribute** page, select the **Free-form** option.</span></span>  
  
8.  <span data-ttu-id="efabe-124">En el cuadro **Nombre** , escriba un nombre para el atributo.</span><span class="sxs-lookup"><span data-stu-id="efabe-124">In the **Name** box, type a name for the attribute.</span></span> <span data-ttu-id="efabe-125">Para obtener una lista de palabras que no se deben usar como nombres de atributo, consulte [palabras reservadas &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="efabe-125">For a list of words that should not be used as attribute names, see [Reserved Words &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span></span>  
  
9. <span data-ttu-id="efabe-126">En el cuadro **Ancho de píxel de la pantalla** , escriba el ancho de la columna de atributo que se va a mostrar en la cuadrícula del **Explorador** .</span><span class="sxs-lookup"><span data-stu-id="efabe-126">In the **Display pixel width** box, type the width of the attribute column to be displayed in the **Explorer** grid.</span></span>  
  
10. <span data-ttu-id="efabe-127">En la lista **Tipo de datos** , seleccione **Número**.</span><span class="sxs-lookup"><span data-stu-id="efabe-127">From the **Data type** list, select **Number**.</span></span>  
  
11. <span data-ttu-id="efabe-128">En el cuadro **Decimales** , escriba la cantidad de números que se pueden escribir después de un decimal.</span><span class="sxs-lookup"><span data-stu-id="efabe-128">In the **Decimals** box, type the number of numbers that can be entered after a decimal.</span></span>  
  
12. <span data-ttu-id="efabe-129">En la lista **máscara de entrada** , seleccione un formato para los números negativos.</span><span class="sxs-lookup"><span data-stu-id="efabe-129">From the **Input mask** list, select a format for negative numbers.</span></span>  
  
13. <span data-ttu-id="efabe-130">Si lo desea, seleccione **Habilitar seguimiento de cambios** para realizar el seguimiento de los cambios en los grupos de atributos.</span><span class="sxs-lookup"><span data-stu-id="efabe-130">Optionally, select **Enable change tracking** to track changes to groups of attributes.</span></span> <span data-ttu-id="efabe-131">Consulte [Agregar atributos a un grupo de seguimiento de cambios &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="efabe-131">See [Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md) for more information.</span></span>  
  
14. <span data-ttu-id="efabe-132">Haga clic en **Guardar atributo**.</span><span class="sxs-lookup"><span data-stu-id="efabe-132">Click **Save attribute**.</span></span>  
  
15. <span data-ttu-id="efabe-133">En la página **Mantenimiento de entidades** , haga clic en **Guardar entidad**.</span><span class="sxs-lookup"><span data-stu-id="efabe-133">On the **Entity Maintenance** page, click **Save entity**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efabe-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="efabe-134">See Also</span></span>  
 <span data-ttu-id="efabe-135">[Atributos &#40;Master Data Services&#41;](attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="efabe-135">[Attributes &#40;Master Data Services&#41;](attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="efabe-136">[Cambiar el nombre de un atributo &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="efabe-136">[Change an Attribute Name &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span></span>  
 <span data-ttu-id="efabe-137">[Cree un atributo basado en dominio &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="efabe-137">[Create a Domain-Based Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="efabe-138">Crear un atributo de archivo &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="efabe-138">Create a File Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-file-attribute-master-data-services.md)  
  
  
