---
title: Usar ensamblados personalizados con informes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom assemblies [Reporting Services]
- assemblies [Reporting Services], custom
- custom assemblies [Reporting Services], about custom assemblies
ms.assetid: 53d141d0-2185-466a-84dc-7b90d284da3d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f77b9da44ebb57617bd45e43d1e1e847e9074662
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745068"
---
# <a name="using-custom-assemblies-with-reports"></a><span data-ttu-id="5d0dc-102">Usar ensamblados personalizados con informes</span><span class="sxs-lookup"><span data-stu-id="5d0dc-102">Using Custom Assemblies with Reports</span></span>
  <span data-ttu-id="5d0dc-103">En [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], puede escribir código personalizado para los valores de elementos de informe, estilos y formato.</span><span class="sxs-lookup"><span data-stu-id="5d0dc-103">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can write custom code for report item values, styles, and formatting.</span></span> <span data-ttu-id="5d0dc-104">Por ejemplo, puede utilizar código personalizado para dar formato a las monedas según la configuración regional, marcar ciertos valores con formato especial o aplicar otras reglas de negocios en vigor en la compañía.</span><span class="sxs-lookup"><span data-stu-id="5d0dc-104">For example, you can use custom code to format currencies based on locale, flag certain values with special formatting, or apply other business rules that are in practice for your company.</span></span> <span data-ttu-id="5d0dc-105">Una manera de incluir este código en los informes es crear un ensamblado de código personalizado mediante al [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] que puede hacer referencia desde los archivos de definición de informe.</span><span class="sxs-lookup"><span data-stu-id="5d0dc-105">One way to include this code in your reports is to create a custom code assembly using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] that you can reference from within your report definition files.</span></span> <span data-ttu-id="5d0dc-106">El servidor llama a las funciones de los ensamblados personalizados cuando se ejecuta un informe.</span><span class="sxs-lookup"><span data-stu-id="5d0dc-106">The server calls the functions in your custom assemblies when a report is run.</span></span> <span data-ttu-id="5d0dc-107">Los ensamblados personalizados se pueden utilizar para recuperar funciones especializadas que piensa utilizar en los informes.</span><span class="sxs-lookup"><span data-stu-id="5d0dc-107">Custom assemblies can be used to retrieve specialized functions that you plan to use in your reports.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5d0dc-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5d0dc-108">In This Section</span></span>  
 [<span data-ttu-id="5d0dc-109">Hacer referencia a ensamblados en un archivo RDL</span><span class="sxs-lookup"><span data-stu-id="5d0dc-109">Referencing Assemblies in an RDL File</span></span>](referencing-assemblies-in-an-rdl-file.md)  
 <span data-ttu-id="5d0dc-110">Describe cómo hacer referencia a ensamblados personalizados en un archivo de lenguaje RDL (Report Definition Language).</span><span class="sxs-lookup"><span data-stu-id="5d0dc-110">Describes how to reference your custom assemblies in a report definition language file.</span></span>  
  
 [<span data-ttu-id="5d0dc-111">Implementación de un ensamblado personalizado</span><span class="sxs-lookup"><span data-stu-id="5d0dc-111">Deploying a Custom Assembly</span></span>](deploying-a-custom-assembly.md)  
 <span data-ttu-id="5d0dc-112">Describe cómo implementar un ensamblado personalizado en el Diseñador de informes y el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="5d0dc-112">Describes how to deploy a custom assembly to Report Designer and the report server.</span></span>  
  
 [<span data-ttu-id="5d0dc-113">Usar ensamblados personalizados con nombre seguro</span><span class="sxs-lookup"><span data-stu-id="5d0dc-113">Using Strong-Named Custom Assemblies</span></span>](using-strong-named-custom-assemblies.md)  
 <span data-ttu-id="5d0dc-114">Describe cómo utilizar ensamblados personalizados con nombres seguros.</span><span class="sxs-lookup"><span data-stu-id="5d0dc-114">Describes how to use custom assemblies with strong names.</span></span>  
  
 [<span data-ttu-id="5d0dc-115">Validar los permisos en ensamblados personalizados</span><span class="sxs-lookup"><span data-stu-id="5d0dc-115">Asserting Permissions in Custom Assemblies</span></span>](asserting-permissions-in-custom-assemblies.md)  
 <span data-ttu-id="5d0dc-116">Describe cómo implementar los ensamblados personalizados con permisos limitados  concretos, y cómo validar esos permisos en el código.</span><span class="sxs-lookup"><span data-stu-id="5d0dc-116">Describes how to deploy custom assemblies with limited and specific permissions and how to assert those permissions in code.</span></span>  
  
 [<span data-ttu-id="5d0dc-117">Acceso a los ensamblados personalizados a través de expresiones</span><span class="sxs-lookup"><span data-stu-id="5d0dc-117">Accessing Custom Assemblies Through Expressions</span></span>](accessing-custom-assemblies-through-expressions.md)  
 <span data-ttu-id="5d0dc-118">Describe cómo llamar a los métodos de ensamblado personalizados como expresiones de informe en las definiciones de informe.</span><span class="sxs-lookup"><span data-stu-id="5d0dc-118">Describes how to call custom assembly methods as report expressions in your report definitions.</span></span>  
  
 [<span data-ttu-id="5d0dc-119">Inicializar objetos de ensamblados personalizados</span><span class="sxs-lookup"><span data-stu-id="5d0dc-119">Initializing Custom Assembly Objects</span></span>](initializing-custom-assembly-objects.md)  
 <span data-ttu-id="5d0dc-120">Describe cómo inicializar los valores para los objetos de ensamblado personalizados llamados desde un informe.</span><span class="sxs-lookup"><span data-stu-id="5d0dc-120">Describes how to initialize values for custom assembly objects called from a report.</span></span>  
  
 [<span data-ttu-id="5d0dc-121">Procedimientos: Depuración de ensamblados personalizados</span><span class="sxs-lookup"><span data-stu-id="5d0dc-121">How to: Debug Custom Assemblies</span></span>](how-to-debug-custom-assemblies.md)  
 <span data-ttu-id="5d0dc-122">Describe cómo depurar el código de ensamblado personalizado.</span><span class="sxs-lookup"><span data-stu-id="5d0dc-122">Describes how to debug your custom assembly code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d0dc-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5d0dc-123">See Also</span></span>  
 [<span data-ttu-id="5d0dc-124">Lenguaje RDL (Report Definition Language) &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="5d0dc-124">Report Definition Language &#40;SSRS&#41;</span></span>](../reports/report-definition-language-ssrs.md)  
  
  
