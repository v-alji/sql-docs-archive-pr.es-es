---
title: Rutas de Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- paths [Integration Services], about paths
- data flow [Integration Services], paths
- paths [Integration Services]
- destinations [Integration Services], paths
- sources [Integration Services], paths
ms.assetid: 6c4629a9-2ede-4011-9101-3b342249640e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c52bbd06974311a7fc94b3058309399d70df0034
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745935"
---
# <a name="integration-services-paths"></a><span data-ttu-id="76e10-102">Rutas de Integration Services</span><span class="sxs-lookup"><span data-stu-id="76e10-102">Integration Services Paths</span></span>
  <span data-ttu-id="76e10-103">Una ruta conecta dos componentes en un flujo de datos conectando la salida de un componente de flujo de datos con la entrada de otro componente.</span><span class="sxs-lookup"><span data-stu-id="76e10-103">A path connects two components in a data flow by connecting the output of one data flow component to the input of another component.</span></span> <span data-ttu-id="76e10-104">Una ruta tiene un origen y un destino.</span><span class="sxs-lookup"><span data-stu-id="76e10-104">A path has a source and a destination.</span></span> <span data-ttu-id="76e10-105">Por ejemplo, si una ruta conecta un origen de OLE DB y una transformación Ordenar, el origen de OLE DB es el origen de la ruta y la transformación Ordenar es el destino de la ruta.</span><span class="sxs-lookup"><span data-stu-id="76e10-105">For example, if a path connects an OLE DB source and a Sort transformation, the OLE DB source is the source of the path, and the Sort transformation is the destination of the path.</span></span> <span data-ttu-id="76e10-106">El origen es el componente donde se inicia la ruta y el destino es el componente donde finaliza la ruta.</span><span class="sxs-lookup"><span data-stu-id="76e10-106">The source is the component where the path starts, and the destination is the component where the path ends.</span></span>  
  
 <span data-ttu-id="76e10-107">Si ejecuta un paquete en el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] , puede ver los datos en un flujo de datos adjuntando los visores de datos a una ruta.</span><span class="sxs-lookup"><span data-stu-id="76e10-107">If you run a package in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, you can view the data in a data flow by attaching data viewers to a path.</span></span> <span data-ttu-id="76e10-108">Un visor de datos se puede configurar para mostrar los datos en una cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="76e10-108">A data viewer can be configured to display data in a grid.</span></span> <span data-ttu-id="76e10-109">Un visor de datos es una herramienta de depuración útil.</span><span class="sxs-lookup"><span data-stu-id="76e10-109">A data viewer is a useful debugging tool.</span></span> <span data-ttu-id="76e10-110">Para más información, consulte [Debugging Data Flow](../troubleshooting/debugging-data-flow.md).</span><span class="sxs-lookup"><span data-stu-id="76e10-110">For more information, see [Debugging Data Flow](../troubleshooting/debugging-data-flow.md).</span></span>  
  
## <a name="configuration-of-the-path"></a><span data-ttu-id="76e10-111">Configuración de la ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="76e10-111">Configuration of the Path</span></span>  
 <span data-ttu-id="76e10-112">El Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] proporciona el cuadro de diálogo **Editor de rutas de flujo de datos** para establecer las propiedades de ruta, ver los metadatos de las columnas de datos que pasan por la ruta y configurar los visores de datos.</span><span class="sxs-lookup"><span data-stu-id="76e10-112">The [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer provides the **Data Flow Path Editor** dialog box for setting path properties, viewing the metadata of the data columns that pass through the path, and configuring data viewers.</span></span>  
  
 <span data-ttu-id="76e10-113">Entre las propiedades configurables de la ruta se incluyen el nombre, descripción y anotación de la ruta.</span><span class="sxs-lookup"><span data-stu-id="76e10-113">The configurable path properties include the name, description, and annotation of the path.</span></span> <span data-ttu-id="76e10-114">También puede configurar rutas mediante programación.</span><span class="sxs-lookup"><span data-stu-id="76e10-114">You can also configure paths programmatically.</span></span> <span data-ttu-id="76e10-115">Para obtener más información, vea [Conectar componentes de flujo de datos mediante programación](../building-packages-programmatically/connecting-data-flow-components-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="76e10-115">For more information, see [Connecting Data Flow Components Programmatically](../building-packages-programmatically/connecting-data-flow-components-programmatically.md).</span></span>  
  
 <span data-ttu-id="76e10-116">Una anotación de ruta muestra el nombre del origen de ruta o el nombre de ruta en la superficie de diseño de la pestaña **Flujo de datos** en el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="76e10-116">A path annotation displays the name of the path source or the path name on the design surface of the **Data Flow** tab in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="76e10-117">Las anotaciones de ruta son similares a las anotaciones que se pueden agregar a los flujos de datos, flujos de control y controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="76e10-117">Path annotations are similar to the annotations you can add to data flows, control flows, and event handlers.</span></span> <span data-ttu-id="76e10-118">La única diferencia es que una anotación de ruta se adjunta a una ruta, mientras que otras anotaciones aparecen en las pestañas **Flujo de datos**, **Flujo de control**y **Controlador de eventos**del Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="76e10-118">The only difference is that a path annotation is attached to a path, whereas other annotations appear on the **Data Flow**, **Control Flow**, and **Event Handle**r tabs of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="76e10-119">Los metadatos muestran el nombre, tipo de datos, precisión, escala, longitud, página de códigos y componente de origen de cada columna en la salida del componente anterior.</span><span class="sxs-lookup"><span data-stu-id="76e10-119">The metadata shows the name, data type, precision, scale, length, code page, and source component of each column in the output of the previous component.</span></span> <span data-ttu-id="76e10-120">El componente de origen es el componente de flujo de datos que creó la columna.</span><span class="sxs-lookup"><span data-stu-id="76e10-120">The source component is the data flow component that created the column.</span></span> <span data-ttu-id="76e10-121">Este componente puede ser el primero en el flujo de datos, o puede no serlo.</span><span class="sxs-lookup"><span data-stu-id="76e10-121">This may or may not be the first component in the data flow.</span></span> <span data-ttu-id="76e10-122">Por ejemplo, las transformaciones Unión de todo y Ordenar crean sus propias columnas, y son los orígenes de sus columnas de salida.</span><span class="sxs-lookup"><span data-stu-id="76e10-122">For example, the Union All and Sort transformations create their own columns, and they are the sources of their output columns.</span></span> <span data-ttu-id="76e10-123">Por otro lado, una transformación Copiar columna puede pasar por columnas sin modificarlas o puede crear nuevas columnas copiando columnas de entrada.</span><span class="sxs-lookup"><span data-stu-id="76e10-123">In contrast, a Copy Column transformation can pass through columns without changing them or can create new columns by copying input columns.</span></span> <span data-ttu-id="76e10-124">La transformación Copiar columna es el componente de origen solamente de las nuevas columnas.</span><span class="sxs-lookup"><span data-stu-id="76e10-124">The Copy Column transformation is the source component only of the new columns.</span></span>  
  
 <span data-ttu-id="76e10-125">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="76e10-125">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="76e10-126">Para obtener más información sobre las propiedades que se pueden establecer en el cuadro de diálogo **Editor de rutas de flujo de datos** , haga clic en uno de los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="76e10-126">For more information about the properties that you can set in the **Data Flow Path Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="76e10-127">Editor de rutas de flujo de datos &#40;página general&#41;</span><span class="sxs-lookup"><span data-stu-id="76e10-127">Data Flow Path Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="76e10-128">Editor de rutas de flujo de datos &#40;página de metadatos&#41;</span><span class="sxs-lookup"><span data-stu-id="76e10-128">Data Flow Path Editor &#40;Metadata Page&#41;</span></span>](../data-flow-path-editor-metadata-page.md)  
  
-   [<span data-ttu-id="76e10-129">Editor de rutas de flujo de datos &#40;página visores de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="76e10-129">Data Flow Path Editor &#40;Data Viewers Page&#41;</span></span>](../data-flow-path-editor-data-viewers-page.md)  
  
 <span data-ttu-id="76e10-130">Para obtener más información acerca de las propiedades que puede establecer mediante programación, vea [Path Properties](../path-properties.md).</span><span class="sxs-lookup"><span data-stu-id="76e10-130">For more information about the properties that you can set programmatically, see [Path Properties](../path-properties.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="76e10-131">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="76e10-131">Related Tasks</span></span>  
  
-   [<span data-ttu-id="76e10-132">Ver los metadatos de rutas con el Editor de rutas de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="76e10-132">View Path Metadata in the Data Flow Path Editor</span></span>](../view-path-metadata-in-the-data-flow-path-editor.md)  
  
-   [<span data-ttu-id="76e10-133">Conectar componentes de un flujo de datos</span><span class="sxs-lookup"><span data-stu-id="76e10-133">Connect Components in a Data Flow</span></span>](connect-components-in-a-data-flow.md)  
  
## <a name="see-also"></a><span data-ttu-id="76e10-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="76e10-134">See Also</span></span>  
 [<span data-ttu-id="76e10-135">Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="76e10-135">Data Flow</span></span>](data-flow.md)  
  
  
