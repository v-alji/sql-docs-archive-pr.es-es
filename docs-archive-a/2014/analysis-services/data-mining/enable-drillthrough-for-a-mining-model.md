---
title: Habilitar la obtención de detalles para un modelo de minería de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], how-to topics
- drillthrough [Analysis Services]
ms.assetid: 4fa44f60-ef9a-4b59-98c0-c0baf1195c8e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0a6adfc389776f91132e527130f50f61c9783d9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663183"
---
# <a name="enable-drillthrough-for-a-mining-model"></a><span data-ttu-id="1612d-102">Habilitar la obtención de detalles para un modelo de minería</span><span class="sxs-lookup"><span data-stu-id="1612d-102">Enable Drillthrough for a Mining Model</span></span>
  <span data-ttu-id="1612d-103">Si ha habilitado la obtención de detalles para un modelo de minería de datos, al examinar el modelo, puede recuperar información detallada sobre los casos que se usaron para crear el modelo.</span><span class="sxs-lookup"><span data-stu-id="1612d-103">If you have enabled drillthrough for a mining model, when you browse the model you can retrieve detailed information about the cases that were used to create the model.</span></span> <span data-ttu-id="1612d-104">Para ver esta información, debe tener los permisos necesarios y se debe de haber procesado la estructura.</span><span class="sxs-lookup"><span data-stu-id="1612d-104">To view this information, you must have the necessary permissions, and the structure must have already been processed.</span></span>  
  
 <span data-ttu-id="1612d-105">**Permisos** : para que un usuario obtenga detalles de los datos del modelo o de los datos de la estructura, el usuario debe ser miembro de un rol con permisos [AllowDrillThrough](https://docs.microsoft.com/bi-reference/assl/properties/allowdrillthrough-element-assl) en el modelo o en la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="1612d-105">**Permissions** For a user to drill through to either model data or structure data, the user must be a member of a role that has [AllowDrillThrough](https://docs.microsoft.com/bi-reference/assl/properties/allowdrillthrough-element-assl) permissions on the mining model or mining structure.</span></span> <span data-ttu-id="1612d-106">Los permisos de obtención de detalles se establecen por separado en la estructura y en el modelo.</span><span class="sxs-lookup"><span data-stu-id="1612d-106">Drillthrough permissions are set separately on the structure and model.</span></span>  
  
-   <span data-ttu-id="1612d-107">Los permisos de obtención de detalles en el modelo permiten obtener detalles del modelo, incluso si no se dispone de permisos en la estructura.</span><span class="sxs-lookup"><span data-stu-id="1612d-107">Drillthrough permissions on the model enable you to drill through from the model, even if you do not have permissions on the structure.</span></span>  
  
-   <span data-ttu-id="1612d-108">Los permisos de obtención de detalles en la estructura ofrecen la posibilidad adicional de incluir columnas de la estructura en las consultas de obtención de detalles del modelo, mediante la función [StructureColumn &#40;DMX&#41;](/sql/dmx/structurecolumn-dmx).</span><span class="sxs-lookup"><span data-stu-id="1612d-108">Drillthrough permissions on the structure provide the additional ability to include structure columns in drillthrough queries from the model, by using the [StructureColumn &#40;DMX&#41;](/sql/dmx/structurecolumn-dmx) function.</span></span> <span data-ttu-id="1612d-109">También puede consultar los casos de prueba y entrenamiento de la estructura mediante el uso de la instrucción SELECT... DESDE \<structure> . Sintaxis de CASEs.</span><span class="sxs-lookup"><span data-stu-id="1612d-109">You can also query the training and test cases in the structure by using the SELECT... FROM \<structure>.CASES syntax.</span></span>  
  
 <span data-ttu-id="1612d-110">**Almacenamiento en caché de casos de entrenamiento** : la obtención de detalles funciona recuperando información sobre los casos de entrenamiento de la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="1612d-110">**Caching of training cases** Drillthrough works by retrieving information about the training cases in the mining structure.</span></span> <span data-ttu-id="1612d-111">Esta información se almacena en la caché cuando se procesa la estructura.</span><span class="sxs-lookup"><span data-stu-id="1612d-111">This information is cached when the structure is processed.</span></span> <span data-ttu-id="1612d-112">Por consiguiente, si decide borrar todos los datos de la caché cambiando la propiedad <xref:Microsoft.AnalysisServices.MiningStructureCacheMode> a `ClearAfterProcessing`, la obtención de detalles no funcionará.</span><span class="sxs-lookup"><span data-stu-id="1612d-112">Therefore, if you choose to clear all cached data by changing the <xref:Microsoft.AnalysisServices.MiningStructureCacheMode> property to `ClearAfterProcessing`, drillthrough will not work.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1612d-113">Si los casos de entrenamiento no se han almacenado en la caché, deberá cambiar la propiedad <xref:Microsoft.AnalysisServices.MiningStructureCacheMode> a **KeepTrainingCases** y, después, deberá volver a procesar el modelo antes de ver los datos de los casos.</span><span class="sxs-lookup"><span data-stu-id="1612d-113">If the training cases have not been cached, you must change the <xref:Microsoft.AnalysisServices.MiningStructureCacheMode> property to **KeepTrainingCases** and then reprocess the model before you can view the case data.</span></span>  
  
 <span data-ttu-id="1612d-114">Para obtener más información, vea [Consultas de obtención de detalles &#40;minería de datos&#41;](drillthrough-queries-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="1612d-114">For more information, see [Drillthrough Queries &#40;Data Mining&#41;](drillthrough-queries-data-mining.md).</span></span>  
  
### <a name="to-enable-drillthrough-on-a-mining-model"></a><span data-ttu-id="1612d-115">Para habilitar la obtención de detalles en un modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="1612d-115">To enable drillthrough on a mining model</span></span>  
  
1.  <span data-ttu-id="1612d-116">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], en la pestaña **Modelos de minería de datos** del Diseñador de minería de datos, haga clic con el botón derecho en el nombre del modelo de minería de datos del que quiere habilitar la obtención de detalles y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="1612d-116">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], on the **Mining Models** tab of Data Mining Designer, right-click the name of the mining model on which you want to enable drillthrough, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="1612d-117">En las ventanas **propiedades** , haga clic en **AllowDrillthrough**y seleccione **true**.</span><span class="sxs-lookup"><span data-stu-id="1612d-117">In the **Properties** windows, click **AllowDrillthrough**, and select **True**.</span></span>  
  
3.  <span data-ttu-id="1612d-118">En la pestaña **modelos de minería de datos** , haga clic con el botón secundario en el modelo y seleccione **procesar modelo**.</span><span class="sxs-lookup"><span data-stu-id="1612d-118">In the **Mining Models** tab, right-click the model, and select **Process Model**.</span></span>  
  
### <a name="to-enable-caching-for-a-mining-structure"></a><span data-ttu-id="1612d-119">Para habilitar el almacenamiento en caché para una estructura de minería de datos</span><span class="sxs-lookup"><span data-stu-id="1612d-119">To enable caching for a mining structure</span></span>  
  
1.  <span data-ttu-id="1612d-120">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], en la pestaña **Estructura de minería de datos** del Diseñador de minería de datos, haga clic con el botón derecho en el nombre de la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="1612d-120">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], on the **Mining Structure** tab of Data Mining Designer, right-click the name of the mining structure.</span></span>  
  
2.  <span data-ttu-id="1612d-121">Abra la ventana **Propiedades** .</span><span class="sxs-lookup"><span data-stu-id="1612d-121">Open the **Properties** window.</span></span>  
  
3.  <span data-ttu-id="1612d-122">En la ventana **Propiedades** , busque la propiedad **CacheMode** y seleccione **KeepTrainingCases** en la lista.</span><span class="sxs-lookup"><span data-stu-id="1612d-122">In the **Properties** window, locate the **CacheMode** property, and select **KeepTrainingCases** from the list.</span></span>  
  
4.  <span data-ttu-id="1612d-123">En el menú **Base de datos** , seleccione **Procesar**.</span><span class="sxs-lookup"><span data-stu-id="1612d-123">On the **Database** menu, select **Process**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1612d-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1612d-124">See Also</span></span>  
 [<span data-ttu-id="1612d-125">Consultas de obtención de detalles &#40;minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="1612d-125">Drillthrough Queries &#40;Data Mining&#41;</span></span>](drillthrough-queries-data-mining.md)  
  
  
