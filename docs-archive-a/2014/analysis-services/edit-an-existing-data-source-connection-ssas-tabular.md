---
title: Editar una conexión de origen de datos existente (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.selexistconn.f1
ms.assetid: 97e63f18-a01d-4c91-a411-e7e6d40a0647
author: minewiskan
ms.author: owend
ms.openlocfilehash: 675a0d1119e25a92231d3e74a79739cb2e96b6d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676237"
---
# <a name="edit-an-existing-data-source-connection-ssas-tabular"></a><span data-ttu-id="9271a-102">Editar una conexión de origen de datos existente (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="9271a-102">Edit an Existing Data Source Connection (SSAS Tabular)</span></span>
  <span data-ttu-id="9271a-103">Este tema describe cómo editar las propiedades de una conexión de origen de datos existente en un modelo tabular.</span><span class="sxs-lookup"><span data-stu-id="9271a-103">This topic describes how to edit the properties of an existing data source connection in a tabular model.</span></span>  
  
 <span data-ttu-id="9271a-104">Después de crear una conexión a un origen de datos externo, puede modificar esa conexión posteriormente de estas maneras:</span><span class="sxs-lookup"><span data-stu-id="9271a-104">After you have created a connection to an external data source, you can later modify that connection in these ways:</span></span>  
  
-   <span data-ttu-id="9271a-105">Puede cambiar la información de conexión, incluido el archivo, fuente o base de datos utilizados como origen, sus propiedades u otras opciones de conexión específicas del proveedor.</span><span class="sxs-lookup"><span data-stu-id="9271a-105">You can change the connection information, including the file, feed, or database used as a source, its properties, or other provider-specific connection options.</span></span>  
  
-   <span data-ttu-id="9271a-106">Puede cambiar las asignaciones de tabla y de columna, así como quitar las referencias a las columnas que ya no se utilizan.</span><span class="sxs-lookup"><span data-stu-id="9271a-106">You can change table and column mappings, and remove references to columns that are no longer used.</span></span>  
  
-   <span data-ttu-id="9271a-107">Puede cambiar las tablas, vistas o columnas que obtiene del origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="9271a-107">You can change the tables, views, or columns that you get from the external data source.</span></span>  
  
## <a name="modify-a-connection"></a><span data-ttu-id="9271a-108">Modificar una conexión</span><span class="sxs-lookup"><span data-stu-id="9271a-108">Modify a Connection</span></span>  
 <span data-ttu-id="9271a-109">Este procedimiento describe cómo modificar una conexión de origen de datos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="9271a-109">This procedure describes how to modify a database data source connection.</span></span> <span data-ttu-id="9271a-110">Algunas opciones para trabajar con orígenes de datos difieren según el tipo de origen de datos; sin embargo, debería ser posible identificar fácilmente las diferencias.</span><span class="sxs-lookup"><span data-stu-id="9271a-110">Some options for working with data sources differ depending on the data source type; however, you should be able to easily identify those differences.</span></span>  
  
#### <a name="to-change-the-external-data-source-used-by-a-current-connection"></a><span data-ttu-id="9271a-111">Para cambiar el origen de datos externo utilizado por una conexión actual</span><span class="sxs-lookup"><span data-stu-id="9271a-111">To change the external data source used by a current connection</span></span>  
  
1.  <span data-ttu-id="9271a-112">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], haga clic en el menú **Modelo** y, a continuación, en **Conexiones existentes**.</span><span class="sxs-lookup"><span data-stu-id="9271a-112">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click the **Model** menu, and then click **Existing Connections**.</span></span>  
  
2.  <span data-ttu-id="9271a-113">Seleccione la conexión de origen de datos que desea modificar y, a continuación, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="9271a-113">Select the data source connection you want to modify, and then click **Edit**.</span></span>  
  
3.  <span data-ttu-id="9271a-114">En el cuadro de diálogo **Editar conexión** , haga clic en **Examinar** para buscar otra base de datos del mismo tipo pero con un nombre o ubicación diferente.</span><span class="sxs-lookup"><span data-stu-id="9271a-114">In the **Edit Connection** dialog box, click **Browse** to locate another database of the same type but with a different name or location.</span></span>  
  
     <span data-ttu-id="9271a-115">En cuanto cambia el archivo de base de datos, un mensaje aparece indicando que tiene que guardar y actualizar las tablas para ver los nuevos datos.</span><span class="sxs-lookup"><span data-stu-id="9271a-115">As soon as you change the database file, a message appears indicating that you need to save and refresh the tables in order to see the new data.</span></span>  
  
4.  <span data-ttu-id="9271a-116">Haga clic en **Guardar**y, a continuación, en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="9271a-116">Click **Save**, and then click **Close**.</span></span>  
  
5.  <span data-ttu-id="9271a-117">En [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], haga clic en **Modelo**, a continuación, en **Procesar**y, por último, en **Procesar todo**.</span><span class="sxs-lookup"><span data-stu-id="9271a-117">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click the **Model**, click **Process**, and then click **Process All**.</span></span>  
  
     <span data-ttu-id="9271a-118">Las tablas se vuelven a procesar utilizando el nuevo origen de datos, pero con las selecciones de datos originales.</span><span class="sxs-lookup"><span data-stu-id="9271a-118">The tables are re-processed using the new data source, but with the original data selections.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9271a-119">Si el nuevo origen de datos contiene alguna tabla adicional que no se encontraba en el origen de datos original, debe volver a abrir la conexión cambiada y agregar las tablas.</span><span class="sxs-lookup"><span data-stu-id="9271a-119">If the new data source contains any additional tables that were not present in the original data source, you must re-open the changed connection and add the tables.</span></span>  
  
## <a name="edit-table-and-column-mappings-bindings"></a><span data-ttu-id="9271a-120">Editar las asignaciones de columna y de tabla (enlaces)</span><span class="sxs-lookup"><span data-stu-id="9271a-120">Edit Table and Column Mappings (Bindings)</span></span>  
 <span data-ttu-id="9271a-121">Este procedimiento describe cómo editar las asignaciones una vez ha cambiado un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="9271a-121">This procedure describes how to edit the mappings after you change a data source.</span></span>  
  
#### <a name="to-edit-column-mappings-when-a-data-source-changes"></a><span data-ttu-id="9271a-122">Para editar la asignación de columnas cuando se cambia un origen de datos</span><span class="sxs-lookup"><span data-stu-id="9271a-122">To edit column mappings when a data source changes</span></span>  
  
1.  <span data-ttu-id="9271a-123">Seleccione una tabla en el diseñador de modelos.</span><span class="sxs-lookup"><span data-stu-id="9271a-123">In the model designer, select a table.</span></span>  
  
2.  <span data-ttu-id="9271a-124">Haga clic en el menú **Tabla** y, a continuación, en **Propiedades de la tabla**.</span><span class="sxs-lookup"><span data-stu-id="9271a-124">Click on the **Table** menu, and then click **Table Properties**.</span></span>  
  
     <span data-ttu-id="9271a-125">El nombre de la tabla seleccionada se muestra en el cuadro **Nombre de la tabla** .</span><span class="sxs-lookup"><span data-stu-id="9271a-125">The name of the selected table is displayed in the **Table Name** box.</span></span> <span data-ttu-id="9271a-126">El cuadro **Nombre del origen** contiene el nombre de la tabla en el origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="9271a-126">The **Source Name** box contains the name of the table in the external data source.</span></span> <span data-ttu-id="9271a-127">Si las columnas tienen nombres distintos en el origen y en el modelo, puede alternar entre los dos conjuntos de nombres de columnas seleccionando las opciones **Origen** o **Modelo**.</span><span class="sxs-lookup"><span data-stu-id="9271a-127">If columns are named differently in the source and in the model, you can toggle between the two sets of column names by selecting the options **Source** or **Model**.</span></span>  
  
3.  <span data-ttu-id="9271a-128">Para cambiar la tabla que se usa como origen de datos, en **Nombre del origen**, seleccione una tabla diferente de la actual.</span><span class="sxs-lookup"><span data-stu-id="9271a-128">To change the table that is used as a data source, for **Source Name**, select a different table than the current one.</span></span>  
  
4.  <span data-ttu-id="9271a-129">Cambie la asignación de columnas si es necesario:</span><span class="sxs-lookup"><span data-stu-id="9271a-129">Change column mappings if needed:</span></span>  
  
    1.  <span data-ttu-id="9271a-130">Para agregar columnas que se encuentran en el origen pero no en el modelo, active la casilla situada al lado del nombre de cada columna.</span><span class="sxs-lookup"><span data-stu-id="9271a-130">To add columns that are present in the source but not in the model, select the checkbox beside the column name.</span></span>  
  
         <span data-ttu-id="9271a-131">Los datos reales se cargarán en el modelo la próxima vez que actualice.</span><span class="sxs-lookup"><span data-stu-id="9271a-131">The actual data will be loaded into the model the next time you refresh.</span></span>  
  
    2.  <span data-ttu-id="9271a-132">Si algunas columnas del modelo ya no están disponibles en el origen de datos actual, aparece un mensaje en el área de notificación con una lista de las columnas no válidas.</span><span class="sxs-lookup"><span data-stu-id="9271a-132">If some columns in the model are no longer available in the current data source, a message appears in the notification area that lists the invalid columns.</span></span> <span data-ttu-id="9271a-133">No es necesario hacer nada más.</span><span class="sxs-lookup"><span data-stu-id="9271a-133">You do not need to do anything else.</span></span>  
  
5.  <span data-ttu-id="9271a-134">Haga clic en **Guardar** para aplicar los cambios en el modelo.</span><span class="sxs-lookup"><span data-stu-id="9271a-134">Click **Save** to apply the changes to your model.</span></span>  
  
     <span data-ttu-id="9271a-135">Cuando guarde el conjunto actual de propiedades de la tabla, es posible que aparezca un mensaje indicando que debe procesar las tablas.</span><span class="sxs-lookup"><span data-stu-id="9271a-135">When you save the current set of table properties, a message may appear indicating that you need to process the tables.</span></span> <span data-ttu-id="9271a-136">Haga clic en **Procesar** para cargar los datos actualizados en el modelo.</span><span class="sxs-lookup"><span data-stu-id="9271a-136">Click **Process** to load updated data into your model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9271a-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9271a-137">See Also</span></span>  
 <span data-ttu-id="9271a-138">[Procesar datos &#40;SSAS tabular&#41;](process-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="9271a-138">[Process Data &#40;SSAS Tabular&#41;](process-data-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="9271a-139">Orígenes de datos compatibles &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="9271a-139">Data Sources Supported &#40;SSAS Tabular&#41;</span></span>](tabular-models/data-sources-supported-ssas-tabular.md)  
  
  
