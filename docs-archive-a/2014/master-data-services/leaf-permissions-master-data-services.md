---
title: Permisos de hoja (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attribute groups [Master Data Services], permissions
- members [Master Data Services], leaf member permissions
- permissions [Master Data Services], leaf members
- leaf members [Master Data Services], attribute permissions
- attributes [Master Data Services], leaf member attribute permissions
ms.assetid: bde16e8c-bcd4-4041-8130-55c5450e5f72
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 794e1d138b91e896b8df16765ae8984c6e60aca7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748817"
---
# <a name="leaf-permissions-master-data-services"></a><span data-ttu-id="2beca-102">Permisos de hoja (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="2beca-102">Leaf Permissions (Master Data Services)</span></span>
  <span data-ttu-id="2beca-103">Los permisos de hoja se aplican a los valores de atributo de todos los miembros hoja de una entidad.</span><span class="sxs-lookup"><span data-stu-id="2beca-103">Leaf permissions apply to the attribute values for all leaf members of an entity.</span></span>  
  
 <span data-ttu-id="2beca-104">Para las entidades sin jerarquías explícitas habilitadas, la asignación de un permiso a **Hoja** es equivalente a asignar un permiso a la entidad.</span><span class="sxs-lookup"><span data-stu-id="2beca-104">For entities without explicit hierarchies enabled, assigning permission to **Leaf** is the same as assigning permission to the entity.</span></span>  
  
 <span data-ttu-id="2beca-105">**Notas:**</span><span class="sxs-lookup"><span data-stu-id="2beca-105">**Notes:**</span></span>  
  
-   <span data-ttu-id="2beca-106">Los permisos de hoja solo se aplican al área funcional del **Explorador** de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="2beca-106">Leaf permissions apply to the **Explorer** functional area of the user interface only.</span></span>  
  
-   <span data-ttu-id="2beca-107">Los permisos asignados a **Nombre** y a los atributos de **Código** no se aplican.</span><span class="sxs-lookup"><span data-stu-id="2beca-107">Permissions assigned to **Name** and **Code** attributes are not enforced.</span></span>  
  
|<span data-ttu-id="2beca-108">Permiso</span><span class="sxs-lookup"><span data-stu-id="2beca-108">Permission</span></span>|<span data-ttu-id="2beca-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="2beca-109">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="2beca-110">**Solo lectura**</span><span class="sxs-lookup"><span data-stu-id="2beca-110">**Read-only**</span></span>|<span data-ttu-id="2beca-111">Se muestran los miembros hoja, pero el usuario no los puede agregar, quitar o cambiar.</span><span class="sxs-lookup"><span data-stu-id="2beca-111">Leaf members are displayed but the user cannot add, remove, or change them.</span></span><br /><br /> <span data-ttu-id="2beca-112">Si hay miembros consolidados, se muestran los nombres y códigos pero el usuario no los puede agregar, quitar o cambiar.</span><span class="sxs-lookup"><span data-stu-id="2beca-112">If consolidated members exist, the names and codes are displayed but the user cannot add, remove, or change them.</span></span>|  
|<span data-ttu-id="2beca-113">**Actualizar**</span><span class="sxs-lookup"><span data-stu-id="2beca-113">**Update**</span></span>|<span data-ttu-id="2beca-114">Se muestran los miembros hoja y el usuario los puede agregar, quitar y cambiar.</span><span class="sxs-lookup"><span data-stu-id="2beca-114">Leaf members are displayed and the user can add, remove, and change them.</span></span><br /><br /> <span data-ttu-id="2beca-115">Si hay miembros consolidados, se muestran los nombres y códigos pero el usuario no los puede agregar, quitar o cambiar.</span><span class="sxs-lookup"><span data-stu-id="2beca-115">If consolidated members exist, the names and codes are displayed but the user cannot add, remove, or change them.</span></span>|  
|<span data-ttu-id="2beca-116">**Denegar**</span><span class="sxs-lookup"><span data-stu-id="2beca-116">**Deny**</span></span>|<span data-ttu-id="2beca-117">No se muestran los miembros hoja para la entidad.</span><span class="sxs-lookup"><span data-stu-id="2beca-117">Leaf members for the entity are not displayed.</span></span>|  
  
## <a name="attribute-permissions"></a><span data-ttu-id="2beca-118">Permisos de atributo</span><span class="sxs-lookup"><span data-stu-id="2beca-118">Attribute Permissions</span></span>  
 <span data-ttu-id="2beca-119">Los permisos de atributo se aplican a los valores del atributo para la entidad concreta.</span><span class="sxs-lookup"><span data-stu-id="2beca-119">Attribute permissions apply to the attribute's values for the specific entity.</span></span> <span data-ttu-id="2beca-120">Los usuarios que tengan únicamente permisos de atributo no pueden agregar o quitar miembros.</span><span class="sxs-lookup"><span data-stu-id="2beca-120">Users with attribute permissions only cannot add or remove members.</span></span>  
  
|<span data-ttu-id="2beca-121">Permiso</span><span class="sxs-lookup"><span data-stu-id="2beca-121">Permission</span></span>|<span data-ttu-id="2beca-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="2beca-122">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="2beca-123">**Solo lectura**</span><span class="sxs-lookup"><span data-stu-id="2beca-123">**Read-only**</span></span>|<span data-ttu-id="2beca-124">Se muestra el atributo, pero el usuario no puede cambiar los valores de atributo.</span><span class="sxs-lookup"><span data-stu-id="2beca-124">The attribute is displayed but the user cannot change attribute values.</span></span>|  
|<span data-ttu-id="2beca-125">**Actualizar**</span><span class="sxs-lookup"><span data-stu-id="2beca-125">**Update**</span></span>|<span data-ttu-id="2beca-126">Se muestra el atributo y el usuario puede cambiar los valores de atributo.</span><span class="sxs-lookup"><span data-stu-id="2beca-126">The attribute is displayed and the user can change attribute values.</span></span>|  
|<span data-ttu-id="2beca-127">**Denegar**</span><span class="sxs-lookup"><span data-stu-id="2beca-127">**Deny**</span></span>|<span data-ttu-id="2beca-128">No se muestra el atributo.</span><span class="sxs-lookup"><span data-stu-id="2beca-128">The attribute is not displayed.</span></span><br /><br /> <span data-ttu-id="2beca-129">Nota: No puede denegar explícitamente el acceso a los atributos Name y Code.</span><span class="sxs-lookup"><span data-stu-id="2beca-129">Note: You cannot explicitly deny access to Name and Code attributes.</span></span>|  
  
### <a name="example"></a><span data-ttu-id="2beca-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2beca-130">Example</span></span>  
 <span data-ttu-id="2beca-131">Para la entidad Product, asigne el permiso **Actualizar** al atributo Subcategory.</span><span class="sxs-lookup"><span data-stu-id="2beca-131">For the Product entity, assign **Update** permission to Subcategory attribute.</span></span> <span data-ttu-id="2beca-132">Deniegue el permiso al resto de los atributos.</span><span class="sxs-lookup"><span data-stu-id="2beca-132">Deny permission to all other attributes.</span></span>  
  
|<span data-ttu-id="2beca-133">Nombre</span><span class="sxs-lookup"><span data-stu-id="2beca-133">Name</span></span>|<span data-ttu-id="2beca-134">Código</span><span class="sxs-lookup"><span data-stu-id="2beca-134">Code</span></span>|<span data-ttu-id="2beca-135">Subcategory (actualizar)</span><span class="sxs-lookup"><span data-stu-id="2beca-135">Subcategory (Update)</span></span>|  
|----------|----------|----------------------------|  
|<span data-ttu-id="2beca-136">Mountain-100</span><span class="sxs-lookup"><span data-stu-id="2beca-136">Mountain-100</span></span>|<span data-ttu-id="2beca-137">BK-M101</span><span class="sxs-lookup"><span data-stu-id="2beca-137">BK-M101</span></span>|<span data-ttu-id="2beca-138">{5}Bicicletas de montaña</span><span class="sxs-lookup"><span data-stu-id="2beca-138">{5} Mountain Bikes</span></span>|  
|<span data-ttu-id="2beca-139">Mountain-100</span><span class="sxs-lookup"><span data-stu-id="2beca-139">Mountain-100</span></span>|<span data-ttu-id="2beca-140">BK-M201</span><span class="sxs-lookup"><span data-stu-id="2beca-140">BK-M201</span></span>|<span data-ttu-id="2beca-141">{5}Bicicletas de montaña</span><span class="sxs-lookup"><span data-stu-id="2beca-141">{5} Mountain Bikes</span></span>|  
  
 <span data-ttu-id="2beca-142">En el **Explorador**, puede actualizar cualquier valor de atributo en la columna Subcategory.</span><span class="sxs-lookup"><span data-stu-id="2beca-142">In **Explorer**, you can update any attribute value in the Subcategory column.</span></span> <span data-ttu-id="2beca-143">Si no dispone del permiso para un atributo, este no se mostrará.</span><span class="sxs-lookup"><span data-stu-id="2beca-143">If you do not have permission to an attribute, the attribute is not displayed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2beca-144">En este ejemplo, Subcategory es un atributo basado en dominio, que depende de la entidad SubcategoryList.</span><span class="sxs-lookup"><span data-stu-id="2beca-144">In this example, Subcategory is a domain-based attribute, based on the SubcategoryList entity.</span></span> <span data-ttu-id="2beca-145">Puede seleccionar una subcategoría diferente para Mountain-100, pero no puede agregar o eliminar miembros en la entidad SubcategoryList.</span><span class="sxs-lookup"><span data-stu-id="2beca-145">You can select a different subcategory for Mountain-100 but you cannot add members to or delete members from the SubcategoryList entity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2beca-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2beca-146">See Also</span></span>  
 <span data-ttu-id="2beca-147">[Asignar permisos de objeto de modelo &#40;Master Data Services&#41;](assign-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="2beca-147">[Assign Model Object Permissions &#40;Master Data Services&#41;](assign-model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="2beca-148">[Permisos consolidados &#40;Master Data Services&#41;](../../2014/master-data-services/consolidated-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="2beca-148">[Consolidated Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/consolidated-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="2beca-149">[Permisos del objeto de modelo &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="2beca-149">[Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="2beca-150">[Miembros &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="2beca-150">[Members &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span></span>  
 [<span data-ttu-id="2beca-151">Atributos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="2beca-151">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)  
  
  
