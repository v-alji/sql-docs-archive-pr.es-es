---
title: Eliminar una vista del origen de datos (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- deleting data source views
- data source views [Analysis Services], deleting
- removing data source views
ms.assetid: ae3f5ca0-ecbf-4b52-8386-eb457719d854
author: minewiskan
ms.author: owend
ms.openlocfilehash: 24b587e8d8961161ea803915c31d117c11f7cf2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677245"
---
# <a name="delete-a-data-source-view-analysis-services"></a><span data-ttu-id="f2ad7-102">Eliminar una vista del origen de datos (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="f2ad7-102">Delete a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="f2ad7-103">Si ha dejado de usar una vista del origen de datos (DSV) en un proyecto de OLAP, puede eliminarla del proyecto en [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2ad7-103">If you are no longer using a data source view (DSV) in an OLAP project, you can delete it from the project in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="f2ad7-104">La eliminación de una DSV es permanente.</span><span class="sxs-lookup"><span data-stu-id="f2ad7-104">Deleting a DSV is permanent.</span></span> <span data-ttu-id="f2ad7-105">No es posible restaurar una DSV eliminada en un proyecto o base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f2ad7-105">You cannot restore a deleted DSV to a [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or database.</span></span>  
  
 <span data-ttu-id="f2ad7-106">No se pueden eliminar las DSV de las que dependen otros objetos desde una base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] abierta por [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] en el modo en línea.</span><span class="sxs-lookup"><span data-stu-id="f2ad7-106">DSVs that other objects depend on cannot be deleted from an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database opened by [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] in online mode.</span></span> <span data-ttu-id="f2ad7-107">Para eliminar una DSV desde un proyecto que está conectado a una base de datos que se ejecuta en un servidor, primero debe eliminar todos los objetos de la base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que dependen de esa DSV antes de eliminar la DSV.</span><span class="sxs-lookup"><span data-stu-id="f2ad7-107">To delete a DSV from a project that is connected o a database running on a server, you must first delete all objects in the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database that depend on that DSV before deleting the DSV itself.</span></span>  
  
 <span data-ttu-id="f2ad7-108">Si elimina una DSV, invalidará otros objetos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que dependen de ella, de modo que, antes de eliminar la DSV, verá la lista de objetos que quedarían invalidados cuando se quite la DSV.</span><span class="sxs-lookup"><span data-stu-id="f2ad7-108">Deleting a DSV will invalidate other [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects that depend on it, so before you delete the DSV, you will see the list of objects that will become invalid once the DSV is removed.</span></span> <span data-ttu-id="f2ad7-109">Revise esta lista con atención para asegurarse de que no contiene objetos que todavía espera usar.</span><span class="sxs-lookup"><span data-stu-id="f2ad7-109">Review this list carefully to be sure that it does not include objects you still expect to use.</span></span>  
  
 <span data-ttu-id="f2ad7-110">![Eliminar objetos, cuadro de diálogo](../media/ssas-olapdsv-deleteobjects.gif "Eliminar objetos, cuadro de diálogo")</span><span class="sxs-lookup"><span data-stu-id="f2ad7-110">![Delete Objects dialog box](../media/ssas-olapdsv-deleteobjects.gif "Delete Objects dialog box")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2ad7-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f2ad7-111">See Also</span></span>  
 <span data-ttu-id="f2ad7-112">[Vistas del origen de datos en modelos multidimensionales](data-source-views-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="f2ad7-112">[Data Source Views in Multidimensional Models](data-source-views-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="f2ad7-113">Cambiar las propiedades de una vista del origen de datos &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="f2ad7-113">Change Properties in a Data Source View &#40;Analysis Services&#41;</span></span>](change-properties-in-a-data-source-view-analysis-services.md)  
  
  
