---
title: Usar variables y parámetros (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- parameters [MDX]
- queries [MDX], variables
- queries [MDX], parameters
- variables [MDX]
ms.assetid: a4754d16-d9c4-49f6-9be0-392180b912e4
author: minewiskan
ms.author: owend
ms.openlocfilehash: fd01cf78ea5e3284aa51cad7dc848176a5dc9298
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748326"
---
# <a name="using-variables-and-parameters-mdx"></a><span data-ttu-id="f1bec-102">Usar variables y parámetros (MDX)</span><span class="sxs-lookup"><span data-stu-id="f1bec-102">Using Variables and Parameters (MDX)</span></span>
  <span data-ttu-id="f1bec-103">En [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] , puede parametrizar una instrucción de expresiones multidimensionales (MDX).</span><span class="sxs-lookup"><span data-stu-id="f1bec-103">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], you can parameterize a Multidimensional Expressions (MDX) statement.</span></span> <span data-ttu-id="f1bec-104">Las instrucciones con parámetros permiten crear instrucciones genéricas que pueden personalizarse en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f1bec-104">A parameterized statement lets you create generic statements that can be customized at runtime.</span></span>  
  
 <span data-ttu-id="f1bec-105">Al crear una instrucción con parámetros se debe identificar el nombre del parámetro mediante un prefijo con el símbolo de arroba (@).</span><span class="sxs-lookup"><span data-stu-id="f1bec-105">In creating a parameterized statement, you identify the parameter name by prefixing the name with the at sign (@).</span></span> <span data-ttu-id="f1bec-106">Por ejemplo, @Year sería un nombre de parámetro válido.</span><span class="sxs-lookup"><span data-stu-id="f1bec-106">For example, @Year would be a valid parameter name</span></span>  
  
 <span data-ttu-id="f1bec-107">MDX solo admite parámetros para valores literales o escalares.</span><span class="sxs-lookup"><span data-stu-id="f1bec-107">MDX supports only parameters for literal or scalar values.</span></span> <span data-ttu-id="f1bec-108">Para crear un parámetro que haga referencia a un miembro, conjunto o tupla debería utilizar una función como [StrToMember](/sql/mdx/strtomember-mdx) o [StrToSet](/sql/mdx/strtoset-mdx).</span><span class="sxs-lookup"><span data-stu-id="f1bec-108">To create a parameter that references a member, set, or tuple, you would have to use a function such as [StrToMember](/sql/mdx/strtomember-mdx) or [StrToSet](/sql/mdx/strtoset-mdx).</span></span>  
  
 <span data-ttu-id="f1bec-109">En el siguiente ejemplo de XML for Analysis (XMLA), el parámetro contendrá @CountryName el país para el que se recuperan los datos del cliente:</span><span class="sxs-lookup"><span data-stu-id="f1bec-109">In the following XML for Analysis (XMLA) example, the @CountryName parameter will contain the country for which customer data is retrieved:</span></span>  
  
```  
<Envelope xmlns="http://schemas.xmlsoap.org/soap/envelope/">  
  <Body>  
    <Execute xmlns="urn:schemas-microsoft-com:xml-analysis">  
      <Command>  
        <Statement>  
select [Measures].members on 0,   
       Filter(Customer.[Customer Geography].Country.members,   
              Customer.[Customer Geography].CurrentMember.Name =  
              @CountryName) on 1  
from [Adventure Works]  
</Statement>  
      </Command>  
      <Properties />  
      <Parameters>  
        <Parameter>  
          <Name>CountryName</Name>  
          <Value>'United Kingdom'</Value>  
        </Parameter>  
      </Parameters>  
    </Execute>  
  </Body>  
</Envelope>  
```  
  
 <span data-ttu-id="f1bec-110">Para utilizar esta funcionalidad con OLE DB, debería usarse la interfaz `ICommandWithParameters`.</span><span class="sxs-lookup"><span data-stu-id="f1bec-110">To use this functionality with OLE DB, you would use the `ICommandWithParameters` interface.</span></span> <span data-ttu-id="f1bec-111">Para utilizar esta funcionalidad con ADOMD.Net, debería usarse la colección **AdomdCommand.Parameters** .</span><span class="sxs-lookup"><span data-stu-id="f1bec-111">To use this functionality with ADOMD.Net, you would use the **AdomdCommand.Parameters** collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1bec-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f1bec-112">See Also</span></span>  
 [<span data-ttu-id="f1bec-113">Aspectos básicos de scripting MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="f1bec-113">MDX Scripting Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-scripting-fundamentals-analysis-services.md)  
  
  
