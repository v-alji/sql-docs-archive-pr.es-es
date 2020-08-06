---
title: SQLNativeSql | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLNativeSql function
ms.assetid: 2d999fec-9e22-4514-ad5f-22a64b82f95b
author: rothja
ms.author: jroth
ms.openlocfilehash: 433b086dc36a79cb82868edebac9f0a4814c21fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677059"
---
# <a name="sqlnativesql"></a><span data-ttu-id="551c5-102">SQLNativeSql</span><span class="sxs-lookup"><span data-stu-id="551c5-102">SQLNativeSql</span></span>
  <span data-ttu-id="551c5-103">El controlador ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client satisface las solicitudes de **SQLNativeSql** sin pasar por el servidor.</span><span class="sxs-lookup"><span data-stu-id="551c5-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver satisfies **SQLNativeSql** requests without visiting the server.</span></span> <span data-ttu-id="551c5-104">La función prueba eficazmente la sintaxis de instrucciones SQL.</span><span class="sxs-lookup"><span data-stu-id="551c5-104">The function efficiently tests the syntax of SQL statements.</span></span> <span data-ttu-id="551c5-105">La comprobación de la sintaxis no determina si los identificadores o los resultados de expresiones en las instrucciones SQL son válidos, además [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] SQLNativeSql **devuelve un** SQL nativo que puede causar un error al ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="551c5-105">Syntax checking does not determine if identifiers or the results of expressions in the SQL statements are valid, and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native SQL returned by **SQLNativeSql** can fail to run.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="551c5-106">Consulte también</span><span class="sxs-lookup"><span data-stu-id="551c5-106">See Also</span></span>  
 <span data-ttu-id="551c5-107">[SQLNativeSql función)](https://go.microsoft.com/fwlink/?LinkID=59358) </span><span class="sxs-lookup"><span data-stu-id="551c5-107">[SQLNativeSql Function](https://go.microsoft.com/fwlink/?LinkID=59358) </span></span>  
 [<span data-ttu-id="551c5-108">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="551c5-108">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
