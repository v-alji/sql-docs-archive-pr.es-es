---
title: Arquitectura de minería de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 105f52e1-ad3b-4cd0-b67b-06dbb451c304
author: minewiskan
ms.author: owend
ms.openlocfilehash: a372972fd7fa39f7bcfd2e10abbc4fbf8f8c10aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676265"
---
# <a name="data-mining-architecture"></a><span data-ttu-id="c7e24-102">Arquitectura de minería de datos</span><span class="sxs-lookup"><span data-stu-id="c7e24-102">Data Mining Architecture</span></span>
  <span data-ttu-id="c7e24-103">En esta sección se describe la arquitectura de las soluciones de minería de datos que se hospedan en una instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7e24-103">This section describes the architecture of data mining solutions that are hosted in an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="c7e24-104">En los temas de esta sección se describe la arquitectura lógica y física de una instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que admita la minería de datos, y también proporcionan información acerca de los clientes, los proveedores y los protocolos que se pueden utilizar para comunicarse con los servidores de minería de datos y trabajar con objetos de minería de datos tanto local como remotamente.</span><span class="sxs-lookup"><span data-stu-id="c7e24-104">The topics in this section describe the logical and physical architecture of an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance that supports data mining, and also provide information about the clients, providers, and protocols that can be used to communicate with data mining servers, and to work with data mining objects either locally or remotely.</span></span>  
  
 <span data-ttu-id="c7e24-105">En general, la minería de datos de SQL Server opera como un servicio que se proporciona como parte de una instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en modo multidimensional; por consiguiente, recomendamos que también repase las secciones siguientes de los Libros en pantalla en las que se describe el funcionamiento, el mantenimiento y la configuración de las soluciones multidimensionales de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c7e24-105">In general, SQL Server Data Mining operates as a service that is provided as part of an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance running in multidimensional mode; therefore, we recommend that you also review the following sections of Books Online that describe the operation, maintenance, and configuration of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] multidimensional solutions.</span></span>  
  
 [<span data-ttu-id="c7e24-106">Procesamiento de objetos del modelo multidimensional</span><span class="sxs-lookup"><span data-stu-id="c7e24-106">Multidimensional Model Object Processing</span></span>](../multidimensional-models/processing-a-multidimensional-model-analysis-services.md)  
  
 [<span data-ttu-id="c7e24-107">Conectar a Analysis Services</span><span class="sxs-lookup"><span data-stu-id="c7e24-107">Connect to Analysis Services</span></span>](../instances/connect-to-analysis-services.md)  
  
 [<span data-ttu-id="c7e24-108">Ubicación de almacenamiento de las bases de datos</span><span class="sxs-lookup"><span data-stu-id="c7e24-108">Database Storage Location</span></span>](../multidimensional-models/database-storage-location.md)  
  
 [<span data-ttu-id="c7e24-109">Cambiar entre los modos ReadOnly y ReadWrite en una base de datos de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="c7e24-109">Switch an Analysis Services database between ReadOnly and ReadWrite modes</span></span>](../multidimensional-models/switch-an-analysis-services-database-between-readonly-and-readwrite-modes.md)  
  
 <span data-ttu-id="c7e24-110">Para obtener más información sobre cómo puede implementar la minería de datos en una solución de Business Intelligence, vea la sección Solution Guides de MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="c7e24-110">For more information about how you can implement data mining in your business intelligence solution, see the Solution Guides section of the MSDN Library.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c7e24-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c7e24-111">In This Section</span></span>  
 [<span data-ttu-id="c7e24-112">Arquitectura lógica &#40;Analysis Services - Minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="c7e24-112">Logical Architecture &#40;Analysis Services - Data Mining&#41;</span></span>](logical-architecture-analysis-services-data-mining.md)  
  
 [<span data-ttu-id="c7e24-113">Arquitectura física &#40;Analysis Services - Minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="c7e24-113">Physical Architecture &#40;Analysis Services - Data Mining&#41;</span></span>](physical-architecture-analysis-services-data-mining.md)  
  
 [<span data-ttu-id="c7e24-114">Servicios de minería de datos y orígenes de datos</span><span class="sxs-lookup"><span data-stu-id="c7e24-114">Data Mining Services and Data Sources</span></span>](data-mining-services-and-data-sources.md)  
  
 [<span data-ttu-id="c7e24-115">Administración de las soluciones y los objetos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="c7e24-115">Management of Data Mining Solutions and Objects</span></span>](management-of-data-mining-solutions-and-objects.md)  
  
 [<span data-ttu-id="c7e24-116">Información general de Seguridad &#40;minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="c7e24-116">Security Overview &#40;Data Mining&#41;</span></span>](security-overview-data-mining.md)  
  
## <a name="see-also"></a><span data-ttu-id="c7e24-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c7e24-117">See Also</span></span>  
 <span data-ttu-id="c7e24-118">[Programación de modelos multidimensionales](../multidimensional-models/multidimensional-model-programming.md) </span><span class="sxs-lookup"><span data-stu-id="c7e24-118">[Multidimensional Model Programming](../multidimensional-models/multidimensional-model-programming.md) </span></span>  
 [<span data-ttu-id="c7e24-119">Programación de minería de datos</span><span class="sxs-lookup"><span data-stu-id="c7e24-119">Data Mining Programming</span></span>](../dev-guide/data-mining-programming.md)  
  
  
