---
title: Reglas de actualización de edición | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 77c4d751-4fea-4e69-a7c8-ab8fc0dbadb2
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 453944ede41bfc5cf258c6f0946b15b716c6c22c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672472"
---
# <a name="edition-upgrade-rules"></a><span data-ttu-id="d68b5-102">Reglas de actualización de edición</span><span class="sxs-lookup"><span data-stu-id="d68b5-102">Edition Upgrade Rules</span></span>
  <span data-ttu-id="d68b5-103">El programa de instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] valida la configuración del equipo antes de que se complete la operación de instalación.</span><span class="sxs-lookup"><span data-stu-id="d68b5-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup validates your computer configuration before the Setup operation completes.</span></span> <span data-ttu-id="d68b5-104">Durante la instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , el Comprobador de configuración del sistema (SCC) examina el equipo en el que se instalará [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d68b5-104">During [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup, the System Configuration Checker (SCC) scans the computer where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will be installed.</span></span> <span data-ttu-id="d68b5-105">El SCC comprueba las condiciones que impiden una operación de instalación correcta de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d68b5-105">The SCC checks for conditions that prevent a successful [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] setup operation.</span></span> <span data-ttu-id="d68b5-106">Antes de que el programa de instalación inicie la actualización de la edición, el SCC recupera el estado de cada elemento.</span><span class="sxs-lookup"><span data-stu-id="d68b5-106">Before Setup starts the edition upgrade, the SCC retrieves the status of each item.</span></span> <span data-ttu-id="d68b5-107">A continuación, compara el resultado con las condiciones necesarias y proporciona instrucciones para evitar problemas de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="d68b5-107">It then compares the result with required conditions and provides guidance for removal of blocking issues.</span></span>  
  
 <span data-ttu-id="d68b5-108">La comprobación de la configuración del sistema genera un informe que contiene una descripción breve de cada regla ejecutada y el estado de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d68b5-108">The system configuration check generates a report which contains a short description for each executed rule, and the execution status.</span></span> <span data-ttu-id="d68b5-109">El informe de comprobación de la configuración del sistema se encuentra en% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="d68b5-109">The system configuration check report is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
 <span data-ttu-id="d68b5-110">Antes de ejecutar la operación de instalación, revise los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="d68b5-110">Before you run the setup operation, review the following topics:</span></span>  
  
1.  [<span data-ttu-id="d68b5-111">Requisitos de hardware y software para instalar SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="d68b5-111">Hardware and Software Requirements for Installing SQL Server 2014</span></span>](hardware-and-software-requirements-for-installing-sql-server.md)  
  
2.  [<span data-ttu-id="d68b5-112">Características admitidas por las ediciones de SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="d68b5-112">Features Supported by the Editions of SQL Server 2014</span></span>](../../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md)  
  
3.  [<span data-ttu-id="d68b5-113">Consideraciones de seguridad para una instalación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="d68b5-113">Security Considerations for a SQL Server Installation</span></span>](../../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
4.  [<span data-ttu-id="d68b5-114">Versiones en idioma local en SQL Server</span><span class="sxs-lookup"><span data-stu-id="d68b5-114">Local Language Versions in SQL Server</span></span>](../../../2014/sql-server/install/local-language-versions-in-sql-server.md)  
  
 <span data-ttu-id="d68b5-115">Otras referencias:</span><span class="sxs-lookup"><span data-stu-id="d68b5-115">Other references:</span></span>  
  
1.  [<span data-ttu-id="d68b5-116">Actualizaciones de ediciones y versiones admitidas</span><span class="sxs-lookup"><span data-stu-id="d68b5-116">Supported Version and Edition Upgrades</span></span>](../../database-engine/install-windows/supported-version-and-edition-upgrades.md)  
  
2.  [<span data-ttu-id="d68b5-117">Antes de instalar los clústeres de conmutación por error</span><span class="sxs-lookup"><span data-stu-id="d68b5-117">Before Installing Failover Clustering</span></span>](../failover-clusters/install/before-installing-failover-clustering.md)  
  
## <a name="see-also"></a><span data-ttu-id="d68b5-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d68b5-118">See Also</span></span>  
 [<span data-ttu-id="d68b5-119">Reglas de instalación</span><span class="sxs-lookup"><span data-stu-id="d68b5-119">Install Rules</span></span>](../../../2014/sql-server/install/install-rules.md)  
  
  
