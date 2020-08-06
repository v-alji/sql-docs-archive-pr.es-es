---
title: Crear un paquete de implementación de modelo mediante el asistente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deployment packages [Master Data Services], creating
- models [Master Data Services], creating a deployment package
- creating packages [Master Data Services]
ms.assetid: b24ec4c2-1378-4c72-ac69-4ec2647030f0
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: abb30f9d8e08d8eec8e04960b61575da3a1dbcc0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677184"
---
# <a name="create-a-model-deployment-package-by-using-the-wizard"></a><span data-ttu-id="379b1-102">Crear un paquete de implementación de modelo mediante el asistente</span><span class="sxs-lookup"><span data-stu-id="379b1-102">Create a Model Deployment Package by Using the Wizard</span></span>
  <span data-ttu-id="379b1-103">Use el Asistente para la implementación de modelos de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] para crear un paquete de los objetos del modelo solamente.</span><span class="sxs-lookup"><span data-stu-id="379b1-103">Use the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] model deployment wizard to create a package of the model objects only.</span></span> <span data-ttu-id="379b1-104">Si necesita incluir datos en un paquete, consulte [Implementar un paquete de implementación de modelo mediante MDSModelDeploy](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span><span class="sxs-lookup"><span data-stu-id="379b1-104">If you need to include data in the package, see [Create a Model Deployment Package by Using MDSModelDeploy](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="379b1-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="379b1-105">Prerequisites</span></span>  
 <span data-ttu-id="379b1-106">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="379b1-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="379b1-107">En la aplicación web [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , debe tener permiso de acceso al área funcional **Administración del sistema** .</span><span class="sxs-lookup"><span data-stu-id="379b1-107">In the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application, you must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="379b1-108">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="379b1-108">You must be a model administrator.</span></span> <span data-ttu-id="379b1-109">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="379b1-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="379b1-110">Debe existir un modelo para que se pueda crear un paquete del mismo.</span><span class="sxs-lookup"><span data-stu-id="379b1-110">A model must exist for you to create a package of.</span></span> <span data-ttu-id="379b1-111">Para obtener más información, consulte [Crear un modelo &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-model-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="379b1-111">For more information, see [Create a Model &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-model-master-data-services.md).</span></span>  
  
### <a name="to-create-a-model-deployment-package"></a><span data-ttu-id="379b1-112">Crear un paquete de implementación de modelo</span><span class="sxs-lookup"><span data-stu-id="379b1-112">To create a model deployment package</span></span>  
  
1.  <span data-ttu-id="379b1-113">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="379b1-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="379b1-114">En la página **Vista de modelo** , en la barra de menús, seleccione **Sistema** y haga clic en **Implementación**.</span><span class="sxs-lookup"><span data-stu-id="379b1-114">On the **Model View** page, from the menu bar, point to **System** and click **Deployment**.</span></span>  
  
3.  <span data-ttu-id="379b1-115">En el **Asistente para la implementación de modelos**, haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="379b1-115">On the **Model Deployment Wizard**, click **Create**.</span></span>  
  
4.  <span data-ttu-id="379b1-116">En la página **Crear paquete** , seleccione un modelo en la lista **Modelo** .</span><span class="sxs-lookup"><span data-stu-id="379b1-116">On the **Create Package** page, select a model from the **Model** list.</span></span>  
  
5.  <span data-ttu-id="379b1-117">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="379b1-117">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="379b1-118">Haga clic en **Descargar**.</span><span class="sxs-lookup"><span data-stu-id="379b1-118">Click **Download**.</span></span>  
  
7.  <span data-ttu-id="379b1-119">Guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="379b1-119">Save the file.</span></span>  
  
8.  <span data-ttu-id="379b1-120">Haga clic en **Cerrar** para cerrar el asistente.</span><span class="sxs-lookup"><span data-stu-id="379b1-120">Click **Close** to close the wizard.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="379b1-121">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="379b1-121">Next Steps</span></span>  
  
-   [<span data-ttu-id="379b1-122">Implementar un paquete de implementación de modelo mediante el asistente</span><span class="sxs-lookup"><span data-stu-id="379b1-122">Deploy a Model Deployment Package by Using the Wizard</span></span>](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-the-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="379b1-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="379b1-123">See Also</span></span>  
 [<span data-ttu-id="379b1-124">Implementar modelos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="379b1-124">Deploying Models &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/deploying-models-master-data-services.md)  
  
  
