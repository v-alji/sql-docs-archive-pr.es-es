---
title: Programación del servidor de ADOMD.NET | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- programming [ADOMD.NET]
- ADOMD.NET, programming
ms.assetid: 7f7ff5be-3826-43a5-b94d-ddeec5ddb2eb
author: minewiskan
ms.author: owend
ms.openlocfilehash: 522478af0b19f1745d80f167e40345d4751136b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743677"
---
# <a name="adomdnet-server-programming"></a><span data-ttu-id="266e5-102">Programación del servidor ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="266e5-102">ADOMD.NET Server Programming</span></span>
  <span data-ttu-id="266e5-103">Los componentes de servidor ADOMD.NET de ADOMD.NET residen en el espacio de nombres `Microsoft.AnalysisServices.AdomdServer` (en msmgdsrv.dll).</span><span class="sxs-lookup"><span data-stu-id="266e5-103">The ADOMD.NET server components of ADOMD.NET reside within the `Microsoft.AnalysisServices.AdomdServer` namespace (in msmgdsrv.dll).</span></span> <span data-ttu-id="266e5-104">Estos componentes de servidor se usan para crear funciones de expresiones multidimensionales (MDX) y procedimientos almacenados que se ejecutan en una instancia de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="266e5-104">You use these server components to create custom Multidimensional Expressions (MDX) functions and stored procedures that are run on an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="266e5-105">Los objetos de servidor proporcionan las capacidades necesarias para realizar consultas en cubos y modelos de minería de datos, así como para evaluar expresiones en un contexto determinado.</span><span class="sxs-lookup"><span data-stu-id="266e5-105">The server objects provide the capabilities for querying cubes and mining models, and for evaluating expressions in a given context.</span></span> <span data-ttu-id="266e5-106">Entre las ventajas de crear funciones y procedimientos almacenados personalizados se incluyen una ejecución rápida, una implementación centralizada y un mantenimiento mejorado.</span><span class="sxs-lookup"><span data-stu-id="266e5-106">The benefits for creating custom functions and stored procedures include fast execution, centralized deployment, and improved maintainability.</span></span>  
  
 <span data-ttu-id="266e5-107">Los temas de la tabla siguiente le ayudarán a desarrollar aplicaciones de servidor ADOMD.NET.</span><span class="sxs-lookup"><span data-stu-id="266e5-107">The topics in the following table will help you develop ADOMD.NET server applications.</span></span>  
  
|<span data-ttu-id="266e5-108">Tema</span><span class="sxs-lookup"><span data-stu-id="266e5-108">Topic</span></span>|<span data-ttu-id="266e5-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="266e5-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="266e5-110">Funcionalidad del servidor de ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="266e5-110">ADOMD.NET Server Functionality</span></span>](https://docs.microsoft.com/bi-reference/adomd/multidimensional-models-adomd-net-server/adomd-net-server-functionality)|<span data-ttu-id="266e5-111">Describe los usos de los objetos de servidor ADOMD.NET.</span><span class="sxs-lookup"><span data-stu-id="266e5-111">Describes the uses for ADOMD.NET server objects.</span></span>|  
|[<span data-ttu-id="266e5-112">Arquitectura de objetos de servidor ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="266e5-112">ADOMD.NET Server Object Architecture</span></span>](https://docs.microsoft.com/bi-reference/adomd/multidimensional-models-adomd-net-server/adomd-net-server-object-architecture)|<span data-ttu-id="266e5-113">Describe la arquitectura de los objetos de servidor ADOMD.NET.</span><span class="sxs-lookup"><span data-stu-id="266e5-113">Describes the object architecture for ADOMD.NET server objects.</span></span>|  
|[<span data-ttu-id="266e5-114">Funciones definidas por el usuario y procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="266e5-114">User Defined Functions and Stored Procedures</span></span>](https://docs.microsoft.com/analysis-services/adomd/multidimensional-models-adomd-net-server/user-defined-functions-and-stored-procedures)|<span data-ttu-id="266e5-115">Le guía por el proceso de creación de una función o un procedimiento almacenado definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="266e5-115">Walks you through the process of creating a user defined function or stored Procedure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="266e5-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="266e5-116">See Also</span></span>  
 <span data-ttu-id="266e5-117">[Programación de cliente de ADOMD.NET](https://docs.microsoft.com/analysis-services/adomd/multidimensional-models-adomd-net-client/adomd-net-client-programming) </span><span class="sxs-lookup"><span data-stu-id="266e5-117">[ADOMD.NET Client Programming](https://docs.microsoft.com/analysis-services/adomd/multidimensional-models-adomd-net-client/adomd-net-client-programming) </span></span>  
 [<span data-ttu-id="266e5-118">Desarrollar con ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="266e5-118">Developing with ADOMD.NET</span></span>](https://docs.microsoft.com/bi-reference/adomd/developing-with-adomd-net)  
  
  
