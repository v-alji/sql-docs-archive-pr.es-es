---
title: Ver el XML de un proyecto de Analysis Services (SSDT) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- projects [Analysis Services], viewing XML
ms.assetid: dd1a4bc6-57b5-47df-8619-09f921aa6351
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1c320145be2073c741498bed0f10732ac8d528e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749500"
---
# <a name="view-the-xml-for-an-analysis-services-project-ssdt"></a><span data-ttu-id="1126d-102">Ver el XML de un proyecto de Analysis Services (SSDT)</span><span class="sxs-lookup"><span data-stu-id="1126d-102">View the XML for an Analysis Services Project (SSDT)</span></span>
  <span data-ttu-id="1126d-103">Al trabajar con una base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en el modo de proyecto, [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] crea una definición XML para cada objeto de la carpeta del proyecto.</span><span class="sxs-lookup"><span data-stu-id="1126d-103">When you are working with an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database in project mode, [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] creates an XML definition for each object within the project folder.</span></span> <span data-ttu-id="1126d-104">Puede ver el contenido del archivo XML de cada objeto en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1126d-104">You can view the contents of the XML file for each object within [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="1126d-105">También puede editar el archivo XML directamente, aunque en la mayoría de los casos no es aconsejable hacerlo porque podría realizar cambios que eviten que [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]lea el archivo XML.</span><span class="sxs-lookup"><span data-stu-id="1126d-105">You can also edit the XML file directly; however, this is not recommended in most circumstances as you may make changes that make the XML unreadable by [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1126d-106">El código XML de todo un proyecto no se puede ver, sino que hay que ver el código de cada objeto, ya que hay un archivo independiente por objeto.</span><span class="sxs-lookup"><span data-stu-id="1126d-106">You cannot view the xml code for an entire project, but rather you view the code for each object because a separate file exists for each object.</span></span> <span data-ttu-id="1126d-107">La única manera de ver el código de un proyecto completo es compilar el proyecto y ver el código ASSL en el \<project name> archivo. asdatabase.</span><span class="sxs-lookup"><span data-stu-id="1126d-107">The only way to view the code for an entire project is to build the project and view the ASSL code in the \<project name>.asdatabase file.</span></span>  
  
### <a name="to-view-the-xml-code-for-an-object"></a><span data-ttu-id="1126d-108">Para ver el código XML de un objeto</span><span class="sxs-lookup"><span data-stu-id="1126d-108">To view the XML code for an object</span></span>  
  
1.  <span data-ttu-id="1126d-109">Abra el proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1126d-109">Open the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="1126d-110">Haga clic con el botón derecho en el objeto en el Explorador de soluciones y, después, haga clic en **Ver código**.</span><span class="sxs-lookup"><span data-stu-id="1126d-110">Right-click the object in Solution Explorer and then click **View Code**.</span></span>  
  
     <span data-ttu-id="1126d-111">El código XML del objeto se muestra en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1126d-111">The XML code for the object appears in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1126d-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1126d-112">See Also</span></span>  
 [<span data-ttu-id="1126d-113">Generar proyectos de Analysis Services &#40;SSDT&#41;</span><span class="sxs-lookup"><span data-stu-id="1126d-113">Build Analysis Services Projects &#40;SSDT&#41;</span></span>](build-analysis-services-projects-ssdt.md)  
  
  
