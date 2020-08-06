---
title: Editor de transformación búsqueda (página general) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.lookuptransformation.general.f1
ms.assetid: 4bd15e48-0feb-4f95-be91-5df58105dbfb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: aa178118f7e090b6a3c15c7ab9347f322461f07b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744769"
---
# <a name="lookup-transformation-editor-general-page"></a><span data-ttu-id="d2e4f-102">Editor de transformación Búsqueda (página General)</span><span class="sxs-lookup"><span data-stu-id="d2e4f-102">Lookup Transformation Editor (General Page)</span></span>
  <span data-ttu-id="d2e4f-103">Utilice la página **General** del cuadro de diálogo Editor de transformación Búsqueda para seleccionar el modo de caché y el tipo de conexión, y especificar cómo administrar las filas sin entradas coincidentes.</span><span class="sxs-lookup"><span data-stu-id="d2e4f-103">Use the **General** page of the Lookup Transformation Editor dialog box to select the cache mode, select the connection type, and specify how to handle rows with no matching entries.</span></span>  
  
 <span data-ttu-id="d2e4f-104">Para obtener más información acerca de la transformación Búsqueda, vea [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="d2e4f-104">To learn more about the Lookup transformation, see [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="d2e4f-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="d2e4f-105">Options</span></span>  
 <span data-ttu-id="d2e4f-106">**Caché completa**</span><span class="sxs-lookup"><span data-stu-id="d2e4f-106">**Full cache**</span></span>  
 <span data-ttu-id="d2e4f-107">Generey cargue el conjunto de datos de referencia en la caché antes de que se ejecute la transformación Búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d2e4f-107">Generate and load the reference dataset into cache before the Lookup transformation is executed.</span></span>  
  
 <span data-ttu-id="d2e4f-108">**Caché parcial**</span><span class="sxs-lookup"><span data-stu-id="d2e4f-108">**Partial cache**</span></span>  
 <span data-ttu-id="d2e4f-109">Genere el conjunto de datos de referencia durante la ejecución de la transformación Búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d2e4f-109">Generate the reference dataset during the execution of the Lookup transformation.</span></span> <span data-ttu-id="d2e4f-110">Cargue en la caché las filas con entradas coincidentes del conjunto de datos de referencia y las que no tienen entradas coincidentes.</span><span class="sxs-lookup"><span data-stu-id="d2e4f-110">Load the rows with matching entries in the reference dataset and the rows with no matching entries in the dataset into cache.</span></span>  
  
 <span data-ttu-id="d2e4f-111">**Sin caché**</span><span class="sxs-lookup"><span data-stu-id="d2e4f-111">**No cache**</span></span>  
 <span data-ttu-id="d2e4f-112">Genere el conjunto de datos de referencia durante la ejecución de la transformación Búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d2e4f-112">Generate the reference dataset during the execution of the Lookup transformation.</span></span> <span data-ttu-id="d2e4f-113">No se carga ningún dato en la caché.</span><span class="sxs-lookup"><span data-stu-id="d2e4f-113">No data is loaded into cache.</span></span>  
  
 <span data-ttu-id="d2e4f-114">**Administrador de conexiones de caché**</span><span class="sxs-lookup"><span data-stu-id="d2e4f-114">**Cache connection manager**</span></span>  
 <span data-ttu-id="d2e4f-115">Configure la transformación Búsqueda para utilizar un administrador de conexiones de caché.</span><span class="sxs-lookup"><span data-stu-id="d2e4f-115">Configure the Lookup transformation to use a Cache connection manager.</span></span> <span data-ttu-id="d2e4f-116">Esta opción solo está disponible si también está seleccionada la opción Caché completa.</span><span class="sxs-lookup"><span data-stu-id="d2e4f-116">This option is available only if the Full cache option is selected.</span></span>  
  
 <span data-ttu-id="d2e4f-117">**Administrador de conexiones OLE DB**</span><span class="sxs-lookup"><span data-stu-id="d2e4f-117">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="d2e4f-118">Configure la transformación Búsqueda para utilizar un administrador de conexiones OLE DB.</span><span class="sxs-lookup"><span data-stu-id="d2e4f-118">Configure the Lookup transformation to use an OLE DB connection manager.</span></span>  
  
 <span data-ttu-id="d2e4f-119">**Especificar cómo administrar las filas sin entradas coincidentes**</span><span class="sxs-lookup"><span data-stu-id="d2e4f-119">**Specify how to handle rows with no matching entries**</span></span>  
 <span data-ttu-id="d2e4f-120">Seleccione una opción para administrar las filas que no coincidan por lo menos con una entrada del conjunto de datos de referencia.</span><span class="sxs-lookup"><span data-stu-id="d2e4f-120">Select an option for handling rows that do not match at least one entry in the reference dataset.</span></span>  
  
 <span data-ttu-id="d2e4f-121">Al seleccionar **Redirigir filas a resultados no coincidentes**, las filas se redirigen a un resultado sin coincidencia y no se tratan como errores.</span><span class="sxs-lookup"><span data-stu-id="d2e4f-121">When you select **Redirect rows to no match output**, the rows are redirected to a no match output and are not handled as errors.</span></span> <span data-ttu-id="d2e4f-122">La opción **Error** de la página **Salida de error** del cuadro de diálogo **Editor de transformación Búsqueda** no está disponible.</span><span class="sxs-lookup"><span data-stu-id="d2e4f-122">The **Error** option on the **Error Output** page of the **Lookup Transformation Editor** dialog box is not available.</span></span>  
  
 <span data-ttu-id="d2e4f-123">Al seleccionar cualquier otra opción del cuadro de lista **Especifique cómo administrar las filas sin entradas coincidentes** , las filas se tratan como errores.</span><span class="sxs-lookup"><span data-stu-id="d2e4f-123">When you select any other option in the **Specify how to handle rows with no matching entries** list box, the rows are handled as errors.</span></span> <span data-ttu-id="d2e4f-124">La opción **Error** de la página **Salida de error** está disponible.</span><span class="sxs-lookup"><span data-stu-id="d2e4f-124">The **Error** option on the **Error Output** page is available.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="d2e4f-125">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="d2e4f-125">External Resources</span></span>  
 <span data-ttu-id="d2e4f-126">Entrada del blog, [Lookup cache modes](https://go.microsoft.com/fwlink/?LinkId=219518) en blogs.msdn.com</span><span class="sxs-lookup"><span data-stu-id="d2e4f-126">Blog entry, [Lookup cache modes](https://go.microsoft.com/fwlink/?LinkId=219518) on blogs.msdn.com</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2e4f-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d2e4f-127">See Also</span></span>  
 <span data-ttu-id="d2e4f-128">[Administrador de conexiones de caché](connection-manager/cache-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="d2e4f-128">[Cache Connection Manager](connection-manager/cache-connection-manager.md) </span></span>  
 <span data-ttu-id="d2e4f-129">[Editor de transformación búsqueda &#40;página de conexión&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md) </span><span class="sxs-lookup"><span data-stu-id="d2e4f-129">[Lookup Transformation Editor &#40;Connection Page&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md) </span></span>  
 <span data-ttu-id="d2e4f-130">[Editor de transformación búsqueda &#40;página columnas&#41;](../../2014/integration-services/lookup-transformation-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="d2e4f-130">[Lookup Transformation Editor &#40;Columns Page&#41;](../../2014/integration-services/lookup-transformation-editor-columns-page.md) </span></span>  
 <span data-ttu-id="d2e4f-131">[Editor de transformación búsqueda &#40;página avanzadas&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="d2e4f-131">[Lookup Transformation Editor &#40;Advanced Page&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="d2e4f-132">Editor de transformación Búsqueda &#40;página Salida de error&#41;</span><span class="sxs-lookup"><span data-stu-id="d2e4f-132">Lookup Transformation Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/lookup-transformation-editor-error-output-page.md)  
  
  
