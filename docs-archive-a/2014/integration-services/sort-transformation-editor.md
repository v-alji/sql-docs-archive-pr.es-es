---
title: Editor de transformación ordenar | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sorttransformation.f1
helpviewer_keywords:
- Sort Transformation Editor
ms.assetid: 8ae23970-49a9-4d6d-9f15-c7074783347c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9f48c366f4337af29b03877f6bb20b804457a293
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751249"
---
# <a name="sort-transformation-editor"></a><span data-ttu-id="c2f5f-102">Editor de transformación Ordenar</span><span class="sxs-lookup"><span data-stu-id="c2f5f-102">Sort Transformation Editor</span></span>
  <span data-ttu-id="c2f5f-103">Use el cuadro de diálogo **Editor de transformación Ordenar** para seleccionar las columnas que desea ordenar, establecer el orden y especificar si deben quitarse los duplicados.</span><span class="sxs-lookup"><span data-stu-id="c2f5f-103">Use the **Sort Transformation Editor** dialog box to select the columns to sort, set the sort order, and specify whether duplicates are removed.</span></span>  
  
 <span data-ttu-id="c2f5f-104">Para obtener más información acerca de la transformación Ordenar, vea [Sort Transformation](data-flow/transformations/sort-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="c2f5f-104">To learn more about the Sort transformation, see [Sort Transformation](data-flow/transformations/sort-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="c2f5f-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="c2f5f-105">Options</span></span>  
 <span data-ttu-id="c2f5f-106">**Columnas de entrada disponibles**</span><span class="sxs-lookup"><span data-stu-id="c2f5f-106">**Available Input Columns**</span></span>  
 <span data-ttu-id="c2f5f-107">Active las casillas de las columnas que desea ordenar.</span><span class="sxs-lookup"><span data-stu-id="c2f5f-107">Using the check boxes, specify the columns to sort.</span></span>  
  
 <span data-ttu-id="c2f5f-108">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="c2f5f-108">**Name**</span></span>  
 <span data-ttu-id="c2f5f-109">Muestra el nombre de todas las columnas de entrada disponibles.</span><span class="sxs-lookup"><span data-stu-id="c2f5f-109">View the name of each available input column.</span></span>  
  
 <span data-ttu-id="c2f5f-110">**Acceso directo**</span><span class="sxs-lookup"><span data-stu-id="c2f5f-110">**Passthrough**</span></span>  
 <span data-ttu-id="c2f5f-111">Permite indicar si la columna debe incluirse en la salida ordenada.</span><span class="sxs-lookup"><span data-stu-id="c2f5f-111">Indicate whether to include the column in the sorted output.</span></span>  
  
 <span data-ttu-id="c2f5f-112">**Columna de entrada**</span><span class="sxs-lookup"><span data-stu-id="c2f5f-112">**Input Column**</span></span>  
 <span data-ttu-id="c2f5f-113">Seleccione de la lista de entradas disponibles las columnas para cada fila.</span><span class="sxs-lookup"><span data-stu-id="c2f5f-113">Select from the list of available input columns for each row.</span></span> <span data-ttu-id="c2f5f-114">Las selecciones se reflejan en las casillas activadas en la tabla **Columnas de entrada disponibles** .</span><span class="sxs-lookup"><span data-stu-id="c2f5f-114">Your selections are reflected in the check box selections in the **Available Input Columns** table.</span></span>  
  
 <span data-ttu-id="c2f5f-115">**Alias de salida**</span><span class="sxs-lookup"><span data-stu-id="c2f5f-115">**Output Alias**</span></span>  
 <span data-ttu-id="c2f5f-116">Escriba un alias para cada columna de salida.</span><span class="sxs-lookup"><span data-stu-id="c2f5f-116">Type an alias for each output column.</span></span> <span data-ttu-id="c2f5f-117">El nombre predeterminado es el de la columna de entrada, pero puede elegir cualquier nombre descriptivo único.</span><span class="sxs-lookup"><span data-stu-id="c2f5f-117">The default is the name of the input column; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="c2f5f-118">**Tipo de orden**</span><span class="sxs-lookup"><span data-stu-id="c2f5f-118">**Sort Type**</span></span>  
 <span data-ttu-id="c2f5f-119">Permite indicar si la ordenación seguirá un orden ascendente o descendente.</span><span class="sxs-lookup"><span data-stu-id="c2f5f-119">Indicate whether to sort in ascending or descending order.</span></span>  
  
 <span data-ttu-id="c2f5f-120">**Criterio de ordenación**</span><span class="sxs-lookup"><span data-stu-id="c2f5f-120">**Sort Order**</span></span>  
 <span data-ttu-id="c2f5f-121">Permite indicar el orden en que deben ordenarse las columnas.</span><span class="sxs-lookup"><span data-stu-id="c2f5f-121">Indicate the order in which to sort columns.</span></span> <span data-ttu-id="c2f5f-122">Esta característica debe establecerse manualmente para cada columna.</span><span class="sxs-lookup"><span data-stu-id="c2f5f-122">This must be set manually for each column.</span></span>  
  
 <span data-ttu-id="c2f5f-123">**Marcas de comparación**</span><span class="sxs-lookup"><span data-stu-id="c2f5f-123">**Comparison Flags**</span></span>  
 <span data-ttu-id="c2f5f-124">Para más información sobre las opciones de comparación de cadenas, vea [Comparar datos de cadena](data-flow/comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="c2f5f-124">For information about the string comparison options, see [Comparing String Data](data-flow/comparing-string-data.md).</span></span>  
  
 <span data-ttu-id="c2f5f-125">**Quitar filas con valores de ordenación duplicados**</span><span class="sxs-lookup"><span data-stu-id="c2f5f-125">**Remove rows with duplicate sort values**</span></span>  
 <span data-ttu-id="c2f5f-126">Permite indicar si la transformación copia filas duplicadas en la salida o crea una única entrada para todos los duplicados utilizando las opciones de comparación de cadenas especificadas.</span><span class="sxs-lookup"><span data-stu-id="c2f5f-126">Indicate whether the transformation copies duplicate rows to the transformation output, or creates a single entry for all duplicates, based on the specified string comparison options.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2f5f-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c2f5f-127">See Also</span></span>  
 [<span data-ttu-id="c2f5f-128">Referencia de errores y mensajes de Integration Services</span><span class="sxs-lookup"><span data-stu-id="c2f5f-128">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
