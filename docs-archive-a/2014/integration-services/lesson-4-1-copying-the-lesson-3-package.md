---
title: 'Paso 1: Copiar el paquete de la lección 3 | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 0d053786-5203-43f3-a613-27a8dd2bc44a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fde3bd907e8a55b1ac9a164b2960268189b19392
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672172"
---
# <a name="step-1-copying-the-lesson-3-package"></a><span data-ttu-id="44397-102">Paso 1: Copia del paquete de la lección 3</span><span class="sxs-lookup"><span data-stu-id="44397-102">Step 1: Copying the Lesson 3 Package</span></span>
  <span data-ttu-id="44397-103">En esta tarea, creará una copia del paquete que ha creado en la lección 3, denominado Lesson 3.dtsx.</span><span class="sxs-lookup"><span data-stu-id="44397-103">In this task, you will create a copy of the Lesson 3.dtsx package that you created in Lesson 3.</span></span> <span data-ttu-id="44397-104">Por otra parte, si no ha completado la lección 3, puede agregar al proyecto el paquete completado de la lección 3 que se incluye con el tutorial y, a continuación, copiar dicho paquete para trabajar.</span><span class="sxs-lookup"><span data-stu-id="44397-104">Alternatively, if you did not complete lesson 3, you can add the completed lesson 3 package that is included with the tutorial to the project, and then make a copy of it to work with.</span></span> <span data-ttu-id="44397-105">Usará esta nueva copia en toda la lección 4.</span><span class="sxs-lookup"><span data-stu-id="44397-105">You will use this new copy throughout the rest of Lesson 4.</span></span>  
  
### <a name="to-create-the-lesson-4-package"></a><span data-ttu-id="44397-106">Para crear el paquete de la lección 4</span><span class="sxs-lookup"><span data-stu-id="44397-106">To create the Lesson 4 package</span></span>  
  
1.  <span data-ttu-id="44397-107">Si [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools no está abierto, haga clic en **Inicio**, seleccione **Todos los programas**, **Microsoft SQL Server**y, después, haga clic en **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="44397-107">If [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools is not already open, click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, and then click **SQL Server Data Tools**.</span></span>  
  
2.  <span data-ttu-id="44397-108">En el menú **Archivo** , haga clic en **Abrir**, haga clic en **Proyecto o solución**, seleccione **SSIS Tutorial** , haga clic en **Abrir**y, después, haga doble clic en **SSIS Tutorial.sln**.</span><span class="sxs-lookup"><span data-stu-id="44397-108">On the **File** menu, click **Open**, click **Project/Solution**, select **SSIS Tutorial** and click **Open**, and then double-click **SSIS Tutorial.sln**.</span></span>  
  
3.  <span data-ttu-id="44397-109">En el Explorador de soluciones, haga clic con el botón derecho en **Lesson 3.dtsx**y, después, haga clic en **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="44397-109">In Solution Explorer, right-click **Lesson 3.dtsx**, and then click **Copy**.</span></span>  
  
4.  <span data-ttu-id="44397-110">En Explorador de soluciones, haga clic con el botón secundario en **paquetes SSIS**y, a continuación, haga clic en **pegar**.</span><span class="sxs-lookup"><span data-stu-id="44397-110">In Solution Explorer, right-click **SSIS Packages**, and then click **Paste**.</span></span>  
  
     <span data-ttu-id="44397-111">De forma predeterminada, el paquete copiado se denomina Lesson 4.dtsx.</span><span class="sxs-lookup"><span data-stu-id="44397-111">By default, the copied package is named Lesson 4.dtsx.</span></span>  
  
5.  <span data-ttu-id="44397-112">En Explorador de soluciones, haga doble clic en la **Lección 4. DTSX** para abrir el paquete.</span><span class="sxs-lookup"><span data-stu-id="44397-112">In Solution Explorer, double-click **Lesson 4.dtsx** to open the package.</span></span>  
  
6.  <span data-ttu-id="44397-113">Haga clic con el botón derecho en cualquier parte del fondo de la pestaña **Flujo de control** y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="44397-113">Right-click anywhere in the background of the **Control Flow** tab and click **Properties**.</span></span>  
  
7.  <span data-ttu-id="44397-114">En el ventana Propiedades, actualice la `Name` propiedad a `Lesson 4` .</span><span class="sxs-lookup"><span data-stu-id="44397-114">In the Properties window, update the `Name` property to `Lesson 4`.</span></span>  
  
8.  <span data-ttu-id="44397-115">Haga clic en el cuadro para la propiedad **ID** y, en la lista, haga clic en **\<Generate New ID>**.</span><span class="sxs-lookup"><span data-stu-id="44397-115">Click the box for the **ID** property, and then in the list, click **\<Generate New ID>**.</span></span>  
  
### <a name="to-add-the-completed-lesson-3-package"></a><span data-ttu-id="44397-116">Para agregar el paquete de la lección 3 completada</span><span class="sxs-lookup"><span data-stu-id="44397-116">To add the completed Lesson 3 package</span></span>  
  
1.  <span data-ttu-id="44397-117">Abra [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] y abra el proyecto SSIS Tutorial.</span><span class="sxs-lookup"><span data-stu-id="44397-117">Open [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and open the SSIS Tutorial project.</span></span>  
  
2.  <span data-ttu-id="44397-118">En Explorador de soluciones, haga clic con el botón secundario en **paquetes SSIS**y haga clic en **Agregar paquete existente**.</span><span class="sxs-lookup"><span data-stu-id="44397-118">In Solution Explorer, right-click **SSIS Packages**, and click **Add Existing Package**.</span></span>  
  
3.  <span data-ttu-id="44397-119">En el cuadro de diálogo **Agregar copia de paquete existente** , en **Ubicación del paquete**, seleccione **Sistema de archivos**.</span><span class="sxs-lookup"><span data-stu-id="44397-119">In the **Add Copy of Existing Package** dialog box, in **Package location**, select **File system**.</span></span>  
  
4.  <span data-ttu-id="44397-120">Haga clic en el botón examinar **(...)** , vaya a la lección 3. DTSX en la máquina y, a continuación, haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="44397-120">Click the browse **(...)** button, navigate to Lesson 3.dtsx on your machine, and then click **Open**.</span></span>  
  
     <span data-ttu-id="44397-121">Para descargar todos los paquetes de lecciones de este tutorial, haga lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="44397-121">To download all of the lesson packages for this tutorial, do the following.</span></span>  
  
    1.  <span data-ttu-id="44397-122">Navegue a los [ejemplos del producto Integration Services](https://go.microsoft.com/fwlink/?LinkId=275027)</span><span class="sxs-lookup"><span data-stu-id="44397-122">Navigate to [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=275027)</span></span>  
  
    2.  <span data-ttu-id="44397-123">Haga clic en la pestaña **descargas** .</span><span class="sxs-lookup"><span data-stu-id="44397-123">Click the **DOWNLOADS** tab.</span></span>  
  
    3.  <span data-ttu-id="44397-124">Haga clic en el archivo SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip.</span><span class="sxs-lookup"><span data-stu-id="44397-124">Click the SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip file.</span></span>  
  
5.  <span data-ttu-id="44397-125">Copie y pegue el paquete de la lección 3 tal como se describe en los pasos del 3 a 8 del procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="44397-125">Copy and paste the Lesson 3 package as described in steps 3-8 in the previous procedure.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="44397-126">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="44397-126">Next Task in Lesson</span></span>  
 [<span data-ttu-id="44397-127">Paso 2: Creación de un archivo dañado</span><span class="sxs-lookup"><span data-stu-id="44397-127">Step 2: Creating a Corrupted File</span></span>](lesson-4-2-creating-a-corrupted-file.md)  
  
  
