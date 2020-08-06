---
title: MSSQLSERVER_1904 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1904 (Database Engine error)
ms.assetid: 2a35d57d-74e2-45a2-8f67-3f2e51d69712
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 568cfe7499c041c2ee6a8ac3698b31698171bece
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672071"
---
# <a name="mssqlserver_1904"></a><span data-ttu-id="8efaa-102">MSSQLSERVER_1904</span><span class="sxs-lookup"><span data-stu-id="8efaa-102">MSSQLSERVER_1904</span></span>
    
## <a name="details"></a><span data-ttu-id="8efaa-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="8efaa-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8efaa-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="8efaa-104">Product Name</span></span>|<span data-ttu-id="8efaa-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8efaa-105">SQL Server</span></span>|  
|<span data-ttu-id="8efaa-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="8efaa-106">Event ID</span></span>|<span data-ttu-id="8efaa-107">1904</span><span class="sxs-lookup"><span data-stu-id="8efaa-107">1904</span></span>|  
|<span data-ttu-id="8efaa-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="8efaa-108">Event Source</span></span>|<span data-ttu-id="8efaa-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8efaa-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8efaa-110">Componente</span><span class="sxs-lookup"><span data-stu-id="8efaa-110">Component</span></span>|<span data-ttu-id="8efaa-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8efaa-111">SQLEngine</span></span>|  
|<span data-ttu-id="8efaa-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="8efaa-112">Symbolic Name</span></span>|<span data-ttu-id="8efaa-113">KEYCOUNT</span><span class="sxs-lookup"><span data-stu-id="8efaa-113">KEYCOUNT</span></span>|  
|<span data-ttu-id="8efaa-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="8efaa-114">Message Text</span></span>|<span data-ttu-id="8efaa-115">%S_MSG '%.\*ls' en la tabla '%.\*ls' tiene %d nombres de columna en la lista de claves %S_MSG.</span><span class="sxs-lookup"><span data-stu-id="8efaa-115">The %S_MSG '%.\*ls' on table '%.\*ls' has %d column names in %S_MSG key list.</span></span> <span data-ttu-id="8efaa-116">El límite máximo para la lista de columnas de clave de índice o estadísticas es %d.</span><span class="sxs-lookup"><span data-stu-id="8efaa-116">The maximum limit for index or statistics key column list is %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8efaa-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="8efaa-117">Explanation</span></span>  
 <span data-ttu-id="8efaa-118">La lista de columnas de clave para el índice o estadística especificados supera el número máximo permitido de columnas.</span><span class="sxs-lookup"><span data-stu-id="8efaa-118">The key column list for the specified index or statistics exceeds the maximum number of columns allowed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8efaa-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="8efaa-119">User Action</span></span>  
 <span data-ttu-id="8efaa-120">Modifique la lista de columnas de clave para que no incluya más columnas del número máximo especificado.</span><span class="sxs-lookup"><span data-stu-id="8efaa-120">Modify the key column list to include no more than the specified maximum number of columns.</span></span>  
  
 <span data-ttu-id="8efaa-121">Con los índices no clúster, considere utilizar la cláusula INCLUDE en la instrucción CREATE INDEX para agregar columnas al índice como columnas sin clave.</span><span class="sxs-lookup"><span data-stu-id="8efaa-121">For nonclustered indexes, consider using the INCLUDE clause in the CREATE INDEX statement to add columns to the index as nonkey columns.</span></span> <span data-ttu-id="8efaa-122">Este método impide superar la limitación de tamaño de índice actual de 16 columnas de clave como máximo.</span><span class="sxs-lookup"><span data-stu-id="8efaa-122">This method avoids exceeding the current index size limitation of a maximum of 16 key columns.</span></span> <span data-ttu-id="8efaa-123">Para más información, consulte [Create Indexes with Included Columns](../indexes/create-indexes-with-included-columns.md).</span><span class="sxs-lookup"><span data-stu-id="8efaa-123">For more information, see [Create Indexes with Included Columns](../indexes/create-indexes-with-included-columns.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8efaa-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8efaa-124">See Also</span></span>  
 <span data-ttu-id="8efaa-125">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8efaa-125">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 [<span data-ttu-id="8efaa-126">CREATE STATISTICS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8efaa-126">CREATE STATISTICS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-statistics-transact-sql)  
  
  
