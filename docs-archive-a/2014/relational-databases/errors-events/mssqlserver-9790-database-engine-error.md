---
title: MSSQLSERVER_9790 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9790 (Database Engine error)
ms.assetid: 83fd379f-5deb-4f97-8cb4-282e3d3fed94
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6d6d065d4a0e841da3b5ecb84f902df17dcfd60c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672028"
---
# <a name="mssqlserver_9790"></a><span data-ttu-id="a506f-102">MSSQLSERVER_9790</span><span class="sxs-lookup"><span data-stu-id="a506f-102">MSSQLSERVER_9790</span></span>
    
## <a name="details"></a><span data-ttu-id="a506f-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="a506f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a506f-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="a506f-104">Product Name</span></span>|<span data-ttu-id="a506f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a506f-105">SQL Server</span></span>|  
|<span data-ttu-id="a506f-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="a506f-106">Event ID</span></span>|<span data-ttu-id="a506f-107">9790</span><span class="sxs-lookup"><span data-stu-id="a506f-107">9790</span></span>|  
|<span data-ttu-id="a506f-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="a506f-108">Event Source</span></span>|<span data-ttu-id="a506f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a506f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a506f-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a506f-110">Component</span></span>|<span data-ttu-id="a506f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a506f-111">SQLEngine</span></span>|  
|<span data-ttu-id="a506f-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="a506f-112">Symbolic Name</span></span>|<span data-ttu-id="a506f-113">SB3_XMIT_ERROR_ENTRANCE_BROKER_SINGLE_USER</span><span class="sxs-lookup"><span data-stu-id="a506f-113">SB3_XMIT_ERROR_ENTRANCE_BROKER_SINGLE_USER</span></span>|  
|<span data-ttu-id="a506f-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="a506f-114">Message Text</span></span>|<span data-ttu-id="a506f-115">No se puede enrutar el mensaje entrante.</span><span class="sxs-lookup"><span data-stu-id="a506f-115">Unable to route the incoming message.</span></span> <span data-ttu-id="a506f-116">La base de datos del sistema MSDB que contiene la información de enrutamiento está en modo SINGLE USER.</span><span class="sxs-lookup"><span data-stu-id="a506f-116">The system database MSDB containing routing information is in SINGLE USER mode.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a506f-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="a506f-117">Explanation</span></span>  
 <span data-ttu-id="a506f-118">Se produjo un error al intentar clasificar un mensaje recibido fuera de la conexión porque la base de datos MSDB estaba en modo SINGLE USER.</span><span class="sxs-lookup"><span data-stu-id="a506f-118">An error occurred while trying to classify a message received off the wire because the MSDB database was in Single User mode.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a506f-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="a506f-119">User Action</span></span>  
 <span data-ttu-id="a506f-120">Cambie MSDB para que esté en modo MULTI USER con el comando ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="a506f-120">Change MSDB to be in MULTI USER mode with the ALTER DATABASE command.</span></span>  
  
  
