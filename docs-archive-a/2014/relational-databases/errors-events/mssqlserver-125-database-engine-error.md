---
title: MSSQLSERVER_125 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "125"
helpviewer_keywords:
- 125 (Database Engine error)
ms.assetid: 0f58338d-2ea0-48b8-8a20-c438b0940433
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 59c732d80ccfafc8f242bb1c42fe60e3dea81f19
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673040"
---
# <a name="mssqlserver_125"></a><span data-ttu-id="4753a-102">MSSQLSERVER_125</span><span class="sxs-lookup"><span data-stu-id="4753a-102">MSSQLSERVER_125</span></span>
    
## <a name="details"></a><span data-ttu-id="4753a-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="4753a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4753a-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="4753a-104">Product Name</span></span>|<span data-ttu-id="4753a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4753a-105">SQL Server</span></span>|  
|<span data-ttu-id="4753a-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="4753a-106">Event ID</span></span>|<span data-ttu-id="4753a-107">125</span><span class="sxs-lookup"><span data-stu-id="4753a-107">125</span></span>|  
|<span data-ttu-id="4753a-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="4753a-108">Event Source</span></span>|<span data-ttu-id="4753a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4753a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4753a-110">Componente</span><span class="sxs-lookup"><span data-stu-id="4753a-110">Component</span></span>|<span data-ttu-id="4753a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4753a-111">SQLEngine</span></span>|  
|<span data-ttu-id="4753a-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="4753a-112">Symbolic Name</span></span>||  
|<span data-ttu-id="4753a-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="4753a-113">Message Text</span></span>|<span data-ttu-id="4753a-114">Las expresiones Case solo pueden anidarse hasta el nivel %d.</span><span class="sxs-lookup"><span data-stu-id="4753a-114">Case expressions may only be nested to level %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4753a-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="4753a-115">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="4753a-116">solo permite 10 niveles de anidamiento en las expresiones CASE.</span><span class="sxs-lookup"><span data-stu-id="4753a-116">allows for only 10 levels of nesting in CASE expressions.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4753a-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="4753a-117">User Action</span></span>  
 <span data-ttu-id="4753a-118">Reduzca el nivel de las instrucciones CASE a 10 o a un número inferior.</span><span class="sxs-lookup"><span data-stu-id="4753a-118">Reduce the level of CASE statements to 10 or less.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4753a-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4753a-119">See Also</span></span>  
 [<span data-ttu-id="4753a-120">CASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4753a-120">CASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/case-transact-sql)  
  
  