---
title: MSSQLSERVER_5554 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5554 (Database Engine error)
ms.assetid: 7134bbe5-d240-4a98-85ce-b13cc8ae9b0e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5095a50f257abafb6ebde97bb32c57bc71fc4e09
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673714"
---
# <a name="mssqlserver_5554"></a><span data-ttu-id="acc2a-102">MSSQLSERVER_5554</span><span class="sxs-lookup"><span data-stu-id="acc2a-102">MSSQLSERVER_5554</span></span>
    
## <a name="details"></a><span data-ttu-id="acc2a-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="acc2a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="acc2a-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="acc2a-104">Product Name</span></span>|<span data-ttu-id="acc2a-105">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="acc2a-105">MSSQLSERVER</span></span>|  
|<span data-ttu-id="acc2a-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="acc2a-106">Event ID</span></span>|<span data-ttu-id="acc2a-107">5554</span><span class="sxs-lookup"><span data-stu-id="acc2a-107">5554</span></span>|  
|<span data-ttu-id="acc2a-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="acc2a-108">Event Source</span></span>|<span data-ttu-id="acc2a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="acc2a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="acc2a-110">Componente</span><span class="sxs-lookup"><span data-stu-id="acc2a-110">Component</span></span>|<span data-ttu-id="acc2a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="acc2a-111">SQLEngine</span></span>|  
|<span data-ttu-id="acc2a-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="acc2a-112">Symbolic Name</span></span>|<span data-ttu-id="acc2a-113">FS_MINIVER_OVERFLOW</span><span class="sxs-lookup"><span data-stu-id="acc2a-113">FS_MINIVER_OVERFLOW</span></span>|  
|<span data-ttu-id="acc2a-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="acc2a-114">Message Text</span></span>|<span data-ttu-id="acc2a-115">El número total de versiones para un único archivo ha alcanzado el límite máximo establecido por el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="acc2a-115">The total number of versions for a single file has reached the maximum limit set by the file system.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="acc2a-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="acc2a-116">Explanation</span></span>  
 <span data-ttu-id="acc2a-117">En conjuntos de resultados activos múltiples (MARS) o escenarios de desencadenador, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usa la miniversión especificada por el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="acc2a-117">In multiple active result sets (MARS) or trigger scenarios, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses the miniversion specified by the operating system.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="acc2a-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="acc2a-118">User Action</span></span>  
 <span data-ttu-id="acc2a-119">Intente evitar las actualizaciones repetidas en los datos de la misma transacción.</span><span class="sxs-lookup"><span data-stu-id="acc2a-119">Try to avoid repeated updates to the data in the same transaction.</span></span>  
  
  
