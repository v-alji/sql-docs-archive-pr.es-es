---
title: 'Tarea 8: agregar la transformación división condicional para dividir la salida de limpieza | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: d4ebe420-a4a9-4076-89d3-41abe726fc5c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 9be7ea6f5330382ad0417df99e18bcba5b59a4e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662396"
---
# <a name="task-8-adding-conditional-split-transform-to-split-cleansing-output"></a><span data-ttu-id="95d2c-102">Tarea 8: Adición de la transformación División condicional para dividir el resultado de la limpieza</span><span class="sxs-lookup"><span data-stu-id="95d2c-102">Task 8: Adding Conditional Split Transform to Split Cleansing Output</span></span>
  <span data-ttu-id="95d2c-103">En esta tarea, agregará una transformación División condicional al flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="95d2c-103">In this transform, you add a Conditional Split Transform to the data flow.</span></span> <span data-ttu-id="95d2c-104">La transformación División condicional puede dirigir filas a salidas diferentes en función del contenido de los datos.</span><span class="sxs-lookup"><span data-stu-id="95d2c-104">The Conditional Split transformation can route rows to different outputs based on the content of the data.</span></span> <span data-ttu-id="95d2c-105">En este tutorial, usará la columna salida del **Estado de registro** de la transformación limpieza de DQS.</span><span class="sxs-lookup"><span data-stu-id="95d2c-105">For this tutorial, you use the **Record Status** output column from the DQS Cleansing transform.</span></span> <span data-ttu-id="95d2c-106">En este tutorial solo cargará los registros correctos o corregidos en el servidor MDS.</span><span class="sxs-lookup"><span data-stu-id="95d2c-106">You will upload only correct or corrected records to MDS server in this tutorial.</span></span> <span data-ttu-id="95d2c-107">Por lo tanto, se comprueba si el **Estado del registro** es **correcto** o **corregido**, y se combinan los registros antes de cargar los registros en MDS.</span><span class="sxs-lookup"><span data-stu-id="95d2c-107">Therefore you check if the **Record Status** is **Correct** or **Corrected**, and combine the records before uploading the records to MDS.</span></span>  
  
1.  <span data-ttu-id="95d2c-108">Arrastre y coloque la **transformación división condicional** desde la sección **común** del **cuadro de herramientas de SSIS** hasta la pestaña flujo de **datos** en **limpiar datos del proveedor**.</span><span class="sxs-lookup"><span data-stu-id="95d2c-108">Drag-drop **Conditional Split Transform** from **Common** section in the **SSIS Toolbox** to the **Data Flow** tab under **Cleanse Supplier Data**.</span></span>  
  
2.  <span data-ttu-id="95d2c-109">Haga clic con el botón secundario en **división condicional**y haga clic en **cambiar nombre**.</span><span class="sxs-lookup"><span data-stu-id="95d2c-109">Right-click **Conditional Split**, and click **Rename**.</span></span> <span data-ttu-id="95d2c-110">Escriba **elegir registros correctos y corregidos** y presione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="95d2c-110">Type **Pick Correct and Corrected Records** and press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="95d2c-111">Conecte **limpiar datos de proveedor** y **Seleccione los registros correctos y corregidos** con el conector azul.</span><span class="sxs-lookup"><span data-stu-id="95d2c-111">Connect **Cleanse Supplier Data** and **Pick Correct and Corrected Records** using the blue connector.</span></span>  
  
     <span data-ttu-id="95d2c-112">![Limpiar datos de proveedor: > seleccionar correcto & corregido](../../2014/tutorials/media/et-addingcsttosplitcleansingoutput-01.jpg "Limpiar datos de proveedor -> Corrección de selección & Corregida")</span><span class="sxs-lookup"><span data-stu-id="95d2c-112">![Cleanse Supplier Data -> Pick Correct & Corrected](../../2014/tutorials/media/et-addingcsttosplitcleansingoutput-01.jpg "Cleanse Supplier Data -> Pick Correct & Corrected")</span></span>  
  
4.  <span data-ttu-id="95d2c-113">Haga doble clic en **seleccionar registros correctos y corregidos** en la pestaña **flujo de datos** .</span><span class="sxs-lookup"><span data-stu-id="95d2c-113">Double-click **Pick Correct and Corrected Records** in the **Data Flow** tab.</span></span>  
  
5.  <span data-ttu-id="95d2c-114">Cambie el **nombre de salida predeterminado** en la parte inferior de la pantalla para **corregirlo**.</span><span class="sxs-lookup"><span data-stu-id="95d2c-114">Change the **Default Output Name** at the bottom of the screen to **Correct**.</span></span>  
  
6.  <span data-ttu-id="95d2c-115">Expanda **columnas** en el **panel superior izquierdo**.</span><span class="sxs-lookup"><span data-stu-id="95d2c-115">Expand **Columns** in the **top-left pane**.</span></span>  
  
     <span data-ttu-id="95d2c-116">![División condicional, editor de transformación](../../2014/tutorials/media/et-addingcsttosplitcleansingoutput-02.jpg "División condicional, editor de transformación")</span><span class="sxs-lookup"><span data-stu-id="95d2c-116">![Conditional Split Transformation Editor](../../2014/tutorials/media/et-addingcsttosplitcleansingoutput-02.jpg "Conditional Split Transformation Editor")</span></span>  
  
7.  <span data-ttu-id="95d2c-117">Arrastre y coloque el **Estado del registro** en la columna **condición** .</span><span class="sxs-lookup"><span data-stu-id="95d2c-117">Drag-drop **Record Status** to the **Condition** column.</span></span>  
  
8.  <span data-ttu-id="95d2c-118">Escriba **= = "corregido"** junto a **[estado del registro]** para la columna **condición** .</span><span class="sxs-lookup"><span data-stu-id="95d2c-118">Type **=="Corrected"** next to **[Record Status]** for the **Condition** column.</span></span>  
  
9. <span data-ttu-id="95d2c-119">Haga clic en el **caso 1** en la **columna Nombre de salida**y cambie el nombre a **corregido**.</span><span class="sxs-lookup"><span data-stu-id="95d2c-119">Click **Case 1** in the **Output Name Column**, and change the name to **Corrected**.</span></span>  
  
10. <span data-ttu-id="95d2c-120">Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Editor de transformación división condicional** .</span><span class="sxs-lookup"><span data-stu-id="95d2c-120">Click **OK** to close the **Conditional Split Transformation Editor** dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="95d2c-121">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="95d2c-121">Next Step</span></span>  
 [<span data-ttu-id="95d2c-122">Tarea 9: Adición de la transformación Unión de todo para combinar los registros correctos y corregidos</span><span class="sxs-lookup"><span data-stu-id="95d2c-122">Task 9: Adding Union All Transform to Combine Correct and Corrected Records</span></span>](../../2014/tutorials/task-9-adding-union-all-transform-to-combine-correct-and-corrected-records.md)  
  
  
