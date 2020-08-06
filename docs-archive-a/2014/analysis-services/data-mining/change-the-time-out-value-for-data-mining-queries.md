---
title: Cambiar el valor de tiempo de espera para las consultas de minería de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- time-out
ms.assetid: f1add4bc-e882-440a-a98b-333cfa274c3e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9dcdcdcbb6e2aef48dd8725f10f38180c73f5f6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674456"
---
# <a name="change-the-time-out-value-for-data-mining-queries"></a><span data-ttu-id="f8ecd-102">Cambiar el valor del tiempo de espera para las consultas de minería de datos</span><span class="sxs-lookup"><span data-stu-id="f8ecd-102">Change the Time-out Value for Data Mining Queries</span></span>
  <span data-ttu-id="f8ecd-103">Al generar un gráfico de elevación o ejecutar una consulta de predicción, en ocasiones se necesita mucho tiempo para generar todos los datos requeridos para la predicción.</span><span class="sxs-lookup"><span data-stu-id="f8ecd-103">When you build a lift chart or execute a prediction query, sometimes it can take a long time to generate all the data required for the prediction.</span></span> <span data-ttu-id="f8ecd-104">Para evitar que se exceda el tiempo de espera de la consulta, puede cambiar el valor que controla cuánto tiempo debe esperar el servidor [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para completar una consulta.</span><span class="sxs-lookup"><span data-stu-id="f8ecd-104">To prevent the query from timing out, you can change the value that controls how long the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] server waits to complete a query.</span></span>  
  
 <span data-ttu-id="f8ecd-105">El valor predeterminado es 15; sin embargo, si sus modelos son complejos o el origen de datos es grande, puede no ser suficiente.</span><span class="sxs-lookup"><span data-stu-id="f8ecd-105">The default value is 15; however, if your models are complex or the data source is large, this might not be enough.</span></span> <span data-ttu-id="f8ecd-106">Si es necesario, puede aumentar significativamente el valor para dejar tiempo suficiente para los procesos.</span><span class="sxs-lookup"><span data-stu-id="f8ecd-106">If necessary, you can increase the value significantly, to enable enough time for processing.</span></span> <span data-ttu-id="f8ecd-107">Por ejemplo, si establece **Tiempo de espera de la consulta** en 600, la consulta podría seguir ejecutándose hasta un tiempo máximo de 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="f8ecd-107">For example, if you set **Query Timeout** to 600, the query could continue to run for up to 10 minutes.</span></span>  
  
 <span data-ttu-id="f8ecd-108">Para más información sobre las consultas de predicción, vea [Tareas y procedimientos de Consulta de minería de datos](data-mining-query-tasks-and-how-tos.md).</span><span class="sxs-lookup"><span data-stu-id="f8ecd-108">For more information about prediction queries, see [Data Mining Query Tasks and How-tos](data-mining-query-tasks-and-how-tos.md).</span></span>  
  
### <a name="configure-the-time-out-value-for-data-mining-queries"></a><span data-ttu-id="f8ecd-109">Configurar el valor del tiempo de espera para las consultas de minería de datos</span><span class="sxs-lookup"><span data-stu-id="f8ecd-109">Configure the time-out value for data mining queries</span></span>  
  
1.  <span data-ttu-id="f8ecd-110">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], en el menú **Herramientas** , seleccione **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="f8ecd-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], from the **Tools** menu, selection **Options**.</span></span>  
  
2.  <span data-ttu-id="f8ecd-111">En el panel **Opciones** , expanda **Diseñadores de Business Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="f8ecd-111">In the **Options** pane, expand **Business Intelligence Designers**.</span></span>  
  
3.  <span data-ttu-id="f8ecd-112">Haga clic en el cuadro de texto **Tiempo de espera de la consulta** y escriba un valor para el número de segundos.</span><span class="sxs-lookup"><span data-stu-id="f8ecd-112">Click the **Query Timeout** text box, and type a value for the number of seconds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8ecd-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f8ecd-113">See Also</span></span>  
 <span data-ttu-id="f8ecd-114">[Tareas y procedimientos de consulta de minería de datos](data-mining-query-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="f8ecd-114">[Data Mining Query Tasks and How-tos](data-mining-query-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="f8ecd-115">Consultas de minería de datos</span><span class="sxs-lookup"><span data-stu-id="f8ecd-115">Data Mining Queries</span></span>](data-mining-queries.md)  
  
  
