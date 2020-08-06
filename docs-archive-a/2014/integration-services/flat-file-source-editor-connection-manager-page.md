---
title: Editor de origen de archivos planos (página Administrador de conexiones) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.flatfilesourceadapter.connection.f1
helpviewer_keywords:
- Flat File Source Editor
ms.assetid: 2efd6baa-ed75-4f3f-b667-514024cebdb8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 03c1693c001dad2c8e90211b065eda208c42a07b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663609"
---
# <a name="flat-file-source-editor-connection-manager-page"></a><span data-ttu-id="c8d27-102">Editor de origen de archivos planos (página Administrador de conexiones)</span><span class="sxs-lookup"><span data-stu-id="c8d27-102">Flat File Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="c8d27-103">Utilice la página **Administrador de conexiones** del cuadro de diálogo **Editor de origen de archivos planos** para seleccionar el administrador de conexiones que utilizará el origen de archivos planos.</span><span class="sxs-lookup"><span data-stu-id="c8d27-103">Use the **Connection Manager** page of the **Flat File Source Editor** dialog box to select the connection manager that the Flat File source will use.</span></span> <span data-ttu-id="c8d27-104">El origen de archivos planos lee los datos de un archivo de texto, que pueden estar en formato delimitado, tener un ancho fijo o ser mixtos.</span><span class="sxs-lookup"><span data-stu-id="c8d27-104">The Flat File source reads data from a text file, which can be in a delimited, fixed width, or mixed format.</span></span>  
  
 <span data-ttu-id="c8d27-105">Un origen de archivos planos puede utilizar uno de los siguientes tipos de administradores de conexiones:</span><span class="sxs-lookup"><span data-stu-id="c8d27-105">A Flat File source can use one of the following types of connection managers:</span></span>  
  
-   <span data-ttu-id="c8d27-106">Un administrador de conexiones de archivos planos, si el origen es un único archivo plano.</span><span class="sxs-lookup"><span data-stu-id="c8d27-106">A Flat File connection manager if the source is a single flat file.</span></span> <span data-ttu-id="c8d27-107">Para más información, consulte [Flat File Connection Manager](connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="c8d27-107">For more information, see [Flat File Connection Manager](connection-manager/file-connection-manager.md).</span></span>  
  
-   <span data-ttu-id="c8d27-108">Un administrador de conexiones de varios archivos planos, si el origen son varios archivos planos y la tarea Flujo de datos se encuentra en un contenedor de bucles, como el contenedor de bucles For.</span><span class="sxs-lookup"><span data-stu-id="c8d27-108">A Multiple Flat Files connection manager if the source is multiple flat files and the Data Flow task is inside a loop container, such as the For Loop container.</span></span> <span data-ttu-id="c8d27-109">En cada bucle del contenedor, el origen de archivos planos carga los datos del siguiente nombre de archivo que proporciona el administrador de conexiones de varios archivos planos.</span><span class="sxs-lookup"><span data-stu-id="c8d27-109">On each loop of the container, the Flat File source loads data from the next file name that the Multiple Flat Files connection manager provides.</span></span> <span data-ttu-id="c8d27-110">Para más información, consulte [Multiple Flat Files Connection Manager](connection-manager/multiple-flat-files-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="c8d27-110">For more information, see [Multiple Flat Files Connection Manager](connection-manager/multiple-flat-files-connection-manager.md).</span></span>  
  
 <span data-ttu-id="c8d27-111">Para obtener más información acerca del origen de archivo plano, vea [Flat File Source](data-flow/flat-file-source.md).</span><span class="sxs-lookup"><span data-stu-id="c8d27-111">To learn more about the Flat File source, see [Flat File Source](data-flow/flat-file-source.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="c8d27-112">Opciones</span><span class="sxs-lookup"><span data-stu-id="c8d27-112">Options</span></span>  
 <span data-ttu-id="c8d27-113">**Administrador de conexiones de archivos planos**</span><span class="sxs-lookup"><span data-stu-id="c8d27-113">**Flat file connection manager**</span></span>  
 <span data-ttu-id="c8d27-114">Seleccione un administrador de conexiones de la lista o cree un nuevo administrador de conexiones haciendo clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="c8d27-114">Select an existing connection manager from the list, or create a new connection manager by clicking **New**.</span></span>  
  
 <span data-ttu-id="c8d27-115">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="c8d27-115">**New**</span></span>  
 <span data-ttu-id="c8d27-116">Crea un nuevo administrador de conexiones mediante el cuadro de diálogo **Editor del administrador de conexiones de archivos planos** .</span><span class="sxs-lookup"><span data-stu-id="c8d27-116">Create a new connection manager by using the **Flat File Connection Manager Editor** dialog box.</span></span>  
  
 <span data-ttu-id="c8d27-117">**Conservar los valores null del origen como valores null en el flujo de datos**</span><span class="sxs-lookup"><span data-stu-id="c8d27-117">**Retain null values from the source as null values in the data flow**</span></span>  
 <span data-ttu-id="c8d27-118">Especifica si deben mantenerse los valores NULL cuando se extraen los datos.</span><span class="sxs-lookup"><span data-stu-id="c8d27-118">Specify whether to keep null values when data is extracted.</span></span> <span data-ttu-id="c8d27-119">El valor predeterminado de esta propiedad es **false**.</span><span class="sxs-lookup"><span data-stu-id="c8d27-119">The default value of this property is **false**.</span></span> <span data-ttu-id="c8d27-120">Cuando este valor es f`alse`, el origen de archivos planos reemplaza los valores NULL del origen de datos por los valores predeterminados correspondientes para cada columna, como cadenas vacías para las columnas de cadenas o cero para las columnas numéricas.</span><span class="sxs-lookup"><span data-stu-id="c8d27-120">When this value is f`alse`, the Flat File source replaces null values from the source data with appropriate default values for each column, such as empty strings for string columns and zero for numeric columns.</span></span>  
  
 <span data-ttu-id="c8d27-121">**Versión preliminar**</span><span class="sxs-lookup"><span data-stu-id="c8d27-121">**Preview**</span></span>  
 <span data-ttu-id="c8d27-122">Muestra una vista previa de los resultados mediante el cuadro de diálogo **Vista de datos** .</span><span class="sxs-lookup"><span data-stu-id="c8d27-122">Preview results by using the **Data View** dialog box.</span></span> <span data-ttu-id="c8d27-123">La vista previa puede mostrar hasta 200 filas.</span><span class="sxs-lookup"><span data-stu-id="c8d27-123">Preview can display up to 200 rows.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8d27-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c8d27-124">See Also</span></span>  
 <span data-ttu-id="c8d27-125">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="c8d27-125">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="c8d27-126">[Página &#40;columnas del editor de origen de archivos planos&#41;](../../2014/integration-services/flat-file-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="c8d27-126">[Flat File Source Editor &#40;Columns Page&#41;](../../2014/integration-services/flat-file-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="c8d27-127">[Editor de origen de archivos planos &#40;página salida de error&#41;](../../2014/integration-services/flat-file-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="c8d27-127">[Flat File Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/flat-file-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="c8d27-128">Administrador de conexiones de archivos planos</span><span class="sxs-lookup"><span data-stu-id="c8d27-128">Flat File Connection Manager</span></span>](connection-manager/file-connection-manager.md)  
  
  
