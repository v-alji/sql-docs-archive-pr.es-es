---
title: Editor de destinos de ADO NET (página salida de error) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.adonetdest.erroroutput.f1
ms.assetid: 1a56c3cf-fb6a-416d-a62c-bb19fe441ae5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b9cfd69d3adec2aa617f5e9d3add35a1a6923804
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673230"
---
# <a name="ado-net-destination-editor-error-output-page"></a><span data-ttu-id="eb4cf-102">Editor de destinos de ADO NET (página Salida de error)</span><span class="sxs-lookup"><span data-stu-id="eb4cf-102">ADO NET Destination Editor (Error Output Page)</span></span>
  <span data-ttu-id="eb4cf-103">Utilice la página **Salida de error** del cuadro de diálogo **Editor de destinos de ADO NET** para especificar las opciones de control de errores.</span><span class="sxs-lookup"><span data-stu-id="eb4cf-103">Use the **Error Output** page of the **ADO NET Destination Editor** dialog box to specify error handling options.</span></span>  
  
 <span data-ttu-id="eb4cf-104">Para obtener más información acerca del destino de ADO NET, vea [ADO NET Destination](data-flow/ado-net-destination.md).</span><span class="sxs-lookup"><span data-stu-id="eb4cf-104">To learn more about the ADO NET destination, see [ADO NET Destination](data-flow/ado-net-destination.md).</span></span>  
  
 <span data-ttu-id="eb4cf-105">**Para abrir la página Salida de error**</span><span class="sxs-lookup"><span data-stu-id="eb4cf-105">**To open the Error Output page**</span></span>  
  
1.  <span data-ttu-id="eb4cf-106">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el paquete [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que tiene el destino de ADO NET.</span><span class="sxs-lookup"><span data-stu-id="eb4cf-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that has the ADO NET destination.</span></span>  
  
2.  <span data-ttu-id="eb4cf-107">En la pestaña **Flujo de datos** , haga doble clic en el destino de ADO NET.</span><span class="sxs-lookup"><span data-stu-id="eb4cf-107">On the **Data Flow** tab, double-click the ADO NET destination.</span></span>  
  
3.  <span data-ttu-id="eb4cf-108">En el **Editor de destinos de ADO NET**, haga clic en **Salida de error**.</span><span class="sxs-lookup"><span data-stu-id="eb4cf-108">In the **ADO NET Destination Editor**, click **Error Output**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="eb4cf-109">Opciones</span><span class="sxs-lookup"><span data-stu-id="eb4cf-109">Options</span></span>  
 <span data-ttu-id="eb4cf-110">**Entrada o salida**</span><span class="sxs-lookup"><span data-stu-id="eb4cf-110">**Input or Output**</span></span>  
 <span data-ttu-id="eb4cf-111">Muestra el nombre de la entrada.</span><span class="sxs-lookup"><span data-stu-id="eb4cf-111">View the name of the input.</span></span>  
  
 <span data-ttu-id="eb4cf-112">**Columna**</span><span class="sxs-lookup"><span data-stu-id="eb4cf-112">**Column**</span></span>  
 <span data-ttu-id="eb4cf-113">No se usa.</span><span class="sxs-lookup"><span data-stu-id="eb4cf-113">Not used.</span></span>  
  
 <span data-ttu-id="eb4cf-114">**Error**</span><span class="sxs-lookup"><span data-stu-id="eb4cf-114">**Error**</span></span>  
 <span data-ttu-id="eb4cf-115">Permite especificar qué debe ocurrir cuando se produce un error: omitir el error, redirigir la fila o hacer que el componente no funcione.</span><span class="sxs-lookup"><span data-stu-id="eb4cf-115">Specify what should happen when an error occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="eb4cf-116">**Temas relacionados:** [Control de errores en los datos](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="eb4cf-116">**Related Topics:** [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>  
  
 <span data-ttu-id="eb4cf-117">**Truncamiento**</span><span class="sxs-lookup"><span data-stu-id="eb4cf-117">**Truncation**</span></span>  
 <span data-ttu-id="eb4cf-118">No se usa.</span><span class="sxs-lookup"><span data-stu-id="eb4cf-118">Not used.</span></span>  
  
 <span data-ttu-id="eb4cf-119">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="eb4cf-119">**Description**</span></span>  
 <span data-ttu-id="eb4cf-120">Muestra la descripción de la operación.</span><span class="sxs-lookup"><span data-stu-id="eb4cf-120">View the description of the operation.</span></span>  
  
 <span data-ttu-id="eb4cf-121">**Establecer este valor en las celdas seleccionadas**</span><span class="sxs-lookup"><span data-stu-id="eb4cf-121">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="eb4cf-122">Permite especificar qué debe ocurrir en todas las celdas seleccionadas cuando se produce un error o un truncamiento: omitir el error, redirigir la fila o hacer que el componente no funcione.</span><span class="sxs-lookup"><span data-stu-id="eb4cf-122">Specify what should happen to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="eb4cf-123">**Aplicar**</span><span class="sxs-lookup"><span data-stu-id="eb4cf-123">**Apply**</span></span>  
 <span data-ttu-id="eb4cf-124">Aplica la opción de control de errores a las celdas seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="eb4cf-124">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb4cf-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eb4cf-125">See Also</span></span>  
 <span data-ttu-id="eb4cf-126">[Editor de destinos de ADO NET &#40;página Administrador de conexiones&#41;](../../2014/integration-services/ado-net-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="eb4cf-126">[ADO NET Destination Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/ado-net-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="eb4cf-127">Editor de destinos de ADO NET &#40;página Asignaciones&#41;</span><span class="sxs-lookup"><span data-stu-id="eb4cf-127">ADO NET Destination Editor &#40;Mappings Page&#41;</span></span>](../../2014/integration-services/ado-net-destination-editor-mappings-page.md)  
  
  
