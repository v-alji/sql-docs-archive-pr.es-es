---
title: Transformación Importar columna | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.importcolumntrans.f1
helpviewer_keywords:
- Import Column transformation [Integration Services]
- columns [Integration Services], importing
- importing data, SSIS packages
- inserting data
ms.assetid: ac3b74c1-ef54-4297-8062-1734324fffcc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f4330438614cce7892e74dc9a1dcbb6680b72972
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676095"
---
# <a name="import-column-transformation"></a><span data-ttu-id="d8603-102">Transformación Importar columna</span><span class="sxs-lookup"><span data-stu-id="d8603-102">Import Column Transformation</span></span>
  <span data-ttu-id="d8603-103">La transformación Importar columna lee datos de archivos y agrega los datos a columnas de un flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="d8603-103">The Import Column transformation reads data from files and adds the data to columns in a data flow.</span></span> <span data-ttu-id="d8603-104">Un paquete puede utilizar esta transformación para agregar texto e imágenes almacenadas en archivos distintos a un flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="d8603-104">Using this transformation, a package can add text and images stored in separate files to a data flow.</span></span> <span data-ttu-id="d8603-105">Por ejemplo, un flujo de datos que carga datos en una tabla que almacena información de productos puede incluir la transformación Importar columna para importar revisiones de clientes de cada producto desde archivos y agregar las revisiones al flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="d8603-105">For example, a data flow that loads data into a table that stores product information can include the Import Column transformation to import customer reviews of each product from files and add the reviews to the data flow.</span></span>  
  
 <span data-ttu-id="d8603-106">Puede configurar la transformación Importar columna de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="d8603-106">You can configure the Import Column transformation in the following ways:</span></span>  
  
-   <span data-ttu-id="d8603-107">Especificar las columnas a las que la transformación agrega datos.</span><span class="sxs-lookup"><span data-stu-id="d8603-107">Specify the columns to which the transformation adds data.</span></span>  
  
-   <span data-ttu-id="d8603-108">Especificar si la transformación debe esperar una marca de orden de bytes (BOM).</span><span class="sxs-lookup"><span data-stu-id="d8603-108">Specify whether the transformation expects a byte-order mark (BOM).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d8603-109">Solo se espera una marca BOM si los datos tienen el tipo de datos DT_NTEXT.</span><span class="sxs-lookup"><span data-stu-id="d8603-109">A BOM is only expected if the data has the DT_NTEXT data type.</span></span>  
  
 <span data-ttu-id="d8603-110">Una columna de la entrada de la transformación contiene los nombres de los archivos en los que están almacenados los datos.</span><span class="sxs-lookup"><span data-stu-id="d8603-110">A column in the transformation input contains the names of files that hold the data.</span></span> <span data-ttu-id="d8603-111">Cada fila del conjunto de datos puede especificar un archivo diferente.</span><span class="sxs-lookup"><span data-stu-id="d8603-111">Each row in the dataset can specify a different file.</span></span> <span data-ttu-id="d8603-112">Cuando la transformación Importar columna procesa una fila, lee el nombre del archivo, abre el archivo correspondiente en el sistema de archivos y carga su contenido en una columna de salida.</span><span class="sxs-lookup"><span data-stu-id="d8603-112">When the Import Column transformation processes a row, it reads the file name, opens the corresponding file in the file system, and loads the file content into an output column.</span></span> <span data-ttu-id="d8603-113">El tipo de datos de la columna de salida debe ser DT_TEXT, DT_NTEXT o DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="d8603-113">The data type of the output column must be DT_TEXT, DT_NTEXT, or DT_IMAGE.</span></span> <span data-ttu-id="d8603-114">Para obtener más información, vea [Integration Services Data Types](../integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="d8603-114">For more information, see [Integration Services Data Types](../integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="d8603-115">Esta transformación tiene una entrada, una salida y una salida de error.</span><span class="sxs-lookup"><span data-stu-id="d8603-115">This transformation has one input, one output, and one error output.</span></span>  
  
## <a name="configuration-of-the-import-column-transformation"></a><span data-ttu-id="d8603-116">Configuración de la transformación Importar columna</span><span class="sxs-lookup"><span data-stu-id="d8603-116">Configuration of the Import Column Transformation</span></span>  
 <span data-ttu-id="d8603-117">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="d8603-117">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="d8603-118">El cuadro de diálogo **Editor avanzado** indica las propiedades que se pueden establecer mediante programación.</span><span class="sxs-lookup"><span data-stu-id="d8603-118">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="d8603-119">Para obtener más información acerca de las propiedades que puede establecer a través del cuadro de diálogo **Editor avanzado** o mediante programación, haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="d8603-119">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="d8603-120">Common Properties</span><span class="sxs-lookup"><span data-stu-id="d8603-120">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="d8603-121">Propiedades personalizadas de transformación</span><span class="sxs-lookup"><span data-stu-id="d8603-121">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="d8603-122">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="d8603-122">Related Tasks</span></span>  
 <span data-ttu-id="d8603-123">Para más información sobre cómo establecer las propiedades de este componente, vea [Establecer las propiedades de un componente de flujo de datos](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="d8603-123">For information about how to set properties of this component, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8603-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d8603-124">See Also</span></span>  
 <span data-ttu-id="d8603-125">[Transformación Exportar columna](export-column-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="d8603-125">[Export Column Transformation](export-column-transformation.md) </span></span>  
 <span data-ttu-id="d8603-126">[Flujo de datos](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="d8603-126">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="d8603-127">Transformaciones de Integration Services</span><span class="sxs-lookup"><span data-stu-id="d8603-127">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
