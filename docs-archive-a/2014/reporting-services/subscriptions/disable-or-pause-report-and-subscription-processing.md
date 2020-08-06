---
title: Pausar el procesamiento de informes y suscripciones | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- pausing schedules
- subscriptions [Reporting Services], pausing
- report processing [Reporting Services], pausing
- shared data sources [Reporting Services]
- pausing subscription processing
- pausing report processing
- temporarily stopping report processing
- disabling shared data sources
- roles [Reporting Services], modifying
- shared schedules [Reporting Services], pausing
ms.assetid: 3cf9a240-24cc-46d4-bec6-976f82d8f830
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1607637630c507588602dd7e566917ce1eeb6080
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747963"
---
# <a name="pause-report-and-subscription-processing"></a><span data-ttu-id="c4682-102">Pausar el procesamiento de informes y suscripciones</span><span class="sxs-lookup"><span data-stu-id="c4682-102">Pause Report and Subscription Processing</span></span>
  <span data-ttu-id="c4682-103">No es posible pausar un informe o una suscripción directamente.</span><span class="sxs-lookup"><span data-stu-id="c4682-103">You cannot pause a report or subscription directly.</span></span> <span data-ttu-id="c4682-104">No obstante, se puede interrumpir su procesamiento antes del inicio del proceso o cuando se realiza una conexión al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="c4682-104">However, you can interrupt report and subscription processing prior to the process starting or when a data source connection is made.</span></span> <span data-ttu-id="c4682-105">También es posible impedir el procesamiento de un informe o una suscripción haciendo que los usuarios no puedan obtener acceso a los mismos.</span><span class="sxs-lookup"><span data-stu-id="c4682-105">You can also prevent a report or subscription from processing by making it inaccessible to users.</span></span>  
  
 <span data-ttu-id="c4682-106">Puede utilizar las siguientes estrategias para impedir temporalmente que se lleve a cabo un proceso.</span><span class="sxs-lookup"><span data-stu-id="c4682-106">The following strategies can be used to temporarily prevent a process from occurring.</span></span>  
  
## <a name="modify-role-assignments-to-prevent-access"></a><span data-ttu-id="c4682-107">Modificar asignaciones de roles para impedir el acceso</span><span class="sxs-lookup"><span data-stu-id="c4682-107">Modify Role Assignments to Prevent Access</span></span>  
 <span data-ttu-id="c4682-108">La mejor manera de hacer que un informe no esté disponible es eliminar temporalmente la asignación de roles que ofrece acceso al informe en cuestión.</span><span class="sxs-lookup"><span data-stu-id="c4682-108">The best way to make a report unavailable is to temporarily remove the role assignment that provides access to the report.</span></span> <span data-ttu-id="c4682-109">Este enfoque es válido para todos los informes, independientemente de cómo se efectúe la conexión al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="c4682-109">This approach can be used on all reports regardless of how the data source connection is made.</span></span> <span data-ttu-id="c4682-110">Esta opción afecta solo al informe, no al funcionamiento de otros informes o elementos.</span><span class="sxs-lookup"><span data-stu-id="c4682-110">This approach targets only the report, without affecting the operation of other reports or items.</span></span>  
  
 <span data-ttu-id="c4682-111">Para eliminar la asignación de roles, abra la página de propiedades Seguridad del informe desde el Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="c4682-111">To remove the role assignment, open the Security Properties page of the report in Report Manager.</span></span> <span data-ttu-id="c4682-112">Si el informe hereda la seguridad de otro informe primario, haga clic en **Editar seguridad del elemento** para crear una directiva de seguridad restrictiva que pase por alto las asignaciones de roles que ofrecen un acceso total (por ejemplo, se puede quitar una asignación de roles que conceda acceso a Todos y mantener la asignación que ofrezca acceso a un grupo reducido de usuarios, como los Administradores).</span><span class="sxs-lookup"><span data-stu-id="c4682-112">If the report inherits security from a parent, you can click **Edit Item Security** to create a restrictive security policy that omits role assignments that provide widespread access (for example, you can remove a role assignment that provides access to Everyone, and keep the role assignment that provides access to a small group of users, such as Administrators).</span></span>  
  
## <a name="disable-a-shared-data-source"></a><span data-ttu-id="c4682-113">Deshabilitar un origen de datos compartido</span><span class="sxs-lookup"><span data-stu-id="c4682-113">Disable a Shared Data Source</span></span>  
 <span data-ttu-id="c4682-114">Una de las ventajas de utilizar orígenes de datos compartidos consiste en la posibilidad de deshabilitarlos para evitar la ejecución de un informe o una suscripción controlada por datos.</span><span class="sxs-lookup"><span data-stu-id="c4682-114">One advantage to using shared data sources is that you can disable it to prevent a report or data-driven subscription from running.</span></span> <span data-ttu-id="c4682-115">Al deshabilitar un origen de datos compartido, el informe se desconecta de su origen externo.</span><span class="sxs-lookup"><span data-stu-id="c4682-115">Disabling a shared data source disconnects the report from its external source.</span></span> <span data-ttu-id="c4682-116">Mientras está deshabilitado, el origen de datos deja de estar disponible para todos los informes y las suscripciones que lo utilizan.</span><span class="sxs-lookup"><span data-stu-id="c4682-116">While it is disabled, the data source is unavailable to all reports and subscriptions that use it.</span></span> <span data-ttu-id="c4682-117">Para deshabilitar un origen de datos compartido, abra dicho origen desde el Administrador de informes y desactive la casilla **Habilitar este origen de datos** .</span><span class="sxs-lookup"><span data-stu-id="c4682-117">To disable a shared data source, open the data source in Report Manager and clear the **Enable this data source** check box.</span></span>  
  
 <span data-ttu-id="c4682-118">Tenga en cuenta que el informe se carga igualmente aunque el origen de datos no esté disponible.</span><span class="sxs-lookup"><span data-stu-id="c4682-118">Note that the report still loads even if the data source is unavailable.</span></span> <span data-ttu-id="c4682-119">El informe no contiene datos, pero los usuarios que dispongan de los permisos adecuados pueden tener acceso a las páginas de propiedades, a la configuración de seguridad, al historial del informe y a la información de suscripción asociada al informe.</span><span class="sxs-lookup"><span data-stu-id="c4682-119">The report does not contain data, but users with appropriate permissions can access the property pages, security settings, report history, and subscription information associated with the report.</span></span>  
  
## <a name="pause-a-shared-schedule"></a><span data-ttu-id="c4682-120">Pausar una programación compartida</span><span class="sxs-lookup"><span data-stu-id="c4682-120">Pause a Shared Schedule</span></span>  
 <span data-ttu-id="c4682-121">Cuando un informe o una suscripción se ejecutan desde una programación compartida, es posible pausar la programación para evitar el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="c4682-121">If a report or subscription runs from a shared schedule, you can pause the schedule to prevent processing.</span></span> <span data-ttu-id="c4682-122">Cualquier proceso de informes o suscripciones controlado por una programación se pospone hasta que se vuelve a reanudar la programación.</span><span class="sxs-lookup"><span data-stu-id="c4682-122">All report and subscription processing that is driven by the schedule is deferred until the schedule is resumed.</span></span> <span data-ttu-id="c4682-123">Para obtener más información, vea [pausar y reanudar programaciones compartidas](schedules.md).</span><span class="sxs-lookup"><span data-stu-id="c4682-123">For more information, see [Pause and Resume Shared Schedules](schedules.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4682-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c4682-124">See Also</span></span>  
 <span data-ttu-id="c4682-125">[Servidor de informes de Reporting Services &#40;modo nativo&#41;](../report-server/reporting-services-report-server-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="c4682-125">[Reporting Services Report Server &#40;Native Mode&#41;](../report-server/reporting-services-report-server-native-mode.md) </span></span>  
 <span data-ttu-id="c4682-126">[Administrador de informes &#40;Modo nativo de SSRS&#41;](../report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="c4682-126">[Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md) </span></span>  
 [<span data-ttu-id="c4682-127">Página de propiedades de seguridad, elementos &#40;Administrador de informes&#41;</span><span class="sxs-lookup"><span data-stu-id="c4682-127">Security Properties Page, Items &#40;Report Manager&#41;</span></span>](../security-properties-page-items-report-manager.md)  
  
  
