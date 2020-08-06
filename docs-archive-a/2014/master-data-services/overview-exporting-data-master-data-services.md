---
title: Exportación de datos (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- exporting data [Master Data Services]
- subscription views [Master Data Services]
- subscription views [Master Data Services], about subscription views
ms.assetid: 8b74409a-ea70-45f8-84c7-da6905e4901a
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: edae5b996c25a1b6053231ed2f69ef511b9fbfa6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673071"
---
# <a name="exporting-data-master-data-services"></a><span data-ttu-id="dd066-102">Exportar datos (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="dd066-102">Exporting Data (Master Data Services)</span></span>
  <span data-ttu-id="dd066-103">Puede exportar datos de [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] a sistemas de suscripción creando vistas de suscripciones.</span><span class="sxs-lookup"><span data-stu-id="dd066-103">You can export [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] data to subscribing systems by creating subscriptions views.</span></span> <span data-ttu-id="dd066-104">Cualquier sistema de suscripción podrá ver los datos publicados en la base de datos de [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dd066-104">Any subscribing system can then view the published data in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="dd066-105">Para obtener más información acerca de las vistas, consulte [Vistas](../relational-databases/views/views.md).</span><span class="sxs-lookup"><span data-stu-id="dd066-105">For more information about views, see [Views](../relational-databases/views/views.md).</span></span>  
  
## <a name="subscription-view-formats"></a><span data-ttu-id="dd066-106">Formatos de vista de suscripciones</span><span class="sxs-lookup"><span data-stu-id="dd066-106">Subscription View Formats</span></span>  
 <span data-ttu-id="dd066-107">Al crear una vista en [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], elige entre un conjunto de formatos de vistas estándar proporcionados por [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dd066-107">When you create a view in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], you choose from a set of standard view formats that [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] provides.</span></span> <span data-ttu-id="dd066-108">Puede utilizar estos formatos para crear vistas que muestren:</span><span class="sxs-lookup"><span data-stu-id="dd066-108">You can use these formats to create views that show:</span></span>  
  
-   <span data-ttu-id="dd066-109">Todos los miembros hoja y sus atributos.</span><span class="sxs-lookup"><span data-stu-id="dd066-109">All leaf members and their attributes.</span></span>  
  
-   <span data-ttu-id="dd066-110">Todos los miembros consolidados y sus atributos.</span><span class="sxs-lookup"><span data-stu-id="dd066-110">All consolidated members and their attributes.</span></span>  
  
-   <span data-ttu-id="dd066-111">Todas las colecciones y sus atributos.</span><span class="sxs-lookup"><span data-stu-id="dd066-111">All collections and their attributes.</span></span>  
  
-   <span data-ttu-id="dd066-112">Los miembros agregados explícitamente a una colección.</span><span class="sxs-lookup"><span data-stu-id="dd066-112">The members explicitly added to a collection.</span></span>  
  
-   <span data-ttu-id="dd066-113">Los miembros de una jerarquía derivada, en formato de nivel o de elemento secundario primario.</span><span class="sxs-lookup"><span data-stu-id="dd066-113">The members in a derived hierarchy, in either a parent child or level format.</span></span>  
  
-   <span data-ttu-id="dd066-114">Los miembros de todas las jerarquías explícitas de una entidad, en formato de nivel o de elemento secundario primario.</span><span class="sxs-lookup"><span data-stu-id="dd066-114">The members in all explicit hierarchies for an entity, in either a parent child or level format.</span></span>  
  
## <a name="subscription-views-can-become-out-of-date"></a><span data-ttu-id="dd066-115">Las vistas de suscripción pueden quedarse obsoletas</span><span class="sxs-lookup"><span data-stu-id="dd066-115">Subscription Views Can Become Out-of-Date</span></span>  
 <span data-ttu-id="dd066-116">Después de crear una vista de suscripción para una entidad o una jerarquía, los cambios en los objetos de modelo asociados no se reflejan automáticamente en la vista.</span><span class="sxs-lookup"><span data-stu-id="dd066-116">After you create a subscription view for an entity or hierarchy, changes to the associated model objects are not automatically reflected in the view.</span></span> <span data-ttu-id="dd066-117">Puede que también necesite volver a generar una vista de suscripción en [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] para reflejar los cambios en los objetos de modelo.</span><span class="sxs-lookup"><span data-stu-id="dd066-117">You might need to regenerate a subscription view in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] to reflect changes to model objects.</span></span> <span data-ttu-id="dd066-118">La columna **Cambiado** en la página **Exportar** se actualiza a **True** cuando los objetos de modelo cambian.</span><span class="sxs-lookup"><span data-stu-id="dd066-118">The **Changed** column on the **Export** page is updated to **True** when model objects change.</span></span> <span data-ttu-id="dd066-119">**True** indica que debería modificar la vista de suscripción y guardarla, con lo que la vista se regenera.</span><span class="sxs-lookup"><span data-stu-id="dd066-119">**True** indicates that you should edit the subscription view and save it, which regenerates the view.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="dd066-120">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="dd066-120">Related Tasks</span></span>  
  
|<span data-ttu-id="dd066-121">Descripción de la tarea</span><span class="sxs-lookup"><span data-stu-id="dd066-121">Task Description</span></span>|<span data-ttu-id="dd066-122">Tema</span><span class="sxs-lookup"><span data-stu-id="dd066-122">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="dd066-123">Crear una vista de suscripción de los datos maestros.</span><span class="sxs-lookup"><span data-stu-id="dd066-123">Create a subscription view of your master data.</span></span>|[<span data-ttu-id="dd066-124">Cree una vista de suscripciones &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="dd066-124">Create a Subscription View &#40;Master Data Services&#41;</span></span>](create-a-subscription-view-to-export-data-master-data-services.md)|  
|<span data-ttu-id="dd066-125">Eliminar una vista de suscripción existente.</span><span class="sxs-lookup"><span data-stu-id="dd066-125">Delete an existing subscription view.</span></span>|[<span data-ttu-id="dd066-126">Eliminar una vista de suscripciones &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="dd066-126">Delete a Subscription View &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-a-subscription-view-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="dd066-127">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="dd066-127">Related Content</span></span>  
  
-   [<span data-ttu-id="dd066-128">Formatos de vista de suscripciones &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="dd066-128">Subscription View Formats &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/subscription-view-formats-master-data-services.md)  
  
-   [<span data-ttu-id="dd066-129">Vistas</span><span class="sxs-lookup"><span data-stu-id="dd066-129">Views</span></span>](../relational-databases/views/views.md)  
  
  
