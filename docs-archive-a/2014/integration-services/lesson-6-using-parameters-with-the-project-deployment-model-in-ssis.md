---
title: 'Lección 6: usar parámetros con el modelo de implementación de proyectos | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 9216f18c-1762-4f2d-8c22-bd0ab7107555
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4bdc6b9dfc019822d6cf1bd9ec7d89ffcc5ea5e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670427"
---
# <a name="lesson-6-using-parameters-with-the-project-deployment-model"></a><span data-ttu-id="b8ba6-102">Lección 6: Uso de parámetros con el modelo de implementación de proyectos</span><span class="sxs-lookup"><span data-stu-id="b8ba6-102">Lesson 6: Using Parameters with the Project Deployment Model</span></span>
  <span data-ttu-id="b8ba6-103">SQL Server 2012 presenta un nuevo modelo de implementación en el que puede implementar sus proyectos en el servidor de Integration Services.</span><span class="sxs-lookup"><span data-stu-id="b8ba6-103">SQL Server 2012 introduces a new deployment model where you can deploy your projects to the Integration Services server.</span></span> <span data-ttu-id="b8ba6-104">El servidor de Integration Services permite administrar y ejecutar paquetes, así como configurar valores en tiempo de ejecución para los paquetes.</span><span class="sxs-lookup"><span data-stu-id="b8ba6-104">The Integration Services server enables you to manage and run packages, and to configure runtime values for packages.</span></span>  
  
 <span data-ttu-id="b8ba6-105">En esta lección, modificará el paquete que creó en la [Lección 5: agregar configuraciones de paquetes para el modelo de implementación de paquetes](lesson-5-add-ssis-package-configurations-for-the-package-deployment-model.md) para usar el modelo de implementación de proyectos.</span><span class="sxs-lookup"><span data-stu-id="b8ba6-105">In this lesson, you will modify the package that you created in [Lesson 5: Adding Package Configurations for the Package Deployment Model](lesson-5-add-ssis-package-configurations-for-the-package-deployment-model.md) to use the Project Deployment Model.</span></span> <span data-ttu-id="b8ba6-106">Reemplazará el valor de configuración con un parámetro para especificar la ubicación de los datos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b8ba6-106">You replace the configuration value with a parameter to specify the sample data location.</span></span> <span data-ttu-id="b8ba6-107">También puede copiar el paquete de la lección 5 completada que se incluye con el tutorial.</span><span class="sxs-lookup"><span data-stu-id="b8ba6-107">You can also copy the completed Lesson 5 package that is included with the tutorial.</span></span>  
  
 <span data-ttu-id="b8ba6-108">Con el Asistente para la conversión de proyectos de Integration Services, convertirá el proyecto al modelo de implementación de proyectos y usará un parámetro en lugar de un valor de configuración para establecer la propiedad Directory.</span><span class="sxs-lookup"><span data-stu-id="b8ba6-108">Using the Integration Services Project Configuration Wizard, you will convert the project to the Project Deployment Model and use a Parameter rather than a configuration value to set the Directory property.</span></span> <span data-ttu-id="b8ba6-109">Esta lección abarca parcialmente los pasos que se seguiría para convertir paquetes SSIS existentes al nuevo modelo de implementación de proyectos.</span><span class="sxs-lookup"><span data-stu-id="b8ba6-109">This lesson partially covers the steps you would follow to convert existing SSIS packages to the new Project Deployment Model.</span></span>  
  
 <span data-ttu-id="b8ba6-110">Cuando ejecute el paquete de nuevo, el servicio Integration Services usará el parámetro para rellenar el valor de la variable y la variable actualizará a su vez la propiedad Directory.</span><span class="sxs-lookup"><span data-stu-id="b8ba6-110">When you run the package again, the Integration Services service uses the parameter to populate the value of the variable, and the variable in turn updates the Directory property.</span></span> <span data-ttu-id="b8ba6-111">Como resultado, el paquete iterará por los archivos de la nueva carpeta de datos especificada por el valor del parámetro, en lugar de iterar por la carpeta que se estableció en el archivo de configuración del paquete.</span><span class="sxs-lookup"><span data-stu-id="b8ba6-111">As a result, the package iterates through the files in the new data folder specified by the parameter value rather than the folder that was set in the package configuration file.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b8ba6-112">Para este tutorial, se necesita la base de datos de ejemplo **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="b8ba6-112">This tutorial requires the **AdventureWorksDW2012** sample database.</span></span> <span data-ttu-id="b8ba6-113">Para obtener más información sobre cómo instalar e implementar **AdventureWorksDW2012**, consulte [Considerations for Installing SQL Server Samples and Sample Databases](https://technet.microsoft.com/library/ms161556%28v=sql.105%29)(Consideraciones para instalar ejemplos y bases de datos de ejemplo de SQL Server).</span><span class="sxs-lookup"><span data-stu-id="b8ba6-113">For more information about how to install and deploy **AdventureWorksDW2012**, see [Considerations for Installing SQL Server Samples and Sample Databases](https://technet.microsoft.com/library/ms161556%28v=sql.105%29).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="b8ba6-114">Tareas de la lección</span><span class="sxs-lookup"><span data-stu-id="b8ba6-114">Lesson Tasks</span></span>  
 <span data-ttu-id="b8ba6-115">Esta lección contiene las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="b8ba6-115">This lesson contains the following tasks:</span></span>  
  
1.  [<span data-ttu-id="b8ba6-116">Paso 1: Copia del paquete de la lección 5</span><span class="sxs-lookup"><span data-stu-id="b8ba6-116">Step 1: Copying the Lesson 5 Package</span></span>](lesson-6-1-copying-the-lesson-5-package.md)  
  
2.  [<span data-ttu-id="b8ba6-117">Paso 2: Convertir el proyecto al modelo de implementación del proyectos</span><span class="sxs-lookup"><span data-stu-id="b8ba6-117">Step 2: Converting the Project to the Project Deployment Model</span></span>](lesson-6-2-converting-the-project-to-the-project-deployment-model.md)  
  
3.  [<span data-ttu-id="b8ba6-118">Paso 3: Prueba del paquete de la lección 6</span><span class="sxs-lookup"><span data-stu-id="b8ba6-118">Step 3: Testing the Lesson 6 Package</span></span>](lesson-6-3-testing-the-lesson-6-package.md)  
  
4.  [<span data-ttu-id="b8ba6-119">Paso 4: Implementación del paquete de la lección 6</span><span class="sxs-lookup"><span data-stu-id="b8ba6-119">Step 4: Deploying the Lesson 6 Package</span></span>](lesson-6-4-deploying-the-lesson-6-package.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="b8ba6-120">Iniciar la lección</span><span class="sxs-lookup"><span data-stu-id="b8ba6-120">Start the Lesson</span></span>  
 [<span data-ttu-id="b8ba6-121">Paso 1: Copia del paquete de la lección 5</span><span class="sxs-lookup"><span data-stu-id="b8ba6-121">Step 1: Copying the Lesson 5 Package</span></span>](lesson-6-1-copying-the-lesson-5-package.md)  
  
  
