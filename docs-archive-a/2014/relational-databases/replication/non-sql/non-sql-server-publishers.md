---
title: Publicadores que no son de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- heterogeneous database replication, non-SQL Server Publishers
- non-SQL Server Publishers
- heterogeneous data sources, non-SQL Server Publishers
- Publishers [SQL Server replication], Oracle
ms.assetid: 08a160a6-33be-46b5-bc7b-d53180d8bdf1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f15f07dbf294d697afd385318f3dbf1447c8e2d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662818"
---
# <a name="non-sql-server-publishers"></a><span data-ttu-id="7012f-102">publicadores que no son de SQL Server</span><span class="sxs-lookup"><span data-stu-id="7012f-102">Non-SQL Server Publishers</span></span>
  <span data-ttu-id="7012f-103">La publicación de datos desde orígenes que no son de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] le permite consolidar datos en [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7012f-103">Publishing data from non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sources allows you to consolidate data in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="7012f-104">pueden suscribirse a datos de instantánea o transaccionales publicados de una base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="7012f-104">can subscribe to snapshot or transactional data published from an Oracle database.</span></span> <span data-ttu-id="7012f-105">Para obtener más información sobre cómo publicar desde Oracle, vea [Información general de la publicación de Oracle](oracle-publishing-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7012f-105">For more information about publishing from Oracle, see [Oracle Publishing Overview](oracle-publishing-overview.md).</span></span>  
  
 <span data-ttu-id="7012f-106">La replicación heterogénea en suscriptores que no son SQL Server está desusada.</span><span class="sxs-lookup"><span data-stu-id="7012f-106">Heterogeneous replication to non-SQL Server subscribers is deprecated.</span></span> <span data-ttu-id="7012f-107">La publicación de Oracle está desusada.</span><span class="sxs-lookup"><span data-stu-id="7012f-107">Oracle Publishing is deprecated.</span></span> <span data-ttu-id="7012f-108">Para mover datos, cree soluciones mediante captura de datos modificados y [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7012f-108">To move data, create solutions using change data capture and [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span></span>  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../../includes/ssnotedepfutureavoid-md.md)]  
  
 <span data-ttu-id="7012f-109">La publicación desde bases de datos que no son de[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] es idónea en los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="7012f-109">Publishing from non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] databases is ideal for the following scenarios:</span></span>  
  
|<span data-ttu-id="7012f-110">Escenario</span><span class="sxs-lookup"><span data-stu-id="7012f-110">Scenario</span></span>|<span data-ttu-id="7012f-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="7012f-111">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="7012f-112">Implementaciones de aplicaciones de[!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7012f-112">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework application deployments</span></span>|<span data-ttu-id="7012f-113">Desarrolle con [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio y [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] cuando trabaje con datos replicados de una base de datos que no es de[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7012f-113">Develop with [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] while operating on data replicated from a non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database.</span></span>|  
|<span data-ttu-id="7012f-114">Servidores provisionales de almacenamiento de datos</span><span class="sxs-lookup"><span data-stu-id="7012f-114">Data warehousing staging servers</span></span>|<span data-ttu-id="7012f-115">Mantenga las bases de datos provisionales de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sincronizadas con una base de datos que no es de[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7012f-115">Keep [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] staging databases synchronized with a non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database.</span></span>|  
|<span data-ttu-id="7012f-116">Migración a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7012f-116">Migration to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span></span>|<span data-ttu-id="7012f-117">Compruebe la aplicación en tiempo real con [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] mientras replica los cambios del sistema de origen.</span><span class="sxs-lookup"><span data-stu-id="7012f-117">Test your application in real time against [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] while replicating the source system's changes.</span></span> <span data-ttu-id="7012f-118">Cambie a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] cuando esté satisfecho con la migración.</span><span class="sxs-lookup"><span data-stu-id="7012f-118">Switch to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] when satisfied with the migration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7012f-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7012f-119">See Also</span></span>  
 [<span data-ttu-id="7012f-120">Replicación de bases de datos heterogéneas</span><span class="sxs-lookup"><span data-stu-id="7012f-120">Heterogeneous Database Replication</span></span>](heterogeneous-database-replication.md)  
  
  
