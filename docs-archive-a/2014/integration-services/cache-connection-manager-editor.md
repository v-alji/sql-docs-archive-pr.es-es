---
title: Editor del administrador de conexiones de caché | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.cacheconnection.f1
ms.assetid: 0d8f9324-0c35-4eea-b06d-da3cc2426d2c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 38a858217925496d8dd937d684368bdb2e061b14
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676627"
---
# <a name="cache-connection-manager-editor"></a><span data-ttu-id="1166b-102">Editor del administrador de conexiones de caché</span><span class="sxs-lookup"><span data-stu-id="1166b-102">Cache Connection Manager Editor</span></span>
  <span data-ttu-id="1166b-103">El administrador de conexiones de caché lee un conjunto de datos de referencia a partir de la transformación de caché o de un archivo caché (.caw) y puede guardar los datos en un archivo caché.</span><span class="sxs-lookup"><span data-stu-id="1166b-103">The Cache connection manager reads a reference dataset from the Cache transform or from a cache file (.caw), and can save the data to a cache file.</span></span> <span data-ttu-id="1166b-104">Los datos siempre se almacenan en memoria.</span><span class="sxs-lookup"><span data-stu-id="1166b-104">The data is always stored in memory.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1166b-105">El administrador de conexiones de caché no admite los tipos de datos de objetos binarios grandes (BLOB) DT_TEXT, DT_NTEXT y DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="1166b-105">The Cache connection manager does not support the Binary Large Object (BLOB) data types DT_TEXT, DT_NTEXT, and DT_IMAGE.</span></span> <span data-ttu-id="1166b-106">Si el conjunto de datos de referencia contiene un tipo de datos BLOB, se producirá un error en el componente al ejecutar el paquete.</span><span class="sxs-lookup"><span data-stu-id="1166b-106">If the reference dataset contains a BLOB data type, the component will fail when you run the package.</span></span> <span data-ttu-id="1166b-107">Puede utilizar el **Editor del administrador de conexiones de caché** para modificar los tipos de datos de columna.</span><span class="sxs-lookup"><span data-stu-id="1166b-107">You can use the **Cache Connection Manager Editor** to modify column data types.</span></span>  
  
 <span data-ttu-id="1166b-108">La transformación de Búsqueda realiza búsquedas en el conjunto de datos de referencia.</span><span class="sxs-lookup"><span data-stu-id="1166b-108">The Lookup transformation performs lookups on the reference dataset.</span></span>  
  
 <span data-ttu-id="1166b-109">En el cuadro de diálogo **Editor del administrador de conexiones de caché** se incluyen estas pestañas:</span><span class="sxs-lookup"><span data-stu-id="1166b-109">The **Cache Connection ManagerEditor** dialog box includes the following tabs:</span></span>  
  
-   [<span data-ttu-id="1166b-110">Pestaña General</span><span class="sxs-lookup"><span data-stu-id="1166b-110">General tab</span></span>](#generaltab)  
  
-   [<span data-ttu-id="1166b-111">Pestaña columnas</span><span class="sxs-lookup"><span data-stu-id="1166b-111">Columns tab</span></span>](#columnstab)  
  
 <span data-ttu-id="1166b-112">Para obtener más información sobre el administrador de conexiones de caché, vea [Administrador de conexiones de caché](connection-manager/cache-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="1166b-112">To learn more about the Cache Connection Manager, see [Cache Connection Manager](connection-manager/cache-connection-manager.md).</span></span>  
  
##  <a name="general-tab"></a><a name="generaltab"></a><span data-ttu-id="1166b-113">Pestaña General</span><span class="sxs-lookup"><span data-stu-id="1166b-113">General Tab</span></span>  
 <span data-ttu-id="1166b-114">Use la pestaña **General** del cuadro de diálogo **Editor del administrador de conexiones de caché** para indicar si la memoria caché se leerá desde un archivo o se guardará en un archivo.</span><span class="sxs-lookup"><span data-stu-id="1166b-114">Use the **General** tab of the **Cache Connection ManagerEditor** dialog box to indicate whether to read the cache from a file or save the cache to a file.</span></span>  
  
### <a name="options"></a><span data-ttu-id="1166b-115">Opciones</span><span class="sxs-lookup"><span data-stu-id="1166b-115">Options</span></span>  
 <span data-ttu-id="1166b-116">**Nombre del administrador de conexiones**</span><span class="sxs-lookup"><span data-stu-id="1166b-116">**Connection manager name**</span></span>  
 <span data-ttu-id="1166b-117">Especifique un nombre único para la conexión de caché en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1166b-117">Provide a unique name for the cache connection in the workflow.</span></span> <span data-ttu-id="1166b-118">El nombre que indique se mostrará en el Diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1166b-118">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="1166b-119">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="1166b-119">**Description**</span></span>  
 <span data-ttu-id="1166b-120">Describe la conexión.</span><span class="sxs-lookup"><span data-stu-id="1166b-120">Describe the connection.</span></span> <span data-ttu-id="1166b-121">Como método recomendado, describa la conexión en función de su propósito, para que los paquetes estén autodocumentados y sean más fáciles de mantener.</span><span class="sxs-lookup"><span data-stu-id="1166b-121">As a best practice, describe the connection according to its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="1166b-122">**Utilizar la caché del archivo.**</span><span class="sxs-lookup"><span data-stu-id="1166b-122">**Use file cache**</span></span>  
 <span data-ttu-id="1166b-123">Indicar si se ha de utilizar un archivo caché.</span><span class="sxs-lookup"><span data-stu-id="1166b-123">Indicate whether to use a cache file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1166b-124">El nivel de protección del paquete no se aplica al archivo caché.</span><span class="sxs-lookup"><span data-stu-id="1166b-124">The protection level of the package does not apply to the cache file.</span></span> <span data-ttu-id="1166b-125">Si el archivo caché contiene información confidencial, utilice una lista de control de acceso (ACL) para restringir el acceso a la ubicación o carpeta en la que almacena el archivo.</span><span class="sxs-lookup"><span data-stu-id="1166b-125">If the cache file contains sensitive information, use an access control list (ACL) to restrict access to the location or folder in which you store the file.</span></span> <span data-ttu-id="1166b-126">Solo debería permitir el acceso a ciertas cuentas.</span><span class="sxs-lookup"><span data-stu-id="1166b-126">You should enable access only to certain accounts.</span></span> <span data-ttu-id="1166b-127">Para más información, vea [Acceso a los archivos usados por los paquetes](../../2014/integration-services/access-to-files-used-by-packages.md).</span><span class="sxs-lookup"><span data-stu-id="1166b-127">For more information, see [Access to Files Used by Packages](../../2014/integration-services/access-to-files-used-by-packages.md).</span></span>  
  
 <span data-ttu-id="1166b-128">Si configura el administrador de conexiones de caché para utilizar un archivo caché, el administrador de conexiones realizará una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="1166b-128">If you configure the cache connection manager to use a cache file, the connection manager will do one of the following actions:</span></span>  
  
-   <span data-ttu-id="1166b-129">Guardar los datos en el archivo cuando se haya configurado una transformación de caché para escribir los datos procedentes de un origen de datos del flujo de datos en el administrador de conexiones de caché.</span><span class="sxs-lookup"><span data-stu-id="1166b-129">Save data to the file when a Cache Transform transformation is configured to write data from a data source in the data flow to the Cache connection manager.</span></span> <span data-ttu-id="1166b-130">Para obtener más información, vea [Cache Transform](data-flow/transformations/cache-transform.md).</span><span class="sxs-lookup"><span data-stu-id="1166b-130">For more information, see [Cache Transform](data-flow/transformations/cache-transform.md).</span></span>  
  
-   <span data-ttu-id="1166b-131">Leer los datos desde el archivo caché.</span><span class="sxs-lookup"><span data-stu-id="1166b-131">Read data from the cache file.</span></span>  
  
 <span data-ttu-id="1166b-132">**Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="1166b-132">**File name**</span></span>  
 <span data-ttu-id="1166b-133">Escriba la ruta y el nombre de archivo del archivo caché.</span><span class="sxs-lookup"><span data-stu-id="1166b-133">Type the path and file name of the cache file.</span></span>  
  
 <span data-ttu-id="1166b-134">**Browse**</span><span class="sxs-lookup"><span data-stu-id="1166b-134">**Browse**</span></span>  
 <span data-ttu-id="1166b-135">Busque el archivo caché.</span><span class="sxs-lookup"><span data-stu-id="1166b-135">Locate the cache file.</span></span>  
  
 <span data-ttu-id="1166b-136">**Actualizar los metadatos**</span><span class="sxs-lookup"><span data-stu-id="1166b-136">**Refresh Metadata**</span></span>  
 <span data-ttu-id="1166b-137">Elimine los metadatos de columna del administrador de conexiones de caché y vuelva a llenar el administrador de conexiones de caché con los metadatos de la columna del archivo caché seleccionado.</span><span class="sxs-lookup"><span data-stu-id="1166b-137">Delete the column metadata in the Cache connection manager and repopulate the Cache connection manager with column metadata from a selected cache file.</span></span>  
  
##  <a name="columns-tab"></a><a name="columnstab"></a><span data-ttu-id="1166b-138">Pestaña columnas</span><span class="sxs-lookup"><span data-stu-id="1166b-138">Columns Tab</span></span>  
 <span data-ttu-id="1166b-139">Utilice la pestaña **Columnas** del cuadro de diálogo **Editor del administrador de conexiones de caché** para configurar las propiedades de cada columna en la caché.</span><span class="sxs-lookup"><span data-stu-id="1166b-139">Use the **Columns** tab of the **Cache Connection Manager Editor** dialog box to configure the properties of each column in the cache.</span></span>  
  
### <a name="options"></a><span data-ttu-id="1166b-140">Opciones</span><span class="sxs-lookup"><span data-stu-id="1166b-140">Options</span></span>  
 <span data-ttu-id="1166b-141">**Columna**</span><span class="sxs-lookup"><span data-stu-id="1166b-141">**Column**</span></span>  
 <span data-ttu-id="1166b-142">Especifique el nombre de la columna.</span><span class="sxs-lookup"><span data-stu-id="1166b-142">Specify the column name.</span></span>  
  
 <span data-ttu-id="1166b-143">**Posición de índice**</span><span class="sxs-lookup"><span data-stu-id="1166b-143">**Index Position**</span></span>  
 <span data-ttu-id="1166b-144">Define qué columnas son columnas de índice especificando la posición de índice de cada columna.</span><span class="sxs-lookup"><span data-stu-id="1166b-144">Specify which columns are index columns by specifying the index position of each column.</span></span> <span data-ttu-id="1166b-145">El índice es una colección de una o varias columnas.</span><span class="sxs-lookup"><span data-stu-id="1166b-145">The index is a collection of one or more columns.</span></span>  
  
 <span data-ttu-id="1166b-146">Para las columnas de no índice, la posición de índice es 0.</span><span class="sxs-lookup"><span data-stu-id="1166b-146">For non-index columns, the index position is 0.</span></span>  
  
 <span data-ttu-id="1166b-147">Para las columnas de índice, la posición de índice es un número secuencial positivo.</span><span class="sxs-lookup"><span data-stu-id="1166b-147">For index columns, the index position is a sequential, positive number.</span></span> <span data-ttu-id="1166b-148">Este número indica el orden en el que la transformación Búsqueda compara las filas del conjunto de datos de referencia con las filas del origen de datos de entrada.</span><span class="sxs-lookup"><span data-stu-id="1166b-148">This number indicates the order in which the Lookup transformation compares rows in the reference dataset to rows in the input data source.</span></span> <span data-ttu-id="1166b-149">La columna con el mayor número de valores únicos debería tener la posición de índice más pequeña.</span><span class="sxs-lookup"><span data-stu-id="1166b-149">The column with the most unique values should have the lowest index position.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1166b-150">Cuando la transformación Búsqueda se configura para utilizar un administrador de conexiones de caché, a las columnas de entrada solo se les puede asignar las columnas de índice del conjunto de datos de referencia.</span><span class="sxs-lookup"><span data-stu-id="1166b-150">When the Lookup transformation is configured to use a Cache connection manager, only index columns in the reference dataset can be mapped to input columns.</span></span> <span data-ttu-id="1166b-151">Asimismo, todas las columnas de índice deben estar asignadas.</span><span class="sxs-lookup"><span data-stu-id="1166b-151">Also, all index columns must be mapped.</span></span>  
  
 <span data-ttu-id="1166b-152">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1166b-152">**Type**</span></span>  
 <span data-ttu-id="1166b-153">Especifica el tipo de datos de la columna.</span><span class="sxs-lookup"><span data-stu-id="1166b-153">Specify the data type of the column.</span></span>  
  
 `Length`  
 <span data-ttu-id="1166b-154">Especifica el tipo de datos de la columna.</span><span class="sxs-lookup"><span data-stu-id="1166b-154">Specifies the column data type.</span></span> <span data-ttu-id="1166b-155">Si procede en el caso del tipo de datos, puede actualizar la `Length`.</span><span class="sxs-lookup"><span data-stu-id="1166b-155">If applicable to the data type, you can update `Length`.</span></span>  
  
 `Precision`  
 <span data-ttu-id="1166b-156">Especifica la precisión para cierto tipo de datos de columna.</span><span class="sxs-lookup"><span data-stu-id="1166b-156">Specifies the precision for certain column data types.</span></span> <span data-ttu-id="1166b-157">La precisión es el número de dígitos de un número.</span><span class="sxs-lookup"><span data-stu-id="1166b-157">Precision is the number of digits in a number.</span></span> <span data-ttu-id="1166b-158">Si procede en el caso del tipo de datos, puede actualizar la `Precision`.</span><span class="sxs-lookup"><span data-stu-id="1166b-158">If applicable to the data type, you can update `Precision`.</span></span>  
  
 `Scale`  
 <span data-ttu-id="1166b-159">Especifica la escala para cierto tipo de datos de columna.</span><span class="sxs-lookup"><span data-stu-id="1166b-159">Specifies the scale for certain column data types.</span></span> <span data-ttu-id="1166b-160">La escala es el número de dígitos situados a la derecha de la coma decimal de un número.</span><span class="sxs-lookup"><span data-stu-id="1166b-160">Scale is the number of digits to the right of the decimal point in a number.</span></span> <span data-ttu-id="1166b-161">Si procede en el caso del tipo de datos, puede actualizar la `Scale`.</span><span class="sxs-lookup"><span data-stu-id="1166b-161">If applicable to the data type, you can update `Scale`.</span></span>  
  
 `Code Page`  
 <span data-ttu-id="1166b-162">Especifica la página de códigos para el tipo de columna.</span><span class="sxs-lookup"><span data-stu-id="1166b-162">Specifies the code page for the column type.</span></span> <span data-ttu-id="1166b-163">Si procede en el caso del tipo de datos, puede actualizar la `Code Page`.</span><span class="sxs-lookup"><span data-stu-id="1166b-163">If applicable to the data type, you can update `Code Page`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1166b-164">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1166b-164">See Also</span></span>  
 [<span data-ttu-id="1166b-165">Transformación Búsqueda</span><span class="sxs-lookup"><span data-stu-id="1166b-165">Lookup Transformation</span></span>](data-flow/transformations/lookup-transformation.md)  
  
  
