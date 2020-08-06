---
title: Trabajar con el seguimiento de cambios (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- change tracking [SQL Server], making changes
- change tracking [SQL Server], troubleshooting
- updating data [SQL Server]
- troubleshooting [SQL Server], change tracking
- data changes [SQL Server]
- tracking data changes [SQL Server]
- data [SQL Server], changing
- change tracking [SQL Server], data restore
- change tracking [SQL Server], ensuring consistent results
- change tracking [SQL Server], handling changes
ms.assetid: 5aec22ce-ae6f-4048-8a45-59ed05f04dc5
author: rothja
ms.author: jroth
ms.openlocfilehash: bdb8205a789894caf8c8e2d3c3f491751757bab6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676949"
---
# <a name="work-with-change-tracking-sql-server"></a><span data-ttu-id="324dc-102">Trabajar con el seguimiento de cambios (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="324dc-102">Work with Change Tracking (SQL Server)</span></span>
  <span data-ttu-id="324dc-103">Las aplicaciones que utilizan el seguimiento de cambios deben poder obtener los cambios que se han sometido a seguimiento, aplicarlos a otro almacén de datos y actualizar la base de datos de origen.</span><span class="sxs-lookup"><span data-stu-id="324dc-103">Applications that use change tracking must be able to obtain tracked changes, apply these changes to another data store, and update the source database.</span></span> <span data-ttu-id="324dc-104">En este tema se describe cómo realizar estas tareas y también el rol que desempeña el seguimiento de cambios cuando se produce una conmutación por error y una base de datos se debe restaurar a partir de una copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="324dc-104">This topic describes how to perform these tasks, and also the role change tracking plays when a failover occurs and a database must be restored from a backup.</span></span>  
  
##  <a name="obtain-changes-by-using-change-tracking-functions"></a><a name="Obtain"></a> <span data-ttu-id="324dc-105">Obtener cambios mediante las funciones de seguimiento de cambios</span><span class="sxs-lookup"><span data-stu-id="324dc-105">Obtain Changes by Using Change Tracking Functions</span></span>  
 <span data-ttu-id="324dc-106">Describe cómo utilizar las funciones de seguimiento de cambios para obtener las modificaciones y la información sobre los cambios que se realizaron en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="324dc-106">Describes how to use the change tracking functions to obtain changes and information about the changes that were made to a database.</span></span>  
  
### <a name="about-the-change-tracking-functions"></a><span data-ttu-id="324dc-107">Acerca de las funciones de seguimiento de cambios</span><span class="sxs-lookup"><span data-stu-id="324dc-107">About the Change Tracking Functions</span></span>  
 <span data-ttu-id="324dc-108">Las aplicaciones pueden utilizar las funciones siguientes para obtener los cambios que se realizan en una base de datos e información sobre ellos:</span><span class="sxs-lookup"><span data-stu-id="324dc-108">Applications can use the following functions to obtain the changes that are made in a database and information about the changes:</span></span>  
  
 <span data-ttu-id="324dc-109">Función CHANGETABLE(CHANGES ...)</span><span class="sxs-lookup"><span data-stu-id="324dc-109">CHANGETABLE(CHANGES ...) function</span></span>  
 <span data-ttu-id="324dc-110">Esta función de conjunto de filas se utiliza para consultar la información sobre los cambios.</span><span class="sxs-lookup"><span data-stu-id="324dc-110">This rowset function is used to query for change information.</span></span> <span data-ttu-id="324dc-111">La función consulta los datos almacenados en las tablas internas de seguimiento de cambios.</span><span class="sxs-lookup"><span data-stu-id="324dc-111">The function queries the data stored in the internal change tracking tables.</span></span> <span data-ttu-id="324dc-112">La función devuelve un conjunto de resultados que contiene las claves principales de las filas que han cambiado, junto con información adicional sobre los cambios, como la operación, las columnas actualizadas y la versión de la fila.</span><span class="sxs-lookup"><span data-stu-id="324dc-112">The function returns a results set that contains the primary keys of rows that have changed together with other change information such as the operation, columns updated and version for the row.</span></span>  
  
 <span data-ttu-id="324dc-113">CHANGETABLE(CHANGES ...) toma como argumento el número de la última versión de sincronización.</span><span class="sxs-lookup"><span data-stu-id="324dc-113">CHANGETABLE(CHANGES ...) takes a last synchronization version as an argument.</span></span> <span data-ttu-id="324dc-114">La última versión de sincronización se obtiene mediante la variable `@last_synchronization_version` .</span><span class="sxs-lookup"><span data-stu-id="324dc-114">The last sychronization version is obtained using the `@last_synchronization_version` variable.</span></span> <span data-ttu-id="324dc-115">La semántica de la última versión de sincronización es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="324dc-115">The semantics of the last synchronization version are as follows:</span></span>  
  
-   <span data-ttu-id="324dc-116">El cliente que realiza la llamada ha obtenido los cambios y sabe todos los que se han realizado hasta la última versión de sincronización, inclusive.</span><span class="sxs-lookup"><span data-stu-id="324dc-116">The calling client has obtained changes and knows about all changes up to and including the last synchronization version.</span></span>  
  
-   <span data-ttu-id="324dc-117">Por tanto, CHANGETABLE(CHANGES ...) devolverá todos los cambios que se han producido después de la última versión de sincronización.</span><span class="sxs-lookup"><span data-stu-id="324dc-117">CHANGETABLE(CHANGES ...) will therefore return all changes that have occurred after the last synchronization version.</span></span>  
  
     <span data-ttu-id="324dc-118">En la ilustración siguiente se muestra cómo se usa CHANGETABLE(CHANGES ...) para obtener los cambios.</span><span class="sxs-lookup"><span data-stu-id="324dc-118">The following illustration shows how CHANGETABLE(CHANGES ...) is used to obtain changes.</span></span>  
  
     <span data-ttu-id="324dc-119">![Ejemplo de resultado de una consulta de seguimiento de cambios](../../database-engine/media/queryoutput.gif "Ejemplo de resultado de una consulta de seguimiento de cambios")</span><span class="sxs-lookup"><span data-stu-id="324dc-119">![Example of change tracking query output](../../database-engine/media/queryoutput.gif "Example of change tracking query output")</span></span>  
  
 <span data-ttu-id="324dc-120">Función CHANGE_TRACKING_CURRENT_VERSION()</span><span class="sxs-lookup"><span data-stu-id="324dc-120">CHANGE_TRACKING_CURRENT_VERSION() function</span></span>  
 <span data-ttu-id="324dc-121">Se utiliza para obtener la versión actual que se utilizará la próxima vez que se consulten los cambios.</span><span class="sxs-lookup"><span data-stu-id="324dc-121">Is used to obtain the current version that will be used the next time when querying changes.</span></span> <span data-ttu-id="324dc-122">Esta versión representa la versión de la última transacción confirmada.</span><span class="sxs-lookup"><span data-stu-id="324dc-122">This version represents the version of the last committed transaction.</span></span>  
  
 <span data-ttu-id="324dc-123">Función CHANGE_TRACKING_MIN_VALID_VERSION()</span><span class="sxs-lookup"><span data-stu-id="324dc-123">CHANGE_TRACKING_MIN_VALID_VERSION()function</span></span>  
 <span data-ttu-id="324dc-124">Se utiliza para obtener el número de versión mínimo válido que un cliente puede tener y seguir obteniendo resultados válidos de CHANGETABLE().</span><span class="sxs-lookup"><span data-stu-id="324dc-124">Is used to obtain the minimum valid version that a client can have and still obtain valid results from CHANGETABLE().</span></span> <span data-ttu-id="324dc-125">El cliente debe comparar la última versión de sincronización con el valor devuelto por esta función.</span><span class="sxs-lookup"><span data-stu-id="324dc-125">The client should check the last synchronization version against the value thatis returned by this function.</span></span> <span data-ttu-id="324dc-126">Si el último número de versión de sincronización es menor que el de la versión devuelta por esta función, el cliente no podrá obtener resultados válidos de CHANGETABLE() y tendrá que reinicializar.</span><span class="sxs-lookup"><span data-stu-id="324dc-126">If the last synchronization version is less than the version returned by this function, the client will be unable to obtain valid results from CHANGETABLE() and will have to reinitialize.</span></span>  
  
### <a name="obtaining-initial-data"></a><span data-ttu-id="324dc-127">Obtener los datos iniciales</span><span class="sxs-lookup"><span data-stu-id="324dc-127">Obtaining Initial Data</span></span>  
 <span data-ttu-id="324dc-128">Para que una aplicación pueda obtener los cambios por primera vez, debe enviar una consulta que obtenga los datos iniciales y la versión de sincronización.</span><span class="sxs-lookup"><span data-stu-id="324dc-128">Before an application can obtain changes for the first time, the application must send a query to obtain the initial data and the synchronization version.</span></span> <span data-ttu-id="324dc-129">La aplicación debe obtener directamente los datos adecuados en la tabla y, a continuación, usar CHANGE_TRACKING_CURRENT_VERSION() para obtener la versión inicial.</span><span class="sxs-lookup"><span data-stu-id="324dc-129">The application must obtain the appropriate data directly from the table, and then use CHANGE_TRACKING_CURRENT_VERSION() to obtain the initial version.</span></span> <span data-ttu-id="324dc-130">Esta versión se pasará a CHANGETABLE(CHANGES ...) la primera vez que se obtengan los cambios.</span><span class="sxs-lookup"><span data-stu-id="324dc-130">This version will be passed to CHANGETABLE(CHANGES ...) the first time that changes are obtained.</span></span>  
  
 <span data-ttu-id="324dc-131">En el ejemplo siguiente se muestra cómo se obtienen los datos de la versión de sincronización inicial y el conjunto de datos inicial.</span><span class="sxs-lookup"><span data-stu-id="324dc-131">The following example shows how to obtain the initial synchronization version and the initial data set.</span></span>  
  
```sql  
    -- Obtain the current synchronization version. This will be used next time that changes are obtained.  
    SET @synchronization_version = CHANGE_TRACKING_CURRENT_VERSION();  
  
    -- Obtain initial data set.  
    SELECT  
        P.ProductID, P.Name, P.ListPrice  
    FROM  
        SalesLT.Product AS P  
```  
  
### <a name="using-the-change-tracking-functions-to-obtain-changes"></a><span data-ttu-id="324dc-132">Usar las funciones de seguimiento de cambios para obtener los cambios</span><span class="sxs-lookup"><span data-stu-id="324dc-132">Using the Change Tracking Functions to Obtain Changes</span></span>  
 <span data-ttu-id="324dc-133">Para obtener las filas cambiadas de una tabla e información sobre los cambios, use CHANGETABLE(CHANGES...). Por ejemplo, la consulta siguiente obtiene los cambios de la tabla `SalesLT.Product` .</span><span class="sxs-lookup"><span data-stu-id="324dc-133">To obtain the changed rows for a table and information about the changes, use CHANGETABLE(CHANGES...). For example, the following query obtains changes for the `SalesLT.Product` table.</span></span>  
  
```sql  
SELECT  
    CT.ProductID, CT.SYS_CHANGE_OPERATION,  
    CT.SYS_CHANGE_COLUMNS, CT.SYS_CHANGE_CONTEXT  
FROM  
    CHANGETABLE(CHANGES SalesLT.Product, @last_synchronization_version) AS CT  
  
```  
  
 <span data-ttu-id="324dc-134">Normalmente, un cliente deseará obtener los últimos datos de una fila y no solo las claves principales de la fila.</span><span class="sxs-lookup"><span data-stu-id="324dc-134">Usually, a client will want to obtain the latest data for a row instead of only the primary keys for the row.</span></span> <span data-ttu-id="324dc-135">Por tanto, una aplicación combinaría los resultados de CHANGETABLE(CHANGES ...) con los datos de la tabla de usuario.</span><span class="sxs-lookup"><span data-stu-id="324dc-135">Therefore, an application would join the results from CHANGETABLE(CHANGES ...) with the data in the user table.</span></span> <span data-ttu-id="324dc-136">Por ejemplo, la siguiente consulta se combina con la tabla `SalesLT.Product` para obtener los valores de las columnas `Name` y `ListPrice` .</span><span class="sxs-lookup"><span data-stu-id="324dc-136">For example, the following query joins with the `SalesLT.Product` table to obtain the values for the `Name` and `ListPrice` columns.</span></span> <span data-ttu-id="324dc-137">Observe el uso de la propiedad `OUTER JOIN`.</span><span class="sxs-lookup"><span data-stu-id="324dc-137">Note the use of `OUTER JOIN`.</span></span> <span data-ttu-id="324dc-138">Esto es necesario para asegurarse de que la información sobre los cambios se devuelve para las filas que han sido eliminadas de la tabla de usuario.</span><span class="sxs-lookup"><span data-stu-id="324dc-138">This is required to make sure that the change information is returned for those rows that have been deleted from the user table.</span></span>  
  
```sql  
SELECT  
    CT.ProductID, P.Name, P.ListPrice,  
    CT.SYS_CHANGE_OPERATION, CT.SYS_CHANGE_COLUMNS,  
    CT.SYS_CHANGE_CONTEXT  
FROM  
    SalesLT.Product AS P  
RIGHT OUTER JOIN  
    CHANGETABLE(CHANGES SalesLT.Product, @last_synchronization_version) AS CT  
ON  
    P.ProductID = CT.ProductID  
```  
  
 <span data-ttu-id="324dc-139">Para obtener la versión que se usará en la enumeración de cambios siguiente, utilice CHANGE_TRACKING_CURRENT_VERSION(), como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="324dc-139">To obtain the version for use in the next change enumeration, use CHANGE_TRACKING_CURRENT_VERSION(), as shown in the following example.</span></span>  
  
```sql  
SET @synchronization_version = CHANGE_TRACKING_CURRENT_VERSION()  
```  
  
 <span data-ttu-id="324dc-140">Cuando una aplicación obtiene los cambios, debe usar CHANGETABLE(CHANGES...) y CHANGE_TRACKING_CURRENT_VERSION(),como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="324dc-140">When an application obtains changes, it must use both CHANGETABLE(CHANGES...) and CHANGE_TRACKING_CURRENT_VERSION(), as shown in the following example.</span></span>  
  
```sql  
-- Obtain the current synchronization version. This will be used the next time CHANGETABLE(CHANGES...) is called.  
SET @synchronization_version = CHANGE_TRACKING_CURRENT_VERSION();  
  
-- Obtain incremental changes by using the synchronization version obtained the last time the data was synchronized.  
SELECT  
    CT.ProductID, P.Name, P.ListPrice,  
    CT.SYS_CHANGE_OPERATION, CT.SYS_CHANGE_COLUMNS,  
    CT.SYS_CHANGE_CONTEXT  
FROM  
    SalesLT.Product AS P  
RIGHT OUTER JOIN  
    CHANGETABLE(CHANGES SalesLT.Product, @last_synchronization_version) AS CT  
ON  
    P.ProductID = CT.ProductID  
```  
  
### <a name="version-numbers"></a><span data-ttu-id="324dc-141">Números de versión</span><span class="sxs-lookup"><span data-stu-id="324dc-141">Version Numbers</span></span>  
 <span data-ttu-id="324dc-142">Una base de datos con el seguimiento de cambios habilitado tiene un contador de versión que se incrementa cuando se realizan cambios en las tablas sometidas a seguimiento.</span><span class="sxs-lookup"><span data-stu-id="324dc-142">A database that has change tracking enabled has a version counter that increases as changes are made to change tracked tables.</span></span> <span data-ttu-id="324dc-143">Cada fila modificada tiene un número de versión asociado a ella.</span><span class="sxs-lookup"><span data-stu-id="324dc-143">Each changed row has a version number that is associated with it.</span></span> <span data-ttu-id="324dc-144">Cuando una solicitud se envía a una aplicación para consultar los cambios, se llama a una función que proporciona un número de versión.</span><span class="sxs-lookup"><span data-stu-id="324dc-144">When a request is sent to an application to query for changes, a function is called that supplies a version number.</span></span> <span data-ttu-id="324dc-145">La función devuelve información sobre todos los cambios realizados desde esa versión.</span><span class="sxs-lookup"><span data-stu-id="324dc-145">The function returns information about all the changes that have been made since that version.</span></span> <span data-ttu-id="324dc-146">En cierto modo, la versión del seguimiento de cambios es similar en su concepto al tipo de datos `rowversion`.</span><span class="sxs-lookup"><span data-stu-id="324dc-146">In some ways, change tracking version is similar in concept to the `rowversion` data type.</span></span>  
  
### <a name="validating-the-last-synchronized-version"></a><span data-ttu-id="324dc-147">Validar la última versión sincronizada</span><span class="sxs-lookup"><span data-stu-id="324dc-147">Validating the Last Synchronized Version</span></span>  
 <span data-ttu-id="324dc-148">La información sobre los cambios se mantiene durante un tiempo limitado.</span><span class="sxs-lookup"><span data-stu-id="324dc-148">Information about changes is maintained for a limited time.</span></span> <span data-ttu-id="324dc-149">El parámetro CHANGE_RETENTION, que se puede especificar como parte de la instrucción ALTER DATABASE, controla el intervalo de tiempo.</span><span class="sxs-lookup"><span data-stu-id="324dc-149">The length of time is controlled by the CHANGE_RETENTION parameter that can be specified as part of the ALTER DATABASE.</span></span>  
  
 <span data-ttu-id="324dc-150">Tenga en cuenta que el tiempo especificado para CHANGE_RETENTION determina la frecuencia con que todas las aplicaciones deben solicitar los cambios de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="324dc-150">Be aware that the time specified for CHANGE_RETENTION determines how frequently all applications must request changes from the database.</span></span> <span data-ttu-id="324dc-151">Si una aplicación tiene un valor para *last_synchronization_version* que es anterior a la versión de sincronización válida mínima para una tabla, esa aplicación no puede realizar una enumeración válida de los cambios.</span><span class="sxs-lookup"><span data-stu-id="324dc-151">If an application has a value for *last_synchronization_version* that is older than the minimum valid synchronization version for a table, that application cannot perform valid change enumeration.</span></span> <span data-ttu-id="324dc-152">Esto se debe a que podría haberse limpiado parte de la información de los cambios.</span><span class="sxs-lookup"><span data-stu-id="324dc-152">This is because some change information might have been cleaned up.</span></span> <span data-ttu-id="324dc-153">Antes de que una aplicación obtenga los cambios mediante CHANGETABLE(CHANGES ...), debe validar el valor de *last_synchronization_version* que planea pasar a CHANGETABLE(CHANGES ...). Si el valor de *last_synchronization_version* no es válido, esa aplicación debe reinicializar todos los datos.</span><span class="sxs-lookup"><span data-stu-id="324dc-153">Before an application obtains changes by using CHANGETABLE(CHANGES ...), the application must validate the value for *last_synchronization_version* that it plans to pass to CHANGETABLE(CHANGES ...). If the value of *last_synchronization_version* is not valid, that application must reinitialize all the data.</span></span>  
  
 <span data-ttu-id="324dc-154">En el ejemplo siguiente se muestra cómo comprobar la validez del valor de `last_synchronization_version` para cada tabla.</span><span class="sxs-lookup"><span data-stu-id="324dc-154">The following example shows how to verify the validity of the value of `last_synchronization_version` for each table.</span></span>  
  
```sql  
-- Check individual table.  
IF (@last_synchronization_version < CHANGE_TRACKING_MIN_VALID_VERSION(  
                                   OBJECT_ID('SalesLT.Product')))  
BEGIN  
  -- Handle invalid version and do not enumerate changes.  
  -- Client must be reinitialized.  
END  
```  
  
 <span data-ttu-id="324dc-155">Como se muestra en el ejemplo siguiente, la validez del valor de `last_synchronization_version` se puede comprobar con todas las tablas de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="324dc-155">As the following example shows, the validity of the value of `last_synchronization_version` can be checked against all tables in the database.</span></span>  
  
```sql  
-- Check all tables with change tracking enabled  
IF EXISTS (  
  SELECT COUNT(*) FROM sys.change_tracking_tables  
  WHERE min_valid_version > @last_synchronization_version )  
BEGIN  
  -- Handle invalid version & do not enumerate changes  
  -- Client must be reinitialized  
END  
```  
  
### <a name="using-column-tracking"></a><span data-ttu-id="324dc-156">Usar el seguimiento de columnas</span><span class="sxs-lookup"><span data-stu-id="324dc-156">Using Column Tracking</span></span>  
 <span data-ttu-id="324dc-157">El seguimiento de columnas permite a las aplicaciones obtener solo los datos de las columnas que han cambiado en lugar de la fila entera.</span><span class="sxs-lookup"><span data-stu-id="324dc-157">Column tracking enables applications to obtain the data for only the columns that have changed instead of the whole row.</span></span> <span data-ttu-id="324dc-158">Por ejemplo, considere el escenario en el que una tabla tiene una o varias columnas que son grandes, pero que raramente cambian. Además, hay otras columnas que cambian con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="324dc-158">For example, consider the scenario in which a table has one or more columns that are large, but rarely change; and also has other columns that frequently change.</span></span> <span data-ttu-id="324dc-159">Sin el seguimiento de columnas, una aplicación solo puede determinar que una fila ha cambiado y tendría que sincronizar todos los datos, incluidos los de las columnas grandes.</span><span class="sxs-lookup"><span data-stu-id="324dc-159">Without column tracking, an application can only determine that a row has changed and would have to synchronize all the data that includes the large column data.</span></span> <span data-ttu-id="324dc-160">Sin embargo, mediante el seguimiento de columnas, una aplicación puede determinar si los datos de las columnas grandes cambiaron y solo puede sincronizar los cambios en caso afirmativo.</span><span class="sxs-lookup"><span data-stu-id="324dc-160">However, by using column tracking, an application can determine whether the large column data changed and only synchronize the data if it has changed.</span></span>  
  
 <span data-ttu-id="324dc-161">La información de seguimiento de columnas aparece en la columna SYS_CHANGE_COLUMNS devuelta por la función CHANGETABLE(CHANGES ...).</span><span class="sxs-lookup"><span data-stu-id="324dc-161">Column tracking information appears in the SYS_CHANGE_COLUMNS column that is returned by the CHANGETABLE(CHANGES ...) function.</span></span>  
  
 <span data-ttu-id="324dc-162">Se puede usar el seguimiento de columnas para que se devuelva NULL cuando una columna no haya cambiado.</span><span class="sxs-lookup"><span data-stu-id="324dc-162">Column tracking can be used so that NULL is returned for a column that has not changed.</span></span> <span data-ttu-id="324dc-163">Si la columna se puede cambiar a NULL, se debe devolver una columna independiente para indicar si la columna cambió.</span><span class="sxs-lookup"><span data-stu-id="324dc-163">If the column can be changed to NULL, a separate column must be returned to indicate whether the column changed.</span></span>  
  
 <span data-ttu-id="324dc-164">En el ejemplo siguiente, la columna `CT_ThumbnailPhoto` será `NULL` si esa columna no cambió.</span><span class="sxs-lookup"><span data-stu-id="324dc-164">In the following example, the `CT_ThumbnailPhoto` column will be `NULL` if that column did not change.</span></span> <span data-ttu-id="324dc-165">Esta columna también podría ser `NULL` si cambió a `NULL` ; la aplicación puede usar la columna `CT_ThumbNailPhoto_Changed` para determinar si la columna cambió.</span><span class="sxs-lookup"><span data-stu-id="324dc-165">This column could also be `NULL` because it was changed to `NULL` - the application can use the `CT_ThumbNailPhoto_Changed` column to determine whether the column changed.</span></span>  
  
```sql  
DECLARE @PhotoColumnId int = COLUMNPROPERTY(  
    OBJECT_ID('SalesLT.Product'),'ThumbNailPhoto', 'ColumnId')  
  
SELECT  
    CT.ProductID, P.Name, P.ListPrice, -- Always obtain values.  
    CASE  
           WHEN CHANGE_TRACKING_IS_COLUMN_IN_MASK(  
                     @PhotoColumnId, CT.SYS_CHANGE_COLUMNS) = 1  
            THEN ThumbNailPhoto  
            ELSE NULL  
      END AS CT_ThumbNailPhoto,  
      CHANGE_TRACKING_IS_COLUMN_IN_MASK(  
                     @PhotoColumnId, CT.SYS_CHANGE_COLUMNS) AS  
                                   CT_ThumbNailPhoto_Changed  
     CT.SYS_CHANGE_OPERATION, CT.SYS_CHANGE_COLUMNS,  
     CT.SYS_CHANGE_CONTEXT  
FROM  
     SalesLT.Product AS P  
INNER JOIN  
     CHANGETABLE(CHANGES SalesLT.Product, @last_synchronization_version) AS CT  
ON  
     P.ProductID = CT.ProductID AND  
     CT.SYS_CHANGE_OPERATION = 'U'  
```  
  
### <a name="obtaining-consistent-and-correct-results"></a><span data-ttu-id="324dc-166">Obtener resultados coherentes y correctos</span><span class="sxs-lookup"><span data-stu-id="324dc-166">Obtaining Consistent and Correct Results</span></span>  
 <span data-ttu-id="324dc-167">Para obtener los datos que han cambiado de una tabla, se requieren varios pasos.</span><span class="sxs-lookup"><span data-stu-id="324dc-167">Obtaining the changed data for a table requires multiple steps.</span></span> <span data-ttu-id="324dc-168">Tenga en cuenta que se pueden devolver resultados incoherentes o incorrectos si no se consideran y se tratan ciertos problemas.</span><span class="sxs-lookup"><span data-stu-id="324dc-168">Be aware that inconsistent or incorrect results could be returned if certain issues are not considered and handled.</span></span>  
  
 <span data-ttu-id="324dc-169">Por ejemplo, para obtener los cambios que se realizaron en las tablas Sales y SalesOrders, una aplicación realizaría los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="324dc-169">For example, to obtain the changes that were made to a Sales table and SalesOrders table, an application would perform the following steps:</span></span>  
  
1.  <span data-ttu-id="324dc-170">Validar la última versión sincronizada con CHANGE_TRACKING_MIN_VALID_VERSION().</span><span class="sxs-lookup"><span data-stu-id="324dc-170">Validate the last synchronized version by using CHANGE_TRACKING_MIN_VALID_VERSION().</span></span>  
  
2.  <span data-ttu-id="324dc-171">Obtener la versión que puede utilizarse la próxima vez para obtener los cambios mediante CHANGE_TRACKING_CURRENT_VERSION().</span><span class="sxs-lookup"><span data-stu-id="324dc-171">Obtain the version that can be used to obtain change the next time by using CHANGE_TRACKING_CURRENT_VERSION().</span></span>  
  
3.  <span data-ttu-id="324dc-172">Obtenga los cambios de la tabla Sales mediante CHANGETABLE(CHANGES ...).</span><span class="sxs-lookup"><span data-stu-id="324dc-172">Obtain the changes for the Sales table by using CHANGETABLE(CHANGES ...).</span></span>  
  
4.  <span data-ttu-id="324dc-173">Obtenga los cambios de la tabla SalesOrders mediante CHANGETABLE(CHANGES ...).</span><span class="sxs-lookup"><span data-stu-id="324dc-173">Obtain the changes for the SalesOrders table by using CHANGETABLE(CHANGES ...).</span></span>  
  
 <span data-ttu-id="324dc-174">Se están produciendo dos procesos en la base de datos que pueden afectar a los resultados que devuelven los pasos anteriores:</span><span class="sxs-lookup"><span data-stu-id="324dc-174">Two processes are occurring in the database that can affect the results that are returned by the previous steps:</span></span>  
  
-   <span data-ttu-id="324dc-175">El proceso de limpieza se ejecuta en segundo plano y quita la información de seguimiento de cambios cuya antigüedad supere el período de retención especificado.</span><span class="sxs-lookup"><span data-stu-id="324dc-175">The cleanup process runs in the background and removes change tracking information that is older than the specified retention period.</span></span>  
  
     <span data-ttu-id="324dc-176">El proceso de limpieza es un proceso en segundo plano independiente que usa el período de retención que se especifica al configurar el seguimiento de cambios para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="324dc-176">The cleanup process is a separate background process that uses the retention period that is specified when you configure change tracking for the database.</span></span> <span data-ttu-id="324dc-177">El problema es que el proceso de limpieza se puede producir en el período que transcurre entre el momento en que se validó la última versión de sincronización y el momento en que se realiza la llamada a CHANGETABLE(CHANGES...).</span><span class="sxs-lookup"><span data-stu-id="324dc-177">The issue is that the cleanup process can occur in the time between when the last synchronization version was validated and when the call to CHANGETABLE(CHANGES...) is made.</span></span> <span data-ttu-id="324dc-178">Una última versión de sincronización que era válida en ese momento podría no serlo cuando se obtienen los cambios.</span><span class="sxs-lookup"><span data-stu-id="324dc-178">A last synchronization version that was just valid might no longer be valid by the time the changes are obtained.</span></span> <span data-ttu-id="324dc-179">Por consiguiente, se podrían devolver resultados incorrectos.</span><span class="sxs-lookup"><span data-stu-id="324dc-179">Therefore, incorrect results might be returned.</span></span>  
  
-   <span data-ttu-id="324dc-180">Se están produciendo operaciones DML continuas en las tablas Sales y SalesOrders, como las siguientes:</span><span class="sxs-lookup"><span data-stu-id="324dc-180">Ongoing DML operations are occurring in the Sales and SalesOrders tables, such as the following operations:</span></span>  
  
    -   <span data-ttu-id="324dc-181">Se pueden realizar cambios en las tablas después de obtenerse la siguiente versión utilizando CHANGE_TRACKING_CURRENT_VERSION().</span><span class="sxs-lookup"><span data-stu-id="324dc-181">Changes can be made to the tables after the version for next time has been obtained by using CHANGE_TRACKING_CURRENT_VERSION().</span></span> <span data-ttu-id="324dc-182">Por lo tanto, se pueden devolver más cambios que los esperados.</span><span class="sxs-lookup"><span data-stu-id="324dc-182">Therefore, more changes can be returned than expected.</span></span>  
  
    -   <span data-ttu-id="324dc-183">Una transacción podría confirmarse en el período que transcurre entre la llamada para obtener los cambios de la tabla Sales y la llamada para obtener los cambios de la tabla SalesOrders.</span><span class="sxs-lookup"><span data-stu-id="324dc-183">A transaction could commit in the time between the call to obtain changes from the Sales table and the call to obtain changes from the SalesOrders table.</span></span> <span data-ttu-id="324dc-184">Por consiguiente, los resultados de la tabla SalesOrders podrían tener un valor de clave externa que no existe en la tabla Sales.</span><span class="sxs-lookup"><span data-stu-id="324dc-184">Therefore, the results for the SalesOrder table could have foreign key value that does not exist in the Sales table.</span></span>  
  
 <span data-ttu-id="324dc-185">Para superar los desafíos enumerados anteriormente, se recomienda utilizar el aislamiento de instantánea.</span><span class="sxs-lookup"><span data-stu-id="324dc-185">To overcome the previously listed challenges, we recommend that you use snapshot isolation.</span></span> <span data-ttu-id="324dc-186">Esto ayudará a garantizar la coherencia de la información de los cambios y a evitar las condiciones de anticipación relacionadas con la tarea de limpieza en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="324dc-186">This will help to ensure consistency of change information and avoid race conditions that are related to the background cleanup task.</span></span> <span data-ttu-id="324dc-187">Si no utiliza transacciones de instantáneas, el desarrollo de una aplicación que use el seguimiento de cambios puede requerir mucho más esfuerzo.</span><span class="sxs-lookup"><span data-stu-id="324dc-187">If you do not use snapshot transactions, developing an application that uses change tracking could require significantly more effort.</span></span>  
  
#### <a name="using-snapshot-isolation"></a><span data-ttu-id="324dc-188">Usar el aislamiento de instantánea</span><span class="sxs-lookup"><span data-stu-id="324dc-188">Using Snapshot Isolation</span></span>  
 <span data-ttu-id="324dc-189">El seguimiento de cambios se ha diseñado para que funcione bien con el aislamiento de instantánea.</span><span class="sxs-lookup"><span data-stu-id="324dc-189">Change tracking has been designed to work well with snapshot isolation.</span></span> <span data-ttu-id="324dc-190">El aislamiento de instantánea se debe habilitar para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="324dc-190">Snapshot isolation must be enabled for the database.</span></span> <span data-ttu-id="324dc-191">Todos los pasos necesarios para obtener los cambios deben estar incluidos dentro de una transacción de instantánea.</span><span class="sxs-lookup"><span data-stu-id="324dc-191">All the steps that are required to obtain changes must be included inside a snapshot transaction.</span></span> <span data-ttu-id="324dc-192">De este modo se garantizará que todos los cambios que se realicen en los datos mientras se obtienen los cambios no serán visibles para las consultas dentro de la transacción de instantánea.</span><span class="sxs-lookup"><span data-stu-id="324dc-192">This will ensure that all changes that are made to data while obtaining changes will not be visible to the queries inside the snapshot transaction.</span></span>  
  
 <span data-ttu-id="324dc-193">Para obtener los datos dentro de una transacción de instantánea, realice los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="324dc-193">To obtain data inside a snapshot transaction, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="324dc-194">Establezca el nivel de aislamiento de transacción en la instantánea e inicie una transacción.</span><span class="sxs-lookup"><span data-stu-id="324dc-194">Set the transaction isolation level to snapshot and start a transaction.</span></span>  
  
2.  <span data-ttu-id="324dc-195">Valide la última versión de sincronización con CHANGE_TRACKING_MIN_VALID_VERSION().</span><span class="sxs-lookup"><span data-stu-id="324dc-195">Validate the last synchronization version by using CHANGE_TRACKING_MIN_VALID_VERSION().</span></span>  
  
3.  <span data-ttu-id="324dc-196">Obtenga la siguiente versión que se va a usar utilizando CHANGE_TRACKING_CURRENT_VERSION().</span><span class="sxs-lookup"><span data-stu-id="324dc-196">Obtain the version to be used the next time by using CHANGE_TRACKING_CURRENT_VERSION().</span></span>  
  
4.  <span data-ttu-id="324dc-197">Obtenga los cambios de la tabla Sales con CHANGETABLE(CHANGES ...)</span><span class="sxs-lookup"><span data-stu-id="324dc-197">Obtain the changes for the Sales table by using CHANGETABLE(CHANGES ...)</span></span>  
  
5.  <span data-ttu-id="324dc-198">Obtenga los cambios de la tabla Salesorders con CHANGETABLE(CHANGES ...)</span><span class="sxs-lookup"><span data-stu-id="324dc-198">Obtain the changes for the Salesorders table by using CHANGETABLE(CHANGES ...)</span></span>  
  
6.  <span data-ttu-id="324dc-199">Confirme la transacción.</span><span class="sxs-lookup"><span data-stu-id="324dc-199">Commit the transaction.</span></span>  
  
 <span data-ttu-id="324dc-200">Algunas cuestiones que hay que recordar ya que todos los pasos para obtener los cambios están dentro de una transacción de instantáneas son:</span><span class="sxs-lookup"><span data-stu-id="324dc-200">Some points to remember as all steps to obtain changes are inside a snapshot transaction:</span></span>  
  
-   <span data-ttu-id="324dc-201">Si la limpieza se produce una vez validada la última versión de sincronización, los resultados de CHANGETABLE(CHANGES ...) seguirán siendo válidos ya que las operaciones de eliminación realizadas en el proceso de limpieza no serán visibles dentro de la transacción.</span><span class="sxs-lookup"><span data-stu-id="324dc-201">If cleanup occurs after the last synchronization version is validated, the results from CHANGETABLE(CHANGES ...) will still be valid as the delete operations performed by cleanup will not be visible inside the transaction.</span></span>  
  
-   <span data-ttu-id="324dc-202">Cualquier cambio que se realice en las tablas Sales o SalesOrders una vez obtenida la versión de sincronización siguiente no será visible y las llamadas a CHANGETABLE(CHANGES ...) nunca devolverán cambios con una versión posterior a la devuelta por CHANGE_TRACKING_CURRENT_VERSION().</span><span class="sxs-lookup"><span data-stu-id="324dc-202">Any changes that are made to the Sales table or the SalesOrders table after the next synchronization version is obtained will not be visible, and the calls to CHANGETABLE(CHANGES ...) will never return changes with a version later than that returned by CHANGE_TRACKING_CURRENT_VERSION().</span></span> <span data-ttu-id="324dc-203">La coherencia entre las tablas Sales y SalesOrders también se mantendrá, porque las transacciones que se confirmaron entre las llamadas a CHANGETABLE(CHANGES ...) no serán visibles.</span><span class="sxs-lookup"><span data-stu-id="324dc-203">Consistency between the Sales table and the SalesOrders table will also be maintained, because the transactions that were committed in the time between calls to CHANGETABLE(CHANGES ...) will not be visible.</span></span>  
  
 <span data-ttu-id="324dc-204">En el ejemplo siguiente se muestra cómo se habilita el aislamiento de instantánea para una base de datos.</span><span class="sxs-lookup"><span data-stu-id="324dc-204">The following example shows how snapshot isolation is enabled for a database.</span></span>  
  
```sql  
-- The database must be configured to enable snapshot isolation.  
ALTER DATABASE AdventureWorksLT  
    SET ALLOW_SNAPSHOT_ISOLATION ON;  
```  
  
 <span data-ttu-id="324dc-205">Una transacción de instantánea se utiliza como sigue:</span><span class="sxs-lookup"><span data-stu-id="324dc-205">A snapshot transaction is used as follows:</span></span>  
  
```sql  
SET TRANSACTION ISOLATION LEVEL SNAPSHOT;  
BEGIN TRAN  
  -- Verify that version of the previous synchronization is valid.  
  -- Obtain the version to use next time.  
  -- Obtain changes.  
COMMIT TRAN  
```  
  
 <span data-ttu-id="324dc-206">Para obtener más información sobre las transacciones de instantáneas, vea [SET TRANSACTION ISOLATION LEVEL &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="324dc-206">For more information about snapshot transactions, see [SET TRANSACTION ISOLATION LEVEL &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql).</span></span>  
  
#### <a name="alternatives-to-using-snapshot-isolation"></a><span data-ttu-id="324dc-207">Alternativas al uso del aislamiento de instantánea</span><span class="sxs-lookup"><span data-stu-id="324dc-207">Alternatives to Using Snapshot Isolation</span></span>  
 <span data-ttu-id="324dc-208">Hay alternativas al uso del aislamiento de instantánea, pero exigen más trabajo para garantizar que se cumplan todos los requisitos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="324dc-208">There are alternatives to using snapshot isolation, but they require more work to make sure all application requirements are met.</span></span> <span data-ttu-id="324dc-209">Para garantizar que el valor de *last_synchronization_version* sea válido y que el proceso de limpieza no quite los datos antes de que se obtengan los cambios, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="324dc-209">To make sure the *last_synchronization_version* is valid and data is not removed by the cleanup process before changes are obtained, do the following:</span></span>  
  
1.  <span data-ttu-id="324dc-210">Compruebe *last_synchronization_version* después de las llamadas a CHANGETABLE().</span><span class="sxs-lookup"><span data-stu-id="324dc-210">Check *last_synchronization_version* after the calls to CHANGETABLE().</span></span>  
  
2.  <span data-ttu-id="324dc-211">Compruebe *last_synchronization_version* como parte de cada consulta para obtener los cambios con CHANGETABLE().</span><span class="sxs-lookup"><span data-stu-id="324dc-211">Check *last_synchronization_version* as part of each query to obtain changes by using CHANGETABLE().</span></span>  
  
 <span data-ttu-id="324dc-212">Los cambios se pueden producir después de haberse obtenido la versión de sincronización de la enumeración siguiente.</span><span class="sxs-lookup"><span data-stu-id="324dc-212">Changes can occur after the synchronization version for the next enumeration has been obtained.</span></span> <span data-ttu-id="324dc-213">Hay dos formas de controlar esta situación.</span><span class="sxs-lookup"><span data-stu-id="324dc-213">There are two ways to handle this situation.</span></span> <span data-ttu-id="324dc-214">La opción utilizada depende de la aplicación y de cómo puede administrar los efectos secundarios de cada enfoque:</span><span class="sxs-lookup"><span data-stu-id="324dc-214">The option that is used depends on the application and how it can handle the side-effects of each approach:</span></span>  
  
-   <span data-ttu-id="324dc-215">Omita los cambios que tengan una versión mayor que la nueva versión de sincronización.</span><span class="sxs-lookup"><span data-stu-id="324dc-215">Ignore changes that have a version larger than the new synchronization version.</span></span>  
  
     <span data-ttu-id="324dc-216">Este enfoque tiene el efecto secundario de que una fila nueva o actualizada se omitiría si se creó o se actualizó antes de la nueva versión de sincronización, aunque se actualizase posteriormente.</span><span class="sxs-lookup"><span data-stu-id="324dc-216">This approach has the side effect that a new or updated row would be skipped if it was created or updated before the new synchronization version, but then updated afterward.</span></span> <span data-ttu-id="324dc-217">Si hay una fila nueva, se podría producir un problema de integridad referencial si hubiera una fila de otra tabla creada que hiciera referencia a la fila omitida.</span><span class="sxs-lookup"><span data-stu-id="324dc-217">If there is a new row, a referential integrity problem might occur if there was a row in another table that was created that referenced the skipped row.</span></span> <span data-ttu-id="324dc-218">Si hay una fila existente actualizada, se omitirá y no se sincronizará hasta la próxima vez.</span><span class="sxs-lookup"><span data-stu-id="324dc-218">If there is an updated existing row, the row will be skipped and not synchronized until the next time.</span></span>  
  
-   <span data-ttu-id="324dc-219">Incluya todos los cambios, incluso los que tengan una versión mayor que la nueva versión de sincronización.</span><span class="sxs-lookup"><span data-stu-id="324dc-219">Include all changes, even those that have a version larger than the new synchronization version.</span></span>  
  
     <span data-ttu-id="324dc-220">Las filas que tengan una versión mayor que la nueva versión de sincronización volverán a obtenerse en la sincronización siguiente.</span><span class="sxs-lookup"><span data-stu-id="324dc-220">The rows that have a version larger than the new synchronization version will be obtained again on the next synchronization.</span></span> <span data-ttu-id="324dc-221">La aplicación debe prever y controlar este punto.</span><span class="sxs-lookup"><span data-stu-id="324dc-221">This must be expected and handled by the application.</span></span>  
  
 <span data-ttu-id="324dc-222">Además de las dos opciones anteriores, puede idear un enfoque que combine ambas opciones, dependiendo de la operación.</span><span class="sxs-lookup"><span data-stu-id="324dc-222">In addition to the previous two options, you can devise approach that combines both options, depending on the operation.</span></span> <span data-ttu-id="324dc-223">Por ejemplo, puede querer crear una aplicación para la que sea mejor omitir los cambios más recientes que la versión de sincronización siguiente en la que se creó o se eliminó la fila, pero en la que no se omitan las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="324dc-223">For example, you might want an application for which it is best to ignore changes newer than the next synchronization version in which the row was created or deleted, but updates are not ignored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="324dc-224">La elección del enfoque que va a funcionar para la aplicación cuando se usa el seguimiento de cambios (o cualquier mecanismo de seguimiento personalizado), requiere un análisis significativo.</span><span class="sxs-lookup"><span data-stu-id="324dc-224">Choosing the approach that will work for the application when you are using change tracking (or any custom tracking mechanism), requires significant analysis.</span></span> <span data-ttu-id="324dc-225">Por consiguiente, es mucho más fácil utilizar el aislamiento de instantánea.</span><span class="sxs-lookup"><span data-stu-id="324dc-225">Therefore, it is much simpler to use snapshot isolation.</span></span>  
  
##  <a name="how-change-tracking-handles-changes-to-a-database"></a><a name="Handles"></a><span data-ttu-id="324dc-226">Cómo Change Tracking controla los cambios en una base de datos</span><span class="sxs-lookup"><span data-stu-id="324dc-226">How Change Tracking Handles Changes to a Database</span></span>  
 <span data-ttu-id="324dc-227">Algunas aplicaciones que utilizan el seguimiento de cambios realizan una sincronización bidireccional con otro almacén de datos.</span><span class="sxs-lookup"><span data-stu-id="324dc-227">Some applications that use change tracking perform two-way synchronization with another data store.</span></span> <span data-ttu-id="324dc-228">Es decir, los cambios que se realizan en la base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se actualizan en el otro almacén de datos y los que se realizan en este se actualizan en la base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="324dc-228">That is, changes that are made in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database are updated in the other data store, and changes that are made in the other store are updated in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="324dc-229">Cuando una aplicación actualiza la base de datos local con los cambios de otro almacén de datos, debe realizar las operaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="324dc-229">When an application updates the local database with changes from another data store, the application must perform the following operations:</span></span>  
  
-   <span data-ttu-id="324dc-230">Comprobar si hay conflictos.</span><span class="sxs-lookup"><span data-stu-id="324dc-230">Check for conflicts.</span></span>  
  
     <span data-ttu-id="324dc-231">Un conflicto se produce cuando los mismos datos se cambian en ambos almacenes de datos al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="324dc-231">A conflict occurs when the same data is changed at the same time in both data stores.</span></span> <span data-ttu-id="324dc-232">La aplicación debe poder comprobar si hay un conflicto y obtener suficiente información para permitir que se resuelva.</span><span class="sxs-lookup"><span data-stu-id="324dc-232">The application must be able to check for a conflict and obtain enough information to enable the conflict to be resolved.</span></span>  
  
-   <span data-ttu-id="324dc-233">Almacenar información de contexto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="324dc-233">Store application context information.</span></span>  
  
     <span data-ttu-id="324dc-234">La aplicación almacena los datos que tienen la información de seguimiento de cambios.</span><span class="sxs-lookup"><span data-stu-id="324dc-234">The application stores data that has the change tracking information.</span></span> <span data-ttu-id="324dc-235">Esta información estaría disponible junto con otra referente al seguimiento de cambios cuando los cambios se obtuvieran de la base de datos local.</span><span class="sxs-lookup"><span data-stu-id="324dc-235">This information would be available together with other change tracking information when changes were obtained from the local database.</span></span> <span data-ttu-id="324dc-236">Un ejemplo común de esta información contextual es un identificador del almacén de datos que fue el origen del cambio.</span><span class="sxs-lookup"><span data-stu-id="324dc-236">A common example of this contextual information is an identifier for the data store that was the source of the change.</span></span>  
  
 <span data-ttu-id="324dc-237">Para realizar las operaciones anteriores, una aplicación de sincronización puede utilizar las funciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="324dc-237">To perform the previous operations, a synchronization application can use the following functions:</span></span>  
  
-   <span data-ttu-id="324dc-238">CHANGETABLE(VERSION...)</span><span class="sxs-lookup"><span data-stu-id="324dc-238">CHANGETABLE(VERSION...)</span></span>  
  
     <span data-ttu-id="324dc-239">Cuando una aplicación está realizando cambios, puede utilizar esta función para comprobar si hay conflictos.</span><span class="sxs-lookup"><span data-stu-id="324dc-239">When an application is making changes, it can use this function to check for conflicts.</span></span> <span data-ttu-id="324dc-240">La función obtiene la información de seguimiento de cambios más reciente para una fila especificada de la tabla de cambios sometida a seguimiento.</span><span class="sxs-lookup"><span data-stu-id="324dc-240">The function obtains the latest change tracking information for a specified row in a change tracked table.</span></span> <span data-ttu-id="324dc-241">La información de seguimiento de cambios incluye el número de versión correspondiente a la fila que se cambió en último lugar.</span><span class="sxs-lookup"><span data-stu-id="324dc-241">The change tracking information includes the version of the row that was last changed.</span></span> <span data-ttu-id="324dc-242">Esta información permite que una aplicación determine si la fila se cambió después de que la aplicación se sincronizara por última vez.</span><span class="sxs-lookup"><span data-stu-id="324dc-242">This information enables an application to determine whether the row was changed after the last time that the application was synchronized.</span></span>  
  
-   <span data-ttu-id="324dc-243">WITH CHANGE_TRACKING_CONTEXT</span><span class="sxs-lookup"><span data-stu-id="324dc-243">WITH CHANGE_TRACKING_CONTEXT</span></span>  
  
     <span data-ttu-id="324dc-244">Una aplicación puede utilizar esta cláusula para almacenar los datos de contexto.</span><span class="sxs-lookup"><span data-stu-id="324dc-244">An application can use this clause to store context data.</span></span>  
  
### <a name="checking-for-conflicts"></a><span data-ttu-id="324dc-245">Comprobar si hay conflictos</span><span class="sxs-lookup"><span data-stu-id="324dc-245">Checking for Conflicts</span></span>  
 <span data-ttu-id="324dc-246">En un escenario de sincronización bidireccional, la aplicación cliente debe determinar si una fila no ha sido actualizada desde que la aplicación obtuvo los cambios por última vez.</span><span class="sxs-lookup"><span data-stu-id="324dc-246">In a two-way synchronization scenario, the client application must determine whether a row has not been updated since the application last obtained the changes.</span></span>  
  
 <span data-ttu-id="324dc-247">En el ejemplo siguiente se muestra cómo usar la función CHANGETABLE(VERSION ...) para comprobar si hay conflictos de la manera más eficaz, sin una consulta independiente.</span><span class="sxs-lookup"><span data-stu-id="324dc-247">The following example shows how to use the CHANGETABLE(VERSION ...) function to check for conflicts in the most efficient way, without a separate query.</span></span> <span data-ttu-id="324dc-248">En el ejemplo, `CHANGETABLE(VERSION ...)` determina `SYS_CHANGE_VERSION` para la fila especificada por `@product id`.</span><span class="sxs-lookup"><span data-stu-id="324dc-248">In the example, `CHANGETABLE(VERSION ...)` determines the `SYS_CHANGE_VERSION` for the row specified by `@product id`.</span></span> <span data-ttu-id="324dc-249">`CHANGETABLE(CHANGES ...)` puede obtener la misma información, pero ese procedimiento sería menos eficiente.</span><span class="sxs-lookup"><span data-stu-id="324dc-249">`CHANGETABLE(CHANGES ...)` can obtain the same information, but that would be less efficient.</span></span> <span data-ttu-id="324dc-250">Si el valor de `SYS_CHANGE_VERSION` para la fila es mayor que el valor de `@last_sync_version`, hay un conflicto.</span><span class="sxs-lookup"><span data-stu-id="324dc-250">If the value of `SYS_CHANGE_VERSION` for the row is larger than the value of `@last_sync_version`, there is a conflict.</span></span> <span data-ttu-id="324dc-251">Si hay un conflicto, la fila no se actualizará.</span><span class="sxs-lookup"><span data-stu-id="324dc-251">If there is a conflict, the row will not be updated.</span></span> <span data-ttu-id="324dc-252">La comprobación `ISNULL()` se requiere porque podría no haber ninguna información de cambios disponible para la fila.</span><span class="sxs-lookup"><span data-stu-id="324dc-252">The `ISNULL()` check is required because there might be no change information available for the row.</span></span> <span data-ttu-id="324dc-253">No existiría ninguna información de cambios si la fila no se hubiera actualizado desde que se habilitó el seguimiento de cambios o desde que se limpió la información de los cambios.</span><span class="sxs-lookup"><span data-stu-id="324dc-253">No change information would exist if the row had not been updated since change tracking was enabled or since the change information was cleaned up.</span></span>  
  
```sql  
-- Assumption: @last_sync_version has been validated.  
  
UPDATE  
    SalesLT.Product  
SET  
    ListPrice = @new_listprice  
FROM  
    SalesLT.Product AS P  
WHERE  
    ProductID = @product_id AND  
    @last_sync_version >= ISNULL (  
        SELECT CT.SYS_CHANGE_VERSION  
        FROM CHANGETABLE(VERSION SalesLT.Product,  
                        (ProductID), (P.ProductID)) AS CT),  
        0)  
```  
  
 <span data-ttu-id="324dc-254">El código siguiente puede comprobar el recuento de filas actualizadas e identificar más información sobre el conflicto.</span><span class="sxs-lookup"><span data-stu-id="324dc-254">The following code can check the updated row count and can identify more information about the conflict.</span></span>  
  
```sql  
-- If the change cannot be made, find out more information.  
IF (@@ROWCOUNT = 0)  
BEGIN  
    -- Obtain the complete change information for the row.  
    SELECT  
        CT.SYS_CHANGE_VERSION, CT.SYS_CHANGE_CREATION_VERSION,  
        CT.SYS_CHANGE_OPERATION, CT.SYS_CHANGE_COLUMNS  
    FROM  
        CHANGETABLE(CHANGES SalesLT.Product, @last_sync_version) AS CT  
    WHERE  
        CT.ProductID = @product_id;  
  
    -- Check CT.SYS_CHANGE_VERSION to verify that it really was a conflict.  
    -- Check CT.SYS_CHANGE_OPERATION to determine the type of conflict:  
    -- update-update or update-delete.  
    -- The row that is specified by @product_id might no longer exist   
    -- if it has been deleted.  
END  
```  
  
### <a name="setting-context-information"></a><span data-ttu-id="324dc-255">Establecer información de contexto</span><span class="sxs-lookup"><span data-stu-id="324dc-255">Setting Context Information</span></span>  
 <span data-ttu-id="324dc-256">Mediante la cláusula WITH CHANGE_TRACKING_CONTEXT, una aplicación puede almacenar la información de contexto junto con la información de cambios.</span><span class="sxs-lookup"><span data-stu-id="324dc-256">By using the WITH CHANGE_TRACKING_CONTEXT clause, an application can store context information together with the change information.</span></span> <span data-ttu-id="324dc-257">Después, esta información se puede obtener de la columna SYS_CHANGE_CONTEXT que CHANGETABLE(CHANGES ...) devuelve.</span><span class="sxs-lookup"><span data-stu-id="324dc-257">This information can then be obtained from the SYS_CHANGE_CONTEXT column that is returned by CHANGETABLE(CHANGES ...).</span></span>  
  
 <span data-ttu-id="324dc-258">La información de contexto se suele utilizar para identificar el origen de los cambios.</span><span class="sxs-lookup"><span data-stu-id="324dc-258">Context information is typically used to identify the source of the changes.</span></span> <span data-ttu-id="324dc-259">Si el origen del cambio se puede identificar, un almacén de datos puede utilizar esa información para evitar obtener los cambios cuando se sincronice de nuevo.</span><span class="sxs-lookup"><span data-stu-id="324dc-259">If the source of the change can be identified, that information can be used by a data store to avoid obtaining changes when it synchronizes again.</span></span>  
  
```sql  
  -- Try to update the row and check for a conflict.  
  WITH CHANGE_TRACKING_CONTEXT (@source_id)  
  UPDATE  
     SalesLT.Product  
  SET  
      ListPrice = @new_listprice  
  FROM  
      SalesLT.Product AS P  
  WHERE  
     ProductID = @product_id AND  
     @last_sync_version >= ISNULL (  
         (SELECT CT.SYS_CHANGE_VERSION FROM CHANGETABLE(VERSION SalesLT.Product,  
         (ProductID), (P.ProductID)) AS CT),  
         0)  
```  
  
### <a name="ensuring-consistent-and-correct-results"></a><span data-ttu-id="324dc-260">Asegurarse de que los resultados son coherentes y correctos</span><span class="sxs-lookup"><span data-stu-id="324dc-260">Ensuring Consistent and Correct Results</span></span>  
 <span data-ttu-id="324dc-261">Una aplicación debe considerar el proceso de limpieza cuando valida el valor de @last_sync_version.</span><span class="sxs-lookup"><span data-stu-id="324dc-261">An application must consider the cleanup process when it validates the value of @last_sync_version.</span></span> <span data-ttu-id="324dc-262">Esto se debe a que los datos se podrían haber quitado después de llamar a CHANGE_TRACKING_MIN_VALID_VERSION(), pero antes de que se realizara la actualización.</span><span class="sxs-lookup"><span data-stu-id="324dc-262">This is because data could have been removed after CHANGE_TRACKING_MIN_VALID_VERSION() was called, but before the update was made.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="324dc-263">Recomendamos usar el aislamiento de instantánea y realizar los cambios dentro de una transacción de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="324dc-263">We recommend that you use snapshot isolation and make the changes within a snapshot transaction.</span></span>  
  
```sql  
-- Prerequisite is to ensure ALLOW_SNAPSHOT_ISOLATION is ON for the database.  
  
SET TRANSACTION ISOLATION LEVEL SNAPSHOT;  
BEGIN TRAN  
    -- Verify that last_sync_version is valid.  
    IF (@last_sync_version <  
CHANGE_TRACKING_MIN_VALID_VERSION(OBJECT_ID('SalesLT.Product')))  
    BEGIN  
       RAISERROR (N'Last_sync_version too old', 16, -1);  
    END  
    ELSE  
    BEGIN  
        -- Try to update the row.  
        -- Check @@ROWCOUNT and check for a conflict.  
    END  
COMMIT TRAN  
```  
  
> [!NOTE]  
>  <span data-ttu-id="324dc-264">Existe la posibilidad de que la fila que se está actualizando en la transacción de instantáneas pueda haber sido actualizada en otra transacción una vez iniciada la transacción de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="324dc-264">There is a possibility that the row being updated within the snapshot transaction could have been updated in another transaction after the snapshot transaction was started.</span></span> <span data-ttu-id="324dc-265">En este caso, se producirá un conflicto de actualización del aislamiento de instantánea que provocará que se termine la transacción.</span><span class="sxs-lookup"><span data-stu-id="324dc-265">In this case, a snapshot isolation update conflict will occur and lead to the transaction being terminated.</span></span> <span data-ttu-id="324dc-266">Si esto ocurre, vuelva a intentar la actualización.</span><span class="sxs-lookup"><span data-stu-id="324dc-266">If this happens, retry the update.</span></span> <span data-ttu-id="324dc-267">Esto conducirá entonces a la detección de un conflicto del seguimiento de cambios y a que no se realicen cambios en ninguna fila.</span><span class="sxs-lookup"><span data-stu-id="324dc-267">This will then lead to a change tracking conflict being detected and no rows being changed.</span></span>  
  
##  <a name="change-tracking-and-data-restore"></a><a name="DataRestore"></a><span data-ttu-id="324dc-268">Change Tracking y restauración de datos</span><span class="sxs-lookup"><span data-stu-id="324dc-268">Change Tracking and Data Restore</span></span>  
 <span data-ttu-id="324dc-269">Las aplicaciones que requieren sincronización deben considerar el caso en el que una base de datos que tiene el seguimiento de cambios habilitado revierta a una versión anterior de los datos.</span><span class="sxs-lookup"><span data-stu-id="324dc-269">Applications that require synchronization must consider the case in which a database that has change tracking enabled reverts to an earlier version of the data.</span></span> <span data-ttu-id="324dc-270">Esta situación se puede producir al restaurar una base de datos a partir de una copia de seguridad, cuando se produce una conmutación por causa de error a un espejo de la base de datos asincrónico, o cuando se produce un error al utilizar trasvase de registros.</span><span class="sxs-lookup"><span data-stu-id="324dc-270">This can occur after a database is restored from a backup, when there is a failover to an asynchronous database mirror, or when there is a failure when using log shipping.</span></span> <span data-ttu-id="324dc-271">El siguiente escenario muestra el problema:</span><span class="sxs-lookup"><span data-stu-id="324dc-271">The following scenario illustrates the issue:</span></span>  
  
1.  <span data-ttu-id="324dc-272">La tabla T1 está sometida a seguimiento de cambios y la versión válida mínima para la tabla es 50.</span><span class="sxs-lookup"><span data-stu-id="324dc-272">Table T1 is change tracked, and the minimum valid version for table is 50.</span></span>  
  
2.  <span data-ttu-id="324dc-273">Una aplicación cliente sincroniza datos en la versión 100 y obtiene información sobre todos los cambios realizados entre las versiones 50 y 100.</span><span class="sxs-lookup"><span data-stu-id="324dc-273">A client application synchronizes data at version 100 and obtains information about all changes between versions 50 and 100.</span></span>  
  
3.  <span data-ttu-id="324dc-274">Se realizan cambios adicionales en la tabla T1 después de la versión 100.</span><span class="sxs-lookup"><span data-stu-id="324dc-274">Additional changes are made to table T1 after version 100.</span></span>  
  
4.  <span data-ttu-id="324dc-275">En la versión 120, se produce un error y el administrador de bases de datos restaura la base de datos con pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="324dc-275">At version 120, there is a failure and the database administrator restores the database with data loss.</span></span> <span data-ttu-id="324dc-276">Tras la operación de restauración, la tabla contiene los datos hasta la versión 70 y la versión sincronizada mínima todavía es 50.</span><span class="sxs-lookup"><span data-stu-id="324dc-276">After the restore operation, the table contains data up through version 70, and the minimum synchronized version is still 50.</span></span>  
  
     <span data-ttu-id="324dc-277">Esto significa que el almacén de datos sincronizado tiene datos que ya no existen en el almacén de datos primario.</span><span class="sxs-lookup"><span data-stu-id="324dc-277">This means that the synchronized data store has data that no longer exists in the primary data store.</span></span>  
  
5.  <span data-ttu-id="324dc-278">T1 se actualiza un buen número de veces.</span><span class="sxs-lookup"><span data-stu-id="324dc-278">T1 is updated many times.</span></span> <span data-ttu-id="324dc-279">Ello hace que la versión actual llegue a la 130.</span><span class="sxs-lookup"><span data-stu-id="324dc-279">This brings the current version to 130.</span></span>  
  
6.  <span data-ttu-id="324dc-280">La aplicación cliente sincroniza de nuevo y proporciona una última versión sincronizada de 100.</span><span class="sxs-lookup"><span data-stu-id="324dc-280">The client application synchronizes again and supplies a last-synchronized version of 100.</span></span> <span data-ttu-id="324dc-281">El cliente da por bueno este número porque 100 es mayor que 50.</span><span class="sxs-lookup"><span data-stu-id="324dc-281">The client validates this number successfully because 100 is greater than 50.</span></span>  
  
     <span data-ttu-id="324dc-282">El cliente obtiene los cambios entre la versión 100 y 130.</span><span class="sxs-lookup"><span data-stu-id="324dc-282">The client obtains changes between version 100 and 130.</span></span> <span data-ttu-id="324dc-283">En este punto, el cliente no es consciente de que los cambios entre 70 y 100 no son los mismos que antes.</span><span class="sxs-lookup"><span data-stu-id="324dc-283">At this point, the client is not aware that the changes between 70 and 100 are not the same as before.</span></span> <span data-ttu-id="324dc-284">Los datos en el cliente y en el servidor no están sincronizados.</span><span class="sxs-lookup"><span data-stu-id="324dc-284">The data on the client and server are not synchronized.</span></span>  
  
 <span data-ttu-id="324dc-285">Tenga en cuenta que si la base de datos se recuperara en un punto posterior a la versión 100, no habría ningún problema con la sincronización.</span><span class="sxs-lookup"><span data-stu-id="324dc-285">Note that if the database was recovered to a point after version 100, there would be no problems with synchronization.</span></span> <span data-ttu-id="324dc-286">El cliente y servidor sincronizarían correctamente los datos durante el intervalo de sincronización siguiente.</span><span class="sxs-lookup"><span data-stu-id="324dc-286">The client and server would synchronize data correctly during the next synchronization interval.</span></span>  
  
 <span data-ttu-id="324dc-287">El seguimiento de cambios no permite recuperarse de una pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="324dc-287">Change tracking does not provide support for recovering from the loss of data.</span></span> <span data-ttu-id="324dc-288">Sin embargo, hay dos opciones para detectar estos tipos de problemas de sincronización:</span><span class="sxs-lookup"><span data-stu-id="324dc-288">However, there are two options for detecting these types of synchronization issues:</span></span>  
  
-   <span data-ttu-id="324dc-289">Almacene un Id. de versión de la base de datos en el servidor y actualice este valor cada vez que una base de datos se recupere o por el contrario pierda datos.</span><span class="sxs-lookup"><span data-stu-id="324dc-289">Store a database version ID on the server, and update this value whenever a database is recovered or otherwise loses data.</span></span> <span data-ttu-id="324dc-290">Cada aplicación cliente almacenaría el Id. y cada cliente tendría que validar este Id. cuando sincronice datos.</span><span class="sxs-lookup"><span data-stu-id="324dc-290">Each client application would store the ID, and each client would have to validate this ID when it synchronizes data.</span></span> <span data-ttu-id="324dc-291">Si se produce una pérdida de datos, los Id. no coincidirán y los clientes se reinicializarían.</span><span class="sxs-lookup"><span data-stu-id="324dc-291">If data loss occurs, the IDs will not match and the clients would reinitialize.</span></span> <span data-ttu-id="324dc-292">Una desventaja es que si la pérdida de datos no hubiera cruzado el último límite sincronizado, el cliente podría hacer una reinicialización innecesaria.</span><span class="sxs-lookup"><span data-stu-id="324dc-292">One drawback is if the data loss had not crossed the last synchronized boundary, the client might do unnecessary reinitialization.</span></span>  
  
-   <span data-ttu-id="324dc-293">Cuando un cliente consulte cambios, registre el último número de versión de sincronización para cada cliente en el servidor.</span><span class="sxs-lookup"><span data-stu-id="324dc-293">When a client queries for changes, record the last synchronization version number for each client on the server.</span></span> <span data-ttu-id="324dc-294">Si hay un problema con los datos, los números de última versión sincronizada no coincidirán.</span><span class="sxs-lookup"><span data-stu-id="324dc-294">If there is a problem with the data, the last synchronized version numbers would not match.</span></span> <span data-ttu-id="324dc-295">Esto indica que se requiere una reinicialización.</span><span class="sxs-lookup"><span data-stu-id="324dc-295">This indicates that a reinitialization is required.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="324dc-296">Consulte también</span><span class="sxs-lookup"><span data-stu-id="324dc-296">See Also</span></span>  
 <span data-ttu-id="324dc-297">[Seguimiento de cambios de datos &#40;SQL Server&#41;](../track-changes/track-data-changes-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="324dc-297">[Track Data Changes &#40;SQL Server&#41;](../track-changes/track-data-changes-sql-server.md) </span></span>  
 <span data-ttu-id="324dc-298">[Acerca del seguimiento de cambios &#40;SQL Server&#41;](../track-changes/about-change-tracking-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="324dc-298">[About Change Tracking &#40;SQL Server&#41;](../track-changes/about-change-tracking-sql-server.md) </span></span>  
 <span data-ttu-id="324dc-299">[Administrar Change Tracking &#40;SQL Server&#41;](../track-changes/manage-change-tracking-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="324dc-299">[Manage Change Tracking &#40;SQL Server&#41;](../track-changes/manage-change-tracking-sql-server.md) </span></span>  
 <span data-ttu-id="324dc-300">[Habilitar y deshabilitar Change Tracking &#40;SQL Server&#41;](../track-changes/enable-and-disable-change-tracking-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="324dc-300">[Enable and Disable Change Tracking &#40;SQL Server&#41;](../track-changes/enable-and-disable-change-tracking-sql-server.md) </span></span>  
 <span data-ttu-id="324dc-301">[CHANGETABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/changetable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="324dc-301">[CHANGETABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/changetable-transact-sql) </span></span>  
 <span data-ttu-id="324dc-302">[CHANGE_TRACKING_MIN_VALID_VERSION &#40;&#41;de Transact-SQL](/sql/relational-databases/system-functions/change-tracking-min-valid-version-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="324dc-302">[CHANGE_TRACKING_MIN_VALID_VERSION &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/change-tracking-min-valid-version-transact-sql) </span></span>  
 <span data-ttu-id="324dc-303">[CHANGE_TRACKING_CURRENT_VERSION &#40;&#41;de Transact-SQL](/sql/relational-databases/system-functions/change-tracking-current-version-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="324dc-303">[CHANGE_TRACKING_CURRENT_VERSION &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/change-tracking-current-version-transact-sql) </span></span>  
 [<span data-ttu-id="324dc-304">WITH CHANGE_TRACKING_CONTEXT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="324dc-304">WITH CHANGE_TRACKING_CONTEXT &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/with-change-tracking-context-transact-sql)  
  
  
