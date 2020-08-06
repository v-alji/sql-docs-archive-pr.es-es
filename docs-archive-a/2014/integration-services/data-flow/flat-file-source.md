---
title: Origen de archivo plano | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.flatfilesource.f1
helpviewer_keywords:
- sources [Integration Services], Flat File
- text file reading [Integration Services]
- flat files
- Flat File source
ms.assetid: 4a64f7f3-f25d-4db0-93b3-a29496030e58
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b1ca0f38c457256b3f2ed2ddb81bfbd0dc06b6c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751314"
---
# <a name="flat-file-source"></a><span data-ttu-id="f1487-102">origen de archivo plano</span><span class="sxs-lookup"><span data-stu-id="f1487-102">Flat File Source</span></span>
  <span data-ttu-id="f1487-103">El origen de archivo plano lee datos de un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="f1487-103">The Flat File source reads data from a text file.</span></span> <span data-ttu-id="f1487-104">El archivo de texto puede tener formato delimitado, de ancho fijo o mixto.</span><span class="sxs-lookup"><span data-stu-id="f1487-104">The text file can be in delimited, fixed width, or mixed format.</span></span>  
  
-   <span data-ttu-id="f1487-105">El formato delimitado utiliza columna y delimitadores de filas para definir columnas y filas.</span><span class="sxs-lookup"><span data-stu-id="f1487-105">Delimited format uses column and row delimiters to define columns and rows.</span></span>  
  
-   <span data-ttu-id="f1487-106">El formato de ancho fijo utiliza el ancho para definir columnas y filas.</span><span class="sxs-lookup"><span data-stu-id="f1487-106">Fixed width format uses width to define columns and rows.</span></span> <span data-ttu-id="f1487-107">Este formato también incluye un carácter para rellenar los campos hasta alcanzar el ancho máximo.</span><span class="sxs-lookup"><span data-stu-id="f1487-107">This format also includes a character for padding fields to their maximum width.</span></span>  
  
-   <span data-ttu-id="f1487-108">El formato derecho irregular utiliza el ancho para definir todas las columnas, excepto la última, que se delimita mediante el delimitador de filas.</span><span class="sxs-lookup"><span data-stu-id="f1487-108">Ragged right format uses width to define all columns, except for the last column, which is delimited by the row delimiter.</span></span>  
  
 <span data-ttu-id="f1487-109">Puede configurar el origen de archivo plano de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="f1487-109">You can configure the Flat File source in the following ways:</span></span>  
  
-   <span data-ttu-id="f1487-110">Agregue una columna a la salida de transformación que contiene el nombre del archivo de texto del que el origen de archivo plano extrae datos.</span><span class="sxs-lookup"><span data-stu-id="f1487-110">Add a column to the transformation output that contains the name of the text file from which the Flat File source extracts data.</span></span>  
  
-   <span data-ttu-id="f1487-111">Especifique si el origen de archivo plano interpreta las cadenas de longitud cero de las columnas como valores NULL.</span><span class="sxs-lookup"><span data-stu-id="f1487-111">Specify whether the Flat File source interprets zero-length strings in columns as null values.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f1487-112">El administrador de conexiones de archivos planos utilizado por el origen de archivo plano debe configurarse para usar un formato delimitado a fin de interpretar cadenas de longitud cero como valores NULL.</span><span class="sxs-lookup"><span data-stu-id="f1487-112">The Flat File connection manager that the Flat File source uses must be configured to use a delimited format to interpret zero-length strings as nulls.</span></span> <span data-ttu-id="f1487-113">Si el administrador de conexiones utiliza los formatos de ancho fijo o derecho irregular, los datos que estén formados por espacios no se podrán interpretar como valores NULL.</span><span class="sxs-lookup"><span data-stu-id="f1487-113">If the connection manager uses the fixed width or ragged right formats, data that consists of spaces cannot be interpreted as null values.</span></span>  
  
 <span data-ttu-id="f1487-114">Las columnas de salida en la salida del origen de archivo plano incluyen la propiedad FastParse.</span><span class="sxs-lookup"><span data-stu-id="f1487-114">The output columns in the output of the Flat File source include the FastParse property.</span></span> <span data-ttu-id="f1487-115">FastParse indica si la columna usa las rutinas de análisis más rápidas que no distinguen la configuración regional y permiten un análisis rápido que [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] proporciona, o las rutinas de análisis estándar que sí distinguen la configuración regional.</span><span class="sxs-lookup"><span data-stu-id="f1487-115">FastParse indicates whether the column uses the quicker, but locale-insensitive, fast parsing routines that [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] provides or the locale-sensitive standard parsing routines.</span></span> <span data-ttu-id="f1487-116">Para obtener más información, consulte [Fast Parse](../fast-parse.md) y [Standard Parse](../standard-parse.md).</span><span class="sxs-lookup"><span data-stu-id="f1487-116">For more information, see [Fast Parse](../fast-parse.md) and [Standard Parse](../standard-parse.md).</span></span>  
  
 <span data-ttu-id="f1487-117">Las columnas de salida también incluyen la propiedad UseBinaryFormat.</span><span class="sxs-lookup"><span data-stu-id="f1487-117">Output columns also include the UseBinaryFormat property.</span></span> <span data-ttu-id="f1487-118">Esta propiedad se usa para implementar en archivos la compatibilidad con datos binarios, como los datos con formato decimal.</span><span class="sxs-lookup"><span data-stu-id="f1487-118">You use this property to implement support for binary data, such as data with the packed decimal format, in files.</span></span> <span data-ttu-id="f1487-119">De forma predeterminada, UseBinaryFormat se establece en `false` .</span><span class="sxs-lookup"><span data-stu-id="f1487-119">By default UseBinaryFormat is set to `false`.</span></span> <span data-ttu-id="f1487-120">Si desea utilizar un formato binario, establezca UseBinaryFormat en `true` y el tipo de datos de la columna de salida en `DT_BYTES` .</span><span class="sxs-lookup"><span data-stu-id="f1487-120">If you want to use a binary format, set UseBinaryFormat to `true` and the data type on the output column to `DT_BYTES`.</span></span> <span data-ttu-id="f1487-121">Al hacer esto, el origen de archivos planos omite la conversión de los datos y los pasa a la columna de salida tal y como están.</span><span class="sxs-lookup"><span data-stu-id="f1487-121">When you do this, the Flat File source skips the data conversion and passes the data to the output column as is.</span></span> <span data-ttu-id="f1487-122">A continuación, se puede usar una transformación como Columna derivada o Conversión de datos para convertir los datos `DT_BYTES` en otro tipo de datos; también se puede escribir un script personalizado en una transformación de script para interpretar los datos.</span><span class="sxs-lookup"><span data-stu-id="f1487-122">You can then use a transformation such as the Derived Column or Data Conversion to cast the `DT_BYTES` data to a different data type, or you can write custom script in a Script transformation to interpret the data.</span></span> <span data-ttu-id="f1487-123">Por último, también se puede escribir un componente de flujo de datos personalizado que interprete los datos.</span><span class="sxs-lookup"><span data-stu-id="f1487-123">You can also write a custom data flow component to interpret the data.</span></span> <span data-ttu-id="f1487-124">Para obtener más información sobre los tipos de datos a los que se puede convertir `DT_BYTES` , consulte [Cast &#40;SSIS Expression&#41;](../expressions/cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="f1487-124">For more information about which data types you can cast `DT_BYTES` to, see [Cast &#40;SSIS Expression&#41;](../expressions/cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="f1487-125">Este origen utiliza un administrador de conexiones de archivos planos para tener acceso al archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="f1487-125">This source uses a Flat File connection manager to access the text file.</span></span> <span data-ttu-id="f1487-126">Si establece las propiedades del administrador de conexiones de archivos planos, puede proporcionar información sobre el archivo y cada columna que contiene, y especificar cómo debe controlar el origen de archivo plano los datos del archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="f1487-126">By setting properties on the Flat File connection manager, you can provide information about the file and each column in it, and specify how the Flat File source should handle the data in the text file.</span></span> <span data-ttu-id="f1487-127">Por ejemplo, puede especificar los caracteres que delimitan columnas y filas en el archivo, así como el tipo de datos y la longitud de cada columna.</span><span class="sxs-lookup"><span data-stu-id="f1487-127">For example, you can specify the characters that delimit columns and rows in the file, and the data type and the length of each column.</span></span> <span data-ttu-id="f1487-128">Para más información, consulte [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="f1487-128">For more information, see [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span></span>  
  
 <span data-ttu-id="f1487-129">Este origen tiene una salida y una salida de error.</span><span class="sxs-lookup"><span data-stu-id="f1487-129">This source has one output and one error output.</span></span>  
  
## <a name="configuration-of-the-flat-file-source"></a><span data-ttu-id="f1487-130">Configuración del origen de archivo plano</span><span class="sxs-lookup"><span data-stu-id="f1487-130">Configuration of the Flat File Source</span></span>  
 <span data-ttu-id="f1487-131">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="f1487-131">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="f1487-132">Para obtener más información acerca de las propiedades que puede establecer en el cuadro de diálogo **Editor de origen de archivos planos** , haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="f1487-132">For more information about the properties that you can set in the **Flat File Source Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="f1487-133">Editor de origen de archivos planos &#40;página Administrador de conexiones&#41;</span><span class="sxs-lookup"><span data-stu-id="f1487-133">Flat File Source Editor &#40;Connection Manager Page&#41;</span></span>](../flat-file-source-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="f1487-134">Editor de origen de archivos planos &#40;página Columnas&#41;</span><span class="sxs-lookup"><span data-stu-id="f1487-134">Flat File Source Editor &#40;Columns Page&#41;</span></span>](../flat-file-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="f1487-135">Editor de origen de archivos planos &#40;página Salida de error&#41;</span><span class="sxs-lookup"><span data-stu-id="f1487-135">Flat File Source Editor &#40;Error Output Page&#41;</span></span>](../flat-file-source-editor-error-output-page.md)  
  
 <span data-ttu-id="f1487-136">El cuadro de diálogo **Editor avanzado** indica las propiedades que se pueden establecer mediante programación.</span><span class="sxs-lookup"><span data-stu-id="f1487-136">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="f1487-137">Para obtener más información acerca de las propiedades que puede establecer a través del cuadro de diálogo **Editor avanzado** o mediante programación, haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="f1487-137">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="f1487-138">Common Properties</span><span class="sxs-lookup"><span data-stu-id="f1487-138">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="f1487-139">Propiedades personalizadas de archivo plano</span><span class="sxs-lookup"><span data-stu-id="f1487-139">Flat File Custom Properties</span></span>](flat-file-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="f1487-140">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="f1487-140">Related Tasks</span></span>  
 <span data-ttu-id="f1487-141">Para obtener más detalles sobre cómo establecer las propiedades de un componente de flujo de datos, vea [Establecer las propiedades de un componente de flujo de datos](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="f1487-141">For details about how to set properties of a data flow component, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1487-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f1487-142">See Also</span></span>  
 <span data-ttu-id="f1487-143">[Destino de archivo plano](flat-file-destination.md) </span><span class="sxs-lookup"><span data-stu-id="f1487-143">[Flat File Destination](flat-file-destination.md) </span></span>  
 [<span data-ttu-id="f1487-144">Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="f1487-144">Data Flow</span></span>](data-flow.md)  
  
  
