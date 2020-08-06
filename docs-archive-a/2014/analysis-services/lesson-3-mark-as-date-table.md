---
title: 'Lección 4: marcar como tabla de fechas | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: c32cc336-b7d8-4122-9d62-4936344d2315
author: minewiskan
ms.author: owend
ms.openlocfilehash: c3ccc57d770d954e9523196d2393fa9dc2ada5b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674424"
---
# <a name="lesson-4-mark-as-date-table"></a><span data-ttu-id="460c1-102">Lección 4: Marcar como tabla de fechas</span><span class="sxs-lookup"><span data-stu-id="460c1-102">Lesson 4: Mark as Date Table</span></span>
  <span data-ttu-id="460c1-103">En la lección 2: Agregar datos, importó una tabla de dimensiones denominada DimDate.</span><span class="sxs-lookup"><span data-stu-id="460c1-103">In Lesson 2: Add Data, you imported a dimension table named DimDate.</span></span> <span data-ttu-id="460c1-104">A continuación cambió el nombre de la tabla DimDate, en la lección 3: Cambiar el nombre de las columnas a, simplemente, Date.</span><span class="sxs-lookup"><span data-stu-id="460c1-104">You then renamed the DimDate table, in Lesson 3: Rename Columns, to simply, Date.</span></span> <span data-ttu-id="460c1-105">Aunque en el modelo esta tabla se denomina Date, puede ser también conocida como *tabla Date*, porque contiene datos de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="460c1-105">While in your model this table is now named Date, it can also be known as a *Date table*, in that it contains date and time data.</span></span>  
  
 <span data-ttu-id="460c1-106">Siempre que use funciones de Inteligencia de tiempo en los cálculos, como hará al crear medidas más adelante, debe especificar propiedades de tabla de fechas, que incluyen una *tabla Date* y *una columna Date* de identificador único en esa tabla.</span><span class="sxs-lookup"><span data-stu-id="460c1-106">Whenever you use Time Intelligence functions in calculations, as you will do when you create measures a little later, you must specify date table properties, which include a *Date table* and a unique identifier *Date column* in that table.</span></span> <span data-ttu-id="460c1-107">Puede crear relaciones válidas entre otras tablas y la tabla Date; es necesario para los cálculos con las funciones de inteligencia de tiempo de DAX.</span><span class="sxs-lookup"><span data-stu-id="460c1-107">You can then create valid relationships between other tables and the Date table; necessary for calculations using DAX time intelligence functions.</span></span>  
  
 <span data-ttu-id="460c1-108">En esta lección, se marcará la tabla Date importada y con el nombre cambiado como *tabla Date* y la columna Date (en la tabla Date) como *columna Date* (identificador único).</span><span class="sxs-lookup"><span data-stu-id="460c1-108">In this lesson, you will mark the imported and renamed Date table as the *Date table* and the Date column (in the Date table) as the *Date column* (unique identifier).</span></span> <span data-ttu-id="460c1-109">Todo el uso del nombre Date puede ser confuso, pero pronto obtendrá la idea.</span><span class="sxs-lookup"><span data-stu-id="460c1-109">All the use of the name Date can get kind of confusing, but you'll soon get the idea.</span></span>  
  
 <span data-ttu-id="460c1-110">Tiempo estimado para completar esta lección: **3 minutos**</span><span class="sxs-lookup"><span data-stu-id="460c1-110">Estimated time to complete this lesson: **3 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="460c1-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="460c1-111">Prerequisites</span></span>  
 <span data-ttu-id="460c1-112">Este tema forma parte de un tutorial de modelado tabular, que se debe completar en orden.</span><span class="sxs-lookup"><span data-stu-id="460c1-112">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="460c1-113">Antes de realizar las tareas de esta lección, debe haber completado la lección anterior: [Lección 3: Cambiar el nombre de las columnas](rename-columns.md).</span><span class="sxs-lookup"><span data-stu-id="460c1-113">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 3: Rename Columns](rename-columns.md).</span></span>  
  
### <a name="to-set-mark-as-date-table"></a><span data-ttu-id="460c1-114">Para establecer Marcar como tabla de fechas, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="460c1-114">To set Mark as Date Table</span></span>  
  
1.  <span data-ttu-id="460c1-115">En el diseñador de modelos, haga clic en la tabla **Date** (pestaña).</span><span class="sxs-lookup"><span data-stu-id="460c1-115">In the model designer, click the **Date** table (tab).</span></span>  
  
2.  <span data-ttu-id="460c1-116">Haga clic en el menú **tabla** , haga clic en **fecha**y, a continuación, haga clic en **marcar como tabla de fechas**.</span><span class="sxs-lookup"><span data-stu-id="460c1-116">Click the **Table** menu, then click **Date**, and then click **Mark as Date Table**.</span></span>  
  
3.  <span data-ttu-id="460c1-117">En el cuadro de diálogo **Marcar como tabla de fechas** en el cuadro de lista **Date** , seleccione la columna **Date** como identificador único.</span><span class="sxs-lookup"><span data-stu-id="460c1-117">In the **Mark as Date Table** dialog box, in the **Date** listbox, select the **Date** column as the unique identifier.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="460c1-118">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="460c1-118">Next Steps</span></span>  
 <span data-ttu-id="460c1-119">Para continuar este tutorial, vaya a la lección siguiente: [Lección 5: Crear relaciones](lesson-4-create-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="460c1-119">To continue this tutorial, go to the next lesson: [Lesson 5: Create Relationships](lesson-4-create-relationships.md).</span></span>  
  
  
