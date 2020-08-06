---
title: Editor de origen de Excel (página columnas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.excelsourceadapter.columns.f1
helpviewer_keywords:
- Excel Source Editor
ms.assetid: 50024686-a18d-4824-b20e-c84123f89d0b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0713d8d3d0c1f56bf322684a924a286e8b81af55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673791"
---
# <a name="excel-source-editor-columns-page"></a><span data-ttu-id="07e56-102">Editor de origen de Excel (página Columnas)</span><span class="sxs-lookup"><span data-stu-id="07e56-102">Excel Source Editor (Columns Page)</span></span>
  <span data-ttu-id="07e56-103">Use la página **Columnas** del cuadro de diálogo **Editor de origen de Excel** para asignar una columna de salida a cada columna externa (origen).</span><span class="sxs-lookup"><span data-stu-id="07e56-103">Use the **Columns** page of the **Excel Source Editor** dialog box to map an output column to each external (source) column.</span></span>  
  
 <span data-ttu-id="07e56-104">Para obtener más información acerca del origen de Excel, vea [Excel Source](data-flow/excel-source.md).</span><span class="sxs-lookup"><span data-stu-id="07e56-104">To learn more about the Excel source, see [Excel Source](data-flow/excel-source.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="07e56-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="07e56-105">Options</span></span>  
 <span data-ttu-id="07e56-106">**Columnas externas disponibles**</span><span class="sxs-lookup"><span data-stu-id="07e56-106">**Available External Columns**</span></span>  
 <span data-ttu-id="07e56-107">Muestra la lista de columnas externas disponibles en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="07e56-107">View the list of available external columns in the data source.</span></span> <span data-ttu-id="07e56-108">Esta tabla no se puede usar para agregar o quitar columnas.</span><span class="sxs-lookup"><span data-stu-id="07e56-108">You cannot use this table to add or delete columns.</span></span>  
  
 <span data-ttu-id="07e56-109">**Columna externa**</span><span class="sxs-lookup"><span data-stu-id="07e56-109">**External Column**</span></span>  
 <span data-ttu-id="07e56-110">Vea las columnas externas (origen) en el orden en que la tarea las leerá.</span><span class="sxs-lookup"><span data-stu-id="07e56-110">View external (source) columns in the order in which the task will read them.</span></span> <span data-ttu-id="07e56-111">Puede cambiar este orden si elimina primero las columnas seleccionadas en la tabla anterior y luego selecciona las columnas externas de la lista en un orden diferente.</span><span class="sxs-lookup"><span data-stu-id="07e56-111">You can change this order by first clearing the selected columns in the table discussed above, and then selecting external columns from the list in a different order.</span></span>  
  
 <span data-ttu-id="07e56-112">**Columna de salida**</span><span class="sxs-lookup"><span data-stu-id="07e56-112">**Output Column**</span></span>  
 <span data-ttu-id="07e56-113">Permite proporcionar un nombre único para cada columna de salida.</span><span class="sxs-lookup"><span data-stu-id="07e56-113">Provide a unique name for each output column.</span></span> <span data-ttu-id="07e56-114">El nombre predeterminado es el nombre de la columna externa (origen) seleccionada; sin embargo, puede elegir un nombre único y descriptivo.</span><span class="sxs-lookup"><span data-stu-id="07e56-114">The default is the name of the selected external (source) column; however, you can choose any unique, descriptive name.</span></span> <span data-ttu-id="07e56-115">El nombre que indique se mostrará en el Diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="07e56-115">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07e56-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="07e56-116">See Also</span></span>  
 <span data-ttu-id="07e56-117">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="07e56-117">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="07e56-118">[Editor de origen de Excel &#40;página Administrador de conexiones&#41;](../../2014/integration-services/excel-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="07e56-118">[Excel Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/excel-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="07e56-119">[Editor de origen de Excel &#40;página salida de error&#41;](../../2014/integration-services/excel-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="07e56-119">[Excel Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/excel-source-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="07e56-120">[Administrador de conexiones con Excel](connection-manager/excel-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="07e56-120">[Excel Connection Manager](connection-manager/excel-connection-manager.md) </span></span>  
 [<span data-ttu-id="07e56-121">Crear bucles entre archivos y tablas de Excel mediante un contenedor de bucles ForEach</span><span class="sxs-lookup"><span data-stu-id="07e56-121">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](control-flow/foreach-loop-container.md)  
  
  
