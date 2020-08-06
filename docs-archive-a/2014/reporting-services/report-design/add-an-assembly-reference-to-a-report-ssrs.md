---
title: Agregar una referencia de ensamblado a un informe (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- code [Reporting Services]
- custom assemblies [Reporting Services], referencing
- custom code [Reporting Services]
- adding assembly references
- assemblies [Reporting Services], references
ms.assetid: 0a03939e-48ce-4c30-b227-98533f2e0ccb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 23dda0c65589e55849f906c621e42ce70f0d7ab5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675212"
---
# <a name="add-an-assembly-reference-to-a-report-ssrs"></a><span data-ttu-id="246f7-102">Agregar una referencia de ensamblado a un informe (SSRS)</span><span class="sxs-lookup"><span data-stu-id="246f7-102">Add an Assembly Reference to a Report (SSRS)</span></span>
  <span data-ttu-id="246f7-103">Al insertar código personalizado que contiene referencias a clases [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] que no están en <xref:System.Math> ni en <xref:System.Convert>, necesita proporcionar una referencia de ensamblado al informe para que el procesador de informes pueda resolver los nombres.</span><span class="sxs-lookup"><span data-stu-id="246f7-103">When you embed custom code that contains references to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] classes that are not in <xref:System.Math> or <xref:System.Convert>, you must provide an assembly reference to the report so that the report processor can resolve the names.</span></span> <span data-ttu-id="246f7-104">Para más información, vea [Agregar código a un informe &#40;SSRS&#41;](add-code-to-a-report-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="246f7-104">For more information, see [Add Code to a Report &#40;SSRS&#41;](add-code-to-a-report-ssrs.md).</span></span>  
  
### <a name="to-add-an-assembly-reference-to-a-report"></a><span data-ttu-id="246f7-105">Para agregar una referencia de ensamblado a un informe</span><span class="sxs-lookup"><span data-stu-id="246f7-105">To add an assembly reference to a report</span></span>  
  
1.  <span data-ttu-id="246f7-106">En la vista **Diseño** , haga clic con el botón derecho en la superficie de diseño (fuera del borde del informe) y, después, haga clic en **Propiedades del informe**.</span><span class="sxs-lookup"><span data-stu-id="246f7-106">In **Design** view, right-click the design surface outside the border of the report and click **Report Properties**.</span></span>  
  
2.  <span data-ttu-id="246f7-107">Haga clic en **Referencias**.</span><span class="sxs-lookup"><span data-stu-id="246f7-107">Click **References**.</span></span>  
  
3.  <span data-ttu-id="246f7-108">En **Agregar o quitar ensamblados**, haga clic en **Agregar** y, a continuación, haga clic en el botón de puntos suspensivos para buscar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="246f7-108">In **Add or remove assemblies**, click **Add** and then click the ellipsis button to browse to the assembly.</span></span>  
  
4.  <span data-ttu-id="246f7-109">En **Agregar o quitar clases**, haga clic en **Agregar** y, a continuación, escriba el nombre de la clase y especifique un nombre de instancia para usarlo dentro del informe.</span><span class="sxs-lookup"><span data-stu-id="246f7-109">In **Add or remove classes**, click **Add** and then type name of the class and provide an instance name to use within the report.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="246f7-110">Especifique un nombre de clase e instancia solo para miembros basados en instancias.</span><span class="sxs-lookup"><span data-stu-id="246f7-110">Specify a class and instance name only for instance-based members.</span></span> <span data-ttu-id="246f7-111">No especifique miembros estáticos en la lista **Clases** .</span><span class="sxs-lookup"><span data-stu-id="246f7-111">Do not specify static members in the **Classes** list.</span></span> <span data-ttu-id="246f7-112">Para obtener más información, vea [Referencias a ensamblados y código personalizado en expresiones en el Diseñador de informes &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md)subyacente.</span><span class="sxs-lookup"><span data-stu-id="246f7-112">For more information, see [Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="246f7-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="246f7-113">See Also</span></span>  
 <span data-ttu-id="246f7-114">[Usar ensamblados personalizados con informes](../custom-assemblies/using-custom-assemblies-with-reports.md) </span><span class="sxs-lookup"><span data-stu-id="246f7-114">[Using Custom Assemblies with Reports](../custom-assemblies/using-custom-assemblies-with-reports.md) </span></span>  
 [<span data-ttu-id="246f7-115">Propiedades del informe (cuadro de diálogo), Referencias</span><span class="sxs-lookup"><span data-stu-id="246f7-115">Report Properties Dialog Box, References</span></span>](../report-properties-dialog-box-references.md)  
  
  
