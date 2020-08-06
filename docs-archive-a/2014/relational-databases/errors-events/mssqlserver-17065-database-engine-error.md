---
title: MSSQLSERVER_17065 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17065 (Database Engine error)
ms.assetid: 63c2ba5a-be34-461e-bee1-03c25b396cd2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 47aebfa29b60a1c2ae50c6699946312996d26e6f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675937"
---
# <a name="mssqlserver_17065"></a><span data-ttu-id="19d75-102">MSSQLSERVER_17065</span><span class="sxs-lookup"><span data-stu-id="19d75-102">MSSQLSERVER_17065</span></span>
    
## <a name="details"></a><span data-ttu-id="19d75-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="19d75-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="19d75-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="19d75-104">Product Name</span></span>|<span data-ttu-id="19d75-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="19d75-105">SQL Server</span></span>|  
|<span data-ttu-id="19d75-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="19d75-106">Event ID</span></span>|<span data-ttu-id="19d75-107">17065</span><span class="sxs-lookup"><span data-stu-id="19d75-107">17065</span></span>|  
|<span data-ttu-id="19d75-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="19d75-108">Event Source</span></span>|<span data-ttu-id="19d75-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="19d75-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="19d75-110">Componente</span><span class="sxs-lookup"><span data-stu-id="19d75-110">Component</span></span>|<span data-ttu-id="19d75-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="19d75-111">SQLEngine</span></span>|  
|<span data-ttu-id="19d75-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="19d75-112">Symbolic Name</span></span>|<span data-ttu-id="19d75-113">SQLASSERT_BOTH</span><span class="sxs-lookup"><span data-stu-id="19d75-113">SQLASSERT_BOTH</span></span>|  
|<span data-ttu-id="19d75-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="19d75-114">Message Text</span></span>|<span data-ttu-id="19d75-115">Aserción de SQL Server: Archivo: \<%s>, línea = %d Error de aserción = '%s' %s.</span><span class="sxs-lookup"><span data-stu-id="19d75-115">SQL Server Assertion: File: \<%s>, line = %d Failed Assertion = '%s' %s.</span></span> <span data-ttu-id="19d75-116">Puede que este error esté relacionado con el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="19d75-116">This error may be timing-related.</span></span> <span data-ttu-id="19d75-117">Si el error persiste después de volver a ejecutar la instrucción, utilice DBCC CHECKDB para comprobar la integridad estructural de la base de datos, o bien reinicie el servidor para asegurarse de que las estructuras de datos en memoria no están dañadas.</span><span class="sxs-lookup"><span data-stu-id="19d75-117">If the error persists after rerunning the statement, use DBCC CHECKDB to check the database for structural integrity, or restart the server to ensure in-memory data structures are not corrupted.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="19d75-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="19d75-118">Explanation</span></span>  
 <span data-ttu-id="19d75-119">Este error puede deberse a errores transitorios relacionados con el control de tiempo, o a que los datos en memoria o en disco estén dañados.</span><span class="sxs-lookup"><span data-stu-id="19d75-119">This error can be caused by transient, timing-related errors, or by in-memory or on-disk data corruption.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="19d75-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="19d75-120">User Action</span></span>  
 <span data-ttu-id="19d75-121">Vuelva a ejecutar la instrucción que hizo que se desencadenara la excepción.</span><span class="sxs-lookup"><span data-stu-id="19d75-121">Rerun the statement that caused the exception to fire.</span></span> <span data-ttu-id="19d75-122">Si el error se debe a un evento relacionado con el control de tiempo, puede que el error no se repita.</span><span class="sxs-lookup"><span data-stu-id="19d75-122">If the error was caused by a timing-related event, the error may not recur.</span></span> <span data-ttu-id="19d75-123">Si el problema persiste, ejecute DBCC CHECKDB para comprobar si el disco está dañado.</span><span class="sxs-lookup"><span data-stu-id="19d75-123">If the problem persists, run DBCC CHECKDB to check for on-disk corruption.</span></span> <span data-ttu-id="19d75-124">Reinicie el servidor para asegurarse de que las estructuras de datos en memoria no están dañadas.</span><span class="sxs-lookup"><span data-stu-id="19d75-124">Restart the server to ensure the in-memory data structures are not corrupted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19d75-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="19d75-125">See Also</span></span>  
 [<span data-ttu-id="19d75-126">DBCC CHECKDB &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="19d75-126">DBCC CHECKDB &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)  
  
  
