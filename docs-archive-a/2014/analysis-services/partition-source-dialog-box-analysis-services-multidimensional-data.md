---
title: Cuadro de diálogo origen de la partición (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitionsourcedialog.f1
ms.assetid: c414dabe-9bad-49b7-9a3c-dfca87fef92b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6732e8f00dc0d01e0d3b708794a1d9c497ae4cf5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743651"
---
# <a name="partition-source-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="5cc62-102">Cuadro de diálogo Origen de la partición (Analysis Services - Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="5cc62-102">Partition Source Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="5cc62-103">Use el cuadro de diálogo **Origen de la partición** de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] para especificar el origen de los datos de la tabla de hechos para una partición.</span><span class="sxs-lookup"><span data-stu-id="5cc62-103">Use the **Partition Source** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to specify the source of fact table data for a partition.</span></span> <span data-ttu-id="5cc62-104">Para mostrar el cuadro de diálogo **Origen de la partición** :</span><span class="sxs-lookup"><span data-stu-id="5cc62-104">You can display the **Partition Source** dialog box by:</span></span>  
  
-   <span data-ttu-id="5cc62-105">Haga clic en el botón **…** de una celda de la cuadrícula **Particiones** de un grupo de medida seleccionado en el panel **Grupos de medida** en la pestaña **Particiones** del Diseñador de cubos.</span><span class="sxs-lookup"><span data-stu-id="5cc62-105">Clicking the **...** button on a cell from the **Partitions** grid of a selected measure group in the **Measure Groups** pane on the **Partitions** tab in Cube Designer.</span></span>  
  
-   <span data-ttu-id="5cc62-106">Haga clic en el botón **…** del valor de propiedad **Origen** de un objeto de **Partición** en la ventana **Propiedades** de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5cc62-106">Clicking the **...** button on the **Source** property value of a **Partition** object in the **Properties** window in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="5cc62-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="5cc62-107">Options</span></span>  
  
|<span data-ttu-id="5cc62-108">Opción</span><span class="sxs-lookup"><span data-stu-id="5cc62-108">Option</span></span>|<span data-ttu-id="5cc62-109">Definición</span><span class="sxs-lookup"><span data-stu-id="5cc62-109">Definition</span></span>|  
|------------|----------------|  
|<span data-ttu-id="5cc62-110">**Tipo de enlace**</span><span class="sxs-lookup"><span data-stu-id="5cc62-110">**Binding type**</span></span>|<span data-ttu-id="5cc62-111">Seleccione el tipo de enlace que desea utilizar como origen de la partición especificada.</span><span class="sxs-lookup"><span data-stu-id="5cc62-111">Select the binding type to use for the source of the specified partition.</span></span> <span data-ttu-id="5cc62-112">Están disponibles las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="5cc62-112">The following options are available:</span></span><br /><br /> <span data-ttu-id="5cc62-113">**Enlace de tablas**: Seleccione esta información para mostrar el panel de **detalles del enlace de tablas** e indicar que la partición está enlazada al contenido de una tabla en un origen de datos o vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="5cc62-113">**Table binding**: Select to display the **Table Binding Detail** pane and indicate that the partition is bound to the contents of a table in a data source or data source view.</span></span> <span data-ttu-id="5cc62-114">Para más información sobre el panel **Detalle del enlace de tablas**, vea [Detalle del enlace de tablas &#40;cuadro de diálogo Origen de la partición&#41; &#40;Analysis Services - Datos multidimensionales&#41;](table-binding-partition-source-dialog-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="5cc62-114">For more information about the **Table Binding Detail** pane, see [Table Binding Detail &#40;Partition Source Dialog Box&#41; &#40;Analysis Services - Multidimensional Data&#41;](table-binding-partition-source-dialog-analysis-services-multidimensional-data.md).</span></span><br /><br /> <span data-ttu-id="5cc62-115">**Detalle**: Seleccione esta información para mostrar el panel **detalle del enlace de consultas** e indique que la partición está enlazada al contenido de una consulta ejecutada en un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="5cc62-115">**Detail**: Select to display the **Query Binding Detail** pane and indicate that the partition is bound to the contents of a query executed on a data source.</span></span> <span data-ttu-id="5cc62-116">Para más información sobre el panel **Detalle del enlace de consultas**, vea [Detalle del enlace de consultas &#40;cuadro de diálogo Origen de la partición&#41; &#40;Analysis Services - Datos multidimensionales&#41;](query-binding-partition-source-dialog-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="5cc62-116">For more information about the **Query Binding Detail** pane, see [Query Binding Detail &#40;Partition Source Dialog Box&#41; &#40;Analysis Services - Multidimensional Data&#41;](query-binding-partition-source-dialog-analysis-services-multidimensional-data.md).</span></span>|  
|<span data-ttu-id="5cc62-117">**Detalle**</span><span class="sxs-lookup"><span data-stu-id="5cc62-117">**Detail**</span></span>|<span data-ttu-id="5cc62-118">Muestra el cuadro de diálogo **Detalle del enlace de tablas** o el cuadro de diálogo **Detalle del enlace de consultas** , según el valor de la opción **Tipo de enlace** .</span><span class="sxs-lookup"><span data-stu-id="5cc62-118">Displays either the **Table Binding Detail** dialog box or the **Query Binding Detail** dialog box, depending on the value of the **Binding type** option.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5cc62-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5cc62-119">See Also</span></span>  
 <span data-ttu-id="5cc62-120">[Particiones &#40;diseñador de cubos&#41; &#40;Analysis Services de datos multidimensionales&#41;](partitions-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="5cc62-120">[Partitions &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](partitions-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="5cc62-121">Analysis Services diseñadores y cuadros de diálogo &#40;datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="5cc62-121">Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;</span></span>](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)  
  
  
