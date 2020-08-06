---
title: 'Tarea 5: establecer relaciones basadas en términos | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 6569d512-637d-4f7b-82e1-1e8582278b37
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 1589ec5843053baa6c42a0b9b0dec019c887da9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747747"
---
# <a name="task-5-setting-term-based-relationships"></a><span data-ttu-id="868fc-102">Tarea 5: Configuración de relaciones basadas en términos</span><span class="sxs-lookup"><span data-stu-id="868fc-102">Task 5: Setting Term Based Relationships</span></span>
  <span data-ttu-id="868fc-103">En esta tarea, se definen algunas relaciones basadas en términos para los valores del dominio **nombre de proveedor** .</span><span class="sxs-lookup"><span data-stu-id="868fc-103">In this task, you define a few term-based relations for values for the **Supplier Name** domain.</span></span> <span data-ttu-id="868fc-104">Una relación basada en términos permite corregir un término que forma parte de un valor en un dominio.</span><span class="sxs-lookup"><span data-stu-id="868fc-104">A term-based relation enables you to make a correction to a term that is part of a value in a domain.</span></span> <span data-ttu-id="868fc-105">Permiten considerar como sinónimos idénticos varios valores que son idénticos salvo por la ortografía de una parte común.</span><span class="sxs-lookup"><span data-stu-id="868fc-105">It enables multiple values that are identical except for the spelling of a common part of them to be considered identical synonyms.</span></span> <span data-ttu-id="868fc-106">Por ejemplo, **Inc.** se puede corregir en **Incorporated**.</span><span class="sxs-lookup"><span data-stu-id="868fc-106">For example, **Inc.** can be corrected to **Incorporated**.</span></span> <span data-ttu-id="868fc-107">DQS emplea estas relaciones en los procesos de detección de conocimiento, limpieza o coincidencia.</span><span class="sxs-lookup"><span data-stu-id="868fc-107">DQS uses these relations in the knowledge discovery, cleansing, or matching processes.</span></span> <span data-ttu-id="868fc-108">Vea [crear relaciones basadas en términos](https://msdn.microsoft.com/library/hh510404.aspx) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="868fc-108">See [Create Term-based Relations](https://msdn.microsoft.com/library/hh510404.aspx) for more details.</span></span>  
  
1.  <span data-ttu-id="868fc-109">Seleccione **nombre de proveedor** en la **lista de dominios**.</span><span class="sxs-lookup"><span data-stu-id="868fc-109">Select **Supplier Name** in the **Domain list**.</span></span>  
  
2.  <span data-ttu-id="868fc-110">Cambie a la pestaña **relaciones basadas en términos** en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="868fc-110">Switch to the **Term-Based Relationships** tab in the right pane.</span></span>  
  
3.  <span data-ttu-id="868fc-111">Haga clic en el botón **Agregar nueva relación** en la barra de herramientas para agregar una relación a la tabla.</span><span class="sxs-lookup"><span data-stu-id="868fc-111">Click **Add new relation** button on the toolbar to add a relation to the table.</span></span>  
  
4.  <span data-ttu-id="868fc-112">Escriba **Co.** en el campo **valor** y **compañía** para el campo **corregir a** .</span><span class="sxs-lookup"><span data-stu-id="868fc-112">Type **Co.** for the **Value** field and **Company** for the **Correct To** field.</span></span>  
  
5.  <span data-ttu-id="868fc-113">Repita los dos pasos anteriores para los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="868fc-113">Repeat the previous two steps for the following values:</span></span>  
  
    |<span data-ttu-id="868fc-114">Value</span><span class="sxs-lookup"><span data-stu-id="868fc-114">Value</span></span>|<span data-ttu-id="868fc-115">Corregir a</span><span class="sxs-lookup"><span data-stu-id="868fc-115">Correct To</span></span>|  
    |-----------|----------------|  
    |<span data-ttu-id="868fc-116">Corp.</span><span class="sxs-lookup"><span data-stu-id="868fc-116">Corp.</span></span>|<span data-ttu-id="868fc-117">Corporation</span><span class="sxs-lookup"><span data-stu-id="868fc-117">Corporation</span></span>|  
    |<span data-ttu-id="868fc-118">Inc.</span><span class="sxs-lookup"><span data-stu-id="868fc-118">Inc.</span></span>|<span data-ttu-id="868fc-119">Incorporated</span><span class="sxs-lookup"><span data-stu-id="868fc-119">Incorporated</span></span>|  
  
     <span data-ttu-id="868fc-120">![Relaciones basadas en términos](../../2014/tutorials/media/et-settingtermbasedrelations.jpg "Relaciones basadas en términos")</span><span class="sxs-lookup"><span data-stu-id="868fc-120">![Term Based Relations](../../2014/tutorials/media/et-settingtermbasedrelations.jpg "Term Based Relations")</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="868fc-121">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="868fc-121">Next Step</span></span>  
 [<span data-ttu-id="868fc-122">Tarea 6: Definición de sinónimos</span><span class="sxs-lookup"><span data-stu-id="868fc-122">Task 6: Setting Synonyms</span></span>](../../2014/tutorials/task-6-setting-synonyms.md)  
  
  
