---
title: Editor de origen de archivos planos (página columnas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.flatfilesourceadapter.columns.f1
helpviewer_keywords:
- Flat File Source Editor
ms.assetid: b5af5f65-c087-44fd-b5ae-d0441245fef2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9b0249b2b17d50fdef4b5cf4aff70a1318614257
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663613"
---
# <a name="flat-file-source-editor-columns-page"></a><span data-ttu-id="04270-102">Editor de origen de archivos planos (página Columnas)</span><span class="sxs-lookup"><span data-stu-id="04270-102">Flat File Source Editor (Columns Page)</span></span>
  <span data-ttu-id="04270-103">Use el nodo **Columnas** del cuadro de diálogo **Editor de origen de archivos planos** para asignar una columna de salida a cada columna externa (origen).</span><span class="sxs-lookup"><span data-stu-id="04270-103">Use the **Columns** node of the **Flat File Source Editor** dialog box to map an output column to each external (source) column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="04270-104">La `FileNameColumnName` propiedad del origen de archivo plano y la `FastParse` propiedad de sus columnas de salida no están disponibles en el **Editor de origen de archivos planos**, pero se pueden establecer mediante el **editor avanzado**.</span><span class="sxs-lookup"><span data-stu-id="04270-104">The `FileNameColumnName` property of the Flat File source and the `FastParse` property of its output columns are not available in the **Flat File Source Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="04270-105">Para obtener más información acerca de estas propiedades, vea la sección sobre el origen de archivos planos en [Flat File Custom Properties](data-flow/flat-file-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="04270-105">For more information on these properties, see the Flat File Source section of [Flat File Custom Properties](data-flow/flat-file-custom-properties.md).</span></span>  
  
 <span data-ttu-id="04270-106">Para obtener más información acerca del origen de archivo plano, vea [Flat File Source](data-flow/flat-file-source.md).</span><span class="sxs-lookup"><span data-stu-id="04270-106">To learn more about the Flat File source, see [Flat File Source](data-flow/flat-file-source.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="04270-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="04270-107">Options</span></span>  
 <span data-ttu-id="04270-108">**Columnas externas disponibles**</span><span class="sxs-lookup"><span data-stu-id="04270-108">**Available External Columns**</span></span>  
 <span data-ttu-id="04270-109">Muestra la lista de columnas externas disponibles en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="04270-109">View the list of available external columns in the data source.</span></span> <span data-ttu-id="04270-110">Esta tabla no se puede usar para agregar o quitar columnas.</span><span class="sxs-lookup"><span data-stu-id="04270-110">You cannot use this table to add or delete columns.</span></span>  
  
 <span data-ttu-id="04270-111">**Columna externa**</span><span class="sxs-lookup"><span data-stu-id="04270-111">**External Column**</span></span>  
 <span data-ttu-id="04270-112">Vea las columnas externas (origen) en el orden en que la tarea las leerá.</span><span class="sxs-lookup"><span data-stu-id="04270-112">View external (source) columns in the order in which the task will read them.</span></span> <span data-ttu-id="04270-113">Puede cambiar este orden si elimina primero las columnas seleccionadas en la tabla y luego selecciona las columnas externas de la lista en un orden diferente.</span><span class="sxs-lookup"><span data-stu-id="04270-113">You can change this order by first clearing the selected columns in the table, and then selecting external columns from the list in a different order.</span></span>  
  
 <span data-ttu-id="04270-114">**Columna de salida**</span><span class="sxs-lookup"><span data-stu-id="04270-114">**Output Column**</span></span>  
 <span data-ttu-id="04270-115">Permite proporcionar un nombre único para cada columna de salida.</span><span class="sxs-lookup"><span data-stu-id="04270-115">Provide a unique name for each output column.</span></span> <span data-ttu-id="04270-116">El nombre predeterminado es el nombre de la columna externa (origen) seleccionada; sin embargo, puede elegir un nombre único y descriptivo.</span><span class="sxs-lookup"><span data-stu-id="04270-116">The default is the name of the selected external (source) column; however, you can choose any unique, descriptive name.</span></span> <span data-ttu-id="04270-117">El nombre que indique se mostrará en el Diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="04270-117">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04270-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="04270-118">See Also</span></span>  
 <span data-ttu-id="04270-119">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="04270-119">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="04270-120">[Editor de origen de archivos planos &#40;página Administrador de conexiones&#41;](../../2014/integration-services/flat-file-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="04270-120">[Flat File Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/flat-file-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="04270-121">[Editor de origen de archivos planos &#40;página salida de error&#41;](../../2014/integration-services/flat-file-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="04270-121">[Flat File Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/flat-file-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="04270-122">Administrador de conexiones de archivos planos</span><span class="sxs-lookup"><span data-stu-id="04270-122">Flat File Connection Manager</span></span>](connection-manager/file-connection-manager.md)  
  
  
