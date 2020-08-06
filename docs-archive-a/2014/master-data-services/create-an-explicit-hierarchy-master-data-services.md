---
title: Crear una jerarquía explícita (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- creating explicit hierarchies [Master Data Services]
- explicit hierarchies, creating
ms.assetid: ba768393-6990-4eda-8cb0-d58cb3cfc2e2
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: aebf95e68f210fe5a573aed092231670c10fa188
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674875"
---
# <a name="create-an-explicit-hierarchy-master-data-services"></a><span data-ttu-id="af205-102">Crear una jerarquía explícita (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="af205-102">Create an Explicit Hierarchy (Master Data Services)</span></span>
  <span data-ttu-id="af205-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], cree una jerarquía explícita cuando necesite una jerarquía desigual en la que los miembros puedan existir en cualquier nivel.</span><span class="sxs-lookup"><span data-stu-id="af205-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create an explicit hierarchy when you need a ragged hierarchy in which members can exist at any level.</span></span> <span data-ttu-id="af205-104">Las jerarquías explícitas contienen los miembros de una sola entidad.</span><span class="sxs-lookup"><span data-stu-id="af205-104">Explicit hierarchies contain members from a single entity.</span></span>  
  
 <span data-ttu-id="af205-105">Después de crear una jerarquía explícita, puede agregarle miembros en el área funcional de **Explorador** .</span><span class="sxs-lookup"><span data-stu-id="af205-105">After you create an explicit hierarchy, you can add members to it in the **Explorer** functional area.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="af205-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="af205-106">Prerequisites</span></span>  
 <span data-ttu-id="af205-107">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="af205-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="af205-108">Debe disponer de permiso para tener acceso al área funcional de **Administración del sistema** .</span><span class="sxs-lookup"><span data-stu-id="af205-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="af205-109">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="af205-109">You must be a model administrator.</span></span> <span data-ttu-id="af205-110">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="af205-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="af205-111">La entidad debe habilitarse para las jerarquías explícitas y las colecciones.</span><span class="sxs-lookup"><span data-stu-id="af205-111">The entity must be enabled for explicit hierarchies and collections.</span></span> <span data-ttu-id="af205-112">Para obtener más información, vea [habilitar una entidad para jerarquías explícitas y colecciones &#40;Master Data Services&#41;](../../2014/master-data-services/enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="af205-112">For more information, see [Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;](../../2014/master-data-services/enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span></span>  
  
### <a name="to-create-an-explicit-hierarchy"></a><span data-ttu-id="af205-113">Crear una jerarquía explícita</span><span class="sxs-lookup"><span data-stu-id="af205-113">To create an explicit hierarchy</span></span>  
  
1.  <span data-ttu-id="af205-114">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="af205-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="af205-115">En la página **Vista de modelo** , en la barra de menús, seleccione **Administrar** y haga clic en **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="af205-115">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="af205-116">En la página **Mantenimiento de entidades** , en la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="af205-116">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="af205-117">Seleccione la fila correspondiente a la entidad para la que desea crear una jerarquía explícita.</span><span class="sxs-lookup"><span data-stu-id="af205-117">Select the row for the entity that you want to create an explicit hierarchy for.</span></span>  
  
5.  <span data-ttu-id="af205-118">Haga clic en **Editar entidad seleccionada**.</span><span class="sxs-lookup"><span data-stu-id="af205-118">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="af205-119">En la página **Editar entidad** , en el panel **jerarquías explícitas** , haga clic en **Agregar jerarquía explícita**.</span><span class="sxs-lookup"><span data-stu-id="af205-119">On the **Edit Entity** page, in the **Explicit hierarchies** pane, click **Add explicit hierarchy**.</span></span>  
  
7.  <span data-ttu-id="af205-120">En la página **Agregar jerarquía explícita** , en el cuadro **nombre de jerarquía explícita** , escriba un nombre para la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="af205-120">On the **Add Explicit Hierarchy** page, in the **Explicit hierarchy name** box, type a name for the hierarchy.</span></span>  
  
8.  <span data-ttu-id="af205-121">Opcionalmente, desactive la casilla **Mandatory hierarchy** (Jerarquía obligatoria) para crear la jerarquía como no obligatoria.</span><span class="sxs-lookup"><span data-stu-id="af205-121">Optionally, clear the **Mandatory hierarchy** check box to create the hierarchy as a non-mandatory hierarchy.</span></span> <span data-ttu-id="af205-122">Para obtener más información sobre los tipos de jerarquías, consulte [Jerarquías explícitas &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="af205-122">For more information about hierarchy types, see [Explicit Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md).</span></span>  
  
9. <span data-ttu-id="af205-123">Haga clic en **Guardar jerarquía**.</span><span class="sxs-lookup"><span data-stu-id="af205-123">Click **Save hierarchy**.</span></span>  
  
10. <span data-ttu-id="af205-124">En la página **Editar entidad** , haga clic en **Guardar entidad**.</span><span class="sxs-lookup"><span data-stu-id="af205-124">On the **Edit Entity** page, click **Save entity**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="af205-125">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="af205-125">Next Steps</span></span>  
  
-   [<span data-ttu-id="af205-126">Crear un miembro consolidado &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="af205-126">Create a Consolidated Member &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-consolidated-member-master-data-services.md)  
  
-   [<span data-ttu-id="af205-127">Movimiento de miembros dentro de una jerarquía &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="af205-127">Move Members within a Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/move-members-within-a-hierarchy-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="af205-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="af205-128">See Also</span></span>  
 <span data-ttu-id="af205-129">[Jerarquías explícitas &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="af205-129">[Explicit Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) </span></span>  
 <span data-ttu-id="af205-130">[Jerarquías derivadas con límites explícitos &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-with-explicit-caps-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="af205-130">[Derived Hierarchies with Explicit Caps &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-with-explicit-caps-master-data-services.md) </span></span>  
 [<span data-ttu-id="af205-131">Crear un nombre de jerarquía explícita &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="af205-131">Change an Explicit Hierarchy Name &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/change-an-explicit-hierarchy-name-master-data-services.md)  
  
  
