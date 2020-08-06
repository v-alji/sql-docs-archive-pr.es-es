---
title: MSSQLSERVER_15599 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 15599 (Database Engine error)
ms.assetid: 97e427a9-8587-46ea-954b-974b5df9c223
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 15f1b3eb6d97837f1c1c4a9944535cade5b31300
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675939"
---
# <a name="mssqlserver_15599"></a><span data-ttu-id="aa1c5-102">MSSQLSERVER_15599</span><span class="sxs-lookup"><span data-stu-id="aa1c5-102">MSSQLSERVER_15599</span></span>
    
## <a name="details"></a><span data-ttu-id="aa1c5-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="aa1c5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="aa1c5-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="aa1c5-104">Product Name</span></span>|<span data-ttu-id="aa1c5-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="aa1c5-105">SQL Server</span></span>|  
|<span data-ttu-id="aa1c5-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="aa1c5-106">Event ID</span></span>|<span data-ttu-id="aa1c5-107">15599</span><span class="sxs-lookup"><span data-stu-id="aa1c5-107">15599</span></span>|  
|<span data-ttu-id="aa1c5-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="aa1c5-108">Event Source</span></span>|<span data-ttu-id="aa1c5-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="aa1c5-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="aa1c5-110">Componente</span><span class="sxs-lookup"><span data-stu-id="aa1c5-110">Component</span></span>|<span data-ttu-id="aa1c5-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="aa1c5-111">SQLEngine</span></span>|  
|<span data-ttu-id="aa1c5-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="aa1c5-112">Symbolic Name</span></span>|<span data-ttu-id="aa1c5-113">SEC_LOCAL_TEMP_AUDIT_PERMISSIONS</span><span class="sxs-lookup"><span data-stu-id="aa1c5-113">SEC_LOCAL_TEMP_AUDIT_PERMISSIONS</span></span>|  
|<span data-ttu-id="aa1c5-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="aa1c5-114">Message Text</span></span>|<span data-ttu-id="aa1c5-115">No se pueden establecer permisos ni auditoría y en objetos temporales locales.</span><span class="sxs-lookup"><span data-stu-id="aa1c5-115">Auditing and permissions can't be set on local temporary objects.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="aa1c5-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="aa1c5-116">Explanation</span></span>  
 <span data-ttu-id="aa1c5-117">La auditoría y los permisos no tienen ningún efecto cuando se establecen en objetos locales o globales temporales.</span><span class="sxs-lookup"><span data-stu-id="aa1c5-117">Auditing and permissions do not have any effect when set for local or global temp objects.</span></span> <span data-ttu-id="aa1c5-118">Las instrucciones no producen un error (las operaciones vuelven correctamente), pero no tienen ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="aa1c5-118">The statements do not result in an error (the operations will return success), but have no effect.</span></span>  
  
 <span data-ttu-id="aa1c5-119">Este comportamiento no ha cambiado, pero a partir de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], este mensaje informativo alerta al usuario.</span><span class="sxs-lookup"><span data-stu-id="aa1c5-119">This behavior has not changed, however beginning with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], this informational message alerts the user.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="aa1c5-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="aa1c5-120">User Action</span></span>  
 <span data-ttu-id="aa1c5-121">No es necesaria ninguna acción, pero considere la posibilidad de quitar las instrucciones que intentan establecer la auditoría o los permisos en objetos locales o globales temporales.</span><span class="sxs-lookup"><span data-stu-id="aa1c5-121">No action is necessary, but consider removing statements that attempt to set auditing or permissions on local or global temp objects.</span></span>  
  
  
