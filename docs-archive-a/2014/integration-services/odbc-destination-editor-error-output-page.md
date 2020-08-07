---
title: Editor de destino de ODBC (página salida de error) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.odbcdest.errorhandling.f1
ms.assetid: 0a743f8d-2a51-4296-9976-8104f5ca22d3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 475a2e00d67b221ddf05fdd273317fbab5248cd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747139"
---
# <a name="odbc-destination-editor-error-output-page"></a><span data-ttu-id="a5c36-102">Editor de destinos de ODBC (página Salida de error)</span><span class="sxs-lookup"><span data-stu-id="a5c36-102">ODBC Destination Editor (Error Output Page)</span></span>
  <span data-ttu-id="a5c36-103">Use la página **Salida de error** del cuadro de diálogo **Editor de destinos de ODBC** para seleccionar las opciones de control de errores.</span><span class="sxs-lookup"><span data-stu-id="a5c36-103">Use the **Error Output** page of the **ODBC Destination Editor** dialog box to select error handling options.</span></span>  
  
 <span data-ttu-id="a5c36-104">Para obtener más información acerca del destino de ODBC, vea [ODBC Destination](data-flow/odbc-destination.md).</span><span class="sxs-lookup"><span data-stu-id="a5c36-104">To learn more about the ODBC destination, see [ODBC Destination](data-flow/odbc-destination.md).</span></span>  
  
 <span data-ttu-id="a5c36-105">**Para abrir la página Salida de error del Editor de destinos de ODBC**</span><span class="sxs-lookup"><span data-stu-id="a5c36-105">**To open the ODBC Destination Editor Error Output Page**</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="a5c36-106">Lista de tareas</span><span class="sxs-lookup"><span data-stu-id="a5c36-106">Task List</span></span>  
  
-   <span data-ttu-id="a5c36-107">En [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], abra el paquete [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] que tiene el destino de ODBC.</span><span class="sxs-lookup"><span data-stu-id="a5c36-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the ODBC destination.</span></span>  
  
-   <span data-ttu-id="a5c36-108">En la pestaña **Flujo de datos** , haga doble clic en el destino de ODBC.</span><span class="sxs-lookup"><span data-stu-id="a5c36-108">On the **Data Flow** tab, double-click the ODBC destination.</span></span>  
  
-   <span data-ttu-id="a5c36-109">En el **Editor de destinos de ODBC**, haga clic en **Salida de error**.</span><span class="sxs-lookup"><span data-stu-id="a5c36-109">In the **ODBC Destination Editor**, click **Error Output**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a5c36-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="a5c36-110">Options</span></span>  
  
### <a name="inputoutput"></a><span data-ttu-id="a5c36-111">Entrada/salida</span><span class="sxs-lookup"><span data-stu-id="a5c36-111">Input/Output</span></span>  
 <span data-ttu-id="a5c36-112">Muestra el nombre del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="a5c36-112">View the name of the data source.</span></span>  
  
### <a name="column"></a><span data-ttu-id="a5c36-113">Columna</span><span class="sxs-lookup"><span data-stu-id="a5c36-113">Column</span></span>  
 <span data-ttu-id="a5c36-114">No se usa.</span><span class="sxs-lookup"><span data-stu-id="a5c36-114">Not used.</span></span>  
  
### <a name="error"></a><span data-ttu-id="a5c36-115">Error</span><span class="sxs-lookup"><span data-stu-id="a5c36-115">Error</span></span>  
 <span data-ttu-id="a5c36-116">Seleccione la forma en la que el destino de ODBC debe controlar errores en un flujo: omitir el error, redirigir la fila o hacer que el componente no funcione.</span><span class="sxs-lookup"><span data-stu-id="a5c36-116">Select how the ODBC destination should handle errors in a flow: ignore the failure, redirect the row, or fail the component.</span></span>  
  
### <a name="truncation"></a><span data-ttu-id="a5c36-117">Truncamiento</span><span class="sxs-lookup"><span data-stu-id="a5c36-117">Truncation</span></span>  
 <span data-ttu-id="a5c36-118">Seleccione la forma en la que el destino de ODBC debe controlar los truncamientos en un flujo: omitir el error, redirigir la fila o hacer que el componente no funcione.</span><span class="sxs-lookup"><span data-stu-id="a5c36-118">Select how the ODBC destination should handle truncation in a flow: ignore the failure, redirect the row, or fail the component.</span></span>  
  
### <a name="description"></a><span data-ttu-id="a5c36-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="a5c36-119">Description</span></span>  
 <span data-ttu-id="a5c36-120">Muestra una descripción del error.</span><span class="sxs-lookup"><span data-stu-id="a5c36-120">View a description of the error.</span></span>  
  
### <a name="set-this-value-to-selected-cells"></a><span data-ttu-id="a5c36-121">Establecer este valor en las celdas seleccionadas</span><span class="sxs-lookup"><span data-stu-id="a5c36-121">Set this value to selected cells</span></span>  
 <span data-ttu-id="a5c36-122">Seleccione la forma en la que el destino de ODBC controla todas las celdas seleccionadas cuando se produce un error o un truncamiento: omitir el error, redirigir la fila o hacer que el componente no funcione.</span><span class="sxs-lookup"><span data-stu-id="a5c36-122">Select how the ODBC destination handles all selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
### <a name="apply"></a><span data-ttu-id="a5c36-123">Aplicar</span><span class="sxs-lookup"><span data-stu-id="a5c36-123">Apply</span></span>  
 <span data-ttu-id="a5c36-124">Aplica las opciones de control de errores a las celdas seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="a5c36-124">Apply the error handling options to the selected cells.</span></span>  
  
## <a name="error-handling-options"></a><span data-ttu-id="a5c36-125">Opciones de control de errores</span><span class="sxs-lookup"><span data-stu-id="a5c36-125">Error Handling Options</span></span>  
 <span data-ttu-id="a5c36-126">Use las opciones siguientes para configurar la forma en la que el destino de ODBC controla errores y truncamientos.</span><span class="sxs-lookup"><span data-stu-id="a5c36-126">You use the following options to configure how the ODBC destination handles errors and truncations.</span></span>  
  
### <a name="fail-component"></a><span data-ttu-id="a5c36-127">Error de componente</span><span class="sxs-lookup"><span data-stu-id="a5c36-127">Fail Component</span></span>  
 <span data-ttu-id="a5c36-128">La tarea Flujo de datos genera un error cuando se produce un error o truncamiento.</span><span class="sxs-lookup"><span data-stu-id="a5c36-128">The Data Flow task fails when an error or a truncation occurs.</span></span> <span data-ttu-id="a5c36-129">Este es el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a5c36-129">This is the default behavior.</span></span>  
  
### <a name="ignore-failure"></a><span data-ttu-id="a5c36-130">Omitir error</span><span class="sxs-lookup"><span data-stu-id="a5c36-130">Ignore Failure</span></span>  
 <span data-ttu-id="a5c36-131">Se omite el error o el truncamiento.</span><span class="sxs-lookup"><span data-stu-id="a5c36-131">The error or the truncation is ignored.</span></span>  
  
### <a name="redirect-flow"></a><span data-ttu-id="a5c36-132">Redirigir fila</span><span class="sxs-lookup"><span data-stu-id="a5c36-132">Redirect Flow</span></span>  
 <span data-ttu-id="a5c36-133">La fila que está produciendo el error o el truncamiento se dirige a la salida de error del destino de ODBC.</span><span class="sxs-lookup"><span data-stu-id="a5c36-133">The row that is causing the error or the truncation is directed to the error output of the ODBC destination.</span></span> <span data-ttu-id="a5c36-134">Para obtener más información, vea Destino de ODBC.</span><span class="sxs-lookup"><span data-stu-id="a5c36-134">For more information, see ODBC Destination.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5c36-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a5c36-135">See Also</span></span>  
 <span data-ttu-id="a5c36-136">[Editor de destino de ODBC &#40;página Administrador de conexiones&#41;](../../2014/integration-services/odbc-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="a5c36-136">[ODBC Destination Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/odbc-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="a5c36-137">Editor de destino de ODBC &#40;página Asignaciones&#41;</span><span class="sxs-lookup"><span data-stu-id="a5c36-137">ODBC Destination Editor &#40;Mappings Page&#41;</span></span>](../../2014/integration-services/odbc-destination-editor-mappings-page.md)  
  
  
