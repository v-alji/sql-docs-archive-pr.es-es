---
title: MSSQLSERVER_9002 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9002 (Database Engine error)
ms.assetid: 2e50841f-2b99-45f4-aec5-aa4add70cbeb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b40fe70db8849d09f9296a06cbeed65a9c71e5a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674844"
---
# <a name="mssqlserver_9002"></a><span data-ttu-id="87778-102">MSSQLSERVER_9002</span><span class="sxs-lookup"><span data-stu-id="87778-102">MSSQLSERVER_9002</span></span>
    
## <a name="details"></a><span data-ttu-id="87778-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="87778-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="87778-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="87778-104">Product Name</span></span>|<span data-ttu-id="87778-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="87778-105">SQL Server</span></span>|  
|<span data-ttu-id="87778-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="87778-106">Event ID</span></span>|<span data-ttu-id="87778-107">9002</span><span class="sxs-lookup"><span data-stu-id="87778-107">9002</span></span>|  
|<span data-ttu-id="87778-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="87778-108">Event Source</span></span>|<span data-ttu-id="87778-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="87778-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="87778-110">Componente</span><span class="sxs-lookup"><span data-stu-id="87778-110">Component</span></span>|<span data-ttu-id="87778-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="87778-111">SQLEngine</span></span>|  
|<span data-ttu-id="87778-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="87778-112">Symbolic Name</span></span>|<span data-ttu-id="87778-113">LOG_IS_FULL</span><span class="sxs-lookup"><span data-stu-id="87778-113">LOG_IS_FULL</span></span>|  
|<span data-ttu-id="87778-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="87778-114">Message Text</span></span>|<span data-ttu-id="87778-115">El registro de transacciones de la base de datos '%.\*ls' está lleno.</span><span class="sxs-lookup"><span data-stu-id="87778-115">The transaction log for database '%.\*ls' is full.</span></span> <span data-ttu-id="87778-116">Para saber por qué no se puede volver a utilizar el espacio del registro, vea la columna log_reuse_wait_desc de sys.databases.</span><span class="sxs-lookup"><span data-stu-id="87778-116">To find out why space in the log cannot be reused, see the log_reuse_wait_desc column in sys.databases.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="87778-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="87778-117">Explanation</span></span>  
 <span data-ttu-id="87778-118">El registro de la base de datos se ha quedado sin espacio.</span><span class="sxs-lookup"><span data-stu-id="87778-118">The database log is out of space.</span></span> <span data-ttu-id="87778-119">En la columna **log_reuse_wait_desc** de **sys.databases** se describe por qué no se puede volver a utilizar el espacio del registro.</span><span class="sxs-lookup"><span data-stu-id="87778-119">The **log_reuse_wait_desc** column in **sys.databases** describes why space in the log cannot be reused.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="87778-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="87778-120">User Action</span></span>  
 <span data-ttu-id="87778-121">Use **sys.databases** para determinar la razón por la que el registro está lleno y solucione el problema.</span><span class="sxs-lookup"><span data-stu-id="87778-121">Use **sys.databases** to determine why the log is full and then correct the condition.</span></span> <span data-ttu-id="87778-122">Para obtener más información, vea "Solucionar problemas de un registro de transacciones lleno (Error 9002)" en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="87778-122">For more information, see "Troubleshooting a Full Transaction Log (Error 9002)" in SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87778-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="87778-123">See Also</span></span>  
 <span data-ttu-id="87778-124">[Solucionar problemas de un registro de transacciones lleno &#40;Error 9002 de SQL Server&#41;](../logs/troubleshoot-a-full-transaction-log-sql-server-error-9002.md) </span><span class="sxs-lookup"><span data-stu-id="87778-124">[Troubleshoot a Full Transaction Log &#40;SQL Server Error 9002&#41;](../logs/troubleshoot-a-full-transaction-log-sql-server-error-9002.md) </span></span>  
 [<span data-ttu-id="87778-125">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="87778-125">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
