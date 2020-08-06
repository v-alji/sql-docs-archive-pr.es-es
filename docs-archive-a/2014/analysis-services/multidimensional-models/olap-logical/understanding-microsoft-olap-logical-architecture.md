---
title: Arquitectura lógica (Analysis Services de datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- Analysis Services, architecture
- logical architecture [Analysis Services Multidimensional Data]
ms.assetid: 1b9cae0a-8990-4194-af5f-a1ea5f2aff06
author: minewiskan
ms.author: owend
ms.openlocfilehash: d93361fb14bc6544ffa7376439c2da0c8e06c3fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675594"
---
# <a name="logical-architecture-analysis-services---multidimensional-data"></a><span data-ttu-id="31a9d-102">Arquitectura lógica (Analysis Services - Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="31a9d-102">Logical Architecture (Analysis Services - Multidimensional Data)</span></span>
  [!INCLUDE[msCoName](../../../includes/msconame-md.md)]<span data-ttu-id="31a9d-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] usa los componentes de servidor y cliente para proporcionar funciones de procesamiento analítico en línea (OLAP) y minería de datos para aplicaciones de Business Intelligence:</span><span class="sxs-lookup"><span data-stu-id="31a9d-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] uses both server and client components to supply online analytical processing (OLAP) and data mining functionality for business intelligence applications:</span></span>  
  
-   <span data-ttu-id="31a9d-104">El componente de servidor de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] se implementa como servicio de Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="31a9d-104">The server component of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] is implemented as a Microsoft Windows service.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="31a9d-105">[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]admite varias instancias en el mismo equipo, con cada instancia de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] implementada como una instancia independiente del servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="31a9d-105">[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] supports multiple instances on the same computer, with each instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] implemented as a separate instance of the Windows service.</span></span>  
  
-   <span data-ttu-id="31a9d-106">Los clientes se comunican con [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] mediante el estándar público XML for Analysis (XMLA), protocolo basado en SOAP para emitir comandos y recibir respuestas, que se expone como servicio web.</span><span class="sxs-lookup"><span data-stu-id="31a9d-106">Clients communicate with [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] using the public standard XML for Analysis (XMLA), a SOAP-based protocol for issuing commands and receiving responses, exposed as a Web service.</span></span> <span data-ttu-id="31a9d-107">Además, se proporcionan modelos de objetos de cliente en XMLA, a los que se puede obtener acceso mediante un proveedor administrado, como ADOMD.NET, o un proveedor OLE DB nativo.</span><span class="sxs-lookup"><span data-stu-id="31a9d-107">Client object models are also provided over XMLA, and can be accessed either by using a managed provider, such as ADOMD.NET, or a native OLE DB provider.</span></span>  
  
-   <span data-ttu-id="31a9d-108">Pueden emitirse comandos de consulta mediante los siguientes lenguajes: SQL; MDX (Expresiones multidimensionales), un lenguaje de consulta estándar para el análisis; o Extensiones de minería de datos (DMX), un lenguaje de consulta estándar orientado a la minería de datos.</span><span class="sxs-lookup"><span data-stu-id="31a9d-108">Query commands can be issued using the following languages: SQL; Multidimensional Expressions (MDX), an industry standard query language for analysis; or Data Mining Extensions (DMX), an industry standard query language oriented toward data mining.</span></span> <span data-ttu-id="31a9d-109">También se puede usar el lenguaje de script de Analysis Services (ASSL) para administrar objetos de base de datos de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="31a9d-109">Analysis Services Scripting Language (ASSL) can also be used to manage [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] database objects.</span></span>  
  
 [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] <span data-ttu-id="31a9d-110">también admite un motor de cubo local que permite a las aplicaciones en clientes desconectados examinar datos multidimensionales almacenados localmente.</span><span class="sxs-lookup"><span data-stu-id="31a9d-110">also supports a local cube engine that enables applications on disconnected clients to browse locally stored multidimensional data.</span></span> <span data-ttu-id="31a9d-111">Para obtener más información, consulte [requisitos de la arquitectura de cliente para el desarrollo de Analysis Services](../olap-physical/client-architecture-requirements-for-analysis-services-development.md)</span><span class="sxs-lookup"><span data-stu-id="31a9d-111">For more information, see [Client Architecture Requirements for Analysis Services Development](../olap-physical/client-architecture-requirements-for-analysis-services-development.md)</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="31a9d-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="31a9d-112">In This Section</span></span>  
 <span data-ttu-id="31a9d-113">**Información general de arquitectura lógica**</span><span class="sxs-lookup"><span data-stu-id="31a9d-113">**Logical Architecture Overview**</span></span>  
 [<span data-ttu-id="31a9d-114">Información general sobre la arquitectura lógica &#40;Analysis Services-datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="31a9d-114">Logical Architecture Overview &#40;Analysis Services - Multidimensional Data&#41;</span></span>](logical-architecture-overview-analysis-services-multidimensional-data.md)  
  
 <span data-ttu-id="31a9d-115">**Objetos de servidor**</span><span class="sxs-lookup"><span data-stu-id="31a9d-115">**Server Objects**</span></span>  
 [<span data-ttu-id="31a9d-116">Objetos de servidor &#40;Analysis Services de datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="31a9d-116">Server Objects &#40;Analysis Services - Multidimensional Data&#41;</span></span>](server-objects-analysis-services-multidimensional-data.md)  
  
 <span data-ttu-id="31a9d-117">**Objetos de base de datos**</span><span class="sxs-lookup"><span data-stu-id="31a9d-117">**Database Objects**</span></span>  
 [<span data-ttu-id="31a9d-118">Objetos de base de datos &#40;Analysis Services - Datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="31a9d-118">Database Objects &#40;Analysis Services - Multidimensional Data&#41;</span></span>](database-objects-analysis-services-multidimensional-data.md)  
  
 <span data-ttu-id="31a9d-119">**Objetos Dimension**</span><span class="sxs-lookup"><span data-stu-id="31a9d-119">**Dimension Objects**</span></span>  
 [<span data-ttu-id="31a9d-120">Objetos de dimensión &#40;Analysis Services de datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="31a9d-120">Dimension Objects &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../../multidimensional-models-olap-logical-dimension-objects/dimension-objects-analysis-services-multidimensional-data.md)  
  
 <span data-ttu-id="31a9d-121">**Objetos de cubo**</span><span class="sxs-lookup"><span data-stu-id="31a9d-121">**Cube Objects**</span></span>  
 [<span data-ttu-id="31a9d-122">Objetos de cubo &#40;Analysis Services de datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="31a9d-122">Cube Objects &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../../multidimensional-models-olap-logical-cube-objects/cube-objects-analysis-services-multidimensional-data.md)  
  
 <span data-ttu-id="31a9d-123">**Seguridad de acceso de usuario**</span><span class="sxs-lookup"><span data-stu-id="31a9d-123">**User Access Security**</span></span>  
 [<span data-ttu-id="31a9d-124">Arquitectura de seguridad para el acceso de los usuarios</span><span class="sxs-lookup"><span data-stu-id="31a9d-124">User Access Security Architecture</span></span>](understanding-microsoft-olap-logical-architecture.md)  
  
## <a name="see-also"></a><span data-ttu-id="31a9d-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="31a9d-125">See Also</span></span>  
 <span data-ttu-id="31a9d-126">[Descripción de la arquitectura OLAP de Microsoft](../olap-physical/understanding-microsoft-olap-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="31a9d-126">[Understanding Microsoft OLAP Architecture](../olap-physical/understanding-microsoft-olap-architecture.md) </span></span>  
 [<span data-ttu-id="31a9d-127">Arquitectura física &#40;Analysis Services - Datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="31a9d-127">Physical Architecture &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../olap-physical/understanding-microsoft-olap-physical-architecture.md)  
  
  
