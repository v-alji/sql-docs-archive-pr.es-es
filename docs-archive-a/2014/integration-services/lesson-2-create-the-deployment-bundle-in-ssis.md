---
title: 'Lección 2: crear el paquete de implementación | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: ab17289d-c3d4-4a5e-b7f5-4fea8ae21707
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 927bcd393e4b54e92971c197d93dcc1e2804dcd8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674899"
---
# <a name="lesson-2-creating-the-deployment-bundle"></a><span data-ttu-id="25178-102">Lección 2: Creación del paquete de implementación</span><span class="sxs-lookup"><span data-stu-id="25178-102">Lesson 2: Creating the Deployment Bundle</span></span>
  <span data-ttu-id="25178-103">En la [Lección 1: Preparar la creación del paquete de implementación](../integration-services/lesson-1-preparing-to-create-the-deployment-bundle.md), ha creado el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] denominado Deployment Tutorial, ha agregado paquetes y archivos auxiliares al proyecto y ha implementado configuraciones en paquetes.</span><span class="sxs-lookup"><span data-stu-id="25178-103">In [Lesson 1: Preparing to Create the Deployment Bundle](../integration-services/lesson-1-preparing-to-create-the-deployment-bundle.md), you created the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project named Deployment Tutorial, added the packages and supporting files to the project, and implemented configurations in packages.</span></span>  
  
 <span data-ttu-id="25178-104">En esta lección, creará el paquete de implementación, que es una carpeta que contiene los elementos que necesita para instalar paquetes en otro equipo.</span><span class="sxs-lookup"><span data-stu-id="25178-104">In this lesson, you will create the deployment bundle, which is a folder that contains the items that you need to install packages on another computer.</span></span> <span data-ttu-id="25178-105">El paquete de implementación incluirá un manifiesto de implementación, copias de los paquetes y copias de los archivos auxiliares del proyecto Deployment Tutorial.</span><span class="sxs-lookup"><span data-stu-id="25178-105">The deployment bundle will include a deployment manifest, copies of the packages, and copies of the supporting files from the Deployment Tutorial project.</span></span> <span data-ttu-id="25178-106">El manifiesto de implementación enumera los paquetes, varios archivos y configuraciones en el paquete de implementación.</span><span class="sxs-lookup"><span data-stu-id="25178-106">The deployment manifest lists the packages, miscellaneous files, and configurations in the deployment bundle.</span></span>  
  
 <span data-ttu-id="25178-107">También comprobará la lista de archivos del paquete de implementación y examinará el contenido del manifiesto.</span><span class="sxs-lookup"><span data-stu-id="25178-107">You will also verify the file list in the deployment bundle and examine the contents of the manifest.</span></span>  
  
 <span data-ttu-id="25178-108">**Tiempo estimado para completar esta lección** : 30 minutos</span><span class="sxs-lookup"><span data-stu-id="25178-108">**Estimated time to complete this lesson:** 30 minutes</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="25178-109">Tareas de la lección</span><span class="sxs-lookup"><span data-stu-id="25178-109">Lesson Tasks</span></span>  
 <span data-ttu-id="25178-110">Esta lección contiene las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="25178-110">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="25178-111">Paso 1: Generar la utilidad de implementación</span><span class="sxs-lookup"><span data-stu-id="25178-111">Step 1: Building the Deployment Utility</span></span>](../integration-services/lesson-2-1-building-the-deployment-utility.md)  
  
-   [<span data-ttu-id="25178-112">Paso 2: Comprobar el paquete de implementación</span><span class="sxs-lookup"><span data-stu-id="25178-112">Step 2: Verifying the Deployment Bundle</span></span>](../integration-services/lesson-2-2-verifying-the-deployment-bundle.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="25178-113">Iniciar la lección</span><span class="sxs-lookup"><span data-stu-id="25178-113">Start the Lesson</span></span>  
 [<span data-ttu-id="25178-114">Paso 1: Generar la utilidad de implementación</span><span class="sxs-lookup"><span data-stu-id="25178-114">Step 1: Building the Deployment Utility</span></span>](../integration-services/lesson-2-1-building-the-deployment-utility.md)  
  
<span data-ttu-id="25178-115">![Integration Services icono (pequeño)](media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="25178-115">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="25178-116">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="25178-116">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="25178-117">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="25178-117">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="25178-118">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="25178-118">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
