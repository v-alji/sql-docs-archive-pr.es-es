---
title: Propiedades de Agente SQL Server (página Historial) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.history.f1
ms.assetid: dc73734c-b3c3-407f-bbd1-8714b4fa47b0
author: stevestein
ms.author: sstein
ms.openlocfilehash: d67ff3da97e11292abcac03958fe1e423b35d7d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676301"
---
# <a name="sql-server-agent-properties-history-page"></a><span data-ttu-id="e6812-102">Propiedades de Agente SQL Server (página Historial)</span><span class="sxs-lookup"><span data-stu-id="e6812-102">SQL Server Agent Properties (History Page)</span></span>
  <span data-ttu-id="e6812-103">Utilice esta página para ver y modificar la configuración para administrar el [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] registro del historial de servicios del agente.</span><span class="sxs-lookup"><span data-stu-id="e6812-103">Use this page to view and modify settings for managing the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service history log.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e6812-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="e6812-104">Options</span></span>  
 <span data-ttu-id="e6812-105">**Limitar tamaño del registro de historial de trabajos**</span><span class="sxs-lookup"><span data-stu-id="e6812-105">**Limit size of job history log**</span></span>  
 <span data-ttu-id="e6812-106">Establece los límites para la cantidad de información del historial de trabajos que el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conserva en el registro.</span><span class="sxs-lookup"><span data-stu-id="e6812-106">Sets limits for the amount of job history information that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent retains in the log.</span></span>  
  
 <span data-ttu-id="e6812-107">**Tamaño máximo del registro de historial de trabajos (filas)**</span><span class="sxs-lookup"><span data-stu-id="e6812-107">**Maximum job history log size (in rows)**</span></span>  
 <span data-ttu-id="e6812-108">Establece el número máximo de filas que conserva el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e6812-108">Sets the maximum number of rows that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent retains.</span></span> <span data-ttu-id="e6812-109">Cuando el registro crece para contener este número de filas, el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] elimina las filas más antiguas del registro a medida que se van incluyendo filas nuevas.</span><span class="sxs-lookup"><span data-stu-id="e6812-109">When the log grows to contain this number of rows, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent removes the oldest rows in the log as new rows are entered.</span></span>  
  
 <span data-ttu-id="e6812-110">**Máximo de filas de historial de trabajos por trabajo**</span><span class="sxs-lookup"><span data-stu-id="e6812-110">**Maximum job history rows per job**</span></span>  
 <span data-ttu-id="e6812-111">Establece el número máximo de filas que el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conserva por trabajo.</span><span class="sxs-lookup"><span data-stu-id="e6812-111">Sets the maximum number of rows that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent retains per job.</span></span> <span data-ttu-id="e6812-112">Cuando el historial para un trabajo determinado crece para contener este número de filas, el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] quita las filas más antiguas del registro a medida que se van incluyendo filas nuevas.</span><span class="sxs-lookup"><span data-stu-id="e6812-112">When the history for a particular job grows to contain this number of rows, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent removes the oldest rows in the log as new rows are entered.</span></span>  
  
 <span data-ttu-id="e6812-113">**Quitar historial del agente**</span><span class="sxs-lookup"><span data-stu-id="e6812-113">**Remove agent history**</span></span>  
 <span data-ttu-id="e6812-114">Especifica que el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] quitará las entradas que han permanecido en el registro más tiempo que el especificado.</span><span class="sxs-lookup"><span data-stu-id="e6812-114">Specifies that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent will remove entries that have been in the log longer than a specified length of time.</span></span> <span data-ttu-id="e6812-115">Es una ejecución única para quitar el historial.</span><span class="sxs-lookup"><span data-stu-id="e6812-115">This is a one-time execution to remove the history.</span></span> <span data-ttu-id="e6812-116">Si es necesaria la repetición de un trabajo, cree y programe un plan de mantenimiento con un trabajo de limpieza.</span><span class="sxs-lookup"><span data-stu-id="e6812-116">If a reoccurring job is needed, create and schedule a maintenance plan with a cleanup job.</span></span>  
  
 <span data-ttu-id="e6812-117">**Anterior a**</span><span class="sxs-lookup"><span data-stu-id="e6812-117">**Older than**</span></span>  
 <span data-ttu-id="e6812-118">Establece el tiempo que el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conservará las entradas.</span><span class="sxs-lookup"><span data-stu-id="e6812-118">Sets the amount of time that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent will retain entries.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6812-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e6812-119">See Also</span></span>  
 [<span data-ttu-id="e6812-120">Registro de errores del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="e6812-120">SQL Server Agent Error Log</span></span>](sql-server-agent-error-log.md)  
  
  
