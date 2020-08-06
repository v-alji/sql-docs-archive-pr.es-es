---
title: Editor de origen de OLE DB (página columnas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.oledbsourceadapter.columns.f1
helpviewer_keywords:
- OLE DB Source Editor
ms.assetid: bfbb0ae1-7759-4d45-8865-31df36ae5b34
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 575a5a02198606d2412ff187750963ccb171e338
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669752"
---
# <a name="ole-db-source-editor-columns-page"></a><span data-ttu-id="f58f2-102">Editor de origen de OLE DB (página Columnas)</span><span class="sxs-lookup"><span data-stu-id="f58f2-102">OLE DB Source Editor (Columns Page)</span></span>
  <span data-ttu-id="f58f2-103">Use la página **Columnas** del cuadro de diálogo **Editor de origen de OLE DB** para asignar una columna de salida a cada columna externa (origen).</span><span class="sxs-lookup"><span data-stu-id="f58f2-103">Use the **Columns** page of the **OLE DB Source Editor** dialog box to map an output column to each external (source) column.</span></span>  
  
 <span data-ttu-id="f58f2-104">Para obtener más información acerca del origen de OLE DB, vea [OLE DB Source](data-flow/ole-db-source.md).</span><span class="sxs-lookup"><span data-stu-id="f58f2-104">To learn more about the OLE DB source, see [OLE DB Source](data-flow/ole-db-source.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="f58f2-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="f58f2-105">Options</span></span>  
 <span data-ttu-id="f58f2-106">**Columnas externas disponibles**</span><span class="sxs-lookup"><span data-stu-id="f58f2-106">**Available External Columns**</span></span>  
 <span data-ttu-id="f58f2-107">Muestra la lista de columnas externas disponibles en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="f58f2-107">View the list of available external columns in the data source.</span></span> <span data-ttu-id="f58f2-108">Esta tabla no se puede usar para agregar o quitar columnas.</span><span class="sxs-lookup"><span data-stu-id="f58f2-108">You cannot use this table to add or delete columns.</span></span>  
  
 <span data-ttu-id="f58f2-109">**Columna externa**</span><span class="sxs-lookup"><span data-stu-id="f58f2-109">**External Column**</span></span>  
 <span data-ttu-id="f58f2-110">Muestra las columnas externas (origen) en el orden en que se verán cuando configure componentes que utilizan datos de este origen.</span><span class="sxs-lookup"><span data-stu-id="f58f2-110">View external (source) columns in the order in which you will see them when configuring components that consume data from this source.</span></span> <span data-ttu-id="f58f2-111">Puede cambiar este orden si elimina primero las columnas seleccionadas en la tabla y luego selecciona las columnas externas de la lista en un orden diferente.</span><span class="sxs-lookup"><span data-stu-id="f58f2-111">You can change this order by first clearing the selected columns in the table, and then selecting external columns from the list in a different order.</span></span>  
  
 <span data-ttu-id="f58f2-112">**Columna de salida**</span><span class="sxs-lookup"><span data-stu-id="f58f2-112">**Output Column**</span></span>  
 <span data-ttu-id="f58f2-113">Permite proporcionar un nombre único para cada columna de salida.</span><span class="sxs-lookup"><span data-stu-id="f58f2-113">Provide a unique name for each output column.</span></span> <span data-ttu-id="f58f2-114">El nombre predeterminado es el nombre de la columna externa (origen) seleccionada; sin embargo, puede elegir un nombre único y descriptivo.</span><span class="sxs-lookup"><span data-stu-id="f58f2-114">The default is the name of the selected external (source) column; however, you can choose any unique, descriptive name.</span></span> <span data-ttu-id="f58f2-115">El nombre que indique se mostrará en el Diseñador SSIS.</span><span class="sxs-lookup"><span data-stu-id="f58f2-115">The name provided will be displayed within the SSIS Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f58f2-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f58f2-116">See Also</span></span>  
 <span data-ttu-id="f58f2-117">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="f58f2-117">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="f58f2-118">[OLE DB Editor de origen &#40;página Administrador de conexiones&#41;](../../2014/integration-services/ole-db-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="f58f2-118">[OLE DB Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/ole-db-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="f58f2-119">[OLE DB Editor de origen &#40;página salida de error&#41;](../../2014/integration-services/ole-db-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="f58f2-119">[OLE DB Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/ole-db-source-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="f58f2-120">[Extraer datos mediante el origen de OLE DB](data-flow/extract-data-by-using-the-ole-db-source.md) </span><span class="sxs-lookup"><span data-stu-id="f58f2-120">[Extract Data by Using the OLE DB Source](data-flow/extract-data-by-using-the-ole-db-source.md) </span></span>  
 [<span data-ttu-id="f58f2-121">Administrador de conexiones OLE DB</span><span class="sxs-lookup"><span data-stu-id="f58f2-121">OLE DB Connection Manager</span></span>](connection-manager/ole-db-connection-manager.md)  
  
  
