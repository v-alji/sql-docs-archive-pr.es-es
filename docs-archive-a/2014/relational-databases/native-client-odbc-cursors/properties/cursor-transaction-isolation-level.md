---
title: Nivel de aislamiento de transacción de cursor | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- isolation levels [ODBC]
- ODBC applications, row versioning
- cursors [ODBC], isolation levels
- ODBC cursors, isolation levels
- row versioning [SQL Server], ODBC
ms.assetid: 0c6663a4-5a25-44aa-8fe4-e35af9bf4a83
author: rothja
ms.author: jroth
ms.openlocfilehash: 30f3dc8a9136a7cbe1d5897cb0bcc9fff8c35ab2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748784"
---
# <a name="cursor-transaction-isolation-level"></a><span data-ttu-id="91346-102">Nivel de aislamiento de las transacciones de cursores</span><span class="sxs-lookup"><span data-stu-id="91346-102">Cursor Transaction Isolation Level</span></span>
  <span data-ttu-id="91346-103">El comportamiento de bloqueo completo de cursores se basa en una interacción entre los atributos de simultaneidad y el nivel de aislamiento de transacciones establecido por el cliente.</span><span class="sxs-lookup"><span data-stu-id="91346-103">The complete locking behavior of cursors is based on an interaction between concurrency attributes and the transaction isolation level set by the client.</span></span> <span data-ttu-id="91346-104">Los clientes ODBC establecen el nivel de aislamiento de transacción mediante los atributos [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) SQL_ATTR_TXN_ISOLATION o SQL_COPT_SS_TXN_ISOLATION.</span><span class="sxs-lookup"><span data-stu-id="91346-104">ODBC clients set the transaction isolation level using the [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) SQL_ATTR_TXN_ISOLATION or SQL_COPT_SS_TXN_ISOLATION attributes.</span></span> <span data-ttu-id="91346-105">El comportamiento del bloqueo de un entorno de cursor específico se determina mediante la combinación de los comportamientos de bloqueo de las opciones de simultaneidad y de nivel de aislamiento de transacción.</span><span class="sxs-lookup"><span data-stu-id="91346-105">The locking behavior of a specific cursor environment is determined by combining the locking behaviors of the concurrency and transaction isolation level options.</span></span>  
  
 <span data-ttu-id="91346-106">El controlador ODBC de Native Client admite los siguientes niveles de aislamiento de transacción de cursor [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="91346-106">The following cursor transaction isolation levels are supported by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver:</span></span>  
  
-   <span data-ttu-id="91346-107">Lectura confirmada (SQL_TXN_READ_COMMITTED)</span><span class="sxs-lookup"><span data-stu-id="91346-107">Read committed (SQL_TXN_READ_COMMITTED)</span></span>  
  
-   <span data-ttu-id="91346-108">Lectura no confirmada (SQL_TXN_READ_UNCOMMITTED)</span><span class="sxs-lookup"><span data-stu-id="91346-108">Read uncommitted (SQL_TXN_READ_UNCOMMITTED)</span></span>  
  
-   <span data-ttu-id="91346-109">Lectura repetible (SQL_TXN_REPEATABLE_READ)</span><span class="sxs-lookup"><span data-stu-id="91346-109">Repeatable read (SQL_TXN_REPEATABLE_READ)</span></span>  
  
-   <span data-ttu-id="91346-110">Serializable (SQL_TXN_SERIALIZABLE)</span><span class="sxs-lookup"><span data-stu-id="91346-110">Serializable (SQL_TXN_SERIALIZABLE)</span></span>  
  
-   <span data-ttu-id="91346-111">Instantánea (SQL_TXN_SS_SNAPSHOT)</span><span class="sxs-lookup"><span data-stu-id="91346-111">Snapshot (SQL_TXN_SS_SNAPSHOT)</span></span>  
  
 <span data-ttu-id="91346-112">Tenga en cuenta que la API de ODBC especifica niveles de aislamiento de transacción adicionales, pero no es compatible con [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ni con el [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] controlador ODBC de Native Client.</span><span class="sxs-lookup"><span data-stu-id="91346-112">Note that the ODBC API specifies additional transaction isolation levels, but these are not supported by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91346-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="91346-113">See Also</span></span>  
 [<span data-ttu-id="91346-114">Propiedades de cursor</span><span class="sxs-lookup"><span data-stu-id="91346-114">Cursor Properties</span></span>](cursor-properties.md)  
  
  
