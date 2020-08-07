---
title: Editor de origen de ODBC (página columnas) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.odbcsource.columns.f1
ms.assetid: 565984eb-8318-4be7-bebc-262209cf5065
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7a11ab6a86978366d07fbe63362f1702310b5d89
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747137"
---
# <a name="odbc-source-editor-columns-page"></a><span data-ttu-id="75417-102">Editor de origen de ODBC (página Columnas)</span><span class="sxs-lookup"><span data-stu-id="75417-102">ODBC Source Editor (Columns Page)</span></span>
  <span data-ttu-id="75417-103">Use la página **Columnas** del cuadro de diálogo **Editor de orígenes ODBC** para asignar una columna de salida a cada columna externa (origen).</span><span class="sxs-lookup"><span data-stu-id="75417-103">Use the **Columns** page of the **ODBC Source Editor** dialog box to map an output column to each external (source) column.</span></span>  
  
 <span data-ttu-id="75417-104">Para obtener más información acerca del origen de ODBC, vea [ODBC Source](data-flow/odbc-source.md).</span><span class="sxs-lookup"><span data-stu-id="75417-104">To learn more about the ODBC source, see [ODBC Source](data-flow/odbc-source.md).</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="75417-105">Lista de tareas</span><span class="sxs-lookup"><span data-stu-id="75417-105">Task List</span></span>  
 <span data-ttu-id="75417-106">**Para abrir la página Columnas del Editor de origen de ODBC**</span><span class="sxs-lookup"><span data-stu-id="75417-106">**To open the ODBC Source Editor Columns Page**</span></span>  
  
1.  <span data-ttu-id="75417-107">En [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], abra el paquete [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] que tiene el origen de ODBC.</span><span class="sxs-lookup"><span data-stu-id="75417-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the ODBC source.</span></span>  
  
2.  <span data-ttu-id="75417-108">En la pestaña **Flujo de datos** , haga doble clic en el origen de ODBC.</span><span class="sxs-lookup"><span data-stu-id="75417-108">On the **Data Flow** tab, double-click the ODBC source.</span></span>  
  
3.  <span data-ttu-id="75417-109">En el **Editor de origen de ODBC**, haga clic en **Columnas**.</span><span class="sxs-lookup"><span data-stu-id="75417-109">In the **ODBC Source Editor**, click **Columns**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="75417-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="75417-110">Options</span></span>  
  
### <a name="available-external-columns"></a><span data-ttu-id="75417-111">Columnas externas disponibles</span><span class="sxs-lookup"><span data-stu-id="75417-111">Available External Columns</span></span>  
 <span data-ttu-id="75417-112">Lista de las columnas externas disponibles en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="75417-112">A list of available external columns in the data source.</span></span> <span data-ttu-id="75417-113">Esta tabla no se puede usar para agregar o quitar columnas.</span><span class="sxs-lookup"><span data-stu-id="75417-113">You cannot use this table to add or delete columns.</span></span> <span data-ttu-id="75417-114">Seleccione las columnas que se van a usar desde el origen.</span><span class="sxs-lookup"><span data-stu-id="75417-114">Select the columns to use from the source.</span></span> <span data-ttu-id="75417-115">Las columnas seleccionadas se agregan a la lista **Columna externa** en el orden en que se seleccionan.</span><span class="sxs-lookup"><span data-stu-id="75417-115">The selected columns are added to the **External Column** list in the order they are selected.</span></span>  
  
 <span data-ttu-id="75417-116">Active la casilla **Seleccionar todas** para seleccionar todas las columnas.</span><span class="sxs-lookup"><span data-stu-id="75417-116">Select the **Select All** check box to select all of the columns.</span></span>  
  
### <a name="external-column"></a><span data-ttu-id="75417-117">Columna externa</span><span class="sxs-lookup"><span data-stu-id="75417-117">External Column</span></span>  
 <span data-ttu-id="75417-118">Vista de las columnas externas (origen) en el orden en que se verán cuando configure los componentes que usan datos del origen de ODBC.</span><span class="sxs-lookup"><span data-stu-id="75417-118">A view of the external (source) columns in the order that you see them when configuring components that consume data from the ODBC source.</span></span>  
  
### <a name="output-column"></a><span data-ttu-id="75417-119">Columna de salida</span><span class="sxs-lookup"><span data-stu-id="75417-119">Output Column</span></span>  
 <span data-ttu-id="75417-120">Especifique un nombre único para cada columna de salida.</span><span class="sxs-lookup"><span data-stu-id="75417-120">Enter a unique name for each output column.</span></span> <span data-ttu-id="75417-121">El nombre predeterminado es el nombre de la columna externa (origen) seleccionada; sin embargo, puede elegir un nombre único y descriptivo.</span><span class="sxs-lookup"><span data-stu-id="75417-121">The default is the name of the selected external (source) column; however, you can choose any unique, descriptive name.</span></span> <span data-ttu-id="75417-122">El nombre especificado se muestra en el Diseñador de SSIS.</span><span class="sxs-lookup"><span data-stu-id="75417-122">The name entered is displayed in the SSIS Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75417-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="75417-123">See Also</span></span>  
 <span data-ttu-id="75417-124">[Editor de origen de ODBC &#40;página Administrador de conexiones&#41;](../../2014/integration-services/odbc-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="75417-124">[ODBC Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/odbc-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="75417-125">Editor de orígenes ODBC &#40;página Salida de error&#41;</span><span class="sxs-lookup"><span data-stu-id="75417-125">ODBC Source Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/odbc-source-editor-error-output-page.md)  
  
  
