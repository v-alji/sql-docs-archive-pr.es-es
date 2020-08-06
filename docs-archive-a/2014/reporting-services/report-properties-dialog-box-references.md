---
title: Propiedades del informe (cuadro de diálogo), referencias | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10530"
- sql12.rtp.rptdesigner.reportproperties.references.f1
ms.assetid: 4639d368-9918-4bb1-9953-7a724ca78dea
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4b28ea0865d37bdc56054d6b23dc8c82d9279b08
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746740"
---
# <a name="report-properties-dialog-box-references"></a><span data-ttu-id="af814-102">Propiedades del informe (cuadro de diálogo), Referencias</span><span class="sxs-lookup"><span data-stu-id="af814-102">Report Properties Dialog Box, References</span></span>
  <span data-ttu-id="af814-103">Seleccione **Referencias** en el cuadro de diálogo **Propiedades del informe** para agregar o quitar referencias a ensamblados personalizados u otros ensamblados externos, así como instancias de clases personalizadas que las expresiones usarán en la definición de informe.</span><span class="sxs-lookup"><span data-stu-id="af814-103">Select **References** on the **Report Properties** dialog box to add or remove references to custom or other external assemblies and custom class instances that are used by expressions in the report definition.</span></span>  
  
## <a name="options"></a><span data-ttu-id="af814-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="af814-104">Options</span></span>  
 <span data-ttu-id="af814-105">**Agregar o quitar ensamblados**</span><span class="sxs-lookup"><span data-stu-id="af814-105">**Add or remove assemblies**</span></span>  
 <span data-ttu-id="af814-106">Muestra los ensamblados a los que el informe hace referencia.</span><span class="sxs-lookup"><span data-stu-id="af814-106">Lists the assemblies that the report references.</span></span> <span data-ttu-id="af814-107">El ensamblado debe estar disponible en el equipo donde está instalada la herramienta que está usando para diseñar el informe y en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="af814-107">The assembly must be available on the computer on which the tool you are using to design the report is installed and on the report server.</span></span> <span data-ttu-id="af814-108">El nombre de la referencia debe coincidir exactamente con el contenido de las **\<CodeModule>** etiquetas del archivo de lenguaje de definición de informes (. rdl).</span><span class="sxs-lookup"><span data-stu-id="af814-108">The name of the reference must match the contents of **\<CodeModule>** tags in the Report Definition Language (.rdl) file exactly.</span></span>  
  
 <span data-ttu-id="af814-109">**Add**</span><span class="sxs-lookup"><span data-stu-id="af814-109">**Add**</span></span>  
 <span data-ttu-id="af814-110">Haga clic en esta opción para agregar un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="af814-110">Click to add an assembly.</span></span> <span data-ttu-id="af814-111">Haga clic en el botón de puntos suspensivos (...) para abrir el cuadro de diálogo **abrir** y seleccionar los ensamblados necesarios para completar el procesamiento del informe y la evaluación de la expresión.</span><span class="sxs-lookup"><span data-stu-id="af814-111">Click the ellipsis (...) button to open the **Open** dialog box and select the assemblies necessary to complete report processing and expression evaluation.</span></span>  
  
 <span data-ttu-id="af814-112">**Eliminar**</span><span class="sxs-lookup"><span data-stu-id="af814-112">**Delete**</span></span>  
 <span data-ttu-id="af814-113">Para quitar una referencia de ensamblado de la lista, seleccione el nombre del ensamblado y haga clic en el botón **Quitar** .</span><span class="sxs-lookup"><span data-stu-id="af814-113">To remove an assembly reference from the list, select the assembly name and click the **Remove** button.</span></span>  
  
 <span data-ttu-id="af814-114">**Agregar o quitar clases**</span><span class="sxs-lookup"><span data-stu-id="af814-114">**Add or remove classes**</span></span>  
 <span data-ttu-id="af814-115">Muestra las instancias de clases que se utilizan en el informe.</span><span class="sxs-lookup"><span data-stu-id="af814-115">Lists the class instances that are used by the report.</span></span> <span data-ttu-id="af814-116">Solo los miembros basados en instancias, no los miembros estáticos, utilizan la lista de clases.</span><span class="sxs-lookup"><span data-stu-id="af814-116">The class list is used only by instance-based members, not static members.</span></span>  
  
 <span data-ttu-id="af814-117">**Add**</span><span class="sxs-lookup"><span data-stu-id="af814-117">**Add**</span></span>  
 <span data-ttu-id="af814-118">Haga clic en esta opción para agregar una referencia de clase.</span><span class="sxs-lookup"><span data-stu-id="af814-118">Click to add a class reference.</span></span> <span data-ttu-id="af814-119">Haga clic en el botón de puntos suspensivos (...) para abrir el cuadro de diálogo **abrir** y seleccionar las clases necesarias para completar el procesamiento del informe y la evaluación de la expresión.</span><span class="sxs-lookup"><span data-stu-id="af814-119">Click the ellipsis (...) button to open the **Open** dialog box and select the classes necessary to complete report processing and expression evaluation.</span></span>  
  
 <span data-ttu-id="af814-120">**Eliminar**</span><span class="sxs-lookup"><span data-stu-id="af814-120">**Delete**</span></span>  
 <span data-ttu-id="af814-121">Para eliminar la instancia de clase, selecciónela y haga clic en el botón **Quitar** .</span><span class="sxs-lookup"><span data-stu-id="af814-121">To delete the class instance, select it and click the **Remove** button.</span></span>  
  
 <span data-ttu-id="af814-122">**Arriba**</span><span class="sxs-lookup"><span data-stu-id="af814-122">**Up**</span></span>  
 <span data-ttu-id="af814-123">Para las clases que tienen dependencias, puede mover esta referencia hacia arriba en la lista.</span><span class="sxs-lookup"><span data-stu-id="af814-123">For classes that have dependencies, you can move this reference higher in the list.</span></span>  
  
 <span data-ttu-id="af814-124">**Bajar**</span><span class="sxs-lookup"><span data-stu-id="af814-124">**Down**</span></span>  
 <span data-ttu-id="af814-125">Para las clases que tienen dependencias, puede mover esta referencia hacia abajo en la lista.</span><span class="sxs-lookup"><span data-stu-id="af814-125">For classes that have dependencies, you can move this reference lower in the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af814-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="af814-126">See Also</span></span>  
 <span data-ttu-id="af814-127">[Referencias a ensamblados y código personalizado en expresiones en el Diseñador de informes &#40;SSRS&#41;](report-design/custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="af814-127">[Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](report-design/custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md) </span></span>  
 <span data-ttu-id="af814-128">[Las referencias a las colecciones de variables de informe y de grupo &#40;Generador de informes y SSRS&#41;](report-design/built-in-collections-report-and-group-variables-references-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="af814-128">[Report and Group Variables Collections References &#40;Report Builder and SSRS&#41;](report-design/built-in-collections-report-and-group-variables-references-report-builder.md) </span></span>  
 [<span data-ttu-id="af814-129">Ejemplos de expresiones &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="af814-129">Expression Examples &#40;Report Builder and SSRS&#41;</span></span>](report-design/expression-examples-report-builder-and-ssrs.md)  
  
  
