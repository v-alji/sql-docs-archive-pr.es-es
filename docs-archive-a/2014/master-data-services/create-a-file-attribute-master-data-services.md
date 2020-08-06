---
title: Crear un atributo de archivo (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- creating file attributes [Master Data Services]
- attributes [Master Data Services], creating file attributes
ms.assetid: d224886b-2ef1-4658-8b01-2213cc4b8df6
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f4f6e2f10a830d089d1d217f7cf54d0b8557add9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669727"
---
# <a name="create-a-file-attribute-master-data-services"></a><span data-ttu-id="9f979-102">Crear un atributo de archivo (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="9f979-102">Create a File Attribute (Master Data Services)</span></span>
  <span data-ttu-id="9f979-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], cree un atributo de archivo para rellenar los valores de atributo con archivos.</span><span class="sxs-lookup"><span data-stu-id="9f979-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a file attribute to populate attribute values with files.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9f979-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9f979-104">Prerequisites</span></span>  
 <span data-ttu-id="9f979-105">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="9f979-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="9f979-106">Debe disponer de permiso para tener acceso al área funcional de **Administración del sistema** .</span><span class="sxs-lookup"><span data-stu-id="9f979-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="9f979-107">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="9f979-107">You must be a model administrator.</span></span> <span data-ttu-id="9f979-108">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9f979-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="9f979-109">Debe existir una entidad para la que crear el atributo.</span><span class="sxs-lookup"><span data-stu-id="9f979-109">An entity must exist to create the attribute for.</span></span> <span data-ttu-id="9f979-110">Para obtener más información, vea [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9f979-110">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-create-a-file-attribute"></a><span data-ttu-id="9f979-111">Crear un atributo de archivo</span><span class="sxs-lookup"><span data-stu-id="9f979-111">To create a file attribute</span></span>  
  
1.  <span data-ttu-id="9f979-112">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="9f979-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="9f979-113">En la página **Vista de modelo** , en la barra de menús, seleccione **Administrar** y haga clic en **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="9f979-113">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="9f979-114">En la página **Mantenimiento de entidades** , en la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="9f979-114">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="9f979-115">Seleccione la fila para la entidad para la que desea crear un atributo.</span><span class="sxs-lookup"><span data-stu-id="9f979-115">Select the row for the entity that you want to create an attribute for.</span></span>  
  
5.  <span data-ttu-id="9f979-116">Haga clic en **Editar entidad seleccionada**.</span><span class="sxs-lookup"><span data-stu-id="9f979-116">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="9f979-117">En la página **Editar entidad** :</span><span class="sxs-lookup"><span data-stu-id="9f979-117">On the **Edit Entity** page:</span></span>  
  
    -   <span data-ttu-id="9f979-118">Si el atributo es para miembros hoja, en el panel **Atributos de miembro hoja** , haga clic en **Agregar atributo hoja**.</span><span class="sxs-lookup"><span data-stu-id="9f979-118">If the attribute is for leaf members, in the **Leaf member attributes** pane, click **Add leaf attribute**.</span></span>  
  
    -   <span data-ttu-id="9f979-119">Si el atributo es para miembros consolidados, en el panel **Atributos de miembro consolidados** , haga clic en **Agregar atributo consolidado**.</span><span class="sxs-lookup"><span data-stu-id="9f979-119">If the attribute is for consolidated members, in the **Consolidated member attributes** pane, click **Add consolidated attribute**.</span></span>  
  
    -   <span data-ttu-id="9f979-120">Si el atributo es para colecciones, en el panel **Atributos de colección** , haga clic en **Agregar atributo de colección**.</span><span class="sxs-lookup"><span data-stu-id="9f979-120">If the attribute is for collections, in the **Collection attributes** pane, click **Add collection attribute**.</span></span>  
  
7.  <span data-ttu-id="9f979-121">En la página **Agregar atributo** , seleccione la opción **archivo** .</span><span class="sxs-lookup"><span data-stu-id="9f979-121">On the **Add Attribute** page, select the **File** option.</span></span>  
  
8.  <span data-ttu-id="9f979-122">En el cuadro **Nombre** , escriba un nombre para el atributo.</span><span class="sxs-lookup"><span data-stu-id="9f979-122">In the **Name** box, type a name for the attribute.</span></span> <span data-ttu-id="9f979-123">Para obtener una lista de palabras que no se deben usar como nombres de atributo, consulte [palabras reservadas &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9f979-123">For a list of words that should not be used as attribute names, see [Reserved Words &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span></span>  
  
9. <span data-ttu-id="9f979-124">En el cuadro **Ancho de píxel de la pantalla** , escriba el ancho de la columna de atributo que se va a mostrar en la cuadrícula del **Explorador** .</span><span class="sxs-lookup"><span data-stu-id="9f979-124">In the **Display pixel width** box, type the width of the attribute column to be displayed in the **Explorer** grid.</span></span>  
  
10. <span data-ttu-id="9f979-125">En la lista **extensión de archivo** , seleccione uno o más tipos de archivo que un usuario puede cargar o deje el valor predeterminado (\*. \* ) para permitir todos los tipos de archivo.</span><span class="sxs-lookup"><span data-stu-id="9f979-125">From the **File extension** list, select one or more file types that a user can upload, or leave the default (\*.\*) to allow all file types.</span></span>  
  
11. <span data-ttu-id="9f979-126">Si lo desea, seleccione **Habilitar seguimiento de cambios** para realizar el seguimiento de los cambios en los grupos de atributos.</span><span class="sxs-lookup"><span data-stu-id="9f979-126">Optionally, select **Enable change tracking** to track changes to groups of attributes.</span></span> <span data-ttu-id="9f979-127">Para obtener más información, consulte [Agregar atributos a un grupo de seguimiento de cambios &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9f979-127">For more information, see [Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span></span>  
  
12. <span data-ttu-id="9f979-128">Haga clic en **Guardar atributo**.</span><span class="sxs-lookup"><span data-stu-id="9f979-128">Click **Save attribute**.</span></span>  
  
13. <span data-ttu-id="9f979-129">En la página **Mantenimiento de entidades** , haga clic en **Guardar entidad**.</span><span class="sxs-lookup"><span data-stu-id="9f979-129">On the **Entity Maintenance** page, click **Save entity**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f979-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9f979-130">See Also</span></span>  
 <span data-ttu-id="9f979-131">[Atributos &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="9f979-131">[Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="9f979-132">[Cambiar el nombre de un atributo &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="9f979-132">[Change an Attribute Name &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span></span>  
 <span data-ttu-id="9f979-133">[Cree un atributo basado en dominio &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="9f979-133">[Create a Domain-Based Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="9f979-134">Crear un atributo de texto &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9f979-134">Create a Text Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-text-attribute-master-data-services.md)  
  
  
