---
title: Modelado multidimensional (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 509df042-fdb3-4e2c-a6b8-86943ce1b0fc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7348a932eccb62f2e00c0b154ca9efc8086fcd1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752469"
---
# <a name="multidimensional-modeling-ssas"></a><span data-ttu-id="ecbb6-102">Modelado multidimensional (SSAS)</span><span class="sxs-lookup"><span data-stu-id="ecbb6-102">Multidimensional Modeling (SSAS)</span></span>
  <span data-ttu-id="ecbb6-103">Una solución multidimensional de Analysis Services usa estructuras de cubierta para analizar datos de negocio en varias dimensiones.</span><span class="sxs-lookup"><span data-stu-id="ecbb6-103">An Analysis Services multidimensional solution uses cube structures for analyzing business data across multiple dimensions.</span></span> <span data-ttu-id="ecbb6-104">El modo multidimensional es el modo de servidor predeterminado de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="ecbb6-104">Multidimensional mode is the default server mode of Analysis Services.</span></span> <span data-ttu-id="ecbb6-105">Incluye un motor de cálculo y consulta de datos OLAP, con los modos de almacenamiento MOLAP, ROLAP y ROLAP para equilibrar el rendimiento con los requisitos de datos escalables.</span><span class="sxs-lookup"><span data-stu-id="ecbb6-105">It includes a query and calculation engine for OLAP data, with MOLAP, ROLAP, and HOLAP storage modes to balance performance with scalable data requirements.</span></span> <span data-ttu-id="ecbb6-106">El motor OLAP de Analysis Services es un servidor OLAP principal del sector que funciona con una amplia variedad de herramientas de BI.</span><span class="sxs-lookup"><span data-stu-id="ecbb6-106">The Analysis Services OLAP engine is an industry leading OLAP server that works well with a broad range of BI tools.</span></span> <span data-ttu-id="ecbb6-107">La mayoría de las implementaciones de Analysis Services se instalan como servidores OLAP clásicos.</span><span class="sxs-lookup"><span data-stu-id="ecbb6-107">Most Analysis Services deployments are installed as classic OLAP servers.</span></span>  
  
## <a name="benefits-of-using-multidimensional-solutions"></a><span data-ttu-id="ecbb6-108">Ventajas de usar soluciones multidimensionales</span><span class="sxs-lookup"><span data-stu-id="ecbb6-108">Benefits of Using Multidimensional Solutions</span></span>  
 <span data-ttu-id="ecbb6-109">La razón principal para generar un modelo multidimensional de Analysis Services es lograr el rendimiento rápido de consultas ad hoc en los datos empresariales.</span><span class="sxs-lookup"><span data-stu-id="ecbb6-109">The primary reason for building an Analysis Services multidimensional model is to achieve fast performance of ad hoc queries against business data.</span></span> <span data-ttu-id="ecbb6-110">Un modelo multidimensional se compone de cubos y dimensiones que se pueden anotar y ampliar para admitir construcciones de consultas complejas.</span><span class="sxs-lookup"><span data-stu-id="ecbb6-110">A multidimensional model is composed of cubes and dimensions that can be annotated and extended to support complex query constructions.</span></span> <span data-ttu-id="ecbb6-111">Los desarrolladores de BI crean cubos para admitir tiempos de respuesta rápida y para proporcionar un único origen de datos para informes empresariales.</span><span class="sxs-lookup"><span data-stu-id="ecbb6-111">BI developers create cubes to support fast response times, and to provide a single data source for business reporting.</span></span> <span data-ttu-id="ecbb6-112">Debido a la mayor importancia de business intelligence en todos los niveles de una organización, el hecho de tener un solo origen de datos analíticos se garantiza que las discrepancias se mantienen al mínimo, si no se eliminan por completo.</span><span class="sxs-lookup"><span data-stu-id="ecbb6-112">Given the growing importance of business intelligence across all levels of an organization, having a single source of analytical data ensures that discrepancies are kept to a minimum, if not eliminated entirely.</span></span>  
  
 <span data-ttu-id="ecbb6-113">Otra ventaja importante del uso de las bases de datos multidimensionales de Analysis Services es la integración con las herramientas de informes BI utilizadas habitualmente, como Excel, Reporting Services y PerformancePoint, así como las aplicaciones personalizadas y las soluciones de terceros.</span><span class="sxs-lookup"><span data-stu-id="ecbb6-113">Another important benefit to using Analysis Services multidimensional databases is integration with commonly used BI reporting tools such as Excel, Reporting Services, and PerformancePoint, as well as custom applications and third-party solutions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ecbb6-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ecbb6-114">In This Section</span></span>  
 [<span data-ttu-id="ecbb6-115">Soluciones de modelos multidimensionales &#40;SSAS&#41;</span><span class="sxs-lookup"><span data-stu-id="ecbb6-115">Multidimensional Model Solutions &#40;SSAS&#41;</span></span>](multidimensional-model-solutions-ssas.md)  
  
 [<span data-ttu-id="ecbb6-116">Bases de datos de modelos multidimensionales &#40;SSAS&#41;</span><span class="sxs-lookup"><span data-stu-id="ecbb6-116">Multidimensional Model Databases &#40;SSAS&#41;</span></span>](multidimensional-model-databases-ssas.md)  
  
 [<span data-ttu-id="ecbb6-117">Procesamiento de objetos del modelo multidimensional</span><span class="sxs-lookup"><span data-stu-id="ecbb6-117">Multidimensional Model Object Processing</span></span>](processing-a-multidimensional-model-analysis-services.md)  
  
 [<span data-ttu-id="ecbb6-118">Roles y permisos &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ecbb6-118">Roles and Permissions &#40;Analysis Services&#41;</span></span>](roles-and-permissions-analysis-services.md)  
  
 [<span data-ttu-id="ecbb6-119">Power View para modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="ecbb6-119">Power View for Multidimensional Models</span></span>](power-view-for-multidimensional-models.md)  
  
 [<span data-ttu-id="ecbb6-120">Administración de ensamblados de modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="ecbb6-120">Multidimensional Model Assemblies Management</span></span>](multidimensional-model-assemblies-management.md)  
  
  
