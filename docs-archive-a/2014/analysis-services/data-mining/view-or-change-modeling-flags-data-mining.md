---
title: Ver o cambiar las marcas de modelado (minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d1169735-fb18-417b-b8d6-9a161e444020
author: minewiskan
ms.author: owend
ms.openlocfilehash: bf0edd827321685a2d6a9041759328a7ac6e7cbd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746620"
---
# <a name="view-or-change-modeling-flags-data-mining"></a><span data-ttu-id="95890-102">Ver o cambiar marcas de modelado (minería de datos)</span><span class="sxs-lookup"><span data-stu-id="95890-102">View or Change Modeling Flags (Data Mining)</span></span>
  <span data-ttu-id="95890-103">Las marcas de modelado son propiedades que se activan en una columna de estructura de minería de datos o columnas de modelo de minería de datos para controlar cómo procesa los datos el algoritmo durante el análisis.</span><span class="sxs-lookup"><span data-stu-id="95890-103">Modeling flags are properties that you set on a mining structure column or mining model columns to control how the algorithm processes the data during analysis.</span></span>  
  
 <span data-ttu-id="95890-104">En el Diseñador de minería de datos, puede ver y modificar las marcas de modelado asociadas a una estructura de minería de datos o a una columna de minería de datos examinando las propiedades de la estructura o del modelo.</span><span class="sxs-lookup"><span data-stu-id="95890-104">In Data Mining Designer, you can view and modify the modeling flags associated with a mining structure or mining column by viewing the properties of the structure or model.</span></span> <span data-ttu-id="95890-105">También puede establecer las marcas de modelado utilizando DMX, AMO o XMLA.</span><span class="sxs-lookup"><span data-stu-id="95890-105">You can also set modeling flags by using DMX, AMO, or XMLA.</span></span>  
  
 <span data-ttu-id="95890-106">Este procedimiento describe cómo cambiar las marcas de modelado en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="95890-106">This procedure describes how to change the modeling flags in the designer.</span></span>  
  
### <a name="view-or-change-the-modeling-flag-for-a-structure-column-or-model-column"></a><span data-ttu-id="95890-107">Ver o cambiar la marca de modelado de una columna de la estructura o columna del modelo</span><span class="sxs-lookup"><span data-stu-id="95890-107">View or change the modeling flag for a structure column or model column</span></span>  
  
1.  <span data-ttu-id="95890-108">En SQL Server Design Studio, abra el Explorador de soluciones y, a continuación, haga doble clic en la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="95890-108">In SQL Server Design Studio, open Solution Explorer, and then double-click the mining structure.</span></span>  
  
2.  <span data-ttu-id="95890-109">Para establecer la marca de modelado NOT NULL, haga clic en la pestaña **estructura de minería de datos** . Para establecer las marcas de REGRESOr o MODEL_EXISTENCE_ONLY, haga clic en la pestaña **modelo de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="95890-109">To set the NOT NULL modeling flag, click the **Mining Structure** tab. To set the REGRESSOR or MODEL_EXISTENCE_ONLY flags, click the **Mining Model** tab.</span></span>  
  
3.  <span data-ttu-id="95890-110">Haga clic con el botón derecho en la columna que quiere ver o cambiar y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="95890-110">Right-click the column you want to view or change, and select **Properties**.</span></span>  
  
4.  <span data-ttu-id="95890-111">Para agregar una nueva marca de modelado, haga clic en el cuadro de texto situado junto a la propiedad **ModelingFlags** y active la casilla o casillas de las marcas de modelado que desea utilizar.</span><span class="sxs-lookup"><span data-stu-id="95890-111">To add a new modeling flag, click the text box next to the **ModelingFlags** property, and select the check box or check boxes for the modeling flags you want to use.</span></span>  
  
     <span data-ttu-id="95890-112">Las marcas de modelado solo se muestran si son adecuadas para el tipo de datos de la columna.</span><span class="sxs-lookup"><span data-stu-id="95890-112">Modeling flags are displayed only if they are appropriate for the column data type.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="95890-113">Después de cambiar una marca de modelado, debe volver a procesar el modelo.</span><span class="sxs-lookup"><span data-stu-id="95890-113">After you change a modeling flag, you must reprocess the model.</span></span>  
  
### <a name="get-the-modeling-flags-used-in-the-model"></a><span data-ttu-id="95890-114">Obtener las marcas de modelado utilizadas en el modelo</span><span class="sxs-lookup"><span data-stu-id="95890-114">Get the modeling flags used in the model</span></span>  
  
-   <span data-ttu-id="95890-115">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], abra una ventana Consulta DMX y escriba una consulta como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="95890-115">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open a DMX Query window, and type a query like the following:</span></span>  
  
    ```  
    SELECT COLUMN_NAME, CONTENT_TYPE, MODELING_FLAG  
    FROM $system.DMSCHEMA_MINING_COLUMNS  
    WHERE MODEL_NAME = 'Forecasting'  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="95890-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="95890-116">See Also</span></span>  
 <span data-ttu-id="95890-117">[Tareas y procedimientos del modelo de minería de datos](mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="95890-117">[Mining Model Tasks and How-tos](mining-model-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="95890-118">Marcas de modelado &#40;Minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="95890-118">Modeling Flags &#40;Data Mining&#41;</span></span>](modeling-flags-data-mining.md)  
  
  
