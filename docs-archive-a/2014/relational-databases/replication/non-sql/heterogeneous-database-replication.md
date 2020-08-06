---
title: Replicación de bases de datos heterogéneas | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- heterogeneous database replication, about heterogeneous database replication
- replication [SQL Server], heterogeneous database replication
- heterogeneous database replication
ms.assetid: 3fd983ad-e206-45db-9054-417c9b5bb815
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d8988a425bc9519d43b8100e4cd34418114edae1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748048"
---
# <a name="heterogeneous-database-replication"></a><span data-ttu-id="a6412-102">replicación de bases de datos heterogéneas</span><span class="sxs-lookup"><span data-stu-id="a6412-102">Heterogeneous Database Replication</span></span>
  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="a6412-103">admite los siguientes escenarios heterogéneos para la replicación de instantáneas y transaccional:</span><span class="sxs-lookup"><span data-stu-id="a6412-103">supports the following heterogeneous scenarios for transactional and snapshot replication:</span></span>  
  
-   <span data-ttu-id="a6412-104">Publicar datos de Oracle en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6412-104">Publishing data from Oracle to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="a6412-105">Publicar datos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en suscriptores que no son de[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a6412-105">Publishing data from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Subscribers.</span></span>  
  
 <span data-ttu-id="a6412-106">La replicación heterogénea en suscriptores que no son SQL Server está desusada.</span><span class="sxs-lookup"><span data-stu-id="a6412-106">Heterogeneous replication to non-SQL Server subscribers is deprecated.</span></span> <span data-ttu-id="a6412-107">La publicación de Oracle está desusada.</span><span class="sxs-lookup"><span data-stu-id="a6412-107">Oracle Publishing is deprecated.</span></span> <span data-ttu-id="a6412-108">Para mover datos, cree soluciones mediante captura de datos modificados y [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6412-108">To move data, create solutions using change data capture and [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span></span>  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../../includes/ssnotedepfutureavoid-md.md)]  
  
## <a name="publishing-data-from-oracle"></a><span data-ttu-id="a6412-109">Publicar datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="a6412-109">Publishing Data from Oracle</span></span>  
 <span data-ttu-id="a6412-110">Puede usar [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para publicar datos de Oracle con la mayoría de características y la misma facilidad de uso que la replicación de instantáneas y transaccional de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a6412-110">You can use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to publish data from Oracle with most of the same features and ease-of-use as [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] snapshot and transactional replication.</span></span> <span data-ttu-id="a6412-111">La publicación de datos de Oracle es ideal en los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="a6412-111">Publishing data from Oracle is ideal for the following scenarios:</span></span>  
  
|<span data-ttu-id="a6412-112">Escenario</span><span class="sxs-lookup"><span data-stu-id="a6412-112">Scenario</span></span>|<span data-ttu-id="a6412-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6412-113">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="a6412-114">Implementaciones de aplicaciones de[!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a6412-114">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework application deployments</span></span>|<span data-ttu-id="a6412-115">Desarrolle con [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio y [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] cuando trabaje con datos replicados de una base de datos que no es de[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a6412-115">Develop with [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] while operating on data replicated from a non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database.</span></span>|  
|<span data-ttu-id="a6412-116">Servidores provisionales de almacenamiento de datos</span><span class="sxs-lookup"><span data-stu-id="a6412-116">Data warehousing staging servers</span></span>|<span data-ttu-id="a6412-117">Mantenga las bases de datos provisionales de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sincronizadas con una base de datos que no es de[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a6412-117">Keep [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] staging databases synchronized with a non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database.</span></span>|  
|<span data-ttu-id="a6412-118">Migración a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6412-118">Migration to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span></span>|<span data-ttu-id="a6412-119">Compruebe la aplicación en tiempo real con [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] mientras replica los cambios del sistema de origen.</span><span class="sxs-lookup"><span data-stu-id="a6412-119">Test your application in real time against [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] while replicating the source system's changes.</span></span> <span data-ttu-id="a6412-120">Cambie a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] cuando esté satisfecho con la migración.</span><span class="sxs-lookup"><span data-stu-id="a6412-120">Switch to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] when satisfied with the migration.</span></span>|  
  
 <span data-ttu-id="a6412-121">Para obtener más información, vea [Oracle Publishing Overview](oracle-publishing-overview.md) (Información general de la publicación de Oracle).</span><span class="sxs-lookup"><span data-stu-id="a6412-121">For more information, see [Oracle Publishing Overview](oracle-publishing-overview.md).</span></span>  
  
## <a name="publishing-data-to-non-sql-server-subscribers"></a><span data-ttu-id="a6412-122">Publicar datos en suscriptores que no son de SQL Server</span><span class="sxs-lookup"><span data-stu-id="a6412-122">Publishing Data to Non-SQL Server Subscribers</span></span>  
 <span data-ttu-id="a6412-123">Las siguientes bases de datos que no son de[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] son compatibles como suscriptores de publicaciones de instantáneas y transaccionales:</span><span class="sxs-lookup"><span data-stu-id="a6412-123">The following non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] databases are supported as Subscribers to snapshot and transactional publications:</span></span>  
  
-   <span data-ttu-id="a6412-124">Oracle para todas las plataformas que admite Oracle.</span><span class="sxs-lookup"><span data-stu-id="a6412-124">Oracle for all platforms that Oracle supports.</span></span>  
  
-   <span data-ttu-id="a6412-125">IBM DB2 para AS400, MVS, Unix, Linux y Windows</span><span class="sxs-lookup"><span data-stu-id="a6412-125">IBM DB2 for AS400, MVS, Unix, Linux, and Windows.</span></span>  
  
 <span data-ttu-id="a6412-126">Para más información, consulte [Non-SQL Server Subscribers](non-sql-server-subscribers.md).</span><span class="sxs-lookup"><span data-stu-id="a6412-126">For more information, see [Non-SQL Server Subscribers](non-sql-server-subscribers.md).</span></span>  
  
  
