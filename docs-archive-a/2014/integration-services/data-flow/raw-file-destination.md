---
title: Destino de archivo sin formato | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.rawfiledest.f1
helpviewer_keywords:
- append options [Integration Services]
- destinations [Integration Services], Raw File
- raw data [Integration Services]
- writing raw data
- Raw File destination
ms.assetid: d311b458-aefc-4b4d-b1a1-4c0ebbb34214
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fc5ce99be6e467ba323137ef885cbb13bfb328ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670458"
---
# <a name="raw-file-destination"></a><span data-ttu-id="3ff25-102">destino de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="3ff25-102">Raw File Destination</span></span>
  <span data-ttu-id="3ff25-103">El destino de archivo sin formato escribe datos sin procesar en un archivo.</span><span class="sxs-lookup"><span data-stu-id="3ff25-103">The Raw File destination writes raw data to a file.</span></span> <span data-ttu-id="3ff25-104">Como el formato de los datos es el nativo del destino, no es necesario traducir los datos y prácticamente no es necesario analizar el archivo.</span><span class="sxs-lookup"><span data-stu-id="3ff25-104">Because the format of the data is native to the destination, the data requires no translation and little parsing.</span></span> <span data-ttu-id="3ff25-105">Esto significa que el destino de archivo sin formato puede escribir datos más rápidamente que otros destinos, como el destino de archivo plano o los destinos de OLE DB.</span><span class="sxs-lookup"><span data-stu-id="3ff25-105">This means that the Raw File destination can write data more quickly than other destinations such as the Flat File and the OLE DB destinations.</span></span>  
  
 <span data-ttu-id="3ff25-106">Además de escribir datos sin procesar en un archivo, puede utilizar el destino de archivo sin formato para generar un archivo sin formato vacío que contenga solo las columnas (archivo solo para metadatos), sin tener que ejecutar el paquete.</span><span class="sxs-lookup"><span data-stu-id="3ff25-106">In addition to writing raw data to a file, you can also use the Raw File destination to generate an empty raw file that contains only the columns (metadata-only file), without having to run the package.</span></span> <span data-ttu-id="3ff25-107">El origen de archivo sin formato se usa para recuperar datos sin formato escritos previamente por el destino.</span><span class="sxs-lookup"><span data-stu-id="3ff25-107">You use the Raw File source to retrieve raw data that was previously written by the destination.</span></span> <span data-ttu-id="3ff25-108">Puede también designar el origen de archivo sin formato para el archivo que solo tiene metadatos.</span><span class="sxs-lookup"><span data-stu-id="3ff25-108">You can also point the Raw File source to the metadata-only file.</span></span>  
  
 <span data-ttu-id="3ff25-109">El archivo sin formato contiene información sobre el orden.</span><span class="sxs-lookup"><span data-stu-id="3ff25-109">The raw file format contains sort information.</span></span> <span data-ttu-id="3ff25-110">El destino de archivo sin formato guarda toda la información sobre el orden incluidas las marcas de comparación para las columnas de cadena.</span><span class="sxs-lookup"><span data-stu-id="3ff25-110">The Raw File Destination saves all the sort information including the comparison flags for string columns.</span></span> <span data-ttu-id="3ff25-111">El origen de archivo sin formato lee y respeta la información sobre el orden.</span><span class="sxs-lookup"><span data-stu-id="3ff25-111">The Raw File source reads and honors the sort information.</span></span> <span data-ttu-id="3ff25-112">Tiene la opción de configurar el origen de archivo sin formato para omitir los marcas de orden en el archivo; para ello use el Editor avanzado.</span><span class="sxs-lookup"><span data-stu-id="3ff25-112">You do have the option of configuring the Raw File Source to ignore the sort flags in the file, using the Advanced Editor.</span></span> <span data-ttu-id="3ff25-113">Para obtener más información acerca de las marcas de comparación, vea [Comparing String Data](comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="3ff25-113">For more information about comparison flags, see [Comparing String Data](comparing-string-data.md).</span></span>  
  
 <span data-ttu-id="3ff25-114">Puede configurar el destino de archivo sin formato de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="3ff25-114">You can configure the Raw File destination in the following ways:</span></span>  
  
-   <span data-ttu-id="3ff25-115">Especifique un modo de acceso que sea el nombre del archivo o una variable que contenga el nombre del archivo en el que escribe el destino de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="3ff25-115">Specify an access mode which is either the name of the file or a variable that contains the name of the file to which the Raw File destination writes.</span></span>  
  
-   <span data-ttu-id="3ff25-116">Indique si el destino de archivo sin formato anexa datos a un archivo existente que tiene el mismo nombre o crea un nuevo archivo.</span><span class="sxs-lookup"><span data-stu-id="3ff25-116">Indicate whether the Raw File destination appends data to an existing file that has the same name or creates a new file.</span></span>  
  
 <span data-ttu-id="3ff25-117">El destino de archivo sin formato con frecuencia se usa para escribir resultados intermedios de datos procesados parcialmente entre ejecuciones de paquetes.</span><span class="sxs-lookup"><span data-stu-id="3ff25-117">The Raw File destination is frequently used to write intermediary results of partly processed data between package executions.</span></span> <span data-ttu-id="3ff25-118">El almacenamiento de datos sin procesar significa que los datos pueden ser leídos rápidamente por un origen de archivo sin formato y luego se pueden transformar todavía más antes de que se carguen en su destino final.</span><span class="sxs-lookup"><span data-stu-id="3ff25-118">Storing raw data means that the data can be read quickly by a Raw File source and then further transformed before it is loaded into its final destination.</span></span> <span data-ttu-id="3ff25-119">Por ejemplo, un paquete puede ejecutarse varias veces y cada vez puede escribir datos sin procesar en los archivos.</span><span class="sxs-lookup"><span data-stu-id="3ff25-119">For example, a package might run several times, and each time write raw data to files.</span></span> <span data-ttu-id="3ff25-120">Posteriormente, otro paquete puede usar el origen de archivo sin formato para leer de cada archivo, usar una transformación Unión de todo para combinar los datos en un solo conjunto de datos y luego aplicar transformaciones adicionales que resuman los datos antes de cargar los datos en su destino final, como una tabla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3ff25-120">Later, a different package can use the Raw File source to read from each file, use a Union All transformation to merge the data into one data set, and then apply additional transformations that summarize the data before loading the data into its final destination such as a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3ff25-121">El destino de archivo sin formato admite datos NULL pero no admite datos de objetos binarios grandes (BLOB).</span><span class="sxs-lookup"><span data-stu-id="3ff25-121">The Raw File destination supports null data but not binary large object (BLOB) data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3ff25-122">El destino de archivo sin formato no usa un administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="3ff25-122">The Raw File destination does not use a connection manager.</span></span>  
  
 <span data-ttu-id="3ff25-123">Este origen tiene una entrada normal.</span><span class="sxs-lookup"><span data-stu-id="3ff25-123">This source has one regular input.</span></span> <span data-ttu-id="3ff25-124">No admite una salida de error.</span><span class="sxs-lookup"><span data-stu-id="3ff25-124">It does not support an error output.</span></span>  
  
## <a name="append-and-new-file-options"></a><span data-ttu-id="3ff25-125">Opciones de anexar y nuevo archivo</span><span class="sxs-lookup"><span data-stu-id="3ff25-125">Append and New File Options</span></span>  
 <span data-ttu-id="3ff25-126">La propiedad WriteOption incluye opciones para anexar datos a un archivo existente o para crear un archivo.</span><span class="sxs-lookup"><span data-stu-id="3ff25-126">The WriteOption property includes options to append data to an existing file or create a new file.</span></span>  
  
 <span data-ttu-id="3ff25-127">En la tabla siguiente se describen las opciones disponibles para la propiedad WriteOption.</span><span class="sxs-lookup"><span data-stu-id="3ff25-127">The following table describes the available options for the WriteOption property.</span></span>  
  
|<span data-ttu-id="3ff25-128">Opción</span><span class="sxs-lookup"><span data-stu-id="3ff25-128">Option</span></span>|<span data-ttu-id="3ff25-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="3ff25-129">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="3ff25-130">Append</span><span class="sxs-lookup"><span data-stu-id="3ff25-130">Append</span></span>|<span data-ttu-id="3ff25-131">Anexa datos a un archivo existente.</span><span class="sxs-lookup"><span data-stu-id="3ff25-131">Appends data to an existing file.</span></span> <span data-ttu-id="3ff25-132">Los metadatos de los datos anexados deben coincidir con el formato del archivo.</span><span class="sxs-lookup"><span data-stu-id="3ff25-132">The metadata of the appended data must match the file format.</span></span>|  
|<span data-ttu-id="3ff25-133">Crear siempre</span><span class="sxs-lookup"><span data-stu-id="3ff25-133">Create always</span></span>|<span data-ttu-id="3ff25-134">Crea siempre un nuevo archivo.</span><span class="sxs-lookup"><span data-stu-id="3ff25-134">Always creates a new file.</span></span>|  
|<span data-ttu-id="3ff25-135">Crear una vez</span><span class="sxs-lookup"><span data-stu-id="3ff25-135">Create once</span></span>|<span data-ttu-id="3ff25-136">Crea un nuevo archivo.</span><span class="sxs-lookup"><span data-stu-id="3ff25-136">Creates a new file.</span></span> <span data-ttu-id="3ff25-137">Si existe el archivo, el componente genera un error.</span><span class="sxs-lookup"><span data-stu-id="3ff25-137">If the file exists, the component fails.</span></span>|  
|<span data-ttu-id="3ff25-138">Truncar y anexar</span><span class="sxs-lookup"><span data-stu-id="3ff25-138">Truncate and append</span></span>|<span data-ttu-id="3ff25-139">Trunca un archivo existente y luego escribe los datos en el archivo.</span><span class="sxs-lookup"><span data-stu-id="3ff25-139">Truncates an existing file and then writes the data to the file.</span></span> <span data-ttu-id="3ff25-140">Los metadatos de los datos anexados deben coincidir con el formato del archivo.</span><span class="sxs-lookup"><span data-stu-id="3ff25-140">The metadata of the appended data must match the file format.</span></span>|  
  
 <span data-ttu-id="3ff25-141">Los siguientes elementos son importantes cuando se anexan datos:</span><span class="sxs-lookup"><span data-stu-id="3ff25-141">The following are important items about appending data:</span></span>  
  
-   <span data-ttu-id="3ff25-142">Cuando se anexan datos a un archivo sin formato existente no se vuelven a ordenar.</span><span class="sxs-lookup"><span data-stu-id="3ff25-142">Appending data to an existing raw file does not re-sort the data.</span></span>  
  
     <span data-ttu-id="3ff25-143">Debe asegurarse de que las claves ordenadas permanecen en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="3ff25-143">You need to make certain that the sorted keys remain in the correct order.</span></span>  
  
-   <span data-ttu-id="3ff25-144">Cuando se anexan datos a un archivo sin formato existente no se cambian los metadatos del archivo (información sobre el orden).</span><span class="sxs-lookup"><span data-stu-id="3ff25-144">Appending data to an existing raw file does not change the file metadata (sort information).</span></span>  
  
 <span data-ttu-id="3ff25-145">Por ejemplo, un paquete lee los datos ordenados en ProductKey (PK).</span><span class="sxs-lookup"><span data-stu-id="3ff25-145">For example, a package reads data sorted on the ProductKey (PK).</span></span> <span data-ttu-id="3ff25-146">El flujo de datos del paquete anexa los datos a un archivo sin formato existente.</span><span class="sxs-lookup"><span data-stu-id="3ff25-146">The package data flow appends the data to an existing raw file.</span></span> <span data-ttu-id="3ff25-147">La primera vez que se ejecuta un paquete, se reciben tres filas (PK 1000, 1100, 1200).</span><span class="sxs-lookup"><span data-stu-id="3ff25-147">The first time the package runs, three rows are received (PK 1000, 1100, 1200).</span></span> <span data-ttu-id="3ff25-148">Ahora, el archivo sin formato contiene los datos siguientes.</span><span class="sxs-lookup"><span data-stu-id="3ff25-148">The raw file now contains the following data.</span></span>  
  
-   <span data-ttu-id="3ff25-149">1000, productA</span><span class="sxs-lookup"><span data-stu-id="3ff25-149">1000, productA</span></span>  
  
-   <span data-ttu-id="3ff25-150">1100, productB</span><span class="sxs-lookup"><span data-stu-id="3ff25-150">1100, productB</span></span>  
  
-   <span data-ttu-id="3ff25-151">1200, productC</span><span class="sxs-lookup"><span data-stu-id="3ff25-151">1200, productC</span></span>  
  
 <span data-ttu-id="3ff25-152">La segunda vez que se ejecuta el paquete, se reciben dos filas nuevas (PK 1001, 1300).</span><span class="sxs-lookup"><span data-stu-id="3ff25-152">The second time the package runs, two new rows are received (PK 1001, 1300).</span></span> <span data-ttu-id="3ff25-153">Ahora, el archivo sin formato contiene los datos siguientes.</span><span class="sxs-lookup"><span data-stu-id="3ff25-153">The raw file now contains the following data.</span></span>  
  
-   <span data-ttu-id="3ff25-154">1000, productA</span><span class="sxs-lookup"><span data-stu-id="3ff25-154">1000, productA</span></span>  
  
-   <span data-ttu-id="3ff25-155">1100, productB</span><span class="sxs-lookup"><span data-stu-id="3ff25-155">1100, productB</span></span>  
  
-   <span data-ttu-id="3ff25-156">1200, productC</span><span class="sxs-lookup"><span data-stu-id="3ff25-156">1200, productC</span></span>  
  
-   <span data-ttu-id="3ff25-157">1001, productD</span><span class="sxs-lookup"><span data-stu-id="3ff25-157">1001, productD</span></span>  
  
-   <span data-ttu-id="3ff25-158">1300, productE</span><span class="sxs-lookup"><span data-stu-id="3ff25-158">1300, productE</span></span>  
  
 <span data-ttu-id="3ff25-159">Los datos nuevos se anexan al final del archivo sin formato y las claves ordenadas (PK) no se incluyen en el orden.</span><span class="sxs-lookup"><span data-stu-id="3ff25-159">The new data is appended to the end of the raw file, and the sorted keys (PK) are out of order.</span></span> <span data-ttu-id="3ff25-160">Además, la operación de anexar no ha cambiado los metadatos del archivo (información sobre el orden).</span><span class="sxs-lookup"><span data-stu-id="3ff25-160">In addition, the append operation didn't change the file metadata (sort information).</span></span> <span data-ttu-id="3ff25-161">Si lee el archivo con el origen de archivo sin formato, el componente indica que el archivo todavía está ordenado según PK aunque los datos del archivo ya no estén en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="3ff25-161">If you read the file by using the Raw File source, the component indicates that the file is still sorted on PK even though the data in the file is no longer in the correct order.</span></span>  
  
 <span data-ttu-id="3ff25-162">Para mantener las claves ordenadas en el orden correcto mientras se anexan datos, puede diseñar el flujo de datos del paquete como sigue:</span><span class="sxs-lookup"><span data-stu-id="3ff25-162">To keep the sorted keys in the correct order while appending data, you can design the package data flow as follows:</span></span>  
  
1.  <span data-ttu-id="3ff25-163">Recupere filas nuevas mediante Origen A.</span><span class="sxs-lookup"><span data-stu-id="3ff25-163">Retrieve new rows by using Source A.</span></span>  
  
2.  <span data-ttu-id="3ff25-164">Recupere filas existentes desde RawFile1 con Origen B.</span><span class="sxs-lookup"><span data-stu-id="3ff25-164">Retrieve existing rows from RawFile1 using Source B.</span></span>  
  
3.  <span data-ttu-id="3ff25-165">Combine las entradas Origen A y Origen B mediante la transformación Unión de todo.</span><span class="sxs-lookup"><span data-stu-id="3ff25-165">Combine the inputs from Source A and Source B by using the Union All transformation.</span></span>  
  
4.  <span data-ttu-id="3ff25-166">Ordene según PK.</span><span class="sxs-lookup"><span data-stu-id="3ff25-166">Sort on PK.</span></span>  
  
5.  <span data-ttu-id="3ff25-167">Escriba en RawFile2 mediante el destino de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="3ff25-167">Write to RawFile2 by using the Raw File destination.</span></span>  
  
     <span data-ttu-id="3ff25-168">RawFile1 está bloqueado porque se está leyendo en el flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="3ff25-168">RawFile1 is locked because it's being read from, in the data flow.</span></span>  
  
6.  <span data-ttu-id="3ff25-169">Reemplace RawFile1 con RawFile2.</span><span class="sxs-lookup"><span data-stu-id="3ff25-169">Replace RawFile1 with RawFile2.</span></span>  
  
### <a name="using-the-raw-file-destination-in-a-loop"></a><span data-ttu-id="3ff25-170">Usar el destino de archivo sin formato en un bucle</span><span class="sxs-lookup"><span data-stu-id="3ff25-170">Using the Raw File Destination in a Loop</span></span>  
 <span data-ttu-id="3ff25-171">Si el flujo de datos que usa el destino de archivo sin formato se encuentra en un bucle, puede resultar conveniente crear el archivo una vez y, después, agregar los datos al archivo cuando se repita el bucle.</span><span class="sxs-lookup"><span data-stu-id="3ff25-171">If the data flow that uses the Raw File destination is in a loop, you may want to create the file once and then append data to the file when the loop repeats.</span></span> <span data-ttu-id="3ff25-172">Para agregar los datos al archivo, los datos agregados deben tener el mismo formato que el archivo existente.</span><span class="sxs-lookup"><span data-stu-id="3ff25-172">To append data to the file, the data that is appended must match the format of the existing file.</span></span>  
  
 <span data-ttu-id="3ff25-173">Para crear el archivo en la primera iteración del bucle y, posteriormente, agregar filas en las iteraciones subsiguientes, debe hacer lo siguiente en tiempo de diseño:</span><span class="sxs-lookup"><span data-stu-id="3ff25-173">To create the file in the first iteration of the loop, and then append rows in the subsequent iterations of the loop, you need to do the following at design time:</span></span>  
  
1.  <span data-ttu-id="3ff25-174">Establezca la propiedad WriteOption en **CreateOnce** o **CreateAlways**y ejecute una iteración del bucle.</span><span class="sxs-lookup"><span data-stu-id="3ff25-174">Set the WriteOption property to **CreateOnce** or **CreateAlways**and run one iteration of the loop.</span></span> <span data-ttu-id="3ff25-175">Se crea el archivo.</span><span class="sxs-lookup"><span data-stu-id="3ff25-175">The file is created.</span></span> <span data-ttu-id="3ff25-176">Así se garantiza que los metadatos de los datos agregados y del archivo sean iguales.</span><span class="sxs-lookup"><span data-stu-id="3ff25-176">This ensures that the metadata of appended data and the file matches.</span></span>  
  
2.  <span data-ttu-id="3ff25-177">Restablezca la propiedad WriteOption en **Append** y establezca la propiedad ValidateExternalMetadata en `False` .</span><span class="sxs-lookup"><span data-stu-id="3ff25-177">Reset the WriteOption property to **Append** and set the ValidateExternalMetadata property to `False`.</span></span>  
  
 <span data-ttu-id="3ff25-178">Si usa la opción **TruncateAppend** en lugar de la opción **Append** , truncará las filas que se agregaron en toda iteración anterior y anexará filas nuevas.</span><span class="sxs-lookup"><span data-stu-id="3ff25-178">If you use the **TruncateAppend** option instead of the **Append** option, it will truncate rows that were added in any previous iteration, and then append new rows.</span></span> <span data-ttu-id="3ff25-179">Con la opción **TruncateAppend** también es necesario que los datos tengan el mismo formato que el archivo.</span><span class="sxs-lookup"><span data-stu-id="3ff25-179">Using the **TruncateAppend** option also requires that the data matches the file format.</span></span>  
  
## <a name="configuration-of-the-raw-file-destination"></a><span data-ttu-id="3ff25-180">Configuración del destino de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="3ff25-180">Configuration of the Raw File Destination</span></span>  
 <span data-ttu-id="3ff25-181">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="3ff25-181">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="3ff25-182">El cuadro de diálogo **Editor avanzado** indica las propiedades que se pueden establecer mediante programación.</span><span class="sxs-lookup"><span data-stu-id="3ff25-182">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="3ff25-183">Para obtener más información acerca de las propiedades que puede establecer a través del cuadro de diálogo **Editor avanzado** o mediante programación, haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="3ff25-183">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="3ff25-184">Common Properties</span><span class="sxs-lookup"><span data-stu-id="3ff25-184">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="3ff25-185">Propiedades personalizadas de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="3ff25-185">Raw File Custom Properties</span></span>](raw-file-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="3ff25-186">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="3ff25-186">Related Tasks</span></span>  
 <span data-ttu-id="3ff25-187">Para obtener información sobre cómo establecer las propiedades del componente, vea [Establecer las propiedades de un componente de flujo de datos](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="3ff25-187">For information about how to set properties of the component, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="3ff25-188">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="3ff25-188">Related Content</span></span>  
 <span data-ttu-id="3ff25-189">Entrada del blog, sobre los [archivos sin formato](https://www.sqlservercentral.com/blogs/31-days-of-ssis-%e2%80%93-raw-files-are-awesome-131), en sqlservercentral.com</span><span class="sxs-lookup"><span data-stu-id="3ff25-189">Blog entry, [Raw Files Are Awesome](https://www.sqlservercentral.com/blogs/31-days-of-ssis-%e2%80%93-raw-files-are-awesome-131), on sqlservercentral.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ff25-190">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3ff25-190">See Also</span></span>  
 <span data-ttu-id="3ff25-191">[Origen de archivo sin formato](raw-file-source.md) </span><span class="sxs-lookup"><span data-stu-id="3ff25-191">[Raw File Source](raw-file-source.md) </span></span>  
 [<span data-ttu-id="3ff25-192">Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="3ff25-192">Data Flow</span></span>](data-flow.md)  
  
  
