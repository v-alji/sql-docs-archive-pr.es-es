---
title: Ejemplo de archivo de entrada XML con carga de trabajo insertada (DTA) | Microsoft Docs
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
ms.assetid: 7c04fe1d-6669-44a1-8b73-36d469e9b002
author: stevestein
ms.author: sstein
ms.openlocfilehash: 93b2ab4279378b4cd392d97a9b65f299d0e9c6dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671286"
---
# <a name="xml-input-file-sample-with-inline-workload-dta"></a><span data-ttu-id="8a18c-102">Ejemplo de archivo de entrada XML con carga de trabajo insertada (DTA)</span><span class="sxs-lookup"><span data-stu-id="8a18c-102">XML Input File Sample with Inline Workload (DTA)</span></span>
  <span data-ttu-id="8a18c-103">Copie y pegue este ejemplo de archivo de entrada XML que especifica una carga de trabajo con el elemento **EventString** en un editor XML o editor de texto.</span><span class="sxs-lookup"><span data-stu-id="8a18c-103">Copy and paste this sample of an XML input file that specifies a workload with the **EventString** element into your favorite XML editor or text editor.</span></span> <span data-ttu-id="8a18c-104">Puede utilizar el elemento **EventString** para especificar una carga de trabajo de scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] en el archivo de entrada XML, en lugar de utilizar un archivo de carga de trabajo independiente.</span><span class="sxs-lookup"><span data-stu-id="8a18c-104">You can use the **EventString** element to specify a [!INCLUDE[tsql](../../includes/tsql-md.md)] script workload in the XML input file instead of using a separate workload file.</span></span> <span data-ttu-id="8a18c-105">Una vez copiado el ejemplo en la herramienta de edición, sustituya los valores especificados en los elementos **Server**, **Database**, **Schema**, **Table**, **Workload**, **EventString**y **TuningOptions** por los de la sesión de optimización concreta.</span><span class="sxs-lookup"><span data-stu-id="8a18c-105">After copying this sample into your editing tool, replace the values specified for the **Server**, **Database**, **Schema**, **Table**, **Workload**, **EventString**, and **TuningOptions** elements with those for your specific tuning session.</span></span> <span data-ttu-id="8a18c-106">Para obtener más información sobre todos los atributos y elementos secundarios que se pueden usar con estos elementos, vea [Referencia del archivo de entrada XML &#40;Asistente para la optimización de motor de base de datos&#41;](xml-input-file-reference-database-engine-tuning-advisor.md).</span><span class="sxs-lookup"><span data-stu-id="8a18c-106">For more information about all of the attributes and child elements that you can use with these elements, see the [XML Input File Reference &#40;Database Engine Tuning Advisor&#41;](xml-input-file-reference-database-engine-tuning-advisor.md).</span></span> <span data-ttu-id="8a18c-107">En el siguiente ejemplo, se utiliza únicamente un subconjunto de opciones de atributos y elementos secundarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="8a18c-107">The following sample uses only a subset of available attribute and child element options.</span></span>  
  
## <a name="code"></a><span data-ttu-id="8a18c-108">Código</span><span class="sxs-lookup"><span data-stu-id="8a18c-108">Code</span></span>  
 [!code-xml[InputFileSamples#InlineWorkloadInputFile](../../snippets/xml/SQL14/dta_xml/inputfilesamples/xml/dta_xml_input_file_samples.xml#inlineworkloadinputfile)]  
  
## <a name="comments"></a><span data-ttu-id="8a18c-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8a18c-109">Comments</span></span>  
 <span data-ttu-id="8a18c-110">`USE database_name` se pueden especificar en la carga de trabajo insertada incluida en el elemento **EventString** .</span><span class="sxs-lookup"><span data-stu-id="8a18c-110">`USE database_name` statements can be specified in the inline workload that is contained in the **EventString** element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a18c-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8a18c-111">See Also</span></span>  
 <span data-ttu-id="8a18c-112">[Iniciar y utilizar el Asistente para la optimización de motor de base de datos](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="8a18c-112">[Start and Use the Database Engine Tuning Advisor](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md) </span></span>  
 <span data-ttu-id="8a18c-113">[Ver y trabajar con la salida del Asistente para la optimización de motor de base de datos](../../relational-databases/performance/view-and-work-with-the-output-from-the-database-engine-tuning-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="8a18c-113">[View and Work with the Output from the Database Engine Tuning Advisor](../../relational-databases/performance/view-and-work-with-the-output-from-the-database-engine-tuning-advisor.md) </span></span>  
 [<span data-ttu-id="8a18c-114">Referencia del archivo de entrada XML &#40;Asistente para la optimización de motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="8a18c-114">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
