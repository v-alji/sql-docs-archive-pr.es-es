---
title: Recuperar información del conjunto de resultados (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- result sets [ODBC]
- result sets [ODBC], fetching
ms.assetid: 34f235e4-f80b-4123-8764-9deb18506f14
author: rothja
ms.author: jroth
ms.openlocfilehash: 0f7ed275eb9b6558a77160c3c7fb2fc233c199cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671037"
---
# <a name="retrieve-result-set-information-odbc"></a><span data-ttu-id="57293-102">Recuperar información del conjunto de resultados (ODBC)</span><span class="sxs-lookup"><span data-stu-id="57293-102">Retrieve Result Set Information (ODBC)</span></span>
    
### <a name="to-get-information-about-a-result-set"></a><span data-ttu-id="57293-103">Para obtener información sobre un conjunto de resultados</span><span class="sxs-lookup"><span data-stu-id="57293-103">To get information about a result set</span></span>  
  
1.  <span data-ttu-id="57293-104">Llame a [SQLNumResultCols](../native-client-odbc-api/sqlnumresultcols.md) para obtener el número de columnas del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="57293-104">Call [SQLNumResultCols](../native-client-odbc-api/sqlnumresultcols.md) to get the number of columns in the result set.</span></span>  
  
2.  <span data-ttu-id="57293-105">Para cada columna del conjunto de resultados:</span><span class="sxs-lookup"><span data-stu-id="57293-105">For each column in the result set:</span></span>  
  
    -   <span data-ttu-id="57293-106">Llame a [SQLDescribeCol](../native-client-odbc-api/sqldescribecol.md) para obtener información sobre la columna de resultados.</span><span class="sxs-lookup"><span data-stu-id="57293-106">Call [SQLDescribeCol](../native-client-odbc-api/sqldescribecol.md) to get information about the result column.</span></span>  
  
     <span data-ttu-id="57293-107">Or</span><span class="sxs-lookup"><span data-stu-id="57293-107">Or</span></span>  
  
    -   <span data-ttu-id="57293-108">Llame a [SQLColAttribute](../native-client-odbc-api/sqlcolattribute.md) para obtener información específica del descriptor sobre la columna de resultados.</span><span class="sxs-lookup"><span data-stu-id="57293-108">Call [SQLColAttribute](../native-client-odbc-api/sqlcolattribute.md) to get specific descriptor information about the result column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57293-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="57293-109">See Also</span></span>  
 <span data-ttu-id="57293-110">[Temas de procedimientos de procesamiento de resultados &#40;ODBC&#41;](../../database-engine/dev-guide/processing-results-how-to-topics-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="57293-110">[Processing Results How-to Topics &#40;ODBC&#41;](../../database-engine/dev-guide/processing-results-how-to-topics-odbc.md) </span></span>  
 [<span data-ttu-id="57293-111">Determinar las características de un conjunto de resultados &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="57293-111">Determining the Characteristics of a Result Set &#40;ODBC&#41;</span></span>](../native-client-odbc-results/determining-the-characteristics-of-a-result-set-odbc.md)  
  
  
