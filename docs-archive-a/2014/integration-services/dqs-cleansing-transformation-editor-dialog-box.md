---
title: Cuadro de diálogo Editor de transformación limpieza de DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssdqs.designer.cleansing.f1
- SQL12.SSDQS.DESIGNER.DQCONNECTION.F1
ms.assetid: 07e79641-71ee-45d0-a9ba-ed6f9f68f333
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e97cd138bb17ce3cfe476496e5bc576875728224
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663030"
---
# <a name="dqs-cleansing-transformation-editor-dialog-box"></a><span data-ttu-id="207a8-102">Cuadro de diálogo Editor de transformación Limpieza de DQS</span><span class="sxs-lookup"><span data-stu-id="207a8-102">DQS Cleansing Transformation Editor Dialog Box</span></span>
  <span data-ttu-id="207a8-103">Use el cuadro de diálogo **Editor de transformación Limpieza de DQS** para corregir datos con Data Quality Services (DQS).</span><span class="sxs-lookup"><span data-stu-id="207a8-103">Use the **DQS Cleansing Transformation Editor** dialog box to correct data using Data Quality Services (DQS).</span></span> <span data-ttu-id="207a8-104">Para más información, consulte [Data Quality Services Concepts](../../2014/data-quality-services/data-quality-services-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="207a8-104">For more information, see [Data Quality Services Concepts](../../2014/data-quality-services/data-quality-services-concepts.md).</span></span>  
  
 <span data-ttu-id="207a8-105">Para obtener más información acerca de la transformación, vea [DQS Cleansing Transformation](data-flow/transformations/dqs-cleansing-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="207a8-105">To learn more about the transformation, see [DQS Cleansing Transformation](data-flow/transformations/dqs-cleansing-transformation.md).</span></span>  
  
 <span data-ttu-id="207a8-106">**¿Qué desea hacer?**</span><span class="sxs-lookup"><span data-stu-id="207a8-106">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="207a8-107">Abrir el Editor de transformación Limpieza de DQS</span><span class="sxs-lookup"><span data-stu-id="207a8-107">Open the DQS Cleansing Transformation Editor</span></span>](#open)  
  
-   [<span data-ttu-id="207a8-108">Establecer opciones en la pestaña administrador de conexiones</span><span class="sxs-lookup"><span data-stu-id="207a8-108">Set options on the Connection Manager tab</span></span>](#connection)  
  
-   [<span data-ttu-id="207a8-109">Establecer opciones en la pestaña Asignación</span><span class="sxs-lookup"><span data-stu-id="207a8-109">Set options on the Mapping tab</span></span>](#mapping)  
  
-   [<span data-ttu-id="207a8-110">Establecer opciones en la pestaña Avanzadas</span><span class="sxs-lookup"><span data-stu-id="207a8-110">Set options on the Advanced tab</span></span>](#advanced)  
  
-   [<span data-ttu-id="207a8-111">Establecer las opciones del cuadro de diálogo Administrador de conexiones de limpieza de DQS</span><span class="sxs-lookup"><span data-stu-id="207a8-111">Set the options in the DQS Cleansing Connection Manager dialog box</span></span>](#manager)  
  
##  <a name="open-the-dqs-cleansing-transformation-editor"></a><a name="open"></a><span data-ttu-id="207a8-112">Abrir el editor de transformación limpieza de DQS</span><span class="sxs-lookup"><span data-stu-id="207a8-112">Open the DQS Cleansing Transformation Editor</span></span>  
  
1.  <span data-ttu-id="207a8-113">Agregue la Transformación Limpieza de DQS al paquete de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="207a8-113">Add the DQS Cleansing Transformation to [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="207a8-114">Haga clic con el botón derecho en el componente y, después, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="207a8-114">Right-click the component and then click **Edit**.</span></span>  
  
##  <a name="set-options-on-the-connection-manager-tab"></a><a name="connection"></a> <span data-ttu-id="207a8-115">Establecer opciones en la pestaña Administrador de conexiones</span><span class="sxs-lookup"><span data-stu-id="207a8-115">Set options on the Connection Manager tab</span></span>  
 <span data-ttu-id="207a8-116">**Administrador de conexiones de calidad de datos**</span><span class="sxs-lookup"><span data-stu-id="207a8-116">**Data quality connection manager**</span></span>  
 <span data-ttu-id="207a8-117">Seleccione un administrador de conexiones DQS existente de la lista, o bien haga clic en **Nuevo**para crear una conexión.</span><span class="sxs-lookup"><span data-stu-id="207a8-117">Select an existing DQS connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="207a8-118">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="207a8-118">**New**</span></span>  
 <span data-ttu-id="207a8-119">Cree un administrador de conexiones con el cuadro de diálogo **Administrador de conexiones de limpieza de DQS** .</span><span class="sxs-lookup"><span data-stu-id="207a8-119">Create a new connection manager by using the **DQS Cleansing Connection Manager** dialog box.</span></span> <span data-ttu-id="207a8-120">Vea [Set the options in the DQS Cleansing Connection Manager dialog box](#manager).</span><span class="sxs-lookup"><span data-stu-id="207a8-120">See [Set the options in the DQS Cleansing Connection Manager dialog box](#manager)</span></span>  
  
 <span data-ttu-id="207a8-121">**Base de conocimiento de calidad de datos**</span><span class="sxs-lookup"><span data-stu-id="207a8-121">**Data Quality Knowledge Base**</span></span>  
 <span data-ttu-id="207a8-122">Seleccione una base de conocimiento de DQS existente para el origen de datos conectado.</span><span class="sxs-lookup"><span data-stu-id="207a8-122">Select an existing DQS knowledge base for the connected data source.</span></span> <span data-ttu-id="207a8-123">Para obtener más información acerca de la base de conocimiento de DQS, vea [DQS Knowledge Bases and Domains](../../2014/data-quality-services/dqs-knowledge-bases-and-domains.md).</span><span class="sxs-lookup"><span data-stu-id="207a8-123">For more information about the DQS knowledge base, see [DQS Knowledge Bases and Domains](../../2014/data-quality-services/dqs-knowledge-bases-and-domains.md).</span></span>  
  
 <span data-ttu-id="207a8-124">**Cifrar conexión**</span><span class="sxs-lookup"><span data-stu-id="207a8-124">**Encrypt connection**</span></span>  
 <span data-ttu-id="207a8-125">Especifique si desea cifrar la conexión para cifrar la transferencia de datos entre el servidor DQS y [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="207a8-125">specify whether to encrypt the connection, in order to encrypt the data transfer between the DQS Server and [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="207a8-126">**Dominios disponibles**</span><span class="sxs-lookup"><span data-stu-id="207a8-126">**Available domains**</span></span>  
 <span data-ttu-id="207a8-127">Enumera los dominios disponibles para la base de conocimiento seleccionada.</span><span class="sxs-lookup"><span data-stu-id="207a8-127">Lists the available domains for the selected knowledge base.</span></span> <span data-ttu-id="207a8-128">Hay dos tipos de dominios: dominios únicos y dominios compuestos que contienen dos o más dominios únicos.</span><span class="sxs-lookup"><span data-stu-id="207a8-128">There are two types of domains: single domains, and composite domains that contain two or more single domains.</span></span>  
  
 <span data-ttu-id="207a8-129">Para obtener información acerca de cómo asignar columnas a dominios compuestos, vea [Map Columns to Composite Domains](data-flow/transformations/map-columns-to-composite-domains.md).</span><span class="sxs-lookup"><span data-stu-id="207a8-129">For information on how to map columns to composite domains, see [Map Columns to Composite Domains](data-flow/transformations/map-columns-to-composite-domains.md).</span></span>  
  
 <span data-ttu-id="207a8-130">Para obtener más información acerca de los dominios, vea [DQS Knowledge Bases and Domains](../../2014/data-quality-services/dqs-knowledge-bases-and-domains.md).</span><span class="sxs-lookup"><span data-stu-id="207a8-130">For more information about domains, see [DQS Knowledge Bases and Domains](../../2014/data-quality-services/dqs-knowledge-bases-and-domains.md).</span></span>  
  
 <span data-ttu-id="207a8-131">**Configurar la salida de errores**</span><span class="sxs-lookup"><span data-stu-id="207a8-131">**Configure Error Output**</span></span>  
 <span data-ttu-id="207a8-132">Especifica cómo se han de administrar los errores de fila.</span><span class="sxs-lookup"><span data-stu-id="207a8-132">Specify how to handle row-level errors.</span></span> <span data-ttu-id="207a8-133">Pueden producirse errores cuando la transformación corrige los datos del origen de datos conectado, debido a restricciones de validación o valores de datos inesperados.</span><span class="sxs-lookup"><span data-stu-id="207a8-133">Errors can occur when the transformation corrects data from the connected data source, due to unexpected data values or validation constraints.</span></span>  
  
 <span data-ttu-id="207a8-134">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="207a8-134">The following are the valid values:</span></span>  
  
-   <span data-ttu-id="207a8-135">**Error de componente**, que indica que los errores de transformación y los datos de entrada no se insertan en la base de datos de Data Quality Services.</span><span class="sxs-lookup"><span data-stu-id="207a8-135">**Fail Component**, which indicates that the transformation fails and the input data is not inserted into the Data Quality Services database.</span></span> <span data-ttu-id="207a8-136">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="207a8-136">This is the default value.</span></span>  
  
-   <span data-ttu-id="207a8-137">**Redirigir fila**, que indica que los datos de entrada no se insertan en la base de datos de Data Quality Services y se redirigen a la salida de error.</span><span class="sxs-lookup"><span data-stu-id="207a8-137">**Redirect Row**, which indicates that the input data is not inserted into the Data Quality Services database and is redirected to the error output.</span></span>  
  
##  <a name="set-options-on-the-mapping-tab"></a><a name="mapping"></a><span data-ttu-id="207a8-138">Establecer opciones en la pestaña asignación</span><span class="sxs-lookup"><span data-stu-id="207a8-138">Set options on the Mapping tab</span></span>  
 <span data-ttu-id="207a8-139">Para obtener información acerca de cómo asignar columnas a dominios compuestos, vea [Map Columns to Composite Domains](data-flow/transformations/map-columns-to-composite-domains.md).</span><span class="sxs-lookup"><span data-stu-id="207a8-139">For information on how to map columns to composite domains, see [Map Columns to Composite Domains](data-flow/transformations/map-columns-to-composite-domains.md).</span></span>  
  
 <span data-ttu-id="207a8-140">**Columnas de entrada disponibles**</span><span class="sxs-lookup"><span data-stu-id="207a8-140">**Available Input Columns**</span></span>  
 <span data-ttu-id="207a8-141">Enumera las columnas del origen de datos conectado.</span><span class="sxs-lookup"><span data-stu-id="207a8-141">Lists the columns from the connected data source.</span></span> <span data-ttu-id="207a8-142">Seleccione una o varias columnas que contengan los datos que desee corregir.</span><span class="sxs-lookup"><span data-stu-id="207a8-142">Select one or more columns that contain data that you want to correct.</span></span>  
  
 <span data-ttu-id="207a8-143">**Columna de entrada**</span><span class="sxs-lookup"><span data-stu-id="207a8-143">**Input Column**</span></span>  
 <span data-ttu-id="207a8-144">Muestra una columna de entrada que ha seleccionado en el área **Columnas de entrada disponibles** .</span><span class="sxs-lookup"><span data-stu-id="207a8-144">Lists an input column that you selected in the **Available Input Columns** area.</span></span>  
  
 <span data-ttu-id="207a8-145">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="207a8-145">**Domain**</span></span>  
 <span data-ttu-id="207a8-146">Seleccione un dominio para asignar a la columna de entrada.</span><span class="sxs-lookup"><span data-stu-id="207a8-146">Select a domain to map to the input column.</span></span>  
  
 <span data-ttu-id="207a8-147">**Alias de origen**</span><span class="sxs-lookup"><span data-stu-id="207a8-147">**Source Alias**</span></span>  
 <span data-ttu-id="207a8-148">Muestra la columna de origen que contiene el valor original de la columna.</span><span class="sxs-lookup"><span data-stu-id="207a8-148">Lists the source column that contains the original column value.</span></span>  
  
 <span data-ttu-id="207a8-149">Haga clic en este campo para modificar el nombre de columna.</span><span class="sxs-lookup"><span data-stu-id="207a8-149">Click in the field to modify the column name.</span></span>  
  
 <span data-ttu-id="207a8-150">**Alias de salida**</span><span class="sxs-lookup"><span data-stu-id="207a8-150">**Output Alias**</span></span>  
 <span data-ttu-id="207a8-151">Muestra la columna devuelta por el **Editor de transformación Limpieza de DQS**.</span><span class="sxs-lookup"><span data-stu-id="207a8-151">Lists the column that is outputted by the **DQS Cleansing Transformation**.</span></span> <span data-ttu-id="207a8-152">La columna contiene el valor original de la columna o el valor corregido.</span><span class="sxs-lookup"><span data-stu-id="207a8-152">The column contains the original column value or the corrected value.</span></span>  
  
 <span data-ttu-id="207a8-153">Haga clic en este campo para modificar el nombre de columna.</span><span class="sxs-lookup"><span data-stu-id="207a8-153">Click in the field to modify the column name.</span></span>  
  
 <span data-ttu-id="207a8-154">**Alias de estado**</span><span class="sxs-lookup"><span data-stu-id="207a8-154">**Status Alias**</span></span>  
 <span data-ttu-id="207a8-155">Muestra la columna que contiene información de estado sobre los datos corregidos.</span><span class="sxs-lookup"><span data-stu-id="207a8-155">Lists the column that contains status information for the corrected data.</span></span> <span data-ttu-id="207a8-156">Haga clic en este campo para modificar el nombre de columna.</span><span class="sxs-lookup"><span data-stu-id="207a8-156">Click in the field to modify the column name.</span></span>  
  
##  <a name="set-options-on-the-advanced-tab"></a><a name="advanced"></a><span data-ttu-id="207a8-157">Establecer opciones en la pestaña avanzadas</span><span class="sxs-lookup"><span data-stu-id="207a8-157">Set options on the Advanced tab</span></span>  
 <span data-ttu-id="207a8-158">**Estandarizar salida**</span><span class="sxs-lookup"><span data-stu-id="207a8-158">**Standardize output**</span></span>  
 <span data-ttu-id="207a8-159">Indica si los datos se van a generar en el formato estandarizado según el formato de salida que se haya definido para los dominios.</span><span class="sxs-lookup"><span data-stu-id="207a8-159">Indicate whether to output the data in the standardized format based on the output format defined for domains.</span></span> <span data-ttu-id="207a8-160">Para más información sobre el formato estandarizado, vea [Limpieza de datos](../../2014/data-quality-services/data-cleansing.md).</span><span class="sxs-lookup"><span data-stu-id="207a8-160">For more information about standardized format, see [Data Cleansing](../../2014/data-quality-services/data-cleansing.md).</span></span>  
  
 <span data-ttu-id="207a8-161">**Confiar**</span><span class="sxs-lookup"><span data-stu-id="207a8-161">**Confidence**</span></span>  
 <span data-ttu-id="207a8-162">Indica si se debe incluir el nivel de confianza para los datos corregidos.</span><span class="sxs-lookup"><span data-stu-id="207a8-162">Indicate whether to include the confidence level for corrected data.</span></span> <span data-ttu-id="207a8-163">El nivel de confianza indica el grado de certeza de DQS para la corrección o sugerencia.</span><span class="sxs-lookup"><span data-stu-id="207a8-163">The confidence level indicates the extend of certainty of DQS for the correction or suggestion.</span></span> <span data-ttu-id="207a8-164">Para más información sobre los niveles de confianza, vea [Limpieza de datos](../../2014/data-quality-services/data-cleansing.md).</span><span class="sxs-lookup"><span data-stu-id="207a8-164">For more information about confidence levels, see [Data Cleansing](../../2014/data-quality-services/data-cleansing.md).</span></span>  
  
 <span data-ttu-id="207a8-165">**Motivo**</span><span class="sxs-lookup"><span data-stu-id="207a8-165">**Reason**</span></span>  
 <span data-ttu-id="207a8-166">Indica si se debe incluir el motivo de la corrección de los datos.</span><span class="sxs-lookup"><span data-stu-id="207a8-166">Indicate whether to include the reason for the data correction.</span></span>  
  
 <span data-ttu-id="207a8-167">**Datos anexados**</span><span class="sxs-lookup"><span data-stu-id="207a8-167">**Appended Data**</span></span>  
 <span data-ttu-id="207a8-168">Indica si se van a generar datos adicionales que se hayan recibido de un proveedor de datos de referencia existente.</span><span class="sxs-lookup"><span data-stu-id="207a8-168">Indicate whether to output additional data that is received from an existing reference data provider.</span></span> <span data-ttu-id="207a8-169">Para obtener más información, consulte [Reference Data Services in DQS](../../2014/data-quality-services/reference-data-services-in-dqs.md).</span><span class="sxs-lookup"><span data-stu-id="207a8-169">For more information, see [Reference Data Services in DQS](../../2014/data-quality-services/reference-data-services-in-dqs.md).</span></span>  
  
 <span data-ttu-id="207a8-170">**Esquema de datos anexados**</span><span class="sxs-lookup"><span data-stu-id="207a8-170">**Appended Data Schema**</span></span>  
 <span data-ttu-id="207a8-171">Indica si se va a generar el esquema de datos.</span><span class="sxs-lookup"><span data-stu-id="207a8-171">Indicate whether to output the data schema.</span></span> <span data-ttu-id="207a8-172">Para obtener más información, vea [adjuntar un dominio o un dominio compuesto a datos de referencia](../../2014/data-quality-services/attach-a-domain-or-composite-domain-to-reference-data.md).</span><span class="sxs-lookup"><span data-stu-id="207a8-172">For more information, see [Attach a Domain or Composite Domain to Reference Data](../../2014/data-quality-services/attach-a-domain-or-composite-domain-to-reference-data.md).</span></span>  
  
##  <a name="set-the-options-in-the-dqs-cleansing-connection-manager-dialog-box"></a><a name="manager"></a><span data-ttu-id="207a8-173">Establecer las opciones del cuadro de diálogo Administrador de conexiones de limpieza de DQS</span><span class="sxs-lookup"><span data-stu-id="207a8-173">Set the options in the DQS Cleansing Connection Manager dialog box</span></span>  
 <span data-ttu-id="207a8-174">**Nombre del servidor**</span><span class="sxs-lookup"><span data-stu-id="207a8-174">**Server name**</span></span>  
 <span data-ttu-id="207a8-175">Seleccione o escriba el nombre del servidor DQS al que desee conectarse.</span><span class="sxs-lookup"><span data-stu-id="207a8-175">Select or type the name of the DQS server that you want to connect to.</span></span> <span data-ttu-id="207a8-176">Para obtener más información acerca del servidor, vea [DQS Administration](../../2014/data-quality-services/dqs-administration.md).</span><span class="sxs-lookup"><span data-stu-id="207a8-176">For more information about the server, see [DQS Administration](../../2014/data-quality-services/dqs-administration.md).</span></span>  
  
 <span data-ttu-id="207a8-177">**Probar conexión**</span><span class="sxs-lookup"><span data-stu-id="207a8-177">**Test Connection**</span></span>  
 <span data-ttu-id="207a8-178">Haga clic para confirmar que la conexión especificada es viable.</span><span class="sxs-lookup"><span data-stu-id="207a8-178">Click to confirm that the connection that you specified is viable.</span></span>  
  
 <span data-ttu-id="207a8-179">También puede abrir el cuadro de diálogo **Administrador de conexiones de limpieza de DQS** desde el área de conexiones; para ello, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="207a8-179">You can also open the **DQS Cleansing Connection Manager** dialog box from the connections area, by doing the following:</span></span>  
  
1.  <span data-ttu-id="207a8-180">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra un proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] existente o cree uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="207a8-180">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open an existing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project or create a new one.</span></span>  
  
2.  <span data-ttu-id="207a8-181">Haga clic con el botón derecho en el área de conexiones, haga clic en **Nueva conexión**y, después, en **DQS**.</span><span class="sxs-lookup"><span data-stu-id="207a8-181">Right-click in the connections area, click **New Connection**, and then click **DQS**.</span></span>  
  
3.  <span data-ttu-id="207a8-182">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="207a8-182">Click **Add**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="207a8-183">Consulte también</span><span class="sxs-lookup"><span data-stu-id="207a8-183">See Also</span></span>  
 [<span data-ttu-id="207a8-184">Aplicar reglas de calidad de los datos al origen de datos</span><span class="sxs-lookup"><span data-stu-id="207a8-184">Apply Data Quality Rules to Data Source</span></span>](data-flow/transformations/apply-data-quality-rules-to-data-source.md)  
  
  
