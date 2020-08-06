---
title: Agregar, editar y actualizar campos en el panel Datos de informe (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2e36f0fe-8100-4513-b169-14d611646f81
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2a20880b84383fc5d9f96c5611419a08facb9ac2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662602"
---
# <a name="add-edit-refresh-fields-in-the-report-data-pane-report-builder-and-ssrs"></a><span data-ttu-id="5280b-102">Agregar, editar y actualizar campos en el panel Datos de informe (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="5280b-102">Add, Edit, Refresh Fields in the Report Data Pane (Report Builder and SSRS)</span></span>
  <span data-ttu-id="5280b-103">Los campos de conjunto de datos son la colección integrada de nombres de campo que representan los datos que se devuelven cuando una consulta de conjunto de datos se ejecuta en un origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="5280b-103">Dataset fields are the built-in collection of field names that represent the data that is returned when a dataset query runs on an external data source.</span></span>  
  
 <span data-ttu-id="5280b-104">En un conjunto de datos incrustado, los campos de conjunto de datos son los que se crean cuando se termina de generar una consulta y se cierra el panel del Diseñador de consultas y los campos calculados que se crean.</span><span class="sxs-lookup"><span data-stu-id="5280b-104">For an embedded dataset, the dataset fields are the fields that are created after you finish building a query and close the Query Designer pane, and calculated fields that you create.</span></span>  
  
 <span data-ttu-id="5280b-105">En un conjunto de datos compartido, los campos de conjunto de datos son los de la definición del conjunto de datos compartido cuando se agregó al informe.</span><span class="sxs-lookup"><span data-stu-id="5280b-105">For a shared dataset, the dataset fields are the fields from the shared dataset definition when you added it to your report.</span></span> <span data-ttu-id="5280b-106">Aunque la consulta del conjunto de datos compartido del servidor de informes siempre se utiliza al ejecutar el informe, la lista de campos de conjunto de datos del informe es estática.</span><span class="sxs-lookup"><span data-stu-id="5280b-106">Although the query from the shared dataset on the report server is always used when you run the report, the list of dataset fields in the report is static.</span></span>  
  
 <span data-ttu-id="5280b-107">Use **Actualizar campos** para actualizar la lista de campos en el informe de modo que coincida con la lista actual de campos de la consulta del conjunto de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="5280b-107">Use **Refresh Fields** to update the list of fields in the report to match the current list of fields from the shared dataset query.</span></span> <span data-ttu-id="5280b-108">Actualizar la lista de campos no afecta a los campos calculados que defina en un informe.</span><span class="sxs-lookup"><span data-stu-id="5280b-108">Refreshing the field list does not affect the calculated fields that you define in your report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-query-field"></a><span data-ttu-id="5280b-109">Para agregar un campo de consulta</span><span class="sxs-lookup"><span data-stu-id="5280b-109">To add a query field</span></span>  
  
1.  <span data-ttu-id="5280b-110">En el panel Datos de informe, haga clic con el botón derecho en el conjunto de datos y, después, haga clic en **Agregar campo de consulta**.</span><span class="sxs-lookup"><span data-stu-id="5280b-110">In the Report Data pane, right-click the dataset, and then click **Add Query Field**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5280b-111">Si no puede ver el panel Datos de informe, en el menú **Ver** , haga clic en **Datos de informe**.</span><span class="sxs-lookup"><span data-stu-id="5280b-111">If you cannot see the Report Data pane, from the **View** menu, click **Report Data**.</span></span>  
  
2.  <span data-ttu-id="5280b-112">En la página **Campos** del cuadro de diálogo **Propiedades del conjunto de datos** , haga clic en **Agregar**y, a continuación, haga clic en **Campo de consulta**.</span><span class="sxs-lookup"><span data-stu-id="5280b-112">In the **Fields** page of the **Dataset Properties** dialog box, click **Add**, and then click **Query Field**.</span></span> <span data-ttu-id="5280b-113">En la parte inferior de la cuadrícula se agrega una nueva fila.</span><span class="sxs-lookup"><span data-stu-id="5280b-113">A new row is added to the bottom of the grid.</span></span>  
  
3.  <span data-ttu-id="5280b-114">En el cuadro de texto **Nombre de campo** , escriba el nombre del campo.</span><span class="sxs-lookup"><span data-stu-id="5280b-114">In the **Field Name** text box, type the name for the field.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5280b-115">El nombre debe ser único en el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="5280b-115">Names must be unique in the dataset.</span></span>  
  
4.  <span data-ttu-id="5280b-116">En el cuadro de texto **Origen del campo** , escriba el nombre de un campo existente en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="5280b-116">In the **Field Source** text box, type the name of an existing field on the data source.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-add-a-calculated-field"></a><span data-ttu-id="5280b-117">Para agregar un campo calculado</span><span class="sxs-lookup"><span data-stu-id="5280b-117">To add a calculated field</span></span>  
  
1.  <span data-ttu-id="5280b-118">En el panel Datos de informe, haga clic con el botón derecho en el conjunto de datos y, después, haga clic en **Agregar campo calculado**.</span><span class="sxs-lookup"><span data-stu-id="5280b-118">In the Report Data pane, right-click the dataset, and then click **Add Calculated Field**.</span></span>  
  
2.  <span data-ttu-id="5280b-119">En la página **Campos** del cuadro de diálogo **Propiedades del conjunto de datos** , haga clic en **Agregar**y, a continuación, haga clic en **Campo calculado**.</span><span class="sxs-lookup"><span data-stu-id="5280b-119">In the **Fields** page of the **Dataset Properties** dialog box, click **Add**, and then click **Calculated Field**.</span></span> <span data-ttu-id="5280b-120">En la parte inferior de la cuadrícula se agrega una nueva fila.</span><span class="sxs-lookup"><span data-stu-id="5280b-120">A new row is added to the bottom of the grid.</span></span>  
  
3.  <span data-ttu-id="5280b-121">En el cuadro de texto **Nombre de campo** , escriba el nombre del campo.</span><span class="sxs-lookup"><span data-stu-id="5280b-121">In the **Field Name** text bo, type the name for the field.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5280b-122">El nombre debe ser único en el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="5280b-122">Names must be unique in the dataset.</span></span>  
  
4.  <span data-ttu-id="5280b-123">En el cuadro de texto **Origen del campo** , escriba la expresión para el campo.</span><span class="sxs-lookup"><span data-stu-id="5280b-123">In the **Field Source** text box, type the expression for the field.</span></span> <span data-ttu-id="5280b-124">Haga clic en el botón Expresión (**fx**) para generar una expresión.</span><span class="sxs-lookup"><span data-stu-id="5280b-124">Click the expression (**fx**) button to build an expression.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5280b-125">La expresión de un campo calculado no puede contener agregados ni referencias a elementos de informe.</span><span class="sxs-lookup"><span data-stu-id="5280b-125">The expression for a calculated field cannot contain aggregates or references to report items.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-edit-a-query-field-or-a-dataset-field"></a><span data-ttu-id="5280b-126">Para modificar un campo de consulta o un campo de conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="5280b-126">To edit a query field or a dataset field</span></span>  
  
1.  <span data-ttu-id="5280b-127">En el panel Datos de informe, haga clic con el botón derecho en el campo y, después, haga clic en **Propiedades del campo**.</span><span class="sxs-lookup"><span data-stu-id="5280b-127">In the Report Data pane, right-click the field, and then click **Field Properties**.</span></span>  
  
2.  <span data-ttu-id="5280b-128">En la página **Campos** del cuadro de diálogo **Propiedades del conjunto de datos** , haga clic en un campo existente para seleccionar la fila.</span><span class="sxs-lookup"><span data-stu-id="5280b-128">In the **Fields** page of the **Dataset Properties** dialog box, click an existing field to select the row.</span></span>  
  
3.  <span data-ttu-id="5280b-129">Cambie el nombre o el valor del campo.</span><span class="sxs-lookup"><span data-stu-id="5280b-129">Change the name of the field or the value of the field.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-delete-a-query-field-or-a-calculated-field"></a><span data-ttu-id="5280b-130">Para eliminar un campo de consulta o un campo calculado</span><span class="sxs-lookup"><span data-stu-id="5280b-130">To delete a query field or a calculated field</span></span>  
  
1.  <span data-ttu-id="5280b-131">En el panel Datos de informe, expanda el conjunto de datos para mostrar la colección de campos.</span><span class="sxs-lookup"><span data-stu-id="5280b-131">In the Report Data pane, expand the dataset to display the field collection.</span></span>  
  
2.  <span data-ttu-id="5280b-132">Haga clic con el botón derecho en el campo que quiera quitar y, después, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="5280b-132">Right-click the field you want to remove, and then click **Delete**.</span></span>  
  
### <a name="to-refresh-the-field-collection-in-the-report-data-pane-for-a-shared-dataset"></a><span data-ttu-id="5280b-133">Para actualizar la colección de campos en el panel Datos de informe para un conjunto de datos compartido</span><span class="sxs-lookup"><span data-stu-id="5280b-133">To refresh the field collection in the Report Data Pane for a shared dataset</span></span>  
  
1.  <span data-ttu-id="5280b-134">En el panel Datos de informe, haga clic con el botón derecho en el conjunto de datos y, después, haga clic en **Consulta**.</span><span class="sxs-lookup"><span data-stu-id="5280b-134">In the Report Data pane, right-click the dataset, and then click **Query**.</span></span>  
  
2.  <span data-ttu-id="5280b-135">Haga clic en **Actualizar campos**.</span><span class="sxs-lookup"><span data-stu-id="5280b-135">Click **Refresh Fields**.</span></span>  
  
     <span data-ttu-id="5280b-136">En el servidor de informes, la consulta del conjunto de datos compartido se ejecuta y devuelve la colección de campos actual.</span><span class="sxs-lookup"><span data-stu-id="5280b-136">On the report server, the shared dataset query runs and returns the current field collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5280b-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5280b-137">See Also</span></span>  
 <span data-ttu-id="5280b-138">[Colección Campos del conjunto de datos &#40;Generador de informes y SSRS&#41;](dataset-fields-collection-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5280b-138">[Dataset Fields Collection &#40;Report Builder and SSRS&#41;](dataset-fields-collection-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5280b-139">[Agregar datos a un informe &#40;Generador de informes y SSRS&#41;](report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5280b-139">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-datasets-ssrs.md) </span></span>  
 <span data-ttu-id="5280b-140">[Conjuntos de datos incrustados y compartidos de informe &#40;Generador de informes y SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5280b-140">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5280b-141">[Diseñadores de consultas de Reporting Services](../reporting-services-query-designers.md) </span><span class="sxs-lookup"><span data-stu-id="5280b-141">[Reporting Services Query Designers](../reporting-services-query-designers.md) </span></span>  
 [<span data-ttu-id="5280b-142">Diseñadores de consultas &#40;Generador de informes&#41;</span><span class="sxs-lookup"><span data-stu-id="5280b-142">Query Designers &#40;Report Builder&#41;</span></span>](../query-designers-report-builder.md)  
  
  
