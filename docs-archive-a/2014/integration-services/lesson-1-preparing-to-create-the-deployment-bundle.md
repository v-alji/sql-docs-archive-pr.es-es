---
title: 'Lección 1: Preparar la creación del conjunto de implementación | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: b6fe283c-9856-4ba1-a497-e3912424fd18
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0deda2a81ddd86d4e40c1c546232b8056264508a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673113"
---
# <a name="lesson-1-preparing-to-create-the-deployment-bundle"></a><span data-ttu-id="a328e-102">Lección 1: Preparar la creación del paquete de implementación</span><span class="sxs-lookup"><span data-stu-id="a328e-102">Lesson 1: Preparing to Create the Deployment Bundle</span></span>
  <span data-ttu-id="a328e-103">En esta lección, creará las carpetas de trabajo y la variables de entorno que admiten el tutorial, creará un proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , agregará varios paquetes y sus archivos auxiliares al proyecto e implementará las configuraciones en los paquetes.</span><span class="sxs-lookup"><span data-stu-id="a328e-103">In this lesson, you will create the working folders and environment variables that support the tutorial, create an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, add several packages and their supporting files to the project, and implement configurations in packages.</span></span>  
  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="a328e-104">implementa paquetes según un proyecto; por tanto, en el primer paso de la creación del paquete de implementación, debe recopilar todos los paquetes y sus dependencias en un proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a328e-104">deploys packages on a project basis; therefore, as the first step in creating the deployment bundle, you must collect all the packages and package dependencies into one [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span> <span data-ttu-id="a328e-105">En muchas ocasiones, esto es útil para incluir otra información con los paquetes implementados: por ejemplo, también agregará un archivo Léame al proyecto que proporcione la documentación básica de este grupo de paquetes.</span><span class="sxs-lookup"><span data-stu-id="a328e-105">Frequently it is useful to include other information with the deployed packages: for example you will also add to the project a Readme file that provides basic documentation for this group of packages.</span></span>  
  
 <span data-ttu-id="a328e-106">Después de agregar los paquetes y archivos, agregará configuraciones a los paquetes que todavía no usan configuraciones.</span><span class="sxs-lookup"><span data-stu-id="a328e-106">After you have added the packages and files, you will add configurations to packages that do not already use configurations.</span></span> <span data-ttu-id="a328e-107">Las configuraciones actualizan las propiedades de los paquetes y los objetos de paquete en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a328e-107">The configurations update properties of packages and package objects at run time.</span></span> <span data-ttu-id="a328e-108">En una lección posterior, modificará los valores de estas configuraciones durante la implementación de paquetes para que admitan los paquetes en el entorno implementado.</span><span class="sxs-lookup"><span data-stu-id="a328e-108">In a later lesson, you will modify the values of these configurations during package deployment to support the packages in the deployed-to environment.</span></span>  
  
 <span data-ttu-id="a328e-109">Después de agregar estas configuraciones, debe abrir los paquetes en el Diseñador de [!INCLUDE[ssIS](../includes/ssis-md.md)] , la herramienta gráfica de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] para generar paquetes ETL, y examinar las propiedades de los paquetes y sus elementos, así como las configuraciones de paquetes para entender mejor los problemas que la implementación de paquetes debe controlar.</span><span class="sxs-lookup"><span data-stu-id="a328e-109">After you have added the configurations, you should open the packages in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] graphical tool for building ETL packages, and examine the properties of packages and package elements as well as the package configurations to better understand the issues that the deployment needs to address.</span></span> <span data-ttu-id="a328e-110">Por ejemplo, uno de los paquetes extrae datos de archivos de texto, por lo que la ubicación de los archivos de datos debe actualizarse antes de que se ejecuten correctamente los paquetes implementados.</span><span class="sxs-lookup"><span data-stu-id="a328e-110">For example, one of the packages extracts data from text files, so the location of the data files must be updated before the deployed packages will run successfully.</span></span>  
  
 <span data-ttu-id="a328e-111">**Tiempo estimado para completar esta lección:** 1 hora</span><span class="sxs-lookup"><span data-stu-id="a328e-111">**Estimated time to complete this lesson:** 1 hour</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="a328e-112">Tareas de la lección</span><span class="sxs-lookup"><span data-stu-id="a328e-112">Lesson Tasks</span></span>  
 <span data-ttu-id="a328e-113">Esta lección contiene las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="a328e-113">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="a328e-114">Paso 1: Crear carpetas de trabajo y variables de entorno</span><span class="sxs-lookup"><span data-stu-id="a328e-114">Step 1: Creating Working Folders and Environment Variables</span></span>](../integration-services/lesson-1-1-creating-working-folders-and-environment-variables.md)  
  
-   [<span data-ttu-id="a328e-115">Paso 2: Crear el proyecto de implementación</span><span class="sxs-lookup"><span data-stu-id="a328e-115">Step 2: Creating the Deployment Project</span></span>](../integration-services/lesson-1-2-creating-the-deployment-project.md)  
  
-   [<span data-ttu-id="a328e-116">Paso 3: Agregar paquetes y otros archivos</span><span class="sxs-lookup"><span data-stu-id="a328e-116">Step 3: Adding Packages and Other Files</span></span>](../integration-services/lesson-1-3-adding-packages-and-other-files.md)  
  
-   [<span data-ttu-id="a328e-117">Paso 4: Agregar configuraciones de paquetes</span><span class="sxs-lookup"><span data-stu-id="a328e-117">Step 4: Adding Package Configurations</span></span>](../integration-services/lesson-1-4-adding-package-configurations.md)  
  
-   [<span data-ttu-id="a328e-118">Paso 5: Probar los paquetes actualizados</span><span class="sxs-lookup"><span data-stu-id="a328e-118">Step 5: Testing the Updated Packages</span></span>](../integration-services/lesson-1-5-testing-the-updated-packages.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="a328e-119">Iniciar la lección</span><span class="sxs-lookup"><span data-stu-id="a328e-119">Start the Lesson</span></span>  
 [<span data-ttu-id="a328e-120">Paso 1: Crear carpetas de trabajo y variables de entorno</span><span class="sxs-lookup"><span data-stu-id="a328e-120">Step 1: Creating Working Folders and Environment Variables</span></span>](../integration-services/lesson-1-1-creating-working-folders-and-environment-variables.md)  
  
<span data-ttu-id="a328e-121">![Integration Services icono (pequeño)](media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="a328e-121">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="a328e-122">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="a328e-122">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="a328e-123">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="a328e-123">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="a328e-124">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="a328e-124">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
