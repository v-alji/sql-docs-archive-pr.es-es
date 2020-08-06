---
title: Eliminar un atributo (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attributes [Master Data Services], deleting
- deleting attributes [Master Data Services]
ms.assetid: ec3e66f7-0e35-43d7-a80d-64899948ebfe
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 96db56dac9356b1131e722fc7f6b779c93305bb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744167"
---
# <a name="delete-an-attribute-master-data-services"></a><span data-ttu-id="df03d-102">Eliminar un atributo (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="df03d-102">Delete an Attribute (Master Data Services)</span></span>
  <span data-ttu-id="df03d-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], elimine un atributo cuando desee eliminar permanentemente el atributo y todos los valores de atributo asociados.</span><span class="sxs-lookup"><span data-stu-id="df03d-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete an attribute when you want to permanently delete the attribute and all associated attribute values.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="df03d-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="df03d-104">Prerequisites</span></span>  
 <span data-ttu-id="df03d-105">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="df03d-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="df03d-106">Debe disponer de permiso para tener acceso al área funcional de **Administración del sistema** .</span><span class="sxs-lookup"><span data-stu-id="df03d-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="df03d-107">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="df03d-107">You must be a model administrator.</span></span> <span data-ttu-id="df03d-108">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="df03d-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-an-attribute"></a><span data-ttu-id="df03d-109">Para eliminar un atributo</span><span class="sxs-lookup"><span data-stu-id="df03d-109">To delete an attribute</span></span>  
  
1.  <span data-ttu-id="df03d-110">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="df03d-110">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="df03d-111">En la página **Vista de modelo** , en la barra de menús, seleccione **Administrar** y haga clic en **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="df03d-111">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="df03d-112">En la página **Mantenimiento de entidades** , en la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="df03d-112">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="df03d-113">Seleccione la fila correspondiente a la entidad que contenga el atributo que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="df03d-113">Select the row for the entity that contains the attribute you want to delete.</span></span>  
  
5.  <span data-ttu-id="df03d-114">Haga clic en **Editar entidad seleccionada**.</span><span class="sxs-lookup"><span data-stu-id="df03d-114">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="df03d-115">En la página **Editar entidad** , haga clic en el atributo que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="df03d-115">On the **Edit Entity** page, click the attribute you want to delete.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="df03d-116">No puede eliminar los atributos Code o Name.</span><span class="sxs-lookup"><span data-stu-id="df03d-116">You cannot delete the Name or Code attributes.</span></span>  
  
7.  <span data-ttu-id="df03d-117">Haga clic en **eliminar atributo seleccionado**.</span><span class="sxs-lookup"><span data-stu-id="df03d-117">Click **Delete selected attribute**.</span></span>  
  
8.  <span data-ttu-id="df03d-118">En el cuadro de diálogo de confirmación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="df03d-118">In the confirmation dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="df03d-119">En el cuadro de diálogo de confirmación adicional, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="df03d-119">In the additional confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df03d-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="df03d-120">See Also</span></span>  
 <span data-ttu-id="df03d-121">[Atributos &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="df03d-121">[Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="df03d-122">[Atributos basados en dominio &#40;Master Data Services&#41;](../../2014/master-data-services/domain-based-attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="df03d-122">[Domain-Based Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/domain-based-attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="df03d-123">[Cree un atributo de texto &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="df03d-123">[Create a Text Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="df03d-124">Crear un atributo basado en dominio &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="df03d-124">Create a Domain-Based Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md)  
  
  
