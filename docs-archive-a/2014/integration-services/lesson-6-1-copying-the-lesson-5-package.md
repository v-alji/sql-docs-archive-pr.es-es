---
title: 'Paso 1: Copiar el paquete de la lección 5 | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: a25fcc13-987e-4f3d-8f0c-76f7e6e59920
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b30ec927084548a2371f22d857d5302e5dc84c5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677777"
---
# <a name="step-1-copying-the-lesson-5-package"></a><span data-ttu-id="9dd13-102">Paso 1: Copia del paquete de la lección 5</span><span class="sxs-lookup"><span data-stu-id="9dd13-102">Step 1: Copying the Lesson 5 Package</span></span>
  <span data-ttu-id="9dd13-103">En esta tarea, creará una copia del paquete que ha creado en la lección 5, denominado Lesson 5.dtsx.</span><span class="sxs-lookup"><span data-stu-id="9dd13-103">In this task, you will create a copy of the Lesson 5.dtsx package that you created in Lesson 5.</span></span> <span data-ttu-id="9dd13-104">También puede agregar al proyecto el paquete completado de la lección 5 que se incluye con el tutorial y, a continuación, copiar dicho paquete.</span><span class="sxs-lookup"><span data-stu-id="9dd13-104">Alternatively, you can add the completed lesson 5 package that is included with the tutorial to the project, and then copy it instead.</span></span> <span data-ttu-id="9dd13-105">Utilizará esta nueva copia en toda la lección 6.</span><span class="sxs-lookup"><span data-stu-id="9dd13-105">You will use this new copy throughout the rest of Lesson 6.</span></span>  
  
### <a name="to-copy-the-lesson-5-package"></a><span data-ttu-id="9dd13-106">Para copiar el paquete de la lección 5</span><span class="sxs-lookup"><span data-stu-id="9dd13-106">To copy the Lesson 5 package</span></span>  
  
1.  <span data-ttu-id="9dd13-107">Si SQL Server Data Tools no está abierto, haga clic en Inicio, seleccione Todos los programas, seleccione Microsoft SQL Server 2012 y, a continuación, haga clic en SQL Server Data Tools.</span><span class="sxs-lookup"><span data-stu-id="9dd13-107">If SQL Server Data Tools is not already open, click Start, point to All Programs, point to Microsoft SQL Server 2012, and then click SQL Server Data Tools.</span></span>  
  
2.  <span data-ttu-id="9dd13-108">En el menú Archivo, haga clic en Abrir, haga clic en Proyecto o solución, seleccione SSIS Tutorial, haga clic en Abrir y, después, haga doble clic en SSIS Tutorial.sln.</span><span class="sxs-lookup"><span data-stu-id="9dd13-108">On the File menu, click Open, click Project/Solution, select SSIS Tutorial and click Open, and then double-click SSIS Tutorial.sln.</span></span>  
  
3.  <span data-ttu-id="9dd13-109">En el Explorador de soluciones, haga clic con el botón secundario en Lesson 5.dtsx y, a continuación, haga clic en Copiar.</span><span class="sxs-lookup"><span data-stu-id="9dd13-109">In Solution Explorer, right-click Lesson 5.dtsx, and then click Copy.</span></span>  
  
4.  <span data-ttu-id="9dd13-110">En el Explorador de soluciones, haga clic con el botón secundario en Paquetes SSIS y, a continuación, haga clic en Pegar.</span><span class="sxs-lookup"><span data-stu-id="9dd13-110">In Solution Explorer, right-click SSIS Packages, and then click Paste.</span></span>  
  
     <span data-ttu-id="9dd13-111">De forma predeterminada, el paquete copiado se denomina Lesson 6.dtsx.</span><span class="sxs-lookup"><span data-stu-id="9dd13-111">By default, the copied package is named Lesson 6.dtsx.</span></span>  
  
5.  <span data-ttu-id="9dd13-112">En el Explorador de soluciones, haga doble clic en Lesson 6.dtsx para abrir el paquete.</span><span class="sxs-lookup"><span data-stu-id="9dd13-112">In the Solution Explorer, double-click Lesson 6.dtsx to open the package.</span></span>  
  
6.  <span data-ttu-id="9dd13-113">Haga clic con el botón secundario en cualquier parte del fondo de la pestaña Flujo de control y luego haga clic en Propiedades.</span><span class="sxs-lookup"><span data-stu-id="9dd13-113">Right-click anywhere in the background of the Control Flow tab then click Properties.</span></span>  
  
7.  <span data-ttu-id="9dd13-114">En la ventana Propiedades, actualice la propiedad Nombre a Lesson 6.</span><span class="sxs-lookup"><span data-stu-id="9dd13-114">In the Properties window, update the Name property to Lesson 6.</span></span>  
  
8.  <span data-ttu-id="9dd13-115">Haga clic en el cuadro de la propiedad Id., haga clic en la flecha desplegable y luego haga clic en \<Generate New ID>.</span><span class="sxs-lookup"><span data-stu-id="9dd13-115">Click the box for the ID property, then click the dropdown arrow, and then click \<Generate New ID>.</span></span>  
  
### <a name="to-add-the-completed-lesson-5-package"></a><span data-ttu-id="9dd13-116">Para agregar el paquete de la lección 5 completada</span><span class="sxs-lookup"><span data-stu-id="9dd13-116">To add the completed Lesson 5 package</span></span>  
  
1.  <span data-ttu-id="9dd13-117">Abra SQL Server Data Tools y el proyecto SSIS Tutorial.</span><span class="sxs-lookup"><span data-stu-id="9dd13-117">Open SQL Server Data Tools and open the SSIS Tutorial project.</span></span>  
  
2.  <span data-ttu-id="9dd13-118">En el Explorador de soluciones, haga clic con el botón secundario en Paquetes SSIS y haga clic en Agregar paquete existente.</span><span class="sxs-lookup"><span data-stu-id="9dd13-118">In Solution Explorer, right-click SSIS Packages, and click Add Existing Package.</span></span>  
  
3.  <span data-ttu-id="9dd13-119">En el cuadro de diálogo Agregar copia de paquete existente, en Ubicación del paquete, seleccione Sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="9dd13-119">In the Add Copy of Existing Package dialog box, in Package location, select File system.</span></span>  
  
4.  <span data-ttu-id="9dd13-120">Haga clic en el botón Examinar (...), Lección 5. DTSX en el equipo y, a continuación, haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="9dd13-120">Click the browse (...) button, Lesson 5.dtsx on your machine, and then click **Open**.</span></span>  
  
     <span data-ttu-id="9dd13-121">Para descargar todos los paquetes de lecciones de este tutorial, haga lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="9dd13-121">To download all of the lesson packages for this tutorial, do the following.</span></span>  
  
    1.  <span data-ttu-id="9dd13-122">Navegue a los [ejemplos del producto Integration Services](https://go.microsoft.com/fwlink/?LinkId=275027)</span><span class="sxs-lookup"><span data-stu-id="9dd13-122">Navigate to [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=275027)</span></span>  
  
    2.  <span data-ttu-id="9dd13-123">Haga clic en la pestaña **descargas** .</span><span class="sxs-lookup"><span data-stu-id="9dd13-123">Click the **DOWNLOADS** tab.</span></span>  
  
    3.  <span data-ttu-id="9dd13-124">Haga clic en el archivo SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip.</span><span class="sxs-lookup"><span data-stu-id="9dd13-124">Click the SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip file.</span></span>  
  
5.  <span data-ttu-id="9dd13-125">Copie y pegue el paquete de la lección 5 tal como se describe en los pasos 3 a 8 del procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="9dd13-125">Copy and paste the Lesson 5 package as described in steps 3-8 in the previous procedure.</span></span>  
  
     <span data-ttu-id="9dd13-126">Después de copiar el paquete de la lección 5, si tiene actualmente los paquetes de las lecciones anteriores en la solución, haga clic con el botón secundario en cada paquete de las lecciones 1 a 5 y, a continuación, haga clic en Excluir del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9dd13-126">After copying the Lesson 5 package, if you currently have the packages from the previous lessons in your solution, right-click each package from lessons 1-5 and click Exclude From Project.</span></span> <span data-ttu-id="9dd13-127">Cuando termine, debe tener solo Lesson 6.dtsx en la solución.</span><span class="sxs-lookup"><span data-stu-id="9dd13-127">When done you should have only Lesson 6.dtsx in your solution.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="9dd13-128">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="9dd13-128">Next Task in Lesson</span></span>  
 [<span data-ttu-id="9dd13-129">Paso 2: Convertir el proyecto al modelo de implementación del proyectos</span><span class="sxs-lookup"><span data-stu-id="9dd13-129">Step 2: Converting the Project to the Project Deployment Model</span></span>](lesson-6-2-converting-the-project-to-the-project-deployment-model.md)  
  
  
