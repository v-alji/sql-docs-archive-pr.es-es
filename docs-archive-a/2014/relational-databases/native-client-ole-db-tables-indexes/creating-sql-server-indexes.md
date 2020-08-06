---
title: Creación de índices de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- CreateIndex function
- constraints [OLE DB]
- SQL Server Native Client OLE DB provider, indexes
- indexes [OLE DB]
- adding indexes
ms.assetid: 6239d440-2818-4b98-bb79-732dced41952
author: rothja
ms.author: jroth
ms.openlocfilehash: 3693355eec7a290c03658c10db500161aa52062d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749258"
---
# <a name="creating-sql-server-indexes"></a><span data-ttu-id="0811e-102">Crear índices de SQL Server</span><span class="sxs-lookup"><span data-stu-id="0811e-102">Creating SQL Server Indexes</span></span>
  <span data-ttu-id="0811e-103">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client expone la función **IIndexDefinition:: CreateIndex** , lo que permite a los consumidores definir nuevos índices en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] las tablas.</span><span class="sxs-lookup"><span data-stu-id="0811e-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **IIndexDefinition::CreateIndex** function, allowing consumers to define new indexes on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables.</span></span>  
  
 <span data-ttu-id="0811e-104">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client crea los índices de tabla como índices o restricciones.</span><span class="sxs-lookup"><span data-stu-id="0811e-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider creates table indexes as either indexes or constraints.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0811e-105">da privilegio de creación de restricciones al propietario de la tabla, el propietario de la base de datos y los miembros de ciertos roles administrativos.</span><span class="sxs-lookup"><span data-stu-id="0811e-105">gives constraint-creation privilege to the table owner, database owner, and members of certain administrative roles.</span></span> <span data-ttu-id="0811e-106">De forma predeterminada, solamente el propietario de la tabla puede crear un índice en una tabla.</span><span class="sxs-lookup"><span data-stu-id="0811e-106">By default, only the table owner can create an index on a table.</span></span> <span data-ttu-id="0811e-107">Por tanto, que la ejecución de **CreateIndex** sea correcta o no depende no solo de los derechos de acceso del usuario de la aplicación, sino también del tipo de índice creado.</span><span class="sxs-lookup"><span data-stu-id="0811e-107">Therefore, the success or failure of **CreateIndex** depends not only on the application user's access rights but also on the type of index created.</span></span>  
  
 <span data-ttu-id="0811e-108">Los consumidores especifican el nombre de tabla como una cadena de caracteres Unicode en el miembro *pwszName* de la unión *uName* en el parámetro *pTableID*.</span><span class="sxs-lookup"><span data-stu-id="0811e-108">Consumers specify the table name as a Unicode character string in the *pwszName* member of the *uName* union in the *pTableID* parameter.</span></span> <span data-ttu-id="0811e-109">El miembro *eKind* de *pTableID* debe ser DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="0811e-109">The *eKind* member of *pTableID* must be DBKIND_NAME.</span></span>  
  
 <span data-ttu-id="0811e-110">El parámetro *pIndexID* puede ser NULL y, si es así, el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client crea un nombre único para el índice.</span><span class="sxs-lookup"><span data-stu-id="0811e-110">The *pIndexID* parameter can be NULL, and if it is, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider creates a unique name for the index.</span></span> <span data-ttu-id="0811e-111">El consumidor puede capturar el nombre del índice especificando un puntero válido a un DBID en el parámetro *ppIndexID*.</span><span class="sxs-lookup"><span data-stu-id="0811e-111">The consumer can capture the name of the index by specifying a valid pointer to a DBID in the *ppIndexID* parameter.</span></span>  
  
 <span data-ttu-id="0811e-112">El consumidor puede especificar el nombre del índice como una cadena de caracteres Unicode en el miembro *pwszName* de la unión *uName* del parámetro *pIndexID*.</span><span class="sxs-lookup"><span data-stu-id="0811e-112">The consumer can specify the index name as a Unicode character string in the *pwszName* member of the *uName* union of the *pIndexID* parameter.</span></span> <span data-ttu-id="0811e-113">El miembro *eKind* de *pIndexID* debe ser DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="0811e-113">The *eKind* member of *pIndexID* must be DBKIND_NAME.</span></span>  
  
 <span data-ttu-id="0811e-114">El consumidor especifica la columna o columnas que participan en el índice por nombre.</span><span class="sxs-lookup"><span data-stu-id="0811e-114">The consumer specifies the column or columns participating in the index by name.</span></span> <span data-ttu-id="0811e-115">Para cada estructura de DBINDEXCOLUMNDESC usada en **CreateIndex**, el miembro *eKind* de *pColumnID* debe ser DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="0811e-115">For each DBINDEXCOLUMNDESC structure used in **CreateIndex**, the *eKind* member of the *pColumnID* must be DBKIND_NAME.</span></span> <span data-ttu-id="0811e-116">El nombre de la columna se especifica como una cadena de caracteres Unicode en el miembro *pwszName* de la unión *uName* en *pColumnID*.</span><span class="sxs-lookup"><span data-stu-id="0811e-116">The name of the column is specified as a Unicode character string in the *pwszName* member of the *uName* union in the *pColumnID*.</span></span>  
  
 <span data-ttu-id="0811e-117">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client y [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] admiten el orden ascendente de los valores del índice.</span><span class="sxs-lookup"><span data-stu-id="0811e-117">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] support ascending order on values in the index.</span></span> <span data-ttu-id="0811e-118">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client devuelve E_INVALIDARG si el consumidor especifica DBINDEX_COL_ORDER_DESC en cualquier estructura DBINDEXCOLUMNDESC.</span><span class="sxs-lookup"><span data-stu-id="0811e-118">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns E_INVALIDARG if the consumer specifies DBINDEX_COL_ORDER_DESC in any DBINDEXCOLUMNDESC structure.</span></span>  
  
 <span data-ttu-id="0811e-119">**CreateIndex** interpreta las propiedades del índice como sigue.</span><span class="sxs-lookup"><span data-stu-id="0811e-119">**CreateIndex** interprets index properties as follows.</span></span>  
  
|<span data-ttu-id="0811e-120">Id. de propiedad</span><span class="sxs-lookup"><span data-stu-id="0811e-120">Property ID</span></span>|<span data-ttu-id="0811e-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="0811e-121">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="0811e-122">DBPROP_INDEX_AUTOUPDATE</span><span class="sxs-lookup"><span data-stu-id="0811e-122">DBPROP_INDEX_AUTOUPDATE</span></span>|<span data-ttu-id="0811e-123">R (lectura) y W (escritura): Lectura/escritura</span><span class="sxs-lookup"><span data-stu-id="0811e-123">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="0811e-124">Valor predeterminado: ninguno</span><span class="sxs-lookup"><span data-stu-id="0811e-124">Default: None</span></span><br /><br /> <span data-ttu-id="0811e-125">Descripción: el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client no admite esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="0811e-125">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="0811e-126">Los intentos de establecer la propiedad en **CreateIndex** producen un valor devuelto de DB_S_ERRORSOCCURRED.</span><span class="sxs-lookup"><span data-stu-id="0811e-126">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="0811e-127">El miembro *dwStatus* de la estructura de propiedad indica DBPROPSTATUS_BADVALUE.</span><span class="sxs-lookup"><span data-stu-id="0811e-127">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="0811e-128">DBPROP_INDEX_CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="0811e-128">DBPROP_INDEX_CLUSTERED</span></span>|<span data-ttu-id="0811e-129">R (lectura) y W (escritura): Lectura/escritura</span><span class="sxs-lookup"><span data-stu-id="0811e-129">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="0811e-130">Valor predeterminado: VARIANT_FALSE</span><span class="sxs-lookup"><span data-stu-id="0811e-130">Default: VARIANT_FALSE</span></span><br /><br /> <span data-ttu-id="0811e-131">Descripción: controla la agrupación en clústeres de índices.</span><span class="sxs-lookup"><span data-stu-id="0811e-131">Description: Controls index clustering.</span></span><br /><br /> <span data-ttu-id="0811e-132">VARIANT_TRUE: el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client intenta crear un índice clúster en la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabla.</span><span class="sxs-lookup"><span data-stu-id="0811e-132">VARIANT_TRUE: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider attempts to create a clustered index on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0811e-133">admite a lo sumo un índice clúster en cualquier tabla.</span><span class="sxs-lookup"><span data-stu-id="0811e-133">supports at most one clustered index on any table.</span></span><br /><br /> <span data-ttu-id="0811e-134">VARIANT_FALSE: el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client intenta crear un índice no clúster en la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabla.</span><span class="sxs-lookup"><span data-stu-id="0811e-134">VARIANT_FALSE: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider attempts to create a nonclustered index on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>|  
|<span data-ttu-id="0811e-135">DBPROP_INDEX_FILLFACTOR</span><span class="sxs-lookup"><span data-stu-id="0811e-135">DBPROP_INDEX_FILLFACTOR</span></span>|<span data-ttu-id="0811e-136">R (lectura) y W (escritura): Lectura/escritura</span><span class="sxs-lookup"><span data-stu-id="0811e-136">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="0811e-137">Predeterminado: 0</span><span class="sxs-lookup"><span data-stu-id="0811e-137">Default: 0</span></span><br /><br /> <span data-ttu-id="0811e-138">Descripción: especifica el porcentaje de una página de índice utilizado para el almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="0811e-138">Description: Specifies the percentage of an index page used for storage.</span></span> <span data-ttu-id="0811e-139">Para obtener más información, vea [CREATE INDEX](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0811e-139">For more information, see [CREATE INDEX](/sql/t-sql/statements/create-index-transact-sql).</span></span><br /><br /> <span data-ttu-id="0811e-140">El tipo del variant es VT_I4.</span><span class="sxs-lookup"><span data-stu-id="0811e-140">The type of the variant is VT_I4.</span></span> <span data-ttu-id="0811e-141">El valor debe ser mayor o igual que 1 y menor o igual que 100.</span><span class="sxs-lookup"><span data-stu-id="0811e-141">The value must be greater than or equal to 1 and less than or equal to 100.</span></span>|  
|<span data-ttu-id="0811e-142">DBPROP_INDEX_INITIALIZE</span><span class="sxs-lookup"><span data-stu-id="0811e-142">DBPROP_INDEX_INITIALIZE</span></span>|<span data-ttu-id="0811e-143">R (lectura) y W (escritura): Lectura/escritura</span><span class="sxs-lookup"><span data-stu-id="0811e-143">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="0811e-144">Valor predeterminado: ninguno</span><span class="sxs-lookup"><span data-stu-id="0811e-144">Default: None</span></span><br /><br /> <span data-ttu-id="0811e-145">Descripción: el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client no admite esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="0811e-145">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="0811e-146">Los intentos de establecer la propiedad en **CreateIndex** producen un valor devuelto de DB_S_ERRORSOCCURRED.</span><span class="sxs-lookup"><span data-stu-id="0811e-146">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="0811e-147">El miembro *dwStatus* de la estructura de propiedad indica DBPROPSTATUS_BADVALUE.</span><span class="sxs-lookup"><span data-stu-id="0811e-147">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="0811e-148">DBPROP_INDEX_NULLCOLLATION</span><span class="sxs-lookup"><span data-stu-id="0811e-148">DBPROP_INDEX_NULLCOLLATION</span></span>|<span data-ttu-id="0811e-149">R (lectura) y W (escritura): Lectura/escritura</span><span class="sxs-lookup"><span data-stu-id="0811e-149">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="0811e-150">Valor predeterminado: ninguno</span><span class="sxs-lookup"><span data-stu-id="0811e-150">Default: None</span></span><br /><br /> <span data-ttu-id="0811e-151">Descripción: el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client no admite esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="0811e-151">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="0811e-152">Los intentos de establecer la propiedad en **CreateIndex** producen un valor devuelto de DB_S_ERRORSOCCURRED.</span><span class="sxs-lookup"><span data-stu-id="0811e-152">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="0811e-153">El miembro *dwStatus* de la estructura de propiedad indica DBPROPSTATUS_BADVALUE.</span><span class="sxs-lookup"><span data-stu-id="0811e-153">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="0811e-154">DBPROP_INDEX_NULLS</span><span class="sxs-lookup"><span data-stu-id="0811e-154">DBPROP_INDEX_NULLS</span></span>|<span data-ttu-id="0811e-155">R (lectura) y W (escritura): Lectura/escritura</span><span class="sxs-lookup"><span data-stu-id="0811e-155">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="0811e-156">Valor predeterminado: ninguno</span><span class="sxs-lookup"><span data-stu-id="0811e-156">Default: None</span></span><br /><br /> <span data-ttu-id="0811e-157">Descripción: el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client no admite esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="0811e-157">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="0811e-158">Los intentos de establecer la propiedad en **CreateIndex** producen un valor devuelto de DB_S_ERRORSOCCURRED.</span><span class="sxs-lookup"><span data-stu-id="0811e-158">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="0811e-159">El miembro *dwStatus* de la estructura de propiedad indica DBPROPSTATUS_BADVALUE.</span><span class="sxs-lookup"><span data-stu-id="0811e-159">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="0811e-160">DBPROP_INDEX_PRIMARYKEY</span><span class="sxs-lookup"><span data-stu-id="0811e-160">DBPROP_INDEX_PRIMARYKEY</span></span>|<span data-ttu-id="0811e-161">R (lectura) y W (escritura): Lectura/escritura</span><span class="sxs-lookup"><span data-stu-id="0811e-161">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="0811e-162">Valor predeterminado: VARIANT_FALSE. Descripción: crea el índice como una integridad referencial, restricción PRIMARY KEY.</span><span class="sxs-lookup"><span data-stu-id="0811e-162">Default: VARIANT_FALSE Description: Creates the index as a referential integrity, PRIMARY KEY constraint.</span></span><br /><br /> <span data-ttu-id="0811e-163">VARIANT_TRUE: el índice se crea para admitir la restricción PRIMARY KEY de la tabla.</span><span class="sxs-lookup"><span data-stu-id="0811e-163">VARIANT_TRUE: The index is created to support the PRIMARY KEY constraint of the table.</span></span> <span data-ttu-id="0811e-164">Las columnas no deben admitir valores NULL.</span><span class="sxs-lookup"><span data-stu-id="0811e-164">The columns must be nonnullable.</span></span><br /><br /> <span data-ttu-id="0811e-165">VARIANT_FALSE: el índice no se utiliza como una restricción PRIMARY KEY para los valores de fila de la tabla.</span><span class="sxs-lookup"><span data-stu-id="0811e-165">VARIANT_FALSE: The index is not used as a PRIMARY KEY constraint for row values in the table.</span></span>|  
|<span data-ttu-id="0811e-166">DBPROP_INDEX_SORTBOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="0811e-166">DBPROP_INDEX_SORTBOOKMARKS</span></span>|<span data-ttu-id="0811e-167">R (lectura) y W (escritura): Lectura/escritura</span><span class="sxs-lookup"><span data-stu-id="0811e-167">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="0811e-168">Valor predeterminado: ninguno</span><span class="sxs-lookup"><span data-stu-id="0811e-168">Default: None</span></span><br /><br /> <span data-ttu-id="0811e-169">Descripción: el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client no admite esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="0811e-169">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="0811e-170">Los intentos de establecer la propiedad en **CreateIndex** producen un valor devuelto de DB_S_ERRORSOCCURRED.</span><span class="sxs-lookup"><span data-stu-id="0811e-170">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="0811e-171">El miembro *dwStatus* de la estructura de propiedad indica DBPROPSTATUS_BADVALUE.</span><span class="sxs-lookup"><span data-stu-id="0811e-171">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="0811e-172">DBPROP_INDEX_TEMPINDEX</span><span class="sxs-lookup"><span data-stu-id="0811e-172">DBPROP_INDEX_TEMPINDEX</span></span>|<span data-ttu-id="0811e-173">R (lectura) y W (escritura): Lectura/escritura</span><span class="sxs-lookup"><span data-stu-id="0811e-173">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="0811e-174">Valor predeterminado: ninguno</span><span class="sxs-lookup"><span data-stu-id="0811e-174">Default: None</span></span><br /><br /> <span data-ttu-id="0811e-175">Descripción: el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client no admite esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="0811e-175">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="0811e-176">Los intentos de establecer la propiedad en **CreateIndex** producen un valor devuelto de DB_S_ERRORSOCCURRED.</span><span class="sxs-lookup"><span data-stu-id="0811e-176">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="0811e-177">El miembro *dwStatus* de la estructura de propiedad indica DBPROPSTATUS_BADVALUE.</span><span class="sxs-lookup"><span data-stu-id="0811e-177">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="0811e-178">DBPROP_INDEX_TYPE</span><span class="sxs-lookup"><span data-stu-id="0811e-178">DBPROP_INDEX_TYPE</span></span>|<span data-ttu-id="0811e-179">R (lectura) y W (escritura): Lectura/escritura</span><span class="sxs-lookup"><span data-stu-id="0811e-179">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="0811e-180">Valor predeterminado: ninguno</span><span class="sxs-lookup"><span data-stu-id="0811e-180">Default: None</span></span><br /><br /> <span data-ttu-id="0811e-181">Descripción: el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client no admite esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="0811e-181">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="0811e-182">Los intentos de establecer la propiedad en **CreateIndex** producen un valor devuelto de DB_S_ERRORSOCCURRED.</span><span class="sxs-lookup"><span data-stu-id="0811e-182">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="0811e-183">El miembro *dwStatus* de la estructura de propiedad indica DBPROPSTATUS_BADVALUE.</span><span class="sxs-lookup"><span data-stu-id="0811e-183">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="0811e-184">DBPROP_INDEX_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="0811e-184">DBPROP_INDEX_UNIQUE</span></span>|<span data-ttu-id="0811e-185">R (lectura) y W (escritura): Lectura/escritura</span><span class="sxs-lookup"><span data-stu-id="0811e-185">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="0811e-186">Valor predeterminado: VARIANT_FALSE</span><span class="sxs-lookup"><span data-stu-id="0811e-186">Default: VARIANT_FALSE</span></span><br /><br /> <span data-ttu-id="0811e-187">Descripción: crea el índice como una restricción UNIQUE en la columna o columnas participantes.</span><span class="sxs-lookup"><span data-stu-id="0811e-187">Description: Creates the index as a UNIQUE constraint on the participating column or columns.</span></span><br /><br /> <span data-ttu-id="0811e-188">VARIANT_TRUE: el índice se utiliza para restringir de forma única los valores de fila de la tabla.</span><span class="sxs-lookup"><span data-stu-id="0811e-188">VARIANT_TRUE: The index is used to uniquely constrain row values in the table.</span></span><br /><br /> <span data-ttu-id="0811e-189">VARIANT_FALSE: el índice no restringe de forma exclusiva los valores de fila.</span><span class="sxs-lookup"><span data-stu-id="0811e-189">VARIANT_FALSE: The index does not uniquely constrain row values.</span></span>|  
  
 <span data-ttu-id="0811e-190">En el conjunto de propiedades específico del proveedor DBPROPSET_SQLSERVERINDEX, el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client define la siguiente propiedad de información de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="0811e-190">In the provider-specific property set DBPROPSET_SQLSERVERINDEX, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider defines the following data source information property.</span></span>  
  
|<span data-ttu-id="0811e-191">Id. de propiedad</span><span class="sxs-lookup"><span data-stu-id="0811e-191">Property ID</span></span>|<span data-ttu-id="0811e-192">Descripción</span><span class="sxs-lookup"><span data-stu-id="0811e-192">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="0811e-193">SSPROP_INDEX_XML</span><span class="sxs-lookup"><span data-stu-id="0811e-193">SSPROP_INDEX_XML</span></span>|<span data-ttu-id="0811e-194">Tipo: VT_BOOL (L/E)</span><span class="sxs-lookup"><span data-stu-id="0811e-194">Type: VT_BOOL (R/W)</span></span><br /><br /> <span data-ttu-id="0811e-195">Valor predeterminado: VARIANT_FALSE</span><span class="sxs-lookup"><span data-stu-id="0811e-195">Default: VARIANT_FALSE</span></span><br /><br /> <span data-ttu-id="0811e-196">Descripción: cuando esta propiedad se especifica con un valor de VARIANT_TRUE con IIndexDefinition::CreateIndex, da como resultado la creación de un índice xml primario correspondiente a la columna que se está indizando.</span><span class="sxs-lookup"><span data-stu-id="0811e-196">Description: When this property is specified with a value of VARIANT_TRUE with IIndexDefinition::CreateIndex, it results in a primary xml index being created corresponding to the column being indexed.</span></span> <span data-ttu-id="0811e-197">Si esta propiedad es VARIANT_TRUE, cIndexColumnDescs debe ser 1, de lo contrario es un error.</span><span class="sxs-lookup"><span data-stu-id="0811e-197">If this property is VARIANT_TRUE, cIndexColumnDescs should be 1, otherwise it is an error.</span></span>|  
  
 <span data-ttu-id="0811e-198">En este ejemplo se crea un índice de la clave principal:</span><span class="sxs-lookup"><span data-stu-id="0811e-198">This example creates a primary key index:</span></span>  
  
```  
// This CREATE TABLE statement shows the referential integrity and   
// PRIMARY KEY constraint on the OrderDetails table that will be created   
// by the following example code.  
//  
// CREATE TABLE OrderDetails  
// (  
//    OrderID      int      NOT NULL  
//    ProductID   int      NOT NULL  
//        CONSTRAINT PK_OrderDetails  
//        PRIMARY KEY CLUSTERED (OrderID, ProductID),  
//    UnitPrice   money      NOT NULL,  
//    Quantity   int      NOT NULL,  
//    Discount   decimal(2,2)   NOT NULL  
//        DEFAULT 0  
// )  
//  
HRESULT CreatePrimaryKey  
    (  
    IIndexDefinition* pIIndexDefinition  
    )  
    {  
    HRESULT             hr = S_OK;  
  
    DBID                dbidTable;  
    DBID                dbidIndex;  
    const ULONG         nCols = 2;  
    ULONG               nCol;  
    const ULONG         nProps = 2;  
    ULONG               nProp;  
  
    DBINDEXCOLUMNDESC   dbidxcoldesc[nCols];  
    DBPROP              dbpropIndex[nProps];  
    DBPROPSET           dbpropset;  
  
    DBID*               pdbidIndexOut = NULL;  
  
    // Set up identifiers for the table and index.  
    dbidTable.eKind = DBKIND_NAME;  
    dbidTable.uName.pwszName = L"OrderDetails";  
  
    dbidIndex.eKind = DBKIND_NAME;  
    dbidIndex.uName.pwszName = L"PK_OrderDetails";  
  
    // Set up column identifiers.  
    for (nCol = 0; nCol < nCols; nCol++)  
        {  
        dbidxcoldesc[nCol].pColumnID = new DBID;  
        dbidxcoldesc[nCol].pColumnID->eKind = DBKIND_NAME;  
  
        dbidxcoldesc[nCol].eIndexColOrder = DBINDEX_COL_ORDER_ASC;  
        }  
    dbidxcoldesc[0].pColumnID->uName.pwszName = L"OrderID";  
    dbidxcoldesc[1].pColumnID->uName.pwszName = L"ProductID";  
  
    // Set properties for the index. The index is clustered,  
    // PRIMARY KEY.  
    for (nProp = 0; nProp < nProps; nProp++)  
        {  
        dbpropIndex[nProp].dwOptions = DBPROPOPTIONS_REQUIRED;  
        dbpropIndex[nProp].colid = DB_NULLID;  
  
        VariantInit(&(dbpropIndex[nProp].vValue));  
  
        dbpropIndex[nProp].vValue.vt = VT_BOOL;  
        }  
    dbpropIndex[0].dwPropertyID = DBPROP_INDEX_CLUSTERED;  
    dbpropIndex[0].vValue.boolVal = VARIANT_TRUE;  
  
    dbpropIndex[1].dwPropertyID = DBPROP_INDEX_PRIMARYKEY;  
    dbpropIndex[1].vValue.boolVal = VARIANT_TRUE;  
  
    dbpropset.rgProperties = dbpropIndex;  
    dbpropset.cProperties = nProps;  
    dbpropset.guidPropertySet = DBPROPSET_INDEX;  
  
    hr = pIIndexDefinition->CreateIndex(&dbidTable, &dbidIndex, nCols,  
        dbidxcoldesc, 1, &dbpropset, &pdbidIndexOut);  
  
    // Clean up dynamically allocated DBIDs.  
    for (nCol = 0; nCol < nCols; nCol++)  
        {  
        delete dbidxcoldesc[nCol].pColumnID;  
        }  
  
    return (hr);  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="0811e-199">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0811e-199">See Also</span></span>  
 [<span data-ttu-id="0811e-200">Tablas e índices</span><span class="sxs-lookup"><span data-stu-id="0811e-200">Tables and Indexes</span></span>](../../relational-databases/native-client-ole-db-tables-indexes/tables-and-indexes.md)  
  
  
