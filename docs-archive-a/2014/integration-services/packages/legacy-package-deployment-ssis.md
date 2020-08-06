---
title: Implementación de paquetes (SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services packages, deploying
- deploying packages [Integration Services]
- SQL Server Integration Services packages, deploying
- deploying packages [Integration Services], about deploying packages
- packages [Integration Services], deploying
- SSIS packages, deploying
ms.assetid: 0f5fc7be-e37e-4ecd-ba99-697c8ae3436f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 32627eddf5e7a696decd549e9b87ebb5c3b9d031
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674192"
---
# <a name="package-deployment-ssis"></a><span data-ttu-id="2cf37-102">Implementación de paquetes (SSIS)</span><span class="sxs-lookup"><span data-stu-id="2cf37-102">Package Deployment (SSIS)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2cf37-103">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] incluye herramientas y asistentes para facilitar la implementación de paquetes del equipo de desarrollo en el servidor de producción o en otros equipos.</span><span class="sxs-lookup"><span data-stu-id="2cf37-103">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes tools and wizards that make it simple to deploy packages from the development computer to the production server or to other computers.</span></span>  
  
 <span data-ttu-id="2cf37-104">El proceso de implementación de paquetes consta de cuatro pasos:</span><span class="sxs-lookup"><span data-stu-id="2cf37-104">There are four steps in the package deployment process:</span></span>  
  
1.  <span data-ttu-id="2cf37-105">El primer paso es opcional e implica crear configuraciones de paquetes que actualizan las propiedades de los elementos de los paquetes en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2cf37-105">The first optional step is optional and involves creating package configurations that update properties of package elements at run time.</span></span> <span data-ttu-id="2cf37-106">Las configuraciones se incluyen automáticamente al implementar los paquetes.</span><span class="sxs-lookup"><span data-stu-id="2cf37-106">The configurations are automatically included when you deploy the packages.</span></span>  
  
2.  <span data-ttu-id="2cf37-107">El segundo paso es generar el proyecto de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] para crear una utilidad de implementación de paquetes.</span><span class="sxs-lookup"><span data-stu-id="2cf37-107">The second step is to build the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project to create a package deployment utility.</span></span> <span data-ttu-id="2cf37-108">La utilidad de implementación del proyecto contiene los paquetes que desea implementar.</span><span class="sxs-lookup"><span data-stu-id="2cf37-108">The deployment utility for the project contains the packages that you want to deploy</span></span>  
  
3.  <span data-ttu-id="2cf37-109">El tercer paso es copiar la carpeta de implementación que se creó al generar el proyecto de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en el equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="2cf37-109">The third step is to copy the deployment folder that was created when you built the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project to the target computer.</span></span>  
  
4.  <span data-ttu-id="2cf37-110">El cuarto paso es ejecutar en el equipo de destino el Asistente para la instalación de paquetes con el fin de instalar los paquetes en el sistema de archivos o en una sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2cf37-110">The fourth step is to run, on the target computer, the Package Installation Wizard to install the packages to the file system or to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="2cf37-111">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="2cf37-111">Related Tasks</span></span>  
 <span data-ttu-id="2cf37-112">Para obtener información sobre cómo crear una utilidad de implementación, vea [Crear una utilidad de implementación](../create-a-deployment-utility.md).</span><span class="sxs-lookup"><span data-stu-id="2cf37-112">For information about how to create a deployment utility, see [Create a Deployment Utility](../create-a-deployment-utility.md).</span></span>  
  
 <span data-ttu-id="2cf37-113">Para obtener información sobre cómo implementar paquetes mediante la utilidad de implementación, vea [Implementar los paquetes mediante la utilidad de implementación](../deploy-packages-by-using-the-deployment-utility.md).</span><span class="sxs-lookup"><span data-stu-id="2cf37-113">For information about how to deploy packages using the deployment utility, see [Deploy Packages by Using the Deployment Utility](../deploy-packages-by-using-the-deployment-utility.md).</span></span>  
  
 <span data-ttu-id="2cf37-114">Para obtener información sobre cómo crear configuraciones de paquete, vea [Crear configuraciones de paquetes](../create-package-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="2cf37-114">For information about how to create package configurations, see [Create Package Configurations](../create-package-configurations.md).</span></span>  
  
  