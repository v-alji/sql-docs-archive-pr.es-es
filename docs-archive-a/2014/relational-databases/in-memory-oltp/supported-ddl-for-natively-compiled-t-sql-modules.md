---
title: Construcciones admitidas en procedimientos almacenados compilados de forma nativa | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 6b21f47e-bceb-4054-8b3c-9d39bb9583c0
author: rothja
ms.author: jroth
ms.openlocfilehash: f3bc7e28fa2a868ac39c6adbb2dea3cc5c3ace73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671547"
---
# <a name="supported-constructs-on-natively-compiled-stored-procedures"></a><span data-ttu-id="1d2c5-102">Construcciones admitidas en procedimientos almacenados compilados de forma nativa</span><span class="sxs-lookup"><span data-stu-id="1d2c5-102">Supported Constructs on Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="1d2c5-103">En este tema se enumeran las construcciones admitidas en procedimientos almacenados compilados de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="1d2c5-103">This topic lists the supported constructs on natively compiled stored procedures.</span></span>  
  
 <span data-ttu-id="1d2c5-104">Para obtener información sobre las construcciones no compatibles, vea [Construcciones Transact-SQL no admitidas por OLTP en memoria](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span><span class="sxs-lookup"><span data-stu-id="1d2c5-104">For information about unsupported constructs, see [Transact-SQL Constructs Not Supported by In-Memory OLTP](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span></span>  
  
## <a name="procedure-ddl"></a><span data-ttu-id="1d2c5-105">Procedimiento DDL</span><span class="sxs-lookup"><span data-stu-id="1d2c5-105">Procedure DDL</span></span>  
 <span data-ttu-id="1d2c5-106">Se admite lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1d2c5-106">The following are supported:</span></span>  
  
-   <span data-ttu-id="1d2c5-107">CREATE PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="1d2c5-107">CREATE PROCEDURE</span></span>  
  
-   <span data-ttu-id="1d2c5-108">DROP PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="1d2c5-108">DROP PROCEDURE</span></span>  
  
-   <span data-ttu-id="1d2c5-109">SCHEMABINDING (se requiere para los procedimientos almacenados compilados de forma nativa)</span><span class="sxs-lookup"><span data-stu-id="1d2c5-109">SCHEMABINDING (required for natively compiled stored procedures)</span></span>  
  
-   <span data-ttu-id="1d2c5-110">NATIVE_COMPILATION</span><span class="sxs-lookup"><span data-stu-id="1d2c5-110">NATIVE_COMPILATION</span></span>  
  
-   <span data-ttu-id="1d2c5-111">Es posible declarar los parámetros como NOT NULL.</span><span class="sxs-lookup"><span data-stu-id="1d2c5-111">Parameters can be declared as NOT NULL.</span></span>  
  
-   <span data-ttu-id="1d2c5-112">Parámetros con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="1d2c5-112">Table-valued parameters.</span></span>  
  
## <a name="security"></a><span data-ttu-id="1d2c5-113">Seguridad</span><span class="sxs-lookup"><span data-stu-id="1d2c5-113">Security</span></span>  
 <span data-ttu-id="1d2c5-114">Se admite lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1d2c5-114">The following are supported:</span></span>  
  
-   <span data-ttu-id="1d2c5-115">Para procedimientos: EXECUTE AS OWNER, SELF y usuario.</span><span class="sxs-lookup"><span data-stu-id="1d2c5-115">For procedures: EXECUTE AS OWNER, SELF, and user.</span></span>  
  
-   <span data-ttu-id="1d2c5-116">GRANT (conceda) y DENY (deniegue) permisos a las tablas y los procedimientos.</span><span class="sxs-lookup"><span data-stu-id="1d2c5-116">GRANT and DENY permissions on tables and procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d2c5-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1d2c5-117">See Also</span></span>  
 [<span data-ttu-id="1d2c5-118">Procedimientos almacenados compilados de forma nativa</span><span class="sxs-lookup"><span data-stu-id="1d2c5-118">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
