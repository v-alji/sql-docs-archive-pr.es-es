---
title: Transformar datos con transformaciones | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- data flow [Integration Services], transformations
- transformations [Integration Services], about transformations
- transforming data [Integration Services]
ms.assetid: e1340b6f-ef75-4b14-af6f-823586eff0ed
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 952d8ea4eeea2dd8010a17a2b3deba41447b6231
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677226"
---
# <a name="transform-data-with-transformations"></a><span data-ttu-id="9ca07-102">Transformar datos con transformaciones</span><span class="sxs-lookup"><span data-stu-id="9ca07-102">Transform Data with Transformations</span></span>
  [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="9ca07-103">incluye tres tipos de componentes de flujo de datos: orígenes, transformaciones y destinos.</span><span class="sxs-lookup"><span data-stu-id="9ca07-103">includes three types of data flow components: sources, transformations, and destinations.</span></span>  
  
 <span data-ttu-id="9ca07-104">El siguiente diagrama muestra un flujo de datos simple que tiene un origen, dos transformaciones y un destino.</span><span class="sxs-lookup"><span data-stu-id="9ca07-104">The following diagram shows a simple data flow that has a source, two transformations, and a destination.</span></span>  
  
 <span data-ttu-id="9ca07-105">![Flujo de datos](../../media/mw-dts-08.gif "flujo de datos")</span><span class="sxs-lookup"><span data-stu-id="9ca07-105">![Data flow](../../media/mw-dts-08.gif "Data flow")</span></span>  
  
 [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="9ca07-106">ofrecen la siguiente funcionalidad:</span><span class="sxs-lookup"><span data-stu-id="9ca07-106">transformations provide the following functionality:</span></span>  
  
-   <span data-ttu-id="9ca07-107">Dividir, copiar y combinar conjuntos de filas y realizar operaciones de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="9ca07-107">Splitting, copying, and merging rowsets and performing lookup operations.</span></span>  
  
-   <span data-ttu-id="9ca07-108">Actualizar valores de columnas y crear nuevas columnas aplicando transformaciones tales como cambio de minúsculas por mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="9ca07-108">Updating column values and creating new columns by applying transformations such as changing lowercase to uppercase.</span></span>  
  
-   <span data-ttu-id="9ca07-109">Operaciones de inteligencia empresarial tales como limpiar datos, realizar minería de texto y ejecutar consultas de predicción de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="9ca07-109">Performing business intelligence operations such as cleaning data, mining text, or running data mining prediction queries.</span></span>  
  
-   <span data-ttu-id="9ca07-110">Crear nuevos conjuntos de filas que se componen de valores agregados u ordenados, datos de muestra o datos dinamizados y de anulación de dinamización.</span><span class="sxs-lookup"><span data-stu-id="9ca07-110">Creating new rowsets that consist of aggregate or sorted values, sample data, or pivoted and unpivoted data.</span></span>  
  
-   <span data-ttu-id="9ca07-111">Realizar tareas tales como exportar e importar datos, proporcionar información de auditoría y trabajar con dimensiones de variación lenta.</span><span class="sxs-lookup"><span data-stu-id="9ca07-111">Performing tasks such as exporting and importing data, providing audit information, and working with slowly changing dimensions.</span></span>  
  
 <span data-ttu-id="9ca07-112">Para más información, consulte [Integration Services Transformations](integration-services-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="9ca07-112">For more information, see [Integration Services Transformations](integration-services-transformations.md).</span></span>  
  
 <span data-ttu-id="9ca07-113">También puede escribir transformaciones personalizadas.</span><span class="sxs-lookup"><span data-stu-id="9ca07-113">You can also write custom transformations.</span></span> <span data-ttu-id="9ca07-114">Para más información, vea [Desarrollar un componente de flujo de datos personalizado](../../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md) y [Desarrollar tipos específicos de componentes de flujo de datos](../../extending-packages-custom-objects-data-flow-types/developing-specific-types-of-data-flow-components.md).</span><span class="sxs-lookup"><span data-stu-id="9ca07-114">For more information, see [Developing a Custom Data Flow Component](../../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md) and [Developing Specific Types of Data Flow Components](../../extending-packages-custom-objects-data-flow-types/developing-specific-types-of-data-flow-components.md).</span></span>  
  
 <span data-ttu-id="9ca07-115">Después de agregar la transformación al diseñador de flujo de datos, pero antes de configurar la transformación, debe conectar la transformación al flujo de datos conectando la salida de otra transformación u origen del flujo de datos a la entrada de esta transformación.</span><span class="sxs-lookup"><span data-stu-id="9ca07-115">After you add the transformation to the data flow designer, but before you configure the transformation, you connect the transformation to the data flow by connecting the output of another transformation or source in the data flow to the input of this transformation.</span></span> <span data-ttu-id="9ca07-116">El conector entre dos componentes de flujo de datos se denomina ruta.</span><span class="sxs-lookup"><span data-stu-id="9ca07-116">The connector between two data flow components is called a path.</span></span> <span data-ttu-id="9ca07-117">Para más información sobre la conexión de componentes y el trabajo con rutas, vea [Conectar componentes con rutas de acceso](../../connect-components-with-paths.md).</span><span class="sxs-lookup"><span data-stu-id="9ca07-117">For more information about connecting components and working with paths, see [Connect Components with Paths](../../connect-components-with-paths.md).</span></span>  
  
### <a name="to-add-a-transformation-to-a-data-flow"></a><span data-ttu-id="9ca07-118">Para agregar una transformación a un flujo de datos</span><span class="sxs-lookup"><span data-stu-id="9ca07-118">To add a transformation to a data flow</span></span>  
  
-   [<span data-ttu-id="9ca07-119">Agregar o eliminar un componente en un flujo de datos</span><span class="sxs-lookup"><span data-stu-id="9ca07-119">Add or Delete a Component in a Data Flow</span></span>](../add-or-delete-a-component-in-a-data-flow.md)  
  
### <a name="to-connect-a-transformation-to-a-data-flow"></a><span data-ttu-id="9ca07-120">Para conectar una transformación a un flujo de datos</span><span class="sxs-lookup"><span data-stu-id="9ca07-120">To connect a transformation to a data flow</span></span>  
  
-   [<span data-ttu-id="9ca07-121">Conectar componentes de un flujo de datos</span><span class="sxs-lookup"><span data-stu-id="9ca07-121">Connect Components in a Data Flow</span></span>](../connect-components-in-a-data-flow.md)  
  
### <a name="to-set-the-properties-of-a-transformation"></a><span data-ttu-id="9ca07-122">Para establecer las propiedades de una transformación</span><span class="sxs-lookup"><span data-stu-id="9ca07-122">To set the properties of a transformation</span></span>  
  
-   [<span data-ttu-id="9ca07-123">Establecer las propiedades de un componente de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="9ca07-123">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
## <a name="see-also"></a><span data-ttu-id="9ca07-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9ca07-124">See Also</span></span>  
 <span data-ttu-id="9ca07-125">[Tarea Flujo de datos](../../control-flow/data-flow-task.md) </span><span class="sxs-lookup"><span data-stu-id="9ca07-125">[Data Flow Task](../../control-flow/data-flow-task.md) </span></span>  
 <span data-ttu-id="9ca07-126">[Flujo de datos](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="9ca07-126">[Data Flow](../data-flow.md) </span></span>  
 <span data-ttu-id="9ca07-127">[Conectar componentes con rutas de acceso](../../connect-components-with-paths.md) </span><span class="sxs-lookup"><span data-stu-id="9ca07-127">[Connect Components with Paths](../../connect-components-with-paths.md) </span></span>  
 <span data-ttu-id="9ca07-128">[Control de errores en los datos](../error-handling-in-data.md) </span><span class="sxs-lookup"><span data-stu-id="9ca07-128">[Error Handling in Data](../error-handling-in-data.md) </span></span>  
 [<span data-ttu-id="9ca07-129">Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="9ca07-129">Data Flow</span></span>](../data-flow.md)  
  
  
