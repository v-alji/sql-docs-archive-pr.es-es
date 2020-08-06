---
title: Procedimientos almacenados compilados de forma nativa y opciones SET de ejecución | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: c1869cf7-9030-4d18-85d6-0e419a4e9af7
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 264a2b3ab1e6f3f0bda97bfe89a4438aa641577d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750969"
---
# <a name="natively-compiled-stored-procedures-and-execution-set-options"></a><span data-ttu-id="d6eba-102">Procedimientos almacenados compilados de forma nativa y opciones SET de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d6eba-102">Natively Compiled Stored Procedures and Execution Set Options</span></span>
  <span data-ttu-id="d6eba-103">Las opciones de sesión son fijas en los bloques atomic.</span><span class="sxs-lookup"><span data-stu-id="d6eba-103">Session options are fixed in atomic blocks.</span></span> <span data-ttu-id="d6eba-104">La ejecución de un procedimiento almacenado no se ve afectada por las opciones SET de una sesión.</span><span class="sxs-lookup"><span data-stu-id="d6eba-104">A stored procedure's execution is not affected by a session's SET options.</span></span> <span data-ttu-id="d6eba-105">Sin embargo, ciertas opciones SET, como SET NOEXEC y SET SHOWPLAN_XML, causan que no se ejecuten los procedimientos almacenados (incluidos los compilados de forma nativa).</span><span class="sxs-lookup"><span data-stu-id="d6eba-105">However, certain SET options, such as SET NOEXEC and SET SHOWPLAN_XML, cause stored procedures (including natively compiled stored procedures) to not execute.</span></span>  
  
 <span data-ttu-id="d6eba-106">Cuando un procedimiento almacenado de forma nativa se ejecuta con la opción STATISTICS activada, las estadísticas se obtienen para el procedimiento en su conjunto y no para cada instrucción.</span><span class="sxs-lookup"><span data-stu-id="d6eba-106">When a natively compiled stored procedure is executed with any STATISTICS option turned on, statistics are gathered for the procedure as a whole and not per statement.</span></span> <span data-ttu-id="d6eba-107">Para obtener más información, vea [SET STATISTICS IO &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-io-transact-sql), [SET STATISTICS PROFILE &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-profile-transact-sql), [SET STATISTICS TIME &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-time-transact-sql) y [SET STATISTICS XML &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-xml-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d6eba-107">For more information, see [SET STATISTICS IO &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-io-transact-sql), [SET STATISTICS PROFILE &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-profile-transact-sql), [SET STATISTICS TIME &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-time-transact-sql), and [SET STATISTICS XML &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-xml-transact-sql).</span></span> <span data-ttu-id="d6eba-108">Para obtener estadísticas de ejecución de nivel de instrucción para los procedimientos almacenados compilados de forma nativa, use una sesión de eventos extendidos en el evento sp_statement_completed, que se inicia cuando finaliza cada una de las consultas de una ejecución de procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="d6eba-108">To obtain execution statistics on a per-statement level in natively compiled stored procedures, use an Extended Event session on the sp_statement_completed event, which starts when each individual query in a stored procedures execution completes.</span></span> <span data-ttu-id="d6eba-109">Para obtener más información sobre cómo crear sesiones de eventos extendidos, vea [CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d6eba-109">For more information on creating Extended Event sessions, see [CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql).</span></span>  
  
 <span data-ttu-id="d6eba-110">`SHOWPLAN_XML` se admite para procedimientos almacenados compilados de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="d6eba-110">`SHOWPLAN_XML` is supported for natively compiled stored procedures.</span></span> <span data-ttu-id="d6eba-111">`SHOWPLAN_ALL` y `SHOWPLAN_TEXT` no son compatibles con los procedimientos almacenados compilados de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="d6eba-111">`SHOWPLAN_ALL` and `SHOWPLAN_TEXT` are not supported with natively compiled stored procedures.</span></span>  
  
 <span data-ttu-id="d6eba-112">`SET FMTONLY` no es compatible con los procedimientos almacenados compilados de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="d6eba-112">`SET FMTONLY` in not supported with natively compiled stored procedures.</span></span> <span data-ttu-id="d6eba-113">Use en su lugar [sp_describe_first_result_set &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-describe-first-result-set-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d6eba-113">Use [sp_describe_first_result_set &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-describe-first-result-set-transact-sql) instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6eba-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d6eba-114">See Also</span></span>  
 [<span data-ttu-id="d6eba-115">Procedimientos almacenados compilados de forma nativa</span><span class="sxs-lookup"><span data-stu-id="d6eba-115">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
