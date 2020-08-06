---
title: Habilitar el modo de diseño de DirectQuery (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 71fc7ebd-2e86-4a76-994b-66d3a57bcc9b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8ccd2dc88f447e78f6558565a89accc341eac37c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673912"
---
# <a name="enable-directquery-design-mode-ssas-tabular"></a><span data-ttu-id="2edfa-102">Habilitar el modo de diseño de DirectQuery (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="2edfa-102">Enable DirectQuery Design Mode (SSAS Tabular)</span></span>
  <span data-ttu-id="2edfa-103">Para crear un modelo en el modo DirectQuery, primero debe cambiar el entorno de tiempo de diseño para que admita al usuario del modo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="2edfa-103">To create a model in DirectQuery mode, you must first change the design-time environment so that it supports the user of DirectQuery mode.</span></span> <span data-ttu-id="2edfa-104">Al hacerlo, el diseñador también hará lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2edfa-104">When you do so, the designer will also do the following:</span></span>  
  
-   <span data-ttu-id="2edfa-105">Habilitará el uso de las propiedades de implementación de DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="2edfa-105">Enable the use of the DirectQuery deployment properties.</span></span>  
  
-   <span data-ttu-id="2edfa-106">Cambiará la base de datos del área de trabajo para que se ejecute en un modo híbrido que utilice la caché para el diseño.</span><span class="sxs-lookup"><span data-stu-id="2edfa-106">Change the workspace database to run in a hybrid mode that uses the cache for designing.</span></span> <span data-ttu-id="2edfa-107">Cuando implemente definitivamente el modelo, el modo se cambiará de nuevo al valor especificado en las propiedades de implementación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="2edfa-107">When you actually deploy the model, the mode will be changed back to whatever value you specified in the project deployment properties.</span></span>  
  
-   <span data-ttu-id="2edfa-108">Deshabilitará las características de diseño que sean incompatibles con el modo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="2edfa-108">Disable design features that are incompatible with DirectQuery mode.</span></span>  
  
-   <span data-ttu-id="2edfa-109">Validará el modelo existente.</span><span class="sxs-lookup"><span data-stu-id="2edfa-109">Validate the existing model.</span></span>  
  
 <span data-ttu-id="2edfa-110">Este procedimiento describe cómo habilitar el modo DirectQuery en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="2edfa-110">This procedure describes how to enable DirectQuery mode in the designer.</span></span>  
  
### <a name="to-enable-use-of-directquery-in-a-model"></a><span data-ttu-id="2edfa-111">Para habilitar el uso de DirectQuery en un modelo</span><span class="sxs-lookup"><span data-stu-id="2edfa-111">To enable use of DirectQuery in a model</span></span>  
  
1.  <span data-ttu-id="2edfa-112">Abra el archivo de la solución en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2edfa-112">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the solution file.</span></span>  
  
2.  <span data-ttu-id="2edfa-113">En el Explorador de objetos, haga doble clic en el archivo Model.bim.</span><span class="sxs-lookup"><span data-stu-id="2edfa-113">In Object Explorer, double-click the Model.bim file.</span></span>  
  
3.  <span data-ttu-id="2edfa-114">En el panel **Propiedades** , cambie la propiedad **DirectQueryMode**a **On**.</span><span class="sxs-lookup"><span data-stu-id="2edfa-114">In the **Properties** pane, change the property, **DirectQueryMode**, to **On**.</span></span>  
  
4.  <span data-ttu-id="2edfa-115">Si hay errores, abra la **Lista de errores** en Visual Studio y solucione los problemas que impiden que el modelo se cambie al modo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="2edfa-115">If there are errors, in Visual Studio, open the **Error List** and resolve any problems that would prevent the model from being switched to DirectQuery mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2edfa-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2edfa-116">See Also</span></span>  
 [<span data-ttu-id="2edfa-117">Modo DirectQuery &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="2edfa-117">DirectQuery Mode &#40;SSAS Tabular&#41;</span></span>](directquery-mode-ssas-tabular.md)  
  
  
