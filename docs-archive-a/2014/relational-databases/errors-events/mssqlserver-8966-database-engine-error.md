---
title: MSSQLSERVER_8966 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8966 (Database Engine error)
ms.assetid: 6b1150fd-9dfd-4df9-8f08-8eca237667db
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8d3a12d5d0732ba8694db3d4c7dcae1eac59d28b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678197"
---
# <a name="mssqlserver_8966"></a><span data-ttu-id="5a674-102">MSSQLSERVER_8966</span><span class="sxs-lookup"><span data-stu-id="5a674-102">MSSQLSERVER_8966</span></span>
    
## <a name="details"></a><span data-ttu-id="5a674-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="5a674-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5a674-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="5a674-104">Product Name</span></span>|<span data-ttu-id="5a674-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5a674-105">SQL Server</span></span>|  
|<span data-ttu-id="5a674-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="5a674-106">Event ID</span></span>|<span data-ttu-id="5a674-107">8966</span><span class="sxs-lookup"><span data-stu-id="5a674-107">8966</span></span>|  
|<span data-ttu-id="5a674-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="5a674-108">Event Source</span></span>|<span data-ttu-id="5a674-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5a674-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5a674-110">Componente</span><span class="sxs-lookup"><span data-stu-id="5a674-110">Component</span></span>|<span data-ttu-id="5a674-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5a674-111">SQLEngine</span></span>|  
|<span data-ttu-id="5a674-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="5a674-112">Symbolic Name</span></span>|<span data-ttu-id="5a674-113">DBCC3_FAILED_TO_READ_AND_LATCH_PAGE</span><span class="sxs-lookup"><span data-stu-id="5a674-113">DBCC3_FAILED_TO_READ_AND_LATCH_PAGE</span></span>|  
|<span data-ttu-id="5a674-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="5a674-114">Message Text</span></span>|<span data-ttu-id="5a674-115">No se puede leer la página de bloqueo temporal P_ID con el tipo de bloqueo temporal TYPE.</span><span class="sxs-lookup"><span data-stu-id="5a674-115">Unable to read and latch page P_ID with latch type TYPE.</span></span> <span data-ttu-id="5a674-116">Error de OPERATION.</span><span class="sxs-lookup"><span data-stu-id="5a674-116">OPERATION failed.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5a674-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="5a674-117">Explanation</span></span>  
 <span data-ttu-id="5a674-118">Se produjo un error en la lectura de página o en un bloqueo temporal en una página PFS o GAM.</span><span class="sxs-lookup"><span data-stu-id="5a674-118">The page read failed or a latch could not be taken on a PFS or GAM page.</span></span> <span data-ttu-id="5a674-119">Es posible que se haya agotado el tiempo de espera para el bloqueo temporal o existan otros mensajes asociados en el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a674-119">There may be latch time-out or other accompanying messages in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5a674-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="5a674-120">User Action</span></span>  
 <span data-ttu-id="5a674-121">Revise en el registro de errores de SQL los mensajes asociados y resuelva estos errores.</span><span class="sxs-lookup"><span data-stu-id="5a674-121">Review the SQL error log for accompanying messages and resolve these errors.</span></span>  
  
  
