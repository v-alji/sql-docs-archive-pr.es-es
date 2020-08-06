---
title: Editor de origen de CDC (página columnas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.cdcsource.columns.f1
ms.assetid: bcf3030e-98d8-4445-967c-33c3f8ecb4fc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: aa30defb5e6873ea05e8e41c733477cf50d0dc4f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676623"
---
# <a name="cdc-source-editor-columns-page"></a><span data-ttu-id="c6513-102">Editor de origen de CDC (página Columnas)</span><span class="sxs-lookup"><span data-stu-id="c6513-102">CDC Source Editor (Columns Page)</span></span>
  <span data-ttu-id="c6513-103">Use la página **Columnas** del cuadro de diálogo **Editor de origen de CDC** para asignar una columna de salida a cada columna externa (origen).</span><span class="sxs-lookup"><span data-stu-id="c6513-103">Use the **Columns** page of the **CDC Source Editor** dialog box to map an output column to each external (source) column.</span></span>  
  
 <span data-ttu-id="c6513-104">Para obtener más información acerca del origen de CDC, vea [CDC Source](data-flow/cdc-source.md).</span><span class="sxs-lookup"><span data-stu-id="c6513-104">To learn more about the CDC source, see [CDC Source](data-flow/cdc-source.md).</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="c6513-105">Lista de tareas</span><span class="sxs-lookup"><span data-stu-id="c6513-105">Task List</span></span>  
 <span data-ttu-id="c6513-106">**Para abrir la página Columnas del Editor de origen de CDC**</span><span class="sxs-lookup"><span data-stu-id="c6513-106">**To open the CDC Source Editor Columns Page**</span></span>  
  
1.  <span data-ttu-id="c6513-107">En [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], abra el paquete [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] que tiene el origen de CDC.</span><span class="sxs-lookup"><span data-stu-id="c6513-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the CDC source.</span></span>  
  
2.  <span data-ttu-id="c6513-108">En la pestaña **Flujo de datos** , haga doble clic en el origen de CDC.</span><span class="sxs-lookup"><span data-stu-id="c6513-108">On the **Data Flow** tab, double-click the CDC source.</span></span>  
  
3.  <span data-ttu-id="c6513-109">En el **Editor de origen de CDC**, haga clic en **Columnas**.</span><span class="sxs-lookup"><span data-stu-id="c6513-109">In the **CDC Source Editor**, click **Columns**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c6513-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="c6513-110">Options</span></span>  
 <span data-ttu-id="c6513-111">**Columnas externas disponibles**</span><span class="sxs-lookup"><span data-stu-id="c6513-111">**Available External Columns**</span></span>  
 <span data-ttu-id="c6513-112">Lista de las columnas externas disponibles en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="c6513-112">A list of available external columns in the data source.</span></span> <span data-ttu-id="c6513-113">Esta tabla no se puede usar para agregar o quitar columnas.</span><span class="sxs-lookup"><span data-stu-id="c6513-113">You cannot use this table to add or delete columns.</span></span> <span data-ttu-id="c6513-114">Seleccione las columnas que se van a usar en el origen.</span><span class="sxs-lookup"><span data-stu-id="c6513-114">Select the columns to use in the source.</span></span> <span data-ttu-id="c6513-115">Las columnas seleccionadas se agregan a la lista **Columna externa** en el orden en que se seleccionan.</span><span class="sxs-lookup"><span data-stu-id="c6513-115">The selected columns are added to the **External Column** list in the order they are selected.</span></span>  
  
 <span data-ttu-id="c6513-116">**Columna externa**</span><span class="sxs-lookup"><span data-stu-id="c6513-116">**External Column**</span></span>  
 <span data-ttu-id="c6513-117">Vista de las columnas externas (origen) en el orden en que se verán cuando configure componentes que usen datos del origen de CDC.</span><span class="sxs-lookup"><span data-stu-id="c6513-117">A view of the external (source) columns in the order that you see them when configuring components that consume data from the CDC source.</span></span> <span data-ttu-id="c6513-118">Para cambiar este orden, en primer lugar borre las columnas seleccionadas en la lista **Columnas externas disponibles** y, a continuación, seleccione las columnas externas en la lista en un orden diferente.</span><span class="sxs-lookup"><span data-stu-id="c6513-118">To change this order, first clear the selected columns in the **Available External Columns** list, and then select external columns from the list in a different order.</span></span> <span data-ttu-id="c6513-119">Las columnas seleccionadas se agregan a la lista **Columna externa** en el orden en que las haya seleccionado.</span><span class="sxs-lookup"><span data-stu-id="c6513-119">The selected columns are added to the **External Column** list in the order you select them.</span></span>  
  
 <span data-ttu-id="c6513-120">**Columna de salida**</span><span class="sxs-lookup"><span data-stu-id="c6513-120">**Output Column**</span></span>  
 <span data-ttu-id="c6513-121">Especifique un nombre único para cada columna de salida.</span><span class="sxs-lookup"><span data-stu-id="c6513-121">Enter a unique name for each output column.</span></span> <span data-ttu-id="c6513-122">El nombre predeterminado es el nombre de la columna externa (origen) seleccionada; sin embargo, puede elegir cualquier nombre único y descriptivo.</span><span class="sxs-lookup"><span data-stu-id="c6513-122">The default is the name of the selected external (source) column, however you can choose any unique, descriptive name.</span></span> <span data-ttu-id="c6513-123">El nombre especificado se muestra en el Diseñador de SSIS.</span><span class="sxs-lookup"><span data-stu-id="c6513-123">The name entered is displayed in the SSIS Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6513-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c6513-124">See Also</span></span>  
 <span data-ttu-id="c6513-125">[Editor de origen de CDC &#40;página Administrador de conexiones&#41;](../../2014/integration-services/cdc-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="c6513-125">[CDC Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/cdc-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="c6513-126">Editor de origen de CDC &#40;página Salida de error&#41;</span><span class="sxs-lookup"><span data-stu-id="c6513-126">CDC Source Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/cdc-source-editor-error-output-page.md)  
  
  
