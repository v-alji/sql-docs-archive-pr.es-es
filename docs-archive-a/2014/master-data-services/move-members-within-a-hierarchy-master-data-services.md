---
title: Movimiento de miembros dentro de una jerarquía (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- hierarchies [Master Data Services], moving members
- explicit hierarchies, moving members
- derived hierarchies, moving members
- members [Master Data Services], moving
ms.assetid: 049c9a15-89c1-478c-8438-028fffc9e187
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 37167f76b965197dbf8e37e365778395ec640d38
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671584"
---
# <a name="move-members-within-a-hierarchy-master-data-services"></a><span data-ttu-id="a63c6-102">Mover miembros dentro de una jerarquía (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="a63c6-102">Move Members within a Hierarchy (Master Data Services)</span></span>
  <span data-ttu-id="a63c6-103">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], mueva los miembros de una jerarquía para cambiar su ubicación o su asignación principal.</span><span class="sxs-lookup"><span data-stu-id="a63c6-103">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], move members within a hierarchy to change their location or parent assignment.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a63c6-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a63c6-104">Prerequisites</span></span>  
 <span data-ttu-id="a63c6-105">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="a63c6-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="a63c6-106">Debe disponer de permiso de acceso al área funcional **Explorador** .</span><span class="sxs-lookup"><span data-stu-id="a63c6-106">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="a63c6-107">En el caso de las jerarquías explícitas, debe tener como mínimo el permiso **Actualizar** para la entidad.</span><span class="sxs-lookup"><span data-stu-id="a63c6-107">For explicit hierarchies, you must have a minimum of **Update** permission to the entity.</span></span>  
  
-   <span data-ttu-id="a63c6-108">En el caso de las jerarquías derivadas, debe tener un mínimo de **actualización** al modelo y a cualquier atributo basado en dominio que se use en la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="a63c6-108">For derived hierarchies, you must have a minimum of **Update** to the model and to any domain-based attributes used in the hierarchy.</span></span>  
  
### <a name="to-move-members-within-a-hierarchy"></a><span data-ttu-id="a63c6-109">Mover miembros dentro de una jerarquía</span><span class="sxs-lookup"><span data-stu-id="a63c6-109">To move members within a hierarchy</span></span>  
  
1.  <span data-ttu-id="a63c6-110">En la página principal de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , en la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="a63c6-110">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="a63c6-111">En la lista **Versión** , seleccione una versión.</span><span class="sxs-lookup"><span data-stu-id="a63c6-111">From the **Version** list, select a version.</span></span>  
  
3.  <span data-ttu-id="a63c6-112">Haga clic en **Explorador**.</span><span class="sxs-lookup"><span data-stu-id="a63c6-112">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="a63c6-113">En la barra de menús, seleccione **jerarquías** y haga clic en *hierarchy_name*.</span><span class="sxs-lookup"><span data-stu-id="a63c6-113">From the menu bar, point to **Hierarchies** and click *hierarchy_name*.</span></span>  
  
5.  <span data-ttu-id="a63c6-114">En el panel **jerarquía** , donde la jerarquía se muestra en una estructura de árbol, haga clic en la casilla de cada miembro que desee desplace.</span><span class="sxs-lookup"><span data-stu-id="a63c6-114">In the **Hierarchy** pane, where the hierarchy is displayed in a tree structure, click the check box for each member you want to move.</span></span>  
  
6.  <span data-ttu-id="a63c6-115">En la parte superior del panel **jerarquía** , haga clic en **cortar**.</span><span class="sxs-lookup"><span data-stu-id="a63c6-115">At the top of the **Hierarchy** pane, click **Cut**.</span></span>  
  
7.  <span data-ttu-id="a63c6-116">En el panel **jerarquía** , haga clic en la casilla correspondiente al miembro al que desea trasladar los miembros.</span><span class="sxs-lookup"><span data-stu-id="a63c6-116">In the **Hierarchy** pane, click the check box for the member you want to move the members to.</span></span>  
  
8.  <span data-ttu-id="a63c6-117">Haga clic en **pegar**.</span><span class="sxs-lookup"><span data-stu-id="a63c6-117">Click **Paste**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a63c6-118">En las jerarquías derivadas, sólo puede mover los miembros al mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="a63c6-118">In derived hierarchies, you can move members to the same level only.</span></span> <span data-ttu-id="a63c6-119">Asimismo, puede cambiar el criterio de ordenación de los miembros.</span><span class="sxs-lookup"><span data-stu-id="a63c6-119">Also, you cannot change the sort order of members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a63c6-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a63c6-120">See Also</span></span>  
 <span data-ttu-id="a63c6-121">[Mueva los miembros de la jerarquía explícita mediante el proceso de almacenamiento provisional &#40;Master Data Services&#41;](add-update-and-delete-data-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="a63c6-121">[Move Explicit Hierarchy Members by Using the Staging Process &#40;Master Data Services&#41;](add-update-and-delete-data-master-data-services.md) </span></span>  
 <span data-ttu-id="a63c6-122">[Jerarquías derivadas &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="a63c6-122">[Derived Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-master-data-services.md) </span></span>  
 [<span data-ttu-id="a63c6-123">Jerarquías explícitas &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="a63c6-123">Explicit Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/explicit-hierarchies-master-data-services.md)  
  
  
