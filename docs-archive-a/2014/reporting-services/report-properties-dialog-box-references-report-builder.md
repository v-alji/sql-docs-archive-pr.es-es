---
title: Propiedades del informe (cuadro de diálogo), referencias (Generador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10082"
ms.assetid: 3414c857-8ea6-4fc4-a6d5-b4883c039efa
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2c28e9053a1c13f8d0e0b7b44f3b1a037976c318
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746743"
---
# <a name="report-properties-dialog-box-references-report-builder"></a><span data-ttu-id="14b3f-102">Propiedades del informe (cuadro de diálogo), Referencias (Generador de informes)</span><span class="sxs-lookup"><span data-stu-id="14b3f-102">Report Properties Dialog Box, References (Report Builder)</span></span>
  <span data-ttu-id="14b3f-103">Seleccione **Referencias** en el cuadro de diálogo **Propiedades del informe** para agregar o quitar referencias a ensamblados personalizados u otros ensamblados externos, así como instancias de clases personalizadas que las expresiones usarán en la definición de informe.</span><span class="sxs-lookup"><span data-stu-id="14b3f-103">Select **References** on the **Report Properties** dialog box to add or remove references to custom or other external assemblies and custom class instances that are used by expressions in the report definition.</span></span> <span data-ttu-id="14b3f-104">Los ensamblados personalizados no se admiten en el modo local en el Generador de informes.</span><span class="sxs-lookup"><span data-stu-id="14b3f-104">Custom assemblies are not supported in local mode in Report Builder.</span></span> <span data-ttu-id="14b3f-105">Para crear informes que usen ensamblados personalizados, use Diseñador de informes en [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="14b3f-105">To author reports that use custom assemblies, use Report Designer in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="14b3f-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="14b3f-106">Options</span></span>  
 <span data-ttu-id="14b3f-107">**Agregar o quitar ensamblados**</span><span class="sxs-lookup"><span data-stu-id="14b3f-107">**Add or remove assemblies**</span></span>  
 <span data-ttu-id="14b3f-108">Muestra los ensamblados a los que el informe hace referencia.</span><span class="sxs-lookup"><span data-stu-id="14b3f-108">Lists the assemblies that the report references.</span></span> <span data-ttu-id="14b3f-109">El ensamblado debe estar disponible en el equipo donde está instalada la herramienta que está usando para diseñar el informe y en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="14b3f-109">The assembly must be available on the computer on which the tool you are using to design the report is installed and on the report server.</span></span> <span data-ttu-id="14b3f-110">El nombre de la referencia debe coincidir exactamente con el contenido de las **\<CodeModule>** etiquetas del archivo de lenguaje de definición de informes (. rdl).</span><span class="sxs-lookup"><span data-stu-id="14b3f-110">The name of the reference must match the contents of **\<CodeModule>** tags in the Report Definition Language (.rdl) file exactly.</span></span>  
  
 <span data-ttu-id="14b3f-111">**Add**</span><span class="sxs-lookup"><span data-stu-id="14b3f-111">**Add**</span></span>  
 <span data-ttu-id="14b3f-112">Haga clic en esta opción para agregar un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="14b3f-112">Click to add an assembly.</span></span> <span data-ttu-id="14b3f-113">Haga clic en el botón de puntos suspensivos (...) para abrir el cuadro de diálogo **abrir** y seleccionar los ensamblados necesarios para completar el procesamiento del informe y la evaluación de la expresión.</span><span class="sxs-lookup"><span data-stu-id="14b3f-113">Click the ellipsis (...) button to open the **Open** dialog box and select the assemblies necessary to complete report processing and expression evaluation.</span></span>  
  
 <span data-ttu-id="14b3f-114">**Remove**</span><span class="sxs-lookup"><span data-stu-id="14b3f-114">**Remove**</span></span>  
 <span data-ttu-id="14b3f-115">Para quitar una referencia de ensamblado de la lista, seleccione el nombre del ensamblado y haga clic en el botón **Quitar** .</span><span class="sxs-lookup"><span data-stu-id="14b3f-115">To remove an assembly reference from the list, select the assembly name and click the **Remove** button.</span></span>  
  
 <span data-ttu-id="14b3f-116">**Agregar o quitar clases**</span><span class="sxs-lookup"><span data-stu-id="14b3f-116">**Add or remove classes**</span></span>  
 <span data-ttu-id="14b3f-117">Muestra las instancias de clases que se utilizan en el informe.</span><span class="sxs-lookup"><span data-stu-id="14b3f-117">Lists the class instances that are used by the report.</span></span> <span data-ttu-id="14b3f-118">Solo los miembros basados en instancias, no los miembros estáticos, utilizan la lista de clases.</span><span class="sxs-lookup"><span data-stu-id="14b3f-118">The class list is used only by instance-based members, not static members.</span></span>  
  
 <span data-ttu-id="14b3f-119">**Add**</span><span class="sxs-lookup"><span data-stu-id="14b3f-119">**Add**</span></span>  
 <span data-ttu-id="14b3f-120">Haga clic en esta opción para agregar una referencia de clase.</span><span class="sxs-lookup"><span data-stu-id="14b3f-120">Click to add a class reference.</span></span> <span data-ttu-id="14b3f-121">Haga clic en el botón de puntos suspensivos (...) para abrir el cuadro de diálogo **abrir** y seleccionar las clases necesarias para completar el procesamiento del informe y la evaluación de la expresión.</span><span class="sxs-lookup"><span data-stu-id="14b3f-121">Click the ellipsis (...) button to open the **Open** dialog box and select the classes necessary to complete report processing and expression evaluation.</span></span>  
  
 <span data-ttu-id="14b3f-122">**Remove**</span><span class="sxs-lookup"><span data-stu-id="14b3f-122">**Remove**</span></span>  
 <span data-ttu-id="14b3f-123">Para eliminar la instancia de clase, selecciónela y haga clic en el botón **Quitar** .</span><span class="sxs-lookup"><span data-stu-id="14b3f-123">To delete the class instance, select it and click the **Remove** button.</span></span>  
  
 <span data-ttu-id="14b3f-124">**Arriba**</span><span class="sxs-lookup"><span data-stu-id="14b3f-124">**Up**</span></span>  
 <span data-ttu-id="14b3f-125">Para las clases que tienen dependencias, puede mover esta referencia hacia arriba en la lista.</span><span class="sxs-lookup"><span data-stu-id="14b3f-125">For classes that have dependencies, you can move this reference higher in the list.</span></span>  
  
 <span data-ttu-id="14b3f-126">**Bajar**</span><span class="sxs-lookup"><span data-stu-id="14b3f-126">**Down**</span></span>  
 <span data-ttu-id="14b3f-127">Para las clases que tienen dependencias, puede mover esta referencia hacia abajo en la lista.</span><span class="sxs-lookup"><span data-stu-id="14b3f-127">For classes that have dependencies, you can move this reference lower in the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14b3f-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="14b3f-128">See Also</span></span>  
 <span data-ttu-id="14b3f-129">[Generador de informes ayuda para cuadros de diálogo, paneles y asistentes](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="14b3f-129">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 [<span data-ttu-id="14b3f-130">Expresiones &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="14b3f-130">Expressions &#40;Report Builder and SSRS&#41;</span></span>](report-design/expressions-report-builder-and-ssrs.md)  
  
  
