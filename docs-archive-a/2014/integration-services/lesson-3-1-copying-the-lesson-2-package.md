---
title: 'Paso 1: Copiar el paquete de la lección 2 | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 4bd91402-4e37-41de-ab78-8ca5a1948a37
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 39bfc965febc401bd66b1077388021b8ccf52aed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745900"
---
# <a name="step-1-copying-the-lesson-2-package"></a><span data-ttu-id="0a234-102">Paso 1: Copia del paquete de la lección 2</span><span class="sxs-lookup"><span data-stu-id="0a234-102">Step 1: Copying the Lesson 2 Package</span></span>
  <span data-ttu-id="0a234-103">En esta tarea, creará una copia del paquete que ha creado en la lección 2, denominado Lesson 2.dtsx.</span><span class="sxs-lookup"><span data-stu-id="0a234-103">In this task, you will create a copy of the Lesson 2.dtsx package that you created in Lesson 2.</span></span> <span data-ttu-id="0a234-104">También puede agregar al proyecto el paquete completado de la lección 2 que se incluye con el tutorial y, después, copiar dicho paquete.</span><span class="sxs-lookup"><span data-stu-id="0a234-104">Alternatively, you can add the completed lesson 2 package that is included with the tutorial to the project, and then copy it instead.</span></span> <span data-ttu-id="0a234-105">Usará esta nueva copia en toda la lección 3.</span><span class="sxs-lookup"><span data-stu-id="0a234-105">You will use this new copy throughout the rest of Lesson 3.</span></span>  
  
### <a name="to-create-the-lesson-3-package"></a><span data-ttu-id="0a234-106">Para crear el paquete de la lección 3</span><span class="sxs-lookup"><span data-stu-id="0a234-106">To create the Lesson 3 package</span></span>  
  
1.  <span data-ttu-id="0a234-107">Si [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools no está abierto, haga clic en **Inicio**, seleccione **Todos los programas**, **Microsoft SQL Server 2012**y, después, haga clic en **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="0a234-107">If [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools is not already open, click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2012**, and then click **SQL Server Data Tools**.</span></span>  
  
2.  <span data-ttu-id="0a234-108">En el menú **Archivo** , haga clic en **Abrir**, haga clic en **Proyecto o solución**, seleccione **SSIS Tutorial** , haga clic en **Abrir**y, después, haga doble clic en **SSIS Tutorial.sln**.</span><span class="sxs-lookup"><span data-stu-id="0a234-108">On the **File** menu, click **Open**, click **Project/Solution**, select **SSIS Tutorial** and click **Open**, and then double-click **SSIS Tutorial.sln**.</span></span>  
  
3.  <span data-ttu-id="0a234-109">En el Explorador de soluciones, haga clic con el botón derecho en **Lesson 2.dtsx**y, después, haga clic en **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="0a234-109">In Solution Explorer, right-click **Lesson 2.dtsx**, and then click **Copy**.</span></span>  
  
4.  <span data-ttu-id="0a234-110">En Explorador de soluciones, haga clic con el botón secundario en **paquetes SSIS**y, a continuación, haga clic en **pegar**.</span><span class="sxs-lookup"><span data-stu-id="0a234-110">In Solution Explorer, right-click **SSIS Packages**, and then click **Paste**.</span></span>  
  
     <span data-ttu-id="0a234-111">De forma predeterminada, el paquete copiado se denomina Lesson 3.dtsx.</span><span class="sxs-lookup"><span data-stu-id="0a234-111">By default, the copied package is named Lesson 3.dtsx.</span></span>  
  
5.  <span data-ttu-id="0a234-112">En Explorador de soluciones, haga doble clic en **Lección 3. DTSX** para abrir el paquete.</span><span class="sxs-lookup"><span data-stu-id="0a234-112">In Solution Explorer, double-click **Lesson 3.dtsx** to open the package.</span></span>  
  
6.  <span data-ttu-id="0a234-113">Haga clic con el botón derecho en cualquier parte del fondo de la pestaña **Flujo de control** y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0a234-113">Right-click anywhere in the background of the **Control Flow** tab and click **Properties**.</span></span>  
  
7.  <span data-ttu-id="0a234-114">En el ventana Propiedades, actualice la `Name` propiedad a `Lesson 3` .</span><span class="sxs-lookup"><span data-stu-id="0a234-114">In the Properties window, update the `Name` property to `Lesson 3`.</span></span>  
  
8.  <span data-ttu-id="0a234-115">Haga clic en el cuadro para la propiedad **ID** y, en la lista, haga clic en **\<Generate New ID>**.</span><span class="sxs-lookup"><span data-stu-id="0a234-115">Click the box for the **ID** property, and then in the list, click **\<Generate New ID>**.</span></span>  
  
### <a name="to-add-the-completed-lesson2-package"></a><span data-ttu-id="0a234-116">Para agregar el paquete de la lección 2 completada</span><span class="sxs-lookup"><span data-stu-id="0a234-116">To add the completed Lesson2 package</span></span>  
  
1.  <span data-ttu-id="0a234-117">Abra [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] y abra el proyecto SSIS Tutorial.</span><span class="sxs-lookup"><span data-stu-id="0a234-117">Open [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and open the SSIS Tutorial project.</span></span>  
  
2.  <span data-ttu-id="0a234-118">En Explorador de soluciones, haga clic con el botón secundario en **paquetes SSIS**y haga clic en **Agregar paquete existente**.</span><span class="sxs-lookup"><span data-stu-id="0a234-118">In Solution Explorer, right-click **SSIS Packages**, and click **Add Existing Package**.</span></span>  
  
3.  <span data-ttu-id="0a234-119">En el cuadro de diálogo **Agregar copia de paquete existente** , en **Ubicación del paquete**, seleccione **Sistema de archivos**.</span><span class="sxs-lookup"><span data-stu-id="0a234-119">In the **Add Copy of Existing Package** dialog box, in **Package location**, select **File system**.</span></span>  
  
4.  <span data-ttu-id="0a234-120">Haga clic en el botón Examinar **(…)**, busque **Lesson 2.dtsx** en el equipo y, después, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="0a234-120">Click the browse **(...)** button, navigate to **Lesson 2.dtsx** on your machine, and then click **Open**.</span></span>  
  
     <span data-ttu-id="0a234-121">Para descargar todos los paquetes de lecciones de este tutorial, haga lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="0a234-121">To download all of the lesson packages for this tutorial, do the following.</span></span>  
  
    1.  <span data-ttu-id="0a234-122">Navegue a los [ejemplos del producto Integration Services](https://go.microsoft.com/fwlink/?LinkId=275027)</span><span class="sxs-lookup"><span data-stu-id="0a234-122">Navigate to [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=275027)</span></span>  
  
    2.  <span data-ttu-id="0a234-123">Haga clic en la pestaña **descargas** .</span><span class="sxs-lookup"><span data-stu-id="0a234-123">Click the **DOWNLOADS** tab.</span></span>  
  
    3.  <span data-ttu-id="0a234-124">Haga clic en el archivo SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip.</span><span class="sxs-lookup"><span data-stu-id="0a234-124">Click the SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip file.</span></span>  
  
5.  <span data-ttu-id="0a234-125">Copie y pegue el paquete de la lección 3 tal como se describe en los pasos del 3 a 8 del procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="0a234-125">Copy and paste the Lesson 3 package as described in steps 3-8 in the previous procedure.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="0a234-126">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="0a234-126">Next Task in Lesson</span></span>  
 [<span data-ttu-id="0a234-127">Paso 2: Adición y configuración de registro</span><span class="sxs-lookup"><span data-stu-id="0a234-127">Step 2: Adding and Configuring Logging</span></span>](lesson-3-2-adding-and-configuring-logging.md)  
  
  
