---
title: Conectar componentes con rutas de acceso | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- data flow [Integration Services], connections
- components [Integration Services], connections
- connections [Integration Services], data flow components
ms.assetid: 05633e4c-1370-4b05-802b-f36b07dd71c8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e11955601406406abe48b53197e95c8224762fee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748870"
---
# <a name="connect-components-with-paths"></a><span data-ttu-id="36212-102">Conectar componentes con rutas de acceso</span><span class="sxs-lookup"><span data-stu-id="36212-102">Connect Components with Paths</span></span>
  <span data-ttu-id="36212-103">El flujo de datos de un paquete se genera en la superficie de diseño de la pestaña **Flujo de datos** en el Diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="36212-103">You construct the data flow in a package on the design surface of the **Data Flow** tab in the [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="36212-104">Si un flujo de datos contiene dos componentes de flujo de datos, puede conectar ambos conectando la salida de un origen o transformación con la entrada de una transformación o destino.</span><span class="sxs-lookup"><span data-stu-id="36212-104">If a data flow contains two data flow components, you can connect them by connecting the output of a source or transformation to the input of a transformation or destination.</span></span> <span data-ttu-id="36212-105">El conector entre dos componentes de flujo de datos se denomina ruta.</span><span class="sxs-lookup"><span data-stu-id="36212-105">The connector between two data flow components is called a path.</span></span>

 <span data-ttu-id="36212-106">El siguiente diagrama muestra un flujo de datos simple con un componente de origen, dos transformaciones, un componente de destino y las rutas que los conectan.</span><span class="sxs-lookup"><span data-stu-id="36212-106">The following diagram shows a simple data flow with a source component, two transformations, a destination component, and the paths that connect them.</span></span>

 <span data-ttu-id="36212-107">![Flujo de datos](media/mw-dts-08.gif "Flujo de datos")</span><span class="sxs-lookup"><span data-stu-id="36212-107">![Data flow](media/mw-dts-08.gif "Data flow")</span></span>

 <span data-ttu-id="36212-108">Una vez conectados dos componentes, puede ver los metadatos de los datos que se mueven por la ruta y las propiedades de la ruta en el **Editor de rutas de flujo de datos**.</span><span class="sxs-lookup"><span data-stu-id="36212-108">After two components are connected, you can view the metadata of the data that moves through the path and the properties of the path in **Data Flow Path Editor**.</span></span> <span data-ttu-id="36212-109">Para más información, consulte [Integration Services Paths](data-flow/integration-services-paths.md).</span><span class="sxs-lookup"><span data-stu-id="36212-109">For more information, see [Integration Services Paths](data-flow/integration-services-paths.md).</span></span>

 <span data-ttu-id="36212-110">También puede agregar visores de datos a las rutas.</span><span class="sxs-lookup"><span data-stu-id="36212-110">You can also add data viewers to paths.</span></span> <span data-ttu-id="36212-111">Un visor de datos permite ver los datos que se mueven entre los componentes de flujo de datos cuando se ejecuta el paquete.</span><span class="sxs-lookup"><span data-stu-id="36212-111">A data viewer makes it possible to view data moving between data flow components when the package is run.</span></span>

### <a name="to-connect-components-in-a-data-flow"></a><span data-ttu-id="36212-112">Para conectar los componentes de un flujo de datos</span><span class="sxs-lookup"><span data-stu-id="36212-112">To connect components in a data flow</span></span>

-   [<span data-ttu-id="36212-113">Conectar componentes de un flujo de datos</span><span class="sxs-lookup"><span data-stu-id="36212-113">Connect Components in a Data Flow</span></span>](data-flow/connect-components-in-a-data-flow.md)

### <a name="to-set-path-properties"></a><span data-ttu-id="36212-114">Para establecer las propiedades de la ruta</span><span class="sxs-lookup"><span data-stu-id="36212-114">To set path properties</span></span>

-   [<span data-ttu-id="36212-115">Establecer las propiedades de una ruta con el Editor de rutas de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="36212-115">Set the Properties of a Path by Using the Data Flow Path Editor</span></span>](../../2014/integration-services/set-the-properties-of-a-path-by-using-the-data-flow-path-editor.md)

### <a name="to-view-path-metadata"></a><span data-ttu-id="36212-116">Para ver metadatos de ruta</span><span class="sxs-lookup"><span data-stu-id="36212-116">To view path metadata</span></span>

-   [<span data-ttu-id="36212-117">Ver los metadatos de rutas con el Editor de rutas de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="36212-117">View Path Metadata in the Data Flow Path Editor</span></span>](../../2014/integration-services/view-path-metadata-in-the-data-flow-path-editor.md)

### <a name="to-view-path-metadata"></a><span data-ttu-id="36212-118">Para ver metadatos de ruta</span><span class="sxs-lookup"><span data-stu-id="36212-118">To view path metadata</span></span>

-   [<span data-ttu-id="36212-119">Agregar un visor de datos a un flujo de datos</span><span class="sxs-lookup"><span data-stu-id="36212-119">Add a Data Viewer to a Data Flow</span></span>](../../2014/integration-services/add-a-data-viewer-to-a-data-flow.md)

## <a name="see-also"></a><span data-ttu-id="36212-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="36212-120">See Also</span></span>
 <span data-ttu-id="36212-121">[Flujo](data-flow/data-flow.md) de datos de la [tarea flujo](control-flow/data-flow-task.md) de datos [transformar datos con transformaciones](data-flow/transformations/transform-data-with-transformations.md) [control de errores en los datos](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="36212-121">[Data Flow Task](control-flow/data-flow-task.md) [Data Flow](data-flow/data-flow.md) [Transform Data with Transformations](data-flow/transformations/transform-data-with-transformations.md) [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>


