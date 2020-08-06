---
title: MSSQL_ENG020596 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG020596 error
ms.assetid: fa33627c-2e99-4be3-9424-52ab83446e07
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8b1c61f3683442e0d474ff36a65c89446dbd7bd1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677576"
---
# <a name="mssql_eng020596"></a><span data-ttu-id="57823-102">MSSQL_ENG020596</span><span class="sxs-lookup"><span data-stu-id="57823-102">MSSQL_ENG020596</span></span>
    
## <a name="message-details"></a><span data-ttu-id="57823-103">Detalles del mensaje</span><span class="sxs-lookup"><span data-stu-id="57823-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="57823-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="57823-104">Product Name</span></span>|<span data-ttu-id="57823-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="57823-105">SQL Server</span></span>|  
|<span data-ttu-id="57823-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="57823-106">Event ID</span></span>|<span data-ttu-id="57823-107">20596</span><span class="sxs-lookup"><span data-stu-id="57823-107">20596</span></span>|  
|<span data-ttu-id="57823-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="57823-108">Event Source</span></span>|<span data-ttu-id="57823-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="57823-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="57823-110">Componente</span><span class="sxs-lookup"><span data-stu-id="57823-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="57823-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="57823-111">Symbolic Name</span></span>||  
|<span data-ttu-id="57823-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="57823-112">Message Text</span></span>|<span data-ttu-id="57823-113">Solo '%1!' o los miembros de db_owner pueden quitar el agente anónimo.</span><span class="sxs-lookup"><span data-stu-id="57823-113">Only '%s' or members of db_owner can drop the anonymous agent.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="57823-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="57823-114">Explanation</span></span>  
 <span data-ttu-id="57823-115">No tiene suficientes permisos para quitar el agente de la suscripción anónima.</span><span class="sxs-lookup"><span data-stu-id="57823-115">You do not have sufficient permissions to drop the agent for the anonymous subscription.</span></span> <span data-ttu-id="57823-116">El inicio de sesión usado al llamar a [sp_dropanonymousagent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropanonymousagent-transact-sql) debe ser un miembro del rol fijo de servidor **sysadmin** del distribuidor o del rol fijo de base de datos **db_owner** de la base de datos de distribución, o bien el usuario debe ser el que inició la primera ejecución del agente.</span><span class="sxs-lookup"><span data-stu-id="57823-116">The login used when calling [sp_dropanonymousagent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropanonymousagent-transact-sql) must be a member of the **sysadmin** fixed server role at the Distributor or **db_owner** fixed database role in the distribution database, or the user must be the one that initiated the first run of the agent.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="57823-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="57823-117">User Action</span></span>  
 <span data-ttu-id="57823-118">Inicie sesión con las credenciales correctas y ejecute **sp_dropanonymousagent**.</span><span class="sxs-lookup"><span data-stu-id="57823-118">Login with the appropriate credentials, and execute **sp_dropanonymousagent**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57823-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="57823-119">See Also</span></span>  
 [<span data-ttu-id="57823-120">Referencia de errores y eventos &#40;replicación&#41;</span><span class="sxs-lookup"><span data-stu-id="57823-120">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
