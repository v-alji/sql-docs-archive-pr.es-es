---
title: Agregar un modelo de minería de datos a una estructura de minería de datos existente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models [Analysis Services], adding
- mining structures [Analysis Services], mining models
- adding mining models
ms.assetid: fcf72300-0674-4e73-a826-9b8eeffefbb5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0afdf5f795303eaa8bb672aa80e68e0f1f891607
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675061"
---
# <a name="add-a-mining-model-to-an-existing-mining-structure"></a><span data-ttu-id="2fe1f-102">Agregar un modelo de minería de datos a una estructura de minería de datos existente</span><span class="sxs-lookup"><span data-stu-id="2fe1f-102">Add a Mining Model to an Existing Mining Structure</span></span>
  <span data-ttu-id="2fe1f-103">Una vez agregado el modelo de minería de datos inicial, podrá agregar más modelos a una estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="2fe1f-103">You can add more mining models to a mining structure, after you add the initial model.</span></span> <span data-ttu-id="2fe1f-104">Los modelos deben incluir columnas que estén presentes en la estructura, pero se puede definir el uso de las columnas de un modo distinto para cada modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="2fe1f-104">Each model must contain columns that exist in the structure, but you can define the usage of the columns differently for each mining model.</span></span> <span data-ttu-id="2fe1f-105">Para obtener más información sobre la forma de definir columnas del modelo de minería de datos, vea [Columnas del modelo de minería de datos](mining-model-columns.md).</span><span class="sxs-lookup"><span data-stu-id="2fe1f-105">For more information about how to define mining models columns, see [Mining Model Columns](mining-model-columns.md).</span></span>  
  
### <a name="to-add-a-mining-model-to-the-structure"></a><span data-ttu-id="2fe1f-106">Para agregar un modelo de minería de datos a la estructura</span><span class="sxs-lookup"><span data-stu-id="2fe1f-106">To add a mining model to the structure</span></span>  
  
1.  <span data-ttu-id="2fe1f-107">En el elemento de menú **Modelo de minería de datos** de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], seleccione **Nuevo modelo de minería de datos**.</span><span class="sxs-lookup"><span data-stu-id="2fe1f-107">From the **Mining Model** menu item in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], select **New Mining Model**.</span></span>  
  
     <span data-ttu-id="2fe1f-108">Se abrirá el cuadro de diálogo **Nuevo modelo de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="2fe1f-108">The **New Mining Model** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="2fe1f-109">En **Nombre del modelo**, escriba un nombre para el nuevo modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="2fe1f-109">Under **Model name**, enter a name for the new mining model.</span></span>  
  
3.  <span data-ttu-id="2fe1f-110">En **Nombre del algoritmo**, seleccione el algoritmo a partir del cual se va a generar el modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="2fe1f-110">Under **Algorithm name**, select the algorithm that the mining model will be built from.</span></span>  
  
4.  <span data-ttu-id="2fe1f-111">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="2fe1f-111">Click **OK**.</span></span>  
  
 <span data-ttu-id="2fe1f-112">Aparece un nuevo modelo de minería de datos en la pestaña **modelos de minería de datos** . El modelo utiliza las columnas predeterminadas que existen en la estructura.</span><span class="sxs-lookup"><span data-stu-id="2fe1f-112">A new mining model appears in the **Mining Models** tab. The model uses the default columns that exist in the structure.</span></span> <span data-ttu-id="2fe1f-113">Para obtener información sobre cómo modificar las columnas, vea [Cambiar las propiedades de un modelo de minería de datos](change-the-properties-of-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="2fe1f-113">For information about how to modify the columns, see [Change the Properties of a Mining Model](change-the-properties-of-a-mining-model.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fe1f-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2fe1f-114">See Also</span></span>  
 [<span data-ttu-id="2fe1f-115">Tareas y procedimientos de los modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="2fe1f-115">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
  
