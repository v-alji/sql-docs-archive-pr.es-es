---
title: Editor de orígenes de ADO NET (página columnas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.adonetsource.columns.f1
ms.assetid: fbc205b9-2001-4737-a76b-1ba777344bd9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0d89f8c926761b9149f19269bc2519c12bcf130e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673229"
---
# <a name="ado-net-source-editor-columns-page"></a><span data-ttu-id="1b31f-102">Editor de orígenes de ADO NET (página Columnas)</span><span class="sxs-lookup"><span data-stu-id="1b31f-102">ADO NET Source Editor (Columns Page)</span></span>
  <span data-ttu-id="1b31f-103">Use la página **Columnas** del cuadro de diálogo **Editor de orígenes de ADO NET** para asignar una columna de salida a cada columna externa (origen).</span><span class="sxs-lookup"><span data-stu-id="1b31f-103">Use the **Columns** page of the **ADO NET Source Editor** dialog box to map an output column to each external (source) column.</span></span>  
  
 <span data-ttu-id="1b31f-104">Para obtener más información acerca del origen de ADO NET, vea [ADO NET Source](data-flow/ado-net-source.md).</span><span class="sxs-lookup"><span data-stu-id="1b31f-104">To learn more about the ADO NET source, see [ADO NET Source](data-flow/ado-net-source.md).</span></span>  
  
 <span data-ttu-id="1b31f-105">**Para abrir la página Columnas**</span><span class="sxs-lookup"><span data-stu-id="1b31f-105">**To open the Columns page**</span></span>  
  
1.  <span data-ttu-id="1b31f-106">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el paquete [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que tiene el origen de ADO NET.</span><span class="sxs-lookup"><span data-stu-id="1b31f-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that has the ADO NET source.</span></span>  
  
2.  <span data-ttu-id="1b31f-107">En la pestaña **Flujo de datos** , haga doble clic en el origen de ADO NET.</span><span class="sxs-lookup"><span data-stu-id="1b31f-107">On the **Data Flow** tab, double-click the ADO NET source.</span></span>  
  
3.  <span data-ttu-id="1b31f-108">En el **Editor de orígenes de ADO NET**, haga clic en **Columnas**.</span><span class="sxs-lookup"><span data-stu-id="1b31f-108">In the **ADO NET Source Editor**, click **Columns**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1b31f-109">Opciones</span><span class="sxs-lookup"><span data-stu-id="1b31f-109">Options</span></span>  
 <span data-ttu-id="1b31f-110">**Columnas externas disponibles**</span><span class="sxs-lookup"><span data-stu-id="1b31f-110">**Available External Columns**</span></span>  
 <span data-ttu-id="1b31f-111">Muestra la lista de columnas externas disponibles en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="1b31f-111">View the list of available external columns in the data source.</span></span> <span data-ttu-id="1b31f-112">Esta tabla no se puede usar para agregar o quitar columnas.</span><span class="sxs-lookup"><span data-stu-id="1b31f-112">You cannot use this table to add or delete columns.</span></span>  
  
 <span data-ttu-id="1b31f-113">**Columna externa**</span><span class="sxs-lookup"><span data-stu-id="1b31f-113">**External Column**</span></span>  
 <span data-ttu-id="1b31f-114">Muestra las columnas externas (origen) en el orden en que se verán cuando configure componentes que utilizan datos de este origen.</span><span class="sxs-lookup"><span data-stu-id="1b31f-114">View external (source) columns in the order in which you will see them when configuring components that consume data from this source.</span></span>  
  
 <span data-ttu-id="1b31f-115">**Columna de salida**</span><span class="sxs-lookup"><span data-stu-id="1b31f-115">**Output Column**</span></span>  
 <span data-ttu-id="1b31f-116">Permite proporcionar un nombre único para cada columna de salida.</span><span class="sxs-lookup"><span data-stu-id="1b31f-116">Provide a unique name for each output column.</span></span> <span data-ttu-id="1b31f-117">El nombre predeterminado es el nombre de la columna externa (origen) seleccionada; sin embargo, puede elegir un nombre único y descriptivo.</span><span class="sxs-lookup"><span data-stu-id="1b31f-117">The default is the name of the selected external (source) column; however, you can choose any unique, descriptive name.</span></span> <span data-ttu-id="1b31f-118">El nombre proporcionado se mostrará en el Diseñador de [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1b31f-118">The name provided will be displayed within the [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b31f-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1b31f-119">See Also</span></span>  
 <span data-ttu-id="1b31f-120">[Editor de orígenes de ADO NET &#40;página Administrador de conexiones&#41;](../../2014/integration-services/ado-net-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="1b31f-120">[ADO NET Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/ado-net-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="1b31f-121">[Editor de orígenes de ADO NET &#40;página salida de error&#41;](../../2014/integration-services/ado-net-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="1b31f-121">[ADO NET Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/ado-net-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="1b31f-122">Administrador de conexiones ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1b31f-122">ADO.NET Connection Manager</span></span>](connection-manager/ado-net-connection-manager.md)  
  
  
