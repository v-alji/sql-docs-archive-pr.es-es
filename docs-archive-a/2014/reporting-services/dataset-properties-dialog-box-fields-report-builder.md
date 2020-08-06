---
title: Propiedades del conjunto de propiedades (cuadro de diálogo), campos (Generador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10021"
ms.assetid: 75c7e54a-3d20-4c9a-88da-ab36dce2ce42
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2b766aa23cce390bc3ffdcf10efdb38efc91f3e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669531"
---
# <a name="dataset-properties-dialog-box-fields-report-builder"></a><span data-ttu-id="b2e05-102">Propiedades del conjunto de datos (cuadro de diálogo), Campos (Generador de informes)</span><span class="sxs-lookup"><span data-stu-id="b2e05-102">Dataset Properties Dialog Box, Fields (Report Builder)</span></span>
  <span data-ttu-id="b2e05-103">Seleccione **Campos** en el cuadro de diálogo **Propiedades del conjunto de datos** para cambiar la colección de campos para el conjunto de datos del informe.</span><span class="sxs-lookup"><span data-stu-id="b2e05-103">Select **Fields** on the **Dataset Properties** dialog box to change the field collection for the report dataset.</span></span> <span data-ttu-id="b2e05-104">La lista de campos se rellena automáticamente, pero puede utilizar **Campos** para agregar, editar y eliminar campos calculados y de consulta.</span><span class="sxs-lookup"><span data-stu-id="b2e05-104">The fields list is automatically populated, but you can use **Fields** to add, edit, and delete query and calculated fields.</span></span>  
  
 <span data-ttu-id="b2e05-105">Los campos calculados solo se admiten en conjuntos de datos insertados.</span><span class="sxs-lookup"><span data-stu-id="b2e05-105">Calculated fields are supported only on embedded datasets.</span></span> <span data-ttu-id="b2e05-106">Para más información, vea [Conjuntos de datos incrustados y compartidos de informe &#40;Generador de informes y SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="b2e05-106">For more information, see [Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="b2e05-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="b2e05-107">Options</span></span>  
 <span data-ttu-id="b2e05-108">**Add (Agregar)**</span><span class="sxs-lookup"><span data-stu-id="b2e05-108">**Add**</span></span>  
 <span data-ttu-id="b2e05-109">Agrega un nuevo campo calculado o de consulta al conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="b2e05-109">Add a new query or calculated field to the dataset.</span></span>  
  
 <span data-ttu-id="b2e05-110">**Eliminar**</span><span class="sxs-lookup"><span data-stu-id="b2e05-110">**Delete**</span></span>  
 <span data-ttu-id="b2e05-111">Elimina el campo seleccionado del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="b2e05-111">Delete the selected field from the dataset.</span></span>  
  
 <span data-ttu-id="b2e05-112">**Nombre del campo**</span><span class="sxs-lookup"><span data-stu-id="b2e05-112">**Field Name**</span></span>  
 <span data-ttu-id="b2e05-113">Escriba el nombre del campo.</span><span class="sxs-lookup"><span data-stu-id="b2e05-113">Type a name for the field.</span></span> <span data-ttu-id="b2e05-114">El campo debe ser único en el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="b2e05-114">The field must be unique within the dataset.</span></span> <span data-ttu-id="b2e05-115">Para cada campo existente en el conjunto de datos, el nombre se rellena previamente.</span><span class="sxs-lookup"><span data-stu-id="b2e05-115">For each existing field in the dataset, the name is pre-populated.</span></span>  
  
 <span data-ttu-id="b2e05-116">**Origen del campo**</span><span class="sxs-lookup"><span data-stu-id="b2e05-116">**Field Source**</span></span>  
 <span data-ttu-id="b2e05-117">Escriba un valor para el campo.</span><span class="sxs-lookup"><span data-stu-id="b2e05-117">Enter a value for the field.</span></span>  
  
 <span data-ttu-id="b2e05-118">Para un campo calculado, el origen del campo debe ser el nombre de un campo existente recuperado por la consulta del conjunto de datos o por una expresión que cree personalmente.</span><span class="sxs-lookup"><span data-stu-id="b2e05-118">For a calculated field, the field source must be the name of an existing field retrieved by the dataset query, or an expression that you create.</span></span> <span data-ttu-id="b2e05-119">Por ejemplo, para crear un campo que representa 10 veces el valor en el campo de consulta Sales, utilice la expresión `=10 * Fields!Sales.Value`.</span><span class="sxs-lookup"><span data-stu-id="b2e05-119">For example, to create a field that represents 10 times the value in the query field Sales, use the expression `=10 * Fields!Sales.Value`.</span></span>  
  
 <span data-ttu-id="b2e05-120">En el caso de un campo de consultas, el origen del campo debe ser el nombre de un campo existente recuperado por la consulta de conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="b2e05-120">For a query field, the field source must be the name of an existing field retrieved by the dataset query.</span></span>  
  
 <span data-ttu-id="b2e05-121">**Expresión (fx)**</span><span class="sxs-lookup"><span data-stu-id="b2e05-121">**Expression (fx)**</span></span>  
 <span data-ttu-id="b2e05-122">Agregue o cambie una expresión para el nuevo campo calculado.</span><span class="sxs-lookup"><span data-stu-id="b2e05-122">Add or change an expression for the new calculated field.</span></span> <span data-ttu-id="b2e05-123">Este botón solamente aparece cuando se hace clic en **Agregar** y se selecciona **Campo calculado**.</span><span class="sxs-lookup"><span data-stu-id="b2e05-123">This button only appears when you click **Add** and select **Calculated Field**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2e05-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b2e05-124">See Also</span></span>  
 <span data-ttu-id="b2e05-125">[Colección Campos del conjunto de datos &#40;Generador de informes y SSRS&#41;](report-data/dataset-fields-collection-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b2e05-125">[Dataset Fields Collection &#40;Report Builder and SSRS&#41;](report-data/dataset-fields-collection-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b2e05-126">[Crear un conjunto de DataSet compartido o un conjunto de &#40;incrustado Generador de informes y SSRS&#41;](report-data/create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b2e05-126">[Create a Shared Dataset or Embedded Dataset &#40;Report Builder and SSRS&#41;](report-data/create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b2e05-127">[Generador de informes ayuda para cuadros de diálogo, paneles y asistentes](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="b2e05-127">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 <span data-ttu-id="b2e05-128">[Propiedades del conjunto de propiedades (cuadro de diálogo), opciones &#40;Generador de informes&#41;](report-data/dataset-properties-dialog-box-options-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="b2e05-128">[Dataset Properties Dialog Box, Options &#40;Report Builder&#41;](report-data/dataset-properties-dialog-box-options-report-builder.md) </span></span>  
 <span data-ttu-id="b2e05-129">[Propiedades del conjunto de propiedades (cuadro de diálogo), filtros &#40;Generador de informes&#41;](../../2014/reporting-services/dataset-properties-dialog-box-filters-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="b2e05-129">[Dataset Properties Dialog Box, Filters &#40;Report Builder&#41;](../../2014/reporting-services/dataset-properties-dialog-box-filters-report-builder.md) </span></span>  
 <span data-ttu-id="b2e05-130">[Propiedades del conjunto de propiedades (cuadro de diálogo), parámetros &#40;Generador de informes&#41;](../../2014/reporting-services/dataset-properties-dialog-box-parameters-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="b2e05-130">[Dataset Properties Dialog Box, Parameters &#40;Report Builder&#41;](../../2014/reporting-services/dataset-properties-dialog-box-parameters-report-builder.md) </span></span>  
 <span data-ttu-id="b2e05-131">[Cuadro de diálogo Propiedades del conjunto de propiedades, &#40;de consultas Generador de informes&#41;](report-data/dataset-properties-dialog-box-query-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="b2e05-131">[Dataset Properties Dialog Box, Query &#40;Report Builder&#41;](report-data/dataset-properties-dialog-box-query-report-builder.md) </span></span>  
 <span data-ttu-id="b2e05-132">[Expresiones &#40;Generador de informes y SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b2e05-132">[Expressions &#40;Report Builder and SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="b2e05-133">Conexiones de datos, orígenes de datos y cadenas de conexión en el Generador de informes</span><span class="sxs-lookup"><span data-stu-id="b2e05-133">Data Connections, Data Sources, and Connection Strings in Report Builder</span></span>](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-report-builder.md)  
  
  
