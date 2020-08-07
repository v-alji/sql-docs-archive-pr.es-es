---
title: Seguimiento de cambios (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- change tracking [SQL Server]
ms.assetid: 5e879c65-0d38-454f-9a20-62a6e72c89f7
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 2d3b69057b02884f41a43aa9a009ab3db937ed25
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746322"
---
# <a name="change-tracking-master-data-services"></a><span data-ttu-id="79e8b-102">Seguimiento de cambios [Master Data Services]</span><span class="sxs-lookup"><span data-stu-id="79e8b-102">Change Tracking (Master Data Services)</span></span>
  <span data-ttu-id="79e8b-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], puede usar grupos de seguimiento de cambios para realizar una acción cuando cambie un valor de atributo.</span><span class="sxs-lookup"><span data-stu-id="79e8b-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can use change tracking groups to take action when an attribute value changes.</span></span> <span data-ttu-id="79e8b-104">Use el seguimiento de cambios cuando no conozca cuál será el nuevo valor, pero quiera saber si se produjo algún cambio.</span><span class="sxs-lookup"><span data-stu-id="79e8b-104">Use change tracking when you don't know what the new value will be, but instead want to know if any change occurred.</span></span>  
  
## <a name="configuring-change-tracking"></a><span data-ttu-id="79e8b-105">Configurar el seguimiento de cambios</span><span class="sxs-lookup"><span data-stu-id="79e8b-105">Configuring Change Tracking</span></span>  
 <span data-ttu-id="79e8b-106">Para configurar el seguimiento de cambios, agregue un atributo a un grupo de seguimiento de cambios.</span><span class="sxs-lookup"><span data-stu-id="79e8b-106">To configure change tracking, you add an attribute to a change tracking group.</span></span> <span data-ttu-id="79e8b-107">El grupo puede contener uno o muchos atributos.</span><span class="sxs-lookup"><span data-stu-id="79e8b-107">The group can contain one or many attributes.</span></span> <span data-ttu-id="79e8b-108">A continuación, cree una regla de negocios para definir la acción que se realizará cuando alguno de los atributos del grupo cambie.</span><span class="sxs-lookup"><span data-stu-id="79e8b-108">Then, you create a business rule to define the action that is taken when any of the attributes in the group change.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="79e8b-109">Las reglas de negocios del seguimiento de cambios consideran los cambios en lo datos almacenados (importados) provisionalmente.</span><span class="sxs-lookup"><span data-stu-id="79e8b-109">Change tracking business rules consider staged (imported) data to be changed.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="79e8b-110">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="79e8b-110">Related Tasks</span></span>  
  
|<span data-ttu-id="79e8b-111">Descripción de la tarea</span><span class="sxs-lookup"><span data-stu-id="79e8b-111">Task Description</span></span>|<span data-ttu-id="79e8b-112">Tema</span><span class="sxs-lookup"><span data-stu-id="79e8b-112">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="79e8b-113">Agregar atributos a un grupo de seguimiento de cambios.</span><span class="sxs-lookup"><span data-stu-id="79e8b-113">Add attributes to a change tracking group.</span></span>|[<span data-ttu-id="79e8b-114">Agregar atributos a un grupo de seguimiento de cambios &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="79e8b-114">Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;</span></span>](add-attributes-to-a-change-tracking-group-master-data-services.md)|  
|<span data-ttu-id="79e8b-115">Crear una regla de negocios para iniciar acciones según los cambios en los atributos.</span><span class="sxs-lookup"><span data-stu-id="79e8b-115">Create a business rule that initiates actions based on attribute changes.</span></span>|[<span data-ttu-id="79e8b-116">Iniciar acciones según los cambios de valores de atributos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="79e8b-116">Initiate Actions Based on Attribute Value Changes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/initiate-actions-based-on-attribute-value-changes-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="79e8b-117">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="79e8b-117">Related Content</span></span>  
  
-   [<span data-ttu-id="79e8b-118">Validación &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="79e8b-118">Validation &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validation-master-data-services.md)  
  
-   [<span data-ttu-id="79e8b-119">Reglas de negocios &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="79e8b-119">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)  
  
-   [<span data-ttu-id="79e8b-120">Atributos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="79e8b-120">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)  
  
  
