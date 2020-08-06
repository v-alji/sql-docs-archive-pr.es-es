---
title: ¿Qué&#39;s nuevo (Integration Services)? | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services, what's new
- what's new [Integration Services]
ms.assetid: da6999c7-e5e3-4a59-a284-1da635995af1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 84f0b668407c89e1d6acc3c8cfbda73f129ca19a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676556"
---
# <a name="what39s-new-integration-services"></a><span data-ttu-id="eb9b2-102">Qué&#39;s nuevo (Integration Services)</span><span class="sxs-lookup"><span data-stu-id="eb9b2-102">What&#39;s New (Integration Services)</span></span>
  [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]<span data-ttu-id="eb9b2-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]no ha cambiado con respecto a la versión anterior.</span><span class="sxs-lookup"><span data-stu-id="eb9b2-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] is unchanged from the previous release.</span></span>  
  
 <span data-ttu-id="eb9b2-104">Para obtener información sobre otros [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] productos y tecnologías, consulte [novedades de SQL Server 2014](../sql-server/what-s-new-in-sql-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="eb9b2-104">For information about other [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] products and technologies, see [What's New in SQL Server 2014](../sql-server/what-s-new-in-sql-server-2016.md).</span></span>  
  
 <span data-ttu-id="eb9b2-105">Para obtener más información sobre los cambios relacionados con [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Business Intelligence, consulte [novedades de Analysis Services e inteligencia empresarial](https://docs.microsoft.com/analysis-services/what-s-new-in-analysis-services).</span><span class="sxs-lookup"><span data-stu-id="eb9b2-105">For more information about changes related to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Business Intelligence, see [What's New in Analysis Services and Business Intelligence](https://docs.microsoft.com/analysis-services/what-s-new-in-analysis-services).</span></span>  
  
##  <a name="rich-xml-validation-output-in-the-xml-task"></a><a name="ValidateXML"></a> <span data-ttu-id="eb9b2-106">Salida enriquecida de validación de XML en la tarea XML</span><span class="sxs-lookup"><span data-stu-id="eb9b2-106">Rich XML validation output in the XML Task</span></span>  
 <span data-ttu-id="eb9b2-107">Valide documentos XML y obtenga una salida de error enriquecida habilitando la propiedad `ValidationDetails` de la tarea XML.</span><span class="sxs-lookup"><span data-stu-id="eb9b2-107">Validate XML documents and get rich error output by enabling the `ValidationDetails` property of the XML Task.</span></span> <span data-ttu-id="eb9b2-108">Antes de que la propiedad `ValidationDetails` estuviera disponible, la validación de XML efectuada mediante la tarea XML solo devolvía un resultado true o false, sin información sobre errores o sus ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="eb9b2-108">Before the `ValidationDetails` property was available, XML validation by the XML Task returned only a true or false result, with no information about errors or their locations.</span></span> <span data-ttu-id="eb9b2-109">Ahora, cuando se establece `ValidationDetails` en true, el archivo de salida contiene información detallada sobre cada uno de los errores, incluido el número de línea y la posición.</span><span class="sxs-lookup"><span data-stu-id="eb9b2-109">Now, when you set `ValidationDetails` to true, the output file contains detailed information about every error including the line number and the position.</span></span> <span data-ttu-id="eb9b2-110">Puede usar esta información para comprender, buscar y corregir errores en documentos XML.</span><span class="sxs-lookup"><span data-stu-id="eb9b2-110">You can use this information to understand, locate, and fix errors in XML documents.</span></span> <span data-ttu-id="eb9b2-111">Para obtener más información, vea [Validate XML with the XML Task](control-flow/xml-task.md).</span><span class="sxs-lookup"><span data-stu-id="eb9b2-111">For more info, see [Validate XML with the XML Task](control-flow/xml-task.md).</span></span>  
  
 [!INCLUDE[ssIS](../includes/ssis-md.md)] <span data-ttu-id="eb9b2-112">introdujo la propiedad `ValidationDetails` en [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] Service Pack 2.</span><span class="sxs-lookup"><span data-stu-id="eb9b2-112">introduced the `ValidationDetails` property in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] Service Pack 2.</span></span> <span data-ttu-id="eb9b2-113">Esta nueva propiedad no se anunció ni documentó en su momento.</span><span class="sxs-lookup"><span data-stu-id="eb9b2-113">This new property was not announced or documented at that time.</span></span> <span data-ttu-id="eb9b2-114">La propiedad `ValidationDetails` también se encuentra disponible en [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] y en SQL Server 2016.</span><span class="sxs-lookup"><span data-stu-id="eb9b2-114">The `ValidationDetails` property is also available in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] and in SQL Server 2016.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb9b2-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eb9b2-115">See Also</span></span>  
 [<span data-ttu-id="eb9b2-116">Características admitidas por las ediciones de SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="eb9b2-116">Features Supported by the Editions of SQL Server 2014</span></span>](../getting-started/features-supported-by-the-editions-of-sql-server-2014.md)  
  
  
