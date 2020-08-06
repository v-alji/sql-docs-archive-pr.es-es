---
title: Modelado tabular (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 80027288-c203-4667-a3e1-40fa572b4975
author: minewiskan
ms.author: owend
ms.openlocfilehash: 44f358f0f36e84ad903a0a4fcb0203291019e7aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670604"
---
# <a name="tabular-modeling-ssas-tabular"></a><span data-ttu-id="2d5dd-102">Modelado tabular (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="2d5dd-102">Tabular Modeling (SSAS Tabular)</span></span>
  <span data-ttu-id="2d5dd-103">Los modelos tabulares son bases de datos "en memoria" de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="2d5dd-103">Tabular models are in-memory databases in Analysis Services.</span></span> <span data-ttu-id="2d5dd-104">Gracias a los algoritmos de compresión avanzados y al procesador de consultas multiproceso, el motor analítico en memoria xVelocity (VertiPaq) ofrece un acceso rápido a los objetos y los datos de los modelos tabulares para aplicaciones cliente de informes como Microsoft Excel y Microsoft [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d5dd-104">Using state-of-the-art compression algorithms and multi-threaded query processor, the xVelocity in-memory analytics engine (VertiPaq) delivers fast access to tabular model objects and data by reporting client applications such as Microsoft Excel and Microsoft [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span></span>  
  
 <span data-ttu-id="2d5dd-105">Los modelos tabulares admiten el acceso a los datos mediante dos modos: modo de almacenamiento en caché y modo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="2d5dd-105">Tabular models support data access through two modes: Cached mode and DirectQuery mode.</span></span> <span data-ttu-id="2d5dd-106">En el modo de almacenamiento en caché, puede integrar datos de varios orígenes como bases de datos relacionales, fuentes de distribución de datos y archivos de texto planos.</span><span class="sxs-lookup"><span data-stu-id="2d5dd-106">In cached mode, you can integrate data from multiple sources including relational databases, data feeds, and flat text files.</span></span> <span data-ttu-id="2d5dd-107">En el modo DirectQuery, puede omitir el modelo en memoria, lo que permite a las aplicaciones cliente consultar los datos directamente en el origen relacional (SQL Server).</span><span class="sxs-lookup"><span data-stu-id="2d5dd-107">In DirectQuery mode, you can bypass the in-memory model, allowing client applications to query data directly at the (SQL Server relational) source.</span></span>  
  
 <span data-ttu-id="2d5dd-108">Los modelos tabulares se crean en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] mediante las nuevas plantillas de proyectos de modelos tabulares.</span><span class="sxs-lookup"><span data-stu-id="2d5dd-108">Tabular models are authored in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] using new tabular model project templates.</span></span> <span data-ttu-id="2d5dd-109">Puede importar datos de varios orígenes y, a continuación, enriquecer el modelo agregando relaciones, columnas calculadas, medidas, KPI y jerarquías.</span><span class="sxs-lookup"><span data-stu-id="2d5dd-109">You can import data from multiple sources, and then enrich the model by adding relationships, calculated columns, measures, KPIs, and hierarchies.</span></span> <span data-ttu-id="2d5dd-110">A continuación, los modelos se pueden implementar en una instancia de Analysis Services que permite a las aplicaciones cliente de informes conectarse con ellos.</span><span class="sxs-lookup"><span data-stu-id="2d5dd-110">Models can then be deployed to an instance of Analysis Services where client reporting applications can connect to them.</span></span> <span data-ttu-id="2d5dd-111">Los modelos implementados se pueden administrar en SQL Server Management Studio del mismo modo que los modelos multidimensionales.</span><span class="sxs-lookup"><span data-stu-id="2d5dd-111">Deployed models can be managed in SQL Server Management Studio just like multidimensional models.</span></span> <span data-ttu-id="2d5dd-112">También se pueden crear particiones de los mismos para optimizar el procesamiento y protegerlos en el nivel de fila usando la seguridad basada en roles.</span><span class="sxs-lookup"><span data-stu-id="2d5dd-112">They can also be partitioned for optimized processing and secured to the row-level by using role based security.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2d5dd-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2d5dd-113">In This Section</span></span>  
 [<span data-ttu-id="2d5dd-114">Soluciones de modelos tabulares &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="2d5dd-114">Tabular Model Solutions &#40;SSAS Tabular&#41;</span></span>](../tabular-model-solutions-ssas-tabular.md)  
  
 [<span data-ttu-id="2d5dd-115">Bases de datos de modelo tabular &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="2d5dd-115">Tabular Model Databases &#40;SSAS Tabular&#41;</span></span>](tabular-model-databases-ssas-tabular.md)  
  
 [<span data-ttu-id="2d5dd-116">Acceso a datos de modelos tabulares</span><span class="sxs-lookup"><span data-stu-id="2d5dd-116">Tabular Model Data Access</span></span>](tabular-model-data-access.md)  
  
  
