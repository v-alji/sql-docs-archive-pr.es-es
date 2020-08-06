---
title: Notificaciones (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- notifications [Master Data Services]
- notifications [Master Data Services], about notifications
- e-mail [Master Data Services]
- e-mail [Master Data Services], about e-mail notifications
ms.assetid: d7ad32d5-9fe5-48fd-8c61-0b00c0aff082
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: a61825f9450dd5b708aff8c3fc72f0f12732337b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677166"
---
# <a name="notifications-master-data-services"></a><span data-ttu-id="fb35a-102">Notificaciones (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="fb35a-102">Notifications (Master Data Services)</span></span>
  [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]<span data-ttu-id="fb35a-103">se puede configurar para enviar una notificación por correo electrónico cuando se produce un error en la validación de la regla de negocios o cuando el estado de una versión del modelo cambia.</span><span class="sxs-lookup"><span data-stu-id="fb35a-103">can be configured to send an email notification when business rule validation fails or the status of a model version changes.</span></span>  
  
## <a name="how-notifications-are-sent"></a><span data-ttu-id="fb35a-104">Cómo se envían las notificaciones</span><span class="sxs-lookup"><span data-stu-id="fb35a-104">How Notifications Are Sent</span></span>  
 <span data-ttu-id="fb35a-105">Las notificaciones se configuran en [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb35a-105">You configure notifications in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)].</span></span> <span data-ttu-id="fb35a-106">Las notificaciones envían mensajes de correo electrónico mediante Correo electrónico de base de datos en la instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../includes/ssde-md.md)] que hospeda la [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] base de datos.</span><span class="sxs-lookup"><span data-stu-id="fb35a-106">Notifications send email messages by using Database Mail on the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../includes/ssde-md.md)] that hosts the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="fb35a-107">Para obtener más información sobre el correo electrónico de base de datos, consulte [Objetos de configuración de Correo electrónico de base de datos](../relational-databases/database-mail/database-mail-configuration-objects.md) en los Libros en pantalla de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fb35a-107">For more information about Database Mail, see [Database Mail Configuration Objects](../relational-databases/database-mail/database-mail-configuration-objects.md) in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="when-notifications-are-sent"></a><span data-ttu-id="fb35a-108">Cuándo se envían notificaciones</span><span class="sxs-lookup"><span data-stu-id="fb35a-108">When Notifications Are Sent</span></span>  
 <span data-ttu-id="fb35a-109">Una vez configuradas las notificaciones, se pueden enviar notificaciones por correo electrónico automatizadas en los casos siguientes.</span><span class="sxs-lookup"><span data-stu-id="fb35a-109">After notifications are configured, automated email notifications can be sent in the following instances.</span></span>  
  
|<span data-ttu-id="fb35a-110">Instancia</span><span class="sxs-lookup"><span data-stu-id="fb35a-110">Instance</span></span>|<span data-ttu-id="fb35a-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="fb35a-111">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="fb35a-112">Haya un error de los datos en la validación de la regla de negocios</span><span class="sxs-lookup"><span data-stu-id="fb35a-112">Data fails business rule validation</span></span>|<span data-ttu-id="fb35a-113">Se deben configurar reglas de negocios individuales para enviar correo electrónico cuando un valor de atributo produce un error en la validación de la regla de negocios.</span><span class="sxs-lookup"><span data-stu-id="fb35a-113">Individual business rules must be configured to send email when an attribute value fails business rule validation.</span></span> <span data-ttu-id="fb35a-114">Para obtener más información, consulte [Configurar reglas de negocios para enviar notificaciones &#40;Master Data Services&#41;](configure-business-rules-to-send-notifications-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="fb35a-114">For more information, see [Configure Business Rules to Send Notifications &#40;Master Data Services&#41;](configure-business-rules-to-send-notifications-master-data-services.md).</span></span>|  
|<span data-ttu-id="fb35a-115">El estado de la versión del modelo cambia</span><span class="sxs-lookup"><span data-stu-id="fb35a-115">Model version status changes</span></span>|<span data-ttu-id="fb35a-116">Cada vez que el estado de una versión del modelo cambia, los usuarios que son administradores de modelo reciben notificaciones automáticamente.</span><span class="sxs-lookup"><span data-stu-id="fb35a-116">Each time a model version's status changes, users that are model administrators receive notifications automatically.</span></span> <span data-ttu-id="fb35a-117">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="fb35a-117">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>|  
  
## <a name="system-settings"></a><span data-ttu-id="fb35a-118">Configuración del sistema</span><span class="sxs-lookup"><span data-stu-id="fb35a-118">System Settings</span></span>  
 <span data-ttu-id="fb35a-119">Hay opciones de [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] que afectan a las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="fb35a-119">There are settings in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] that affect notifications.</span></span> <span data-ttu-id="fb35a-120">Puede ajustarlas en [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] o directamente en la tabla Configuración del sistema de la base de datos de [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fb35a-120">You can adjust these settings in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] or directly in the System Settings table in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="fb35a-121">Para obtener más información, vea [Configuración del sistema &#40;Master Data Services&#41;](../../2014/master-data-services/system-settings-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="fb35a-121">For more information, see [System Settings &#40;Master Data Services&#41;](../../2014/master-data-services/system-settings-master-data-services.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="fb35a-122">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="fb35a-122">Related Tasks</span></span>  
  
|<span data-ttu-id="fb35a-123">Descripción de la tarea</span><span class="sxs-lookup"><span data-stu-id="fb35a-123">Task Description</span></span>|<span data-ttu-id="fb35a-124">Tema</span><span class="sxs-lookup"><span data-stu-id="fb35a-124">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="fb35a-125">Configurar [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] para enviar notificaciones por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="fb35a-125">Configure [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] to send email notifications.</span></span>|[<span data-ttu-id="fb35a-126">Configurar notificaciones por correo electrónico &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="fb35a-126">Configure Email Notifications &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/configure-email-notifications-master-data-services.md)|  
|<span data-ttu-id="fb35a-127">Configurar [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] para enviar notificaciones cuando cambien los valores de atributo.</span><span class="sxs-lookup"><span data-stu-id="fb35a-127">Configure [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] to send notifications when attribute values change.</span></span>|[<span data-ttu-id="fb35a-128">Configurar reglas de negocios para enviar notificaciones &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="fb35a-128">Configure Business Rules to Send Notifications &#40;Master Data Services&#41;</span></span>](configure-business-rules-to-send-notifications-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="fb35a-129">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="fb35a-129">Related Content</span></span>  
  
-   [<span data-ttu-id="fb35a-130">Reglas de negocios &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="fb35a-130">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)  
  
-   [<span data-ttu-id="fb35a-131">Versiones &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="fb35a-131">Versions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/versions-master-data-services.md)  
  
-   [<span data-ttu-id="fb35a-132">Solucionar problemas de notificaciones de correo electrónico (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="fb35a-132">Troubleshooting Email Notifications (Master Data Services)</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/troubleshooting-email-notifications-master-data-services.aspx)  
  
  
