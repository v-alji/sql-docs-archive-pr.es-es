---
title: 'Paso 2: Convertir el proyecto al modelo de implementación de proyectos | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 80964293-f1f5-4da7-b1fb-00ab8c30c1c5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1a7b879b2bea4afd58a48cdfc6f0890353fe6758
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663573"
---
# <a name="step-2-converting-the-project-to-the-project-deployment-model"></a><span data-ttu-id="85477-102">Paso 2: Convertir el proyecto al modelo de implementación del proyectos</span><span class="sxs-lookup"><span data-stu-id="85477-102">Step 2: Converting the Project to the Project Deployment Model</span></span>
  <span data-ttu-id="85477-103">En esta tarea, usará al Asistente para conversión de proyectos de Integration Services para convertir el proyecto en el modelo de implementación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="85477-103">In this task, you will use the Integration Services Project Conversion Wizard to convert the project to the Project Deployment Model.</span></span>  
  
### <a name="converting-the-project-to-the-project-deployment-model"></a><span data-ttu-id="85477-104">Convertir el proyecto al modelo de implementación del proyectos</span><span class="sxs-lookup"><span data-stu-id="85477-104">Converting the Project to the Project Deployment Model</span></span>  
  
1.  <span data-ttu-id="85477-105">En el menú Proyecto, haga clic en Convertir al modelo de implementación de proyectos.</span><span class="sxs-lookup"><span data-stu-id="85477-105">On the Project Menu, click Convert to Project Deployment Model.</span></span>  
  
2.  <span data-ttu-id="85477-106">En la página de introducción del Asistente para conversión de proyectos de Integration Services, revise los pasos y haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="85477-106">On the Integration Services Project Conversion Wizard Introduction page, review the steps then click Next.</span></span>  
  
3.  <span data-ttu-id="85477-107">En la página Seleccionar paquetes, en la lista de paquetes, desactive todas las casillas de verificación excepto Lesson 6.dtsx y haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="85477-107">On the Select Packages page, in the Packages list, clear all checkboxes except Lesson 6.dtsx then click Next.</span></span>  
  
4.  <span data-ttu-id="85477-108">En la página Especificar propiedades del proyecto, haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="85477-108">On the Specify Project Properties page, click Next.</span></span>  
  
5.  <span data-ttu-id="85477-109">En la página Actualizar tarea Ejecutar paquete, haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="85477-109">On the Update Execute Package Task page click Next.</span></span>  
  
6.  <span data-ttu-id="85477-110">En la página Seleccionar configuración, asegúrese de que el paquete Lesson 6.dtsx está seleccionado en la lista de configuraciones y haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="85477-110">On the Select Configurations page, make sure the Lesson 6.dtsx package is selected in the Configurations list, then click Next.</span></span>  
  
7.  <span data-ttu-id="85477-111">En la página Crear parámetros, asegúrese de que el paquete Lesson 6.dtsx está seleccionado y el ámbito está configurado en Paquete, en la lista de propiedades de configuración, y haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="85477-111">On the Create Parameters page make sure the Lesson 6.dtsx package is selected, and the Scope is set to Package, in the Configuration Properties List, then Click Next.</span></span>  
  
8.  <span data-ttu-id="85477-112">En la página Configurar parámetros, compruebe que los valores de Nombre y Valor son el mismo nombre y el mismo valor especificados en Lesson 5 para la variable y el valor de configuración, y haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="85477-112">On the Configure Parameters page verify that the values for Name and Value are the same name and value specified in Lesson 5 for the variable and configuration value, then click Next.</span></span>  
  
9. <span data-ttu-id="85477-113">En la página Revisar, en el panel de resumen, tenga en cuenta que el asistente ha usado la información del archivo de configuración para establecer las propiedades que se van a convertir.</span><span class="sxs-lookup"><span data-stu-id="85477-113">On the Review page, in the Summary pane, notice that the wizard has used the information from the configuration file to set the Properties to be converted.</span></span>  
  
10. <span data-ttu-id="85477-114">Haga clic en Convertir.</span><span class="sxs-lookup"><span data-stu-id="85477-114">Click Convert.</span></span>  
  
     <span data-ttu-id="85477-115">Cuando la conversión finaliza, se muestra un mensaje que advierte que los cambios no se guardarán hasta que el proyecto se guarde en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="85477-115">When the conversion completes a message is displayed warning that the changes are not saved until the project is saved in Visual Studio.</span></span> <span data-ttu-id="85477-116">Haga clic en Aceptar del cuadro de diálogo de advertencia.</span><span class="sxs-lookup"><span data-stu-id="85477-116">Click OK on the warning dialog.</span></span>  
  
11. <span data-ttu-id="85477-117">En el Asistente para conversión de proyectos de Integration Services, haga clic en Cerrar.</span><span class="sxs-lookup"><span data-stu-id="85477-117">On the Integration Services Project Conversion Wizard click Close.</span></span>  
  
12. <span data-ttu-id="85477-118">En Herramientas de datos de SQL Server, haga clic en el menú Archivo y haga clic en Guardar para guardar el paquete convertido.</span><span class="sxs-lookup"><span data-stu-id="85477-118">In SQL Server Data Tools, click the File menu, then click Save to save the converted package.</span></span>  
  
13. <span data-ttu-id="85477-119">Haga clic en la ficha Parámetros y compruebe que el paquete contiene un parámetro para VarFolderName, y que el valor es la misma ruta de acceso especificada para la carpeta Nuevos datos de ejemplo del archivo de configuración Lesson 5.</span><span class="sxs-lookup"><span data-stu-id="85477-119">Click the Parameters Tab and verify that the package now contains a parameter for VarFolderName and that the value is the same path specified for the New Sample Data folder from the Lesson 5 configuration file.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="85477-120">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="85477-120">Next Task in Lesson</span></span>  
 [<span data-ttu-id="85477-121">Paso 3: Prueba del paquete de la lección 6</span><span class="sxs-lookup"><span data-stu-id="85477-121">Step 3: Testing the Lesson 6 Package</span></span>](lesson-6-3-testing-the-lesson-6-package.md)  
  
  
