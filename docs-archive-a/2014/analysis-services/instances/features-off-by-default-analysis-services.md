---
title: Características desactivadas de forma predeterminada (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a9529edf-337e-4fdd-9a13-99cfe96b4fa1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 87752b8760ffc80e80c87ac1132cae36f2f151b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745490"
---
# <a name="features-off-by-default-analysis-services"></a><span data-ttu-id="8f9ae-102">Características desactivadas de manera predeterminada (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="8f9ae-102">Features off by default (Analysis Services)</span></span>
  <span data-ttu-id="8f9ae-103">Una instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] está diseñada para que sea segura de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="8f9ae-103">An instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] is designed to be secure by default.</span></span> <span data-ttu-id="8f9ae-104">Por lo tanto, las características que comprometen la seguridad se deshabilitan de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="8f9ae-104">Therefore, features that might compromise security are disabled by default.</span></span> <span data-ttu-id="8f9ae-105">Las siguientes características están instaladas en estado deshabilitado y deben habilitarse específicamente si se desean utilizar.</span><span class="sxs-lookup"><span data-stu-id="8f9ae-105">The following features are installed in a disabled state and must specifically be enabled if you want to use them.</span></span>  
  
## <a name="feature-list"></a><span data-ttu-id="8f9ae-106">Lista de características</span><span class="sxs-lookup"><span data-stu-id="8f9ae-106">Feature List</span></span>  
 <span data-ttu-id="8f9ae-107">Para habilitar las siguientes características, conéctese a [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f9ae-107">To enable the following features, connect to [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="8f9ae-108">Haga clic con el botón derecho en el nombre de la instancia y seleccione **Facetas**.</span><span class="sxs-lookup"><span data-stu-id="8f9ae-108">Right-click the instance name and choose **Facets**.</span></span> <span data-ttu-id="8f9ae-109">También puede habilitar estas características utilizando las propiedades del servidor, como se describe en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="8f9ae-109">Alternatively, you can enable these features through server properties, as described in the next section.</span></span>  
  
-   <span data-ttu-id="8f9ae-110">Consultas ad hoc de minería de datos (OpenRowset)</span><span class="sxs-lookup"><span data-stu-id="8f9ae-110">Ad Hoc Data Mining (OpenRowset) Queries</span></span>  
  
-   <span data-ttu-id="8f9ae-111">Objetos vinculados (a)</span><span class="sxs-lookup"><span data-stu-id="8f9ae-111">Linked Objects (To)</span></span>  
  
-   <span data-ttu-id="8f9ae-112">Objetos vinculados (desde)</span><span class="sxs-lookup"><span data-stu-id="8f9ae-112">Linked Objects (From)</span></span>  
  
-   <span data-ttu-id="8f9ae-113">Escuchar solo en conexiones locales</span><span class="sxs-lookup"><span data-stu-id="8f9ae-113">Listen Only On Local Connections</span></span>  
  
-   <span data-ttu-id="8f9ae-114">Funciones definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="8f9ae-114">User Defined Functions</span></span>  
  
## <a name="server-properties"></a><span data-ttu-id="8f9ae-115">Propiedades del servidor</span><span class="sxs-lookup"><span data-stu-id="8f9ae-115">Server properties</span></span>  
 <span data-ttu-id="8f9ae-116">Otras características que están deshabilitadas de manera predeterminada se pueden habilitar mediante las propiedades del servidor.</span><span class="sxs-lookup"><span data-stu-id="8f9ae-116">Additional features that are off by default can be enabled through server properties.</span></span> <span data-ttu-id="8f9ae-117">Conéctese a [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f9ae-117">Connect to [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="8f9ae-118">Haga clic con el botón derecho en el nombre de la instancia y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="8f9ae-118">Right-click the instance name and choose **Properties**.</span></span> <span data-ttu-id="8f9ae-119">Haga clic en **General**y, a continuación, haga clic en **Mostrar avanzadas** para visualizar una lista de propiedades más extensa.</span><span class="sxs-lookup"><span data-stu-id="8f9ae-119">Click **General**, and then click **Show Advanced** to display a larger property list.</span></span>  
  
-   <span data-ttu-id="8f9ae-120">Consultas ad hoc de minería de datos (OpenRowset)</span><span class="sxs-lookup"><span data-stu-id="8f9ae-120">Ad Hoc Data Mining (OpenRowset) Queries</span></span>  
  
-   <span data-ttu-id="8f9ae-121">Permitir modelos de minería de datos de sesión (minería de datos)</span><span class="sxs-lookup"><span data-stu-id="8f9ae-121">Allow Session Mining Models (Data Mining)</span></span>  
  
-   <span data-ttu-id="8f9ae-122">Objetos vinculados (a)</span><span class="sxs-lookup"><span data-stu-id="8f9ae-122">Linked Objects (To)</span></span>  
  
-   <span data-ttu-id="8f9ae-123">Objetos vinculados (desde)</span><span class="sxs-lookup"><span data-stu-id="8f9ae-123">Linked Objects (From)</span></span>  
  
-   <span data-ttu-id="8f9ae-124">Funciones definidas por el usuario basadas en COM</span><span class="sxs-lookup"><span data-stu-id="8f9ae-124">COM based user-defined functions</span></span>  
  
-   <span data-ttu-id="8f9ae-125">Definición de seguimiento de la Caja negra (plantillas).</span><span class="sxs-lookup"><span data-stu-id="8f9ae-125">Flight Recorder Trace Definitions (templates).</span></span>  
  
-   <span data-ttu-id="8f9ae-126">Registro de consultas</span><span class="sxs-lookup"><span data-stu-id="8f9ae-126">Query logging</span></span>  
  
-   <span data-ttu-id="8f9ae-127">Escuchar solo en conexiones locales</span><span class="sxs-lookup"><span data-stu-id="8f9ae-127">Listen Only On Local Connections</span></span>  
  
-   <span data-ttu-id="8f9ae-128">XML binario</span><span class="sxs-lookup"><span data-stu-id="8f9ae-128">Binary XML</span></span>  
  
-   <span data-ttu-id="8f9ae-129">Compresión</span><span class="sxs-lookup"><span data-stu-id="8f9ae-129">Compression</span></span>  
  
-   <span data-ttu-id="8f9ae-130">Afinidad del grupo.</span><span class="sxs-lookup"><span data-stu-id="8f9ae-130">Group affinity.</span></span> <span data-ttu-id="8f9ae-131">Para obtener información detallada, vea [Thread Pool Properties](../server-properties/thread-pool-properties.md) .</span><span class="sxs-lookup"><span data-stu-id="8f9ae-131">See [Thread Pool Properties](../server-properties/thread-pool-properties.md) for details.</span></span>  
  
  
