---
title: Quitar llamadas al comando DBCC CONCURRENCYVIOLATION desusado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 2cc9f6ff-de36-4e94-bd04-59f5c45c4911
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cde04ebfc2ea9996d1c9ed233123e5b66f6e81fa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748511"
---
# <a name="remove-calls-to-the-deprecated-dbcc-concurrencyviolation-command"></a><span data-ttu-id="cce4f-102">Quitar llamadas al comando desusado DBCC CONCURRENCYVIOLATION</span><span class="sxs-lookup"><span data-stu-id="cce4f-102">Remove calls to the deprecated DBCC CONCURRENCYVIOLATION command</span></span>
  <span data-ttu-id="cce4f-103">El Asesor de actualizaciones ha detectado el uso del comando DBCC CONCURRENCYVIOLATION.</span><span class="sxs-lookup"><span data-stu-id="cce4f-103">Upgrade Advisor detected the use of the DBCC CONCURRENCYVIOLATION command.</span></span> <span data-ttu-id="cce4f-104">Este comando ya no está disponible.</span><span class="sxs-lookup"><span data-stu-id="cce4f-104">This command is no longer available.</span></span> <span data-ttu-id="cce4f-105">Al ejecutar este comando, se devuelve el error 2526.</span><span class="sxs-lookup"><span data-stu-id="cce4f-105">Executing this command returns error 2526.</span></span>  
  
## <a name="component"></a><span data-ttu-id="cce4f-106">Componente</span><span class="sxs-lookup"><span data-stu-id="cce4f-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="cce4f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="cce4f-107">Description</span></span>  
 <span data-ttu-id="cce4f-108">Ninguna versión reciente de la edición de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] incluye un regulador de carga de trabajo; por ello, se ha quitado el comando.</span><span class="sxs-lookup"><span data-stu-id="cce4f-108">No recent version of edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] includes a workload governor; therefore the command has been removed.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="cce4f-109">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="cce4f-109">Corrective Action</span></span>  
 <span data-ttu-id="cce4f-110">Actualice las aplicaciones y los scripts para quitar todas las referencias a este comando desusado.</span><span class="sxs-lookup"><span data-stu-id="cce4f-110">Update applications and scripts to remove references to this deprecated command.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="cce4f-111">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="cce4f-111">External Resources</span></span>  
  
