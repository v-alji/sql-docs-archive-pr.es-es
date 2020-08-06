---
title: 'Paso 1: Copiar el paquete de la lección 1 | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 7f1616c2-2b4e-4010-be50-27d7b897403a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 43e117d82983bdaca8959fe7af8940d248ded97b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673104"
---
# <a name="step-1-copying-the-lesson-1-package"></a><span data-ttu-id="13b60-102">Paso 1: Copia del paquete de la lección 1</span><span class="sxs-lookup"><span data-stu-id="13b60-102">Step 1: Copying the Lesson 1 Package</span></span>
  <span data-ttu-id="13b60-103">En esta tarea, creará una copia del paquete que ha creado en la lección 1, denominado Lesson 1.dtsx.</span><span class="sxs-lookup"><span data-stu-id="13b60-103">In this task, you will create a copy of the Lesson 1.dtsx package that you created in Lesson 1.</span></span> <span data-ttu-id="13b60-104">Si no ha completado la lección 1, puede agregar al proyecto el paquete completado de la lección 1 que se incluye con el tutorial y, después, copiar dicho paquete.</span><span class="sxs-lookup"><span data-stu-id="13b60-104">If you did not complete Lesson 1, you can add the completed lesson 1 package that is included with the tutorial to the project, and then copy it instead.</span></span> <span data-ttu-id="13b60-105">Usará esta nueva copia en toda la lección 2.</span><span class="sxs-lookup"><span data-stu-id="13b60-105">You will use this new copy throughout the rest of Lesson 2.</span></span>  
  
### <a name="to-create-the-lesson-2-package"></a><span data-ttu-id="13b60-106">Para crear el paquete de la lección 2</span><span class="sxs-lookup"><span data-stu-id="13b60-106">To create the Lesson 2 package</span></span>  
  
1.  <span data-ttu-id="13b60-107">Si [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools no está abierto, haga clic en **Inicio**, seleccione **Todos los programas**, **Microsoft SQL Server 2012**y, después, haga clic en **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="13b60-107">If [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools is not already open, click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2012**, and then click **SQL Server Data Tools**.</span></span>  
  
2.  <span data-ttu-id="13b60-108">En el menú **Archivo** , haga clic en **Abrir**y en **Proyecto o solución**, haga clic en la carpeta **SSIS Tutorial** , haga clic en **Abrir**y, después, haga doble clic en **SSIS Tutorial.sln**.</span><span class="sxs-lookup"><span data-stu-id="13b60-108">On the **File** menu, click **Open**, click **Project/Solution**, click the **SSIS Tutorial** folder and click **Open**, and then double-click **SSIS Tutorial.sln**.</span></span>  
  
3.  <span data-ttu-id="13b60-109">En el Explorador de soluciones, haga clic con el botón derecho en **Lesson 1.dtsx**y luego haga clic en **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="13b60-109">In Solution Explorer, right-click **Lesson 1.dtsx**, and then click **Copy**.</span></span>  
  
4.  <span data-ttu-id="13b60-110">En Explorador de soluciones, haga clic con el botón secundario en **paquetes SSIS**y, a continuación, haga clic en **pegar**.</span><span class="sxs-lookup"><span data-stu-id="13b60-110">In Solution Explorer, right-click **SSIS Packages**, and then click **Paste**.</span></span>  
  
     <span data-ttu-id="13b60-111">De forma predeterminada, el paquete copiado se denominará Lesson 2.dtsx.</span><span class="sxs-lookup"><span data-stu-id="13b60-111">By default, the copied package will be named Lesson 2.dtsx.</span></span>  
  
5.  <span data-ttu-id="13b60-112">En Explorador de soluciones, haga doble clic en la **Lección 2. DTSX** para abrir el paquete</span><span class="sxs-lookup"><span data-stu-id="13b60-112">In Solution Explorer, double-click **Lesson 2.dtsx** to open the package</span></span>  
  
6.  <span data-ttu-id="13b60-113">Haga clic con el botón derecho en cualquier parte del fondo de la superficie de diseño de **Flujo de control** y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="13b60-113">Right-click anywhere in the background of the **Control Flow** design surface and click **Properties**.</span></span>  
  
7.  <span data-ttu-id="13b60-114">En el ventana Propiedades, actualice la `Name` propiedad a `Lesson 2` .</span><span class="sxs-lookup"><span data-stu-id="13b60-114">In the Properties window, update the `Name` property to `Lesson 2`.</span></span>  
  
8.  <span data-ttu-id="13b60-115">Haga clic en el cuadro de la propiedad **Id.** , haga clic en la flecha desplegable y luego haga clic en **\<Generate New ID>**.</span><span class="sxs-lookup"><span data-stu-id="13b60-115">Click the box for the **ID** property, click the dropdown arrow and then click **\<Generate New ID>**.</span></span>  
  
### <a name="to-add-the-completed-lesson-1-package"></a><span data-ttu-id="13b60-116">Para agregar el paquete de la lección 1 completada</span><span class="sxs-lookup"><span data-stu-id="13b60-116">To add the completed Lesson 1 package</span></span>  
  
1.  <span data-ttu-id="13b60-117">Abra [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools y el proyecto SSIS Tutorial.</span><span class="sxs-lookup"><span data-stu-id="13b60-117">Open [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools and open the SSIS Tutorial project.</span></span>  
  
2.  <span data-ttu-id="13b60-118">En Explorador de soluciones, haga clic con el botón secundario en **paquetes SSIS**y haga clic en **Agregar paquete existente**.</span><span class="sxs-lookup"><span data-stu-id="13b60-118">In Solution Explorer, right-click **SSIS Packages**, and click **Add Existing Package**.</span></span>  
  
3.  <span data-ttu-id="13b60-119">En el cuadro de diálogo **Agregar copia de paquete existente** , en **Ubicación del paquete**, seleccione **Sistema de archivos**.</span><span class="sxs-lookup"><span data-stu-id="13b60-119">In the **Add Copy of Existing Package** dialog box, in **Package location**, select **File system**.</span></span>  
  
4.  <span data-ttu-id="13b60-120">Haga clic en el botón Examinar **(…)**, busque **Lesson 1.dtsx** en el equipo y, después, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="13b60-120">Click the browse **(...)** button, navigate to **Lesson 1.dtsx** on your machine, and then click **Open**.</span></span>  
  
     <span data-ttu-id="13b60-121">Para descargar todos los paquetes de lecciones de este tutorial, haga lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="13b60-121">To download all of the lesson packages for this tutorial, do the following.</span></span>  
  
    1.  <span data-ttu-id="13b60-122">Navegue a los [ejemplos del producto Integration Services](https://go.microsoft.com/fwlink/?LinkId=275027)</span><span class="sxs-lookup"><span data-stu-id="13b60-122">Navigate to [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=275027)</span></span>  
  
    2.  <span data-ttu-id="13b60-123">Haga clic en la pestaña **descargas** .</span><span class="sxs-lookup"><span data-stu-id="13b60-123">Click the **DOWNLOADS** tab.</span></span>  
  
    3.  <span data-ttu-id="13b60-124">Haga clic en el archivo SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip.</span><span class="sxs-lookup"><span data-stu-id="13b60-124">Click the SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip file.</span></span>  
  
5.  <span data-ttu-id="13b60-125">Copie y pegue el paquete de la lección 1 tal como se describe en los pasos 3 a 8 del procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="13b60-125">Copy and paste the Lesson 1 package as described in steps 3-8 in the previous procedure.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="13b60-126">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="13b60-126">Next Task in Lesson</span></span>  
 [<span data-ttu-id="13b60-127">Paso 2: Adición y configuración del contenedor de bucles Foreach</span><span class="sxs-lookup"><span data-stu-id="13b60-127">Step 2: Adding and Configuring the Foreach Loop Container</span></span>](lesson-2-2-adding-and-configuring-the-foreach-loop-container.md)  
  
  
