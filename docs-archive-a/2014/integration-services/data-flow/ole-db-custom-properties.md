---
title: Propiedades personalizadas de OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 13a82d41-dd7a-4708-bc84-4407a536c877
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ee45740af06d0b9d89bcbd8f3e428308c8b43b88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670477"
---
# <a name="ole-db-custom-properties"></a><span data-ttu-id="7ee20-102">Propiedades personalizadas de OLE DB</span><span class="sxs-lookup"><span data-stu-id="7ee20-102">OLE DB Custom Properties</span></span>
  <span data-ttu-id="7ee20-103">**Propiedades personalizadas de origen**</span><span class="sxs-lookup"><span data-stu-id="7ee20-103">**Source Custom Properties**</span></span>  
  
 <span data-ttu-id="7ee20-104">El origen de OLE DB tiene tanto propiedades personalizadas como propiedades comunes a todos los componentes de flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="7ee20-104">The OLE DB source has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="7ee20-105">En la tabla siguiente se describen las propiedades personalizadas del origen de OLE DB.</span><span class="sxs-lookup"><span data-stu-id="7ee20-105">The following table describes the custom properties of the OLE DB source.</span></span> <span data-ttu-id="7ee20-106">Todas las propiedades son de lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="7ee20-106">All properties are read/write.</span></span>  
  
|<span data-ttu-id="7ee20-107">Nombre de propiedad</span><span class="sxs-lookup"><span data-stu-id="7ee20-107">Property name</span></span>|<span data-ttu-id="7ee20-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="7ee20-108">Data Type</span></span>|<span data-ttu-id="7ee20-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ee20-109">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="7ee20-110">AccessMode</span><span class="sxs-lookup"><span data-stu-id="7ee20-110">AccessMode</span></span>|<span data-ttu-id="7ee20-111">Entero</span><span class="sxs-lookup"><span data-stu-id="7ee20-111">Integer</span></span>|<span data-ttu-id="7ee20-112">Modo que se usa para tener acceso a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7ee20-112">The mode used to access the database.</span></span> <span data-ttu-id="7ee20-113">Los valores posibles son **Open Rowset**, **Open Rowset from variable**, `SQL Command` y **SQL Command from variable**.</span><span class="sxs-lookup"><span data-stu-id="7ee20-113">The possible values are **Open Rowset**, **Open Rowset from Variable**, `SQL Command`, and **SQL Command from Variable**.</span></span> <span data-ttu-id="7ee20-114">El valor predeterminado es **Open Rowset**.</span><span class="sxs-lookup"><span data-stu-id="7ee20-114">The default value is **Open Rowset**.</span></span>|  
|<span data-ttu-id="7ee20-115">AlwaysUseDefaultCodePage</span><span class="sxs-lookup"><span data-stu-id="7ee20-115">AlwaysUseDefaultCodePage</span></span>|<span data-ttu-id="7ee20-116">Boolean</span><span class="sxs-lookup"><span data-stu-id="7ee20-116">Boolean</span></span>|<span data-ttu-id="7ee20-117">Valor que indica si usar el valor de la propiedad `DefaultCodePage` para cada columna, o intentar derivar la página de códigos de la configuración regional de cada columna.</span><span class="sxs-lookup"><span data-stu-id="7ee20-117">A value that indicates whether to use the value of the `DefaultCodePage` property for each column, or to try to derive the codepage from each column's locale.</span></span> <span data-ttu-id="7ee20-118">El valor predeterminado de esta propiedad es `False`.</span><span class="sxs-lookup"><span data-stu-id="7ee20-118">The default value of this property is `False`.</span></span>|  
|<span data-ttu-id="7ee20-119">CommandTimeout</span><span class="sxs-lookup"><span data-stu-id="7ee20-119">CommandTimeout</span></span>|<span data-ttu-id="7ee20-120">Entero</span><span class="sxs-lookup"><span data-stu-id="7ee20-120">Integer</span></span>|<span data-ttu-id="7ee20-121">Número de segundos que tienen que transcurrir antes de que un comando supere el tiempo de espera. El valor 0 indica un tiempo infinito.</span><span class="sxs-lookup"><span data-stu-id="7ee20-121">The number of seconds before a command times out. A value of 0 indicates an infinite time-out.</span></span><br /><br /> <span data-ttu-id="7ee20-122">Nota: Esta propiedad no está disponible en el **Editor de origen de OLE DB**, pero se puede definir con el **Editor avanzado**.</span><span class="sxs-lookup"><span data-stu-id="7ee20-122">Note: This property is not available in the **OLE DB Source Editor**, but can be set by using the **Advanced Editor**.</span></span>|  
|<span data-ttu-id="7ee20-123">DefaultCodePage</span><span class="sxs-lookup"><span data-stu-id="7ee20-123">DefaultCodePage</span></span>|<span data-ttu-id="7ee20-124">Entero</span><span class="sxs-lookup"><span data-stu-id="7ee20-124">Integer</span></span>|<span data-ttu-id="7ee20-125">Página de códigos que se usa cuando no hay información disponible de la misma en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="7ee20-125">The code page to use when code page information is unavailable from the data source.</span></span>|  
|<span data-ttu-id="7ee20-126">OpenRowset</span><span class="sxs-lookup"><span data-stu-id="7ee20-126">OpenRowset</span></span>|<span data-ttu-id="7ee20-127">String</span><span class="sxs-lookup"><span data-stu-id="7ee20-127">String</span></span>|<span data-ttu-id="7ee20-128">Nombre del objeto de base de datos que se usa para abrir un conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="7ee20-128">The name of the database object that is used to open a rowset.</span></span>|  
|<span data-ttu-id="7ee20-129">OpenRowsetVariable</span><span class="sxs-lookup"><span data-stu-id="7ee20-129">OpenRowsetVariable</span></span>|<span data-ttu-id="7ee20-130">String</span><span class="sxs-lookup"><span data-stu-id="7ee20-130">String</span></span>|<span data-ttu-id="7ee20-131">Variable que contiene el objeto del objeto de base de datos que se usa para abrir un conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="7ee20-131">The variable that contains the name of the database object that is used to open a rowset.</span></span>|  
|<span data-ttu-id="7ee20-132">ParameterMapping</span><span class="sxs-lookup"><span data-stu-id="7ee20-132">ParameterMapping</span></span>|<span data-ttu-id="7ee20-133">String</span><span class="sxs-lookup"><span data-stu-id="7ee20-133">String</span></span>|<span data-ttu-id="7ee20-134">Asignación de los parámetros del comando SQL a variables.</span><span class="sxs-lookup"><span data-stu-id="7ee20-134">The mapping from parameters in the SQL command to variables.</span></span>|  
|<span data-ttu-id="7ee20-135">SqlCommand</span><span class="sxs-lookup"><span data-stu-id="7ee20-135">SqlCommand</span></span>|<span data-ttu-id="7ee20-136">String</span><span class="sxs-lookup"><span data-stu-id="7ee20-136">String</span></span>|<span data-ttu-id="7ee20-137">Comando SQL que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="7ee20-137">The SQL command to be executed.</span></span>|  
|<span data-ttu-id="7ee20-138">SqlCommandVariable</span><span class="sxs-lookup"><span data-stu-id="7ee20-138">SqlCommandVariable</span></span>|<span data-ttu-id="7ee20-139">String</span><span class="sxs-lookup"><span data-stu-id="7ee20-139">String</span></span>|<span data-ttu-id="7ee20-140">Variable que contiene el comando SQL que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="7ee20-140">The variable that contains the SQL command to be executed.</span></span>|  
  
 <span data-ttu-id="7ee20-141">La salida y las columnas de salida del origen de OLE DB no tienen ninguna propiedad personalizada.</span><span class="sxs-lookup"><span data-stu-id="7ee20-141">The output and the output columns of the OLE DB source have no custom properties.</span></span>  
  
 <span data-ttu-id="7ee20-142">Para más información, consulte [OLE DB Source](ole-db-source.md).</span><span class="sxs-lookup"><span data-stu-id="7ee20-142">For more information, see [OLE DB Source](ole-db-source.md).</span></span>  
  
 <span data-ttu-id="7ee20-143">**Propiedades personalizadas de los destinos**</span><span class="sxs-lookup"><span data-stu-id="7ee20-143">**Destination Custom Properties**</span></span>  
  
 <span data-ttu-id="7ee20-144">El destino de OLE DB tiene propiedades personalizadas y propiedades comunes a todos los componentes de flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="7ee20-144">The OLE DB destination has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="7ee20-145">En la tabla siguiente se describen las propiedades personalizadas del destino OLE DB.</span><span class="sxs-lookup"><span data-stu-id="7ee20-145">The following table describes the custom properties of the OLE DB destination.</span></span> <span data-ttu-id="7ee20-146">Todas las propiedades son de lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="7ee20-146">All properties are read/write.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7ee20-147">Las opciones de carga rápida enumeradas aquí (FastLoadKeepIdentity, FastLoadKeepNulls y FastLoadOptions) corresponden a las propiedades con nombre similar que expone la interfaz `IRowsetFastLoad` implementada por el proveedor Microsoft OLE DB para SQL Server (SQLOLEDB).</span><span class="sxs-lookup"><span data-stu-id="7ee20-147">The FastLoad options listed here (FastLoadKeepIdentity, FastLoadKeepNulls, and FastLoadOptions) correspond to the similarly named properties exposed by the `IRowsetFastLoad` interface implemented by the Microsoft OLE DB Provider for SQL Server (SQLOLEDB).</span></span> <span data-ttu-id="7ee20-148">Para obtener más información, busque IRowsetFastLoad en la MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="7ee20-148">For more information, search for IRowsetFastLoad in the MSDN Library.</span></span>  
  
|<span data-ttu-id="7ee20-149">Nombre de propiedad</span><span class="sxs-lookup"><span data-stu-id="7ee20-149">Property name</span></span>|<span data-ttu-id="7ee20-150">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="7ee20-150">Data Type</span></span>|<span data-ttu-id="7ee20-151">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ee20-151">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="7ee20-152">AccessMode</span><span class="sxs-lookup"><span data-stu-id="7ee20-152">AccessMode</span></span>|<span data-ttu-id="7ee20-153">Integer (enumeración)</span><span class="sxs-lookup"><span data-stu-id="7ee20-153">Integer (enumeration)</span></span>|<span data-ttu-id="7ee20-154">Valor que especifica cómo tiene acceso el destino a su base de datos de destino.</span><span class="sxs-lookup"><span data-stu-id="7ee20-154">A value that specifies how the destination access its destination database.</span></span><br /><br /> <span data-ttu-id="7ee20-155">Esta propiedad admite cualquiera de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="7ee20-155">This property can have one of the following values:</span></span><br /><br /> <span data-ttu-id="7ee20-156">`OpenRowset`(0): se proporciona el nombre de una tabla o vista.</span><span class="sxs-lookup"><span data-stu-id="7ee20-156">`OpenRowset` (0): You provide the name of a table or view.</span></span><br /><span data-ttu-id="7ee20-157">`OpenRowset from Variable`(1): se proporciona el nombre de una variable que contiene el nombre de una tabla o vista.</span><span class="sxs-lookup"><span data-stu-id="7ee20-157">`OpenRowset from Variable` (1): You provide the name of a variable that contains the name of a table or view.</span></span><br /><span data-ttu-id="7ee20-158">`OpenRowset Using Fastload`(3): se proporciona el nombre de una tabla o vista.</span><span class="sxs-lookup"><span data-stu-id="7ee20-158">`OpenRowset Using Fastload` (3): You provide the name of a table or view.</span></span><br /><span data-ttu-id="7ee20-159">`OpenRowset Using Fastload from Variable`(4): se proporciona el nombre de una variable que contiene el nombre de una tabla o vista.</span><span class="sxs-lookup"><span data-stu-id="7ee20-159">`OpenRowset Using Fastload from Variable` (4): You provide the name of a variable that contains the name of a table or view.</span></span><br /><span data-ttu-id="7ee20-160">`SQL Command`(2): se proporciona una instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="7ee20-160">`SQL Command` (2): You provide a SQL statement.</span></span>|  
|<span data-ttu-id="7ee20-161">AlwaysUseDefaultCodePage</span><span class="sxs-lookup"><span data-stu-id="7ee20-161">AlwaysUseDefaultCodePage</span></span>|<span data-ttu-id="7ee20-162">Boolean</span><span class="sxs-lookup"><span data-stu-id="7ee20-162">Boolean</span></span>|<span data-ttu-id="7ee20-163">Valor que indica si usar el valor de la propiedad `DefaultCodePage` para cada columna, o intentar derivar la página de códigos de la configuración regional de cada columna.</span><span class="sxs-lookup"><span data-stu-id="7ee20-163">A value that indicates whether to use the value of the `DefaultCodePage` property for each column, or to try to derive the codepage from each column's locale.</span></span> <span data-ttu-id="7ee20-164">El valor predeterminado de esta propiedad es `False`.</span><span class="sxs-lookup"><span data-stu-id="7ee20-164">The default value of this property is `False`.</span></span>|  
|<span data-ttu-id="7ee20-165">CommandTimeout</span><span class="sxs-lookup"><span data-stu-id="7ee20-165">CommandTimeout</span></span>|<span data-ttu-id="7ee20-166">Entero</span><span class="sxs-lookup"><span data-stu-id="7ee20-166">Integer</span></span>|<span data-ttu-id="7ee20-167">Número máximo de segundos que el comando SQL se puede ejecutar antes de superar el tiempo de espera. Un valor de 0 indica un tiempo infinito.</span><span class="sxs-lookup"><span data-stu-id="7ee20-167">The maximum number of seconds that the SQL command can run before timing out. A value of 0 indicates an infinite time.</span></span> <span data-ttu-id="7ee20-168">El valor predeterminado de esta propiedad es 0.</span><span class="sxs-lookup"><span data-stu-id="7ee20-168">The default value of this property is 0.</span></span><br /><br /> <span data-ttu-id="7ee20-169">Nota: Esta propiedad no está disponible en el **Editor de destino OLE DB**, pero se puede definir con el **Editor avanzado**.</span><span class="sxs-lookup"><span data-stu-id="7ee20-169">Note: This property is not available in the **OLE DB Destination Editor**, but can be set by using the **Advanced Editor**.</span></span>|  
|<span data-ttu-id="7ee20-170">DefaultCodePage</span><span class="sxs-lookup"><span data-stu-id="7ee20-170">DefaultCodePage</span></span>|<span data-ttu-id="7ee20-171">Entero</span><span class="sxs-lookup"><span data-stu-id="7ee20-171">Integer</span></span>|<span data-ttu-id="7ee20-172">Página de códigos predeterminada asociada al destino OLE DB.</span><span class="sxs-lookup"><span data-stu-id="7ee20-172">The default codepage associated with the OLE DB destination.</span></span>|  
|<span data-ttu-id="7ee20-173">FastLoadKeepIdentity</span><span class="sxs-lookup"><span data-stu-id="7ee20-173">FastLoadKeepIdentity</span></span>|<span data-ttu-id="7ee20-174">Boolean</span><span class="sxs-lookup"><span data-stu-id="7ee20-174">Boolean</span></span>|<span data-ttu-id="7ee20-175">Valor que especifica si se copian los valores de identidad cuando se cargan los datos.</span><span class="sxs-lookup"><span data-stu-id="7ee20-175">A value that specifies whether to copy identity values when data is loaded.</span></span> <span data-ttu-id="7ee20-176">Esta propiedad solo está disponible con una de las opciones de carga rápida.</span><span class="sxs-lookup"><span data-stu-id="7ee20-176">This property is available only with one of the fast load options.</span></span> <span data-ttu-id="7ee20-177">El valor predeterminado de esta propiedad es `False`.</span><span class="sxs-lookup"><span data-stu-id="7ee20-177">The default value of this property is `False`.</span></span> <span data-ttu-id="7ee20-178">Esta propiedad corresponde a la propiedad OLE DB [IRowsetFastLoad &#40;OLE DB&#41;](../../relational-databases/native-client-ole-db-interfaces/irowsetfastload-ole-db.md) `SSPROP_FASTLOADKEEPIDENTITY` .</span><span class="sxs-lookup"><span data-stu-id="7ee20-178">This property corresponds to the OLE DB [IRowsetFastLoad &#40;OLE DB&#41;](../../relational-databases/native-client-ole-db-interfaces/irowsetfastload-ole-db.md) property `SSPROP_FASTLOADKEEPIDENTITY`.</span></span>|  
|<span data-ttu-id="7ee20-179">FastLoadKeepNulls</span><span class="sxs-lookup"><span data-stu-id="7ee20-179">FastLoadKeepNulls</span></span>|<span data-ttu-id="7ee20-180">Boolean</span><span class="sxs-lookup"><span data-stu-id="7ee20-180">Boolean</span></span>|<span data-ttu-id="7ee20-181">Valor que especifica si se copian los valores Null cuando se cargan los datos.</span><span class="sxs-lookup"><span data-stu-id="7ee20-181">A value that specifies whether to copy Null values when data is loaded.</span></span> <span data-ttu-id="7ee20-182">Esta propiedad solo está disponible con una de las opciones de carga rápida.</span><span class="sxs-lookup"><span data-stu-id="7ee20-182">This property is available only with one of the fast load options.</span></span> <span data-ttu-id="7ee20-183">El valor predeterminado de esta propiedad es `False`.</span><span class="sxs-lookup"><span data-stu-id="7ee20-183">The default value of this property is `False`.</span></span> <span data-ttu-id="7ee20-184">Esta propiedad corresponde a la propiedad OLE DB [IRowsetFastLoad &#40;OLE DB&#41;](../../relational-databases/native-client-ole-db-interfaces/irowsetfastload-ole-db.md) `SSPROP_FASTLOADKEEPNULLS` .</span><span class="sxs-lookup"><span data-stu-id="7ee20-184">This property corresponds to the OLE DB [IRowsetFastLoad &#40;OLE DB&#41;](../../relational-databases/native-client-ole-db-interfaces/irowsetfastload-ole-db.md) property `SSPROP_FASTLOADKEEPNULLS`.</span></span>|  
|<span data-ttu-id="7ee20-185">FastLoadMaxInsertCommitSize</span><span class="sxs-lookup"><span data-stu-id="7ee20-185">FastLoadMaxInsertCommitSize</span></span>|<span data-ttu-id="7ee20-186">Entero</span><span class="sxs-lookup"><span data-stu-id="7ee20-186">Integer</span></span>|<span data-ttu-id="7ee20-187">Valor que especifica el tamaño de lote que el destino OLE DB intenta confirmar en operaciones de carga rápida.</span><span class="sxs-lookup"><span data-stu-id="7ee20-187">A value that specifies the batch size that the OLE DB destination tries to commit during fast load operations.</span></span> <span data-ttu-id="7ee20-188">El valor predeterminado, **0**, indica una operación de confirmación única después de que se procesen todas las filas.</span><span class="sxs-lookup"><span data-stu-id="7ee20-188">The default value, **0**, indicates a single commit operation after all rows are processed.</span></span>|  
|<span data-ttu-id="7ee20-189">FastLoadOptions</span><span class="sxs-lookup"><span data-stu-id="7ee20-189">FastLoadOptions</span></span>|<span data-ttu-id="7ee20-190">String</span><span class="sxs-lookup"><span data-stu-id="7ee20-190">String</span></span>|<span data-ttu-id="7ee20-191">Colección de opciones de carga rápida.</span><span class="sxs-lookup"><span data-stu-id="7ee20-191">A collection of fast load options.</span></span> <span data-ttu-id="7ee20-192">Las opciones de carga rápida incluyen el bloqueo de las tablas y la comprobación de las restricciones.</span><span class="sxs-lookup"><span data-stu-id="7ee20-192">The fast load options include the locking of tables and the checking of constraints.</span></span> <span data-ttu-id="7ee20-193">Puede especificar una, ambas o ninguna.</span><span class="sxs-lookup"><span data-stu-id="7ee20-193">You can specify one, both, or neither.</span></span> <span data-ttu-id="7ee20-194">Esta propiedad corresponde a la propiedad OLE DB IRowsetFastLoad `SSPROP_FASTLOADOPTIONS` y acepta opciones de cadena como `CHECK_CONSTRAINTS` y `TABLOCK` .</span><span class="sxs-lookup"><span data-stu-id="7ee20-194">This property corresponds to the OLE DB IRowsetFastLoad property `SSPROP_FASTLOADOPTIONS` and accepts string options such as `CHECK_CONSTRAINTS` and `TABLOCK`.</span></span><br /><br /> <span data-ttu-id="7ee20-195">Nota: Algunas opciones de esta propiedad no están disponibles en el **Editor de destino de Excel**, pero pueden definirse con el **Editor avanzado**.</span><span class="sxs-lookup"><span data-stu-id="7ee20-195">Note: Some options for this property are not available in the **Excel Destination Editor**, but can be set by using the **Advanced Editor**.</span></span>|  
|<span data-ttu-id="7ee20-196">OpenRowset</span><span class="sxs-lookup"><span data-stu-id="7ee20-196">OpenRowset</span></span>|<span data-ttu-id="7ee20-197">String</span><span class="sxs-lookup"><span data-stu-id="7ee20-197">String</span></span>|<span data-ttu-id="7ee20-198">Cuando AccessMode es `OpenRowset` , el nombre de la tabla o vista a la que tiene acceso el OLE DB de destino.</span><span class="sxs-lookup"><span data-stu-id="7ee20-198">When AccessMode is `OpenRowset`, the name of the table or view that the OLE DB destination accesses.</span></span>|  
|<span data-ttu-id="7ee20-199">OpenRowsetVariable</span><span class="sxs-lookup"><span data-stu-id="7ee20-199">OpenRowsetVariable</span></span>|<span data-ttu-id="7ee20-200">String</span><span class="sxs-lookup"><span data-stu-id="7ee20-200">String</span></span>|<span data-ttu-id="7ee20-201">Cuando AccessMode es `OpenRowset from Variable` , el nombre de la variable que contiene el nombre de la tabla o vista a la que el destino de OLE DB tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="7ee20-201">When AccessMode is `OpenRowset from Variable`, the name of the variable that contains the name of the table or view that the OLE DB destination accesses.</span></span>|  
|<span data-ttu-id="7ee20-202">SqlCommand</span><span class="sxs-lookup"><span data-stu-id="7ee20-202">SqlCommand</span></span>|<span data-ttu-id="7ee20-203">String</span><span class="sxs-lookup"><span data-stu-id="7ee20-203">String</span></span>|<span data-ttu-id="7ee20-204">Cuando AccessMode es `SQL Command` , la instrucción de Transact-SQL que el destino OLE DB utiliza para especificar las columnas de destino de los datos.</span><span class="sxs-lookup"><span data-stu-id="7ee20-204">When AccessMode is `SQL Command`, the Transact-SQL statement that the OLE DB destination uses to specify the destination columns for the data.</span></span>|  
  
 <span data-ttu-id="7ee20-205">La entrada y las columnas de entrada del destino de OLE DB no tienen ninguna propiedad personalizada.</span><span class="sxs-lookup"><span data-stu-id="7ee20-205">The input and the input columns of the OLE DB destination have no custom properties.</span></span>  
  
 <span data-ttu-id="7ee20-206">Para más información, consulte [OLE DB Destination](ole-db-destination.md).</span><span class="sxs-lookup"><span data-stu-id="7ee20-206">For more information, see [OLE DB Destination](ole-db-destination.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ee20-207">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7ee20-207">See Also</span></span>  
 [<span data-ttu-id="7ee20-208">Common Properties</span><span class="sxs-lookup"><span data-stu-id="7ee20-208">Common Properties</span></span>](../common-properties.md)  
  
  