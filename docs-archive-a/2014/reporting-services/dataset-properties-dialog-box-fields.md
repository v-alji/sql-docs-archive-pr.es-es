---
title: Propiedades del conjunto de propiedades (cuadro de diálogo), campos | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.datasetproperties.fields.f1
- "10140"
ms.assetid: e1367556-736e-4a6b-b9e7-10432a3e50b5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1b9d315f85751c0f73896e809a522613fefece5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669530"
---
# <a name="dataset-properties-dialog-box-fields"></a><span data-ttu-id="ed64d-102">Propiedades del conjunto de datos (cuadro de diálogo), Campos</span><span class="sxs-lookup"><span data-stu-id="ed64d-102">Dataset Properties Dialog Box, Fields</span></span>
  <span data-ttu-id="ed64d-103">Seleccione **Campos** en el cuadro de diálogo **Propiedades del conjunto de datos** para cambiar la colección de campos para el conjunto de datos del informe.</span><span class="sxs-lookup"><span data-stu-id="ed64d-103">Select **Fields** on the **Dataset Properties** dialog box to change the field collection for the report dataset.</span></span> <span data-ttu-id="ed64d-104">La lista de campos se rellena automáticamente, pero puede utilizar **Campos** para agregar, editar y eliminar campos calculados y de consulta.</span><span class="sxs-lookup"><span data-stu-id="ed64d-104">The fields list is automatically populated, but you can use **Fields** to add, edit, and delete query and calculated fields.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ed64d-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="ed64d-105">Options</span></span>  
 <span data-ttu-id="ed64d-106">**Add (Agregar)**</span><span class="sxs-lookup"><span data-stu-id="ed64d-106">**Add**</span></span>  
 <span data-ttu-id="ed64d-107">Agrega un nuevo campo de consulta o campo calculado al conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="ed64d-107">Add a new query field or calculated field to the dataset.</span></span>  
  
 <span data-ttu-id="ed64d-108">**Eliminar**</span><span class="sxs-lookup"><span data-stu-id="ed64d-108">**Delete**</span></span>  
 <span data-ttu-id="ed64d-109">Elimina el campo seleccionado del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="ed64d-109">Delete the selected field from the dataset.</span></span>  
  
 <span data-ttu-id="ed64d-110">**Nombre del campo**</span><span class="sxs-lookup"><span data-stu-id="ed64d-110">**Field Name**</span></span>  
 <span data-ttu-id="ed64d-111">Escriba el nombre del campo.</span><span class="sxs-lookup"><span data-stu-id="ed64d-111">Type a name for the field.</span></span> <span data-ttu-id="ed64d-112">El campo debe ser único en el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="ed64d-112">The field must be unique within the dataset.</span></span> <span data-ttu-id="ed64d-113">Para cada campo existente en la consulta del conjunto de datos, el nombre se rellena previamente.</span><span class="sxs-lookup"><span data-stu-id="ed64d-113">For each existing field in the dataset query, the name is pre-populated.</span></span>  
  
 <span data-ttu-id="ed64d-114">**Origen del campo**</span><span class="sxs-lookup"><span data-stu-id="ed64d-114">**Field Source**</span></span>  
 <span data-ttu-id="ed64d-115">Escriba un valor para el campo.</span><span class="sxs-lookup"><span data-stu-id="ed64d-115">Enter a value for the field.</span></span>  
  
 <span data-ttu-id="ed64d-116">Para un campo calculado, el origen del campo debe ser el nombre de un campo existente recuperado por la consulta del conjunto de datos o por una expresión que cree personalmente.</span><span class="sxs-lookup"><span data-stu-id="ed64d-116">For a calculated field, the field source must be the name of an existing field retrieved by the dataset query, or an expression that you create.</span></span> <span data-ttu-id="ed64d-117">Por ejemplo, para crear un campo que representa 10 veces el valor en el campo de consulta Sales, utilice la expresión `=10 * Fields!Sales.Value`.</span><span class="sxs-lookup"><span data-stu-id="ed64d-117">For example, to create a field that represents 10 times the value in the query field Sales, use the expression `=10 * Fields!Sales.Value`.</span></span>  
  
 <span data-ttu-id="ed64d-118">En el caso de un campo de consultas, el origen del campo debe ser el nombre de un campo existente recuperado por la consulta de conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="ed64d-118">For a query field, the field source must be the name of an existing field retrieved by the dataset query.</span></span>  
  
 <span data-ttu-id="ed64d-119">**Expresión (fx)**</span><span class="sxs-lookup"><span data-stu-id="ed64d-119">**Expression (fx)**</span></span>  
 <span data-ttu-id="ed64d-120">Agregue o cambie una expresión para el campo calculado.</span><span class="sxs-lookup"><span data-stu-id="ed64d-120">Add or change an expression for the calculated field.</span></span> <span data-ttu-id="ed64d-121">Este botón solamente aparece cuando se hace clic en **Agregar** y se selecciona **Campo calculado**.</span><span class="sxs-lookup"><span data-stu-id="ed64d-121">This button only appears when you click **Add** and select **Calculated Field**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed64d-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ed64d-122">See Also</span></span>  
 <span data-ttu-id="ed64d-123">[Colección Campos del conjunto de datos &#40;Generador de informes y SSRS&#41;](report-data/dataset-fields-collection-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ed64d-123">[Dataset Fields Collection &#40;Report Builder and SSRS&#41;](report-data/dataset-fields-collection-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ed64d-124">[Agregar datos a un informe &#40;Generador de informes y SSRS&#41;](report-data/report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ed64d-124">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-data/report-datasets-ssrs.md) </span></span>  
 [<span data-ttu-id="ed64d-125">Expresiones &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ed64d-125">Expressions &#40;Report Builder and SSRS&#41;</span></span>](report-design/expressions-report-builder-and-ssrs.md)  
  
  
