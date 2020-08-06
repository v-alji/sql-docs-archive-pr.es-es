---
title: MSSQLSERVER_21893 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21893 (Database Engine error)
ms.assetid: 1ab1195a-fe2a-4e06-b871-b177b6bea1fe
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 92479d7727ac2300d6a60d02492667d99a69b022
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675431"
---
# <a name="mssqlserver_21893"></a><span data-ttu-id="6567e-102">MSSQLSERVER_21893</span><span class="sxs-lookup"><span data-stu-id="6567e-102">MSSQLSERVER_21893</span></span>
    
## <a name="details"></a><span data-ttu-id="6567e-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="6567e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6567e-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="6567e-104">Product Name</span></span>|<span data-ttu-id="6567e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6567e-105">SQL Server</span></span>|  
|<span data-ttu-id="6567e-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="6567e-106">Event ID</span></span>|<span data-ttu-id="6567e-107">21893</span><span class="sxs-lookup"><span data-stu-id="6567e-107">21893</span></span>|  
|<span data-ttu-id="6567e-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="6567e-108">Event Source</span></span>|<span data-ttu-id="6567e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6567e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6567e-110">Componente</span><span class="sxs-lookup"><span data-stu-id="6567e-110">Component</span></span>|<span data-ttu-id="6567e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6567e-111">SQLEngine</span></span>|  
|<span data-ttu-id="6567e-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="6567e-112">Symbolic Name</span></span>|<span data-ttu-id="6567e-113">SQLErrorNum21893</span><span class="sxs-lookup"><span data-stu-id="6567e-113">SQLErrorNum21893</span></span>|  
|<span data-ttu-id="6567e-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="6567e-114">Message Text</span></span>|<span data-ttu-id="6567e-115">Los suscriptores (%s) del publicador original "%s" no aparecen como servidores remotos en el publicador redireccionado "%s".</span><span class="sxs-lookup"><span data-stu-id="6567e-115">The subscribers ( %s ) of original publisher '%s' do not appear as remote servers at redirected publisher '%s'.</span></span> <span data-ttu-id="6567e-116">Ejecute `sp_addlinkedserver` en el publicador redirigido para agregar estos suscriptores como servidores remotos.</span><span class="sxs-lookup"><span data-stu-id="6567e-116">Run `sp_addlinkedserver` at the redirected publisher to add these subscribers as remote servers .</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6567e-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="6567e-117">Explanation</span></span>  
 <span data-ttu-id="6567e-118">`sp_validate_redirected_publisher` usa las tablas de metadatos de suscripción de la base de datos del publicador en el servidor remoto para identificar sus suscriptores asociados y comprueba que hay entradas asociadas en master.dbo.sysservers para los suscriptores.</span><span class="sxs-lookup"><span data-stu-id="6567e-118">`sp_validate_redirected_publisher` uses the subscription metadata tables of the publisher database at the remote server to identify its associated subscribers and verifies that there are associated entries in master.dbo.sysservers for the subscribers.</span></span> <span data-ttu-id="6567e-119">Este error se devuelve si ninguno de los suscriptores identificados está presente.</span><span class="sxs-lookup"><span data-stu-id="6567e-119">This error is returned if any of the identified subscribers are not present.</span></span>  
  
 <span data-ttu-id="6567e-120">Este error no se considera irrecuperable.</span><span class="sxs-lookup"><span data-stu-id="6567e-120">This error is not considered a fatal error.</span></span> <span data-ttu-id="6567e-121">Los agentes que encuentran este error lo registrarán como informativo pero no finalizarán, ya que un error que tenga las entradas de suscriptor adecuadas en el nuevo publicador tiene un impacto limitado en la replicación.</span><span class="sxs-lookup"><span data-stu-id="6567e-121">Agents encountering this error will log the error as informational but will not terminate, since a failure to have appropriate subscriber entries at the new publisher has limited impact on replication.</span></span> <span data-ttu-id="6567e-122">Sin una entrada correspondiente para un suscriptor en sysservers, algunas de las actividades de administración de suscripciones pueden generar un error cuando se ejecutan a través de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6567e-122">Without an appropriate entry for a subscriber in sysservers, some subscription management activities may fail when executed through [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="6567e-123">No obstante, estas mismas actividades se pueden realizar correctamente mediante la ejecución de los procedimientos almacenados de administración de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="6567e-123">However, these same activities can be successfully performed by executing the management stored procedures explicitly.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6567e-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="6567e-124">User Action</span></span>  
 <span data-ttu-id="6567e-125">Ejecute `sp_addlinkedserver` en el publicador redireccionado por cada uno de los suscriptores identificados para agregarlos como servidores remotos.</span><span class="sxs-lookup"><span data-stu-id="6567e-125">Run `sp_addlinkedserver` at the redirected publisher for each of the identified subscribers to add them as remote servers.</span></span> <span data-ttu-id="6567e-126">A continuación, ejecute `sp_serveroption` para establecer el bit de suscriptor para el servidor.</span><span class="sxs-lookup"><span data-stu-id="6567e-126">Then, run `sp_serveroption` to set the subscriber bit for the server.</span></span>  
  
  
