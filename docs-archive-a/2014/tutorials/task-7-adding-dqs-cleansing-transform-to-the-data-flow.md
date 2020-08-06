---
title: 'Tarea 7: agregar la transformación limpieza de DQS al flujo de datos | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 0b749c71-dfb6-493a-804f-600290d46eef
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 887bc361a51b61e9137404e054bd52e2b630ca5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663843"
---
# <a name="task-7-adding-dqs-cleansing-transform-to-the-data-flow"></a><span data-ttu-id="03065-102">Tarea 7: Adición de la transformación Limpieza de DQS al flujo de datos</span><span class="sxs-lookup"><span data-stu-id="03065-102">Task 7: Adding DQS Cleansing Transform to the Data Flow</span></span>
  <span data-ttu-id="03065-103">En esta tarea, agregará la transformación Limpieza de DQS al flujo de datos para limpiar los datos de proveedor de entrada mediante DQS.</span><span class="sxs-lookup"><span data-stu-id="03065-103">In this task, you add DQS Cleansing Transform to the data flow to cleanse the input supplier data by using DQS.</span></span> <span data-ttu-id="03065-104">Vea **[transformación limpieza de DQS](https://msdn.microsoft.com/library/ee677619.aspx)** para obtener más detalles sobre la transformación.</span><span class="sxs-lookup"><span data-stu-id="03065-104">See **[DQS Cleansing Transform](https://msdn.microsoft.com/library/ee677619.aspx)** for more details about the transform.</span></span>  
  
1.  <span data-ttu-id="03065-105">Haga clic con el botón secundario en **limpieza de DQS** en la pestaña **flujo de datos** y haga clic en **cambiar nombre**.</span><span class="sxs-lookup"><span data-stu-id="03065-105">Right-click **DQS Cleansing** in the **Data Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="03065-106">Escriba **limpiar datos de proveedor**y presione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="03065-106">Type **Cleanse Supplier Data**, and press **ENTER**.</span></span>  
  
2.  <span data-ttu-id="03065-107">Seleccione **leer datos de proveedor del archivo de Excel**; Arrastre el conector azul para **limpiar los datos de proveedor**.</span><span class="sxs-lookup"><span data-stu-id="03065-107">Select **Read Supplier Data from Excel File**; drag the blue connector to **Cleanse Supplier Data**.</span></span> <span data-ttu-id="03065-108">Los componentes ahora están conectados.</span><span class="sxs-lookup"><span data-stu-id="03065-108">The components are now connected.</span></span>  
  
     <span data-ttu-id="03065-109">![Leer datos de proveedor: > limpiar los datos de proveedor](../../2014/tutorials/media/et-addingdqscleansingtransformtothedataflow-01.jpg "Leer datos de proveedor -> Limpiar datos de proveedor")</span><span class="sxs-lookup"><span data-stu-id="03065-109">![Read Supplier Data -> Cleanse Supplier Data](../../2014/tutorials/media/et-addingdqscleansingtransformtothedataflow-01.jpg "Read Supplier Data -> Cleanse Supplier Data")</span></span>  
  
3.  <span data-ttu-id="03065-110">Haga doble clic en **limpiar datos de proveedor**.</span><span class="sxs-lookup"><span data-stu-id="03065-110">Double-click **Cleanse Supplier Data**.</span></span>  
  
4.  <span data-ttu-id="03065-111">En el **Editor de transformación limpieza de DQS**, haga clic en **nuevo** junto a la lista desplegable **Administrador de conexiones de calidad de datos**.</span><span class="sxs-lookup"><span data-stu-id="03065-111">In the **DQS Cleansing Transformation Editor**, click **New** next to the **Data Quality Connection Manager drop-down list**.</span></span>  
  
5.  <span data-ttu-id="03065-112">En el cuadro de diálogo **Administrador de conexiones de limpieza de DQS** , escriba **(local)** o **punto** (.) para conectarse al servidor local.</span><span class="sxs-lookup"><span data-stu-id="03065-112">In the **DQS Cleansing Connection Manager** dialog box, type **(local)** or **period** (.) to connect to the local server.</span></span> <span data-ttu-id="03065-113">En esta lección se da por supuesto que ha instalado DQS en un servidor local.</span><span class="sxs-lookup"><span data-stu-id="03065-113">This lesson assumes that you have DQS installed on a local server.</span></span>  
  
6.  <span data-ttu-id="03065-114">Haga clic en **probar conexión** para probar la conexión con el servidor DQS.</span><span class="sxs-lookup"><span data-stu-id="03065-114">Click **Test Connection** to test the connection to DQS server.</span></span>  
  
7.  <span data-ttu-id="03065-115">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="03065-115">Click **OK** to close the dialog box.</span></span>  
  
8.  <span data-ttu-id="03065-116">Seleccione **proveedores** en la **base de conocimiento de calidad de datos**.</span><span class="sxs-lookup"><span data-stu-id="03065-116">Select **Suppliers** for the **Data Quality Knowledge Base**.</span></span>  
  
     <span data-ttu-id="03065-117">![Editor de transformación Limpieza de DQS - Knowledge Base de los proveedores](../../2014/tutorials/media/et-addingdqscleansingtransformtothedataflow-02.jpg "Editor de transformación Limpieza de DQS - Knowledge Base de los proveedores")</span><span class="sxs-lookup"><span data-stu-id="03065-117">![DQS Cleansing Transformation Editor - Suppliers KB](../../2014/tutorials/media/et-addingdqscleansingtransformtothedataflow-02.jpg "DQS Cleansing Transformation Editor - Suppliers KB")</span></span>  
  
9. <span data-ttu-id="03065-118">Cambie a la pestaña **asignación** en la parte superior.</span><span class="sxs-lookup"><span data-stu-id="03065-118">Switch to the **Mapping** tab at the top.</span></span>  
  
10. <span data-ttu-id="03065-119">En **columnas de entrada disponibles**, **Seleccione Nombre del proveedor**, **ContactEmailAddress**, línea de **Dirección**, **ciudad**, **Estado**, **país**y **código postal** . para ello, active las casillas de verificación.</span><span class="sxs-lookup"><span data-stu-id="03065-119">From **Available Input Columns**, select **Supplier Name**, **ContactEmailAddress**, **Address Line**, **City**, **State**, **Country**, and **Zip Code** by selecting the check boxes.</span></span>  
  
     <span data-ttu-id="03065-120">![Editor de transformación Limpieza de DQS - Asignaciones](../../2014/tutorials/media/et-addingdqscleansingtransformtothedataflow-03.jpg "Editor de transformación Limpieza de DQS - Asignaciones")</span><span class="sxs-lookup"><span data-stu-id="03065-120">![DQS Cleansing Transformation Editor - Mappings](../../2014/tutorials/media/et-addingdqscleansingtransformtothedataflow-03.jpg "DQS Cleansing Transformation Editor - Mappings")</span></span>  
  
11. <span data-ttu-id="03065-121">En el panel inferior, asigne estas columnas mediante listas desplegables de la columna **dominio** :</span><span class="sxs-lookup"><span data-stu-id="03065-121">In the bottom pane, map these columns by using drop-down lists in the **Domain** column:</span></span>  
  
    |<span data-ttu-id="03065-122">Columna</span><span class="sxs-lookup"><span data-stu-id="03065-122">Column</span></span>|<span data-ttu-id="03065-123">Dominio</span><span class="sxs-lookup"><span data-stu-id="03065-123">Domain</span></span>|  
    |------------|------------|  
    |<span data-ttu-id="03065-124">Nombre del proveedor</span><span class="sxs-lookup"><span data-stu-id="03065-124">Supplier Name</span></span>|<span data-ttu-id="03065-125">Nombre del proveedor</span><span class="sxs-lookup"><span data-stu-id="03065-125">Supplier Name</span></span>|  
    |<span data-ttu-id="03065-126">ContactEmailAddress</span><span class="sxs-lookup"><span data-stu-id="03065-126">ContactEmailAddress</span></span>|<span data-ttu-id="03065-127">Dirección de correo electrónico de contacto</span><span class="sxs-lookup"><span data-stu-id="03065-127">Contact Email</span></span>|  
    |<span data-ttu-id="03065-128">Address Line</span><span class="sxs-lookup"><span data-stu-id="03065-128">Address Line</span></span>|<span data-ttu-id="03065-129">Address Line</span><span class="sxs-lookup"><span data-stu-id="03065-129">Address Line</span></span>|  
    |<span data-ttu-id="03065-130">City</span><span class="sxs-lookup"><span data-stu-id="03065-130">City</span></span>|<span data-ttu-id="03065-131">City</span><span class="sxs-lookup"><span data-stu-id="03065-131">City</span></span>|  
    |<span data-ttu-id="03065-132">State</span><span class="sxs-lookup"><span data-stu-id="03065-132">State</span></span>|<span data-ttu-id="03065-133">State</span><span class="sxs-lookup"><span data-stu-id="03065-133">State</span></span>|  
    |<span data-ttu-id="03065-134">Country</span><span class="sxs-lookup"><span data-stu-id="03065-134">Country</span></span>|<span data-ttu-id="03065-135">Country</span><span class="sxs-lookup"><span data-stu-id="03065-135">Country</span></span>|  
    |<span data-ttu-id="03065-136">Zip Code</span><span class="sxs-lookup"><span data-stu-id="03065-136">Zip Code</span></span>|<span data-ttu-id="03065-137">Zip</span><span class="sxs-lookup"><span data-stu-id="03065-137">Zip</span></span>|  
  
12. <span data-ttu-id="03065-138">Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Editor de transformación limpieza de DQS** .</span><span class="sxs-lookup"><span data-stu-id="03065-138">Click **OK** to close the **DQS Cleansing Transformation Editor** dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="03065-139">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="03065-139">Next Step</span></span>  
 [<span data-ttu-id="03065-140">Tarea 8: Adición de la transformación División condicional para dividir el resultado de la limpieza</span><span class="sxs-lookup"><span data-stu-id="03065-140">Task 8: Adding Conditional Split Transform to Split Cleansing Output</span></span>](../../2014/tutorials/task-8-adding-conditional-split-transform-to-split-cleansing-output.md)  
  
  
