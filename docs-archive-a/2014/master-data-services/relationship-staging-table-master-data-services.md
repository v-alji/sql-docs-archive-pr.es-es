---
title: Tabla de ensayo de relaciones (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- relationships staging table [Master Data Services]
- database [Master Data Services], relationships table
ms.assetid: e19b6002-67bd-4e7d-9f19-ecb455522b1a
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 529d0521c320ff2e893a2269fe020d191a6ce284
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676026"
---
# <a name="relationship-staging-table-master-data-services"></a><span data-ttu-id="74a55-102">Tabla de ensayo de relaciones (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="74a55-102">Relationship Staging Table (Master Data Services)</span></span>
  <span data-ttu-id="74a55-103">Use la tabla de almacenamiento provisional de relaciones (stg.name_Relationship) en la base de datos de [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] para cambiar la ubicación de los miembros de una jerarquía explícita, en función de las relaciones que tienen los miembros entre sí.</span><span class="sxs-lookup"><span data-stu-id="74a55-103">Use the relationship staging table (stg.name_Relationship) in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database to change the location of members in an explicit hierarchy, based on the relationship the members have to one another.</span></span>  
  
##  <a name="table-columns"></a><a name="TableColumns"></a><span data-ttu-id="74a55-104">Columnas de la tabla</span><span class="sxs-lookup"><span data-stu-id="74a55-104">Table Columns</span></span>  
 <span data-ttu-id="74a55-105">En la tabla siguiente se explica para qué se usa cada uno de los campos de la tabla de ensayo Relationship.</span><span class="sxs-lookup"><span data-stu-id="74a55-105">The following table explains what each of the fields in the Relationship staging table are used for.</span></span>  
  
|<span data-ttu-id="74a55-106">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="74a55-106">Column Name</span></span>|<span data-ttu-id="74a55-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="74a55-107">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="74a55-108">**Id**</span><span class="sxs-lookup"><span data-stu-id="74a55-108">**ID**</span></span>|<span data-ttu-id="74a55-109">Identificador asignado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="74a55-109">An automatically assigned identifier.</span></span> <span data-ttu-id="74a55-110">No especifique ningún valor en este campo.</span><span class="sxs-lookup"><span data-stu-id="74a55-110">Do not enter a value in this field.</span></span> <span data-ttu-id="74a55-111">Si no se ha procesado el lote, este campo está en blanco.</span><span class="sxs-lookup"><span data-stu-id="74a55-111">If the batch has not been processed, this field is blank.</span></span>|  
|<span data-ttu-id="74a55-112">**RelationshipType**</span><span class="sxs-lookup"><span data-stu-id="74a55-112">**RelationshipType**</span></span><br /><br /> <span data-ttu-id="74a55-113">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="74a55-113">Required</span></span>|<span data-ttu-id="74a55-114">Tipo de relación que se está estableciendo.</span><span class="sxs-lookup"><span data-stu-id="74a55-114">The type of relationship that's being set.</span></span> <span data-ttu-id="74a55-115">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="74a55-115">Possible values are:</span></span><br /><br /> <span data-ttu-id="74a55-116">**1**: primario</span><span class="sxs-lookup"><span data-stu-id="74a55-116">**1**:Parent</span></span><br /><br /> <span data-ttu-id="74a55-117">**2**: relacionado (del mismo nivel)</span><span class="sxs-lookup"><span data-stu-id="74a55-117">**2**: Sibling (at the same level)</span></span>|  
|<span data-ttu-id="74a55-118">**ImportStatus_ID**</span><span class="sxs-lookup"><span data-stu-id="74a55-118">**ImportStatus_ID**</span></span><br /><br /> <span data-ttu-id="74a55-119">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="74a55-119">Required</span></span>|<span data-ttu-id="74a55-120">Estado del proceso de importación.</span><span class="sxs-lookup"><span data-stu-id="74a55-120">The status of the import process.</span></span> <span data-ttu-id="74a55-121">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="74a55-121">Possible values are:</span></span><br /><br /> <span data-ttu-id="74a55-122">**0**, que se especifica para indicar que el registro está listo para el almacenamiento provisional.</span><span class="sxs-lookup"><span data-stu-id="74a55-122">**0**, which you specify to indicate that the record is ready for staging.</span></span><br /><br /> <span data-ttu-id="74a55-123">**1**, que se asigna e indica automáticamente que el proceso de almacenamiento provisional del registro ha sido correcto.</span><span class="sxs-lookup"><span data-stu-id="74a55-123">**1**, which is automatically assigned and indicates that the staging process for the record has succeeded.</span></span><br /><br /> <span data-ttu-id="74a55-124">**2**, que se asigna automáticamente e indica que el proceso de almacenamiento provisional del registro no ha sido correcto.</span><span class="sxs-lookup"><span data-stu-id="74a55-124">**2**, which is automatically assigned and indicates that the staging process for the record has failed.</span></span>|  
|<span data-ttu-id="74a55-125">**Batch_ID**</span><span class="sxs-lookup"><span data-stu-id="74a55-125">**Batch_ID**</span></span><br /><br /> <span data-ttu-id="74a55-126">Solo lo necesita el servicio web</span><span class="sxs-lookup"><span data-stu-id="74a55-126">Required by web service only</span></span>|<span data-ttu-id="74a55-127">Identificador asignado automáticamente que agrupa los registros para el almacenamiento provisional.</span><span class="sxs-lookup"><span data-stu-id="74a55-127">An automatically assigned identifier that groups records for staging.</span></span> <span data-ttu-id="74a55-128">A todos los miembros del lote se les asigna este identificador, que se muestra en la columna [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] Id. **de la interfaz de usuario de** .</span><span class="sxs-lookup"><span data-stu-id="74a55-128">All members in the batch are assigned this identifier, which is displayed in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] user interface in the **ID** column.</span></span><br /><br /> <span data-ttu-id="74a55-129">Si no se ha procesado el lote, este campo está en blanco.</span><span class="sxs-lookup"><span data-stu-id="74a55-129">If the batch has not been processed, this field is blank.</span></span>|  
|<span data-ttu-id="74a55-130">**BatchTag**</span><span class="sxs-lookup"><span data-stu-id="74a55-130">**BatchTag**</span></span><br /><br /> <span data-ttu-id="74a55-131">Obligatorio, excepto para el servicio web</span><span class="sxs-lookup"><span data-stu-id="74a55-131">Required, except by web service</span></span>|<span data-ttu-id="74a55-132">Nombre único para el lote, de hasta 50 caracteres.</span><span class="sxs-lookup"><span data-stu-id="74a55-132">A unique name for the batch, up to 50 characters.</span></span>|  
|<span data-ttu-id="74a55-133">**HierarchyName**</span><span class="sxs-lookup"><span data-stu-id="74a55-133">**HierarchyName**</span></span><br /><br /> <span data-ttu-id="74a55-134">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="74a55-134">Required</span></span>|<span data-ttu-id="74a55-135">Nombre de jerarquía explícita.</span><span class="sxs-lookup"><span data-stu-id="74a55-135">The explicit hierarchy name.</span></span> <span data-ttu-id="74a55-136">Cada miembro consolidado solo puede pertenecer a una jerarquía.</span><span class="sxs-lookup"><span data-stu-id="74a55-136">Each consolidated member can belong to one hierarchy only.</span></span>|  
|<span data-ttu-id="74a55-137">**ParentCode**</span><span class="sxs-lookup"><span data-stu-id="74a55-137">**ParentCode**</span></span><br /><br /> <span data-ttu-id="74a55-138">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="74a55-138">Required</span></span>|<span data-ttu-id="74a55-139">Para las relaciones de elementos primarios y secundarios, el código del miembro consolidado que será el elemento primario del miembro secundario hoja o consolidado.</span><span class="sxs-lookup"><span data-stu-id="74a55-139">For parent-child relationships, the code of the consolidated member that will be the parent of the child leaf or consolidated member.</span></span><br /><br /> <span data-ttu-id="74a55-140">Para las relaciones relacionadas, el código de uno de los miembros relacionados.</span><span class="sxs-lookup"><span data-stu-id="74a55-140">For sibling relationships, the code of one of the siblings.</span></span>|  
|<span data-ttu-id="74a55-141">**ChildCode**</span><span class="sxs-lookup"><span data-stu-id="74a55-141">**ChildCode**</span></span><br /><br /> <span data-ttu-id="74a55-142">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="74a55-142">Required</span></span>|<span data-ttu-id="74a55-143">Para las relaciones de elementos primarios y secundarios, el código del miembro consolidado u hoja que será el elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="74a55-143">For parent-child relationships, the code of the consolidated or leaf member that will be the child.</span></span><br /><br /> <span data-ttu-id="74a55-144">Para las relaciones relacionadas, el código de uno de los miembros relacionados.</span><span class="sxs-lookup"><span data-stu-id="74a55-144">For sibling relationships, the code of one of the siblings.</span></span>|  
|<span data-ttu-id="74a55-145">**Criterio de ordenación**</span><span class="sxs-lookup"><span data-stu-id="74a55-145">**Sort Order**</span></span><br /><br /> <span data-ttu-id="74a55-146">Opcional</span><span class="sxs-lookup"><span data-stu-id="74a55-146">Optional</span></span>|<span data-ttu-id="74a55-147">Entero que indica el orden del miembro en relación con los demás miembros bajo el elemento primario.</span><span class="sxs-lookup"><span data-stu-id="74a55-147">An integer that indicates the order of the member in relation to the other members under the parent.</span></span> <span data-ttu-id="74a55-148">Cada miembro secundario debe tener un identificador único.</span><span class="sxs-lookup"><span data-stu-id="74a55-148">Each child member should have a unique identifier.</span></span>|  
|<span data-ttu-id="74a55-149">**ErrorCode**</span><span class="sxs-lookup"><span data-stu-id="74a55-149">**ErrorCode**</span></span>|<span data-ttu-id="74a55-150">Muestra un código de error.</span><span class="sxs-lookup"><span data-stu-id="74a55-150">Displays an error code.</span></span> <span data-ttu-id="74a55-151">Para todos los registros con un **ImportStatus_ID** de **2**, consulte [Errores del proceso de almacenamiento provisional &#40;Master Data Services&#41;](staging-process-errors-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="74a55-151">For all records with a **ImportStatus_ID** of **2**, see [Staging Process Errors &#40;Master Data Services&#41;](staging-process-errors-master-data-services.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="74a55-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="74a55-152">See Also</span></span>  
 <span data-ttu-id="74a55-153">[Mueva los miembros de la jerarquía explícita mediante el proceso de almacenamiento provisional &#40;Master Data Services&#41;](add-update-and-delete-data-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="74a55-153">[Move Explicit Hierarchy Members by Using the Staging Process &#40;Master Data Services&#41;](add-update-and-delete-data-master-data-services.md) </span></span>  
 <span data-ttu-id="74a55-154">[Master Data Services de &#40;de importación de datos&#41;](overview-importing-data-from-tables-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="74a55-154">[Data Import &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md) </span></span>  
 <span data-ttu-id="74a55-155">[Ver los errores que se producen durante el proceso de almacenamiento provisional &#40;Master Data Services&#41;](view-errors-that-occur-during-staging-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="74a55-155">[View Errors that Occur During the Staging Process &#40;Master Data Services&#41;](view-errors-that-occur-during-staging-master-data-services.md) </span></span>  
 [<span data-ttu-id="74a55-156">Errores del proceso de almacenamiento provisional &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="74a55-156">Staging Process Errors &#40;Master Data Services&#41;</span></span>](staging-process-errors-master-data-services.md)  
  
  