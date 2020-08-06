---
title: Crear un atributo de vínculo (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attributes [Master Data Services], creating link attributes
- creating link attributes [Master Data Services]
ms.assetid: e6658e9c-5b08-4b8d-b556-17ec2dd041d2
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 4770d7904371c10dc6720e8d3d7f28ca797d9b80
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677751"
---
# <a name="create-a-link-attribute-master-data-services"></a><span data-ttu-id="5152a-102">Crear un atributo de vínculo (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="5152a-102">Create a Link Attribute (Master Data Services)</span></span>
  <span data-ttu-id="5152a-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], cree un atributo de vínculo cuando quiera que los usuarios escriban un hipervínculo como valor de atributo, como `http://www.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="5152a-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a link attribute when you want users to enter a hyperlink as an attribute value, such as `http://www.contoso.com`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5152a-104">Cuando los usuarios escriban un valor para un atributo de vínculo, la cadena debe comenzar por **http://** o se mostrará un error.</span><span class="sxs-lookup"><span data-stu-id="5152a-104">When users enter a value for a link attribute, the string must begin with **http://** or an error will be displayed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5152a-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5152a-105">Prerequisites</span></span>  
 <span data-ttu-id="5152a-106">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="5152a-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="5152a-107">Debe disponer de permiso para tener acceso al área funcional de **Administración del sistema** .</span><span class="sxs-lookup"><span data-stu-id="5152a-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="5152a-108">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="5152a-108">You must be a model administrator.</span></span> <span data-ttu-id="5152a-109">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="5152a-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="5152a-110">Debe existir una entidad para la que crear el atributo.</span><span class="sxs-lookup"><span data-stu-id="5152a-110">An entity must exist to create the attribute for.</span></span> <span data-ttu-id="5152a-111">Para obtener más información, vea [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="5152a-111">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-create-a-link-attribute"></a><span data-ttu-id="5152a-112">Crear un atributo de vínculo</span><span class="sxs-lookup"><span data-stu-id="5152a-112">To create a link attribute</span></span>  
  
1.  <span data-ttu-id="5152a-113">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="5152a-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="5152a-114">En la página **Vista de modelo** , en la barra de menús, seleccione **Administrar** y haga clic en **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="5152a-114">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="5152a-115">En la página **Mantenimiento de entidades** , en la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="5152a-115">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="5152a-116">Seleccione la fila para la entidad para la que desea crear un atributo.</span><span class="sxs-lookup"><span data-stu-id="5152a-116">Select the row for the entity that you want to create an attribute for.</span></span>  
  
5.  <span data-ttu-id="5152a-117">Haga clic en **Editar entidad seleccionada**.</span><span class="sxs-lookup"><span data-stu-id="5152a-117">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="5152a-118">En la página **Editar entidad** :</span><span class="sxs-lookup"><span data-stu-id="5152a-118">On the **Edit Entity** page:</span></span>  
  
    -   <span data-ttu-id="5152a-119">Si el atributo es para miembros hoja, en el panel **Atributos de miembro hoja** , haga clic en **Agregar atributo hoja**.</span><span class="sxs-lookup"><span data-stu-id="5152a-119">If the attribute is for leaf members, in the **Leaf member attributes** pane, click **Add leaf attribute**.</span></span>  
  
    -   <span data-ttu-id="5152a-120">Si el atributo es para miembros consolidados, en el panel **Atributos de miembro consolidados** , haga clic en **Agregar atributo consolidado**.</span><span class="sxs-lookup"><span data-stu-id="5152a-120">If the attribute is for consolidated members, in the **Consolidated member attributes** pane, click **Add consolidated attribute**.</span></span>  
  
    -   <span data-ttu-id="5152a-121">Si el atributo es para colecciones, en el panel **Atributos de colección** , haga clic en **Agregar atributo de colección**.</span><span class="sxs-lookup"><span data-stu-id="5152a-121">If the attribute is for collections, in the **Collection attributes** pane, click **Add collection attribute**.</span></span>  
  
7.  <span data-ttu-id="5152a-122">En la página **Agregar atributo** , seleccione la opción **Forma libre** .</span><span class="sxs-lookup"><span data-stu-id="5152a-122">On the **Add Attribute** page, select the **Free-form** option.</span></span>  
  
8.  <span data-ttu-id="5152a-123">En el cuadro **Nombre** , escriba un nombre para el atributo.</span><span class="sxs-lookup"><span data-stu-id="5152a-123">In the **Name** box, type a name for the attribute.</span></span> <span data-ttu-id="5152a-124">Para obtener una lista de palabras que no se deben usar como nombres de atributo, consulte [palabras reservadas &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="5152a-124">For a list of words that should not be used as attribute names, see [Reserved Words &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span></span>  
  
9. <span data-ttu-id="5152a-125">En el cuadro **Ancho de píxel de la pantalla** , escriba el ancho de la columna de atributo que se va a mostrar en la cuadrícula del **Explorador** .</span><span class="sxs-lookup"><span data-stu-id="5152a-125">In the **Display pixel width** box, type the width of the attribute column to be displayed in the **Explorer** grid.</span></span>  
  
10. <span data-ttu-id="5152a-126">En la lista **Tipo de datos** , seleccione **Vínculo**.</span><span class="sxs-lookup"><span data-stu-id="5152a-126">From the **Data type** list, select **Link**.</span></span>  
  
11. <span data-ttu-id="5152a-127">En el cuadro **Longitud** , escriba el número máximo de caracteres permitidos.</span><span class="sxs-lookup"><span data-stu-id="5152a-127">In the **Length** box, type the maximum number of characters allowed.</span></span>  
  
12. <span data-ttu-id="5152a-128">Si lo desea, seleccione **Habilitar seguimiento de cambios** para realizar el seguimiento de los cambios en los grupos de atributos.</span><span class="sxs-lookup"><span data-stu-id="5152a-128">Optionally, select **Enable change tracking** to track changes to groups of attributes.</span></span> <span data-ttu-id="5152a-129">Para obtener más información, consulte [Agregar atributos a un grupo de seguimiento de cambios &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="5152a-129">For more information, see [Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span></span>  
  
13. <span data-ttu-id="5152a-130">Haga clic en **Guardar atributo**.</span><span class="sxs-lookup"><span data-stu-id="5152a-130">Click **Save attribute**.</span></span>  
  
14. <span data-ttu-id="5152a-131">En la página **Mantenimiento de entidades** , haga clic en **Guardar entidad**.</span><span class="sxs-lookup"><span data-stu-id="5152a-131">On the **Entity Maintenance** page, click **Save entity**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5152a-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5152a-132">See Also</span></span>  
 <span data-ttu-id="5152a-133">[Atributos &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="5152a-133">[Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="5152a-134">[Cambiar el nombre de un atributo &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="5152a-134">[Change an Attribute Name &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span></span>  
 <span data-ttu-id="5152a-135">[Cree un atributo basado en dominio &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="5152a-135">[Create a Domain-Based Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="5152a-136">Crear un atributo de archivo &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5152a-136">Create a File Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-file-attribute-master-data-services.md)  
  
  
