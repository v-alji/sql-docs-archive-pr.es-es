---
title: Editor de origen de ODBC (página salida de error) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.odbcsource.errorhandling.f1
ms.assetid: b2f6866c-db07-4cb3-9f38-889f8d2b03e6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a8e169875a26efbe0a7f1ac3d06856b393266eb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747133"
---
# <a name="odbc-source-editor-error-output-page"></a><span data-ttu-id="e838d-102">Editor de origen de ODBC (página Salida de error)</span><span class="sxs-lookup"><span data-stu-id="e838d-102">ODBC Source Editor (Error Output Page)</span></span>
  <span data-ttu-id="e838d-103">Use la página **Salida de error** del cuadro de diálogo **Editor de origen de ODBC** para seleccionar las opciones de control de errores.</span><span class="sxs-lookup"><span data-stu-id="e838d-103">Use the **Error Output** page of the **ODBC Source Editor** dialog box to select error handling options.</span></span>  
  
 <span data-ttu-id="e838d-104">Para obtener más información acerca del origen de ODBC, vea [CDC Source](data-flow/cdc-source.md).</span><span class="sxs-lookup"><span data-stu-id="e838d-104">To learn more about the ODBC source, see [CDC Source](data-flow/cdc-source.md).</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="e838d-105">Lista de tareas</span><span class="sxs-lookup"><span data-stu-id="e838d-105">Task List</span></span>  
 <span data-ttu-id="e838d-106">**Para abrir la página Salida de error del Editor de origen de ODBC**</span><span class="sxs-lookup"><span data-stu-id="e838d-106">**To open the ODBC Source Editor Error Output Page**</span></span>  
  
-   <span data-ttu-id="e838d-107">En [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], abra el paquete [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] que tiene el origen de ODBC.</span><span class="sxs-lookup"><span data-stu-id="e838d-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the ODBC source.</span></span>  
  
-   <span data-ttu-id="e838d-108">En la pestaña **Flujo de datos** , haga doble clic en el origen de ODBC.</span><span class="sxs-lookup"><span data-stu-id="e838d-108">On the **Data Flow** tab, double-click the ODBC source.</span></span>  
  
-   <span data-ttu-id="e838d-109">En el **Editor de origen de ODBC**, haga clic en **Salida de error**.</span><span class="sxs-lookup"><span data-stu-id="e838d-109">In the **ODBC Source Editor**, click **Error Output**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e838d-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="e838d-110">Options</span></span>  
  
### <a name="inputoutput"></a><span data-ttu-id="e838d-111">Entrada/salida</span><span class="sxs-lookup"><span data-stu-id="e838d-111">Input/Output</span></span>  
 <span data-ttu-id="e838d-112">Muestra el nombre del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="e838d-112">View the name of the data source.</span></span>  
  
### <a name="column"></a><span data-ttu-id="e838d-113">Columna</span><span class="sxs-lookup"><span data-stu-id="e838d-113">Column</span></span>  
 <span data-ttu-id="e838d-114">No se usa.</span><span class="sxs-lookup"><span data-stu-id="e838d-114">Not used.</span></span>  
  
### <a name="error"></a><span data-ttu-id="e838d-115">Error</span><span class="sxs-lookup"><span data-stu-id="e838d-115">Error</span></span>  
 <span data-ttu-id="e838d-116">Seleccione la forma en la que el origen de ODBC debe controlar errores en un flujo: omitir el error, redirigir la fila o hacer que el componente no funcione.</span><span class="sxs-lookup"><span data-stu-id="e838d-116">Select how the ODBC source should handle errors in a flow: ignore the failure, redirect the row, or fail the component.</span></span>  
  
### <a name="truncation"></a><span data-ttu-id="e838d-117">Truncamiento</span><span class="sxs-lookup"><span data-stu-id="e838d-117">Truncation</span></span>  
 <span data-ttu-id="e838d-118">Seleccione la forma en la que el origen de ODBC debe controlar el truncamiento en un flujo: omitir el error, redirigir la fila o hacer que el componente no funcione.</span><span class="sxs-lookup"><span data-stu-id="e838d-118">Select how the ODBC source should handle truncation in a flow: ignore the failure, redirect the row, or fail the component.</span></span>  
  
### <a name="description"></a><span data-ttu-id="e838d-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="e838d-119">Description</span></span>  
 <span data-ttu-id="e838d-120">No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="e838d-120">Not used.</span></span>  
  
### <a name="set-this-value-to-selected-cells"></a><span data-ttu-id="e838d-121">Establecer este valor en las celdas seleccionadas</span><span class="sxs-lookup"><span data-stu-id="e838d-121">Set this value to selected cells</span></span>  
 <span data-ttu-id="e838d-122">Seleccione cómo el origen de ODBC va a controlar todas las celdas seleccionadas cuando se produzca un error o un truncamiento: omitir el error, redirigir la fila o hacer que el componente no funcione.</span><span class="sxs-lookup"><span data-stu-id="e838d-122">Select how the ODBC source handles all selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
### <a name="apply"></a><span data-ttu-id="e838d-123">Aplicar</span><span class="sxs-lookup"><span data-stu-id="e838d-123">Apply</span></span>  
 <span data-ttu-id="e838d-124">Aplica las opciones de control de errores a las celdas seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="e838d-124">Apply the error handling options to the selected cells.</span></span>  
  
## <a name="error-handling-options"></a><span data-ttu-id="e838d-125">Opciones de control de errores</span><span class="sxs-lookup"><span data-stu-id="e838d-125">Error Handling Options</span></span>  
 <span data-ttu-id="e838d-126">Use las opciones siguientes para configurar la forma en la que el origen de ODBC controla errores y truncamientos.</span><span class="sxs-lookup"><span data-stu-id="e838d-126">You use the following options to configure how the ODBC source handles errors and truncations.</span></span>  
  
### <a name="fail-component"></a><span data-ttu-id="e838d-127">Error de componente</span><span class="sxs-lookup"><span data-stu-id="e838d-127">Fail Component</span></span>  
 <span data-ttu-id="e838d-128">La tarea Flujo de datos genera un error cuando se produce un error o truncamiento.</span><span class="sxs-lookup"><span data-stu-id="e838d-128">The Data Flow task fails when an error or a truncation occurs.</span></span> <span data-ttu-id="e838d-129">Este es el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e838d-129">This is the default behavior.</span></span>  
  
### <a name="ignore-failure"></a><span data-ttu-id="e838d-130">Omitir error</span><span class="sxs-lookup"><span data-stu-id="e838d-130">Ignore Failure</span></span>  
 <span data-ttu-id="e838d-131">Se omite el error o el truncamiento.</span><span class="sxs-lookup"><span data-stu-id="e838d-131">The error or the truncation is ignored.</span></span>  
  
### <a name="redirect-flow"></a><span data-ttu-id="e838d-132">Redirigir fila</span><span class="sxs-lookup"><span data-stu-id="e838d-132">Redirect Flow</span></span>  
 <span data-ttu-id="e838d-133">La fila que está produciendo el error o el truncamiento se dirige a la salida de error del origen de ODBC.</span><span class="sxs-lookup"><span data-stu-id="e838d-133">The row that is causing the error or the truncation is directed to the error output of the ODBC source.</span></span> <span data-ttu-id="e838d-134">Para más información, consulte [ODBC Source](data-flow/odbc-source.md).</span><span class="sxs-lookup"><span data-stu-id="e838d-134">For more information, see [ODBC Source](data-flow/odbc-source.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e838d-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e838d-135">See Also</span></span>  
 <span data-ttu-id="e838d-136">[Editor de origen de ODBC &#40;página Administrador de conexiones&#41;](../../2014/integration-services/odbc-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="e838d-136">[ODBC Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/odbc-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="e838d-137">Editor de orígenes ODBC &#40;página Columnas&#41;</span><span class="sxs-lookup"><span data-stu-id="e838d-137">ODBC Source Editor &#40;Columns Page&#41;</span></span>](../../2014/integration-services/odbc-source-editor-columns-page.md)  
  
  
