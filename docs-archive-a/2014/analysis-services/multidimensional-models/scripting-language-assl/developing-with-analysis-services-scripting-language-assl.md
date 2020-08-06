---
title: Desarrollo con Analysis Services lenguaje de scripting (ASSL) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- Analysis Services Scripting Language
- ASSL
ms.assetid: ce9aca4d-b7ad-451e-bb7f-20c2b0c03f29
author: minewiskan
ms.author: owend
ms.openlocfilehash: fbb64c120e67d5b4ac12e7bd77f0e0c4e5736757
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673350"
---
# <a name="developing-with-analysis-services-scripting-language-assl"></a><span data-ttu-id="a895e-102">Desarrollar aplicaciones con Analysis Services Scripting Language (ASSL)</span><span class="sxs-lookup"><span data-stu-id="a895e-102">Developing with Analysis Services Scripting Language (ASSL)</span></span>
  <span data-ttu-id="a895e-103">El lenguaje de scripting de Analysis Services (ASSL) es una extensión de XMLA que agrega un lenguaje de definición de objetos y un lenguaje de comandos para crear y administrar estructuras Analysis Services directamente en el servidor.</span><span class="sxs-lookup"><span data-stu-id="a895e-103">Analysis Services Scripting Language (ASSL) is an extension to XMLA that adds an object definition language and command language for creating and managing Analysis Services structures directly on the server.</span></span> <span data-ttu-id="a895e-104">Puede utilizar ASSL en la aplicación personalizada para comunicarse con Analysis Services a través del protocolo XMLA.</span><span class="sxs-lookup"><span data-stu-id="a895e-104">You can use ASSL in custom application to communicate with Analysis Services over the XMLA protocol.</span></span> <span data-ttu-id="a895e-105">ASSL consta de dos partes:</span><span class="sxs-lookup"><span data-stu-id="a895e-105">ASSL is made up of two parts:</span></span>  
  
-   <span data-ttu-id="a895e-106">Un lenguaje de definición de datos (DDL), o lenguaje de definición de objetos, que define y describe una instancia de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], así como las bases de datos y los objetos de base de datos que la instancia contiene.</span><span class="sxs-lookup"><span data-stu-id="a895e-106">A Data Definition Language (DDL), or object definition language, defines and describes an instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], as well as the databases and database objects that the instance contains.</span></span>  
  
-   <span data-ttu-id="a895e-107">Un lenguaje de comandos que envía comandos de acción, como `Create`, `Alter`o `Process`, a una instancia de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="a895e-107">A command language that sends action commands, such as `Create`, `Alter`, or `Process`, to an instance of Analysis Services.</span></span> <span data-ttu-id="a895e-108">Este lenguaje de comandos se describe en la [XML for Analysis &#40;XMLA&#41; referencia](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-xmla-reference).</span><span class="sxs-lookup"><span data-stu-id="a895e-108">This command language is discussed in the [XML for Analysis  &#40;XMLA&#41; Reference](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-xmla-reference).</span></span>  
  
 <span data-ttu-id="a895e-109">Para ver el ASSL que describe una solución multidimensional en [!INCLUDE[ssBIDevStudio](../../../includes/ssbidevstudio-md.md)], puede utilizar el comando Ver código en el nivel de proyecto.</span><span class="sxs-lookup"><span data-stu-id="a895e-109">To view the ASSL that describes a multidimensional solution in [!INCLUDE[ssBIDevStudio](../../../includes/ssbidevstudio-md.md)], you can use the View Code command at the project level.</span></span> <span data-ttu-id="a895e-110">También puede crear o modificar el script de ASSL en [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] utilizando el editor de consultas XMLA.</span><span class="sxs-lookup"><span data-stu-id="a895e-110">You can also create or edit ASSL script in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] using the XMLA query editor.</span></span> <span data-ttu-id="a895e-111">Los scripts que cree pueden usarse para administrar objetos o ejecutar comandos en el servidor.</span><span class="sxs-lookup"><span data-stu-id="a895e-111">The scripts you build can be used to manage objects or run commands on the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a895e-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a895e-112">See Also</span></span>  
 <span data-ttu-id="a895e-113">[Objetos y características de objetos ASSL](assl-objects-and-object-characteristics.md) </span><span class="sxs-lookup"><span data-stu-id="a895e-113">[ASSL Objects and Object Characteristics](assl-objects-and-object-characteristics.md) </span></span>  
 <span data-ttu-id="a895e-114">[ASSL convenciones XML](assl-xml-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="a895e-114">[ASSL XML Conventions](assl-xml-conventions.md) </span></span>  
 [<span data-ttu-id="a895e-115">Orígenes de datos y enlaces &#40;SSAS multidimensional&#41;</span><span class="sxs-lookup"><span data-stu-id="a895e-115">Data Sources and Bindings &#40;SSAS Multidimensional&#41;</span></span>](../data-sources-and-bindings-ssas-multidimensional.md)  
  
  
