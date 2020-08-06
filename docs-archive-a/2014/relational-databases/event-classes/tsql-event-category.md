---
title: TSQL (categoría de eventos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- SQL Server event classes, TSQL event category
- TSQL event category [SQL Server]
- event classes [SQL Server], TSQL event category
ms.assetid: 215f8747-64b5-4bf3-9845-d476b10cda3a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 763d5f31fd3562f54b274a74324ed4715b623a18
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744099"
---
# <a name="tsql-event-category"></a><span data-ttu-id="d3473-102">TSQL (categoría de eventos)</span><span class="sxs-lookup"><span data-stu-id="d3473-102">TSQL Event Category</span></span>
  <span data-ttu-id="d3473-103">La categoría de eventos **TSQL** contiene eventos TSQL generales.</span><span class="sxs-lookup"><span data-stu-id="d3473-103">The **TSQL** event category contains general TSQL events.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d3473-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d3473-104">In This Section</span></span>  
  
|<span data-ttu-id="d3473-105">Tema</span><span class="sxs-lookup"><span data-stu-id="d3473-105">Topic</span></span>|<span data-ttu-id="d3473-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="d3473-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="d3473-107">Exec Prepared SQL (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="d3473-107">Exec Prepared SQL Event Class</span></span>](exec-prepared-sql-event-class.md)|<span data-ttu-id="d3473-108">Indica que SqlClient, ODBC, OLE DB o DB-Library ha ejecutado una o varias instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] preparadas.</span><span class="sxs-lookup"><span data-stu-id="d3473-108">Indicates that the SqlClient, ODBC, OLE DB, or DB-Library has executed a prepared [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or statements.</span></span>|  
|[<span data-ttu-id="d3473-109">Prepare SQL (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="d3473-109">Prepare SQL Event Class</span></span>](prepare-sql-event-class.md)|<span data-ttu-id="d3473-110">Indica que SqlClient, ODBC, OLE DB o DB-Library ha preparado para su uso una o varias instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d3473-110">Indicates that SqlClient, ODBC, OLE DB, or DB-Library has prepared a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or statements for use.</span></span>|  
|[<span data-ttu-id="d3473-111">SQL:BatchCompleted (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="d3473-111">SQL:BatchCompleted Event Class</span></span>](sql-batchcompleted-event-class.md)|<span data-ttu-id="d3473-112">Indica que se ha completado el procesamiento de un lote de instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d3473-112">Indicates that the [!INCLUDE[tsql](../../includes/tsql-md.md)] batch has completed.</span></span>|  
|[<span data-ttu-id="d3473-113">SQL:BatchStarting (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="d3473-113">SQL:BatchStarting Event Class</span></span>](sql-batchstarting-event-class.md)|<span data-ttu-id="d3473-114">Indica que se está iniciando el procesamiento de un lote de instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d3473-114">Indicates that the [!INCLUDE[tsql](../../includes/tsql-md.md)] batch is starting.</span></span>|  
|[<span data-ttu-id="d3473-115">SQL:StmtCompleted (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="d3473-115">SQL:StmtCompleted Event Class</span></span>](sql-stmtcompleted-event-class.md)|<span data-ttu-id="d3473-116">Indica que se ha completado una instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d3473-116">Indicates that a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement has completed.</span></span>|  
|[<span data-ttu-id="d3473-117">SQL:StmtRecompile (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="d3473-117">SQL:StmtRecompile Event Class</span></span>](sql-stmtrecompile-event-class.md)|<span data-ttu-id="d3473-118">Indica recopilaciones de nivel de instrucción producidas por lotes de todos los tipos: procedimientos almacenados, desencadenadores, lotes ad hoc y consultas.</span><span class="sxs-lookup"><span data-stu-id="d3473-118">Indicates statement-level recompilations caused by all types of batches: stored procedures, triggers, ad hoc batches, and queries.</span></span>|  
|[<span data-ttu-id="d3473-119">SQL:StmtStarting (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="d3473-119">SQL:StmtStarting Event Class</span></span>](sql-stmtstarting-event-class.md)|<span data-ttu-id="d3473-120">Indica que se está iniciando una instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d3473-120">Indicates that a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement is starting.</span></span>|  
|[<span data-ttu-id="d3473-121">Unprepare SQL (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="d3473-121">Unprepare SQL Event Class</span></span>](unprepare-sql-event-class.md)|<span data-ttu-id="d3473-122">Indica que SqlClient, ODBC, OLE DB o DB-Library ha eliminado una o varias instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] preparadas.</span><span class="sxs-lookup"><span data-stu-id="d3473-122">Indicates that the SqlClient, ODBC, OLE DB, or DB-Library has deleted a prepared [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or statements.</span></span>|  
|[<span data-ttu-id="d3473-123">XQuery Static Type (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="d3473-123">XQuery Static Type Event Class</span></span>](xquery-static-type-event-class.md)|<span data-ttu-id="d3473-124">Se produce cuando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ejecuta una expresión XQuery.</span><span class="sxs-lookup"><span data-stu-id="d3473-124">Occurs when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executes an XQuery expression.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d3473-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d3473-125">See Also</span></span>  
 [<span data-ttu-id="d3473-126">Referencia de Transact-SQL &#40;motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="d3473-126">Transact-SQL Reference &#40;Database Engine&#41;</span></span>](/sql/t-sql/language-reference)  
  
  
