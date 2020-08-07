---
title: Especificar respuestas de trabajos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], responses
- SQL Server Agent jobs, responses
- actions [SQL Server Agent jobs]
- responding to jobs
ms.assetid: 050242e1-9b79-4ade-91a9-580707b9d2d9
author: stevestein
ms.author: sstein
ms.openlocfilehash: d41c5e1552a1ff16343bdb2c4e9feaafb51c5783
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743905"
---
# <a name="specify-job-responses"></a><span data-ttu-id="ac2f3-102">Especificar respuestas de trabajos</span><span class="sxs-lookup"><span data-stu-id="ac2f3-102">Specify Job Responses</span></span>
  <span data-ttu-id="ac2f3-103">Las respuestas de trabajos especifican acciones que realizará el servicio del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tras completar un trabajo.</span><span class="sxs-lookup"><span data-stu-id="ac2f3-103">Job responses specify actions that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service will take after a job completes.</span></span> <span data-ttu-id="ac2f3-104">Estas respuestas permiten a los administradores de las bases de datos saber cuándo se completan los trabajos y con qué frecuencia se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="ac2f3-104">Job responses ensure that database administrators know when jobs complete and how frequently they run.</span></span> <span data-ttu-id="ac2f3-105">Algunas respuestas de trabajos típicas son:</span><span class="sxs-lookup"><span data-stu-id="ac2f3-105">Typical job responses include:</span></span>  
  
-   <span data-ttu-id="ac2f3-106">Notificar al operador mediante correo electrónico, localizador electrónico o un mensaje de **net send** .</span><span class="sxs-lookup"><span data-stu-id="ac2f3-106">Notifying the operator by using e-mail, electronic paging, or a **net send** message.</span></span>  
  
     <span data-ttu-id="ac2f3-107">Use una de estas respuestas de trabajo si el operador debe realizar una acción de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ac2f3-107">Use one of these job responses if the operator must perform a follow-up action.</span></span> <span data-ttu-id="ac2f3-108">Por ejemplo, si un trabajo de copia de seguridad se realiza correctamente, se debe notificar de ello al operador para que quite la cinta de copia de seguridad y la guarde en un lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="ac2f3-108">For example, if a backup job completes successfully, the operator must be notified to remove the backup tape and store it in a safe location.</span></span>  
  
-   <span data-ttu-id="ac2f3-109">Escribir un mensaje de evento en el registro de aplicación Windows.</span><span class="sxs-lookup"><span data-stu-id="ac2f3-109">Writing an event message to the Windows application log.</span></span>  
  
     <span data-ttu-id="ac2f3-110">Puede utilizar esta respuesta solo para trabajos con errores.</span><span class="sxs-lookup"><span data-stu-id="ac2f3-110">You can use this response only for failed jobs.</span></span>  
  
-   <span data-ttu-id="ac2f3-111">Eliminar automáticamente el trabajo.</span><span class="sxs-lookup"><span data-stu-id="ac2f3-111">Automatically deleting the job.</span></span>  
  
     <span data-ttu-id="ac2f3-112">Utilice esta respuesta de trabajo si está seguro de que no necesita volver a ejecutar este trabajo.</span><span class="sxs-lookup"><span data-stu-id="ac2f3-112">Use this job response if you are certain that you do not need to rerun this job.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="ac2f3-113">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="ac2f3-113">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ac2f3-114">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ac2f3-114">**Description**</span></span>|<span data-ttu-id="ac2f3-115">**Tema.**</span><span class="sxs-lookup"><span data-stu-id="ac2f3-115">**Topic**</span></span>|  
|<span data-ttu-id="ac2f3-116">Describe cómo notificar a un operador el estado de un trabajo.</span><span class="sxs-lookup"><span data-stu-id="ac2f3-116">Describes how to notify an operator of job status.</span></span>|[<span data-ttu-id="ac2f3-117">Notify an Operator of Job Status</span><span class="sxs-lookup"><span data-stu-id="ac2f3-117">Notify an Operator of Job Status</span></span>](notify-an-operator-of-job-status.md)|  
|<span data-ttu-id="ac2f3-118">Describe cómo escribir el estado de un trabajo en el registro de aplicación Windows.</span><span class="sxs-lookup"><span data-stu-id="ac2f3-118">Describes how to write job status to the Windows application log.</span></span>|[<span data-ttu-id="ac2f3-119">Write the Job Status to the Windows Application Log</span><span class="sxs-lookup"><span data-stu-id="ac2f3-119">Write the Job Status to the Windows Application Log</span></span>](../../reporting-services/report-server/windows-application-log.md)|  
  
## <a name="see-also"></a><span data-ttu-id="ac2f3-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ac2f3-120">See Also</span></span>  
 [<span data-ttu-id="ac2f3-121">Supervisar y responder a eventos</span><span class="sxs-lookup"><span data-stu-id="ac2f3-121">Monitor and Respond to Events</span></span>](monitor-and-respond-to-events.md)  
  
  
