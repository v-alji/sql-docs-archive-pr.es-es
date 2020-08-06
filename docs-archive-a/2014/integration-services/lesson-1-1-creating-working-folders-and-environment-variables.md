---
title: 'Paso 1: Crear carpetas de trabajo y variables de entorno | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 45091ba2-ea3d-4399-9814-489d812b42cc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 63308d406e230538e5ca8b90dbb55bb802759bd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673142"
---
# <a name="step-1-creating-working-folders-and-environment-variables"></a><span data-ttu-id="503ed-102">Paso 1: Creación de las carpetas de trabajo y las variables de entorno</span><span class="sxs-lookup"><span data-stu-id="503ed-102">Step 1: Creating Working Folders and Environment Variables</span></span>
  <span data-ttu-id="503ed-103">En esta tarea, creará la carpeta de trabajo (C:\DeploymentTutorial) y las nuevas variables de entorno del sistema (`DataTransfer` y `LoadXMLData`) que usará en posteriores tareas del tutorial.</span><span class="sxs-lookup"><span data-stu-id="503ed-103">In this task, you will create the working folder (C:\DeploymentTutorial) and the new system environment variables (`DataTransfer` and `LoadXMLData`) that you will use in later tutorial tasks.</span></span>  
  
 <span data-ttu-id="503ed-104">La carpeta de trabajo está en la raíz de la unidad C.</span><span class="sxs-lookup"><span data-stu-id="503ed-104">The working folder is at the root of the C drive.</span></span> <span data-ttu-id="503ed-105">Si debe usar otra unidad o ubicación, puede hacerlo.</span><span class="sxs-lookup"><span data-stu-id="503ed-105">If you must use a different drive or location, you can do that.</span></span> <span data-ttu-id="503ed-106">No obstante, deberá anotar esta ubicación y usarla siempre que el tutorial haga referencia a la ubicación de la carpeta de trabajo DeploymentTutorial.</span><span class="sxs-lookup"><span data-stu-id="503ed-106">However, you need to note this location and then use it wherever the tutorial refers to the location of the DeploymentTutorial working folder.</span></span>  
  
 <span data-ttu-id="503ed-107">En una lección posterior implementará paquetes que están guardados en el sistema de archivos en la tabla sysssispackages de la base de datos msdb de[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="503ed-107">In a later lesson, you will deploy packages that are saved to the file system to the sysssispackages table in the msdb[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="503ed-108">Lo ideal es que implemente los paquetes de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] en otro equipo.</span><span class="sxs-lookup"><span data-stu-id="503ed-108">Ideally you will deploy the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages to a different computer.</span></span> <span data-ttu-id="503ed-109">Si no es posible, puede aprender a hacerlo en este tutorial si implementa los paquetes en una instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que se encuentre en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="503ed-109">If that is not possible, you can still learn a lot from doing this tutorial by deploying the packages to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that is on the local computer.</span></span> <span data-ttu-id="503ed-110">Las variables de entorno que se utilizan en el equipo local y de destino tienen los mismos nombres de variable, pero diferentes valores almacenados.</span><span class="sxs-lookup"><span data-stu-id="503ed-110">The environment variables that are used on the local and destination computers have the same variable names, but different values are stored in the variables.</span></span> <span data-ttu-id="503ed-111">Por ejemplo, en el equipo local, el valor de la variable de entorno `DataTransfer` hace referencia a la carpeta C:\DeploymentTutorial, mientras que en el equipo de destino la variable de entorno `DataTransfer` hace referencia a la carpeta C:\DeploymentTutorialInstall.</span><span class="sxs-lookup"><span data-stu-id="503ed-111">For example, on the local computer, the value of the environment variable `DataTransfer` references the C:\DeploymentTutorial folder, whereas on the target computer the environment variable `DataTransfer` references the C:\DeploymentTutorialInstall folder.</span></span>  
  
 <span data-ttu-id="503ed-112">Si planea realizar una implementación en el equipo local, solamente necesita crear un conjunto de variables de entorno; no obstante, deberá actualizar el valor de las variables de entorno en un valor apropiado antes de realizar la implementación local.</span><span class="sxs-lookup"><span data-stu-id="503ed-112">If you plan to deploy to the local computer, you need to create only one set of environment variables; however, you will need to update the value of the environment variables to an appropriate value before you do the local deployment.</span></span>  
  
 <span data-ttu-id="503ed-113">Si planea implementar los paquetes en otro equipo, debe crear dos conjuntos de variables de entorno: un conjunto para el equipo local y otro para el equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="503ed-113">If you plan to deploy the packages to a different computer, you must create two sets of environment variables: one set for the local computer, and one set for the destination computer.</span></span> <span data-ttu-id="503ed-114">Ahora solamente puede crear las variables para el equipo de origen y, más tarde, crear las variables para el equipo de destino, pero debe tener la carpeta y las variables de entorno disponibles en el equipo de destino antes de poder instalar los paquetes en ese equipo.</span><span class="sxs-lookup"><span data-stu-id="503ed-114">You can create only the variables for the source computer now, and create the variables for the destination computer later, but you must have both the folder and environment variables available on the destination computer before you can install the packages on that computer.</span></span>  
  
### <a name="to-create-the-local-working-folder"></a><span data-ttu-id="503ed-115">Para crear la carpeta de trabajo local</span><span class="sxs-lookup"><span data-stu-id="503ed-115">To create the local working folder</span></span>  
  
1.  <span data-ttu-id="503ed-116">Haga clic con el botón secundario en el menú Inicio y haga clic en Explorar.</span><span class="sxs-lookup"><span data-stu-id="503ed-116">Right-click the Start menu, and click Explore.</span></span>  
  
2.  <span data-ttu-id="503ed-117">Haga clic en **Disco local (C:)** .</span><span class="sxs-lookup"><span data-stu-id="503ed-117">Click **Local Disk (C:)**.</span></span>  
  
3.  <span data-ttu-id="503ed-118">En el menú **Archivo** , seleccione **Nuevo**y haga clic en **Carpeta**.</span><span class="sxs-lookup"><span data-stu-id="503ed-118">On the **File** menu, point to **New**, and then click **Folder**.</span></span>  
  
4.  <span data-ttu-id="503ed-119">Cambie el nombre de la nueva carpeta a `DeploymentTutorial` .</span><span class="sxs-lookup"><span data-stu-id="503ed-119">Rename New Folder to `DeploymentTutorial`.</span></span>  
  
### <a name="to-create-local-environment-variables"></a><span data-ttu-id="503ed-120">Para crear variables del entorno local</span><span class="sxs-lookup"><span data-stu-id="503ed-120">To create local environment variables</span></span>  
  
1.  <span data-ttu-id="503ed-121">En el menú **Inicio** , haga clic en **Panel de control**.</span><span class="sxs-lookup"><span data-stu-id="503ed-121">On the **Start** menu, click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="503ed-122">En el Panel de control, haga doble clic en **Sistema**.</span><span class="sxs-lookup"><span data-stu-id="503ed-122">In Control Panel, double-click **System**.</span></span>  
  
3.  <span data-ttu-id="503ed-123">En el cuadro de diálogo **Propiedades del sistema** , haga clic en la pestaña **Opciones avanzadas** y, a continuación, haga clic en **Variables de entorno**.</span><span class="sxs-lookup"><span data-stu-id="503ed-123">In the **System Properties** dialog box, click the **Advanced** tab, and then click **Environment Variables**.</span></span>  
  
4.  <span data-ttu-id="503ed-124">En el cuadro de diálogo **Variables de entorno** , en el marco **Variables del sistema** , haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="503ed-124">In the **Environment Variables** dialog box, in the **System variables** frame, click **New**.</span></span>  
  
5.  <span data-ttu-id="503ed-125">En el cuadro de diálogo **nueva variable del sistema** , escriba `DataTransfer` en el cuadro **nombre de variable** y, `C:\DeploymentTutorial\datatransferconfig.dtsconfig` en el cuadro **valor de variable** .</span><span class="sxs-lookup"><span data-stu-id="503ed-125">In the **New System Variable** dialog box, type `DataTransfer` in the **Variable name** box, and `C:\DeploymentTutorial\datatransferconfig.dtsconfig` in the **Variable value** box.</span></span>  
  
6.  <span data-ttu-id="503ed-126">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="503ed-126">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="503ed-127">Vuelva a hacer clic en **nuevo** y escriba `LoadXMLData` en el cuadro **nombre de variable** y `C:\DeploymentTutorial\loadxmldataconfig.dtsconfig` en el cuadro **valor de variable** .</span><span class="sxs-lookup"><span data-stu-id="503ed-127">Click **New** again, and type `LoadXMLData` in the **Variable name** box, and `C:\DeploymentTutorial\loadxmldataconfig.dtsconfig` in the **Variable value** box.</span></span>  
  
8.  <span data-ttu-id="503ed-128">Haga clic en **Aceptar** para salir del cuadro de diálogo **Variables de entorno** .</span><span class="sxs-lookup"><span data-stu-id="503ed-128">Click **OK** to exit the **Environment Variables** dialog box.</span></span>  
  
9. <span data-ttu-id="503ed-129">Haga clic en **Aceptar** para salir del cuadro de diálogo **Propiedades del sistema** .</span><span class="sxs-lookup"><span data-stu-id="503ed-129">Click **OK** to exit the **System Properties** dialog box.</span></span>\  
  
10. <span data-ttu-id="503ed-130">Opcionalmente, reinicie el equipo.</span><span class="sxs-lookup"><span data-stu-id="503ed-130">Optionally, restart your computer.</span></span> <span data-ttu-id="503ed-131">Si no reinicia el equipo, el nombre de la nueva variable no se mostrará en el Asistente para la configuración de paquetes, pero podrá usarla.</span><span class="sxs-lookup"><span data-stu-id="503ed-131">If you do not restart the computer, the name of the new variable will not be displayed in the Package Configuration Wizard, but you can still use it.</span></span>  
  
### <a name="to-create-destination-environment-variables"></a><span data-ttu-id="503ed-132">Para crear variables del entorno de destino</span><span class="sxs-lookup"><span data-stu-id="503ed-132">To create destination environment variables</span></span>  
  
1.  <span data-ttu-id="503ed-133">En el menú **Inicio** , haga clic en **Panel de control**.</span><span class="sxs-lookup"><span data-stu-id="503ed-133">On the **Start** menu, click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="503ed-134">En el Panel de control, haga doble clic en **Sistema**.</span><span class="sxs-lookup"><span data-stu-id="503ed-134">In Control Panel, double-click **System**.</span></span>  
  
3.  <span data-ttu-id="503ed-135">En el cuadro de diálogo **Propiedades del sistema** , haga clic en la pestaña **Opciones avanzadas** y, a continuación, haga clic en **Variables de entorno**.</span><span class="sxs-lookup"><span data-stu-id="503ed-135">In the **System Properties** dialog box, click the **Advanced** tab, and then click **Environment Variables**.</span></span>  
  
4.  <span data-ttu-id="503ed-136">En el cuadro de diálogo **Variables de entorno** , en el marco **Variables del sistema** , haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="503ed-136">In the **Environment Variables** dialog box, in **System variables** frame, click **New**.</span></span>  
  
5.  <span data-ttu-id="503ed-137">En el cuadro de diálogo **nuevas variables del sistema** , escriba `DataTransfer` en el cuadro **nombre de variable** y, `C:\DeploymentTutorialInstall\datatransferconfig.dtsconfig` en el cuadro **valor de variable** .</span><span class="sxs-lookup"><span data-stu-id="503ed-137">In the **New System Variables** dialog box, type `DataTransfer` in the **Variable name** box, and `C:\DeploymentTutorialInstall\datatransferconfig.dtsconfig` in the **Variable value** box.</span></span>  
  
6.  <span data-ttu-id="503ed-138">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="503ed-138">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="503ed-139">Vuelva a hacer clic en **nuevo** y escriba `LoadXMLData` en el cuadro **nombre de variable** y `C:\DeploymentTutorialInstall\loadxmldataconfig.dtsconfig` en el cuadro **valor de variable** .</span><span class="sxs-lookup"><span data-stu-id="503ed-139">Click **New** again, and type `LoadXMLData` in the **Variable name** box, and `C:\DeploymentTutorialInstall\loadxmldataconfig.dtsconfig` in the **Variable value** box.</span></span>  
  
8.  <span data-ttu-id="503ed-140">Haga clic en **Aceptar** para salir del cuadro de diálogo **Variables de entorno** .</span><span class="sxs-lookup"><span data-stu-id="503ed-140">Click **OK** to exit the **Environment Variables** dialog box.</span></span>  
  
9. <span data-ttu-id="503ed-141">Haga clic en **Aceptar** para salir del cuadro de diálogo **Propiedades del sistema** .</span><span class="sxs-lookup"><span data-stu-id="503ed-141">Click **OK** to exit the **System Properties** dialog box.</span></span>\  
  
10. <span data-ttu-id="503ed-142">Opcionalmente, reinicie el equipo.</span><span class="sxs-lookup"><span data-stu-id="503ed-142">Optionally, restart your computer.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="503ed-143">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="503ed-143">Next Task in Lesson</span></span>  
 [<span data-ttu-id="503ed-144">Paso 2: Crear el proyecto de implementación</span><span class="sxs-lookup"><span data-stu-id="503ed-144">Step 2: Creating the Deployment Project</span></span>](../integration-services/lesson-1-2-creating-the-deployment-project.md)  
  
<span data-ttu-id="503ed-145">![Integration Services icono (pequeño)](media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="503ed-145">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="503ed-146">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="503ed-146">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="503ed-147">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="503ed-147">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="503ed-148">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="503ed-148">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
