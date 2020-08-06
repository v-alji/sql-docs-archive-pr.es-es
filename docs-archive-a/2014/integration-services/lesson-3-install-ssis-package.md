---
title: 'Lección 3: instalar paquetes | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 87bc4d82-39d8-424f-886f-98cf1e4bb07a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9f8b58cee7bd8e16cd0ca2e726dc8e5eff2cfec5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672173"
---
# <a name="lesson-3-installing-packages"></a><span data-ttu-id="feef9-102">Lección 3: Instalar paquetes</span><span class="sxs-lookup"><span data-stu-id="feef9-102">Lesson 3: Installing Packages</span></span>
  <span data-ttu-id="feef9-103">En [la lección 2: crear el paquete de implementación](../integration-services/lesson-2-create-the-deployment-bundle-in-ssis.md), ha creado una utilidad de implementación y ha creado el paquete de implementación que contiene los elementos en los que debe instalar paquetes en otro equipo.</span><span class="sxs-lookup"><span data-stu-id="feef9-103">In [Lesson 2: Creating the Deployment Bundle](../integration-services/lesson-2-create-the-deployment-bundle-in-ssis.md), you built a deployment utility and created the deployment bundle that contains the items that you must install packages on another computer.</span></span> <span data-ttu-id="feef9-104">También ha comprobado la lista de archivos en el paquete de implementación y ha examinado el contenido del archivo de manifiesto que se creó al generar la utilidad de implementación.</span><span class="sxs-lookup"><span data-stu-id="feef9-104">You also verified the file list in the deployment bundle and examined the contents of the manifest file that was created when you built the deployment utility.</span></span>  
  
 <span data-ttu-id="feef9-105">En esta lección, copiará el paquete de implementación en el equipo de destino y, a continuación, ejecutará el Asistente para la instalación de paquetes para instalar los paquetes, sus dependencias y los archivos auxiliares en ese equipo.</span><span class="sxs-lookup"><span data-stu-id="feef9-105">In this lesson, you will copy the deployment bundle to the destination computer and then run the Package Installation Wizard to install the packages, package dependencies, and ancillary files on that computer.</span></span> <span data-ttu-id="feef9-106">Los paquetes se instalarán en la **msdb** [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] base de datos msdb y los demás elementos se instalarán en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="feef9-106">The packages will be installed in the **msdb**[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database and the other items will be installed in the file system.</span></span> <span data-ttu-id="feef9-107">Después de completar la instalación de los paquetes, para probar la implementación, ejecutará los paquetes desde [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] con la Utilidad de ejecución de paquetes.</span><span class="sxs-lookup"><span data-stu-id="feef9-107">After you complete the package installation, you will test the deployment by running the packages from [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] using the Execute Package Utility.</span></span>  
  
 <span data-ttu-id="feef9-108">**Tiempo estimado para completar esta lección** : 30 minutos</span><span class="sxs-lookup"><span data-stu-id="feef9-108">**Estimated time to complete this lesson:** 30 minutes</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="feef9-109">Tareas de la lección</span><span class="sxs-lookup"><span data-stu-id="feef9-109">Lesson Tasks</span></span>  
 <span data-ttu-id="feef9-110">Esta lección contiene las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="feef9-110">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="feef9-111">Paso 1: Copia del paquete de implementación</span><span class="sxs-lookup"><span data-stu-id="feef9-111">Step 1: Copying the Deployment Bundle</span></span>](../integration-services/lesson-3-1-copying-the-deployment-bundle.md)  
  
-   [<span data-ttu-id="feef9-112">Paso 2: Ejecución del Asistente para la instalación de paquetes</span><span class="sxs-lookup"><span data-stu-id="feef9-112">Step 2: Running the Package Installation Wizard</span></span>](../integration-services/lesson-3-2-running-the-package-installation-wizard.md)  
  
-   [<span data-ttu-id="feef9-113">Paso 3: Prueba de los paquetes implementados</span><span class="sxs-lookup"><span data-stu-id="feef9-113">Step 3: Testing the Deployed Packages</span></span>](../integration-services/lesson-3-3-testing-the-deployed-packages.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="feef9-114">Iniciar la lección</span><span class="sxs-lookup"><span data-stu-id="feef9-114">Start the Lesson</span></span>  
 [<span data-ttu-id="feef9-115">Paso 1: Copia del paquete de implementación</span><span class="sxs-lookup"><span data-stu-id="feef9-115">Step 1: Copying the Deployment Bundle</span></span>](../integration-services/lesson-3-1-copying-the-deployment-bundle.md)  
  
<span data-ttu-id="feef9-116">![Integration Services icono (pequeño)](media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="feef9-116">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="feef9-117">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="feef9-117">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="feef9-118">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="feef9-118">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="feef9-119">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="feef9-119">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
