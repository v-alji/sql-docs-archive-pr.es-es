---
title: 'Propiedades del trabajo: nuevo trabajo (página notificaciones) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.job.notifications.f1
ms.assetid: ed393cbd-4496-4399-a177-e5baa92fb689
author: stevestein
ms.author: sstein
ms.openlocfilehash: 30eca88943b48bd81bd38e236711d19ee7ec4503
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663266"
---
# <a name="job-properties-new-job-notifications-page"></a><span data-ttu-id="de258-102">Propiedades del trabajo: Nuevo trabajo (página Notificaciones)</span><span class="sxs-lookup"><span data-stu-id="de258-102">Job Properties: New Job (Notifications Page)</span></span>
  <span data-ttu-id="de258-103">Use esta página para establecer acciones [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que el agente debe realizar cuando se completa el trabajo.</span><span class="sxs-lookup"><span data-stu-id="de258-103">Use this page to set actions for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to perform when the job completes.</span></span>  
  
## <a name="options"></a><span data-ttu-id="de258-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="de258-104">Options</span></span>  
 <span data-ttu-id="de258-105">**Por**</span><span class="sxs-lookup"><span data-stu-id="de258-105">**E-mail**</span></span>  
 <span data-ttu-id="de258-106">Seleccione esta opción para enviar correo electrónico cuando el trabajo finalice.</span><span class="sxs-lookup"><span data-stu-id="de258-106">Select this option to send e-mail when the job completes.</span></span> <span data-ttu-id="de258-107">Después de seleccionar esta opción, elija el operador al que se va a notificar y la condición que activará la notificación: **Si el trabajo tiene éxito**; **Si el trabajo no tiene éxito**; o **Si el trabajo termina**.</span><span class="sxs-lookup"><span data-stu-id="de258-107">After selecting this option, choose the operator to notify and the condition that will trigger the notification: **When the job succeeds**; **When the job fails**; or **When the job completes**.</span></span>  
  
 <span data-ttu-id="de258-108">**Page**</span><span class="sxs-lookup"><span data-stu-id="de258-108">**Page**</span></span>  
 <span data-ttu-id="de258-109">Seleccione esta opción para enviar correo electrónico al buscapersonas de un operador cuando el trabajo finalice.</span><span class="sxs-lookup"><span data-stu-id="de258-109">Select this option to send e-mail to an operator's pager when the job completes.</span></span> <span data-ttu-id="de258-110">Después de seleccionar esta opción, especifique el operador al que se va a notificar y la condición que activará la notificación: **Si el trabajo tiene éxito**; **Si el trabajo no tiene éxito**; o **Si el trabajo termina**.</span><span class="sxs-lookup"><span data-stu-id="de258-110">After selecting this option, specify the operator to notify and the condition that will trigger the notification: **When the job succeeds**; **When the job fails**; or **When the job completes**.</span></span>  
  
 <span data-ttu-id="de258-111">**Net send**</span><span class="sxs-lookup"><span data-stu-id="de258-111">**Net send**</span></span>  
 <span data-ttu-id="de258-112">Seleccione esta opción para utilizar NET SEND para avisar a un operador cuando el trabajo finalice.</span><span class="sxs-lookup"><span data-stu-id="de258-112">Select this option to use net send to notify an operator when the job completes.</span></span> <span data-ttu-id="de258-113">Después de seleccionar esta opción, especifique el operador al que se va a notificar y la condición que activará la notificación: **Si el trabajo tiene éxito**; **Si el trabajo no tiene éxito**; o **Si el trabajo termina**.</span><span class="sxs-lookup"><span data-stu-id="de258-113">After selecting this option, specify the operator to notify and the condition that will trigger the notification: **When the job succeeds**; **When the job fails**; or **When the job completes**.</span></span>  
  
 <span data-ttu-id="de258-114">**Escribir en el registro de eventos de aplicación Windows**</span><span class="sxs-lookup"><span data-stu-id="de258-114">**Write to the Windows Application event log**</span></span>  
 <span data-ttu-id="de258-115">Seleccione esta opción para escribir una entrada en el registro de eventos de la aplicación cuando el trabajo finalice.</span><span class="sxs-lookup"><span data-stu-id="de258-115">Select this option to write an entry in the application event log when the job completes.</span></span> <span data-ttu-id="de258-116">Después de seleccionar esta opción, especifique la condición que hará que se escriba la entrada: **Si el trabajo tiene éxito**; **Si el trabajo no tiene éxito**; o **Si el trabajo termina**.</span><span class="sxs-lookup"><span data-stu-id="de258-116">After selecting this option, specify the condition that will cause the entry to be written: **When the job succeeds**; **When the job fails**; or **When the job completes**.</span></span>  
  
 <span data-ttu-id="de258-117">**Eliminar automáticamente el trabajo**</span><span class="sxs-lookup"><span data-stu-id="de258-117">**Automatically delete job**</span></span>  
 <span data-ttu-id="de258-118">Seleccione esta opción para eliminar el trabajo cuando éste finalice.</span><span class="sxs-lookup"><span data-stu-id="de258-118">Select this option to delete the job when the job completes.</span></span> <span data-ttu-id="de258-119">Después de seleccionar esta opción, especifique la condición que activará la eliminación del trabajo: **Si el trabajo tiene éxito**; **Si el trabajo no tiene éxito**; o **Si el trabajo termina**.</span><span class="sxs-lookup"><span data-stu-id="de258-119">After selecting this option, specify the condition that will trigger deletion of the job: **When the job succeeds**; **When the job fails**; or **When the job completes**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de258-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="de258-120">See Also</span></span>  
 <span data-ttu-id="de258-121">[Implementar trabajos](implement-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="de258-121">[Implement Jobs](implement-jobs.md) </span></span>  
 [<span data-ttu-id="de258-122">Configurar el Agente SQL Server para que use el Correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="de258-122">Configure SQL Server Agent Mail to Use Database Mail</span></span>](../../relational-databases/database-mail/configure-sql-server-agent-mail-to-use-database-mail.md)  
  
  
