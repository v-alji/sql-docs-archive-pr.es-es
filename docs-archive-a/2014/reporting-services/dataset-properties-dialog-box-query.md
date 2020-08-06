---
title: Propiedades del conjunto de propiedades (cuadro de diálogo), consulta | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10160"
- sql12.rtp.rptdesigner.datasetproperties.query.f1
ms.assetid: 1fa34a4b-7de0-4e92-99fa-bc28a206773f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bffb14155d37e67333eb626747e1fcc54e618bbe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677435"
---
# <a name="dataset-properties-dialog-box-query"></a><span data-ttu-id="56aa6-102">Propiedades del conjunto de datos (cuadro de diálogo), Consulta</span><span class="sxs-lookup"><span data-stu-id="56aa6-102">Dataset Properties Dialog Box, Query</span></span>
  <span data-ttu-id="56aa6-103">Seleccione **Consulta** en el cuadro de diálogo **Propiedades del conjunto de datos** para elegir un origen de datos y crear una consulta.</span><span class="sxs-lookup"><span data-stu-id="56aa6-103">Select **Query** on the **Dataset Properties** dialog box to choose a data source and create a query.</span></span>  
  
 <span data-ttu-id="56aa6-104">El cuadro de diálogo **Propiedades del conjunto de datos** incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="56aa6-104">The **Dataset Properties** dialog box includes the following:</span></span>  
  
-   [<span data-ttu-id="56aa6-105">Propiedades del conjunto de datos (cuadro de diálogo), Parámetros</span><span class="sxs-lookup"><span data-stu-id="56aa6-105">Dataset Properties Dialog Box, Parameters</span></span>](report-data/dataset-properties-dialog-box-parameters.md)  
  
-   [<span data-ttu-id="56aa6-106">Propiedades del conjunto de datos (cuadro de diálogo), Campos</span><span class="sxs-lookup"><span data-stu-id="56aa6-106">Dataset Properties Dialog Box, Fields</span></span>](../../2014/reporting-services/dataset-properties-dialog-box-fields.md)  
  
-   [<span data-ttu-id="56aa6-107">Propiedades del conjunto de datos (cuadro de diálogo), Opciones</span><span class="sxs-lookup"><span data-stu-id="56aa6-107">Dataset Properties Dialog Box, Options</span></span>](../../2014/reporting-services/dataset-properties-dialog-box-options.md)  
  
-   [<span data-ttu-id="56aa6-108">Propiedades del conjunto de datos (cuadro de diálogo), Filtros</span><span class="sxs-lookup"><span data-stu-id="56aa6-108">Dataset Properties Dialog Box, Filters</span></span>](report-data/dataset-properties-dialog-box-filters.md)  
  
## <a name="options"></a><span data-ttu-id="56aa6-109">Opciones</span><span class="sxs-lookup"><span data-stu-id="56aa6-109">Options</span></span>  
 <span data-ttu-id="56aa6-110">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="56aa6-110">**Name**</span></span>  
 <span data-ttu-id="56aa6-111">Escriba el nombre del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="56aa6-111">Type a name for the dataset.</span></span> <span data-ttu-id="56aa6-112">Este nombre no puede coincidir con el nombre de cualquier grupo o región de datos del informe.</span><span class="sxs-lookup"><span data-stu-id="56aa6-112">The name cannot be the same as a name for any data region or group in the report.</span></span>  
  
 <span data-ttu-id="56aa6-113">**Data Source** (Origen de datos)</span><span class="sxs-lookup"><span data-stu-id="56aa6-113">**Data Source**</span></span>  
 <span data-ttu-id="56aa6-114">Seleccione el origen de datos en el que se basará el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="56aa6-114">Select the data source on which to base the dataset.</span></span> <span data-ttu-id="56aa6-115">Para crear un origen de datos nuevo, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="56aa6-115">To create a new data source, click **New**.</span></span>  
  
 <span data-ttu-id="56aa6-116">**Tipo de consulta**</span><span class="sxs-lookup"><span data-stu-id="56aa6-116">**Query type**</span></span>  
 <span data-ttu-id="56aa6-117">Seleccione el tipo de comando o consulta que se utilizará para el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="56aa6-117">Select the type of command or query to use for the dataset.</span></span> <span data-ttu-id="56aa6-118">Seleccione **Texto** para ejecutar una consulta con el objeto de recuperar datos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="56aa6-118">Select **Text** to run a query to retrieve data from the database.</span></span> <span data-ttu-id="56aa6-119">Seleccione **Tabla** para usar la característica de **TableDirect** de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] y seleccionar todos los campos de una tabla.</span><span class="sxs-lookup"><span data-stu-id="56aa6-119">Select **Table** to use the **TableDirect** feature of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to select all the fields within a table.</span></span> <span data-ttu-id="56aa6-120">Seleccione **Procedimiento almacenado** para ejecutar un procedimiento almacenado por su nombre.</span><span class="sxs-lookup"><span data-stu-id="56aa6-120">Select **Stored Procedure** to run a stored procedure by name.</span></span> <span data-ttu-id="56aa6-121">**Text** está seleccionado de manera predeterminada y se utiliza para la mayoría de las consultas.</span><span class="sxs-lookup"><span data-stu-id="56aa6-121">**Text** is selected by default and is used for most queries.</span></span> <span data-ttu-id="56aa6-122">Para editar la consulta de origen de datos seleccionada, haga clic en **Diseñador de consultas**.</span><span class="sxs-lookup"><span data-stu-id="56aa6-122">To edit the selected data source query, click **Query Designer**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="56aa6-123">Todos los orígenes de datos no admiten todos los tipos de consulta.</span><span class="sxs-lookup"><span data-stu-id="56aa6-123">Not all query types are supported by all data sources.</span></span> <span data-ttu-id="56aa6-124">Por ejemplo, **Tabla** solo la admiten los tipos de orígenes de datos **OLE DB** y **ODBC**.</span><span class="sxs-lookup"><span data-stu-id="56aa6-124">For example, **Table** is supported only by data source types **OLE DB** and **ODBC**.</span></span>  
  
 <span data-ttu-id="56aa6-125">**Consultar**</span><span class="sxs-lookup"><span data-stu-id="56aa6-125">**Query**</span></span>  
 <span data-ttu-id="56aa6-126">Esta opción aparece cuando se elige la opción de tipo de comando **Texto** .</span><span class="sxs-lookup"><span data-stu-id="56aa6-126">This option appears when you choose the **Text** command type option.</span></span> <span data-ttu-id="56aa6-127">Escriba una consulta o importe una consulta existente haciendo clic en **Importar**.</span><span class="sxs-lookup"><span data-stu-id="56aa6-127">Type a query or import a pre-existing query by clicking **Import**.</span></span> <span data-ttu-id="56aa6-128">Haga clic en el botón **Expresión** (*fx*) para editar la expresión.</span><span class="sxs-lookup"><span data-stu-id="56aa6-128">Click the **Expression** (*fx*) button to edit the expression.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="56aa6-129">Si usó un diseñador de consultas para crear una consulta, el texto de la misma aparece en este cuadro.</span><span class="sxs-lookup"><span data-stu-id="56aa6-129">If you used a query designer to build a query, the text of the query appears in this box.</span></span>  
  
 <span data-ttu-id="56aa6-130">**Nombre de la tabla**</span><span class="sxs-lookup"><span data-stu-id="56aa6-130">**Table name**</span></span>  
 <span data-ttu-id="56aa6-131">Escriba el nombre de la tabla que desea usar como conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="56aa6-131">Enter the name of the table that you want to use as a dataset.</span></span> <span data-ttu-id="56aa6-132">Esta opción aparece cuando se selecciona **Tabla**.</span><span class="sxs-lookup"><span data-stu-id="56aa6-132">This option appears when you select **Table**.</span></span>  
  
 <span data-ttu-id="56aa6-133">**Seleccione o escriba el nombre del procedimiento almacenado**</span><span class="sxs-lookup"><span data-stu-id="56aa6-133">**Select or enter stored procedure name**</span></span>  
 <span data-ttu-id="56aa6-134">Escriba o elija el nombre del procedimiento almacenado que desea usar.</span><span class="sxs-lookup"><span data-stu-id="56aa6-134">Type or choose the name of the stored procedure that you want to use.</span></span> <span data-ttu-id="56aa6-135">Haga clic en el botón **Expresión** (*fx*) para editar la expresión.</span><span class="sxs-lookup"><span data-stu-id="56aa6-135">Click the **Expression** (*fx*) button to edit the expression.</span></span> <span data-ttu-id="56aa6-136">Esta opción aparece cuando se elige la opción de tipo de comando Procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="56aa6-136">This option appears when you choose the Stored Procedure command type option.</span></span>  
  
 <span data-ttu-id="56aa6-137">**Tiempo de espera (en segundos)**</span><span class="sxs-lookup"><span data-stu-id="56aa6-137">**Time out (in seconds)**</span></span>  
 <span data-ttu-id="56aa6-138">Escriba el número de segundos hasta que se agote el tiempo de espera de la consulta. El valor predeterminado es 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="56aa6-138">Type the number of seconds until the query times out. The default is 30 seconds.</span></span> <span data-ttu-id="56aa6-139">El valor de **Tiempo de espera** debe permanecer en blanco o ser mayor que cero.</span><span class="sxs-lookup"><span data-stu-id="56aa6-139">The value for **Time out** must be empty or greater than zero.</span></span> <span data-ttu-id="56aa6-140">Si está en blanco, nunca se supera el tiempo de espera de la consulta.</span><span class="sxs-lookup"><span data-stu-id="56aa6-140">If it is empty, the query does not time out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56aa6-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="56aa6-141">See Also</span></span>  
 <span data-ttu-id="56aa6-142">[Conexiones de datos, orígenes de datos y cadenas de conexión en Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="56aa6-142">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 <span data-ttu-id="56aa6-143">[Agregar datos a un informe &#40;Generador de informes y SSRS&#41;](report-data/report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="56aa6-143">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-data/report-datasets-ssrs.md) </span></span>  
 <span data-ttu-id="56aa6-144">[Diseñadores de consultas &#40;Generador de informes&#41;](../../2014/reporting-services/query-designers-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="56aa6-144">[Query Designers &#40;Report Builder&#41;](../../2014/reporting-services/query-designers-report-builder.md) </span></span>  
 [<span data-ttu-id="56aa6-145">Diseñadores de consultas de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="56aa6-145">Reporting Services Query Designers</span></span>](../../2014/reporting-services/reporting-services-query-designers.md)  
  
  
