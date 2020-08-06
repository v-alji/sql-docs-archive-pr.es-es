---
title: Arquitectura de elementos de informe personalizados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom report items, architecture
ms.assetid: 2a88ea46-c9f8-4dd7-aad1-16de11da4f06
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a053eb55547da9030eebe9036667cca2e14606f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662671"
---
# <a name="custom-report-item-architecture"></a><span data-ttu-id="2da66-102">Arquitectura de elementos de informe personalizados</span><span class="sxs-lookup"><span data-stu-id="2da66-102">Custom Report Item Architecture</span></span>
  <span data-ttu-id="2da66-103">Un elemento de informe personalizado es una extensión del lenguaje RDL (Report Definition Language) que permite a los programadores agregar la funcionalidad que no se admite de forma nativa en RDL o que extiende la funcionalidad de los controles existentes.</span><span class="sxs-lookup"><span data-stu-id="2da66-103">A custom report item is an extension to the Report Definition Language (RDL) that allows developers to add functionality that's not natively supported in RDL or extend the functionality of existing controls.</span></span> <span data-ttu-id="2da66-104">Hay dos componentes principales en un elemento de informe personalizado: el componente de tiempo de ejecución y el componente de tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="2da66-104">There are two main components to a custom report item: the run-time component and the design-time component.</span></span> <span data-ttu-id="2da66-105">Estos componentes se implementan como ensamblados de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] y se pueden escribir en cualquier lenguaje compatible con CLS.</span><span class="sxs-lookup"><span data-stu-id="2da66-105">These components are implemented as [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] assemblies, and can be written in any CLS-compliant language.</span></span>  
  
## <a name="the-run-time-component"></a><span data-ttu-id="2da66-106">Componente en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="2da66-106">The Run-Time Component</span></span>  
 <span data-ttu-id="2da66-107">El procesador de informes llama en tiempo de ejecución al componente de tiempo de ejecución para un elemento de informe personalizado.</span><span class="sxs-lookup"><span data-stu-id="2da66-107">The run-time component for a custom report item is called by the report processor at run time.</span></span> <span data-ttu-id="2da66-108">El componente de tiempo de ejecución acepta los datos que pasa en tiempo de ejecución el procesador del informe, procesa estos datos y devuelve una imagen que contiene el elemento de informe personalizado representado.</span><span class="sxs-lookup"><span data-stu-id="2da66-108">The run-time component accepts data passed by the report processor at run time, processes this data, and returns an image containing the rendered custom report item.</span></span>  
  
 <span data-ttu-id="2da66-109">![Componente de tiempo de ejecución de elemento de informe personalizado](../../../2014/reporting-services/media/customreportitemrun-timecomponentarchitecture.gif "Componente de tiempo de ejecución de elemento de informe personalizado")</span><span class="sxs-lookup"><span data-stu-id="2da66-109">![Custom report item run-time component](../../../2014/reporting-services/media/customreportitemrun-timecomponentarchitecture.gif "Custom report item run-time component")</span></span>  
  
## <a name="the-design-time-component"></a><span data-ttu-id="2da66-110">Componente de tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="2da66-110">The Design-Time Component</span></span>  
 <span data-ttu-id="2da66-111">El componente de tiempo de diseño permite definir y manipular el elemento de informe personalizado en la interfaz del Diseñador de informes en [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2da66-111">The design-time component allows the custom report item to be defined and manipulated in the Report Designer interface in [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="2da66-112">El componente de tiempo de diseño está compuesto de varios subcontroles que controlan la apariencia y las propiedades del elemento de informe personalizado en el entorno de diseño.</span><span class="sxs-lookup"><span data-stu-id="2da66-112">The design-time component consists of several sub-controls that control the appearance and properties of the custom report item in the design environment.</span></span>  
  
 <span data-ttu-id="2da66-113">![Componente de tiempo de diseño de elemento de informe personalizado](../../../2014/reporting-services/media/customreportitemdesign-timecomponentarchitecture.gif "Componente de tiempo de diseño de elemento de informe personalizado")</span><span class="sxs-lookup"><span data-stu-id="2da66-113">![Custom report item design-time component](../../../2014/reporting-services/media/customreportitemdesign-timecomponentarchitecture.gif "Custom report item design-time component")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2da66-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2da66-114">See Also</span></span>  
 <span data-ttu-id="2da66-115">[Crear un componente de tiempo de ejecución de elemento de informe personalizado](../custom-report-items/creating-a-custom-report-item-run-time-component.md) </span><span class="sxs-lookup"><span data-stu-id="2da66-115">[Creating a Custom Report Item Run-Time Component](../custom-report-items/creating-a-custom-report-item-run-time-component.md) </span></span>  
 <span data-ttu-id="2da66-116">[Crear un componente de tiempo de diseño de elemento de informe personalizado](../custom-report-items/creating-a-custom-report-item-design-time-component.md) </span><span class="sxs-lookup"><span data-stu-id="2da66-116">[Creating a Custom Report Item Design-Time Component](../custom-report-items/creating-a-custom-report-item-design-time-component.md) </span></span>  
 [<span data-ttu-id="2da66-117">Cómo: Implementar un elemento de informe personalizado</span><span class="sxs-lookup"><span data-stu-id="2da66-117">How to: Deploy a Custom Report Item</span></span>](../custom-report-items/how-to-deploy-a-custom-report-item.md)  
  
  
