---
title: Editor de origen de Excel (página salida de error) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.excelsourceadapter.erroroutput.f1
helpviewer_keywords:
- Excel Source Editor
ms.assetid: 8d14019e-cb60-4bc1-b71e-7f2326de8317
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 37b2291844aa690cfe4cd412a14569057adb9e85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673789"
---
# <a name="excel-source-editor-error-output-page"></a><span data-ttu-id="a1aec-102">Editor de origen de Excel (página Salida de error)</span><span class="sxs-lookup"><span data-stu-id="a1aec-102">Excel Source Editor (Error Output Page)</span></span>
  <span data-ttu-id="a1aec-103">Utilice la página **Salida de error** del cuadro de diálogo **Editor de origen de Excel** para seleccionar opciones de control de errores y establecer las propiedades en las columnas de salida de errores.</span><span class="sxs-lookup"><span data-stu-id="a1aec-103">Use the **Error Output** page of the **Excel Source Editor** dialog box to select error handling options and to set properties on error output columns.</span></span>  
  
 <span data-ttu-id="a1aec-104">Para obtener más información acerca del origen de Excel, vea [Excel Source](data-flow/excel-source.md).</span><span class="sxs-lookup"><span data-stu-id="a1aec-104">To learn more about the Excel source, see [Excel Source](data-flow/excel-source.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="a1aec-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="a1aec-105">Options</span></span>  
 <span data-ttu-id="a1aec-106">**Entrada o salida**</span><span class="sxs-lookup"><span data-stu-id="a1aec-106">**Input or Output**</span></span>  
 <span data-ttu-id="a1aec-107">Muestra el nombre del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="a1aec-107">View the name of the data source.</span></span>  
  
 <span data-ttu-id="a1aec-108">**Columna**</span><span class="sxs-lookup"><span data-stu-id="a1aec-108">**Column**</span></span>  
 <span data-ttu-id="a1aec-109">Permite ver las columnas externas (origen) seleccionadas en la página **Administrador de conexiones** del cuadro de diálogo **Editor de origen de Excel**.</span><span class="sxs-lookup"><span data-stu-id="a1aec-109">View the external (source) columns that you selected on the **Connection Manager** page of the **Excel Source Editor**dialog box.</span></span>  
  
 <span data-ttu-id="a1aec-110">**Error**</span><span class="sxs-lookup"><span data-stu-id="a1aec-110">**Error**</span></span>  
 <span data-ttu-id="a1aec-111">Permite especificar qué debe ocurrir cuando se produce un error: omitir el error, redirigir la fila o hacer que el componente no funcione.</span><span class="sxs-lookup"><span data-stu-id="a1aec-111">Specify what should happen when an error occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="a1aec-112">**Temas relacionados:** [Control de errores en los datos](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="a1aec-112">**Related Topics:** [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>  
  
 <span data-ttu-id="a1aec-113">**Truncamiento**</span><span class="sxs-lookup"><span data-stu-id="a1aec-113">**Truncation**</span></span>  
 <span data-ttu-id="a1aec-114">Permite especificar qué debe ocurrir cuando se produce un truncamiento: omitir el error, redirigir la fila o hacer que el componente no funcione.</span><span class="sxs-lookup"><span data-stu-id="a1aec-114">Specify what should happen when a truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="a1aec-115">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a1aec-115">**Description**</span></span>  
 <span data-ttu-id="a1aec-116">Muestra la descripción del error.</span><span class="sxs-lookup"><span data-stu-id="a1aec-116">View the description of the error.</span></span>  
  
 <span data-ttu-id="a1aec-117">**Establecer este valor en las celdas seleccionadas**</span><span class="sxs-lookup"><span data-stu-id="a1aec-117">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="a1aec-118">Permite especificar qué debe ocurrir en todas las celdas seleccionadas cuando se produce un error o un truncamiento: omitir el error, redirigir la fila o hacer que el componente no funcione.</span><span class="sxs-lookup"><span data-stu-id="a1aec-118">Specify what should happen to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="a1aec-119">**Aplicar**</span><span class="sxs-lookup"><span data-stu-id="a1aec-119">**Apply**</span></span>  
 <span data-ttu-id="a1aec-120">Aplica la opción de control de errores a las celdas seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="a1aec-120">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1aec-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a1aec-121">See Also</span></span>  
 <span data-ttu-id="a1aec-122">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="a1aec-122">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="a1aec-123">[Editor de origen de Excel &#40;página Administrador de conexiones&#41;](../../2014/integration-services/excel-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="a1aec-123">[Excel Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/excel-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="a1aec-124">[Editor de origen de Excel &#40;página columnas&#41;](../../2014/integration-services/excel-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="a1aec-124">[Excel Source Editor &#40;Columns Page&#41;](../../2014/integration-services/excel-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="a1aec-125">[Administrador de conexiones con Excel](connection-manager/excel-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="a1aec-125">[Excel Connection Manager](connection-manager/excel-connection-manager.md) </span></span>  
 [<span data-ttu-id="a1aec-126">Crear bucles entre archivos y tablas de Excel mediante un contenedor de bucles ForEach</span><span class="sxs-lookup"><span data-stu-id="a1aec-126">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](control-flow/foreach-loop-container.md)  
  
  
