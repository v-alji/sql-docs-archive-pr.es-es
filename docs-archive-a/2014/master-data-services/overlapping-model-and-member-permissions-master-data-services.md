---
title: Superponer permisos de modelo y de miembro (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- models [Master Data Services], effective permissions
- permissions [Master Data Services], model and member overlaps
- members [Master Data Services], effective permissions
ms.assetid: 9fd7a555-43bf-4796-a8b6-1ca63a291216
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ec5f4019f25a777e4c70433bd9a7e72fca2277e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663548"
---
# <a name="overlapping-model-and-member-permissions-master-data-services"></a><span data-ttu-id="8096c-102">Superponer permisos de modelo y de miembro (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="8096c-102">Overlapping Model and Member Permissions (Master Data Services)</span></span>
  <span data-ttu-id="8096c-103">El permiso que se asigne a un miembro puede solaparse con el permiso asignado a un objeto del modelo.</span><span class="sxs-lookup"><span data-stu-id="8096c-103">Permission assigned to a member can overlap with permission assigned to a model object.</span></span> <span data-ttu-id="8096c-104">Cuando se producen las superposiciones, el permiso más restrictivo será el que surta efecto.</span><span class="sxs-lookup"><span data-stu-id="8096c-104">When overlaps occur, the more restrictive permission takes effect.</span></span>  
  
 <span data-ttu-id="8096c-105">Si un miembro tiene permiso distinto al de su objeto del modelo correspondiente, se aplicarán las reglas siguientes:</span><span class="sxs-lookup"><span data-stu-id="8096c-105">If a member has permission that is different than its corresponding model object, the following rules apply:</span></span>  
  
-   <span data-ttu-id="8096c-106">**Denegar** invalida al resto de permisos.</span><span class="sxs-lookup"><span data-stu-id="8096c-106">**Deny** overrides all other permissions.</span></span>  
  
-   <span data-ttu-id="8096c-107">**La actualización de solo lectura** invalida **Update**.</span><span class="sxs-lookup"><span data-stu-id="8096c-107">**Read-only** overrides **Update**.</span></span>  
  
 <span data-ttu-id="8096c-108">La siguiente imagen muestra qué permisos surten efecto en un valor de atributo individual cuando los permisos de atributo son diferentes que los permisos de miembro.</span><span class="sxs-lookup"><span data-stu-id="8096c-108">The following image shows which permissions take effect on an individual attribute value when attribute permissions are different than member permissions.</span></span>  
  
 <span data-ttu-id="8096c-109">![mds_conc_security_member_overlap_table](../../2014/master-data-services/media/mds-conc-security-member-overlap-table.gif "mds_conc_security_member_overlap_table")</span><span class="sxs-lookup"><span data-stu-id="8096c-109">![mds_conc_security_member_overlap_table](../../2014/master-data-services/media/mds-conc-security-member-overlap-table.gif "mds_conc_security_member_overlap_table")</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="8096c-110">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="8096c-110">Example 1</span></span>  
 <span data-ttu-id="8096c-111">![mds_conc_overlap_model_1](../../2014/master-data-services/media/mds-conc-overlap-model-1.gif "mds_conc_overlap_model_1")</span><span class="sxs-lookup"><span data-stu-id="8096c-111">![mds_conc_overlap_model_1](../../2014/master-data-services/media/mds-conc-overlap-model-1.gif "mds_conc_overlap_model_1")</span></span>  
  
 <span data-ttu-id="8096c-112">En la pestaña **Modelos** , la entidad Product tiene asignado el permiso **Actualizar** .</span><span class="sxs-lookup"><span data-stu-id="8096c-112">On the **Models** tab, the Product entity has **Update** permission assigned.</span></span> <span data-ttu-id="8096c-113">Todos los atributos de la entidad heredan ese permiso.</span><span class="sxs-lookup"><span data-stu-id="8096c-113">All attributes in the entity inherit that permission.</span></span>  
  
 <span data-ttu-id="8096c-114">En la pestaña **Miembros de la jerarquía** , el nodo de subcategoría de bicicletas de montaña de una jerarquía derivada tiene asignado el permiso **Actualizar** .</span><span class="sxs-lookup"><span data-stu-id="8096c-114">On the **Hierarchy Members** tab, the Mountain Bikes subcategory node in a derived hierarchy has **Update** permission assigned.</span></span>  
  
 <span data-ttu-id="8096c-115">Como consecuencia, el usuario tiene el permiso **Actualizar**para todos los valores de atributo de todos los miembros del nodo Mountain Bikes en **Explorador** .</span><span class="sxs-lookup"><span data-stu-id="8096c-115">Result: In **Explorer**, the user has **Update** permission to all attribute values for all members in the Mountain Bikes node.</span></span> <span data-ttu-id="8096c-116">Se ocultan todos los demás miembros y atributos.</span><span class="sxs-lookup"><span data-stu-id="8096c-116">All other members and attributes are hidden.</span></span>  
  
 <span data-ttu-id="8096c-117">![mds_conc_overlap_model_example_1](../../2014/master-data-services/media/mds-conc-overlap-model-example-1.gif "mds_conc_overlap_model_example_1")</span><span class="sxs-lookup"><span data-stu-id="8096c-117">![mds_conc_overlap_model_example_1](../../2014/master-data-services/media/mds-conc-overlap-model-example-1.gif "mds_conc_overlap_model_example_1")</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="8096c-118">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="8096c-118">Example 2</span></span>  
 <span data-ttu-id="8096c-119">![mds_conc_overlap_model_2](../../2014/master-data-services/media/mds-conc-overlap-model-2.gif "mds_conc_overlap_model_2")</span><span class="sxs-lookup"><span data-stu-id="8096c-119">![mds_conc_overlap_model_2](../../2014/master-data-services/media/mds-conc-overlap-model-2.gif "mds_conc_overlap_model_2")</span></span>  
  
 <span data-ttu-id="8096c-120">En la pestaña **Modelos** , el atributo Subcategory tiene asignado el permiso **Actualizar** .</span><span class="sxs-lookup"><span data-stu-id="8096c-120">On the **Models** tab, the Subcategory attribute has **Update** permission assigned.</span></span>  
  
 <span data-ttu-id="8096c-121">En la pestaña miembros de la **jerarquía** , el nodo de subcategoría Mountain bikes de una jerarquía derivada tiene asignado explícitamente el permiso **de solo lectura** .</span><span class="sxs-lookup"><span data-stu-id="8096c-121">On the **Hierarchy Members** tab, the Mountain Bikes subcategory node in a derived hierarchy is explicitly assigned **Read-only** permission.</span></span>  
  
 <span data-ttu-id="8096c-122">Resultado: en el **Explorador**, el usuario tiene permiso de **solo lectura** para los valores de atributo de subcategoría para los miembros del nodo Mountain bikes.</span><span class="sxs-lookup"><span data-stu-id="8096c-122">Result: In **Explorer**, the user has **Read-only** permission to the Subcategory attribute values for the members in the Mountain Bikes node.</span></span> <span data-ttu-id="8096c-123">Se ocultan todos los demás miembros y atributos.</span><span class="sxs-lookup"><span data-stu-id="8096c-123">All other members and attributes are hidden.</span></span>  
  
 <span data-ttu-id="8096c-124">![mds_conc_overlap_model_example_2](../../2014/master-data-services/media/mds-conc-overlap-model-example-2.gif "mds_conc_overlap_model_example_2")</span><span class="sxs-lookup"><span data-stu-id="8096c-124">![mds_conc_overlap_model_example_2](../../2014/master-data-services/media/mds-conc-overlap-model-example-2.gif "mds_conc_overlap_model_example_2")</span></span>  
  
## <a name="example-3"></a><span data-ttu-id="8096c-125">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="8096c-125">Example 3</span></span>  
 <span data-ttu-id="8096c-126">![mds_conc_overlap_model_3](../../2014/master-data-services/media/mds-conc-overlap-model-3.gif "mds_conc_overlap_model_3")</span><span class="sxs-lookup"><span data-stu-id="8096c-126">![mds_conc_overlap_model_3](../../2014/master-data-services/media/mds-conc-overlap-model-3.gif "mds_conc_overlap_model_3")</span></span>  
  
 <span data-ttu-id="8096c-127">En la pestaña **modelos** , el atributo subcategory tiene asignado el permiso **de solo lectura** .</span><span class="sxs-lookup"><span data-stu-id="8096c-127">On the **Models** tab, the Subcategory attribute has **Read-only** permission assigned.</span></span>  
  
 <span data-ttu-id="8096c-128">En la pestaña **Miembros** , el nodo de subcategoría de bicicletas de montaña de una jerarquía derivada tiene asignado el permiso **Actualizar** explícitamente.</span><span class="sxs-lookup"><span data-stu-id="8096c-128">On the **Hierarchy Members** tab, the Mountain Bikes subcategory in a derived hierarchy is explicitly assigned **Update** permission.</span></span>  
  
 <span data-ttu-id="8096c-129">Resultado: en el **Explorador**, el usuario tiene permiso de **solo lectura** para los valores de atributo.</span><span class="sxs-lookup"><span data-stu-id="8096c-129">Result: In **Explorer**, the user has **Read-only** permission to the attribute values.</span></span> <span data-ttu-id="8096c-130">Se ocultan todos los demás miembros y atributos.</span><span class="sxs-lookup"><span data-stu-id="8096c-130">All other members and attributes are hidden.</span></span>  
  
 <span data-ttu-id="8096c-131">![mds_conc_overlap_model_example_2](../../2014/master-data-services/media/mds-conc-overlap-model-example-2.gif "mds_conc_overlap_model_example_2")</span><span class="sxs-lookup"><span data-stu-id="8096c-131">![mds_conc_overlap_model_example_2](../../2014/master-data-services/media/mds-conc-overlap-model-example-2.gif "mds_conc_overlap_model_example_2")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8096c-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8096c-132">See Also</span></span>  
 <span data-ttu-id="8096c-133">[Cómo se determinan los permisos &#40;Master Data Services&#41;](how-permissions-are-determined-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="8096c-133">[How Permissions Are Determined &#40;Master Data Services&#41;](how-permissions-are-determined-master-data-services.md) </span></span>  
 [<span data-ttu-id="8096c-134">Superponer permisos de usuario y de grupo &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8096c-134">Overlapping User and Group Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/overlapping-user-and-group-permissions-master-data-services.md)  
  
  
