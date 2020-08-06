---
title: 'Lección 1: crear el proyecto y el paquete básico | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 84d0b877-603f-4f8e-bb6b-671558ade5c2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1a9ddc36ef242cc4e4b146e90dfa9de470e68d83
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673116"
---
# <a name="lesson-1-creating-the-project-and-basic-package"></a><span data-ttu-id="c3d0d-102">Lección 1: Creación del proyecto y el paquete básico</span><span class="sxs-lookup"><span data-stu-id="c3d0d-102">Lesson 1: Creating the Project and Basic Package</span></span>
  <span data-ttu-id="c3d0d-103">En esta lección, creará un paquete ETL simple que extrae datos de un único origen de archivo plano, transforma los datos usando dos componentes de la transformación de búsqueda y escribe dichos datos en la tabla de hechos **FactCurrency** de **AdventureWorksDW2012**.</span><span class="sxs-lookup"><span data-stu-id="c3d0d-103">In this lesson, you will create a simple ETL package that extracts data from a single flat file source, transforms the data using two lookup transformation components, and writes that data to the **FactCurrency** fact table in **AdventureWorksDW2012**.</span></span> <span data-ttu-id="c3d0d-104">Como parte de esta lección, aprenderá a crear paquetes nuevos, agregar y configurar orígenes de datos y conexiones de destino, y trabajar con nuevos componentes de flujo de control y flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="c3d0d-104">As part of this lesson, you will learn how to create new packages, add and configure data source and destination connections, and work with new control flow and data flow components.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c3d0d-105">Para este tutorial, se necesita la base de datos de ejemplo **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="c3d0d-105">This tutorial requires the **AdventureWorksDW2012** sample database.</span></span> <span data-ttu-id="c3d0d-106">Para obtener más información sobre la instalación e implementación de **AdventureWorksDW2012**, vea [Microsoft SQL Server Product samples: Reporting Services](https://archive.codeplex.com/?p=msftrsprodsamples).</span><span class="sxs-lookup"><span data-stu-id="c3d0d-106">For more information on installing and deploying **AdventureWorksDW2012**, see [Microsoft SQL Server Product Samples: Reporting Services](https://archive.codeplex.com/?p=msftrsprodsamples).</span></span>  
  
## <a name="understanding-the-package-requirements"></a><span data-ttu-id="c3d0d-107">Descripción de los requisitos de paquete</span><span class="sxs-lookup"><span data-stu-id="c3d0d-107">Understanding the Package Requirements</span></span>  
 <span data-ttu-id="c3d0d-108">Este tutorial necesita Microsoft SQL Server Data Tools.</span><span class="sxs-lookup"><span data-stu-id="c3d0d-108">This tutorial requires Microsoft SQL Server Data Tools.</span></span>  
  
 <span data-ttu-id="c3d0d-109">Para obtener más información sobre cómo instalar SQL Server Data Tools, consulte [Descargar SQL Server Data Tools](https://docs.microsoft.com/sql/ssdt/download-sql-server-data-tools-ssdt?view=sql-server-2017).</span><span class="sxs-lookup"><span data-stu-id="c3d0d-109">For more information on installing the SQL Server Data Tools see [SQL Server Data Tools Download](https://docs.microsoft.com/sql/ssdt/download-sql-server-data-tools-ssdt?view=sql-server-2017).</span></span>  
  
 <span data-ttu-id="c3d0d-110">Antes de crear un paquete, debe saber qué formato se utiliza en los datos de origen y de destino.</span><span class="sxs-lookup"><span data-stu-id="c3d0d-110">Before creating a package, you need a good understanding of the formatting used in both the source data and the destination.</span></span> <span data-ttu-id="c3d0d-111">Una vez que conozca ambos formatos de datos, estará listo para definir las transformaciones necesarias para asignar los datos de origen al destino.</span><span class="sxs-lookup"><span data-stu-id="c3d0d-111">Once you understand both of these data formats, you will be ready to define the transformations necessary to map the source data to the destination.</span></span>  
  
### <a name="looking-at-the-source"></a><span data-ttu-id="c3d0d-112">Información sobre el origen</span><span class="sxs-lookup"><span data-stu-id="c3d0d-112">Looking at the Source</span></span>  
 <span data-ttu-id="c3d0d-113">En este tutorial, los datos de origen son un conjunto de datos de moneda históricos que se encuentra en el archivo plano SampleCurrencyData.txt.</span><span class="sxs-lookup"><span data-stu-id="c3d0d-113">For this tutorial, the source data is a set of historical currency data contained in the flat file, SampleCurrencyData.txt.</span></span> <span data-ttu-id="c3d0d-114">Los datos de origen tienen las cuatro columnas siguientes: tipo de cambio medio de la moneda, una clave de moneda, una clave de fecha y el tipo de cambio de final del día.</span><span class="sxs-lookup"><span data-stu-id="c3d0d-114">The source data has the following four columns: the average rate of the currency, a currency key, a date key, and the end-of-day rate.</span></span>  
  
 <span data-ttu-id="c3d0d-115">A continuación se muestra un ejemplo de datos de origen del archivo SampleCurrencyData.txt:</span><span class="sxs-lookup"><span data-stu-id="c3d0d-115">Here is an example of the source data contained in the SampleCurrencyData.txt file:</span></span>  
  
 `1.00070049USD9/3/05 0:001.001201442`  
  
 `1.00020004USD9/4/05 0:001`  
  
 `1.00020004USD9/5/05 0:001.001201442`  
  
 `1.00020004USD9/6/05 0:001`  
  
 `1.00020004USD9/7/05 0:001.00070049`  
  
 `1.00070049USD9/8/05 0:000.99980004`  
  
 `1.00070049USD9/9/05 0:001.001502253`  
  
 `1.00070049USD9/10/05 0:000.99990001`  
  
 `1.00020004USD9/11/05 0:001.001101211`  
  
 `1.00020004USD9/12/05 0:000.99970009`  
  
 <span data-ttu-id="c3d0d-116">Cuando se trabaja con datos de origen de un archivo plano, es importante entender el modo en que el administrador de conexiones de archivos planos interpreta los datos del archivo plano.</span><span class="sxs-lookup"><span data-stu-id="c3d0d-116">When working with flat file source data, it is important to understand how the Flat File connection manager interprets the flat file data.</span></span> <span data-ttu-id="c3d0d-117">Si el origen de archivo plano es Unicode, el administrador de conexiones de archivos planos define todas las columnas como [DT_WSTR], con un ancho de columna predeterminado de 50.</span><span class="sxs-lookup"><span data-stu-id="c3d0d-117">If the flat file source is Unicode, the Flat File connection manager defines all columns as [DT_WSTR] with a default column width of 50.</span></span> <span data-ttu-id="c3d0d-118">Si el origen de archivo plano tiene la codificación ANSI, las columnas se definen como [DT_STR], con un ancho de columna de 50.</span><span class="sxs-lookup"><span data-stu-id="c3d0d-118">If the flat file source is ANSI-encoded, the columns are defined as [DT_STR] with a column width of 50.</span></span> <span data-ttu-id="c3d0d-119">Es probable que tenga que cambiar estos valores predeterminados para que los tipos de columna de cadena sean más adecuados para los datos.</span><span class="sxs-lookup"><span data-stu-id="c3d0d-119">You will probably have to change these defaults to make the string column types more appropriate for your data.</span></span> <span data-ttu-id="c3d0d-120">Para ello, deberá saber cuál es el tipo de datos del destino en el que se escribirán los datos y luego elegir el tipo correcto dentro del administrador de conexiones de archivos planos.</span><span class="sxs-lookup"><span data-stu-id="c3d0d-120">To do this, you will need to look at the data type of the destination where the data will be written to and then choose the correct type within the Flat File connection manager.</span></span>  
  
### <a name="looking-at-the-destination"></a><span data-ttu-id="c3d0d-121">Información sobre el destino</span><span class="sxs-lookup"><span data-stu-id="c3d0d-121">Looking at the Destination</span></span>  
 <span data-ttu-id="c3d0d-122">El destino final de los datos de origen es la tabla de hechos **FactCurrency** de **AdventureWorksDW**.</span><span class="sxs-lookup"><span data-stu-id="c3d0d-122">The ultimate destination for the source data is the **FactCurrency** fact table in **AdventureWorksDW**.</span></span> <span data-ttu-id="c3d0d-123">La tabla de hechos **FactCurrency** tiene cuatro columnas y tiene relaciones con dos tablas de dimensiones, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="c3d0d-123">The **FactCurrency** fact table has four columns, and has relationships to two dimension tables, as shown in the following table.</span></span>  
  
|<span data-ttu-id="c3d0d-124">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="c3d0d-124">Column Name</span></span>|<span data-ttu-id="c3d0d-125">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="c3d0d-125">Data Type</span></span>|<span data-ttu-id="c3d0d-126">Tabla de búsqueda</span><span class="sxs-lookup"><span data-stu-id="c3d0d-126">Lookup Table</span></span>|<span data-ttu-id="c3d0d-127">columna de búsqueda</span><span class="sxs-lookup"><span data-stu-id="c3d0d-127">Lookup Column</span></span>|  
|-----------------|---------------|------------------|-------------------|  
|<span data-ttu-id="c3d0d-128">AverageRate</span><span class="sxs-lookup"><span data-stu-id="c3d0d-128">AverageRate</span></span>|<span data-ttu-id="c3d0d-129">FLOAT</span><span class="sxs-lookup"><span data-stu-id="c3d0d-129">float</span></span>|<span data-ttu-id="c3d0d-130">None</span><span class="sxs-lookup"><span data-stu-id="c3d0d-130">None</span></span>|<span data-ttu-id="c3d0d-131">None</span><span class="sxs-lookup"><span data-stu-id="c3d0d-131">None</span></span>|  
|<span data-ttu-id="c3d0d-132">CurrencyKey</span><span class="sxs-lookup"><span data-stu-id="c3d0d-132">CurrencyKey</span></span>|<span data-ttu-id="c3d0d-133">int (FK)</span><span class="sxs-lookup"><span data-stu-id="c3d0d-133">int (FK)</span></span>|<span data-ttu-id="c3d0d-134">DimCurrency</span><span class="sxs-lookup"><span data-stu-id="c3d0d-134">DimCurrency</span></span>|<span data-ttu-id="c3d0d-135">CurrencyKey (PK)</span><span class="sxs-lookup"><span data-stu-id="c3d0d-135">CurrencyKey (PK)</span></span>|  
|<span data-ttu-id="c3d0d-136">DateKey</span><span class="sxs-lookup"><span data-stu-id="c3d0d-136">DateKey</span></span>|<span data-ttu-id="c3d0d-137">int (FK)</span><span class="sxs-lookup"><span data-stu-id="c3d0d-137">Int (FK)</span></span>|<span data-ttu-id="c3d0d-138">DimDate</span><span class="sxs-lookup"><span data-stu-id="c3d0d-138">DimDate</span></span>|<span data-ttu-id="c3d0d-139">DateKey (PK)</span><span class="sxs-lookup"><span data-stu-id="c3d0d-139">DateKey (PK)</span></span>|  
|<span data-ttu-id="c3d0d-140">EndOfDayRate</span><span class="sxs-lookup"><span data-stu-id="c3d0d-140">EndOfDayRate</span></span>|<span data-ttu-id="c3d0d-141">FLOAT</span><span class="sxs-lookup"><span data-stu-id="c3d0d-141">float</span></span>|<span data-ttu-id="c3d0d-142">None</span><span class="sxs-lookup"><span data-stu-id="c3d0d-142">None</span></span>|<span data-ttu-id="c3d0d-143">None</span><span class="sxs-lookup"><span data-stu-id="c3d0d-143">None</span></span>|  
  
### <a name="mapping-source-data-to-be-compatible-with-the-destination"></a><span data-ttu-id="c3d0d-144">Asignar datos de origen para que sean compatibles con el destino</span><span class="sxs-lookup"><span data-stu-id="c3d0d-144">Mapping Source Data to be Compatible with the Destination</span></span>  
 <span data-ttu-id="c3d0d-145">El análisis de los formatos de datos de origen y de destino indica que serán necesarias búsquedas para los valores **CurrencyKey** y **DateKey** .</span><span class="sxs-lookup"><span data-stu-id="c3d0d-145">Analysis of the source and destination data formats indicates that lookups will be necessary for the **CurrencyKey** and **DateKey** values.</span></span> <span data-ttu-id="c3d0d-146">Las transformaciones que realizarán estas búsquedas obtendrán los valores de **CurrencyKey** y **DateKey** usando las claves alternativas de las tablas de dimensiones **DimCurrency** y **DimDate** .</span><span class="sxs-lookup"><span data-stu-id="c3d0d-146">The transformations that will perform these lookups will obtain the **CurrencyKey** and **DateKey** values by using the alternate keys from **DimCurrency** and **DimDate** dimension tables.</span></span>  
  
|<span data-ttu-id="c3d0d-147">Columna de archivo plano</span><span class="sxs-lookup"><span data-stu-id="c3d0d-147">Flat File Column</span></span>|<span data-ttu-id="c3d0d-148">Nombre de la tabla</span><span class="sxs-lookup"><span data-stu-id="c3d0d-148">Table Name</span></span>|<span data-ttu-id="c3d0d-149">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="c3d0d-149">Column Name</span></span>|<span data-ttu-id="c3d0d-150">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="c3d0d-150">Data Type</span></span>|  
|----------------------|----------------|-----------------|---------------|  
|<span data-ttu-id="c3d0d-151">0</span><span class="sxs-lookup"><span data-stu-id="c3d0d-151">0</span></span>|<span data-ttu-id="c3d0d-152">FactCurrency</span><span class="sxs-lookup"><span data-stu-id="c3d0d-152">FactCurrency</span></span>|<span data-ttu-id="c3d0d-153">AverageRate</span><span class="sxs-lookup"><span data-stu-id="c3d0d-153">AverageRate</span></span>|<span data-ttu-id="c3d0d-154">FLOAT</span><span class="sxs-lookup"><span data-stu-id="c3d0d-154">float</span></span>|  
|<span data-ttu-id="c3d0d-155">1</span><span class="sxs-lookup"><span data-stu-id="c3d0d-155">1</span></span>|<span data-ttu-id="c3d0d-156">DimCurrency</span><span class="sxs-lookup"><span data-stu-id="c3d0d-156">DimCurrency</span></span>|<span data-ttu-id="c3d0d-157">CurrencyAlternateKey</span><span class="sxs-lookup"><span data-stu-id="c3d0d-157">CurrencyAlternateKey</span></span>|<span data-ttu-id="c3d0d-158">nchar (3)</span><span class="sxs-lookup"><span data-stu-id="c3d0d-158">nchar (3)</span></span>|  
|<span data-ttu-id="c3d0d-159">2</span><span class="sxs-lookup"><span data-stu-id="c3d0d-159">2</span></span>|<span data-ttu-id="c3d0d-160">DimDate</span><span class="sxs-lookup"><span data-stu-id="c3d0d-160">DimDate</span></span>|<span data-ttu-id="c3d0d-161">FullDateAlternateKey</span><span class="sxs-lookup"><span data-stu-id="c3d0d-161">FullDateAlternateKey</span></span>|<span data-ttu-id="c3d0d-162">date</span><span class="sxs-lookup"><span data-stu-id="c3d0d-162">date</span></span>|  
|<span data-ttu-id="c3d0d-163">3</span><span class="sxs-lookup"><span data-stu-id="c3d0d-163">3</span></span>|<span data-ttu-id="c3d0d-164">FactCurrency</span><span class="sxs-lookup"><span data-stu-id="c3d0d-164">FactCurrency</span></span>|<span data-ttu-id="c3d0d-165">EndOfDayRate</span><span class="sxs-lookup"><span data-stu-id="c3d0d-165">EndOfDayRate</span></span>|<span data-ttu-id="c3d0d-166">FLOAT</span><span class="sxs-lookup"><span data-stu-id="c3d0d-166">float</span></span>|  
  
## <a name="lesson-tasks"></a><span data-ttu-id="c3d0d-167">Tareas de la lección</span><span class="sxs-lookup"><span data-stu-id="c3d0d-167">Lesson Tasks</span></span>  
 <span data-ttu-id="c3d0d-168">Esta lección contiene las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="c3d0d-168">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="c3d0d-169">Paso 1: Creación de un proyecto de Integration Services</span><span class="sxs-lookup"><span data-stu-id="c3d0d-169">Step 1: Creating a New Integration Services Project</span></span>](lesson-1-1-creating-a-new-integration-services-project.md)  
  
-   [<span data-ttu-id="c3d0d-170">Paso 2: Adición y configuración de un administrador de conexiones de archivos planos</span><span class="sxs-lookup"><span data-stu-id="c3d0d-170">Step 2: Adding and Configuring a Flat File Connection Manager</span></span>](lesson-1-2-adding-and-configuring-a-flat-file-connection-manager.md)  
  
-   [<span data-ttu-id="c3d0d-171">Paso 3: Adición y configuración de un administrador de conexiones OLE DB</span><span class="sxs-lookup"><span data-stu-id="c3d0d-171">Step 3: Adding and Configuring an OLE DB Connection Manager</span></span>](lesson-1-3-adding-and-configuring-an-ole-db-connection-manager.md)  
  
-   [<span data-ttu-id="c3d0d-172">Paso 4: Adición de una tarea Flujo de datos al paquete</span><span class="sxs-lookup"><span data-stu-id="c3d0d-172">Step 4: Adding a Data Flow Task to the Package</span></span>](lesson-1-4-adding-a-data-flow-task-to-the-package.md)  
  
-   [<span data-ttu-id="c3d0d-173">Paso 5: Adición y configuración del origen de archivo plano</span><span class="sxs-lookup"><span data-stu-id="c3d0d-173">Step 5: Adding and Configuring the Flat File Source</span></span>](lesson-1-5-adding-and-configuring-the-flat-file-source.md)  
  
-   [<span data-ttu-id="c3d0d-174">Paso 6: Adición y configuración de transformaciones de búsqueda</span><span class="sxs-lookup"><span data-stu-id="c3d0d-174">Step 6: Adding and Configuring the Lookup Transformations</span></span>](lesson-1-6-adding-and-configuring-the-lookup-transformations.md)  
  
-   [<span data-ttu-id="c3d0d-175">Paso 7: Adición y configuración del destino de OLE DB</span><span class="sxs-lookup"><span data-stu-id="c3d0d-175">Step 7: Adding and Configuring the OLE DB Destination</span></span>](lesson-1-7-adding-and-configuring-the-ole-db-destination.md)  
  
-   [<span data-ttu-id="c3d0d-176">Paso 8: Facilitar la comprensión del paquete de la lección 1</span><span class="sxs-lookup"><span data-stu-id="c3d0d-176">Step 8: Making the Lesson 1 Package Easier to Understand</span></span>](lesson-1-8-making-the-lesson-1-package-easier-to-understand.md)  
  
-   [<span data-ttu-id="c3d0d-177">Paso 9: Prueba del paquete del tutorial de la lección 1</span><span class="sxs-lookup"><span data-stu-id="c3d0d-177">Step 9: Testing the Lesson 1 Tutorial Package</span></span>](lesson-1-9-testing-the-lesson-1-tutorial-package.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="c3d0d-178">Iniciar la lección</span><span class="sxs-lookup"><span data-stu-id="c3d0d-178">Start the Lesson</span></span>  
 [<span data-ttu-id="c3d0d-179">Paso 1: Creación de un proyecto de Integration Services</span><span class="sxs-lookup"><span data-stu-id="c3d0d-179">Step 1: Creating a New Integration Services Project</span></span>](lesson-1-1-creating-a-new-integration-services-project.md)  
  
  
