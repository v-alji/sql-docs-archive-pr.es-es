---
title: Cambiar la partición DirectQuery (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: f9df1e66-dd23-41b4-95eb-af110d10eda4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 43d14785f72d9bfe6406e2b81d3f1b97e9b7cc2e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670702"
---
# <a name="change-the-directquery-partition-ssas-tabular"></a><span data-ttu-id="ff65c-102">Cambiar la partición DirectQuery (SSAS Tabular)</span><span class="sxs-lookup"><span data-stu-id="ff65c-102">Change the DirectQuery Partition (SSAS Tabular)</span></span>
  <span data-ttu-id="ff65c-103">Dado que únicamente se puede designar una partición de una tabla como la partición DirectQuery, Analysis Services utiliza de forma predeterminada la primera partición que se creó en la tabla.</span><span class="sxs-lookup"><span data-stu-id="ff65c-103">Because only one partition in a table can be designated as the DirectQuery partition, by default, Analysis Services uses the first partition that was created in the table.</span></span> <span data-ttu-id="ff65c-104">Durante la creación del proyecto de modelos, puede cambiar la partición DirectQuery utilizando el cuadro de diálogo Administrador de particiones de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff65c-104">During model project authoring, you can change the DirectQuery partition by using the Partition Manager dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="ff65c-105">Para los modelos implementados, puede cambiar la partición DirectQuery utilizando [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff65c-105">For deployed models, you can change the DirectQuery partition by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
### <a name="change-the-directquery-partition-for-a-tabular-model-project"></a><span data-ttu-id="ff65c-106">Cambiar la partición de DirectQuery para un proyecto de modelos tabular</span><span class="sxs-lookup"><span data-stu-id="ff65c-106">Change the DirectQuery partition for a tabular model project</span></span>  
  
1.  <span data-ttu-id="ff65c-107">En [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], en el diseñador de modelos, haga clic en la tabla (pestaña) que contiene la tabla con particiones.</span><span class="sxs-lookup"><span data-stu-id="ff65c-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], in the model designer, click on the table (tab) that contains the partitioned table.</span></span>  
  
2.  <span data-ttu-id="ff65c-108">Haga clic en el menú **Tabla** y en **Particiones**.</span><span class="sxs-lookup"><span data-stu-id="ff65c-108">Click on the **Table** menu, and then click **Partitions**.</span></span>  
  
3.  <span data-ttu-id="ff65c-109">En el **Administrador de particiones**, la partición asignada como la partición DirectQuery actual incluye el prefijo **(DirectQuery)** en el nombre de partición.</span><span class="sxs-lookup"><span data-stu-id="ff65c-109">In **Partition Manager**, the partition that is the current Direct Query partition in indicated by the prefix **(DirectQuery)** on the partition name.</span></span>  
  
     <span data-ttu-id="ff65c-110">Seleccione otra partición en la lista **Particiones** y haga clic en **Establecer como DirectQuery**.</span><span class="sxs-lookup"><span data-stu-id="ff65c-110">Select a different partition from the **Partitions** list, and then click **Set as DirectQuery**.</span></span> <span data-ttu-id="ff65c-111">El botón **Establecer como DirectQuery** no está habilitado si está seleccionada la partición DirectQuery actual, y no está visible si el modelo no se ha habilitado para el modo de consulta directa.</span><span class="sxs-lookup"><span data-stu-id="ff65c-111">The **Set as DirectQuery** button is not enabled when the current DirectQuery partition is selected, and is not visible if the model has not been enabled for Direct Query mode.</span></span>  
  
4.  <span data-ttu-id="ff65c-112">Si es necesario, cambie las opciones de procesamiento y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ff65c-112">If necessary, change the processing options, and then click **OK**.</span></span>  
  
### <a name="change-the-directquery-partition-for-a-deployed-tabular-model"></a><span data-ttu-id="ff65c-113">Cambiar la partición de DirectQuery para un modelo tabular implementado</span><span class="sxs-lookup"><span data-stu-id="ff65c-113">Change the DirectQuery partition for a deployed tabular model</span></span>  
  
1.  <span data-ttu-id="ff65c-114">En [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], abra la base de datos del modelo en el Explorador de objetos.</span><span class="sxs-lookup"><span data-stu-id="ff65c-114">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], open the model database in Object Explorer.</span></span>  
  
2.  <span data-ttu-id="ff65c-115">Expanda el nodo **Tablas** , haga clic con el botón derecho en la tabla con particiones y, después, seleccione **Particiones**.</span><span class="sxs-lookup"><span data-stu-id="ff65c-115">Expand the **Tables** node, then right-click the partitioned table, and then select **Partitions**.</span></span>  
  
     <span data-ttu-id="ff65c-116">La partición designada para su uso con el modo DirectQuery tiene el prefijo (DirectQuery) en el nombre de partición.</span><span class="sxs-lookup"><span data-stu-id="ff65c-116">The partition that is designated for use with DirectQuery mode has the prefix (DirectQuery) on the partition name.</span></span>  
  
3.  <span data-ttu-id="ff65c-117">Para cambiar a una partición diferente, haga clic en el icono **Consulta directa** de la barra de herramientas para abrir el cuadro de diálogo **Establecer partición DirectQuery** .</span><span class="sxs-lookup"><span data-stu-id="ff65c-117">To change to a different partition, click the **Direct Query** toolbar icon to open the **Set DirectQuery Partition** dialog box.</span></span> <span data-ttu-id="ff65c-118">El icono de la barra de herramientas de DirectQuery no está disponible en los modelos no habilitados para la consulta directa.</span><span class="sxs-lookup"><span data-stu-id="ff65c-118">The DirectQuery toolbar icon is not available on models that have not been enabled for Direct Query.</span></span>  
  
4.  <span data-ttu-id="ff65c-119">Elija una partición diferente en la lista desplegable **Nombre de partición** y, a continuación, cambie las opciones de procesamiento de la partición si es necesario.</span><span class="sxs-lookup"><span data-stu-id="ff65c-119">Choose a different partition from the **Partition Name** dropdown list, and then change processing options on the partition if necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff65c-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ff65c-120">See Also</span></span>  
 [<span data-ttu-id="ff65c-121">Particiones &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="ff65c-121">Partitions &#40;SSAS Tabular&#41;</span></span>](tabular-models/partitions-ssas-tabular.md)  
  
  
