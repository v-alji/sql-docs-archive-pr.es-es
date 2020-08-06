---
title: 'Paso 1: Copiar el paquete de la lección 4 | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 8aa7d690-4649-4c0a-ac6f-9504637ee426
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1140c0e7d26f11f79e18d42143c1ed084c4ff144
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677209"
---
# <a name="step-1-copying-the-lesson-4-package"></a><span data-ttu-id="551fe-102">Paso 1: Copia del paquete de la lección 4</span><span class="sxs-lookup"><span data-stu-id="551fe-102">Step 1: Copying the Lesson 4 Package</span></span>
  <span data-ttu-id="551fe-103">En esta tarea, creará una copia del paquete que ha creado en la lección 4, denominado Lesson 4.dtsx.</span><span class="sxs-lookup"><span data-stu-id="551fe-103">In this task, you will create a copy of the Lesson 4.dtsx package that you created in Lesson 4.</span></span> <span data-ttu-id="551fe-104">También puede agregar al proyecto el paquete completado de la lección 4 que se incluye con el tutorial y, después, copiar ese paquete.</span><span class="sxs-lookup"><span data-stu-id="551fe-104">Alternatively, you can add the completed lesson 4 package that is included with the tutorial to the project, and then copy it instead.</span></span> <span data-ttu-id="551fe-105">Usará esta nueva copia en toda la lección 5.</span><span class="sxs-lookup"><span data-stu-id="551fe-105">You will use this new copy throughout the rest of Lesson 5.</span></span>  
  
### <a name="to-copy-the-lesson-4-package"></a><span data-ttu-id="551fe-106">Para copiar el paquete de la lección 4</span><span class="sxs-lookup"><span data-stu-id="551fe-106">To copy the Lesson 4 package</span></span>  
  
1.  <span data-ttu-id="551fe-107">Si [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools no está abierto, haga clic en **Inicio**, seleccione **Todos los programas**, **Microsoft SQL Server 2012**y, después, haga clic en **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="551fe-107">If [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools is not already open, click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2012**, and then click **SQL Server Data Tools**.</span></span>  
  
2.  <span data-ttu-id="551fe-108">En el menú **Archivo** , haga clic en **Abrir**, haga clic en **Proyecto o solución**, seleccione **SSIS Tutorial** , haga clic en **Abrir**y, después, haga doble clic en **SSIS Tutorial.sln**.</span><span class="sxs-lookup"><span data-stu-id="551fe-108">On the **File** menu, click **Open**, click **Project/Solution**, select **SSIS Tutorial** and click **Open**, and then double-click **SSIS Tutorial.sln**.</span></span>  
  
3.  <span data-ttu-id="551fe-109">En el Explorador de soluciones, haga clic con el botón derecho en **Lesson 4.dtsx**y luego haga clic en **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="551fe-109">In Solution Explorer, right-click **Lesson 4.dtsx**, and then click **Copy**.</span></span>  
  
4.  <span data-ttu-id="551fe-110">En Explorador de soluciones, haga clic con el botón secundario en **paquetes SSIS**y, a continuación, haga clic en **pegar**.</span><span class="sxs-lookup"><span data-stu-id="551fe-110">In Solution Explorer, right-click **SSIS Packages**, and then click **Paste**.</span></span>  
  
     <span data-ttu-id="551fe-111">De manera predeterminada, el paquete copiado se denomina Lesson 5.dtsx.</span><span class="sxs-lookup"><span data-stu-id="551fe-111">By default, the copied package is named Lesson 5.dtsx.</span></span>  
  
5.  <span data-ttu-id="551fe-112">En el Explorador de soluciones, haga doble clic en **Lesson 5.dtsx** para abrir el paquete.</span><span class="sxs-lookup"><span data-stu-id="551fe-112">In the Solution Explorer, double-click **Lesson 5.dtsx** to open the package.</span></span>  
  
6.  <span data-ttu-id="551fe-113">Haga clic con el botón secundario en cualquier parte del fondo de la pestaña **flujo de control** y, después, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="551fe-113">Right-click anywhere in the background of the **Control Flow** tab then click **Properties**.</span></span>  
  
7.  <span data-ttu-id="551fe-114">En el ventana Propiedades, actualice la `Name` propiedad a `Lesson 5` .</span><span class="sxs-lookup"><span data-stu-id="551fe-114">In the Properties window, update the `Name` property to `Lesson 5`.</span></span>  
  
8.  <span data-ttu-id="551fe-115">Haga clic en el cuadro de la propiedad **Id.** , haga clic en la flecha desplegable y luego haga clic en **\<Generate New ID>**.</span><span class="sxs-lookup"><span data-stu-id="551fe-115">Click the box for the **ID** property, then click the dropdown arrow, and then click **\<Generate New ID>**.</span></span>  
  
### <a name="to-add-the-completed-lesson-4-package"></a><span data-ttu-id="551fe-116">Para agregar el paquete de la lección 4 completada</span><span class="sxs-lookup"><span data-stu-id="551fe-116">To add the completed Lesson 4 package</span></span>  
  
1.  <span data-ttu-id="551fe-117">Abra [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools y el proyecto SSIS Tutorial.</span><span class="sxs-lookup"><span data-stu-id="551fe-117">Open [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools and open the SSIS Tutorial project.</span></span>  
  
2.  <span data-ttu-id="551fe-118">En Explorador de soluciones, haga clic con el botón secundario en **paquetes SSIS**y haga clic en **Agregar paquete existente**.</span><span class="sxs-lookup"><span data-stu-id="551fe-118">In Solution Explorer, right-click **SSIS Packages**, and click **Add Existing Package**.</span></span>  
  
3.  <span data-ttu-id="551fe-119">En el cuadro de diálogo **Agregar copia de paquete existente** , en **Ubicación del paquete**, seleccione **Sistema de archivos**.</span><span class="sxs-lookup"><span data-stu-id="551fe-119">In the **Add Copy of Existing Package** dialog box, in **Package location**, select **File system**.</span></span>  
  
4.  <span data-ttu-id="551fe-120">Haga clic en el botón examinar **(...)** , vaya a la **Lección 4. DTSX** del equipo y, a continuación, haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="551fe-120">Click the browse **(...)** button, navigate to **Lesson 4.dtsx** on your machine, and then click **Open**.</span></span>  
  
     <span data-ttu-id="551fe-121">Para descargar todos los paquetes de lecciones de este tutorial, haga lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="551fe-121">To download all of the lesson packages for this tutorial, do the following.</span></span>  
  
    1.  <span data-ttu-id="551fe-122">Navegue a los [ejemplos del producto Integration Services](https://go.microsoft.com/fwlink/?LinkId=275027)</span><span class="sxs-lookup"><span data-stu-id="551fe-122">Navigate to [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=275027)</span></span>  
  
    2.  <span data-ttu-id="551fe-123">Haga clic en la pestaña **descargas** .</span><span class="sxs-lookup"><span data-stu-id="551fe-123">Click the **DOWNLOADS** tab.</span></span>  
  
    3.  <span data-ttu-id="551fe-124">Haga clic en el archivo SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip.</span><span class="sxs-lookup"><span data-stu-id="551fe-124">Click the SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip file.</span></span>  
  
5.  <span data-ttu-id="551fe-125">Copie y pegue el paquete de la lección 4 tal como se describe en los pasos 3 a 8 del procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="551fe-125">Copy and paste the Lesson 4 package as described in steps 3-8 in the previous procedure.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="551fe-126">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="551fe-126">Next Task in Lesson</span></span>  
 [<span data-ttu-id="551fe-127">Paso 2: Habilitación y configuración de configuraciones de paquete</span><span class="sxs-lookup"><span data-stu-id="551fe-127">Step 2: Enabling and Configuring Package Configurations</span></span>](lesson-5-2-enabling-and-configuring-package-configurations.md)  
  
  
