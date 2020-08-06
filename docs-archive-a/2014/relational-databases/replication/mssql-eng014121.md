---
title: MSSQL_ENG014121 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014121 error
ms.assetid: c8595854-cce1-4566-ad64-d565555caded
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 04d4cbdd2197745d2d795814d88c4f7bc28eb90e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661939"
---
# <a name="mssql_eng014121"></a><span data-ttu-id="aaa5a-102">MSSQL_ENG014121</span><span class="sxs-lookup"><span data-stu-id="aaa5a-102">MSSQL_ENG014121</span></span>
    
## <a name="message-details"></a><span data-ttu-id="aaa5a-103">Detalles del mensaje</span><span class="sxs-lookup"><span data-stu-id="aaa5a-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="aaa5a-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="aaa5a-104">Product Name</span></span>|<span data-ttu-id="aaa5a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="aaa5a-105">SQL Server</span></span>|  
|<span data-ttu-id="aaa5a-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="aaa5a-106">Event ID</span></span>|<span data-ttu-id="aaa5a-107">14121</span><span class="sxs-lookup"><span data-stu-id="aaa5a-107">14121</span></span>|  
|<span data-ttu-id="aaa5a-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="aaa5a-108">Event Source</span></span>|<span data-ttu-id="aaa5a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="aaa5a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="aaa5a-110">Componente</span><span class="sxs-lookup"><span data-stu-id="aaa5a-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="aaa5a-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="aaa5a-111">Symbolic Name</span></span>||  
|<span data-ttu-id="aaa5a-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="aaa5a-112">Message Text</span></span>|<span data-ttu-id="aaa5a-113">No se pudo quitar el distribuidor '%s'.</span><span class="sxs-lookup"><span data-stu-id="aaa5a-113">Could not drop the Distributor '%s'.</span></span> <span data-ttu-id="aaa5a-114">Tiene asociadas bases de datos de distribución.</span><span class="sxs-lookup"><span data-stu-id="aaa5a-114">This Distributor has associated distribution databases.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="aaa5a-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="aaa5a-115">Explanation</span></span>  
 <span data-ttu-id="aaa5a-116">No se puede quitar una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] configurada como distribuidor del rol de distribuidor porque hay bases de datos de distribución asociadas con esa instancia.</span><span class="sxs-lookup"><span data-stu-id="aaa5a-116">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that is configured as a Distributor cannot be removed from the role of Distributor because there are distribution databases associated with the instance.</span></span> <span data-ttu-id="aaa5a-117">Este error se produce si intenta quitar una base de datos de distribución que está asociada a uno o más publicadores.</span><span class="sxs-lookup"><span data-stu-id="aaa5a-117">This error occurs if you attempt to drop a distribution database that is associated with one or more Publishers.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="aaa5a-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="aaa5a-118">User Action</span></span>  
 <span data-ttu-id="aaa5a-119">Para buscar los nombres de todos los publicadores y bases de datos de distribución asociados a este distribuidor, ejecute [sp_helpdistpublisher &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpdistpublisher-transact-sql) desde cualquier base de datos del distribuidor.</span><span class="sxs-lookup"><span data-stu-id="aaa5a-119">To find the names of any Publishers and distribution databases associated with this Distributor, execute [sp_helpdistpublisher &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpdistpublisher-transact-sql) from any database on the Distributor.</span></span>  
  
 <span data-ttu-id="aaa5a-120">Ejecute [sp_dropdistributiondb &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdistributiondb-transact-sql) para todas las bases de datos de distribución asociadas con este distribuidor.</span><span class="sxs-lookup"><span data-stu-id="aaa5a-120">Execute [sp_dropdistributiondb &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdistributiondb-transact-sql) for any distribution databases associated with this Distributor.</span></span> <span data-ttu-id="aaa5a-121">Cuando haya quitado todas las asociaciones con bases de datos de distribución, puede deshabilitar la distribución.</span><span class="sxs-lookup"><span data-stu-id="aaa5a-121">After all distribution database associations are removed, you can disable distribution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaa5a-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aaa5a-122">See Also</span></span>  
 <span data-ttu-id="aaa5a-123">[Referencia de errores y eventos &#40;replicación&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="aaa5a-123">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 [<span data-ttu-id="aaa5a-124">Configurar distribución</span><span class="sxs-lookup"><span data-stu-id="aaa5a-124">Configure Distribution</span></span>](configure-distribution.md)  
  
  
