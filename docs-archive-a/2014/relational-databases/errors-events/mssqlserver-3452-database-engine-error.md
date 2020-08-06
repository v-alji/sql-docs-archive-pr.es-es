---
title: MSSQLSERVER_3452 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3452 (Database Engine error)
ms.assetid: bf838f02-7186-4b33-b01e-361b0c02de1f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 662d342064e8094400a6b672e21704877b4d0448
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662066"
---
# <a name="mssqlserver_3452"></a><span data-ttu-id="8f821-102">MSSQLSERVER_3452</span><span class="sxs-lookup"><span data-stu-id="8f821-102">MSSQLSERVER_3452</span></span>
    
## <a name="details"></a><span data-ttu-id="8f821-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="8f821-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8f821-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="8f821-104">Product Name</span></span>|<span data-ttu-id="8f821-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8f821-105">SQL Server</span></span>|  
|<span data-ttu-id="8f821-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="8f821-106">Event ID</span></span>|<span data-ttu-id="8f821-107">3452</span><span class="sxs-lookup"><span data-stu-id="8f821-107">3452</span></span>|  
|<span data-ttu-id="8f821-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="8f821-108">Event Source</span></span>|<span data-ttu-id="8f821-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8f821-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8f821-110">Componente</span><span class="sxs-lookup"><span data-stu-id="8f821-110">Component</span></span>|<span data-ttu-id="8f821-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8f821-111">SQLEngine</span></span>|  
|<span data-ttu-id="8f821-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="8f821-112">Symbolic Name</span></span>|<span data-ttu-id="8f821-113">REC_CHECKIDENTITY</span><span class="sxs-lookup"><span data-stu-id="8f821-113">REC_CHECKIDENTITY</span></span>|  
|<span data-ttu-id="8f821-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="8f821-114">Message Text</span></span>|<span data-ttu-id="8f821-115">En la recuperación de la base de datos '%.\*ls' (%d) se detectó una posible incoherencia de valores de identidad en la tabla con id. %d.</span><span class="sxs-lookup"><span data-stu-id="8f821-115">Recovery of database '%.\*ls' (%d) detected possible identity value inconsistency in table ID %d.</span></span> <span data-ttu-id="8f821-116">Ejecute DBCC CHECKIDENT ("%.\*ls").</span><span class="sxs-lookup"><span data-stu-id="8f821-116">Run DBCC CHECKIDENT ('%.\*ls').</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8f821-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="8f821-117">Explanation</span></span>  
 <span data-ttu-id="8f821-118">Durante la actualización a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], el proceso de recuperación de los valores de identidad de la base de datos detectó una incoherencia en los metadatos.</span><span class="sxs-lookup"><span data-stu-id="8f821-118">During the upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], the process to recover the identity values in the database found an inconsistency in the metadata.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8f821-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="8f821-119">User Action</span></span>  
 <span data-ttu-id="8f821-120">Ejecute DBCC CHECKIDENT.</span><span class="sxs-lookup"><span data-stu-id="8f821-120">Run DBCC CHECKIDENT.</span></span>  
  
  
