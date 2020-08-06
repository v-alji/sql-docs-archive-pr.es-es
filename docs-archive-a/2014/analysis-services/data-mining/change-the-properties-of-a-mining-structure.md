---
title: Cambiar las propiedades de una estructura de minería de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], properties
ms.assetid: 03b16897-2e36-42b8-9f7d-db1b9b898401
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2c1e63ad5fada770394e2fc283e0e592319281b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743699"
---
# <a name="change-the-properties-of-a-mining-structure"></a><span data-ttu-id="a737e-102">Cambiar las propiedades de una estructura de minería de datos</span><span class="sxs-lookup"><span data-stu-id="a737e-102">Change the Properties of a Mining Structure</span></span>
  <span data-ttu-id="a737e-103">Hay dos tipos de propiedades en una estructura de minería de datos que pueden modificarse:</span><span class="sxs-lookup"><span data-stu-id="a737e-103">There are two kinds of properties on a mining structure, both of which can be modified:</span></span>  
  
-   <span data-ttu-id="a737e-104">Propiedades de la estructura de minería de datos que afectan a la estructura entera</span><span class="sxs-lookup"><span data-stu-id="a737e-104">Properties of the mining structure that affect the entire structure</span></span>  
  
-   <span data-ttu-id="a737e-105">Propiedades de columnas individuales en la estructura</span><span class="sxs-lookup"><span data-stu-id="a737e-105">Properties on individual columns in the structure</span></span>  
  
 <span data-ttu-id="a737e-106">Tenga en cuenta que algunas de estas propiedades dependen de la configuración de otras propiedades.</span><span class="sxs-lookup"><span data-stu-id="a737e-106">Note that some properties are dependent on other property settings.</span></span> <span data-ttu-id="a737e-107">Por ejemplo, no puede establecer las propiedades que controlan el comportamiento de discretización (como <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationMethod%2A> o <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationBucketCount%2A>) hasta que haya establecido el tipo de datos de la columna en `Discretized`.</span><span class="sxs-lookup"><span data-stu-id="a737e-107">For example, you cannot set properties that control binning behavior (such as <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationMethod%2A> or <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationBucketCount%2A>) until you have set the data type of the column to `Discretized`.</span></span>  
  
 <span data-ttu-id="a737e-108">Para más información sobre las propiedades de la estructura de minería, vea [Columnas de la estructura de minería de datos](mining-structure-columns.md).</span><span class="sxs-lookup"><span data-stu-id="a737e-108">For more information about mining structure properties, see [Mining Structure Columns](mining-structure-columns.md).</span></span>  
  
### <a name="to-change-the-properties-of-a-mining-structure"></a><span data-ttu-id="a737e-109">Para cambiar las propiedades de una estructura de minería de datos</span><span class="sxs-lookup"><span data-stu-id="a737e-109">To change the properties of a mining structure</span></span>  
  
1.  <span data-ttu-id="a737e-110">En la pestaña **Estructura de minería de datos** del Diseñador de minería de datos, haga clic con el botón derecho en la estructura de minería de datos o en una columna de la estructura de minería de datos y, después, seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a737e-110">On the **Mining Structure** tab in Data Mining Designer, right-click either the mining structure or a column in the mining structure, and then select **Properties**.</span></span>  
  
     <span data-ttu-id="a737e-111">La ventana **Propiedades** se abre en la parte derecha de la pantalla, si es que aún no estaba visible.</span><span class="sxs-lookup"><span data-stu-id="a737e-111">The **Properties** window opens on the right side of the screen, if it was not already visible.</span></span>  
  
2.  <span data-ttu-id="a737e-112">En la ventana **Propiedades** , seleccione el valor correspondiente a la propiedad que desee cambiar y, a continuación, escriba el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="a737e-112">In the **Properties** window, select the value that corresponds to the property that you want to change, and then enter the new value.</span></span>  
  
     <span data-ttu-id="a737e-113">El nuevo valor tendrá efecto cuando se seleccione otro elemento diferente en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="a737e-113">The new value will take effect when you select a different element in the designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a737e-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a737e-114">See Also</span></span>  
 [<span data-ttu-id="a737e-115">Tareas y procedimientos de las estructuras de minería de datos</span><span class="sxs-lookup"><span data-stu-id="a737e-115">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
  
