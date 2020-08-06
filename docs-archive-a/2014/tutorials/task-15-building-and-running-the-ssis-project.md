---
title: 'Tarea 15: compilar y ejecutar el proyecto de SSIS | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 13adf4e0-216a-4992-b13d-b7b1e1629e77
ms.author: lle
author: lrtoyou1223
ms.openlocfilehash: 2a008cd848c95b48e6e22798b6ef903942b4d656
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747287"
---
# <a name="task-15-building-and-running-the-ssis-project"></a><span data-ttu-id="c7b97-102">Tarea 15: Compilación y ejecución del proyecto de SSIS</span><span class="sxs-lookup"><span data-stu-id="c7b97-102">Task 15: Building and Running the SSIS Project</span></span>

  <span data-ttu-id="c7b97-103">En esta tarea, compilará y ejecutará el proyecto de SSIS.</span><span class="sxs-lookup"><span data-stu-id="c7b97-103">In this task, you build and run the SSIS project.</span></span> <span data-ttu-id="c7b97-104">Si tiene instalada la versión de 64 bits de Excel 2010 en el equipo, debe establecer el valor de **Run64BitRuntime** en **false** para que el origen de Excel funcione.</span><span class="sxs-lookup"><span data-stu-id="c7b97-104">If you have the 64-bit version of Excel 2010 installed on your computer, you should set the value of **Run64BitRuntime** to **False** for the Excel source to work.</span></span>  
  
1.  <span data-ttu-id="c7b97-105">En la ventana de **Explorador de soluciones** , haga clic en **proyecto** en el menú y, a continuación, haga clic en **propiedades de CleanseAndCurateSuppliers**.</span><span class="sxs-lookup"><span data-stu-id="c7b97-105">In the **Solution Explorer** window, click **Project** on the menu, and click **CleanseAndCurateSuppliers Properties**.</span></span>  
  
2.  <span data-ttu-id="c7b97-106">En el cuadro de diálogo **propiedades** , expanda **propiedades de configuración** a la izquierda y haga clic en **depuración**.</span><span class="sxs-lookup"><span data-stu-id="c7b97-106">In the **Properties** dialog box, expand **Configuration Properties** on left, and click **Debugging**.</span></span>  
  
3.  <span data-ttu-id="c7b97-107">Establezca **Run64BitRuntime** en **false**.</span><span class="sxs-lookup"><span data-stu-id="c7b97-107">Set **Run64BitRuntime** to **False**.</span></span>  
  
     <span data-ttu-id="c7b97-108">![Propiedades del proyecto CleanseAndCurateSuppliers](../../2014/tutorials/media/et-buildingandrunningthessisproject-01.jpg "Propiedades del proyecto CleanseAndCurateSuppliers")</span><span class="sxs-lookup"><span data-stu-id="c7b97-108">![CleanseAndCurateSuppliers Project Properties](../../2014/tutorials/media/et-buildingandrunningthessisproject-01.jpg "CleanseAndCurateSuppliers Project Properties")</span></span>  
  
4.  <span data-ttu-id="c7b97-109">Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c7b97-109">Click **OK** to close the **Properties** dialog box.</span></span>  
  
5.  <span data-ttu-id="c7b97-110">Haga clic en **compilar** en la barra de menús y haga clic en **generar CleanseAndCurateSuppliers**.</span><span class="sxs-lookup"><span data-stu-id="c7b97-110">Click **Build** on menu bar and click **Build CleanseAndCurateSuppliers**.</span></span> <span data-ttu-id="c7b97-111">Asegúrese de que no hay errores de compilación.</span><span class="sxs-lookup"><span data-stu-id="c7b97-111">Make sure that there are no build errors.</span></span>  
  
6.  <span data-ttu-id="c7b97-112">Haga clic en **depurar** en la barra de menús y haga clic en **iniciar depuración**.</span><span class="sxs-lookup"><span data-stu-id="c7b97-112">Click **Debug** on the menu bar and click **Start Debugging**.</span></span>  
  
7.  <span data-ttu-id="c7b97-113">Revise los mensajes en la ventana de **progreso** y compruebe que el paquete se ejecutó y finalizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="c7b97-113">Review messages in the **Progress** window and verify that package executed and ended successfully.</span></span>  
  
     <span data-ttu-id="c7b97-114">![Resultados de la ventana de progreso](../../2014/tutorials/media/et-buildingandrunningthessisproject-02.jpg "Resultados de la ventana de progreso")</span><span class="sxs-lookup"><span data-stu-id="c7b97-114">![Results from Progress Window](../../2014/tutorials/media/et-buildingandrunningthessisproject-02.jpg "Results from Progress Window")</span></span>  
  
     <span data-ttu-id="c7b97-115">![Estado final de la ventana de progreso](../../2014/tutorials/media/et-buildingandrunningthessisproject-03.jpg "Estado final de la ventana de progreso")</span><span class="sxs-lookup"><span data-stu-id="c7b97-115">![Final Status from Progress Window](../../2014/tutorials/media/et-buildingandrunningthessisproject-03.jpg "Final Status from Progress Window")</span></span>  
  
8.  <span data-ttu-id="c7b97-116">Haga clic en **depurar** en la barra de menús y en **detener depuración** para detener la sesión de depuración.</span><span class="sxs-lookup"><span data-stu-id="c7b97-116">Click **Debug** on menu bar and click **Stop Debugging** to stop the debugging session.</span></span> <span data-ttu-id="c7b97-117">Si se produce un error en el paquete, debe habilitar los visores de datos y ver cómo fluyen los datos entre los componentes.</span><span class="sxs-lookup"><span data-stu-id="c7b97-117">If the package fails, you should enable data viewers and see how the data flows between components.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="c7b97-118">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="c7b97-118">Next Step</span></span>  
 [<span data-ttu-id="c7b97-119">Tarea 16: Comprobación con Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="c7b97-119">Task 16: Verifying with Master Data Manager</span></span>](../../2014/tutorials/task-16-verifying-with-master-data-manager.md)  
  
  
