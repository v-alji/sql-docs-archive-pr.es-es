---
title: Editor de transformación búsqueda (página salida de error) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.lookuptransformation.erroroutput.f1
ms.assetid: 15d53bb0-8be1-46fb-b459-04a397e75fac
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9cd78f40a0072f7f0c5c923cdd51431873402f3e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673095"
---
# <a name="lookup-transformation-editor-error-output-page"></a><span data-ttu-id="1e3bc-102">Editor de transformación Búsqueda (página Salida de error)</span><span class="sxs-lookup"><span data-stu-id="1e3bc-102">Lookup Transformation Editor (Error Output Page)</span></span>
  <span data-ttu-id="1e3bc-103">Utilice la página **Salida de error** del cuadro de diálogo **Editor de transformación Búsqueda** para especificar las opciones de control de errores.</span><span class="sxs-lookup"><span data-stu-id="1e3bc-103">Use the **Error Output** page of the **Lookup Transformation Editor** dialog box to specify error handling options.</span></span>  
  
 <span data-ttu-id="1e3bc-104">Para obtener más información acerca de la transformación Búsqueda, vea [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="1e3bc-104">To learn more about the Lookup transformation, see [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="1e3bc-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="1e3bc-105">Options</span></span>  
 <span data-ttu-id="1e3bc-106">**Entrada/salida**</span><span class="sxs-lookup"><span data-stu-id="1e3bc-106">**Input/Output**</span></span>  
 <span data-ttu-id="1e3bc-107">Muestra el nombre de la entrada.</span><span class="sxs-lookup"><span data-stu-id="1e3bc-107">View the name of the input.</span></span>  
  
 <span data-ttu-id="1e3bc-108">**Columna**</span><span class="sxs-lookup"><span data-stu-id="1e3bc-108">**Column**</span></span>  
 <span data-ttu-id="1e3bc-109">No se usa.</span><span class="sxs-lookup"><span data-stu-id="1e3bc-109">Not used.</span></span>  
  
 <span data-ttu-id="1e3bc-110">**Error**</span><span class="sxs-lookup"><span data-stu-id="1e3bc-110">**Error**</span></span>  
 <span data-ttu-id="1e3bc-111">Especifica el tipo de error que se producirá al administrar filas sin entradas coincidentes en el conjunto de datos de referencia:</span><span class="sxs-lookup"><span data-stu-id="1e3bc-111">Specify what type of error should occur when handling rows without matching entries in the reference dataset:</span></span>  
  
-   <span data-ttu-id="1e3bc-112">Pasar por alto el error y dirigir las filas a un resultado.</span><span class="sxs-lookup"><span data-stu-id="1e3bc-112">Ignore the failure and direct the rows to an output.</span></span>  
  
-   <span data-ttu-id="1e3bc-113">Redirigir las filas a una salida de error.</span><span class="sxs-lookup"><span data-stu-id="1e3bc-113">Redirect the rows to an error output.</span></span>  
  
-   <span data-ttu-id="1e3bc-114">Producir un error en el componente.</span><span class="sxs-lookup"><span data-stu-id="1e3bc-114">Fail the component.</span></span>  
  
 <span data-ttu-id="1e3bc-115">Esta opción no está disponible al seleccionar **Redirigir filas a resultados no coincidentes** en la lista **Especificar cómo tratar las filas sin entradas coincidentes** .</span><span class="sxs-lookup"><span data-stu-id="1e3bc-115">This option is not available when you select **Redirect rows to no match output** in the **Specify how to handle rows with no matching entries** list.</span></span> <span data-ttu-id="1e3bc-116">La lista está en la página **General** del cuadro de diálogo **Editor de transformación Búsqueda** .</span><span class="sxs-lookup"><span data-stu-id="1e3bc-116">This list is on the **General** page of the **Lookup Transformation Editor** dialog box.</span></span>  
  
 <span data-ttu-id="1e3bc-117">**Temas relacionados:** [Control de errores en los datos](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="1e3bc-117">**Related Topics:** [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>  
  
 <span data-ttu-id="1e3bc-118">**Truncamiento**</span><span class="sxs-lookup"><span data-stu-id="1e3bc-118">**Truncation**</span></span>  
 <span data-ttu-id="1e3bc-119">Especifica lo que debe suceder cuando se produce un truncamiento de datos:</span><span class="sxs-lookup"><span data-stu-id="1e3bc-119">Specify what should happen when data truncation occurs:</span></span>  
  
-   <span data-ttu-id="1e3bc-120">Pasar por alto el error.</span><span class="sxs-lookup"><span data-stu-id="1e3bc-120">Ignore the failure.</span></span>  
  
-   <span data-ttu-id="1e3bc-121">Redirigir la fila.</span><span class="sxs-lookup"><span data-stu-id="1e3bc-121">Redirect the row.</span></span>  
  
-   <span data-ttu-id="1e3bc-122">Producir un error en el componente.</span><span class="sxs-lookup"><span data-stu-id="1e3bc-122">Fail the component.</span></span>  
  
 <span data-ttu-id="1e3bc-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="1e3bc-123">**Description**</span></span>  
 <span data-ttu-id="1e3bc-124">Muestra la descripción de la operación.</span><span class="sxs-lookup"><span data-stu-id="1e3bc-124">View the description of the operation.</span></span>  
  
 <span data-ttu-id="1e3bc-125">**Establecer este valor en las celdas seleccionadas**</span><span class="sxs-lookup"><span data-stu-id="1e3bc-125">**Set selected cells to this value**</span></span>  
 <span data-ttu-id="1e3bc-126">Especifica qué debe suceder a todas las celdas seleccionadas cuando se produce un error o truncación:</span><span class="sxs-lookup"><span data-stu-id="1e3bc-126">Specify what should happen to all the selected cells when an error or truncation occurs:</span></span>  
  
-   <span data-ttu-id="1e3bc-127">Pasar por alto el error.</span><span class="sxs-lookup"><span data-stu-id="1e3bc-127">Ignore the failure.</span></span>  
  
-   <span data-ttu-id="1e3bc-128">Redirigir la fila.</span><span class="sxs-lookup"><span data-stu-id="1e3bc-128">Redirect the row.</span></span>  
  
-   <span data-ttu-id="1e3bc-129">Producir un error en el componente.</span><span class="sxs-lookup"><span data-stu-id="1e3bc-129">Fail the component.</span></span>  
  
 <span data-ttu-id="1e3bc-130">**Aplicar**</span><span class="sxs-lookup"><span data-stu-id="1e3bc-130">**Apply**</span></span>  
 <span data-ttu-id="1e3bc-131">Aplica la opción de control de errores a las celdas seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="1e3bc-131">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e3bc-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1e3bc-132">See Also</span></span>  
 [<span data-ttu-id="1e3bc-133">Referencia de errores y mensajes de Integration Services</span><span class="sxs-lookup"><span data-stu-id="1e3bc-133">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
