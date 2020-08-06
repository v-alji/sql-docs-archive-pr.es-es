---
title: 'Tarea 3: limpiar datos con la base de conocimiento proveedores | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 647c924a-9b91-4294-8d96-e81416e4e90e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 13201a8b904a5fc5232b9fa860710e4e39cce67a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747750"
---
# <a name="task-3-cleansing-data-against-the-suppliers-knowledge-base"></a><span data-ttu-id="8127e-102">Tarea 3: Limpieza de datos en la base de conocimiento Proveedores</span><span class="sxs-lookup"><span data-stu-id="8127e-102">Task 3: Cleansing Data against the Suppliers Knowledge Base</span></span>
  <span data-ttu-id="8127e-103">En esta tarea, ejecutará el proceso de limpieza asistida por PC.</span><span class="sxs-lookup"><span data-stu-id="8127e-103">In this task, you run the computer-assisted cleansing process.</span></span> <span data-ttu-id="8127e-104">DQS emplea algoritmos avanzados y niveles de confianza basados en los valores de umbral especificados para analizar los datos comparándolos con la base de conocimiento seleccionada; a continuación, los limpia.</span><span class="sxs-lookup"><span data-stu-id="8127e-104">DQS uses advanced algorithms and confidence levels based on the threshold values specified to analyze the data against the selected knowledge base, and then cleanse it.</span></span> <span data-ttu-id="8127e-105">Vea [Limpiar datos mediante el conocimiento de DQS (interno)](https://msdn.microsoft.com/library/hh213061.aspx) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="8127e-105">See [Cleansing Data Using DQS (Internal) Knowledge](https://msdn.microsoft.com/library/hh213061.aspx) for more details.</span></span>

1.  <span data-ttu-id="8127e-106">Haga clic en **Iniciar** para iniciar el proceso de limpieza asistido por PC.</span><span class="sxs-lookup"><span data-stu-id="8127e-106">Click **Start** to start the computer-assisted cleansing process.</span></span>

     <span data-ttu-id="8127e-107">![Página de limpieza del proceso de limpieza](../../2014/tutorials/media/et-cleansingdataagainstthesupplierkb-01.jpg "Página de limpieza del proceso de limpieza")</span><span class="sxs-lookup"><span data-stu-id="8127e-107">![Cleanse Page of the Cleansing Process](../../2014/tutorials/media/et-cleansingdataagainstthesupplierkb-01.jpg "Cleanse Page of the Cleansing Process")</span></span>

2.  <span data-ttu-id="8127e-108">Una vez completado el proceso de limpieza, revise las **estadísticas** en la pestaña **generador de perfiles** . Las estadísticas de origen proporcionan el número de registros procesados, el número de registros que se detectan como correctos, el número de registros que DQS corrige, el número de registros que tienen cambios sugeridos por DQS y el número de registros que no son válidos.</span><span class="sxs-lookup"><span data-stu-id="8127e-108">When the cleansing process is completed, review **statistics** in the **Profiler** tab. The Source Statistics provide the number of records processed, number of records that are found to be correct, number of records that DQS corrects, number of records that have changes suggested by DQS, and the number of records that are invalid.</span></span> <span data-ttu-id="8127e-109">En el cuadro de lista de la derecha puede ver los valores corregidos, los valores sugeridos y la integridad (la medida en la que los datos están presentes) y la precisión (la medida en que los datos se pueden usar para los fines previstos) de los valores de todos los dominios implicados en el proceso de limpieza.</span><span class="sxs-lookup"><span data-stu-id="8127e-109">In the list box to the right, you can see the corrected values, suggested values, and the completeness (the extent to which the data is present) and accuracy (the extent to which the data can be used for intended purposes) of values for each domain involved in the cleansing process.</span></span>

     <span data-ttu-id="8127e-110">![Resultados de la limpieza](../../2014/tutorials/media/et-cleansingdataagainstthesupplierkb-02.jpg "Resultados de la limpieza")</span><span class="sxs-lookup"><span data-stu-id="8127e-110">![Cleansing Results](../../2014/tutorials/media/et-cleansingdataagainstthesupplierkb-02.jpg "Cleansing Results")</span></span>

3.  <span data-ttu-id="8127e-111">Haga clic en **Siguiente** para cambiar a la página **Administrar y ver resultados** .</span><span class="sxs-lookup"><span data-stu-id="8127e-111">Click **Next** to switch to **Manage and View Results** page.</span></span>

## <a name="next-step"></a><span data-ttu-id="8127e-112">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="8127e-112">Next Step</span></span>
 [<span data-ttu-id="8127e-113">Tarea 4: administrar y ver los resultados</span><span class="sxs-lookup"><span data-stu-id="8127e-113">Task 4: Manaing and Viewing Results</span></span>](../../2014/tutorials/task-4-manaing-and-viewing-results.md)


