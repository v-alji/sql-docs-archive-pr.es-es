---
title: Referencia a ensamblados en un archivo RDL | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- RDL [Reporting Services], referencing assemblies
- referencing custom assemblies
- custom assemblies [Reporting Services], referencing
- Report Definition Language, referencing assemblies
- report definition files [Reporting Services]
ms.assetid: 9a48e552-7d47-4243-9be1-894990c506d9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 14593717d2319d7d702fd0c414e0c24428006f51
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744529"
---
# <a name="referencing-assemblies-in-an-rdl-file"></a><span data-ttu-id="50fe2-102">Hacer referencia a ensamblados en un archivo RDL</span><span class="sxs-lookup"><span data-stu-id="50fe2-102">Referencing Assemblies in an RDL File</span></span>
  <span data-ttu-id="50fe2-103">Para admitir el uso de ensamblados de código personalizados en archivos de definición de informe, se incluyen dos elementos del lenguaje RDL (Report Definition Language) en la especificación RDL: **CodeModules** y **Classes**.</span><span class="sxs-lookup"><span data-stu-id="50fe2-103">To support the use of custom code assemblies in report definition files, two Report Definition Language (RDL) elements are included in the RDL specification: the **CodeModules** element and the **Classes** element.</span></span>  
  
 <span data-ttu-id="50fe2-104">El elemento **CodeModules** le permite hacer referencia a los ensamblados de código administrado en las expresiones de informe.</span><span class="sxs-lookup"><span data-stu-id="50fe2-104">The **CodeModules** element enables you to refer to managed code assemblies in report expressions.</span></span> <span data-ttu-id="50fe2-105">**CodeModules** es un elemento de nivel superior que contiene la referencia al ensamblado que se utiliza en los archivos de definición de informe para llamar a las funciones especializadas.</span><span class="sxs-lookup"><span data-stu-id="50fe2-105">**CodeModules** is a top-level element that contains the reference to the assembly that you use in your report definition files to call specialized functions.</span></span> <span data-ttu-id="50fe2-106">Una entrada en una definición de informe que admita el uso de un ensamblado personalizado podría parecerse a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="50fe2-106">An entry in a report definition that supports the use of a custom assembly might look like the following:</span></span>  
  
```  
<CodeModules>  
   <CodeModule>CurrencyConversion, Version=1.0.1363.31103, Culture=neutral, PublicKeyToken=null</CodeModule>  
</CodeModules>  
```  
  
 <span data-ttu-id="50fe2-107">En lugar de llamar a <xref:System.Reflection.Assembly.Load%2A> desde el código personalizado, registre los ensamblados personalizados agregando manualmente los elementos **CodeModule** al archivo RDL o usando la pestaña **Referencias** del cuadro de diálogo **Propiedades del informe**.</span><span class="sxs-lookup"><span data-stu-id="50fe2-107">Instead of calling <xref:System.Reflection.Assembly.Load%2A> from your custom code, register your custom assemblies by either manually adding **CodeModule** elements to your RDL file or by using the **References** tab of the **Report Properties** dialog.</span></span> <span data-ttu-id="50fe2-108">Para obtener más información, vea [Referencias a ensamblados y código personalizado en expresiones en el Diseñador de informes &#40;SSRS&#41;](../report-design/custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md)subyacente.</span><span class="sxs-lookup"><span data-stu-id="50fe2-108">For more information, see [Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](../report-design/custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span></span>  
  
 <span data-ttu-id="50fe2-109">El elemento **Classes** admite el uso de miembros de instancia en una definición de informe.</span><span class="sxs-lookup"><span data-stu-id="50fe2-109">The **Classes** element supports the use of instance members in a report definition.</span></span> <span data-ttu-id="50fe2-110">**Classes** es un elemento de nivel superior que contiene una referencia al nombre de clase y un nombre de instancia.</span><span class="sxs-lookup"><span data-stu-id="50fe2-110">**Classes** is a top-level element that contains a reference to the class name and an instance name.</span></span> <span data-ttu-id="50fe2-111">La entrada de una definición de informe que admita el uso de miembros de instancia podría parecerse a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="50fe2-111">An entry in a report definition that supports the use of instance members might look like the following:</span></span>  
  
```  
<Classes>  
   <Class>  
      <ClassName>CurrencyConversion.DollarCurrencyConversion</ClassName>  
      <InstanceName>m_myDollarConversion</InstanceName>  
   </Class>  
</Classes>  
```  
  
 <span data-ttu-id="50fe2-112">Para más información, vea [Acceso a los ensamblados personalizados a través de expresiones](accessing-custom-assemblies-through-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="50fe2-112">For more information, see [Accessing Custom Assemblies Through Expressions](accessing-custom-assemblies-through-expressions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50fe2-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="50fe2-113">See Also</span></span>  
 [<span data-ttu-id="50fe2-114">Usar ensamblados personalizados con informes</span><span class="sxs-lookup"><span data-stu-id="50fe2-114">Using Custom Assemblies with Reports</span></span>](using-custom-assemblies-with-reports.md)  
  
  
