---
title: Implementar desde SQL Server Data Tools (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.deploystatus.f1
ms.assetid: 67dde3fe-ba43-41f3-b56c-c656029ee93f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8bc8008e7c79e1652b54b21e6afb116301d1700b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673914"
---
# <a name="deploy-from-sql-server-data-tools-ssas-tabular"></a><span data-ttu-id="7c403-102">Implementar con SQL Server Data Tools (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="7c403-102">Deploy From SQL Server Data Tools (SSAS Tabular)</span></span>
  <span data-ttu-id="7c403-103">Utilice las tareas de este tema para implementar una solución de modelo tabular mediante el comando Implementar en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7c403-103">Use the tasks in this topic to deploy a tabular model solution by using the Deploy command in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="7c403-104">Secciones de este tema:</span><span class="sxs-lookup"><span data-stu-id="7c403-104">Sections in this topic:</span></span>  
  
-   [<span data-ttu-id="7c403-105">Configurar las propiedades opciones de implementación y servidor de implementación</span><span class="sxs-lookup"><span data-stu-id="7c403-105">Configure Deployment Options and Deployment Server Properties</span></span>](#bkmk_deploy)  
  
-   [<span data-ttu-id="7c403-106">Implementar una solución de modelo tabular</span><span class="sxs-lookup"><span data-stu-id="7c403-106">Deploy a Tabular Model Solution</span></span>](#bkmk_deploy_proc)  
  
-   [<span data-ttu-id="7c403-107">Estado de la implementación</span><span class="sxs-lookup"><span data-stu-id="7c403-107">Deploy Status</span></span>](#bkmk_deploy_status)  
  
##  <a name="configure-deployment-options-and-deployment-server-properties"></a><a name="bkmk_deploy"></a><span data-ttu-id="7c403-108">Configurar las propiedades opciones de implementación y servidor de implementación</span><span class="sxs-lookup"><span data-stu-id="7c403-108">Configure Deployment Options and Deployment Server Properties</span></span>  
 <span data-ttu-id="7c403-109">Antes de implementar la solución de modelo tabular, primero debe especificar las propiedades Opciones de implementación y Servidor de implementación.</span><span class="sxs-lookup"><span data-stu-id="7c403-109">Before you deploy your tabular model solution, you must first specify the Deployment Options and Deployment Server properties.</span></span> <span data-ttu-id="7c403-110">Para obtener más información sobre las propiedades y la configuración de la implementación, vea [Implementación de soluciones de modelos tabulares &#40;SSAS tabular&#41;](tabular-model-solution-deployment-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="7c403-110">For more information about deployment properties and settings, see [Tabular Model Solution Deployment &#40;SSAS Tabular&#41;](tabular-model-solution-deployment-ssas-tabular.md).</span></span>  
  
#### <a name="to-configure-deployment-options-and-deployment-server-properties"></a><span data-ttu-id="7c403-111">Para configurar las propiedades Opciones de implementación y Servidor de implementación</span><span class="sxs-lookup"><span data-stu-id="7c403-111">To configure Deployment Options and Deployment Server properties</span></span>  
  
1.  <span data-ttu-id="7c403-112">En [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], en el **Explorador de soluciones**, haga clic con el botón derecho en el nombre del proyecto y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7c403-112">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], in **Solution Explorer**, right-click the project name, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="7c403-113">En el cuadro de diálogo \*\* \<project name> propiedades\*\* , en **Opciones de implementación**, especifique la configuración de propiedades si es diferente de la predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7c403-113">In the **\<project name> Properties** dialog, in **Deployment Options**, specify property settings if different from the default settings.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7c403-114">Para los modelos en modo de almacenamiento en caché, el **Modo de consulta** siempre es **In-Memory**.</span><span class="sxs-lookup"><span data-stu-id="7c403-114">For models in cached mode, **Query Mode** is always **In-Memory**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7c403-115"> No puede especificar la **Configuración de suplantación** de los modelos que se encuentran en modo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="7c403-115">You cannot specify **Impersonation Settings** for models in DirectQuery mode.</span></span>  
  
3.  <span data-ttu-id="7c403-116">En **Servidor de implementación**, especifique la configuración de las propiedades **Servidor** (nombre), **Edición**, **Base de datos** (nombre) y **Nombre del cubo** si difiere de la predeterminada y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7c403-116">In **Deployment Server**, specify the **Server** (name), **Edition**, **Database** (name), and **Cube Name** property settings, if different from the default settings, and then click **OK**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7c403-117">También puede especificar el valor de la propiedad Servidor de implementación predeterminado de modo que los proyectos que se creen se implementen automáticamente en el servidor especificado.</span><span class="sxs-lookup"><span data-stu-id="7c403-117">You can also specify the Default Deployment Server property setting so any new projects you create will automatically be deployed to the specified server.</span></span> <span data-ttu-id="7c403-118">Para obtener más información, vea [Configurar las propiedades predeterminadas de modelado de datos y de implementación &#40;SSAS tabular&#41;](properties-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="7c403-118">For more information, see [Configure Default Data Modeling and Deployment Properties &#40;SSAS Tabular&#41;](properties-ssas-tabular.md).</span></span>  
  
##  <a name="deploy-a-tabular-model-solution"></a><a name="bkmk_deploy_proc"></a><span data-ttu-id="7c403-119">Implementar una solución de modelo tabular</span><span class="sxs-lookup"><span data-stu-id="7c403-119">Deploy a Tabular Model Solution</span></span>  
  
#### <a name="to-deploy-a-tabular-model-solution"></a><span data-ttu-id="7c403-120">Para implementar una solución de modelo tabular</span><span class="sxs-lookup"><span data-stu-id="7c403-120">To deploy a tabular model solution</span></span>  
  
-   <span data-ttu-id="7c403-121">En [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] , en el menú **compilar** , haga clic en \*\*implementar \<project name> \*\*.</span><span class="sxs-lookup"><span data-stu-id="7c403-121">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], on the **Build** menu, click **Deploy \<project name>**.</span></span>  
  
     <span data-ttu-id="7c403-122">Aparecerá el cuadro de diálogo **Implementar** e indicará el estado de la implementación de los metadatos y del procesamiento (a menos que se haya establecido la propiedad Opción de procesamiento en No procesar) de cada tabla incluida en el modelo.</span><span class="sxs-lookup"><span data-stu-id="7c403-122">The **Deploy** dialog box will appear and indicate the status of the metadata deployment and the processing (unless Processing Option property is set to Do Not Process) of each table included in the model.</span></span> <span data-ttu-id="7c403-123">Una vez completado el proceso de implementación, use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para conectarse a la instancia de Analysis Services y comprobar que se ha creado el nuevo objeto de base de datos de modelo, o use una aplicación cliente de informes para conectarse al modelo implementado.</span><span class="sxs-lookup"><span data-stu-id="7c403-123">After the deployment process is complete, use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to connect to the Analysis Services instance and verify the new model database object has been created or use a client reporting application to connect to the deployed model.</span></span>  
  
##  <a name="deploy-status"></a><a name="bkmk_deploy_status"></a><span data-ttu-id="7c403-124">Estado de implementación</span><span class="sxs-lookup"><span data-stu-id="7c403-124">Deploy Status</span></span>  
 <span data-ttu-id="7c403-125">El cuadro de diálogo **Implementar** permite supervisar el progreso de una operación de implementación.</span><span class="sxs-lookup"><span data-stu-id="7c403-125">The **Deploy** dialog box enables you to monitor the progress of a Deploy operation.</span></span> <span data-ttu-id="7c403-126">Una operación de implementación también se puede detener.</span><span class="sxs-lookup"><span data-stu-id="7c403-126">A deploy operation can also be stopped.</span></span>  
  
 <span data-ttu-id="7c403-127">**Estado**</span><span class="sxs-lookup"><span data-stu-id="7c403-127">**Status**</span></span>  
 <span data-ttu-id="7c403-128">Indica si la operación de implementación se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="7c403-128">Indicates whether the Deploy operation was successful or not.</span></span>  
  
 <span data-ttu-id="7c403-129">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="7c403-129">**Details**</span></span>  
 <span data-ttu-id="7c403-130">Enumera los elementos de metadatos implementados y el estado de cada uno, y proporciona un mensaje sobre cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="7c403-130">Lists the metadata items that were deployed, the status for each metadata item, and provides a message of any issues.</span></span>  
  
 <span data-ttu-id="7c403-131">**Detener implementación**</span><span class="sxs-lookup"><span data-stu-id="7c403-131">**Stop Deploy**</span></span>  
 <span data-ttu-id="7c403-132">Haga clic en esta opción para detener la operación de implementación.</span><span class="sxs-lookup"><span data-stu-id="7c403-132">Click to halt the Deploy operation.</span></span> <span data-ttu-id="7c403-133">Esta opción resulta útil si la operación de implementación tarda demasiado o hay demasiados errores.</span><span class="sxs-lookup"><span data-stu-id="7c403-133">This option is useful if the Deploy operation is taking too long, or if there are too many errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c403-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7c403-134">See Also</span></span>  
 <span data-ttu-id="7c403-135">[Implementación de soluciones de modelos tabulares &#40;SSAS tabular&#41;](tabular-model-solution-deployment-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="7c403-135">[Tabular Model Solution Deployment &#40;SSAS Tabular&#41;](tabular-model-solution-deployment-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="7c403-136">Configurar las propiedades predeterminadas de modelado de datos y de implementación &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="7c403-136">Configure Default Data Modeling and Deployment Properties &#40;SSAS Tabular&#41;</span></span>](properties-ssas-tabular.md)  
  
  
