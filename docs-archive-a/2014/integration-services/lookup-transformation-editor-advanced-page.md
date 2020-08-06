---
title: Editor de transformación búsqueda (página avanzadas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.lookuptransformation.advanced.f1
helpviewer_keywords:
- Lookup Transformation Editor
ms.assetid: f3395c65-0320-47f9-8d83-daaa082d8713
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 23f235ef0506da7ac808d832db6ac36d53cfa604
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673100"
---
# <a name="lookup-transformation-editor-advanced-page"></a><span data-ttu-id="7fdc2-102">Editor de transformación Búsqueda (página Avanzadas)</span><span class="sxs-lookup"><span data-stu-id="7fdc2-102">Lookup Transformation Editor (Advanced Page)</span></span>
  <span data-ttu-id="7fdc2-103">Utilice la página **Avanzadas** del cuadro de diálogo **Editor de transformación Búsqueda** para configurar el almacenamiento parcial en caché y modificar la instrucción SQL para la transformación Búsqueda.</span><span class="sxs-lookup"><span data-stu-id="7fdc2-103">Use the **Advanced** page of the **Lookup Transformation Editor** dialog box to configure partial caching and to modify the SQL statement for the Lookup transformation.</span></span>  
  
 <span data-ttu-id="7fdc2-104">Para obtener más información acerca de la transformación Búsqueda, vea [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="7fdc2-104">To learn more about the Lookup transformation, see [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="7fdc2-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="7fdc2-105">Options</span></span>  
 <span data-ttu-id="7fdc2-106">**Tamaño de caché (32 bits)**</span><span class="sxs-lookup"><span data-stu-id="7fdc2-106">**Cache size (32-bit)**</span></span>  
 <span data-ttu-id="7fdc2-107">Ajuste el tamaño de caché (en megabytes) para los equipos de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="7fdc2-107">Adjust the  cache size (in megabytes) for 32-bit computers.</span></span> <span data-ttu-id="7fdc2-108">El valor predeterminado es 5 megabytes.</span><span class="sxs-lookup"><span data-stu-id="7fdc2-108">The default value is 5 megabytes.</span></span>  
  
 <span data-ttu-id="7fdc2-109">**Tamaño de caché (64 bits)**</span><span class="sxs-lookup"><span data-stu-id="7fdc2-109">**Cache size (64-bit)**</span></span>  
 <span data-ttu-id="7fdc2-110">Ajuste el tamaño de caché (en megabytes) para los equipos de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="7fdc2-110">Adjust the cache size (in megabytes) for 64-bit computers.</span></span> <span data-ttu-id="7fdc2-111">El valor predeterminado es 5 megabytes.</span><span class="sxs-lookup"><span data-stu-id="7fdc2-111">The default value is 5 megabytes.</span></span>  
  
 <span data-ttu-id="7fdc2-112">**Habilitar caché para filas sin entradas coincidentes**</span><span class="sxs-lookup"><span data-stu-id="7fdc2-112">**Enable cache for rows with no matching entries**</span></span>  
 <span data-ttu-id="7fdc2-113">Almacene en caché filas sin entradas coincidentes en el conjunto de datos de referencia.</span><span class="sxs-lookup"><span data-stu-id="7fdc2-113">Cache rows with no matching entries in the reference dataset.</span></span>  
  
 <span data-ttu-id="7fdc2-114">**Asignación de caché**</span><span class="sxs-lookup"><span data-stu-id="7fdc2-114">**Allocation from cache**</span></span>  
 <span data-ttu-id="7fdc2-115">Especifique el porcentaje de caché que se debe asignar a las filas sin entradas coincidentes en el conjunto de datos de referencia.</span><span class="sxs-lookup"><span data-stu-id="7fdc2-115">Specify the percentage of the cache to allocate for rows with no matching entries in the reference dataset.</span></span>  
  
 <span data-ttu-id="7fdc2-116">**Modificar la instrucción SQL**</span><span class="sxs-lookup"><span data-stu-id="7fdc2-116">**Modify the SQL statement**</span></span>  
 <span data-ttu-id="7fdc2-117">Modifique la instrucción SQL que se utiliza para generar el conjunto de datos de referencia.</span><span class="sxs-lookup"><span data-stu-id="7fdc2-117">Modify the SQL statement that is used to generate the reference dataset.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7fdc2-118">La instrucción SQL opcional que se especifica en esta página invalida y reemplaza el nombre de tabla que se especificó en la página **Conexión** del **Editor de transformación Búsqueda**.</span><span class="sxs-lookup"><span data-stu-id="7fdc2-118">The optional SQL statement that you specify on this page overrides and replaces the table name that you specified on the **Connection** page of the **Lookup Transformation Editor**.</span></span> <span data-ttu-id="7fdc2-119">Para más información, vea [Editor de transformación Búsqueda &#40;página Conexión&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md).</span><span class="sxs-lookup"><span data-stu-id="7fdc2-119">For more information, see [Lookup Transformation Editor &#40;Connection Page&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md).</span></span>  
  
 <span data-ttu-id="7fdc2-120">**Establecer parámetros**</span><span class="sxs-lookup"><span data-stu-id="7fdc2-120">**Set Parameters**</span></span>  
 <span data-ttu-id="7fdc2-121">Asigne columnas de entrada a parámetros mediante el cuadro de diálogo **Establecer parámetros de consulta** .</span><span class="sxs-lookup"><span data-stu-id="7fdc2-121">Map input columns to parameters by using the **Set Query Parameters** dialog box.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="7fdc2-122">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="7fdc2-122">External Resources</span></span>  
 <span data-ttu-id="7fdc2-123">Entrada del blog, [Lookup cache modes](https://go.microsoft.com/fwlink/?LinkId=219518) en blogs.msdn.com</span><span class="sxs-lookup"><span data-stu-id="7fdc2-123">Blog entry, [Lookup cache modes](https://go.microsoft.com/fwlink/?LinkId=219518) on blogs.msdn.com</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fdc2-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7fdc2-124">See Also</span></span>  
 <span data-ttu-id="7fdc2-125">[Editor de transformación búsqueda &#40;página general&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="7fdc2-125">[Lookup Transformation Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="7fdc2-126">[Editor de transformación búsqueda &#40;página de conexión&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md) </span><span class="sxs-lookup"><span data-stu-id="7fdc2-126">[Lookup Transformation Editor &#40;Connection Page&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md) </span></span>  
 <span data-ttu-id="7fdc2-127">[Editor de transformación búsqueda &#40;página columnas&#41;](../../2014/integration-services/lookup-transformation-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="7fdc2-127">[Lookup Transformation Editor &#40;Columns Page&#41;](../../2014/integration-services/lookup-transformation-editor-columns-page.md) </span></span>  
 <span data-ttu-id="7fdc2-128">[Editor de transformación búsqueda &#40;página salida de error&#41;](../../2014/integration-services/lookup-transformation-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="7fdc2-128">[Lookup Transformation Editor &#40;Error Output Page&#41;](../../2014/integration-services/lookup-transformation-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="7fdc2-129">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="7fdc2-129">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="7fdc2-130">Búsqueda aproximada, transformación</span><span class="sxs-lookup"><span data-stu-id="7fdc2-130">Fuzzy Lookup Transformation</span></span>](data-flow/transformations/fuzzy-lookup-transformation.md)  
  
  
