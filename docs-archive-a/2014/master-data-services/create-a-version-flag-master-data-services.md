---
title: Crear una marca de versión (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- creating version flags [Master Data Services]
- version flags [Master Data Services], creating
- versions [Master Data Services], creating flags
ms.assetid: 3067e1e3-05b7-4f11-9206-c612ef4e7e42
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f04c93f8315ccd5b53e07db169783da53afe0156
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674883"
---
# <a name="create-a-version-flag-master-data-services"></a><span data-ttu-id="3ea06-102">Crear una marca de versión (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="3ea06-102">Create a Version Flag (Master Data Services)</span></span>
  <span data-ttu-id="3ea06-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], cree una marca de versión para asignarla a una versión.</span><span class="sxs-lookup"><span data-stu-id="3ea06-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a version flag to assign to a version.</span></span> <span data-ttu-id="3ea06-104">La marca puede indicar la versión que los usuarios o los sistemas que se suscriben deben utilizar.</span><span class="sxs-lookup"><span data-stu-id="3ea06-104">The flag can indicate the version that users or subscribing systems should use.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3ea06-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="3ea06-105">Prerequisites</span></span>  
 <span data-ttu-id="3ea06-106">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="3ea06-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="3ea06-107">Debe disponer del permiso para tener acceso al área funcional de **Administración de versiones** .</span><span class="sxs-lookup"><span data-stu-id="3ea06-107">You must have permission to access the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="3ea06-108">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="3ea06-108">You must be a model administrator.</span></span> <span data-ttu-id="3ea06-109">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="3ea06-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-create-a-version-flag"></a><span data-ttu-id="3ea06-110">Crear una marca de versión</span><span class="sxs-lookup"><span data-stu-id="3ea06-110">To create a version flag</span></span>  
  
1.  <span data-ttu-id="3ea06-111">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Administración de versiones**.</span><span class="sxs-lookup"><span data-stu-id="3ea06-111">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="3ea06-112">En la página **Administración de versiones** , en la barra de menús, seleccione **Administrar** y, a continuación, haga clic en **Marcas**.</span><span class="sxs-lookup"><span data-stu-id="3ea06-112">On the **Manage Versions** page, from the menu bar, point to **Manage** and then click **Flags**.</span></span>  
  
3.  <span data-ttu-id="3ea06-113">En la página **Administrar marcas de versión** , en el campo **Modelo** , seleccione el modelo para el que desea crear una marca.</span><span class="sxs-lookup"><span data-stu-id="3ea06-113">On the **Manage Version Flags** page, from the **Model** field, select the model for which you want to create a flag.</span></span>  
  
4.  <span data-ttu-id="3ea06-114">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="3ea06-114">Click **Add**.</span></span>  
  
5.  <span data-ttu-id="3ea06-115">En el cuadro **Nombre** , escriba un nombre.</span><span class="sxs-lookup"><span data-stu-id="3ea06-115">In the **Name** box, type a name.</span></span>  
  
6.  <span data-ttu-id="3ea06-116">En el cuadro **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="3ea06-116">In the **Description** box, type a description.</span></span>  
  
7.  <span data-ttu-id="3ea06-117">En el campo **Solo versiones confirmadas** , seleccione **Verdadero** para indicar que la marca solo puede asignarse a las versiones con el estado **Confirmado** .</span><span class="sxs-lookup"><span data-stu-id="3ea06-117">In the **Committed Versions Only** field, select **True** to indicate that the flag can be assigned to versions with a status of **Committed** only.</span></span> <span data-ttu-id="3ea06-118">Seleccione **Falso** para indicar que la marca puede asignarse a versiones que tengan cualquier estado.</span><span class="sxs-lookup"><span data-stu-id="3ea06-118">Select **False** to indicate that the flag can be assigned to versions with any status.</span></span>  
  
8.  <span data-ttu-id="3ea06-119">Haga clic en **Save**(Guardar).</span><span class="sxs-lookup"><span data-stu-id="3ea06-119">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="3ea06-120">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="3ea06-120">Next Steps</span></span>  
  
-   [<span data-ttu-id="3ea06-121">Asignar una marca a una versión &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="3ea06-121">Assign a Flag to a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/assign-a-flag-to-a-version-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="3ea06-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3ea06-122">See Also</span></span>  
 <span data-ttu-id="3ea06-123">[Versiones &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="3ea06-123">[Versions &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span></span>  
 [<span data-ttu-id="3ea06-124">Cambiar el nombre de marca de una versión &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="3ea06-124">Change a Version Flag Name &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/change-a-version-flag-name-master-data-services.md)  
  
  
