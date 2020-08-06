---
title: MSSQLSERVER_10737 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10737 (Database Engine error)
ms.assetid: 208af6ed-b271-4ab8-803e-7666025385c8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: df8a4de014552d3aca00b3eb244f7ff8df56756b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675436"
---
# <a name="mssqlserver_10737"></a><span data-ttu-id="911be-102">MSSQLSERVER_10737</span><span class="sxs-lookup"><span data-stu-id="911be-102">MSSQLSERVER_10737</span></span>
    
## <a name="details"></a><span data-ttu-id="911be-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="911be-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="911be-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="911be-104">Product Name</span></span>|<span data-ttu-id="911be-105">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="911be-105">MSSQLSERVER</span></span>|  
|<span data-ttu-id="911be-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="911be-106">Event ID</span></span>|<span data-ttu-id="911be-107">10737</span><span class="sxs-lookup"><span data-stu-id="911be-107">10737</span></span>|  
|<span data-ttu-id="911be-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="911be-108">Event Source</span></span>|<span data-ttu-id="911be-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="911be-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="911be-110">Componente</span><span class="sxs-lookup"><span data-stu-id="911be-110">Component</span></span>|<span data-ttu-id="911be-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="911be-111">SQLEngine</span></span>|  
|<span data-ttu-id="911be-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="911be-112">Symbolic Name</span></span>|<span data-ttu-id="911be-113">REBUILD_PARTITION_ALL_NOT_SPECIFIED</span><span class="sxs-lookup"><span data-stu-id="911be-113">REBUILD_PARTITION_ALL_NOT_SPECIFIED</span></span>|  
|<span data-ttu-id="911be-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="911be-114">Message Text</span></span>|<span data-ttu-id="911be-115">En una instrucción ALTER TABLE REBUILD o ALTER INDEX REBUILD, cuando se especifica una partición en una cláusula DATA_COMPRESSION, se debe especificar PARTITION=ALL.</span><span class="sxs-lookup"><span data-stu-id="911be-115">In an ALTER TABLE REBUILD or ALTER INDEX REBUILD statement, when a partition is specified in a DATA_COMPRESSION clause, PARTITION=ALL must be specified.</span></span> <span data-ttu-id="911be-116">La cláusula PARTITION=ALL se utiliza para reforzar que se volverán a generar todas las particiones de la tabla o índice, aunque solo se especifique un subconjunto en la cláusula DATA_COMPRESSION.</span><span class="sxs-lookup"><span data-stu-id="911be-116">The PARTITION=ALL clause is used to reinforce that all partitions of the table or index will be rebuilt, even if only a subset is specified in the DATA_COMPRESSION clause.</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="911be-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="911be-117">User Action</span></span>  
 <span data-ttu-id="911be-118">Agregue la cláusula PARTITION=ALL a la instrucción ALTER TABLE o ALTER INDEX.</span><span class="sxs-lookup"><span data-stu-id="911be-118">Add the PARTITION=ALL clause to the ALTER TABLE or ALTER INDEX statement.</span></span> <span data-ttu-id="911be-119">También puede recompilar una partición concreta mediante REBUILD PARTITION = \<partition-number-expr> WITH (DATA_COMPRESSION={ON | OFF}).</span><span class="sxs-lookup"><span data-stu-id="911be-119">Or, to rebuild a specific partition, use REBUILD PARTITION = \<partition-number-expr> WITH (DATA_COMPRESSION={ON | OFF}).</span></span>  
  
  
