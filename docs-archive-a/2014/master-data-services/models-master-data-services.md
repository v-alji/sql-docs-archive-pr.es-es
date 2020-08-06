---
title: Modelos (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- models [Master Data Services], about models
- models [Master Data Services]
ms.assetid: 9f862a3d-25ab-41e9-b833-1db99959e825
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 1d5a4a431d3ca7b6fa499de68a2bc4c5033cd086
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677169"
---
# <a name="models-master-data-services"></a><span data-ttu-id="9664d-102">Modelos (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="9664d-102">Models (Master Data Services)</span></span>
  <span data-ttu-id="9664d-103">Los modelos son el nivel superior de organización de datos en [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9664d-103">Models are the highest level of data organization in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span></span> <span data-ttu-id="9664d-104">Un modelo define la estructura de datos de la solución de administración de datos maestros.</span><span class="sxs-lookup"><span data-stu-id="9664d-104">A model defines the structure of data in your master data management solution.</span></span> <span data-ttu-id="9664d-105">Un modelo contiene los siguientes objetos:</span><span class="sxs-lookup"><span data-stu-id="9664d-105">A model contains the following objects:</span></span>  
  
-   <span data-ttu-id="9664d-106">Entidades</span><span class="sxs-lookup"><span data-stu-id="9664d-106">Entities</span></span>  
  
-   <span data-ttu-id="9664d-107">Atributos y grupos de atributos</span><span class="sxs-lookup"><span data-stu-id="9664d-107">Attributes and attribute groups</span></span>  
  
-   <span data-ttu-id="9664d-108">Jerarquías derivadas y explícitas</span><span class="sxs-lookup"><span data-stu-id="9664d-108">Explicit and derived hierarchies</span></span>  
  
-   <span data-ttu-id="9664d-109">Colecciones</span><span class="sxs-lookup"><span data-stu-id="9664d-109">Collections</span></span>  
  
 <span data-ttu-id="9664d-110">Los modelos organizan la estructura de los datos maestros.</span><span class="sxs-lookup"><span data-stu-id="9664d-110">Models organize the structure of your master data.</span></span> <span data-ttu-id="9664d-111">Su implementación de [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] puede tener uno o varios modelos que agrupan tipos de datos similares.</span><span class="sxs-lookup"><span data-stu-id="9664d-111">Your [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] implementation can have one or many models that each group similar kinds of data.</span></span> <span data-ttu-id="9664d-112">En general, los datos maestros se pueden clasificar en una de estas cuatro categorías: personas, lugares, cosas o conceptos.</span><span class="sxs-lookup"><span data-stu-id="9664d-112">In general, master data can be categorized in one of four ways: people, places, things, or concepts.</span></span> <span data-ttu-id="9664d-113">Por ejemplo, puede crear un modelo Producto que vaya a contener datos relacionados con productos o un modelo Cliente para que contenga datos relacionados con clientes.</span><span class="sxs-lookup"><span data-stu-id="9664d-113">For example, you can create a Product model to contain product-related data or a Customer model to contain customer-related data.</span></span>  
  
 <span data-ttu-id="9664d-114">Puede asignar a usuarios y grupos el permiso para ver y actualizar los objetos dentro del modelo.</span><span class="sxs-lookup"><span data-stu-id="9664d-114">You can assign users and groups permission to view and update objects within the model.</span></span> <span data-ttu-id="9664d-115">Si no concede permisos al modelo, no se mostrará.</span><span class="sxs-lookup"><span data-stu-id="9664d-115">If you do not give permission to the model, it is not displayed.</span></span>  
  
 <span data-ttu-id="9664d-116">En un momento determinado, podrá crear copias de los datos maestros dentro de un modelo.</span><span class="sxs-lookup"><span data-stu-id="9664d-116">At any given time, you can create copies of the master data within a model.</span></span> <span data-ttu-id="9664d-117">Estas copias se denominan versiones.</span><span class="sxs-lookup"><span data-stu-id="9664d-117">These copies are called versions.</span></span>  
  
 <span data-ttu-id="9664d-118">Una vez haya definido un modelo en un entorno de prueba, puede implementarlo, con o sin los datos correspondientes, desde el entorno de prueba hasta un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="9664d-118">When you have defined a model in a test environment, you can deploy it, with or without the corresponding data, from the test environment to a production environment.</span></span> <span data-ttu-id="9664d-119">Esto elimina la necesidad de volver a crear los modelos en el entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="9664d-119">This eliminates the need to recreate your models in your production environment.</span></span>  
  
## <a name="how-models-relate-to-other-objects"></a><span data-ttu-id="9664d-120">Cómo se relacionan los modelos con otros objetos</span><span class="sxs-lookup"><span data-stu-id="9664d-120">How Models Relate to Other Objects</span></span>  
 <span data-ttu-id="9664d-121">Un modelo contiene entidades.</span><span class="sxs-lookup"><span data-stu-id="9664d-121">A model contains entities.</span></span> <span data-ttu-id="9664d-122">Las entidades contienen atributos, jerarquías explícitas y colecciones.</span><span class="sxs-lookup"><span data-stu-id="9664d-122">Entities contain attributes, explicit hierarchies, and collections.</span></span> <span data-ttu-id="9664d-123">Los atributos pueden estar contenidos en grupos de atributos.</span><span class="sxs-lookup"><span data-stu-id="9664d-123">Attributes can be contained in attribute groups.</span></span> <span data-ttu-id="9664d-124">Los atributos basados en dominios existen cuando se usa una entidad como atributo para otra entidad.</span><span class="sxs-lookup"><span data-stu-id="9664d-124">Domain-based attributes exist when an entity is used as an attribute for another entity.</span></span>  
  
 <span data-ttu-id="9664d-125">Esta imagen muestra las relaciones existentes entre los objetos de un modelo.</span><span class="sxs-lookup"><span data-stu-id="9664d-125">This image shows the relationships among the objects in a model.</span></span>  
  
 <span data-ttu-id="9664d-126">![Objetos de un modelo de Master Data Services](../../2014/master-data-services/media/mds-conc-model-circles.gif "Objetos de un modelo de Master Data Services")</span><span class="sxs-lookup"><span data-stu-id="9664d-126">![Objects in a Master Data Services Model](../../2014/master-data-services/media/mds-conc-model-circles.gif "Objects in a Master Data Services Model")</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9664d-127">Las jerarquías derivadas también son objetos de modelo, pero no se muestran en la imagen.</span><span class="sxs-lookup"><span data-stu-id="9664d-127">Derived hierarchies are also model objects, but they are not shown in the image.</span></span> <span data-ttu-id="9664d-128">Las jerarquías derivadas se derivan de las relaciones de atributo basadas en dominios que existen entre las entidades.</span><span class="sxs-lookup"><span data-stu-id="9664d-128">Derived hierarchies are derived from the domain-based attribute relationships that exist between entities.</span></span> <span data-ttu-id="9664d-129">Vea [Jerarquías derivadas &#40;Master Data Services&#41;](derived-hierarchies-master-data-services.md) para más información.</span><span class="sxs-lookup"><span data-stu-id="9664d-129">See [Derived Hierarchies &#40;Master Data Services&#41;](derived-hierarchies-master-data-services.md) for more information.</span></span>  
  
 <span data-ttu-id="9664d-130">Los datos maestros son los datos contenidos en los objetos de modelo.</span><span class="sxs-lookup"><span data-stu-id="9664d-130">Master data is the data that is contained in the model objects.</span></span> <span data-ttu-id="9664d-131">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], los datos maestros se almacenan como miembros de una entidad.</span><span class="sxs-lookup"><span data-stu-id="9664d-131">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], master data is stored as members in an entity.</span></span>  
  
 <span data-ttu-id="9664d-132">Los objetos de modelo se mantienen en el área funcional de **Administración del sistema** de la interfaz de usuario de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9664d-132">Model objects are maintained in the **System Administration** functional area of the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] user interface.</span></span>  
  
## <a name="model-example"></a><span data-ttu-id="9664d-133">Ejemplo de modelo</span><span class="sxs-lookup"><span data-stu-id="9664d-133">Model Example</span></span>  
 <span data-ttu-id="9664d-134">En el ejemplo siguiente, los objetos del modelo Product agrupan lógicamente los datos relacionados con los productos.</span><span class="sxs-lookup"><span data-stu-id="9664d-134">In the following example, the objects in the Product model logically group product-related data.</span></span>  
  
 <span data-ttu-id="9664d-135">![Ejemplo de datos maestros de modelo de producto](../../2014/master-data-services/media/mds-conc-model.gif "Ejemplo de datos maestros de modelo de producto")</span><span class="sxs-lookup"><span data-stu-id="9664d-135">![Product Model Master Data Example](../../2014/master-data-services/media/mds-conc-model.gif "Product Model Master Data Example")</span></span>  
  
 <span data-ttu-id="9664d-136">Otros modelos comunes son:</span><span class="sxs-lookup"><span data-stu-id="9664d-136">Other common models are:</span></span>  
  
-   <span data-ttu-id="9664d-137">Accounts: podrían incluir entidades como cuentas de balance, cuentas de balance de resultados, estadísticas y tipos de cuenta.</span><span class="sxs-lookup"><span data-stu-id="9664d-137">Accounts, which could include entities such as balance sheet accounts, income statement accounts, statistics, and account type.</span></span>  
  
-   <span data-ttu-id="9664d-138">Customer: podría incluir entidades como género, educación, ocupación y estado civil.</span><span class="sxs-lookup"><span data-stu-id="9664d-138">Customer, which could include entities such as gender, education, occupation, and marital status.</span></span>  
  
-   <span data-ttu-id="9664d-139">Geography: podría incluir entidades como códigos postales, ciudades, municipios, estados, provincias, regiones, territorios, países y continentes.</span><span class="sxs-lookup"><span data-stu-id="9664d-139">Geography, which could include entities such as postal codes, cities, counties, states, provinces, regions, territories, countries, and continents.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="9664d-140">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="9664d-140">Related Tasks</span></span>  
  
|<span data-ttu-id="9664d-141">Descripción de la tarea</span><span class="sxs-lookup"><span data-stu-id="9664d-141">Task Description</span></span>|<span data-ttu-id="9664d-142">Tema</span><span class="sxs-lookup"><span data-stu-id="9664d-142">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="9664d-143">Crear un modelo para organizar los datos maestros.</span><span class="sxs-lookup"><span data-stu-id="9664d-143">Create a model to organize your master data.</span></span>|[<span data-ttu-id="9664d-144">Crear un modelo &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9664d-144">Create a Model &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-model-master-data-services.md)|  
|<span data-ttu-id="9664d-145">Cambiar el nombre de un modelo existente.</span><span class="sxs-lookup"><span data-stu-id="9664d-145">Change the name of an existing model.</span></span>|[<span data-ttu-id="9664d-146">Cambiar el nombre de un modelo &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9664d-146">Change a Model Name &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/change-a-model-name-master-data-services.md)|  
|<span data-ttu-id="9664d-147">Eliminar un modelo existente.</span><span class="sxs-lookup"><span data-stu-id="9664d-147">Delete an existing model.</span></span>|[<span data-ttu-id="9664d-148">Eliminar un modelo &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9664d-148">Delete a Model &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-a-model-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="9664d-149">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="9664d-149">Related Content</span></span>  
  
-   [<span data-ttu-id="9664d-150">Introducción a Master Data Services</span><span class="sxs-lookup"><span data-stu-id="9664d-150">Master Data Services Overview</span></span>](master-data-services-overview-mds.md)  
  
-   [<span data-ttu-id="9664d-151">Entidades &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9664d-151">Entities &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/entities-master-data-services.md)  
  
-   [<span data-ttu-id="9664d-152">Atributos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9664d-152">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)  
  
-   [<span data-ttu-id="9664d-153">Implementar modelos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9664d-153">Deploying Models &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/deploying-models-master-data-services.md)  
  
-   [<span data-ttu-id="9664d-154">Permisos de objeto del modelo &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9664d-154">Model Object Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/model-object-permissions-master-data-services.md)  
  
  
