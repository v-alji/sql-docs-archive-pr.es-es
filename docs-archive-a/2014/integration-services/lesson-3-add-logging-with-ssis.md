---
title: 'Lección 3: agregar registro | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 64cd24cc-ba8e-4bd7-b10b-6b80d8b04af6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 58fcc29759f19ad215a76a1b9ed9bf313b4c869c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672174"
---
# <a name="lesson-3-adding-logging"></a><span data-ttu-id="f9af8-102">Lección 3: Adición de registro</span><span class="sxs-lookup"><span data-stu-id="f9af8-102">Lesson 3: Adding Logging</span></span>
  [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="f9af8-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] incluye características de registro que permiten supervisar y solucionar los problemas de ejecución de paquetes mediante el seguimiento de eventos de tarea y de contenedor.</span><span class="sxs-lookup"><span data-stu-id="f9af8-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] includes logging features that let you troubleshoot and monitor package execution by providing a trace of task and container events.</span></span> <span data-ttu-id="f9af8-104">La características de registro son flexibles, pueden habilitarse en el nivel de paquete o en tareas y contendores individuales del paquete.</span><span class="sxs-lookup"><span data-stu-id="f9af8-104">The logging features are flexible, and can be enabled at the package level or on individual tasks and containers within the package.</span></span> <span data-ttu-id="f9af8-105">Puede seleccionar qué eventos deben registrarse y crear varios registros para un único paquete.</span><span class="sxs-lookup"><span data-stu-id="f9af8-105">You can select which events you want to log, and create multiple logs against a single package.</span></span>  
  
 <span data-ttu-id="f9af8-106">El registro lo proporciona un proveedor de registro.</span><span class="sxs-lookup"><span data-stu-id="f9af8-106">Logging is provided by a log provider.</span></span> <span data-ttu-id="f9af8-107">Cada proveedor de registro puede escribir información de registro en distintos formatos y tipos de destino.</span><span class="sxs-lookup"><span data-stu-id="f9af8-107">Each log provider can write logging information to different formats and destination types.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="f9af8-108">proporciona los siguientes proveedores de registro:</span><span class="sxs-lookup"><span data-stu-id="f9af8-108">provides the following log providers:</span></span>  
  
-   <span data-ttu-id="f9af8-109">Archivo de texto</span><span class="sxs-lookup"><span data-stu-id="f9af8-109">Text file</span></span>  
  
-   [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)]  
  
-   <span data-ttu-id="f9af8-110">Registro de eventos de Windows</span><span class="sxs-lookup"><span data-stu-id="f9af8-110">Windows Event log</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]  
  
-   <span data-ttu-id="f9af8-111">Archivo XML</span><span class="sxs-lookup"><span data-stu-id="f9af8-111">XML file</span></span>  
  
 <span data-ttu-id="f9af8-112">En esta lección, creará una copia del paquete que creó en la [Lección 2: agregar bucles](lesson-2-adding-looping-with-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="f9af8-112">In this lesson, you will create a copy of the package that you created in [Lesson 2: Adding Looping](lesson-2-adding-looping-with-ssis.md).</span></span> <span data-ttu-id="f9af8-113">Utilizando este nuevo paquete, luego agregará y configurará el registro para supervisar eventos específicos durante la ejecución del paquete.</span><span class="sxs-lookup"><span data-stu-id="f9af8-113">Working with this new package, you will then add and configure logging to monitor specific events during package execution.</span></span> <span data-ttu-id="f9af8-114">Si no ha finalizado cualquiera de las lecciones anteriores, también puede copiar el paquete de la lección 2 finalizada incluido en el tutorial.</span><span class="sxs-lookup"><span data-stu-id="f9af8-114">If you have not completed any of the previous lessons, you can also copy the completed Lesson 2 package that is included with the tutorial.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f9af8-115">Para este tutorial, se necesita la base de datos de ejemplo **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="f9af8-115">This tutorial requires the **AdventureWorksDW2012** sample database.</span></span> <span data-ttu-id="f9af8-116">Para obtener más información sobre cómo instalar e implementar **AdventureWorksDW2012**, [Reporting Services ejemplos de productos en github](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span><span class="sxs-lookup"><span data-stu-id="f9af8-116">For more information about how to install and deploy **AdventureWorksDW2012**, [Reporting Services Product Samples on GitHub](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="f9af8-117">Tareas de la lección</span><span class="sxs-lookup"><span data-stu-id="f9af8-117">Lesson Tasks</span></span>  
 <span data-ttu-id="f9af8-118">Esta lección contiene las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="f9af8-118">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="f9af8-119">Paso 1: Copia del paquete de la lección 2</span><span class="sxs-lookup"><span data-stu-id="f9af8-119">Step 1: Copying the Lesson 2 Package</span></span>](lesson-3-1-copying-the-lesson-2-package.md)  
  
-   [<span data-ttu-id="f9af8-120">Paso 2: Adición y configuración de registro</span><span class="sxs-lookup"><span data-stu-id="f9af8-120">Step 2: Adding and Configuring Logging</span></span>](lesson-3-2-adding-and-configuring-logging.md)  
  
-   [<span data-ttu-id="f9af8-121">Paso 3: Prueba del paquete del tutorial de la lección 3</span><span class="sxs-lookup"><span data-stu-id="f9af8-121">Step 3: Testing the Lesson 3 Tutorial Package</span></span>](../integration-services/lesson-3-3-testing-the-lesson-3-tutorial-package.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="f9af8-122">Iniciar la lección</span><span class="sxs-lookup"><span data-stu-id="f9af8-122">Start the Lesson</span></span>  
 [<span data-ttu-id="f9af8-123">Paso 1: Copia del paquete de la lección 2</span><span class="sxs-lookup"><span data-stu-id="f9af8-123">Step 1: Copying the Lesson 2 Package</span></span>](lesson-3-1-copying-the-lesson-2-package.md)  
  
  
