---
title: Elementos de informe personalizados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- extending Reporting Services
- Reporting Services, extending
- custom report items
ms.assetid: 64dcaf2c-1af5-4937-8ff7-98f1ec3b367e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 86b819cb4d305e537a52a2e7f25cdfa3aefa5f9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750533"
---
# <a name="custom-report-items"></a><span data-ttu-id="e1ff5-102">Elementos de informe personalizados</span><span class="sxs-lookup"><span data-stu-id="e1ff5-102">Custom Report Items</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="e1ff5-103">proporciona un abundante conjunto de herramientas para crear y publicar informes de empresa, administrar la seguridad y las suscripciones, y extender la funcionalidad de informes a través de una completa API.</span><span class="sxs-lookup"><span data-stu-id="e1ff5-103">provides a rich set of tools for building and publishing enterprise reports, managing security and subscriptions, and extending the reporting functionality through a comprehensive API.</span></span> <span data-ttu-id="e1ff5-104">Los informes se definen utilizando un lenguaje basado en XML denominado lenguaje RDL (Report Definition Language).</span><span class="sxs-lookup"><span data-stu-id="e1ff5-104">Reports are defined using an XML-based language called Report Definition Language (RDL).</span></span> <span data-ttu-id="e1ff5-105">RDL proporciona un conjunto de instrucciones que describen el diseño, la información de las consultas y los tipos de elementos de un informe.</span><span class="sxs-lookup"><span data-stu-id="e1ff5-105">RDL provides a set of instructions that describe layout, query information, and item types for a report.</span></span> <span data-ttu-id="e1ff5-106">Se puede extender RDL escribiendo un elemento de informe personalizado.</span><span class="sxs-lookup"><span data-stu-id="e1ff5-106">It is possible to extend RDL by writing a custom report item.</span></span> <span data-ttu-id="e1ff5-107">El elemento de informe personalizado consta de un componente de tiempo de ejecución, que se denomina procesador de informes en tiempo de ejecución, y un componente de tiempo de diseño, que permite al elemento de informe personalizado estar disponible en el Diseñador de informes.</span><span class="sxs-lookup"><span data-stu-id="e1ff5-107">The custom report item consists of a run-time component, which is called by the report processor at run time, and a design-time component, which allows the custom report item to be available in Report Designer.</span></span>  
  
 <span data-ttu-id="e1ff5-108">Para obtener un ejemplo de un elemento de informe personalizado totalmente implementado, vea [Ejemplos del producto SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="e1ff5-108">For a sample of a fully implemented custom report item, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="custom-report-item-scenarios"></a><span data-ttu-id="e1ff5-109">Escenarios de elementos de informe personalizado</span><span class="sxs-lookup"><span data-stu-id="e1ff5-109">Custom Report Item Scenarios</span></span>  
 <span data-ttu-id="e1ff5-110">Los desarrolladores de software que necesitan integrar [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en sus aplicaciones pueden requerir alguna funcionalidad que no se admita de forma nativa en RDL.</span><span class="sxs-lookup"><span data-stu-id="e1ff5-110">Developers who need to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into their applications may require functionality that is not natively supported in RDL.</span></span> <span data-ttu-id="e1ff5-111">Esto puede incluir elementos como controles de mapas, listas horizontales, listas de columnas y matrices dinámicas.</span><span class="sxs-lookup"><span data-stu-id="e1ff5-111">This may include items such as: map controls, horizontal lists, columnar lists, and repivotable matrixes.</span></span> <span data-ttu-id="e1ff5-112">Un componente de elemento de informe personalizado de tiempo de ejecución se puede desarrollar y distribuir con una aplicación para cubrir esta necesidad.</span><span class="sxs-lookup"><span data-stu-id="e1ff5-112">A run-time custom report item component can be developed and distributed with an application to fill this need.</span></span>  
  
 <span data-ttu-id="e1ff5-113">Además de proporcionar una funcionalidad que no se admita de forma nativa, algunos programadores pueden querer extender la funcionalidad existente con versiones alternativas de controles que ya están incluidos con [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e1ff5-113">In addition to providing functionality that isn't natively supported, some developers may want to extend existing functionality with alternative versions of controls that are already included with [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="e1ff5-114">En este escenario, un programador podría proporcionar tres componentes: un componente de tiempo de ejecución, un componente de tiempo de diseño y un componente de conversión de elementos de informe de tiempo de diseño que convierte un elemento de informe existente en un elemento de informe personalizado a petición.</span><span class="sxs-lookup"><span data-stu-id="e1ff5-114">In this scenario, a developer could provide three components: a run-time component, a design-time component, and a design-time report item conversion component that converts an existing report item into a custom report item on demand.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e1ff5-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e1ff5-115">In This Section</span></span>  
 [<span data-ttu-id="e1ff5-116">Arquitectura de elementos de informe personalizados</span><span class="sxs-lookup"><span data-stu-id="e1ff5-116">Custom Report Item Architecture</span></span>](custom-report-item-architecture.md)  
 <span data-ttu-id="e1ff5-117">Describe los componentes que constituyen un elemento de informe personalizado.</span><span class="sxs-lookup"><span data-stu-id="e1ff5-117">Describes the components that make up a custom report item.</span></span>  
  
 [<span data-ttu-id="e1ff5-118">Requisitos de implementación de elementos de informe personalizados</span><span class="sxs-lookup"><span data-stu-id="e1ff5-118">Custom Report Item Implementation Requirements</span></span>](custom-report-item-implementation-requirements.md)  
 <span data-ttu-id="e1ff5-119">Describe los requisitos previos para crear un elemento de informe personalizado.</span><span class="sxs-lookup"><span data-stu-id="e1ff5-119">Describes prerequisites for creating a custom report item.</span></span>  
  
 [<span data-ttu-id="e1ff5-120">Crear un componente de tiempo de ejecución de elemento de informe personalizado</span><span class="sxs-lookup"><span data-stu-id="e1ff5-120">Creating a Custom Report Item Run-Time Component</span></span>](creating-a-custom-report-item-run-time-component.md)  
 <span data-ttu-id="e1ff5-121">Describe cómo crear un componente de tiempo de ejecución de elementos de informe personalizado.</span><span class="sxs-lookup"><span data-stu-id="e1ff5-121">Describes how to create a custom report item run-time component.</span></span>  
  
 [<span data-ttu-id="e1ff5-122">Crear un componente de tiempo de diseño de elemento de informe personalizado</span><span class="sxs-lookup"><span data-stu-id="e1ff5-122">Creating a Custom Report Item Design-Time Component</span></span>](creating-a-custom-report-item-design-time-component.md)  
 <span data-ttu-id="e1ff5-123">Describe cómo crear un componente de tiempo de diseño de elementos de informe personalizado.</span><span class="sxs-lookup"><span data-stu-id="e1ff5-123">Describes how to create a custom report item design-time component.</span></span>  
  
 [<span data-ttu-id="e1ff5-124">Cómo: Implementar un elemento de informe personalizado</span><span class="sxs-lookup"><span data-stu-id="e1ff5-124">How to: Deploy a Custom Report Item</span></span>](how-to-deploy-a-custom-report-item.md)  
 <span data-ttu-id="e1ff5-125">Describe cómo implementar un elemento de informe personalizado.</span><span class="sxs-lookup"><span data-stu-id="e1ff5-125">Describes how to deploy a custom report item.</span></span>  
  
 [<span data-ttu-id="e1ff5-126">Bibliotecas de clases de elemento de informe personalizado</span><span class="sxs-lookup"><span data-stu-id="e1ff5-126">Custom Report Item Class Libraries</span></span>](custom-report-item-class-libraries.md)  
 <span data-ttu-id="e1ff5-127">Describe las clases de infraestructuras de los elementos de informe personalizados y las clases contenedoras administradas en el espacio de nombres `Microsoft.ReportDesigner`.</span><span class="sxs-lookup"><span data-stu-id="e1ff5-127">Describes the custom report item infrastructure classes and managed wrapper classes in the `Microsoft.ReportDesigner` namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1ff5-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e1ff5-128">See Also</span></span>  
 [<span data-ttu-id="e1ff5-129">Referencia técnica &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e1ff5-129">Technical Reference &#40;SSRS&#41;</span></span>](../technical-reference-ssrs.md)  
  
  
