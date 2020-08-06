---
title: Editor de origen de OLE DB (página salida de error) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.oledbsourceadapter.errorhandling.f1
helpviewer_keywords:
- OLE DB Source Editor
ms.assetid: 7737c6ae-c16b-4856-aa6e-5882640093b7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ded87747f041a4d8451048d4ef4671b029125873
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676584"
---
# <a name="ole-db-source-editor-error-output-page"></a><span data-ttu-id="2afce-102">Editor de origen de OLE DB (página Salida de error)</span><span class="sxs-lookup"><span data-stu-id="2afce-102">OLE DB Source Editor (Error Output Page)</span></span>
  <span data-ttu-id="2afce-103">Utilice la página **Salida de error** del cuadro de diálogo **Editor de origen de OLE DB** para seleccionar opciones de control de errores y establecer propiedades en columnas de salida de errores.</span><span class="sxs-lookup"><span data-stu-id="2afce-103">Use the **Error Output** page of the **OLE DB Source Editor** dialog box to select error handling options and to set properties on error output columns.</span></span>  
  
 <span data-ttu-id="2afce-104">Para obtener más información acerca del origen de OLE DB, vea [OLE DB Source](data-flow/ole-db-source.md).</span><span class="sxs-lookup"><span data-stu-id="2afce-104">To learn more about the OLE DB source, see [OLE DB Source](data-flow/ole-db-source.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="2afce-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="2afce-105">Options</span></span>  
 <span data-ttu-id="2afce-106">**Entrada/salida**</span><span class="sxs-lookup"><span data-stu-id="2afce-106">**Input/Output**</span></span>  
 <span data-ttu-id="2afce-107">Muestra el nombre del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="2afce-107">View the name of the data source.</span></span>  
  
 <span data-ttu-id="2afce-108">**Columna**</span><span class="sxs-lookup"><span data-stu-id="2afce-108">**Column**</span></span>  
 <span data-ttu-id="2afce-109">Muestra las columnas externas (origen) que se han seleccionado en la página **Administrador de conexiones** del cuadro de diálogo **Editor de origen de OLE DB**.</span><span class="sxs-lookup"><span data-stu-id="2afce-109">View the external (source) columns that you selected on the **Connection Manager** page of the **OLE DB Source Editor**dialog box.</span></span>  
  
 <span data-ttu-id="2afce-110">**Error**</span><span class="sxs-lookup"><span data-stu-id="2afce-110">**Error**</span></span>  
 <span data-ttu-id="2afce-111">Permite especificar qué debe ocurrir cuando se produce un error: omitir el error, redirigir la fila o hacer que el componente no funcione.</span><span class="sxs-lookup"><span data-stu-id="2afce-111">Specify what should happen when an error occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="2afce-112">**Temas relacionados:** [Control de errores en los datos](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="2afce-112">**Related Topics:** [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>  
  
 <span data-ttu-id="2afce-113">**Truncamiento**</span><span class="sxs-lookup"><span data-stu-id="2afce-113">**Truncation**</span></span>  
 <span data-ttu-id="2afce-114">Permite especificar qué debe ocurrir cuando se produce un truncamiento: omitir el error, redirigir la fila o hacer que el componente no funcione.</span><span class="sxs-lookup"><span data-stu-id="2afce-114">Specify what should happen when a truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="2afce-115">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="2afce-115">**Description**</span></span>  
 <span data-ttu-id="2afce-116">Muestra la descripción del error.</span><span class="sxs-lookup"><span data-stu-id="2afce-116">View the description of the error.</span></span>  
  
 <span data-ttu-id="2afce-117">**Establecer este valor en las celdas seleccionadas**</span><span class="sxs-lookup"><span data-stu-id="2afce-117">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="2afce-118">Permite especificar qué debe ocurrir en todas las celdas seleccionadas cuando se produce un error o un truncamiento: omitir el error, redirigir la fila o hacer que el componente no funcione.</span><span class="sxs-lookup"><span data-stu-id="2afce-118">Specify what should happen to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="2afce-119">**Aplicar**</span><span class="sxs-lookup"><span data-stu-id="2afce-119">**Apply**</span></span>  
 <span data-ttu-id="2afce-120">Aplica la opción de control de errores a las celdas seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="2afce-120">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2afce-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2afce-121">See Also</span></span>  
 <span data-ttu-id="2afce-122">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="2afce-122">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="2afce-123">[OLE DB Editor de origen &#40;página Administrador de conexiones&#41;](../../2014/integration-services/ole-db-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="2afce-123">[OLE DB Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/ole-db-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="2afce-124">[&#40;página columnas del editor de origen de OLE DB&#41;](../../2014/integration-services/ole-db-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="2afce-124">[OLE DB Source Editor &#40;Columns Page&#41;](../../2014/integration-services/ole-db-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="2afce-125">[Extraer datos mediante el origen de OLE DB](data-flow/extract-data-by-using-the-ole-db-source.md) </span><span class="sxs-lookup"><span data-stu-id="2afce-125">[Extract Data by Using the OLE DB Source](data-flow/extract-data-by-using-the-ole-db-source.md) </span></span>  
 [<span data-ttu-id="2afce-126">Administrador de conexiones OLE DB</span><span class="sxs-lookup"><span data-stu-id="2afce-126">OLE DB Connection Manager</span></span>](connection-manager/ole-db-connection-manager.md)  
  
  
