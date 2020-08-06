---
title: Agregar código a un informe (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- code [Reporting Services]
- custom code [Reporting Services]
- expressions [Reporting Services], code
- adding code
- reports [Reporting Services], code
ms.assetid: 00ef8fc6-99fe-49b2-8a22-7eb475881dc4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c1964e69d00e1a27da29ce8cfb73b7bee1bece7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746785"
---
# <a name="add-code-to-a-report-ssrs"></a><span data-ttu-id="ed458-102">Agregar código a un informe (SSRS)</span><span class="sxs-lookup"><span data-stu-id="ed458-102">Add Code to a Report (SSRS)</span></span>
  <span data-ttu-id="ed458-103">Si lo desea, puede llamar a su propio código personalizado en cualquier expresión.</span><span class="sxs-lookup"><span data-stu-id="ed458-103">In any expression, you can call your own custom code.</span></span> <span data-ttu-id="ed458-104">Puede proporcionar el código de estas dos formas:</span><span class="sxs-lookup"><span data-stu-id="ed458-104">You can provide code in the following two ways:</span></span>  
  
-   <span data-ttu-id="ed458-105">Incrustando el código escrito en [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] directamente en el informe.</span><span class="sxs-lookup"><span data-stu-id="ed458-105">Embed code written in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] directly in your report.</span></span> <span data-ttu-id="ed458-106">Si el código hace referencia a un ensamblado de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] que no es <xref:System.Math> ni <xref:System.Convert>, debe agregar la referencia al informe.</span><span class="sxs-lookup"><span data-stu-id="ed458-106">If your code refers to a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] that is not <xref:System.Math> or <xref:System.Convert>, you must add the reference to the report.</span></span> <span data-ttu-id="ed458-107">Para más información, vea [Agregar una referencia de ensamblado a un informe &#40;SSRS&#41;](add-an-assembly-reference-to-a-report-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ed458-107">For more information, see [Add an Assembly Reference to a Report &#40;SSRS&#41;](add-an-assembly-reference-to-a-report-ssrs.md).</span></span> <span data-ttu-id="ed458-108">Para más información sobre otras referencias que puede usar desde el código, vea [Referencias a ensamblados y código personalizado en expresiones en el Diseñador de informes &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ed458-108">For more information about other references you can make from your code, see [Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span></span>  
  
-   <span data-ttu-id="ed458-109">Proporcionando un ensamblado de código personalizado usando [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed458-109">Provide a custom code assembly by using the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="ed458-110">Si proporciona un ensamblado personalizado, debe instalarlo tanto en el equipo donde crea el informe como en el servidor de informes donde ve el informe.</span><span class="sxs-lookup"><span data-stu-id="ed458-110">If you provide a custom assembly, you must install it on both the computer where you author the report and the report server where you view the report.</span></span> <span data-ttu-id="ed458-111">Para más información, consulte [Using Custom Assemblies with Reports](../custom-assemblies/using-custom-assemblies-with-reports.md).</span><span class="sxs-lookup"><span data-stu-id="ed458-111">For more information, see [Using Custom Assemblies with Reports](../custom-assemblies/using-custom-assemblies-with-reports.md).</span></span>  
  
### <a name="to-add-embedded-code-to-a-report"></a><span data-ttu-id="ed458-112">Para agregar código incrustado a un informe</span><span class="sxs-lookup"><span data-stu-id="ed458-112">To add embedded code to a report</span></span>  
  
1.  <span data-ttu-id="ed458-113">En la vista **Diseño** , haga clic con el botón derecho en la superficie de diseño (fuera del borde del informe) y, después, haga clic en **Propiedades del informe**.</span><span class="sxs-lookup"><span data-stu-id="ed458-113">In **Design** view, right-click the design surface outside the border of the report and click **Report Properties**.</span></span>  
  
2.  <span data-ttu-id="ed458-114">Haga clic en **Código**.</span><span class="sxs-lookup"><span data-stu-id="ed458-114">Click **Code**.</span></span>  
  
3.  <span data-ttu-id="ed458-115">En **Código personalizado**, escriba el código.</span><span class="sxs-lookup"><span data-stu-id="ed458-115">In **Custom code**, type the code.</span></span> <span data-ttu-id="ed458-116">Los errores en el código generan advertencias al ejecutar el informe.</span><span class="sxs-lookup"><span data-stu-id="ed458-116">Errors in the code produce warnings when the report runs.</span></span> <span data-ttu-id="ed458-117">En el ejemplo siguiente se crea una función personalizada denominada `ChangeWord` que reemplaza la palabra "`Bike`" por "`Bicycle`".</span><span class="sxs-lookup"><span data-stu-id="ed458-117">The following example creates a custom function named `ChangeWord` that replaces the word "`Bike`" with "`Bicycle`".</span></span>  
  
    ```  
    Public Function ChangeWord(ByVal s As String) As String  
       Dim strBuilder As New System.Text.StringBuilder(s)  
       If s.Contains("Bike") Then  
          strBuilder.Replace("Bike", "Bicycle")  
          Return strBuilder.ToString()  
          Else : Return s  
       End If  
    End Function  
    ```  
  
4.  <span data-ttu-id="ed458-118">En el ejemplo siguiente se muestra cómo pasar un campo de conjunto de datos denominado Category a esta función en una expresión:</span><span class="sxs-lookup"><span data-stu-id="ed458-118">The following example shows how to pass a dataset field named Category to this function in an expression:</span></span>  
  
    ```  
    =Code.ChangeWord(Fields!Category.Value)  
    ```  
  
     <span data-ttu-id="ed458-119">Si agrega esta expresión a una celda de tabla que muestre valores de categoría, cada vez que la palabra "Bike" aparezca en el campo de conjunto de datos para esa fila, el valor de la celda de tabla muestra en su lugar la palabra "Bicycle".</span><span class="sxs-lookup"><span data-stu-id="ed458-119">If you add this expression to a table cell that displays category values, whenever the word "Bike" is in the dataset field for that row, the table cell value displays the word "Bicycle" instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed458-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ed458-120">See Also</span></span>  
 <span data-ttu-id="ed458-121">[Propiedades del informe (cuadro de diálogo), Código](../report-properties-dialog-box-code.md) </span><span class="sxs-lookup"><span data-stu-id="ed458-121">[Report Properties Dialog Box, Code](../report-properties-dialog-box-code.md) </span></span>  
 <span data-ttu-id="ed458-122">[Ejemplos de expresiones &#40;Generador de informes y SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ed458-122">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="ed458-123">Usar referencias a la colección de parámetros &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ed458-123">Parameters Collection References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-parameters-collection-references-report-builder.md)  
  
  
