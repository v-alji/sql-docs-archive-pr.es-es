---
title: Habilitar una entidad para las jerarquías explícitas y colecciones (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- entities [Master Data Services], enabling for collections
- entities [Master Data Services], enabling for explicit hierarchies
ms.assetid: 380e77e5-ad60-43d4-9605-34a84525f5dd
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: a8129b3f67f050603f85ffb782a9dd209cb303fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744156"
---
# <a name="enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services"></a><span data-ttu-id="bf334-102">Habilitar una entidad para jerarquías explícitas y colecciones (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="bf334-102">Enable an Entity for Explicit Hierarchies and Collections (Master Data Services)</span></span>
  <span data-ttu-id="bf334-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], habilite una entidad para las jerarquías y colecciones explícitas de modo que pueda crearlas para la entidad.</span><span class="sxs-lookup"><span data-stu-id="bf334-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], enable an entity for explicit hierarchies and collections so that you can create explicit hierarchies and collections for the entity.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bf334-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="bf334-104">Prerequisites</span></span>  
 <span data-ttu-id="bf334-105">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="bf334-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="bf334-106">Debe disponer de permiso para tener acceso al área funcional de **Administración del sistema** .</span><span class="sxs-lookup"><span data-stu-id="bf334-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="bf334-107">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="bf334-107">You must be a model administrator.</span></span> <span data-ttu-id="bf334-108">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="bf334-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="bf334-109">Debe existir una entidad.</span><span class="sxs-lookup"><span data-stu-id="bf334-109">An entity must exist.</span></span> <span data-ttu-id="bf334-110">Para obtener más información, vea [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="bf334-110">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-enable-an-entity-for-explicit-hierarchies-and-collections"></a><span data-ttu-id="bf334-111">Habilitar una entidad para las colecciones y jerarquías explícitas</span><span class="sxs-lookup"><span data-stu-id="bf334-111">To enable an entity for explicit hierarchies and collections</span></span>  
  
1.  <span data-ttu-id="bf334-112">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="bf334-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="bf334-113">En la página **Vista de modelo** , en la barra de menús, seleccione **Administrar** y haga clic en **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="bf334-113">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="bf334-114">En la página **Mantenimiento de entidades** , en la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="bf334-114">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="bf334-115">Seleccione la fila para la entidad que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="bf334-115">Select the row for the entity that you want to update.</span></span>  
  
5.  <span data-ttu-id="bf334-116">Haga clic en **Editar entidad seleccionada**.</span><span class="sxs-lookup"><span data-stu-id="bf334-116">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="bf334-117">En la lista **Habilitar jerarquías explícitas y colecciones** , seleccione **sí**.</span><span class="sxs-lookup"><span data-stu-id="bf334-117">From the **Enable explicit hierarchies and collections** list, select **Yes**.</span></span>  
  
7.  <span data-ttu-id="bf334-118">En el cuadro **nombre de jerarquía explícita** , escriba un nombre para una jerarquía explícita.</span><span class="sxs-lookup"><span data-stu-id="bf334-118">In the **Explicit hierarchy name** box, type a name for an explicit hierarchy.</span></span>  
  
8.  <span data-ttu-id="bf334-119">Opcionalmente, desactive la casilla **Mandatory hierarchy** (Jerarquía obligatoria) para crear la jerarquía como no obligatoria.</span><span class="sxs-lookup"><span data-stu-id="bf334-119">Optionally, clear the **Mandatory hierarchy** check box to create the hierarchy as a non-mandatory hierarchy.</span></span>  
  
9. <span data-ttu-id="bf334-120">Haga clic en **Guardar entidad**.</span><span class="sxs-lookup"><span data-stu-id="bf334-120">Click **Save entity**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="bf334-121">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="bf334-121">Next Steps</span></span>  
  
-   [<span data-ttu-id="bf334-122">Crear una jerarquía explícita &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="bf334-122">Create an Explicit Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md)  
  
-   [<span data-ttu-id="bf334-123">Crear una colección &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="bf334-123">Create a Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-collection-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="bf334-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bf334-124">See Also</span></span>  
 <span data-ttu-id="bf334-125">[Entidades &#40;Master Data Services&#41;](../../2014/master-data-services/entities-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="bf334-125">[Entities &#40;Master Data Services&#41;](../../2014/master-data-services/entities-master-data-services.md) </span></span>  
 <span data-ttu-id="bf334-126">[Jerarquías explícitas &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="bf334-126">[Explicit Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) </span></span>  
 [<span data-ttu-id="bf334-127">Colecciones &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="bf334-127">Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collections-master-data-services.md)  
  
  
