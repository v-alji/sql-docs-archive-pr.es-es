---
title: Especificando el destino de la instalación | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- input files [Analysis Services]
- installation targets [Analysis Services]
- Analysis Services deployments, installation targets
- Analysis Services Deployment Wizard, installation targets
- deploying [Analysis Services], installation targets
- modifying installation targets
ms.assetid: cb706817-6f63-4771-92c3-b70030bbce3d
author: minewiskan
ms.author: owend
ms.openlocfilehash: e830fc353898e3ec835b338e84765a0cad0de43f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673932"
---
# <a name="specifying-the-installation-target"></a><span data-ttu-id="3ff61-102">Especificar el destino de instalación</span><span class="sxs-lookup"><span data-stu-id="3ff61-102">Specifying the Installation Target</span></span>
  <span data-ttu-id="3ff61-103">El [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Asistente para la implementación de Lee la información de destino de la instalación del \<*project name*> archivo. deploymenttargets.</span><span class="sxs-lookup"><span data-stu-id="3ff61-103">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard reads the installation target information from the \<*project name*>.deploymenttargets file.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="3ff61-104">crea este archivo al compilar el [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] proyecto.</span><span class="sxs-lookup"><span data-stu-id="3ff61-104">creates this file when you build the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="3ff61-105">usa la base de datos y el servidor especificados en la página **implementación** del *\<project name>* cuadro de diálogo páginas de **propiedades** para crear el \<*project name*> archivo. targets.</span><span class="sxs-lookup"><span data-stu-id="3ff61-105">uses the database and server specified on the **Deployment** page of the *\<project name>* **Properties Pages** dialog box to create the \<*project name*>.targets file.</span></span>  
  
## <a name="modifying-the-installation-target-for-deployment"></a><span data-ttu-id="3ff61-106">Modificar el destino de instalación para la implementación</span><span class="sxs-lookup"><span data-stu-id="3ff61-106">Modifying the Installation Target for Deployment</span></span>  
 <span data-ttu-id="3ff61-107">En algunas situaciones, puede que necesite implementar un proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en una base de datos o en una instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que sea diferente a la especificada en la página **Implementación** .</span><span class="sxs-lookup"><span data-stu-id="3ff61-107">In some situations, you may need to deploy an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project to a database or [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance that is different than the one specified on the **Deployment** page.</span></span> <span data-ttu-id="3ff61-108">Por ejemplo, puede que desee implementar el proyecto en un servidor para realizar pruebas antes de la implementación y, a continuación, implementarlo en un servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="3ff61-108">For example, you may want to deploy the project to a server for testing before deployment, and then deploy it to a production server after testing is finished.</span></span> <span data-ttu-id="3ff61-109">Puede que también desee implementar un proyecto finalizado y probado en varios servidores de producción de un clúster de equilibrio de carga de red (NLB), o en un servidor de ensayo y un servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="3ff61-109">You may also want to deploy a completed and tested project to multiple production servers in a Network Load Balancing cluster, or to a staging server and a production server.</span></span>  
  
 <span data-ttu-id="3ff61-110">Para implementar un proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en una base de datos o una instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] diferentes, puede cambiar el destino de instalación del archivo de entrada mediante uno de los métodos descritos en el siguiente procedimiento.</span><span class="sxs-lookup"><span data-stu-id="3ff61-110">To deploy an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project to a different database or [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance, you can change the installation target in the input file by using one of the methods described in the following procedure.</span></span>  
  
#### <a name="to-change-the-installation-target-after-the-input-files-have-been-generated"></a><span data-ttu-id="3ff61-111">Para cambiar el destino de instalación después de haber generado los archivos de entrada</span><span class="sxs-lookup"><span data-stu-id="3ff61-111">To change the installation target after the input files have been generated</span></span>  
  
-   <span data-ttu-id="3ff61-112">Ejecute el Asistente para la implementación de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] de forma interactiva.</span><span class="sxs-lookup"><span data-stu-id="3ff61-112">Run the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard interactively.</span></span> <span data-ttu-id="3ff61-113">En la página **Destino de instalación** , especifique un nuevo destino para la instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] y la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3ff61-113">On the **Installation Target** page, specify a new destination for the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance and database.</span></span>  
  
     <span data-ttu-id="3ff61-114">O bien</span><span class="sxs-lookup"><span data-stu-id="3ff61-114">-or-</span></span>  
  
-   <span data-ttu-id="3ff61-115">Ejecute el Asistente para la implementación de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en el símbolo del sistema y ajuste el asistente de manera que se ejecute en modo de archivo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="3ff61-115">Run the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard at the command prompt and set the wizard to run in answer file mode.</span></span> <span data-ttu-id="3ff61-116">Para obtener más información acerca del modo de archivo de respuesta, vea [Running the Analysis Services Deployment Wizard](running-the-analysis-services-deployment-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="3ff61-116">For more information about answer file mode, see [Running the Analysis Services Deployment Wizard](running-the-analysis-services-deployment-wizard.md).</span></span>  
  
     <span data-ttu-id="3ff61-117">O bien</span><span class="sxs-lookup"><span data-stu-id="3ff61-117">-or-</span></span>  
  
-   <span data-ttu-id="3ff61-118">Modifique el \<*project name*> archivo. deploymenttargets con cualquier editor de texto.</span><span class="sxs-lookup"><span data-stu-id="3ff61-118">Modify the \<*project name*>.deploymenttargets file by using any text editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ff61-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3ff61-119">See Also</span></span>  
 <span data-ttu-id="3ff61-120">[Especificar las opciones de implementación de roles y particiones](deployment-script-files-partition-and-role-deployment-options.md) </span><span class="sxs-lookup"><span data-stu-id="3ff61-120">[Specifying Partition and Role Deployment Options](deployment-script-files-partition-and-role-deployment-options.md) </span></span>  
 <span data-ttu-id="3ff61-121">[Especificar los valores de configuración para la implementación de la solución](deployment-script-files-solution-deployment-config-settings.md) </span><span class="sxs-lookup"><span data-stu-id="3ff61-121">[Specifying Configuration Settings for Solution Deployment](deployment-script-files-solution-deployment-config-settings.md) </span></span>  
 [<span data-ttu-id="3ff61-122">Especificar opciones de procesamiento</span><span class="sxs-lookup"><span data-stu-id="3ff61-122">Specifying Processing Options</span></span>](deployment-script-files-specifying-processing-options.md)  
  
  
