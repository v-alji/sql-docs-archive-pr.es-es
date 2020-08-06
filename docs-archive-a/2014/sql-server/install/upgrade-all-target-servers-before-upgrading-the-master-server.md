---
title: Actualizar todos los servidores de destino antes de actualizar el servidor maestro | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- TSX [SQL Server Agent]
- target servers [SQL Server Agent]
- MSX [SQL Server Agent]
- master servers [SQL Server Agent]
ms.assetid: 2c231793-3878-4a5e-a425-1fa0d787ba84
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 031fedc4af4b058704cef1da8df846397b235305
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663284"
---
# <a name="upgrade-all-target-servers-before-upgrading-the-master-server"></a><span data-ttu-id="4734b-102">Actualizar todos los servidores de destino antes de actualizar el servidor maestro</span><span class="sxs-lookup"><span data-stu-id="4734b-102">Upgrade all target servers before upgrading the master server</span></span>
  <span data-ttu-id="4734b-103">Antes de actualizar el servidor maestro, actualice todos los equipos que ejecuten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y estén configurados como servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="4734b-103">Before you upgrade the master server, upgrade all computers that are running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are configured as target servers.</span></span>  
  
## <a name="component"></a><span data-ttu-id="4734b-104">Componente</span><span class="sxs-lookup"><span data-stu-id="4734b-104">Component</span></span>  
 <span data-ttu-id="4734b-105">e[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4734b-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent</span></span>  
  
## <a name="description"></a><span data-ttu-id="4734b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="4734b-106">Description</span></span>  
 <span data-ttu-id="4734b-107">Para automatizar el proceso de administración en entornos con varios servidores, deberá disponer de al menos un servidor maestro y un servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="4734b-107">To automate administration in multiserver environments, you must have at least one master server and at least one target server.</span></span> <span data-ttu-id="4734b-108">Los servidores maestros distribuyen trabajos a los servidores de destino y reciben eventos de éstos.</span><span class="sxs-lookup"><span data-stu-id="4734b-108">A master server distributes jobs to, and receives events from, target servers.</span></span> <span data-ttu-id="4734b-109">Asimismo, almacenan la copia central de definiciones de trabajos ejecutados en servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="4734b-109">A master server also stores the central copy of job definitions for jobs that are run on target servers.</span></span>  
  
 <span data-ttu-id="4734b-110">Si el servidor actual se configura como un servidor maestro, actualice todos sus servidores de destino antes de actualizar el servidor maestro.</span><span class="sxs-lookup"><span data-stu-id="4734b-110">If the current server is configured as a master server, upgrade all of your target servers first before you upgrade the master server.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="4734b-111">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="4734b-111">Corrective Action</span></span>  
 <span data-ttu-id="4734b-112">Si no puede actualizar todos los servidores de destino antes de actualizar el servidor maestro, debe dar de baja todos los servidores de destino y volverlos a dar de alta una vez haya llevado a cabo la actualización.</span><span class="sxs-lookup"><span data-stu-id="4734b-112">If you cannot upgrade all target servers before you upgrade the master server, you must defect all target servers and reenlist them after you upgrade.</span></span>  
  
 <span data-ttu-id="4734b-113">Para obtener más información, vea los temas "Automatizar la administración en una empresa", "Cómo dar de baja un servidor de destino en un servidor maestro" y "Cómo dar de alta un servidor de destino en un servidor maestro" en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4734b-113">For more information, see the topics "Automating Administration across an Enterprise," "How to: Defect a Target Server from a Master Server," and "How to: Enlist a Target Server to a Master" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4734b-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4734b-114">See Also</span></span>  
 <span data-ttu-id="4734b-115">[Problemas de actualización Agente SQL Server](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="4734b-115">[SQL Server Agent Upgrade Issues](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="4734b-116">Problemas de actualización del Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="4734b-116">SQL Server Agent Upgrade Issues</span></span>](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md)  
  
  
