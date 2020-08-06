---
title: Editor de transformación exportar columna (página columnas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fileextractortransformation.columns.f1
helpviewer_keywords:
- Export Column Transformation Editor
ms.assetid: b659a5c2-5509-4b5b-9c82-136c971d5c7f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 404b404e2328228049ae46fb1c3089b0b4089f0a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671116"
---
# <a name="export-column-transformation-editor-columns-page"></a><span data-ttu-id="a5eb1-102">Editor de transformación Exportar columna (página Columnas)</span><span class="sxs-lookup"><span data-stu-id="a5eb1-102">Export Column Transformation Editor (Columns Page)</span></span>
  <span data-ttu-id="a5eb1-103">Use la página **Columnas** del cuadro de diálogo **Editor de transformación Exportar columna** para especificar las columnas del flujo de datos que desea extraer a los archivos.</span><span class="sxs-lookup"><span data-stu-id="a5eb1-103">Use the **Columns** page of the **Export Column Transformation Editor** dialog box to specify columns in the data flow to extract to files.</span></span> <span data-ttu-id="a5eb1-104">Podrá especificar si desea que la transformación Exportar columna anexe los datos a un archivo o sobrescriba un archivo existente.</span><span class="sxs-lookup"><span data-stu-id="a5eb1-104">You can specify whether the Export Column transformation appends data to a file or overwrites an existing file.</span></span>  
  
 <span data-ttu-id="a5eb1-105">Para obtener más información acerca de la transformación Exportar columna, vea [Export Column Transformation](data-flow/transformations/export-column-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="a5eb1-105">To learn more about the Export Column transformation, see [Export Column Transformation](data-flow/transformations/export-column-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="a5eb1-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="a5eb1-106">Options</span></span>  
 <span data-ttu-id="a5eb1-107">**Columna Extraer**</span><span class="sxs-lookup"><span data-stu-id="a5eb1-107">**Extract Column**</span></span>  
 <span data-ttu-id="a5eb1-108">Seleccione de la lista las columnas de entrada que contengan datos de texto o imagen.</span><span class="sxs-lookup"><span data-stu-id="a5eb1-108">Select from the list of input columns that contain text or image data.</span></span> <span data-ttu-id="a5eb1-109">Todas las filas deben poseer definiciones para la **Columna Extraer** y la **Columna Ruta de archivo**.</span><span class="sxs-lookup"><span data-stu-id="a5eb1-109">All rows should have definitions for **Extract Column** and **File Path Column**.</span></span>  
  
 <span data-ttu-id="a5eb1-110">**Columna Ruta de archivo**</span><span class="sxs-lookup"><span data-stu-id="a5eb1-110">**File Path Column**</span></span>  
 <span data-ttu-id="a5eb1-111">Seleccione de la lista las columnas de entrada que contengan rutas de archivo y nombres de archivo.</span><span class="sxs-lookup"><span data-stu-id="a5eb1-111">Select from the list of input columns that contain file paths and file names.</span></span> <span data-ttu-id="a5eb1-112">Todas las filas deben poseer definiciones para la **Columna Extraer** y la **Columna Ruta de archivo**.</span><span class="sxs-lookup"><span data-stu-id="a5eb1-112">All rows should have definitions for **Extract Column** and **File Path Column**.</span></span>  
  
 <span data-ttu-id="a5eb1-113">**Permitir la anexión**</span><span class="sxs-lookup"><span data-stu-id="a5eb1-113">**Allow Append**</span></span>  
 <span data-ttu-id="a5eb1-114">Especifique si desea que la transformación anexe los datos a los archivos existentes.</span><span class="sxs-lookup"><span data-stu-id="a5eb1-114">Specify whether the transformation appends data to existing files.</span></span> <span data-ttu-id="a5eb1-115">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="a5eb1-115">The default is `false`.</span></span>  
  
 <span data-ttu-id="a5eb1-116">**Forzar el truncamiento**</span><span class="sxs-lookup"><span data-stu-id="a5eb1-116">**Force Truncate**</span></span>  
 <span data-ttu-id="a5eb1-117">Especifique si desea que la transformación elimine el contenido de los archivos existentes antes de escribir los datos.</span><span class="sxs-lookup"><span data-stu-id="a5eb1-117">Specify whether the transformation deletes the contents of existing files before writing data.</span></span> <span data-ttu-id="a5eb1-118">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="a5eb1-118">The default is `false`.</span></span>  
  
 <span data-ttu-id="a5eb1-119">**BOM de escritura**</span><span class="sxs-lookup"><span data-stu-id="a5eb1-119">**Write BOM**</span></span>  
 <span data-ttu-id="a5eb1-120">Especifique si desea escribir una marca de orden de bytes (BOM) en el archivo.</span><span class="sxs-lookup"><span data-stu-id="a5eb1-120">Specify whether to write a byte-order mark (BOM) to the file.</span></span> <span data-ttu-id="a5eb1-121">Solo se escribirá una BOM si los datos poseen el tipo de datos `DT_NTEXT` o DT_WSTR y no están anexados a un archivo de datos existente.</span><span class="sxs-lookup"><span data-stu-id="a5eb1-121">A BOM is only written if the data has the `DT_NTEXT` or DT_WSTR data type and is not appended to an existing data file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5eb1-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a5eb1-122">See Also</span></span>  
 <span data-ttu-id="a5eb1-123">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="a5eb1-123">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="a5eb1-124">Editor de transformación Exportar columna &#40;página Salida de error&#41;</span><span class="sxs-lookup"><span data-stu-id="a5eb1-124">Export Column Transformation Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/export-column-transformation-editor-error-output-page.md)  
  
  
