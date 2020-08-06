---
title: Crear un conjunto de datos compartido o un conjunto de datos incrustado (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d1d7bc71-f0e9-4ce5-b3ad-6fee54388a31
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fca74e1ba7965eeef6ce562e79e378af5bb9e145
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744514"
---
# <a name="create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs"></a><span data-ttu-id="95931-102">Crear un conjunto de datos compartido o un conjunto de datos incrustado (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="95931-102">Create a Shared Dataset or Embedded Dataset (Report Builder and SSRS)</span></span>
  <span data-ttu-id="95931-103">Puede crear un conjunto de datos incrustado para usarlo en un solo informe o un conjunto de datos compartido, que se guardará en un servidor de informes, para usarlo en varios informes.</span><span class="sxs-lookup"><span data-stu-id="95931-103">You can create an embedded dataset for use in a single report or a shared dataset to save to a report server, for use by multiple reports.</span></span> <span data-ttu-id="95931-104">Para crear un conjunto de datos, debe tener un origen de datos incrustado o compartido.</span><span class="sxs-lookup"><span data-stu-id="95931-104">To create a dataset, you must have an embedded or shared data source.</span></span>

 <span data-ttu-id="95931-105">Use el Generador de informes para realizar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="95931-105">Use Report Builder to do the following tasks:</span></span>

-   <span data-ttu-id="95931-106">Crear un conjunto de datos compartido en la vista de diseño de conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="95931-106">Create a shared dataset in Dataset Design View.</span></span> <span data-ttu-id="95931-107">Los conjuntos de datos compartidos deben usar orígenes de datos compartidos publicados.</span><span class="sxs-lookup"><span data-stu-id="95931-107">Shared datasets must use published shared data sources.</span></span>

-   <span data-ttu-id="95931-108">Crear un conjunto de datos incrustado en la vista de diseño de informe.</span><span class="sxs-lookup"><span data-stu-id="95931-108">Create an embedded dataset in Report Design View.</span></span>

-   <span data-ttu-id="95931-109">Guardar el conjunto de datos directamente en el servidor de informes o el sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="95931-109">Save the dataset directly to the report server or SharePoint site.</span></span>

 <span data-ttu-id="95931-110">Use el Diseñador de informes en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] para realizar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="95931-110">Use Report Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] to do the following tasks:</span></span>

1.  <span data-ttu-id="95931-111">Crear un conjunto de datos compartido en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="95931-111">Create a shared dataset in Solution Explorer.</span></span> <span data-ttu-id="95931-112">Los orígenes de datos compartidos deben usar orígenes de datos de la capeta Orígenes de datos compartidos en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="95931-112">Shared datasets must use data sources from the Shared Data Sources folder in Solution Explorer.</span></span>

2.  <span data-ttu-id="95931-113">Crear un conjunto de datos compartido en el panel Datos de informe.</span><span class="sxs-lookup"><span data-stu-id="95931-113">Create an embedded dataset in the Report Data pane.</span></span>

3.  <span data-ttu-id="95931-114">Opcionalmente, implementar los conjuntos de datos compartidos y el origen de datos compartido con el informe.</span><span class="sxs-lookup"><span data-stu-id="95931-114">Optionally deploy the shared datasets and shared data source with the report.</span></span> <span data-ttu-id="95931-115">Para cada tipo de elemento, use Propiedades del proyecto para especificar las rutas de acceso a las carpetas del servidor de informes o del sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="95931-115">For each type of item, use Project Properties to specify paths to folders on the report server or SharePoint site.</span></span>

 <span data-ttu-id="95931-116">Para más información, vea [Conjuntos de datos incrustados y compartidos de informe &#40;Generador de informes y SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="95931-116">For more information, see [Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md).</span></span>

> [!NOTE]
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]

### <a name="to-open-report-builder-and-create-a-shared-dataset"></a><span data-ttu-id="95931-117">Para abrir el Generador de informes y crear un conjunto de datos compartido</span><span class="sxs-lookup"><span data-stu-id="95931-117">To open Report Builder and create a shared dataset</span></span>

1.  <span data-ttu-id="95931-118">Abra el Generador de informes.</span><span class="sxs-lookup"><span data-stu-id="95931-118">Open Report Builder.</span></span> <span data-ttu-id="95931-119">Se abre el panel **Nuevo informe o conjunto de datos** , como se muestra en en la siguiente figura:</span><span class="sxs-lookup"><span data-stu-id="95931-119">The **New report or dataset pane** opens, as shown in the following figure:</span></span>

     <span data-ttu-id="95931-120">![rs_NewSharedDataset](../media/rs-newshareddataset.gif "rs_NewSharedDataset")</span><span class="sxs-lookup"><span data-stu-id="95931-120">![rs_NewSharedDataset](../media/rs-newshareddataset.gif "rs_NewSharedDataset")</span></span>

    > [!NOTE]
    >  <span data-ttu-id="95931-121"> Si el panel **Nuevo informe o conjunto de datos** no aparece, en el botón Generador de informes haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="95931-121">If the **New report or dataset pane** does not appear, from the Report Builder button, click **New**.</span></span>

2.  <span data-ttu-id="95931-122">En el panel izquierdo, bajo **Crear un conjunto de datos**, haga clic en **Conjunto de datos compartido**.</span><span class="sxs-lookup"><span data-stu-id="95931-122">In the left pane, under **Create a dataset**, click **Shared Dataset**.</span></span>

3.  <span data-ttu-id="95931-123">En el panel derecho, haga clic en **Examinar** para seleccionar un origen de datos compartido del servidor de informes y, a continuación, haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="95931-123">In the right pane, click **Browse** to select a shared data source from the report server, and then click **Create**.</span></span> <span data-ttu-id="95931-124">Se abre el diseñador de consultas asociado al origen de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="95931-124">The query designer associated with the shared data source opens.</span></span>

4.  <span data-ttu-id="95931-125">En el diseñador de consultas, especifique los campos que se incluirán en el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="95931-125">In the query designer, specify the fields to include in the dataset.</span></span>

5.  <span data-ttu-id="95931-126">Haga clic en **Ejecutar** (**!**) para ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="95931-126">Click **Run** (**!**) to run the query.</span></span>

6.  <span data-ttu-id="95931-127">En el botón **Generador de informes** , haga clic en **Guardar** o **Guardar como** para guardar el conjunto de datos compartido en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="95931-127">On the **Report Builder** button, click **Save** or **Save As** to save the shared dataset to the report server.</span></span>

7.  <span data-ttu-id="95931-128">Para salir del Generador de informes, haga clic en **Generador de informes**y, a continuación, haga clic en **Salir del Generador de informes**.</span><span class="sxs-lookup"><span data-stu-id="95931-128">To exit Report Builder, click **Report Builder**, and then click **Exit Report Builder**.</span></span> <span data-ttu-id="95931-129">Para trabajar con informes, haga clic en **Generador de informes**y haga clic en **Nuevo** o en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="95931-129">To work with reports, click **Report Builder**, and then click **New** or **Open**.</span></span>

### <a name="to-set-query-parameter-options"></a><span data-ttu-id="95931-130">Para establecer opciones de los parámetros de consultas</span><span class="sxs-lookup"><span data-stu-id="95931-130">To set query parameter options</span></span>

1.  <span data-ttu-id="95931-131">Abra el Generador de informes.</span><span class="sxs-lookup"><span data-stu-id="95931-131">Open Report Builder.</span></span>

2.  <span data-ttu-id="95931-132">Haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="95931-132">Click **Open**.</span></span>

3.  <span data-ttu-id="95931-133">Vaya al servidor de informes y seleccione la carpeta para el origen de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="95931-133">Browse to the report server, and select the folder for the shared data source.</span></span>

4.  <span data-ttu-id="95931-134">En **Elementos de tipo**, haga clic en Datasets (\*.rsd) en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="95931-134">In **Items of type**, click Datasets (\*.rsd) in the drop-down list.</span></span>

5.  <span data-ttu-id="95931-135">Seleccione el conjunto de datos compartido y, a continuación, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="95931-135">Select the shared dataset, and then click **Open**.</span></span> <span data-ttu-id="95931-136">Se abre el diseñador de consultas asociado.</span><span class="sxs-lookup"><span data-stu-id="95931-136">The associated query designer opens.</span></span>

6.  <span data-ttu-id="95931-137">En la cinta de opciones, haga clic en **Propiedades del conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="95931-137">On the Ribbon, click **Dataset Properties**.</span></span>

7.  <span data-ttu-id="95931-138">Haga clic en **Parámetros**.</span><span class="sxs-lookup"><span data-stu-id="95931-138">Click **Parameters**.</span></span> <span data-ttu-id="95931-139">En esta página, establezca un valor predeterminado en una constante o expresión, marque el parámetro como de solo lectura o que admite valores NULL, o elija **Omitir en la consulta**.</span><span class="sxs-lookup"><span data-stu-id="95931-139">On this page, set a default value to a constant or an expression, mark the parameter as read-only, nullable, or **Omit From Query**.</span></span> <span data-ttu-id="95931-140">Para obtener más información, vea [Propiedades del conjunto de datos (cuadro de diálogo), Parámetros &#40;Generador de informes&#41;](../dataset-properties-dialog-box-parameters-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="95931-140">For more information, see [Dataset Properties Dialog Box, Parameters &#40;Report Builder&#41;](../dataset-properties-dialog-box-parameters-report-builder.md).</span></span>

8.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]


### <a name="to-create-a-dataset-from-a-sql-server-relational-database"></a><span data-ttu-id="95931-141">Crear un conjunto de datos a partir de una base de datos relacional de SQL Server</span><span class="sxs-lookup"><span data-stu-id="95931-141">To create a dataset from a SQL Server relational database</span></span>

1.  <span data-ttu-id="95931-142">En el panel Datos de informe, haga clic con el botón derecho en el nombre del origen de datos y, después, haga clic en **Agregar conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="95931-142">In the Report Data pane, right-click the name of the data source, and then click **Add Dataset**.</span></span> <span data-ttu-id="95931-143">Se abrirá la página **Consulta** del cuadro de diálogo **Propiedades del conjunto de datos** .</span><span class="sxs-lookup"><span data-stu-id="95931-143">The **Query** page of the **Dataset Properties** dialog box opens.</span></span>

2.  <span data-ttu-id="95931-144">En **Nombre**, escriba un nombre para el conjunto de datos o acepte el nombre predeterminado.</span><span class="sxs-lookup"><span data-stu-id="95931-144">In **Name**, type a name for the dataset or accept the default name.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="95931-145">El nombre del conjunto de datos se utiliza internamente en el informe.</span><span class="sxs-lookup"><span data-stu-id="95931-145">The dataset name is used internally within the report.</span></span> <span data-ttu-id="95931-146">Para evitar confusiones, se recomienda que el nombre del conjunto de datos describa los datos que devuelve la consulta.</span><span class="sxs-lookup"><span data-stu-id="95931-146">For clarity, we recommend that the name of the dataset describe the data that the query returns.</span></span>

3.  <span data-ttu-id="95931-147">En **Origen de datos**, busque el nombre de un origen de datos compartido existente y selecciónelo, o haga clic en **Nuevo** para crear un nuevo origen de datos incrustado.</span><span class="sxs-lookup"><span data-stu-id="95931-147">In **Data source**, browse to and select the name of an existing shared data source, or click **New** to create a new embedded data source.</span></span>

4.  <span data-ttu-id="95931-148">Seleccione una opción en el cuadro **Tipo de consulta** .</span><span class="sxs-lookup"><span data-stu-id="95931-148">Select a **Query type** option.</span></span> <span data-ttu-id="95931-149">Las opciones de este cuadro dependen del tipo de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="95931-149">Options depend on the data source type.</span></span>

    -   <span data-ttu-id="95931-150">Seleccione **Text** para escribir una consulta con el lenguaje de consulta del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="95931-150">Select **Text** to write a query using the query language of the data source.</span></span>

    -   <span data-ttu-id="95931-151">Seleccione **Table** para devolver todos los campos en una tabla de base de datos relacional.</span><span class="sxs-lookup"><span data-stu-id="95931-151">Select **Table** to return all the fields in a relational database table.</span></span>

    -   <span data-ttu-id="95931-152">Seleccione **StoredProcedure** para ejecutar un procedimiento almacenado por su nombre.</span><span class="sxs-lookup"><span data-stu-id="95931-152">Select **StoredProcedure** to run a stored procedure by name.</span></span>

5.  <span data-ttu-id="95931-153">En **Consulta**, escriba la consulta, el procedimiento almacenado o el nombre de tabla.</span><span class="sxs-lookup"><span data-stu-id="95931-153">In **Query**, type the query, stored procedure, or table name.</span></span> <span data-ttu-id="95931-154">O bien, haga clic en **Diseñador de consultas** para abrir el diseñador gráfico de consultas o el diseñador de consultas basado en texto, o en **Importar** para importar la consulta desde un informe existente.</span><span class="sxs-lookup"><span data-stu-id="95931-154">Alternatively, click **Query Designer** to open the graphical or text-based query designer tool, or **Import** to import the query from an existing report.</span></span>

     <span data-ttu-id="95931-155">En algunos casos, la colección de campos especificada por la consulta solo se puede determinar ejecutando la consulta en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="95931-155">In a few cases, the field collection specified by the query can only be determined by running the query on the data source.</span></span> <span data-ttu-id="95931-156">Por ejemplo, un procedimiento almacenado puede devolver un conjunto variable de campos en el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="95931-156">For example, a stored procedure may return a variable set of fields in the result set.</span></span> <span data-ttu-id="95931-157">Haga clic en **Actualizar campos** para ejecutar la consulta en el origen de datos y recuperar los nombres de campo necesarios para rellenar la colección de campos del conjunto de datos en el panel Datos de informe.</span><span class="sxs-lookup"><span data-stu-id="95931-157">Click **Refresh Fields** to run the query on the data source and retrieve the field names that are needed to populate the dataset field collection in the Report Data pane.</span></span> <span data-ttu-id="95931-158">La colección de campos aparece bajo el nodo del conjunto de datos al cerrar el cuadro de diálogo **Propiedades del conjunto de datos** .</span><span class="sxs-lookup"><span data-stu-id="95931-158">The field collection appears under the dataset node after you close the **Dataset Properties** dialog box.</span></span>

6.  <span data-ttu-id="95931-159">En **Tiempo de espera**, escriba el número de segundos que el servidor de informes esperará una respuesta de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="95931-159">In **Timeout**, type the number of seconds that the report server waits for a response from the database.</span></span> <span data-ttu-id="95931-160">El valor predeterminado es 0 segundos.</span><span class="sxs-lookup"><span data-stu-id="95931-160">The default value is 0 seconds.</span></span> <span data-ttu-id="95931-161">Si el tiempo de espera es 0 segundos, nunca se supera el tiempo de espera de la consulta.</span><span class="sxs-lookup"><span data-stu-id="95931-161">When the time out value is 0 seconds, the query does not time out.</span></span>

7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]

     <span data-ttu-id="95931-162">El conjunto de datos y su colección de campos aparecen en el panel Datos de informe bajo el nodo del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="95931-162">The dataset and its field collection appear in the Report Data pane under the data source node.</span></span>

## <a name="see-also"></a><span data-ttu-id="95931-163">Consulte también</span><span class="sxs-lookup"><span data-stu-id="95931-163">See Also</span></span>
 <span data-ttu-id="95931-164">[Conjuntos de datos incrustados de informe y conjuntos de datos Compartidos &#40;generador de informes y ssrs&#41;colección de](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) [campos de conjunto de datos &#40;Generador de informes y SSRS&#41;](dataset-fields-collection-report-builder-and-ssrs.md) [diseñadores de consultas &#40;](../query-designers-report-builder.md) generador de informes&#41;generador de informes la [ayuda de cuadros de diálogo, paneles y asistentes](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) [Agregar datos a un informe &#40;](report-datasets-ssrs.md) generador de informes y SSRS&#41;[conexiones de datos, orígenes de datos y cadenas de conexión en generador de informes](../data-connections-data-sources-and-connection-strings-in-report-builder.md) &#40;[y SSRS](embedded-and-shared-datasets-report-builder-and-ssrs.md) generador de informes</span><span class="sxs-lookup"><span data-stu-id="95931-164">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) [Dataset Fields Collection &#40;Report Builder and SSRS&#41;](dataset-fields-collection-report-builder-and-ssrs.md) [Query Designers &#40;Report Builder&#41;](../query-designers-report-builder.md) [Report Builder Help for Dialog Boxes, Panes, and Wizards](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) [Add Data to a Report &#40;Report Builder and SSRS&#41;](report-datasets-ssrs.md) [Data Connections, Data Sources, and Connection Strings in Report Builder](../data-connections-data-sources-and-connection-strings-in-report-builder.md) [Embedded and Shared Datasets &#40;Report Builder and SSRS&#41;](embedded-and-shared-datasets-report-builder-and-ssrs.md)</span></span>


