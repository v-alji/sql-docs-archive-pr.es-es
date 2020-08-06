---
title: Eliminar un modelo de minería de datos de una estructura de minería de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], mining models
- deleting mining models
- removing mining models
- mining models [Analysis Services], deleting
ms.assetid: 9ab1506b-856e-4762-a663-5adf15ac71e3
author: minewiskan
ms.author: owend
ms.openlocfilehash: 72c79dcdccf6225b8e75144f8b090dcab7506c10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676263"
---
# <a name="delete-a-mining-model-from-a-mining-structure"></a><span data-ttu-id="e6e07-102">Eliminar un modelo de minería de datos de una estructura de minería de datos</span><span class="sxs-lookup"><span data-stu-id="e6e07-102">Delete a Mining Model from a Mining Structure</span></span>
  <span data-ttu-id="e6e07-103">Puede utilizar el Diseñador de minería de datos para eliminar los modelos de minería de datos, bien mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]o bien mediante instrucciones DMX.</span><span class="sxs-lookup"><span data-stu-id="e6e07-103">You can delete mining models by using Data Mining Designer, by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], or by using DMX statements.</span></span>  
  
### <a name="delete-a-mining-model-using-sql-server-data-tools"></a><span data-ttu-id="e6e07-104">Eliminar un modelo de minería de datos mediante las Herramientas de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="e6e07-104">Delete a mining model using SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="e6e07-105">Seleccione la pestaña **Modelos de minería de datos** en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e07-105">Select the **Mining Models** tab in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="e6e07-106">Haga clic con el botón derecho en el modelo que quiere eliminar y, después, seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="e6e07-106">Right-click the model that you want to delete, and select **Delete**.</span></span>  
  
     <span data-ttu-id="e6e07-107">Se abre el cuadro de diálogo **Eliminar objetos** .</span><span class="sxs-lookup"><span data-stu-id="e6e07-107">The **Delete Objects** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="e6e07-108">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="e6e07-108">Click **OK**.</span></span>  
  
### <a name="delete-a-mining-model-using-sql-server-management-studio"></a><span data-ttu-id="e6e07-109">Eliminar un modelo de minería de datos mediante SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e6e07-109">Delete a mining model using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="e6e07-110">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], abra la base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que contiene el modelo.</span><span class="sxs-lookup"><span data-stu-id="e6e07-110">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database that contains the model.</span></span>  
  
2.  <span data-ttu-id="e6e07-111">Expanda **Estructuras de minería de datos**y, a continuación, expanda **Modelos de minería de datos**.</span><span class="sxs-lookup"><span data-stu-id="e6e07-111">Expand **Mining Structures**, and then expand **Mining Models**.</span></span>  
  
3.  <span data-ttu-id="e6e07-112">Haga clic con el botón derecho en el modelo que quiere eliminar y, después, seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="e6e07-112">Right-click the model you want to delete, and select **Delete**.</span></span>  
  
     <span data-ttu-id="e6e07-113">Al eliminar el modelo, no se eliminan los datos de entrenamiento, solo los metadatos y los patrones creados al realizar el entrenamiento del modelo.</span><span class="sxs-lookup"><span data-stu-id="e6e07-113">Deleting the model does not delete the training data, only the metadata and any patterns created when you trained the model.</span></span>  
  
### <a name="delete-a-mining-model-using-dmx"></a><span data-ttu-id="e6e07-114">Eliminar un modelo de minería de datos mediante DMX</span><span class="sxs-lookup"><span data-stu-id="e6e07-114">Delete a mining model using DMX</span></span>  
  
-   [<span data-ttu-id="e6e07-115">DROP MINING MODEL &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="e6e07-115">DROP MINING MODEL &#40;DMX&#41;</span></span>](/sql/dmx/drop-mining-model-dmx)  
  
## <a name="see-also"></a><span data-ttu-id="e6e07-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e6e07-116">See Also</span></span>  
 [<span data-ttu-id="e6e07-117">Tareas y procedimientos de los modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="e6e07-117">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
  
