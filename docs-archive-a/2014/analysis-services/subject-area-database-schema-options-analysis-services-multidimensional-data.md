---
title: Opciones de esquema de la base de datos del área de asunto (Asistente para generar esquemas) (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.schemagenwizard.subjectareaschemaopts.f1
ms.assetid: 4c109bb8-e19d-412b-908f-bfdd7f872439
author: minewiskan
ms.author: owend
ms.openlocfilehash: 98460332478d02de823addcd113fb9c1e87d6958
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671711"
---
# <a name="subject-area-database-schema-options-schema-generation-wizard-analysis-services---multidimensional-data"></a><span data-ttu-id="cd023-102">Opciones de esquema de la base de datos del área de asunto (Asistente para generar esquemas) (Analysis Services - Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="cd023-102">Subject Area Database Schema Options (Schema Generation Wizard) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="cd023-103">Use la página **Opciones de esquema de la base de datos del área de asunto** para controlar cómo se genera el esquema y definir cómo se mantienen los datos.</span><span class="sxs-lookup"><span data-stu-id="cd023-103">Use the **Subject Area Database Schema Options** page to control how the schema is generated, as well as to define how data is preserved.</span></span>  
  
## <a name="options"></a><span data-ttu-id="cd023-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="cd023-104">Options</span></span>  
 <span data-ttu-id="cd023-105">**Esquema de propiedad**</span><span class="sxs-lookup"><span data-stu-id="cd023-105">**Owning schema**</span></span>  
 <span data-ttu-id="cd023-106">Especifica el nombre del esquema dentro de la nueva base de datos de área de asunto.</span><span class="sxs-lookup"><span data-stu-id="cd023-106">Specifies the name of the schema within the new subject area database.</span></span>  
  
 <span data-ttu-id="cd023-107">**Crear claves principales en tablas de dimensiones**</span><span class="sxs-lookup"><span data-stu-id="cd023-107">**Create primary keys on dimension tables**</span></span>  
 <span data-ttu-id="cd023-108">Crea claves principales en las tablas de dimensiones en el esquema generado.</span><span class="sxs-lookup"><span data-stu-id="cd023-108">Creates primary keys on the dimension tables in the generated schema.</span></span> <span data-ttu-id="cd023-109">Si no selecciona esta opción, no se genera ningún índice.</span><span class="sxs-lookup"><span data-stu-id="cd023-109">No index is generated if you do not select this option.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cd023-110">Si no selecciona esta opción, se exige integridad referencial.</span><span class="sxs-lookup"><span data-stu-id="cd023-110">If you do not select this option, referential integrity is enforced.</span></span>  
  
 <span data-ttu-id="cd023-111">**Creación de índices**</span><span class="sxs-lookup"><span data-stu-id="cd023-111">**Create indexes**</span></span>  
 <span data-ttu-id="cd023-112">Crea índices en columnas de clave externa en el esquema generado.</span><span class="sxs-lookup"><span data-stu-id="cd023-112">Creates indexes on foreign key columns in the generated schema.</span></span>  
  
 <span data-ttu-id="cd023-113">**Exigir integridad referencial**</span><span class="sxs-lookup"><span data-stu-id="cd023-113">**Enforce referential integrity**</span></span>  
 <span data-ttu-id="cd023-114">Exige integridad referencial en el esquema generado.</span><span class="sxs-lookup"><span data-stu-id="cd023-114">Enforces referential integrity within the generated schema.</span></span> <span data-ttu-id="cd023-115">Si no selecciona esta opción, las relaciones se crean, pero no se exigen.</span><span class="sxs-lookup"><span data-stu-id="cd023-115">If you do not select this option, relationships are created but not enforced.</span></span>  
  
 <span data-ttu-id="cd023-116">**Mantener los datos al volver a generar**</span><span class="sxs-lookup"><span data-stu-id="cd023-116">**Preserve data on regeneration**</span></span>  
 <span data-ttu-id="cd023-117">Mantiene la base de datos del área de asunto cuando el asistente termina.</span><span class="sxs-lookup"><span data-stu-id="cd023-117">Retains data in the subject area database when the wizard finishes.</span></span> <span data-ttu-id="cd023-118">Si no selecciona esta opción, todos los datos de la base de datos del área de asunto se pueden eliminar sin previo aviso.</span><span class="sxs-lookup"><span data-stu-id="cd023-118">If you do not select this option, all the data in the subject area database may be erased without warning.</span></span>  
  
 <span data-ttu-id="cd023-119">**Llenar la tabla de tiempos**</span><span class="sxs-lookup"><span data-stu-id="cd023-119">**Populate time table(s)**</span></span>  
 <span data-ttu-id="cd023-120">Especifica cómo rellena el asistente las tablas de tiempos.</span><span class="sxs-lookup"><span data-stu-id="cd023-120">Specifies how the wizard populates the time tables.</span></span> <span data-ttu-id="cd023-121">En la siguiente tabla se describen los posibles valores para esta opción.</span><span class="sxs-lookup"><span data-stu-id="cd023-121">The following table describes the possible values for this option.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cd023-122">Esta opción solo está habilitada si se realiza una llamada al Asistente para generar esquemas desde un proyecto de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , con [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] en modo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="cd023-122">This option is enabled only if Schema Generation Wizard is called from an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, using [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] in project mode.</span></span>  
  
|<span data-ttu-id="cd023-123">Value</span><span class="sxs-lookup"><span data-stu-id="cd023-123">Value</span></span>|<span data-ttu-id="cd023-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="cd023-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cd023-125">Llenar</span><span class="sxs-lookup"><span data-stu-id="cd023-125">Populate</span></span>|<span data-ttu-id="cd023-126">Las tablas de tiempos del área de asunto se llenan.</span><span class="sxs-lookup"><span data-stu-id="cd023-126">The subject area time tables are populated.</span></span>|  
|<span data-ttu-id="cd023-127">No llenar</span><span class="sxs-lookup"><span data-stu-id="cd023-127">Do not populate</span></span>|<span data-ttu-id="cd023-128">Las tablas de tiempos del área de asunto no se llenan.</span><span class="sxs-lookup"><span data-stu-id="cd023-128">The subject area time tables are not populated.</span></span>|  
|<span data-ttu-id="cd023-129">Llenar solamente si está vacía</span><span class="sxs-lookup"><span data-stu-id="cd023-129">Populate only if empty</span></span>|<span data-ttu-id="cd023-130">Las tablas de tiempos del área de asunto se llenan solo si están vacías.</span><span class="sxs-lookup"><span data-stu-id="cd023-130">The subject area time tables are populated only if they are empty.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cd023-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cd023-131">See Also</span></span>  
 [<span data-ttu-id="cd023-132">Asistente para generar esquemas ayuda F1 &#40;Analysis Services-datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="cd023-132">Schema Generation Wizard F1 Help &#40;Analysis Services - Multidimensional Data&#41;</span></span>](schema-generation-wizard-f1-help-analysis-services-multidimensional-data.md)  
  
  
