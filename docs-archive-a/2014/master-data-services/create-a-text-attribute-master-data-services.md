---
title: Crear un atributo de texto (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attributes [Master Data Services], creating text attributes
- creating text attributes [Master Data Services]
ms.assetid: cd8b57de-364d-42a3-9273-c1c6b992bb40
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c0f44e0e6c6e3df49b6a3746648ee46a23a7a3ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678232"
---
# <a name="create-a-text-attribute-master-data-services"></a><span data-ttu-id="85bf1-102">Crear un atributo de texto (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="85bf1-102">Create a Text Attribute (Master Data Services)</span></span>
  <span data-ttu-id="85bf1-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], cree un atributo de texto cuando desee que los usuarios escriban una cadena de texto como un valor de atributo.</span><span class="sxs-lookup"><span data-stu-id="85bf1-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a text attribute when you want users to enter a text string as an attribute value.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="85bf1-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="85bf1-104">Prerequisites</span></span>  
 <span data-ttu-id="85bf1-105">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="85bf1-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="85bf1-106">Debe disponer de permiso para tener acceso al área funcional de **Administración del sistema** .</span><span class="sxs-lookup"><span data-stu-id="85bf1-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="85bf1-107">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="85bf1-107">You must be a model administrator.</span></span> <span data-ttu-id="85bf1-108">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="85bf1-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="85bf1-109">Debe existir una entidad para la que crear el atributo.</span><span class="sxs-lookup"><span data-stu-id="85bf1-109">An entity must exist to create the attribute for.</span></span> <span data-ttu-id="85bf1-110">Para obtener más información, vea [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="85bf1-110">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-create-a-text-attribute"></a><span data-ttu-id="85bf1-111">Crear un atributo de texto</span><span class="sxs-lookup"><span data-stu-id="85bf1-111">To create a text attribute</span></span>  
  
1.  <span data-ttu-id="85bf1-112">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="85bf1-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="85bf1-113">En la página **Vista de modelo** , en la barra de menús, seleccione **Administrar** y haga clic en **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="85bf1-113">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="85bf1-114">En la página **Mantenimiento de entidades** , en la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="85bf1-114">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="85bf1-115">Seleccione la fila para la entidad para la que desea crear un atributo.</span><span class="sxs-lookup"><span data-stu-id="85bf1-115">Select the row for the entity that you want to create an attribute for.</span></span>  
  
5.  <span data-ttu-id="85bf1-116">Haga clic en **Editar entidad seleccionada**.</span><span class="sxs-lookup"><span data-stu-id="85bf1-116">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="85bf1-117">En la página **Editar entidad** :</span><span class="sxs-lookup"><span data-stu-id="85bf1-117">On the **Edit Entity** page:</span></span>  
  
    -   <span data-ttu-id="85bf1-118">Si el atributo es para miembros hoja, en el panel **Atributos de miembro hoja** , haga clic en **Agregar atributo hoja**.</span><span class="sxs-lookup"><span data-stu-id="85bf1-118">If the attribute is for leaf members, in the **Leaf member attributes** pane, click **Add leaf attribute**.</span></span>  
  
    -   <span data-ttu-id="85bf1-119">Si el atributo es para miembros consolidados, en el panel **Atributos de miembro consolidados** , haga clic en **Agregar atributo consolidado**.</span><span class="sxs-lookup"><span data-stu-id="85bf1-119">If the attribute is for consolidated members, in the **Consolidated member attributes** pane, click **Add consolidated attribute**.</span></span>  
  
    -   <span data-ttu-id="85bf1-120">Si el atributo es para colecciones, en el panel **Atributos de colección** , haga clic en **Agregar atributo de colección**.</span><span class="sxs-lookup"><span data-stu-id="85bf1-120">If the attribute is for collections, in the **Collection attributes** pane, click **Add collection attribute**.</span></span>  
  
7.  <span data-ttu-id="85bf1-121">En la página **Agregar atributo** , seleccione la opción **Forma libre** .</span><span class="sxs-lookup"><span data-stu-id="85bf1-121">On the **Add Attribute** page, select the **Free-form** option.</span></span>  
  
8.  <span data-ttu-id="85bf1-122">En el cuadro **Nombre** , escriba un nombre para el atributo.</span><span class="sxs-lookup"><span data-stu-id="85bf1-122">In the **Name** box, type a name for the attribute.</span></span> <span data-ttu-id="85bf1-123">Para obtener una lista de palabras que no se deben usar como nombres de atributo, consulte [palabras reservadas &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="85bf1-123">For a list of words that should not be used as attribute names, see [Reserved Words &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span></span>  
  
9. <span data-ttu-id="85bf1-124">En el cuadro **Ancho de píxel de la pantalla** , escriba el ancho de la columna de atributo que se va a mostrar en la cuadrícula del **Explorador** .</span><span class="sxs-lookup"><span data-stu-id="85bf1-124">In the **Display pixel width** box, type the width of the attribute column to be displayed in the **Explorer** grid.</span></span>  
  
10. <span data-ttu-id="85bf1-125">En la lista **Tipo de datos** , seleccione **Texto**.</span><span class="sxs-lookup"><span data-stu-id="85bf1-125">From the **Data type** list, select **Text**.</span></span>  
  
11. <span data-ttu-id="85bf1-126">En el cuadro **Longitud** , escriba el número máximo de caracteres permitidos.</span><span class="sxs-lookup"><span data-stu-id="85bf1-126">In the **Length** box, type the maximum number of characters allowed.</span></span>  
  
12. <span data-ttu-id="85bf1-127">Si lo desea, seleccione **Habilitar seguimiento de cambios** para realizar el seguimiento de los cambios en los grupos de atributos.</span><span class="sxs-lookup"><span data-stu-id="85bf1-127">Optionally, select **Enable change tracking** to track changes to groups of attributes.</span></span> <span data-ttu-id="85bf1-128">Para obtener más información, consulte [Agregar atributos a un grupo de seguimiento de cambios &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="85bf1-128">For more information, see [Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span></span>  
  
13. <span data-ttu-id="85bf1-129">Haga clic en **Guardar atributo**.</span><span class="sxs-lookup"><span data-stu-id="85bf1-129">Click **Save attribute**.</span></span>  
  
14. <span data-ttu-id="85bf1-130">En la página **Mantenimiento de entidades** , haga clic en **Guardar entidad**.</span><span class="sxs-lookup"><span data-stu-id="85bf1-130">On the **Entity Maintenance** page, click **Save entity**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85bf1-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="85bf1-131">See Also</span></span>  
 <span data-ttu-id="85bf1-132">[Atributos &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="85bf1-132">[Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="85bf1-133">[Cambiar el nombre de un atributo &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="85bf1-133">[Change an Attribute Name &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span></span>  
 <span data-ttu-id="85bf1-134">[Cree un atributo basado en dominio &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="85bf1-134">[Create a Domain-Based Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="85bf1-135">Crear un atributo de archivo &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="85bf1-135">Create a File Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-file-attribute-master-data-services.md)  
  
  
