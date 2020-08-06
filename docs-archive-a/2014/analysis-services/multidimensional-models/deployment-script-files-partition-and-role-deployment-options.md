---
title: Especificar opciones de implementación de roles y particiones | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- input files [Analysis Services]
- partitions [Analysis Services], deployment options
- Analysis Services deployments, roles
- Analysis Services deployments, partitions
- Analysis Services Deployment Wizard, roles
- Analysis Services Deployment Wizard, partitions
- deploying [Analysis Services], roles
- roles [Analysis Services], deployment options
- deploying [Analysis Services], partitions
- modifying role deployments
- modifying partition deployments
ms.assetid: e9b9ca57-a5cc-4fc0-87b5-305257038d56
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8c8dd7bcb482c2d28a18e3039f5acb777b121202
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676690"
---
# <a name="specifying-partition-and-role-deployment-options"></a><span data-ttu-id="8d27c-102">Especificar opciones de implementación de roles y particiones</span><span class="sxs-lookup"><span data-stu-id="8d27c-102">Specifying Partition and Role Deployment Options</span></span>
  <span data-ttu-id="8d27c-103">El [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Asistente para la implementación de Lee las opciones de implementación de roles y particiones del \<*project name*> archivo. archivo deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="8d27c-103">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard reads the partition and role deployment options from the \<*project name*>.deploymentoptions file.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="8d27c-104">crea este archivo al compilar el [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] proyecto.</span><span class="sxs-lookup"><span data-stu-id="8d27c-104">creates this file when you build the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="8d27c-105">usa las opciones de implementación de particiones y roles del proyecto actual cuando \<*project name*> se crea el archivo. archivo deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="8d27c-105">uses the partition and role deployment options of the current project when the \<*project name*>.deploymentoptions file is created.</span></span> <span data-ttu-id="8d27c-106">Para obtener más información acerca de los valores de configuración, vea [Understanding the Input Files Used to Create the Deployment Script](deployment-script-files-input-used-to-create-deployment-script.md).</span><span class="sxs-lookup"><span data-stu-id="8d27c-106">For more information about configuration settings, see [Understanding the Input Files Used to Create the Deployment Script](deployment-script-files-input-used-to-create-deployment-script.md).</span></span>  
  
## <a name="reviewing-the-partition-and-role-deployment-options"></a><span data-ttu-id="8d27c-107">Revisar las opciones de implementación de roles y particiones</span><span class="sxs-lookup"><span data-stu-id="8d27c-107">Reviewing the Partition and Role Deployment Options</span></span>  
 <span data-ttu-id="8d27c-108">Entre las opciones de implementación del \<*project name*> archivo. archivo deploymentoptions se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="8d27c-108">The deployment options in the \<*project name*>.deploymentoptions file include the following:</span></span>  
  
 <span data-ttu-id="8d27c-109">**Opciones de implementación de particiones**</span><span class="sxs-lookup"><span data-stu-id="8d27c-109">**Partition deployment options**</span></span>  
 <span data-ttu-id="8d27c-110">El \<*project name*> archivo. archivo deploymentoptions especifica si las particiones existentes en la base de datos de destino se conservan o se sobrescriben (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="8d27c-110">The \<*project name*>.deploymentoptions file specifies whether existing partitions in the destination database are retained or overwritten (default).</span></span> <span data-ttu-id="8d27c-111">Si las particiones existentes se conservan, solo se implementarán nuevas particiones, y el diseño de las particiones y agregaciones de todos los grupos de medida existentes permanecerán inalterados.</span><span class="sxs-lookup"><span data-stu-id="8d27c-111">If existing partitions are retained, only new partitions will be deployed, and the partitions and aggregation designs on all existing measure groups are left unchanged.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8d27c-112">Si se elimina el grupo de medida en el que existe la partición, la partición se elimina también automáticamente.</span><span class="sxs-lookup"><span data-stu-id="8d27c-112">If the measure group in which the partition exists is deleted, the partition is automatically deleted.</span></span>  
  
 <span data-ttu-id="8d27c-113">**Opciones de implementación de roles**</span><span class="sxs-lookup"><span data-stu-id="8d27c-113">**Role deployment options**</span></span>  
 <span data-ttu-id="8d27c-114">El \<*project name*> archivo. archivo deploymentoptions especifica una de las siguientes opciones de implementación de roles:</span><span class="sxs-lookup"><span data-stu-id="8d27c-114">The \<*project name*>.deploymentoptions file specifies one of the following role deployment options:</span></span>  
  
-   <span data-ttu-id="8d27c-115">Los roles y miembros de roles existentes en la base de datos de destino se conservan, y solo se implementan los roles y miembros de roles nuevos.</span><span class="sxs-lookup"><span data-stu-id="8d27c-115">Existing roles and role members in the destination database are retained, and only new roles and role members are deployed.</span></span>  
  
-   <span data-ttu-id="8d27c-116">Todos los miembros y roles existentes en la base de datos de destino se reemplazan por los roles y los miembros implementados.</span><span class="sxs-lookup"><span data-stu-id="8d27c-116">All existing roles and members in the destination database are replaced by the roles and members being deployed.</span></span>  
  
-   <span data-ttu-id="8d27c-117">Los roles y miembros de roles existentes en la base de datos de destino se conservan, y no se implementan los roles nuevos.</span><span class="sxs-lookup"><span data-stu-id="8d27c-117">Existing roles and role members in the destination database are retained, and no new roles are deployed.</span></span>  
  
-   <span data-ttu-id="8d27c-118">**Nota** Cuando se conservan los roles y los miembros existentes, los permisos asociados con esos roles se restablecen en ninguno.</span><span class="sxs-lookup"><span data-stu-id="8d27c-118">**Note** When existing roles and members are retained, the permissions associated with those roles are reset to none.</span></span> <span data-ttu-id="8d27c-119">Los permisos de seguridad están incluidos en los objetos que protegen, no en los roles de seguridad a los que están asociados.</span><span class="sxs-lookup"><span data-stu-id="8d27c-119">Security permissions are contained by the objects they secure, not by the security roles with which they are associated.</span></span> <span data-ttu-id="8d27c-120">Para obtener más información acerca de cómo trabajar con este comportamiento mediante el Asistente para la implementación de Analysis Services, vea el apartado sobre la conservación de roles y miembros de Microsoft Knowledge base.</span><span class="sxs-lookup"><span data-stu-id="8d27c-120">For more information about how to work with this behavior by using the Analysis Service Deployment Wizard, see 'Retain Roles and Members' in the Microsoft Knowledge Base.</span></span>  
  
## <a name="modifying-the-partition-and-role-deployment-options"></a><span data-ttu-id="8d27c-121">Modificar las opciones de implementación de roles y particiones</span><span class="sxs-lookup"><span data-stu-id="8d27c-121">Modifying the Partition and Role Deployment Options</span></span>  
 <span data-ttu-id="8d27c-122">Es posible que tenga que implementar el [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] proyecto con distintas opciones de particiones y roles que las almacenadas en el \<*project name*> archivo. archivo deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="8d27c-122">You may have to deploy the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project using different partition and role options than those stored in the \<*project name*>.deploymentoptions file.</span></span> <span data-ttu-id="8d27c-123">Por ejemplo, puede que desee conservar las particiones, los roles y los miembros de roles existentes, en lugar de reemplazar todas las particiones, los roles y los miembros existentes, como se indica en el \<*project name*> archivo. archivo deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="8d27c-123">For example, you may want to retain existing partitions, roles, and role members, instead of replacing all existing partitions, roles, and members as indicated in the \<*project name*>.deploymentoptions file.</span></span>  
  
 <span data-ttu-id="8d27c-124">Para modificar la implementación de particiones y roles en un [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] proyecto de, no puede cambiar la configuración de particiones y roles del proyecto porque el *\<project name>* cuadro de diálogo **páginas de propiedades** de no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] muestra estas opciones.</span><span class="sxs-lookup"><span data-stu-id="8d27c-124">To modify the deployment of partitions and roles in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, you cannot change the partition and roles settings within the project because the *\<project name>* **Properties Pages** dialog box in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] does not display these options.</span></span> <span data-ttu-id="8d27c-125">Si desea cambiar las opciones de implementación de roles y particiones, debe cambiar esta información dentro del \<*project name*> propio archivo. archivo deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="8d27c-125">If you want to change the deployment options for roles and partitions, you must change this information within the \<*project name*>.deploymentoptions file itself.</span></span> <span data-ttu-id="8d27c-126">En el siguiente procedimiento se describe cómo cambiar las opciones de implementación de roles y particiones en el \<*project name*> archivo. archivo deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="8d27c-126">The following procedure describes how to change the partition and role deployment options within the \<*project name*>.deploymentoptions file.</span></span>  
  
#### <a name="to-change-the-deployment-of-partitions-or-roles-after-the-input-files-have-been-generated"></a><span data-ttu-id="8d27c-127">Para cambiar la implementación de particiones o roles después de haber generado los archivos de entrada</span><span class="sxs-lookup"><span data-stu-id="8d27c-127">To change the deployment of partitions or roles after the input files have been generated</span></span>  
  
-   <span data-ttu-id="8d27c-128">Ejecute el Asistente para la implementación de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] de forma interactiva, y en la página **Opciones de implementación de particiones y roles** , especifique nuevas opciones de implementación para las particiones y los roles.</span><span class="sxs-lookup"><span data-stu-id="8d27c-128">Run the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard interactively, and on the **Partition and Role Deployment Options** page, specify new deployment options for the partitions and roles.</span></span>  
  
     <span data-ttu-id="8d27c-129">O bien</span><span class="sxs-lookup"><span data-stu-id="8d27c-129">-or-</span></span>  
  
-   <span data-ttu-id="8d27c-130">Ejecute el Asistente para la implementación de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en el símbolo del sistema y ajuste el asistente de manera que se ejecute en modo de archivo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="8d27c-130">Run the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard at the command prompt, and set the wizard to run in answer file mode.</span></span> <span data-ttu-id="8d27c-131">(Para obtener más información acerca del modo de archivo de respuesta, vea [ejecutar el Asistente para la implementación de Analysis Services](running-the-analysis-services-deployment-wizard.md)).</span><span class="sxs-lookup"><span data-stu-id="8d27c-131">(For more information about answer file mode, see [Running the Analysis Services Deployment Wizard](running-the-analysis-services-deployment-wizard.md).)</span></span>  
  
     <span data-ttu-id="8d27c-132">O bien</span><span class="sxs-lookup"><span data-stu-id="8d27c-132">-or-</span></span>  
  
-   <span data-ttu-id="8d27c-133">Abra el \<*project name*> . archivo deploymentoptions en cualquier editor de texto y cambie manualmente las opciones.</span><span class="sxs-lookup"><span data-stu-id="8d27c-133">Open the \<*project name*>.deploymentoptions in any text editor and manually change the options.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d27c-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8d27c-134">See Also</span></span>  
 <span data-ttu-id="8d27c-135">[Especificar el destino de instalación](deployment-script-files-specifying-the-installation-target.md) </span><span class="sxs-lookup"><span data-stu-id="8d27c-135">[Specifying the Installation Target](deployment-script-files-specifying-the-installation-target.md) </span></span>  
 <span data-ttu-id="8d27c-136">[Especificar los valores de configuración para la implementación de la solución](deployment-script-files-solution-deployment-config-settings.md) </span><span class="sxs-lookup"><span data-stu-id="8d27c-136">[Specifying Configuration Settings for Solution Deployment](deployment-script-files-solution-deployment-config-settings.md) </span></span>  
 [<span data-ttu-id="8d27c-137">Especificar opciones de procesamiento</span><span class="sxs-lookup"><span data-stu-id="8d27c-137">Specifying Processing Options</span></span>](deployment-script-files-specifying-processing-options.md)  
  
  
