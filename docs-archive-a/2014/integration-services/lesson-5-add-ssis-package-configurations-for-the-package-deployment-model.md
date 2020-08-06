---
title: 'Lección 5: agregar configuraciones de paquetes para el modelo de implementación de paquetes | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 1c10dd54-67cb-4b63-9e4d-aa6ff0452ecb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ee03d624ac7144cf6aef0829bcb7835fe5af9c53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744770"
---
# <a name="lesson-5-adding-package-configurations-for-the-package-deployment-model"></a><span data-ttu-id="0f5b7-102">Lección 5: Adición de configuraciones de paquete para el modelo de implementación de paquetes</span><span class="sxs-lookup"><span data-stu-id="0f5b7-102">Lesson 5: Adding Package Configurations for the Package Deployment Model</span></span>
  <span data-ttu-id="0f5b7-103">Las configuraciones de paquetes permiten definir propiedades y variables de tiempo de ejecución desde el exterior del entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="0f5b7-103">Package configurations let you set run-time properties and variables from outside of the development environment.</span></span> <span data-ttu-id="0f5b7-104">Las configuraciones permiten desarrollar paquetes que son flexibles y fáciles de implementar y distribuir.</span><span class="sxs-lookup"><span data-stu-id="0f5b7-104">Configurations allow you to develop packages that are flexible and easy to both deploy and distribute.</span></span> [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="0f5b7-105">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] ofrece los tipos de configuración siguientes:</span><span class="sxs-lookup"><span data-stu-id="0f5b7-105">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] offers the following configuration types:</span></span>  
  
-   <span data-ttu-id="0f5b7-106">Archivo de configuración XML</span><span class="sxs-lookup"><span data-stu-id="0f5b7-106">XML configuration file</span></span>  
  
-   <span data-ttu-id="0f5b7-107">Variable de entorno</span><span class="sxs-lookup"><span data-stu-id="0f5b7-107">Environment variable</span></span>  
  
-   <span data-ttu-id="0f5b7-108">Entrada del Registro</span><span class="sxs-lookup"><span data-stu-id="0f5b7-108">Registry entry</span></span>  
  
-   <span data-ttu-id="0f5b7-109">Variable de paquete primario</span><span class="sxs-lookup"><span data-stu-id="0f5b7-109">Parent package variable</span></span>  
  
-   <span data-ttu-id="0f5b7-110">Tabla [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f5b7-110">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] table</span></span>  
  
 <span data-ttu-id="0f5b7-111">En esta lección, modificará el paquete simple de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que creó en [Lesson 4: Adding Error Flow Redirection](lesson-4-add-error-flow-redirection-with-ssis.md) para usar el modelo de implementación de paquetes y aprovechar las configuraciones de paquetes.</span><span class="sxs-lookup"><span data-stu-id="0f5b7-111">In this lesson, you will modify the simple [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that you created in [Lesson 4: Adding Error Flow Redirection](lesson-4-add-error-flow-redirection-with-ssis.md) to use the Package Deployment Model and take advantage of package configurations.</span></span> <span data-ttu-id="0f5b7-112">También puede copiar el paquete de la lección 4 completada que se incluye con el tutorial.</span><span class="sxs-lookup"><span data-stu-id="0f5b7-112">You can also copy the completed Lesson 4 package that is included with the tutorial.</span></span> <span data-ttu-id="0f5b7-113">Mediante el Asistente para la configuración de paquetes, creará un archivo de configuración XML que actualiza la propiedad `Directory` del contenedor de bucles Foreach utilizando una variable de nivel de paquete asignada a la propiedad Directory.</span><span class="sxs-lookup"><span data-stu-id="0f5b7-113">Using the Package Configuration Wizard, you will create an XML configuration that updates the `Directory` property of the Foreach Loop container by using a package-level variable mapped to the Directory property.</span></span> <span data-ttu-id="0f5b7-114">Una vez que haya creado el archivo de configuración, modificará el valor de la variable desde el exterior del entorno de desarrollo y hará que la propiedad haga referencia a una nueva carpeta de datos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0f5b7-114">Once you have created the configuration file, you will modify the value of the variable from outside of the development environment and point the modified property to a new sample data folder.</span></span> <span data-ttu-id="0f5b7-115">Al ejecutar el paquete de nuevo, el archivo de configuración rellena el valor de la variable y, a su vez, la variable actualiza la `Directory` propiedad.</span><span class="sxs-lookup"><span data-stu-id="0f5b7-115">When you run the package again, the configuration file populates the value of the variable, and the variable in turn updates the `Directory` property.</span></span> <span data-ttu-id="0f5b7-116">Como consecuencia de ello, el paquete se iterará en los archivos de la nueva carpeta de datos, en lugar de iterarse en los archivos de la carpeta original del paquete codificada de forma rígida.</span><span class="sxs-lookup"><span data-stu-id="0f5b7-116">As a result, the package iterates through the files in the new data folder, rather than iterating through the files in the original folder that was hard-coded in the package.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0f5b7-117">Para este tutorial, se necesita la base de datos de ejemplo **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="0f5b7-117">This tutorial requires the **AdventureWorksDW2012** sample database.</span></span> <span data-ttu-id="0f5b7-118">Para obtener más información sobre cómo instalar e implementar **AdventureWorksDW2012**, vea [Ejemplos de productos de Reporting Services en CodePlex](https://go.microsoft.com/fwlink/?LinkID=526910).</span><span class="sxs-lookup"><span data-stu-id="0f5b7-118">For more information about how to install and deploy **AdventureWorksDW2012**, see [Reporting Services Product Samples on CodePlex](https://go.microsoft.com/fwlink/?LinkID=526910).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="0f5b7-119">Tareas de la lección</span><span class="sxs-lookup"><span data-stu-id="0f5b7-119">Lesson Tasks</span></span>  
 <span data-ttu-id="0f5b7-120">Esta lección contiene las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="0f5b7-120">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="0f5b7-121">Paso 1: Copia del paquete de la lección 4</span><span class="sxs-lookup"><span data-stu-id="0f5b7-121">Step 1: Copying the Lesson 4 Package</span></span>](lesson-5-1-copying-the-lesson-4-package.md)  
  
-   [<span data-ttu-id="0f5b7-122">Paso 2: Habilitación y configuración de configuraciones de paquete</span><span class="sxs-lookup"><span data-stu-id="0f5b7-122">Step 2: Enabling and Configuring Package Configurations</span></span>](lesson-5-2-enabling-and-configuring-package-configurations.md)  
  
-   [<span data-ttu-id="0f5b7-123">Paso 3: Modificación del valor de configuración de la propiedad Directory</span><span class="sxs-lookup"><span data-stu-id="0f5b7-123">Step 3: Modifying the Directory Property Configuration Value</span></span>](lesson-5-3-modifying-the-directory-property-configuration-value.md)  
  
-   [<span data-ttu-id="0f5b7-124">Paso 4: Prueba del paquete del tutorial de la lección 5</span><span class="sxs-lookup"><span data-stu-id="0f5b7-124">Step 4: Testing the Lesson 5 Tutorial Package</span></span>](lesson-5-4-testing-the-lesson-5-tutorial-package.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="0f5b7-125">Iniciar la lección</span><span class="sxs-lookup"><span data-stu-id="0f5b7-125">Start the Lesson</span></span>  
  
-   [<span data-ttu-id="0f5b7-126">Paso 1: Copia del paquete de la lección 4</span><span class="sxs-lookup"><span data-stu-id="0f5b7-126">Step 1: Copying the Lesson 4 Package</span></span>](lesson-5-1-copying-the-lesson-4-package.md)  
  
  
