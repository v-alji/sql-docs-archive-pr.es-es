---
title: Configurar reglas de negocios para enviar notificaciones (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- business rules [Master Data Services], configuring notifications
- e-mail [Master Data Services], configuring business rules
- notifications [Master Data Services], configuring business rules
ms.assetid: b24f7b11-ab53-4642-999c-e17b543b3558
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: cb1a12167dffe123e55760f031e21499fe22a945
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678236"
---
# <a name="configure-business-rules-to-send-notifications-master-data-services"></a><span data-ttu-id="bf87f-102">Configurar reglas de negocios para enviar notificaciones (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="bf87f-102">Configure Business Rules to Send Notifications (Master Data Services)</span></span>
  <span data-ttu-id="bf87f-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], configure reglas de negocios para enviar notificaciones cuando desee notificar a los usuarios los cambios de los valores de los atributos.</span><span class="sxs-lookup"><span data-stu-id="bf87f-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], configure business rules to send notifications when you want to notify users about attribute value changes.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bf87f-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="bf87f-104">Prerequisites</span></span>  
 <span data-ttu-id="bf87f-105">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="bf87f-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="bf87f-106">Debe disponer del permiso para tener acceso a las áreas funcionales de **Permisos de usuario y de grupo** y de **Administración del sistema** .</span><span class="sxs-lookup"><span data-stu-id="bf87f-106">You must have permission to access the **System Administration** and **User and Group Permissions** functional areas.</span></span> <span data-ttu-id="bf87f-107">Si no tiene permiso para el área funcional de **Permisos de usuario y grupo** , no puede ver la lista de usuarios y grupos a los que enviar las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="bf87f-107">If you do not have permission to the **User and Group Permissions** functional area, you cannot view the list of users and groups to send notifications to.</span></span>  
  
-   <span data-ttu-id="bf87f-108">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="bf87f-108">You must be a model administrator.</span></span> <span data-ttu-id="bf87f-109">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="bf87f-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="bf87f-110">Ya debe existir una regla de negocio que use una acción de validación.</span><span class="sxs-lookup"><span data-stu-id="bf87f-110">A business rule that uses a validation action must already exist.</span></span> <span data-ttu-id="bf87f-111">Para obtener más información, consulte [Crear y publicar una regla de negocios &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="bf87f-111">For more information, see [Create and Publish a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="bf87f-112">El usuario o grupo que recibe la notificación debe tener al menos permiso de **Solo lectura** para el atributo que produce un error en la validación.</span><span class="sxs-lookup"><span data-stu-id="bf87f-112">The user or group that receives the notification must have at least **Read-only** permission to the attribute that fails validation.</span></span> <span data-ttu-id="bf87f-113">Los usuarios o grupos a los que se haya denegado explícita o implícitamente el permiso para el atributo recibirán el correo electrónico pero no podrán obtener acceso al atributo en [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf87f-113">Users or groups that are explicitly or implicitly denied permission to the attribute will receive the email but will not be able to access the attribute in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
-   <span data-ttu-id="bf87f-114">Si el correo se envía a un grupo, solo los miembros del mismo que hayan tenido acceso a [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] recibirán el correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="bf87f-114">If mail is sent to a group, only members of the group that have accessed [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] will get the email.</span></span>  
  
### <a name="to-configure-business-rules-to-send-notifications"></a><span data-ttu-id="bf87f-115">Configurar reglas de negocios para enviar notificaciones</span><span class="sxs-lookup"><span data-stu-id="bf87f-115">To configure business rules to send notifications</span></span>  
  
1.  <span data-ttu-id="bf87f-116">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="bf87f-116">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="bf87f-117">En la barra de menús, seleccione **Administrar** y haga clic en **Reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="bf87f-117">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="bf87f-118">En la página **Mantenimiento de reglas de negocios** , en la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="bf87f-118">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="bf87f-119">En la lista **Entidad** , seleccione una entidad.</span><span class="sxs-lookup"><span data-stu-id="bf87f-119">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="bf87f-120">En la lista **tipo de miembro** , seleccione un tipo de miembro.</span><span class="sxs-lookup"><span data-stu-id="bf87f-120">From the **Member Type** list, select a type of member.</span></span>  
  
6.  <span data-ttu-id="bf87f-121">En la lista **Atributo** , seleccione un atributo o deje el valor predeterminado de **Todos**.</span><span class="sxs-lookup"><span data-stu-id="bf87f-121">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="bf87f-122">En la cuadrícula, en la fila de la regla de negocios, haga doble clic en el campo **notificación** .</span><span class="sxs-lookup"><span data-stu-id="bf87f-122">In the grid, in the row for the business rule, double-click the **Notification** field.</span></span>  
  
8.  <span data-ttu-id="bf87f-123">En el submenú, haga clic en un usuario o un grupo al que desea enviar la notificación por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="bf87f-123">From the sub-menu, click a user or group to send the email notification to.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="bf87f-124">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="bf87f-124">Next Steps</span></span>  
  
-   <span data-ttu-id="bf87f-125">Aplique las reglas de negocios a los datos siguiendo uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="bf87f-125">Apply business rules to data by following one of these procedures:</span></span>  
  
    -   [<span data-ttu-id="bf87f-126">Validar miembros específicos con las reglas de negocios &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="bf87f-126">Validate Specific Members against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-specific-members-against-business-rules-master-data-services.md)  
  
    -   [<span data-ttu-id="bf87f-127">Validar una versión con las reglas de negocios &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="bf87f-127">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
-   <span data-ttu-id="bf87f-128">Configure el protocolo de correo electrónico de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="bf87f-128">Configure the email protocol as follows:</span></span>  
  
    -   [<span data-ttu-id="bf87f-129">Configurar notificaciones por correo electrónico &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="bf87f-129">Configure Email Notifications &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/configure-email-notifications-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="bf87f-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bf87f-130">See Also</span></span>  
 <span data-ttu-id="bf87f-131">[Notificaciones &#40;Master Data Services&#41;](../../2014/master-data-services/notifications-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="bf87f-131">[Notifications &#40;Master Data Services&#41;](../../2014/master-data-services/notifications-master-data-services.md) </span></span>  
 [<span data-ttu-id="bf87f-132">Configurar notificaciones por correo electrónico &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="bf87f-132">Configure Email Notifications &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/configure-email-notifications-master-data-services.md)  
  
  
