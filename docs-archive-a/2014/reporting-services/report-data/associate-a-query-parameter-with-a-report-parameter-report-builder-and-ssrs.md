---
title: Asociar un parámetro de consulta a un parámetro de informe (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- queries [Reporting Services], parameters
- parameters [Reporting Services], queries
ms.assetid: 6d297e1a-ff71-472a-addc-349e863092b5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f65aa36e8910378d68963c8c9990518b661025ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745065"
---
# <a name="associate-a-query-parameter-with-a-report-parameter-report-builder-and-ssrs"></a><span data-ttu-id="8d750-102">Asociar un parámetro de consulta a un parámetro de informe (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="8d750-102">Associate a Query Parameter with a Report Parameter (Report Builder and SSRS)</span></span>
  <span data-ttu-id="8d750-103">Cuando define una consulta de conjunto de datos que contiene una variable de consulta, se analiza el comando de consulta.</span><span class="sxs-lookup"><span data-stu-id="8d750-103">When you define a dataset query that contains a query variable, the query command is parsed.</span></span> <span data-ttu-id="8d750-104">Para cada variable de consulta, se crea un parámetro de informe y un parámetro de conjunto de datos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="8d750-104">For each query variable, a corresponding dataset parameter and report parameter are created.</span></span> <span data-ttu-id="8d750-105">El parámetro de conjunto de datos señala el parámetro de informe.</span><span class="sxs-lookup"><span data-stu-id="8d750-105">The dataset parameter points to the report parameter.</span></span> <span data-ttu-id="8d750-106">Esto permite al usuario especificar un valor que pasa directamente a la consulta.</span><span class="sxs-lookup"><span data-stu-id="8d750-106">This enables a user to enter a value that passes directly to the query.</span></span> <span data-ttu-id="8d750-107">Cada vez que se modifica el comando de consulta, se realiza el mismo proceso.</span><span class="sxs-lookup"><span data-stu-id="8d750-107">Each time you edit the query command, the same process takes place.</span></span>  
  
 <span data-ttu-id="8d750-108">Si cambia el nombre de un parámetro de informe que está enlazado a un parámetro de consulta, deberá vincular manualmente los parámetros de consulta al parámetro de informe con el nuevo nombre; para ello, deberá seguir el procedimiento descrito en este tema.</span><span class="sxs-lookup"><span data-stu-id="8d750-108">If you rename a report parameter that is bound to a query parameter, you need to manually link the query parameters to the renamed report parameter by using the procedure in this topic.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-associate-a-query-parameter-with-a-report-parameter"></a><span data-ttu-id="8d750-109">Para asociar un parámetro de consulta a un parámetro de informe</span><span class="sxs-lookup"><span data-stu-id="8d750-109">To associate a query parameter with a report parameter</span></span>  
  
1.  <span data-ttu-id="8d750-110">En el panel Datos de informe, haga clic con el botón derecho en el conjunto de datos, haga clic en **Propiedades del conjunto de datos**y, después, haga clic en **Parámetros**.</span><span class="sxs-lookup"><span data-stu-id="8d750-110">In the Report Data pane, right-click the dataset, click **Dataset Properties**, and then click **Parameters**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8d750-111"> Si el panel Datos de informe no está visible, haga clic en **Datos de informe** en el menú **Ver** .</span><span class="sxs-lookup"><span data-stu-id="8d750-111">If the Report Data pane is not visible, click **Report Data** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="8d750-112">En la columna **Nombre de parámetro**, busque el nombre del parámetro de consulta.</span><span class="sxs-lookup"><span data-stu-id="8d750-112">In the column **Parameter Name**, find the name of the query parameter.</span></span> <span data-ttu-id="8d750-113">Los nombres de los parámetros se rellenan automáticamente basándose en la consulta.</span><span class="sxs-lookup"><span data-stu-id="8d750-113">Parameter names are automatically populated based on the query.</span></span> <span data-ttu-id="8d750-114">Cada vez que cambia la consulta, la consulta se comprueba para ver si existen nuevos parámetros de consulta.</span><span class="sxs-lookup"><span data-stu-id="8d750-114">Every time you change the query, the query is checked for new query parameters.</span></span> <span data-ttu-id="8d750-115">Los parámetros de consulta creados manualmente no cambian cuando cambia la consulta.</span><span class="sxs-lookup"><span data-stu-id="8d750-115">Query parameters that you create manually are not changed when the query changes.</span></span>  
  
    -   <span data-ttu-id="8d750-116">En **Nombre de parámetro**, busque el nombre del parámetro de consulta tal y como existe en la consulta.</span><span class="sxs-lookup"><span data-stu-id="8d750-116">In **Parameter Name**, find the query parameter name as it exists in the query.</span></span> <span data-ttu-id="8d750-117">También puede agregar manualmente un nuevo parámetro de consulta y escribir un nombre.</span><span class="sxs-lookup"><span data-stu-id="8d750-117">You can also manually add a new query parameter and enter a name.</span></span>  
  
    -   <span data-ttu-id="8d750-118">En **Valor de parámetro**, escriba o seleccione una expresión que se evalúe como el valor que se va a pasar al parámetro de consulta.</span><span class="sxs-lookup"><span data-stu-id="8d750-118">In **Parameter Value**, type or select an expression that evaluates to the value to pass to the query parameter.</span></span> <span data-ttu-id="8d750-119">Éste es normalmente el nombre del parámetro de informe.</span><span class="sxs-lookup"><span data-stu-id="8d750-119">This is typically the name of the report parameter.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="8d750-120">El valor de los parámetros de consulta no está limitado a parámetros de informe.</span><span class="sxs-lookup"><span data-stu-id="8d750-120">You are not limited to report parameters as values for a query parameter.</span></span> <span data-ttu-id="8d750-121">Como valor del parámetro se puede utilizar cualquier expresión que se evalúe como un valor.</span><span class="sxs-lookup"><span data-stu-id="8d750-121">You can use any expression that evaluates to a value for the parameter value.</span></span>  
  
3.  <span data-ttu-id="8d750-122">Repita el paso 2 para otros parámetros de consulta.</span><span class="sxs-lookup"><span data-stu-id="8d750-122">Repeat step 2 for additional query parameters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d750-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8d750-123">See Also</span></span>  
 <span data-ttu-id="8d750-124">[Conjuntos de valores integrados de informe y conjuntos de recursos compartidos &#40;Generador de informes y SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8d750-124">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="8d750-125">Concepto de parámetros de informe &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8d750-125">Report Parameters Concept &#40;Report Builder and SSRS&#41;</span></span>](../report-design/report-parameters-concepts-report-builder-and-ssrs.md)  
  
  
