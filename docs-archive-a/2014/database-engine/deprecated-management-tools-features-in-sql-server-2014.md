---
title: Características desusadas de las herramientas de administración de SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: a08d1354-cc91-4ab7-a73f-3ad815af3d5a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 484e4078e25249e17a1d8b87426a395c3cfa1725
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670549"
---
# <a name="deprecated-management-tools-features-in-sql-server-2014"></a><span data-ttu-id="c1b90-102">Características desusadas de las herramientas de administración de SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="c1b90-102">Deprecated Management Tools Features in SQL Server 2014</span></span>
  <span data-ttu-id="c1b90-103">En este tema se describen las características desusadas de las herramientas de administración que siguen estando disponibles en [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1b90-103">This topic describes the deprecated Management Tools features that are still available in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="c1b90-104">Está previsto quitar estas características en una futura versión de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1b90-104">These features are scheduled to be removed in a future release of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c1b90-105">Las características en desuso no se deben usar en nuevas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="c1b90-105">Deprecated features should not be used in new applications.</span></span>  
  
|<span data-ttu-id="c1b90-106">Característica</span><span class="sxs-lookup"><span data-stu-id="c1b90-106">Feature</span></span>|<span data-ttu-id="c1b90-107">Fase de la eliminación en la que se encuentra</span><span class="sxs-lookup"><span data-stu-id="c1b90-107">Deprecation stage</span></span>|  
|-------------|-----------------------|  
|[!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)]<span data-ttu-id="c1b90-108">API de servidor registrada</span><span class="sxs-lookup"><span data-stu-id="c1b90-108">Registered Server API</span></span>|<span data-ttu-id="c1b90-109">Anuncio</span><span class="sxs-lookup"><span data-stu-id="c1b90-109">Announcement</span></span>|  
|<span data-ttu-id="c1b90-110">sqlps.exe</span><span class="sxs-lookup"><span data-stu-id="c1b90-110">sqlps.exe</span></span>|<span data-ttu-id="c1b90-111">Advertencia</span><span class="sxs-lookup"><span data-stu-id="c1b90-111">Warning</span></span>|  
|<span data-ttu-id="c1b90-112">osql.exe</span><span class="sxs-lookup"><span data-stu-id="c1b90-112">osql.exe</span></span>|<span data-ttu-id="c1b90-113">Advertencia</span><span class="sxs-lookup"><span data-stu-id="c1b90-113">Warning</span></span>|  
|<span data-ttu-id="c1b90-114">SQLMail</span><span class="sxs-lookup"><span data-stu-id="c1b90-114">SQLMail</span></span>|<span data-ttu-id="c1b90-115">Advertencia</span><span class="sxs-lookup"><span data-stu-id="c1b90-115">Warning</span></span>|  
|<span data-ttu-id="c1b90-116">Clase SMO: clase Microsoft.SQLServer.Management.Smo.Information</span><span class="sxs-lookup"><span data-stu-id="c1b90-116">SMO class: Microsoft.SQLServer.Management.Smo.Information class</span></span>|<span data-ttu-id="c1b90-117">Anuncio</span><span class="sxs-lookup"><span data-stu-id="c1b90-117">Announcement</span></span>|  
|<span data-ttu-id="c1b90-118">Clase SMO: clase Microsoft.SQLServer.Management.Smo.Settings</span><span class="sxs-lookup"><span data-stu-id="c1b90-118">SMO class: Microsoft.SQLServer.Management.Smo.Settings class</span></span>|<span data-ttu-id="c1b90-119">Anuncio</span><span class="sxs-lookup"><span data-stu-id="c1b90-119">Announcement</span></span>|  
|<span data-ttu-id="c1b90-120">Clase SMO: clase Microsoft.SQLServer.Management.Smo.DatabaseOptions</span><span class="sxs-lookup"><span data-stu-id="c1b90-120">SMO Class: Microsoft.SQLServer.Management.Smo.DatabaseOptions class</span></span>|<span data-ttu-id="c1b90-121">Anuncio</span><span class="sxs-lookup"><span data-stu-id="c1b90-121">Announcement</span></span>|  
|<span data-ttu-id="c1b90-122">Clase SMO: propiedad Microsoft.SqlServer.Management.Smo.DatabaseDdlTrigger.NotForReplication</span><span class="sxs-lookup"><span data-stu-id="c1b90-122">SMO Class: Microsoft.SqlServer.Management.Smo.DatabaseDdlTrigger.NotForReplication property</span></span>|<span data-ttu-id="c1b90-123">Anuncio</span><span class="sxs-lookup"><span data-stu-id="c1b90-123">Announcement</span></span>|  
|<span data-ttu-id="c1b90-124">El sistema del proyecto de base de datos, incluida la integración del control de código fuente, en SSMS</span><span class="sxs-lookup"><span data-stu-id="c1b90-124">The Database Project System, including source-control integration, in SSMS</span></span>|<span data-ttu-id="c1b90-125">Anuncio</span><span class="sxs-lookup"><span data-stu-id="c1b90-125">Announcement</span></span>|  
|<span data-ttu-id="c1b90-126">Notificaciones NET SEND (Agente[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="c1b90-126">Net send notifications ([!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent)</span></span>|<span data-ttu-id="c1b90-127">Anuncio</span><span class="sxs-lookup"><span data-stu-id="c1b90-127">Announcement</span></span>|  
|<span data-ttu-id="c1b90-128">Notificaciones mediante buscapersonas (Agente[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="c1b90-128">Pager notifications ([!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent)</span></span>|<span data-ttu-id="c1b90-129">Anuncio</span><span class="sxs-lookup"><span data-stu-id="c1b90-129">Announcement</span></span>|  
|<span data-ttu-id="c1b90-130">Subsistema ActiveX (Agente[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="c1b90-130">The ActiveX subsystem ([!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent)</span></span>|<span data-ttu-id="c1b90-131">Anuncio</span><span class="sxs-lookup"><span data-stu-id="c1b90-131">Announcement</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c1b90-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c1b90-132">See Also</span></span>  
 [<span data-ttu-id="c1b90-133">Compatibilidad con versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="c1b90-133">Backward Compatibility</span></span>](../../2014/getting-started/backward-compatibility.md)  
  
  
