---
title: 'Tarea 11: agregar la transformación división condicional para filtrar duplicados | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 3094bd57-5cf4-4860-bf51-fadd1b309f94
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: e8370563c4275df0d0513d5434a8b16efba728d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751585"
---
# <a name="task-11-adding-conditional-split-transform-to-filter-duplicates"></a><span data-ttu-id="235bd-102">Tarea 11: Adición de la transformación División condicional para filtrar duplicados</span><span class="sxs-lookup"><span data-stu-id="235bd-102">Task 11: Adding Conditional Split Transform to Filter Duplicates</span></span>
  <span data-ttu-id="235bd-103">En esta tarea, agregará la transformación División condicional al flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="235bd-103">In this task, you add the Conditional Split Transform to the data flow.</span></span> <span data-ttu-id="235bd-104">Esta transformación ayuda a filtrar duplicados del conjunto de registros de entrada.</span><span class="sxs-lookup"><span data-stu-id="235bd-104">This transform helps you filter duplicates from the incoming record set.</span></span> <span data-ttu-id="235bd-105">La transformación Agrupación aproximada agrupa los registros que son coincidentes y elige uno de ellos como registro dinámico.</span><span class="sxs-lookup"><span data-stu-id="235bd-105">The Fuzzy Group transform groups the records that it finds to be matches and picks one of the records as a pivot record.</span></span> <span data-ttu-id="235bd-106">Todos los registros de un grupo tienen el mismo valor _key_out.</span><span class="sxs-lookup"><span data-stu-id="235bd-106">All the records in a group have the same _key_out value.</span></span> <span data-ttu-id="235bd-107">El registro dinámica del grupo tiene el mismo valor de _key_in que de _key_out.</span><span class="sxs-lookup"><span data-stu-id="235bd-107">The pivot record in the group has _key_in same as the _key_out value.</span></span> <span data-ttu-id="235bd-108">Los demás registros del grupo tienen valores diferentes para _key_in y _key_out.</span><span class="sxs-lookup"><span data-stu-id="235bd-108">The other records in the group have different values for _key_in and _key_out.</span></span> <span data-ttu-id="235bd-109">Por tanto, cuando se filtra mediante la condición _key_in==_key_out, solo se obtiene la fila dinámica del grupo.</span><span class="sxs-lookup"><span data-stu-id="235bd-109">Therefore, when you filter using the condition _key_in==_key_out, you only get the pivot row in the group.</span></span>  
  
1.  <span data-ttu-id="235bd-110">Arrastre y coloque la transformación **división condicional** desde la sección **común** del **cuadro de herramientas de SSIS** hasta la pestaña flujo de **datos** .</span><span class="sxs-lookup"><span data-stu-id="235bd-110">Drag-drop **Conditional Split** Transform from **Common** section in the **SSIS Toolbox** to the **Data Flow** tab.</span></span>  
  
2.  <span data-ttu-id="235bd-111">Haga clic con el botón secundario en **transformación división condicional** en la pestaña **flujo de datos** y haga clic en **cambiar nombre**.</span><span class="sxs-lookup"><span data-stu-id="235bd-111">Right-click **Conditional Split Transform** in the **Data Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="235bd-112">Escriba **filtrar duplicados** y presione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="235bd-112">Type **Filter Duplicates** and press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="235bd-113">Conectar **proveedores de grupos con identificadores coincidentes** para **filtrar duplicados**.</span><span class="sxs-lookup"><span data-stu-id="235bd-113">Connect **Group Suppliers with Matching IDs** to **Filter Duplicates**.</span></span>  
  
4.  <span data-ttu-id="235bd-114">Haga doble clic en **filtrar duplicados** para iniciar el cuadro de diálogo **Editor de transformación división condicional** .</span><span class="sxs-lookup"><span data-stu-id="235bd-114">Double-click **Filter Duplicates** to launch the **Conditional Split Transform Editor** dialog box.</span></span>  
  
5.  <span data-ttu-id="235bd-115">Expanda **columnas** en el panel superior izquierdo.</span><span class="sxs-lookup"><span data-stu-id="235bd-115">Expand **Columns** in the top-left pane.</span></span>  
  
6.  <span data-ttu-id="235bd-116">Arrastre y coloque **_key_in** a la columna **condición** .</span><span class="sxs-lookup"><span data-stu-id="235bd-116">Drag-drop **_key_in** to the **Condition** column.</span></span>  
  
7.  <span data-ttu-id="235bd-117">Type = = (es igual a) junto a **_key_in** y arrastrar y colocar **_key_out**.</span><span class="sxs-lookup"><span data-stu-id="235bd-117">Type == (equals to) next to **_key_in** and drag-drop **_key_out**.</span></span>  
  
8.  <span data-ttu-id="235bd-118">Haga clic en el **caso 1** en la columna **nombre de salida** , escriba **Registros únicos**y presione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="235bd-118">Click **Case 1** in the **Output Name** column, type **Unique Records**, and press **ENTER**.</span></span>  
  
     <span data-ttu-id="235bd-119">![División condicional, editor de transformación](../../2014/tutorials/media/et-addingconditionalsplittransformtofilterduplicates.jpg "División condicional, editor de transformación")</span><span class="sxs-lookup"><span data-stu-id="235bd-119">![Conditional Split Transformation Editor](../../2014/tutorials/media/et-addingconditionalsplittransformtofilterduplicates.jpg "Conditional Split Transformation Editor")</span></span>  
  
9. <span data-ttu-id="235bd-120">Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Editor de transformación división condicional** .</span><span class="sxs-lookup"><span data-stu-id="235bd-120">Click **OK** to close the **Conditional Split Transformation Editor** dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="235bd-121">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="235bd-121">Next Step</span></span>  
 [<span data-ttu-id="235bd-122">Tarea 12: Adición de la transformación Columna derivada para agregar las columnas necesarias en MDS</span><span class="sxs-lookup"><span data-stu-id="235bd-122">Task 12: Adding Derived Column Transform to Add Columns Required by MDS</span></span>](../../2014/tutorials/task-12-adding-derived-column-transform-to-add-columns-required-by-mds.md)  
  
  
