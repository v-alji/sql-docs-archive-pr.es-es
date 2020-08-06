---
title: Especificar marcar como tabla de fechas para su uso con inteligencia de tiempo (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 30841d1f-0c3b-4575-8f4a-27a1492e248c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 81038369b8cb8636a2aa216f1c26783a96d5f7ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743638"
---
# <a name="specify-mark-as-date-table-for-use-with-time-intelligence-ssas-tabular"></a><span data-ttu-id="fdb29-102">Especificar Marcar como tabla de fechas con inteligencia de tiempo (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="fdb29-102">Specify Mark as Date Table for use with Time Intelligence (SSAS Tabular)</span></span>
  <span data-ttu-id="fdb29-103">Para usar las funciones de inteligencia de tiempo en fórmulas DAX, debe especificar una tabla de fechas y una columna de identificador único (datetime) del tipo de datos Date.</span><span class="sxs-lookup"><span data-stu-id="fdb29-103">In order to use time intelligence functions in DAX formulas, you must specify a date table and a unique identifier (datetime) column of the Date data type.</span></span> <span data-ttu-id="fdb29-104">Una vez especificada una columna en la tabla de fechas como identificador único, puede crear relaciones entre las columnas de la tabla de fechas y cualquier tabla de hechos.</span><span class="sxs-lookup"><span data-stu-id="fdb29-104">Once a column in the date table is specified as a unique identifier, you can create relationships between columns in the date table and any fact tables.</span></span>  
  
 <span data-ttu-id="fdb29-105">Cuando se usan las funciones de inteligencia de tiempo, se aplican las siguientes reglas:</span><span class="sxs-lookup"><span data-stu-id="fdb29-105">When using time intelligence functions, the following rules apply:</span></span>  
  
-   <span data-ttu-id="fdb29-106">Cuando use funciones de inteligencia de tiempo DAX, no especifique nunca una columna datetime desde una tabla de hechos.</span><span class="sxs-lookup"><span data-stu-id="fdb29-106">When using DAX time intelligence functions, never specify a datetime column from a fact table.</span></span> <span data-ttu-id="fdb29-107">Cree siempre una tabla de fechas independiente en el modelo con al menos una columna datetime del tipo de datos Date y con valores únicos.</span><span class="sxs-lookup"><span data-stu-id="fdb29-107">Always create a separate date table in your model with at least one datetime column of Date data type and with unique values.</span></span>  
  
-   <span data-ttu-id="fdb29-108">Asegúrese de que la tabla de fechas tiene un intervalo de fechas continuo.</span><span class="sxs-lookup"><span data-stu-id="fdb29-108">Make sure your date table has a continuous date range.</span></span>  
  
-   <span data-ttu-id="fdb29-109">La columna datetime de la tabla de fechas debe estar desglosada por día (sin fracciones de día).</span><span class="sxs-lookup"><span data-stu-id="fdb29-109">The datetime column in the date table should be at day granularity (without fractions of a day).</span></span>  
  
-   <span data-ttu-id="fdb29-110">Debe especificar una tabla de fechas y una columna de identificador único mediante el cuadro de diálogo **Marcar como tabla de fechas** .</span><span class="sxs-lookup"><span data-stu-id="fdb29-110">You must specify a date table and a unique identifier column by using the **Mark the Date Table** dialog box.</span></span>  
  
-   <span data-ttu-id="fdb29-111">Cree relaciones entre las tablas de hechos y las columnas de tipo de datos Date en la tabla de fechas.</span><span class="sxs-lookup"><span data-stu-id="fdb29-111">Create relationships between fact tables and columns of Date data type in the date table.</span></span>  
  
#### <a name="to-specify-a-date-table-and-unique-identifier"></a><span data-ttu-id="fdb29-112">Para especificar una tabla de fechas y un identificador único</span><span class="sxs-lookup"><span data-stu-id="fdb29-112">To specify a date table and unique identifier</span></span>  
  
1.  <span data-ttu-id="fdb29-113">En el diseñador de modelos, haga clic en la tabla de fechas.</span><span class="sxs-lookup"><span data-stu-id="fdb29-113">In the model designer, click the date table.</span></span>  
  
2.  <span data-ttu-id="fdb29-114">Haga clic en el menú **Tabla** , haga clic en **Fecha**y después haga clic en **Marcar como tabla de fechas**</span><span class="sxs-lookup"><span data-stu-id="fdb29-114">Click the **Table** menu, then click **Date**, and then click **Mark as Date Table**</span></span>  
  
3.  <span data-ttu-id="fdb29-115">En el cuadro de diálogo **Marcar como tabla de fechas** , en el cuadro de lista **Fecha** , seleccione la columna que se utilizará como identificador único.</span><span class="sxs-lookup"><span data-stu-id="fdb29-115">In the **Mark as Date Table** dialog box, in the **Date** listbox, select a column to be used as a unique identifier.</span></span> <span data-ttu-id="fdb29-116">Esta columna debe contener valores únicos y debe ser de tipo de datos Date.</span><span class="sxs-lookup"><span data-stu-id="fdb29-116">This column must contain unique values and should be of Date data type.</span></span> <span data-ttu-id="fdb29-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fdb29-117">For example:</span></span>  
  
    |<span data-ttu-id="fdb29-118">Date</span><span class="sxs-lookup"><span data-stu-id="fdb29-118">Date</span></span>|  
    |----------|  
    |<span data-ttu-id="fdb29-119">1/7/2010 12:00:00 a.m.</span><span class="sxs-lookup"><span data-stu-id="fdb29-119">7/1/2010 12:00:00 AM</span></span>|  
    |<span data-ttu-id="fdb29-120">2/7/2010 12:00:00 a.m.</span><span class="sxs-lookup"><span data-stu-id="fdb29-120">7/2/2010 12:00:00 AM</span></span>|  
    |<span data-ttu-id="fdb29-121">3/7/2010 12:00:00 a.m.</span><span class="sxs-lookup"><span data-stu-id="fdb29-121">7/3/2010 12:00:00 AM</span></span>|  
    |<span data-ttu-id="fdb29-122">4/7/2010 12:00:00 a.m.</span><span class="sxs-lookup"><span data-stu-id="fdb29-122">7/4/2010 12:00:00 AM</span></span>|  
    |<span data-ttu-id="fdb29-123">5/7/2010 12:00:00 a.m.</span><span class="sxs-lookup"><span data-stu-id="fdb29-123">7/5/2010 12:00:00 AM</span></span>|  
  
4.  <span data-ttu-id="fdb29-124">Si fuera necesario, cree las relaciones entre las tablas de hechos y la tabla de fechas.</span><span class="sxs-lookup"><span data-stu-id="fdb29-124">If necessary, create any relationships between fact tables and the date table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdb29-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fdb29-125">See Also</span></span>  
 <span data-ttu-id="fdb29-126">[Cálculos &#40;&#41;tabular de SSAS](calculations-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="fdb29-126">[Calculations &#40;SSAS Tabular&#41;](calculations-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="fdb29-127">Funciones de inteligencia de tiempo &#40;DAX&#41;</span><span class="sxs-lookup"><span data-stu-id="fdb29-127">Time Intelligence Functions &#40;DAX&#41;</span></span>](/dax/time-intelligence-functions-dax)  
  
  
