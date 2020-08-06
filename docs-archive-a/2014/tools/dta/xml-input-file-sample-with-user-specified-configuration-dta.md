---
title: Ejemplo de archivo de entrada XML con configuración especificada por el usuario (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- sample applications [DTA]
ms.assetid: b29c9716-e5c3-4003-9efb-3ade2197b630
author: stevestein
ms.author: sstein
ms.openlocfilehash: 121972518aa114e16cc81517d52a9d9656b067c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675082"
---
# <a name="xml-input-file-sample-with-user-specified-configuration-dta"></a><span data-ttu-id="1a8ef-102">Ejemplo de archivo de entrada XML con configuración especificada por el usuario (DTA)</span><span class="sxs-lookup"><span data-stu-id="1a8ef-102">XML Input File Sample with User-specified Configuration (DTA)</span></span>
  <span data-ttu-id="1a8ef-103">Copie y pegue este ejemplo de archivo de entrada XML que especifica una configuración especificada por el usuario con el elemento **Configuration** en un editor XML o editor de texto.</span><span class="sxs-lookup"><span data-stu-id="1a8ef-103">Copy and paste this sample of an XML input file that specifies a user-specified configuration with the **Configuration** element into your favorite XML editor or text editor.</span></span> <span data-ttu-id="1a8ef-104">Esto le permitirá realizar análisis de escenarios condicionales.</span><span class="sxs-lookup"><span data-stu-id="1a8ef-104">This enables you to perform "what-if" analysis.</span></span> <span data-ttu-id="1a8ef-105">Los análisis de escenarios condicionales implican el uso del elemento **Configuration** para especificar un conjunto de estructuras de diseño físico hipotéticas para la base de datos que se quiere optimizar.</span><span class="sxs-lookup"><span data-stu-id="1a8ef-105">"What-if" analysis involves using the **Configuration** element to specify a set of hypothetical physical design structures for the database you want to tune.</span></span> <span data-ttu-id="1a8ef-106">A continuación se utiliza el Asistente para la optimización de motor de base de datos para analizar los efectos de la ejecución de una carga de trabajo en esta configuración hipotética con el objetivo de descubrir si mejora el rendimiento a la hora de procesar las consultas.</span><span class="sxs-lookup"><span data-stu-id="1a8ef-106">Then you use Database Engine Tuning Advisor to analyze the effects of running a workload against this hypothetical configuration to find out whether it improves query processing performance.</span></span> <span data-ttu-id="1a8ef-107">Este tipo de análisis tiene la ventaja de evaluar la nueva configuración sin incurrir en la sobrecarga que supone implementarla realmente.</span><span class="sxs-lookup"><span data-stu-id="1a8ef-107">This type of analysis provides the advantage of evaluating the new configuration without incurring the overhead of actually implementing it.</span></span> <span data-ttu-id="1a8ef-108">Si la configuración hipotética no proporciona las mejoras de rendimiento que desea, es fácil modificarla y volver a analizarla hasta conseguir la configuración que produzca los resultados necesarios.</span><span class="sxs-lookup"><span data-stu-id="1a8ef-108">If your hypothetical configuration does not provide the performance improvements you want, it is easy to change it and analyze it again until you reach the configuration that produces the results you need.</span></span>  
  
 <span data-ttu-id="1a8ef-109">Una vez copiado el ejemplo en la herramienta de edición, sustituya los valores especificados en los elementos **Server**, **Database**, **Schema**, **Table**, **Workload**, **TuningOptions**y **Configuration** por los de la sesión de optimización concreta.</span><span class="sxs-lookup"><span data-stu-id="1a8ef-109">After copying this sample into your editing tool, replace the values specified for the **Server**, **Database**, **Schema**, **Table**, **Workload**, **TuningOptions**, and **Configuration** elements with those for your specific tuning session.</span></span> <span data-ttu-id="1a8ef-110">Para obtener más información sobre todos los atributos y elementos secundarios que se pueden usar con estos elementos, vea [Referencia del archivo de entrada XML &#40;Asistente para la optimización de motor de base de datos&#41;](xml-input-file-reference-database-engine-tuning-advisor.md).</span><span class="sxs-lookup"><span data-stu-id="1a8ef-110">For more information about all of the attributes and child elements that you can use with these elements, see the [XML Input File Reference &#40;Database Engine Tuning Advisor&#41;](xml-input-file-reference-database-engine-tuning-advisor.md).</span></span> <span data-ttu-id="1a8ef-111">En el siguiente ejemplo, se utiliza únicamente un subconjunto de opciones de atributos y elementos secundarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="1a8ef-111">The following sample uses only a subset of available attribute and child element options.</span></span>  
  
## <a name="code"></a><span data-ttu-id="1a8ef-112">Código</span><span class="sxs-lookup"><span data-stu-id="1a8ef-112">Code</span></span>  
 [!code-xml[InputFileSamples#UserSpecifiedConfigInputFile](../../snippets/xml/SQL14/dta_xml/inputfilesamples/xml/dta_xml_input_file_samples.xml#userspecifiedconfiginputfile)]  
  
## <a name="comments"></a><span data-ttu-id="1a8ef-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1a8ef-113">Comments</span></span>  
  
-   <span data-ttu-id="1a8ef-114">Cuando se especifica el modo **Absolute** para el elemento **Configuration** (`Configuration SpecificationMode="Absolute"`), no se permite quitar las estructuras de diseño físico.</span><span class="sxs-lookup"><span data-stu-id="1a8ef-114">Dropping physical design structures is not supported if you specify the **Absolute** mode for the **Configuration** element (`Configuration SpecificationMode="Absolute"`).</span></span>  
  
-   <span data-ttu-id="1a8ef-115">No es posible crear y quitar la misma estructura de diseño físico en ningún modo (**Relative** o **Absolute**) del elemento **Configuration** .</span><span class="sxs-lookup"><span data-stu-id="1a8ef-115">You cannot create and drop the same physical design structure in either mode (**Relative** or **Absolute**) of the **Configuration** element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a8ef-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1a8ef-116">See Also</span></span>  
 <span data-ttu-id="1a8ef-117">[Iniciar y utilizar el Asistente para la optimización de motor de base de datos](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="1a8ef-117">[Start and Use the Database Engine Tuning Advisor](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md) </span></span>  
 <span data-ttu-id="1a8ef-118">[Ver y trabajar con la salida del Asistente para la optimización de motor de base de datos](../../relational-databases/performance/view-and-work-with-the-output-from-the-database-engine-tuning-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="1a8ef-118">[View and Work with the Output from the Database Engine Tuning Advisor](../../relational-databases/performance/view-and-work-with-the-output-from-the-database-engine-tuning-advisor.md) </span></span>  
 [<span data-ttu-id="1a8ef-119">Referencia del archivo de entrada XML &#40;Asistente para la optimización de motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="1a8ef-119">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
