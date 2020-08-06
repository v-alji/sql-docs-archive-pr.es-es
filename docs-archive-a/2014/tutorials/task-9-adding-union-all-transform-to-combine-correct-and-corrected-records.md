---
title: 'Tarea 9: agregar una transformación Unión de todo para combinar los registros correctos y corregidos | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 24ba466d-a7d3-49e7-9111-b348399c9e58
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 83afb5ea9367660048fe36d00ab59d808da17b81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751581"
---
# <a name="task-9-adding-union-all-transform-to-combine-correct-and-corrected-records"></a><span data-ttu-id="f0a30-102">Tarea 9: Adición de la transformación Unión de todo para combinar los registros correctos y corregidos</span><span class="sxs-lookup"><span data-stu-id="f0a30-102">Task 9: Adding Union All Transform to Combine Correct and Corrected Records</span></span>
  <span data-ttu-id="f0a30-103">En esta tarea, agregará la transformación Unión de todo al flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="f0a30-103">In this task, you add the Union All Transform to the data flow.</span></span> <span data-ttu-id="f0a30-104">La transformación Unión de todo combina varias entradas en una salida.</span><span class="sxs-lookup"><span data-stu-id="f0a30-104">The Union All transformation combines multiple inputs into one output.</span></span> <span data-ttu-id="f0a30-105">En su escenario, combina los registros Correctos y Corregidos en un flujo.</span><span class="sxs-lookup"><span data-stu-id="f0a30-105">In your scenario, it combine both Correct and Corrected records into one stream.</span></span>  
  
1.  <span data-ttu-id="f0a30-106">Arrastre y coloque **UNION ALL** Transform desde la sección **común** del **cuadro de herramientas de SSIS** hasta la pestaña **flujo de datos** y colóquela en **seleccionar registros correctos y corregidos**.</span><span class="sxs-lookup"><span data-stu-id="f0a30-106">Drag-drop **Union All** Transform from **Common** section of the **SSIS Toolbox** to the **Data Flow** tab and place it under **Pick Correct and Corrected Records**.</span></span>  
  
2.  <span data-ttu-id="f0a30-107">Haga clic con el botón secundario en transformación **Unión de todo** en la pestaña **flujo de datos** y haga clic en **cambiar nombre**.</span><span class="sxs-lookup"><span data-stu-id="f0a30-107">Right-click **Union All** Transform in the **Data Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="f0a30-108">Escriba **combinar registros correctos y corregidos**y presione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="f0a30-108">Type **Combine Correct and Corrected Records**, and press **ENTER**.</span></span>  
  
     <span data-ttu-id="f0a30-109">![Combinar registros correctos y corregidos](../../2014/tutorials/media/et-addinguattocombinecacrecords-01.jpg "Combinar registros correctos y corregidos")</span><span class="sxs-lookup"><span data-stu-id="f0a30-109">![Combine Correct and Corrected Reocrds](../../2014/tutorials/media/et-addinguattocombinecacrecords-01.jpg "Combine Correct and Corrected Reocrds")</span></span>  
  
3.  <span data-ttu-id="f0a30-110">Conecte **Seleccione los registros correctos y corregidos** para **combinar los registros correctos y corregidos** en la pestaña **flujo de datos** mediante el conector azul.</span><span class="sxs-lookup"><span data-stu-id="f0a30-110">Connect **Pick Correct and Corrected Records** to **Combine Correct and Corrected Records** in the **Data Flow** tab by using the blue connector.</span></span> <span data-ttu-id="f0a30-111">Debería ver el cuadro de diálogo **selección de entrada y salida** .</span><span class="sxs-lookup"><span data-stu-id="f0a30-111">You should see the **Input Output Selection** dialog box.</span></span>  
  
4.  <span data-ttu-id="f0a30-112">En el cuadro de diálogo **salida de entrada** , seleccione **correcto** en **salida** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f0a30-112">In the **Input Output** dialog box, select **Correct** for **Output** and click **OK**.</span></span>  
  
     <span data-ttu-id="f0a30-113">![Cuadro de diálogo Selección de entrada y salida](../../2014/tutorials/media/et-addinguattocombinecacrecords-02.jpg "Cuadro de diálogo Selección de entrada y salida")</span><span class="sxs-lookup"><span data-stu-id="f0a30-113">![Input Output Selection Dialog Box](../../2014/tutorials/media/et-addinguattocombinecacrecords-02.jpg "Input Output Selection Dialog Box")</span></span>  
  
5.  <span data-ttu-id="f0a30-114">Mueva el conector con el título **correcto** a la izquierda arrastrando y soltando el punto al final del conector a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="f0a30-114">Move the connector titled **Correct** to the left by dragging and dropping the dot at the end of the connector to left.</span></span>  
  
     <span data-ttu-id="f0a30-115">![Conexión - Corrección para Combinar correctos y corregidos](../../2014/tutorials/media/et-addinguattocombinecacrecords-03.jpg "Conexión - Corrección para Combinar correctos y corregidos")</span><span class="sxs-lookup"><span data-stu-id="f0a30-115">![Connect Correct to Combine Correct and Corrected](../../2014/tutorials/media/et-addinguattocombinecacrecords-03.jpg "Connect Correct to Combine Correct and Corrected")</span></span>  
  
6.  <span data-ttu-id="f0a30-116">Si selecciona la transformación seleccionar **los registros correctos y corregidos** , debería ver otro conector azul.</span><span class="sxs-lookup"><span data-stu-id="f0a30-116">If you select **Pick Correct and Corrected Records** transform, you should see another blue connector.</span></span> <span data-ttu-id="f0a30-117">Arrastre ese conector azul para **combinar los registros correctos y corregidos**.</span><span class="sxs-lookup"><span data-stu-id="f0a30-117">Drag that blue connector to **Combine Correct and Corrected Records**.</span></span>  
  
     <span data-ttu-id="f0a30-118">![Conexión - Corregidos para Combinar correctos y corregidos](../../2014/tutorials/media/et-addinguattocombinecacrecords-04.jpg "Conexión - Corregidos para Combinar correctos y corregidos")</span><span class="sxs-lookup"><span data-stu-id="f0a30-118">![Connect Corrected to Combine Correct and Corrected](../../2014/tutorials/media/et-addinguattocombinecacrecords-04.jpg "Connect Corrected to Combine Correct and Corrected")</span></span>  
  
7.  <span data-ttu-id="f0a30-119">El título de este **conector** debe ser **corregido**.</span><span class="sxs-lookup"><span data-stu-id="f0a30-119">This **connector** should be titled **Corrected**.</span></span> <span data-ttu-id="f0a30-120">Puesto que solo tiene dos condiciones de **corrección** y **corrección, y**una condición ya se ha usado, el cuadro de diálogo Selección de **salida de entrada** no se muestra en este momento.</span><span class="sxs-lookup"><span data-stu-id="f0a30-120">Since you have only two conditions **Correct** and **Corrected**, and one condition was already used, the **Input Output Selection** dialog box is not displayed this time.</span></span> <span data-ttu-id="f0a30-121">Si los conectores se superponen, mueva uno hacia la izquierda y el otro hacia la derecha arrastrando el conector hacia la izquierda o hacia la derecha.</span><span class="sxs-lookup"><span data-stu-id="f0a30-121">If the connectors overlap, move one to left and the other one to right by dragging the connector to left or right.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="f0a30-122">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="f0a30-122">Next Step</span></span>  
 [<span data-ttu-id="f0a30-123">Tarea 10: Adición de la transformación Agrupación aproximada para identificar duplicados</span><span class="sxs-lookup"><span data-stu-id="f0a30-123">Task 10: Adding Fuzzy Group Transform to Identify Duplicates</span></span>](../../2014/tutorials/task-10-adding-fuzzy-group-transform-to-identify-duplicates.md)  
  
  
