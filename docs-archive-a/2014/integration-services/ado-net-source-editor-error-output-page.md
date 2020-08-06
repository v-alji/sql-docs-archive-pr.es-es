---
title: Editor de orígenes de ADO NET (página salida de error) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.adonetsource.erroroutput.f1
ms.assetid: 4dd9d129-a95c-4d3a-bbbf-e84a39089950
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b9ee480caa8764d70b52b25a416f200f353d30c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749415"
---
# <a name="ado-net-source-editor-error-output-page"></a><span data-ttu-id="c0491-102">Editor de orígenes de ADO NET (página Salida de error)</span><span class="sxs-lookup"><span data-stu-id="c0491-102">ADO NET Source Editor (Error Output Page)</span></span>
  <span data-ttu-id="c0491-103">Utilice la página **Salida de error** del cuadro de diálogo **Editor de orígenes de ADO NET** para seleccionar las opciones de control de errores y para establecer las propiedades en las columnas de salida de errores.</span><span class="sxs-lookup"><span data-stu-id="c0491-103">Use the **Error Output** page of the **ADO NET Source Editor** dialog box to select error handling options and to set properties on error output columns.</span></span>  
  
 <span data-ttu-id="c0491-104">Para obtener más información acerca del origen de ADO NET, vea [ADO NET Source](data-flow/ado-net-source.md).</span><span class="sxs-lookup"><span data-stu-id="c0491-104">To learn more about the ADO NET source, see [ADO NET Source](data-flow/ado-net-source.md).</span></span>  
  
 <span data-ttu-id="c0491-105">**Para abrir la página Salida de error**</span><span class="sxs-lookup"><span data-stu-id="c0491-105">**To open the Error Output page**</span></span>  
  
1.  <span data-ttu-id="c0491-106">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el paquete [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que tiene el origen de ADO NET.</span><span class="sxs-lookup"><span data-stu-id="c0491-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that has the ADO NET source.</span></span>  
  
2.  <span data-ttu-id="c0491-107">En la pestaña **Flujo de datos** , haga doble clic en el origen de ADO NET.</span><span class="sxs-lookup"><span data-stu-id="c0491-107">On the **Data Flow** tab, double-click the ADO NET source.</span></span>  
  
3.  <span data-ttu-id="c0491-108">En el **Editor de orígenes de ADO NET**, haga clic en **Salida de error**.</span><span class="sxs-lookup"><span data-stu-id="c0491-108">In the **ADO NET Source Editor**, click **Error Output**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c0491-109">Opciones</span><span class="sxs-lookup"><span data-stu-id="c0491-109">Options</span></span>  
 <span data-ttu-id="c0491-110">**Entrada/salida**</span><span class="sxs-lookup"><span data-stu-id="c0491-110">**Input/Output**</span></span>  
 <span data-ttu-id="c0491-111">Muestra el nombre del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="c0491-111">View the name of the data source.</span></span>  
  
 <span data-ttu-id="c0491-112">**Columna**</span><span class="sxs-lookup"><span data-stu-id="c0491-112">**Column**</span></span>  
 <span data-ttu-id="c0491-113">Muestra las columnas externas (origen) que se han seleccionado en la página **Administrador de conexiones** del cuadro de diálogo **Editor de orígenes de ADO NET** .</span><span class="sxs-lookup"><span data-stu-id="c0491-113">View the external (source) columns that you selected on the **Connection Manager** page of the **ADO NET Source Editor** dialog box.</span></span>  
  
 <span data-ttu-id="c0491-114">**Error**</span><span class="sxs-lookup"><span data-stu-id="c0491-114">**Error**</span></span>  
 <span data-ttu-id="c0491-115">Permite especificar qué debe ocurrir cuando se produce un error: omitir el error, redirigir la fila o hacer que el componente no funcione.</span><span class="sxs-lookup"><span data-stu-id="c0491-115">Specify what should happen when an error occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="c0491-116">**Temas relacionados:** [Control de errores en los datos](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="c0491-116">**Related Topics:** [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>  
  
 <span data-ttu-id="c0491-117">**Truncamiento**</span><span class="sxs-lookup"><span data-stu-id="c0491-117">**Truncation**</span></span>  
 <span data-ttu-id="c0491-118">Permite especificar qué debe ocurrir cuando se produce un truncamiento: omitir el error, redirigir la fila o hacer que el componente no funcione.</span><span class="sxs-lookup"><span data-stu-id="c0491-118">Specify what should happen when a truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="c0491-119">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="c0491-119">**Description**</span></span>  
 <span data-ttu-id="c0491-120">Muestra la descripción del error.</span><span class="sxs-lookup"><span data-stu-id="c0491-120">View the description of the error.</span></span>  
  
 <span data-ttu-id="c0491-121">**Establecer este valor en las celdas seleccionadas**</span><span class="sxs-lookup"><span data-stu-id="c0491-121">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="c0491-122">Permite especificar qué debe ocurrir en todas las celdas seleccionadas cuando se produce un error o un truncamiento: omitir el error, redirigir la fila o hacer que el componente no funcione.</span><span class="sxs-lookup"><span data-stu-id="c0491-122">Specify what should happen to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="c0491-123">**Aplicar**</span><span class="sxs-lookup"><span data-stu-id="c0491-123">**Apply**</span></span>  
 <span data-ttu-id="c0491-124">Aplica la opción de control de errores a las celdas seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="c0491-124">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0491-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c0491-125">See Also</span></span>  
 <span data-ttu-id="c0491-126">[Editor de orígenes de ADO NET &#40;página Administrador de conexiones&#41;](../../2014/integration-services/ado-net-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="c0491-126">[ADO NET Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/ado-net-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="c0491-127">[Editor de orígenes de ADO NET &#40;página columnas&#41;](../../2014/integration-services/ado-net-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="c0491-127">[ADO NET Source Editor &#40;Columns Page&#41;](../../2014/integration-services/ado-net-source-editor-columns-page.md) </span></span>  
 [<span data-ttu-id="c0491-128">Administrador de conexiones ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c0491-128">ADO.NET Connection Manager</span></span>](connection-manager/ado-net-connection-manager.md)  
  
  
