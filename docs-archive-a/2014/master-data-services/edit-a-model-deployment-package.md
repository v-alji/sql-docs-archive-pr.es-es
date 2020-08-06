---
title: Editar un paquete de implementación de modelos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 6b0fdb7d-83dd-4392-9011-4ae642c471f1
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: b8bfd7083e2ba763d15a405266260b5a096c8378
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678209"
---
# <a name="edit-a-model-deployment-package"></a><span data-ttu-id="df2ad-102">Editar un paquete de implementación de modelos</span><span class="sxs-lookup"><span data-stu-id="df2ad-102">Edit a Model Deployment Package</span></span>
  <span data-ttu-id="df2ad-103">En este tema se describe cómo implementar partes específicas de un modelo de MDS en lugar de un modelo completo.</span><span class="sxs-lookup"><span data-stu-id="df2ad-103">This topic describes how to deploy selected parts of a model in MDS, rather than an entire model.</span></span> <span data-ttu-id="df2ad-104">Para ello, deberá editar un paquete de modelo de MDS con el Editor de paquetes de modelo.</span><span class="sxs-lookup"><span data-stu-id="df2ad-104">To do so, you edit an MDS model package using the Model Package Editor.</span></span>  
  
 <span data-ttu-id="df2ad-105">El asistente del Editor de paquetes de modelo le permite seleccionar las entidades, jerarquías derivadas, vistas de suscripciones y reglas de negocios de un modelo que desea incluir en un paquete de MDS para su posterior implementación.</span><span class="sxs-lookup"><span data-stu-id="df2ad-105">The Model Package Editor wizard enables you to select the specific entities, derived hierarchies, subscription views, and business rules in a model that you want to include in an MDS package, and then later deploy.</span></span> <span data-ttu-id="df2ad-106">Puede dejar al margen las partes del modelo que no desea implementar.</span><span class="sxs-lookup"><span data-stu-id="df2ad-106">You can leave out those parts of the model that you do not want to deploy.</span></span> <span data-ttu-id="df2ad-107">Cuando se selecciona una entidad, se seleccionan automáticamente todos los objetos dependientes de dicha entidad.</span><span class="sxs-lookup"><span data-stu-id="df2ad-107">When you select an entity, all of the dependent objects in that entity are also automatically selected.</span></span>  
  
 <span data-ttu-id="df2ad-108">Utilice el Editor de paquetes de modelo para seleccionar partes de un modelo de un archivo de paquete creado por la herramienta MDSModelDeploy (que crea un archivo de paquete que incluye objetos y datos) o por el Asistente para la implementación de modelos (que crea un archivo que incluye solo la estructura del modelo).</span><span class="sxs-lookup"><span data-stu-id="df2ad-108">You use the Model Package Editor to select parts of a model in a package file that was created by either the MDSModelDeploy tool (which creates a package file that includes objects and data) or the Model Deployment wizard (which creates a file that includes only the model structure).</span></span> <span data-ttu-id="df2ad-109">Después de modificar el modelo del paquete, utilice la herramienta MDSModelDeploy para implementar objetos y datos, o el Asistente para la implementación de modelos para implementar solo la estructura del modelo.</span><span class="sxs-lookup"><span data-stu-id="df2ad-109">After editing the model in the package, you use the MDSModelDeploy tool to deploy objects and data, or the Model Deployment wizard to deploy just the model structure.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="df2ad-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="df2ad-110">Prerequisites</span></span>  
 <span data-ttu-id="df2ad-111">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="df2ad-111">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="df2ad-112">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="df2ad-112">You must be a model administrator.</span></span> <span data-ttu-id="df2ad-113">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="df2ad-113">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="df2ad-114">Debe existir un paquete de modelo.</span><span class="sxs-lookup"><span data-stu-id="df2ad-114">A model package must exist for you to edit.</span></span> <span data-ttu-id="df2ad-115">Para obtener más información, consulte [Implementar modelos &#40;Master Data Services&#41;](../../2014/master-data-services/deploying-models-master-data-services.md) y [Crear un paquete de implementación de modelo mediante el asistente](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md) o [Crear un paquete de implementación de modelo mediante MDSModelDeploy](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span><span class="sxs-lookup"><span data-stu-id="df2ad-115">For more information, see [Deploying Models &#40;Master Data Services&#41;](../../2014/master-data-services/deploying-models-master-data-services.md) and [Create a Model Deployment Package by Using the Wizard](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md) or [Create a Model Deployment Package by Using MDSModelDeploy](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span></span>  
  
### <a name="to-edit-a-model-deployment-package"></a><span data-ttu-id="df2ad-116">Para editar un paquete de implementación de modelos</span><span class="sxs-lookup"><span data-stu-id="df2ad-116">To edit a model deployment package</span></span>  
  
1.  <span data-ttu-id="df2ad-117">En el Explorador de Windows del servidor de MDS, desplácese hasta *drive*:\Archivos de programa\Microsoft SQL Server\120\Master Data Services\Configuration.</span><span class="sxs-lookup"><span data-stu-id="df2ad-117">In Windows Explorer on the MDS server, move to *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\Configuration.</span></span>  
  
2.  <span data-ttu-id="df2ad-118">Ejecute ModelPackageEditor.exe.</span><span class="sxs-lookup"><span data-stu-id="df2ad-118">Execute ModelPackageEditor.exe.</span></span>  
  
3.  <span data-ttu-id="df2ad-119">En el asistente del Editor de paquetes de modelo, haga clic en **Examinar**, desplácese a la carpeta que contiene los paquetes, seleccione un paquete y, a continuación, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="df2ad-119">In the Model Package Editor wizard, click **Browse**, move to the folder containing your packages, select a package, and then click **Open**.</span></span> <span data-ttu-id="df2ad-120">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="df2ad-120">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="df2ad-121">Seleccione las entidades, jerarquías derivadas, vistas de suscripciones o reglas de negocios que desea implementar.</span><span class="sxs-lookup"><span data-stu-id="df2ad-121">Select those entities, derived hierarchies, subscriptions views, or business rules that you want to deploy.</span></span> <span data-ttu-id="df2ad-122">Anule la selección de los elementos que no desea implementar.</span><span class="sxs-lookup"><span data-stu-id="df2ad-122">Deselect those that you do not want to deploy.</span></span> <span data-ttu-id="df2ad-123">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="df2ad-123">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="df2ad-124">Compruebe la lista de elementos que va a implementar.</span><span class="sxs-lookup"><span data-stu-id="df2ad-124">Verify the list of selections to deploy.</span></span> <span data-ttu-id="df2ad-125">Si desea realizar algún cambio, haga clic en **Atrás** y repita el paso 4.</span><span class="sxs-lookup"><span data-stu-id="df2ad-125">To change, click **Back** and repeat step 4.</span></span>  
  
6.  <span data-ttu-id="df2ad-126">Haga clic en **Examinar**, desplácese a la carpeta en la que quiera guardar el paquete parcial y escriba el nombre de archivo de ese paquete (con la extensión .pkg).</span><span class="sxs-lookup"><span data-stu-id="df2ad-126">Click **Browse**, move to the folder that you want to save the partial package in, and then enter the file name of the partial package (with a .pkg extension).</span></span> <span data-ttu-id="df2ad-127">Haga clic en **Save**(Guardar).</span><span class="sxs-lookup"><span data-stu-id="df2ad-127">Click **Save**.</span></span>  
  
7.  <span data-ttu-id="df2ad-128">Haga clic en **Finalizar**</span><span class="sxs-lookup"><span data-stu-id="df2ad-128">Click **Finish**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="df2ad-129">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="df2ad-129">Next Steps</span></span>  
  
-   [<span data-ttu-id="df2ad-130">Implementar un paquete de implementación de modelo mediante el asistente</span><span class="sxs-lookup"><span data-stu-id="df2ad-130">Deploy a Model Deployment Package by Using the Wizard</span></span>](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-the-wizard.md)  
  
-   [<span data-ttu-id="df2ad-131">Implementar un paquete de implementación de modelo mediante MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="df2ad-131">Deploy a Model Deployment Package by Using MDSModelDeploy</span></span>](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-mdsmodeldeploy.md)  
  
  
