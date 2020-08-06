---
title: Usar mis suscripciones | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- subscriptions [Reporting Services], My Subscriptions page
- My Subscriptions page [Reporting Services]
ms.assetid: e96623ba-677e-4748-8787-f32bed3b5c12
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f3378a65637ad04151cc517fd9047363af954c31
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749028"
---
# <a name="use-my-subscriptions"></a><span data-ttu-id="f033c-102">Usar Mis suscripciones</span><span class="sxs-lookup"><span data-stu-id="f033c-102">Use My Subscriptions</span></span>
  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]<span data-ttu-id="f033c-103">Administrador de informes incluye una página **Mis suscripciones** que organiza todas las suscripciones en un solo lugar.</span><span class="sxs-lookup"><span data-stu-id="f033c-103">Report Manager includes a **My Subscriptions** page that organizes all of your subscriptions into one place.</span></span> <span data-ttu-id="f033c-104">Puede utilizar Mis suscripciones para ver, modificar y eliminar suscripciones existentes.</span><span class="sxs-lookup"><span data-stu-id="f033c-104">You can use My Subscriptions to view, modify, and delete existing subscriptions.</span></span> <span data-ttu-id="f033c-105">Sin embargo, no puede utilizar esta página para crear suscripciones.</span><span class="sxs-lookup"><span data-stu-id="f033c-105">However, you cannot use it to create subscriptions.</span></span>  
  
||  
|-|  
|<span data-ttu-id="f033c-106">**[!INCLUDE[applies](../../includes/applies-md.md)]** Modo nativo de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f033c-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Native mode</span></span>|  
  
 <span data-ttu-id="f033c-107">En Mis suscripciones, puede ordenar las suscripciones por carpeta, informe, descripción, desencadenador, última ejecución o estado.</span><span class="sxs-lookup"><span data-stu-id="f033c-107">Within My Subscriptions, you can sort subscriptions by folder, report, description, trigger, last run, or status.</span></span> <span data-ttu-id="f033c-108">Todos los valores se ordenan alfabéticamente, a excepción de Última ejecución, que utiliza el orden cronológico.</span><span class="sxs-lookup"><span data-stu-id="f033c-108">All values are sorted alphabetically except for Last Run, which is in chronological order.</span></span>  
  
 <span data-ttu-id="f033c-109">Mis suscripciones solo muestra las suscripciones que haya creado.</span><span class="sxs-lookup"><span data-stu-id="f033c-109">My Subscriptions shows only the subscriptions that you create.</span></span> <span data-ttu-id="f033c-110">No enumera las suscripciones que sean propiedad de otros usuarios, aunque el usuario esté agregado como suscriptor a ellas, ni muestra suscripciones controladas por datos.</span><span class="sxs-lookup"><span data-stu-id="f033c-110">It does not list subscriptions that are owned by other users, even if you are added as a subscriber to those subscriptions, nor does it show data-driven subscriptions.</span></span>  
  
 <span data-ttu-id="f033c-111">No puede buscar suscripciones por nombre, ni tampoco basándose en información del desencadenador, información de estado, etc.</span><span class="sxs-lookup"><span data-stu-id="f033c-111">You cannot search for subscriptions by name, nor can you search for subscriptions based on trigger information, status information, and so forth.</span></span> <span data-ttu-id="f033c-112">Para obtener más información, vea [crear, modificar y eliminar suscripciones estándar &#40;Reporting Services en modo nativo&#41;](create-and-manage-subscriptions-for-native-mode-report-servers.md).</span><span class="sxs-lookup"><span data-stu-id="f033c-112">For more information, see [Create, Modify, and Delete Standard Subscriptions &#40;Reporting Services in Native Mode&#41;](create-and-manage-subscriptions-for-native-mode-report-servers.md).</span></span>  
  
## <a name="how-to-use-my-subscriptions"></a><span data-ttu-id="f033c-113">Cómo usar Mis suscripciones</span><span class="sxs-lookup"><span data-stu-id="f033c-113">How to Use My Subscriptions</span></span>  
 <span data-ttu-id="f033c-114">Mis suscripciones se encuentra disponible mediante el Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="f033c-114">My Subscriptions is available through Report Manager.</span></span> <span data-ttu-id="f033c-115">Para obtener acceso a Mis suscripciones, haga clic en **Mis suscripciones** en la barra de herramientas global del Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="f033c-115">To access My Subscriptions, click **My Subscriptions** on the Report Manager global toolbar.</span></span>  
  
## <a name="use-windows-powershell-to-list-mysubscriptions"></a><span data-ttu-id="f033c-116">Usar Windows PowerShell para enumerar MySubscriptions</span><span class="sxs-lookup"><span data-stu-id="f033c-116">Use Windows PowerShell to list MySubscriptions</span></span>  
 <span data-ttu-id="f033c-117">![Contenido relacionado con PowerShell](../media/rs-powershellicon.jpg "Contenido relacionado con PowerShell")</span><span class="sxs-lookup"><span data-stu-id="f033c-117">![PowerShell related content](../media/rs-powershellicon.jpg "PowerShell related content")</span></span>  
  
 <span data-ttu-id="f033c-118">El siguiente script de PowerShell devolverá la lista de suscripciones y propiedades de suscripción del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="f033c-118">The following PowerShell script will return the list of subscriptions and subscription properties for the current user.</span></span> <span data-ttu-id="f033c-119">Para obtener más información, vea [ReportingService2010.ListMySubscriptions (Método)](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.listmysubscriptions.aspx).</span><span class="sxs-lookup"><span data-stu-id="f033c-119">For more information, see [ReportingService2010.ListMySubscriptions Method](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.listmysubscriptions.aspx).</span></span>  
  
```powershell
#server -  all subscriptions of the current user at the given server or site  
$server="[server name]/reportserver"  
$rs2010 = New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential ;  
  
$subscriptions=ListMySubscriptions(ItemPathOrSiteURL)  
$subscriptions | select Path, report, Description, Owner, SubscriptionID, lastexecuted,Status  
#uncomment the following to list all the subscription properties  
#$subscriptions
```  
  
## <a name="see-also"></a><span data-ttu-id="f033c-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f033c-120">See Also</span></span>  
 <span data-ttu-id="f033c-121">[Data-Driven Subscriptions](data-driven-subscriptions.md) </span><span class="sxs-lookup"><span data-stu-id="f033c-121">[Data-Driven Subscriptions](data-driven-subscriptions.md) </span></span>  
 <span data-ttu-id="f033c-122">[Suscripciones y entrega &#40;Reporting Services&#41;](subscriptions-and-delivery-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="f033c-122">[Subscriptions and Delivery &#40;Reporting Services&#41;](subscriptions-and-delivery-reporting-services.md) </span></span>  
 [<span data-ttu-id="f033c-123">Creación y administración de suscripciones para servidores de informes en modo nativo</span><span class="sxs-lookup"><span data-stu-id="f033c-123">Create and Manage Subscriptions for Native Mode Report Servers</span></span>](../create-manage-subscriptions-native-mode-report-servers.md)  
