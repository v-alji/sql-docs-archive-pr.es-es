---
title: Editor de origen de CDC (página salida de error) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.cdcsource.errorhandling.f1
ms.assetid: 8a4c2cb8-fd2f-4c45-824f-b93473a8981e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b39532304fddfa90fabe8cafe2a6caf5b1fb5c8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676622"
---
# <a name="cdc-source-editor-error-output-page"></a><span data-ttu-id="affd1-102">Editor de origen de CDC (página Salida de error)</span><span class="sxs-lookup"><span data-stu-id="affd1-102">CDC Source Editor (Error Output Page)</span></span>
  <span data-ttu-id="affd1-103">Use la página **Salida de error** del cuadro de diálogo **Editor de origen de CDC** para seleccionar las opciones de control de errores.</span><span class="sxs-lookup"><span data-stu-id="affd1-103">Use the **Error Output** page of the **CDC Source Editor** dialog box to select error handling options.</span></span>  
  
 <span data-ttu-id="affd1-104">Para obtener más información acerca del origen de CDC, vea [CDC Source](data-flow/cdc-source.md).</span><span class="sxs-lookup"><span data-stu-id="affd1-104">To learn more about the CDC source, see [CDC Source](data-flow/cdc-source.md).</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="affd1-105">Lista de tareas</span><span class="sxs-lookup"><span data-stu-id="affd1-105">Task List</span></span>  
 <span data-ttu-id="affd1-106">**Para abrir la página Salida de error del Editor de origen de CDC**</span><span class="sxs-lookup"><span data-stu-id="affd1-106">**To open the CDC Source Editor Error Output Page**</span></span>  
  
1.  <span data-ttu-id="affd1-107">En [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], abra el paquete [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] que tiene el origen de CDC.</span><span class="sxs-lookup"><span data-stu-id="affd1-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the CDC source.</span></span>  
  
2.  <span data-ttu-id="affd1-108">En la pestaña **Flujo de datos** , haga doble clic en el origen de CDC.</span><span class="sxs-lookup"><span data-stu-id="affd1-108">On the **Data Flow** tab, double-click the CDC source.</span></span>  
  
3.  <span data-ttu-id="affd1-109">En el **Editor de origen de CDC**, haga clic en **Salida de error**.</span><span class="sxs-lookup"><span data-stu-id="affd1-109">In the **CDC Source Editor**, click **Error Output**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="affd1-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="affd1-110">Options</span></span>  
 <span data-ttu-id="affd1-111">**Entrada/salida**</span><span class="sxs-lookup"><span data-stu-id="affd1-111">**Input/Output**</span></span>  
 <span data-ttu-id="affd1-112">Muestra el nombre del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="affd1-112">View the name of the data source.</span></span>  
  
 <span data-ttu-id="affd1-113">**Columna**</span><span class="sxs-lookup"><span data-stu-id="affd1-113">**Column**</span></span>  
 <span data-ttu-id="affd1-114">Muestra las columnas externas (origen) que se han seleccionado en la página **Administrador de conexiones** del cuadro de diálogo **Editor de origen de CDC** .</span><span class="sxs-lookup"><span data-stu-id="affd1-114">View the external (source) columns that you selected on the **Connection Manager** page of the **CDC Source Editor** dialog box.</span></span>  
  
 <span data-ttu-id="affd1-115">**Error**</span><span class="sxs-lookup"><span data-stu-id="affd1-115">**Error**</span></span>  
 <span data-ttu-id="affd1-116">Seleccione la forma en la que el origen de CDC debe controlar errores en un flujo: omitir el error, redirigir la fila o hacer que el componente no funcione.</span><span class="sxs-lookup"><span data-stu-id="affd1-116">Select how the CDC source should handle errors in a flow: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="affd1-117">**Truncamiento**</span><span class="sxs-lookup"><span data-stu-id="affd1-117">**Truncation**</span></span>  
 <span data-ttu-id="affd1-118">Seleccione la forma en la que el origen de CDC debe controlar el truncamiento en un flujo: omitir el error, redirigir la fila o hacer que el componente no funcione.</span><span class="sxs-lookup"><span data-stu-id="affd1-118">Select how the CDC source should handle truncation in a flow: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="affd1-119">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="affd1-119">**Description**</span></span>  
 <span data-ttu-id="affd1-120">No se usa.</span><span class="sxs-lookup"><span data-stu-id="affd1-120">Not used.</span></span>  
  
 <span data-ttu-id="affd1-121">**Establecer este valor en las celdas seleccionadas**</span><span class="sxs-lookup"><span data-stu-id="affd1-121">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="affd1-122">Seleccione la forma en la que el origen de CDC controla todas las celdas seleccionadas cuando se produce un error o un truncamiento: omitir el error, redirigir la fila o hacer que el componente no funcione.</span><span class="sxs-lookup"><span data-stu-id="affd1-122">Select how the CDC source handles all selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="affd1-123">**Aplicar**</span><span class="sxs-lookup"><span data-stu-id="affd1-123">**Apply**</span></span>  
 <span data-ttu-id="affd1-124">Aplica las opciones de control de errores a las celdas seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="affd1-124">Apply the error handling options to the selected cells.</span></span>  
  
## <a name="error-handling-options"></a><span data-ttu-id="affd1-125">Opciones de control de errores</span><span class="sxs-lookup"><span data-stu-id="affd1-125">Error Handling Options</span></span>  
 <span data-ttu-id="affd1-126">Use las opciones siguientes para configurar la forma en la que el origen de CDC controla errores y truncamientos.</span><span class="sxs-lookup"><span data-stu-id="affd1-126">You use the following options to configure how the CDC source handles errors and truncations.</span></span>  
  
 <span data-ttu-id="affd1-127">**Error de componente**</span><span class="sxs-lookup"><span data-stu-id="affd1-127">**Fail Component**</span></span>  
 <span data-ttu-id="affd1-128">La tarea Flujo de datos genera un error cuando se produce un error o truncamiento.</span><span class="sxs-lookup"><span data-stu-id="affd1-128">The Data Flow task fails when an error or a truncation occurs.</span></span> <span data-ttu-id="affd1-129">Este es el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="affd1-129">This is the default behavior.</span></span>  
  
 <span data-ttu-id="affd1-130">**Omitir error**</span><span class="sxs-lookup"><span data-stu-id="affd1-130">**Ignore Failure**</span></span>  
 <span data-ttu-id="affd1-131">El error o el truncamiento se omite y la fila de datos se dirige a la salida de origen de CDC.</span><span class="sxs-lookup"><span data-stu-id="affd1-131">The error or the truncation is ignored and the data row is directed to the CDC source output.</span></span>  
  
 <span data-ttu-id="affd1-132">**Redirigir fila**</span><span class="sxs-lookup"><span data-stu-id="affd1-132">**Redirect Flow**</span></span>  
 <span data-ttu-id="affd1-133">La fila de datos de error o truncamiento se dirige a la salida de error del origen de CDC.</span><span class="sxs-lookup"><span data-stu-id="affd1-133">The error or the truncation data row is directed to the error output of the CDC source.</span></span> <span data-ttu-id="affd1-134">En este caso, se usa el control de errores de origen de CDC.</span><span class="sxs-lookup"><span data-stu-id="affd1-134">In this case the CDC source error handling is used.</span></span> <span data-ttu-id="affd1-135">Para más información, consulte [CDC Source](data-flow/cdc-source.md).</span><span class="sxs-lookup"><span data-stu-id="affd1-135">For more information, see [CDC Source](data-flow/cdc-source.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="affd1-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="affd1-136">See Also</span></span>  
 <span data-ttu-id="affd1-137">[Editor de origen de CDC &#40;página Administrador de conexiones&#41;](../../2014/integration-services/cdc-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="affd1-137">[CDC Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/cdc-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="affd1-138">Editor de origen de CDC &#40;página Columnas&#41;</span><span class="sxs-lookup"><span data-stu-id="affd1-138">CDC Source Editor &#40;Columns Page&#41;</span></span>](../../2014/integration-services/cdc-source-editor-columns-page.md)  
  
  
