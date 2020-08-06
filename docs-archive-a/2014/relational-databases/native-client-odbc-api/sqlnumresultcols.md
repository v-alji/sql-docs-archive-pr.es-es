---
title: SQLNumResultCols | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLNumResultCols function
ms.assetid: f79d8b3c-521e-4e50-a564-21d73ae5767b
author: rothja
ms.author: jroth
ms.openlocfilehash: 45e72165eef621dc377b02ed3d2e7e1e3cf7ab8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677058"
---
# <a name="sqlnumresultcols"></a><span data-ttu-id="7c708-102">SQLNumResultCols</span><span class="sxs-lookup"><span data-stu-id="7c708-102">SQLNumResultCols</span></span>
  <span data-ttu-id="7c708-103">Para las instrucciones ejecutadas, el controlador ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client no tiene acceso al servidor para notificar el número de columnas de un conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="7c708-103">For executed statements, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver does not visit the server to report the number of columns in a result set.</span></span> <span data-ttu-id="7c708-104">En este caso, `SQLNumResultCols` no produce un viaje de ida y vuelta al servidor.</span><span class="sxs-lookup"><span data-stu-id="7c708-104">In this case, `SQLNumResultCols` does not cause a server roundtrip.</span></span> <span data-ttu-id="7c708-105">Como [SQLDescribeCol](sqldescribecol.md) y [SQLColAttribute](sqlcolattribute.md), al llamar a `SQLNumResultCols` en instrucciones preparadas pero no ejecutadas se genera un viaje de ida y vuelta al servidor.</span><span class="sxs-lookup"><span data-stu-id="7c708-105">Like [SQLDescribeCol](sqldescribecol.md) and [SQLColAttribute](sqlcolattribute.md), calling `SQLNumResultCols` on prepared but not executed statements generates a server roundtrip.</span></span>  
  
 <span data-ttu-id="7c708-106">Cuando una instrucción o un lote de instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] devuelve varios conjuntos de filas de resultados, es posible que el número de columnas del conjunto de resultados cambie de un conjunto a otro.</span><span class="sxs-lookup"><span data-stu-id="7c708-106">When a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or statement batch returns multiple result row sets, it is possible for the number of result set columns to change from one set to another.</span></span> <span data-ttu-id="7c708-107">`SQLNumResultCols`se debe llamar a para cada conjunto.</span><span class="sxs-lookup"><span data-stu-id="7c708-107">`SQLNumResultCols` should be called for each set.</span></span> <span data-ttu-id="7c708-108">Cuando el número de columnas cambia, la aplicación debe volver a enlazar los valores de datos antes de capturar los resultados de la fila.</span><span class="sxs-lookup"><span data-stu-id="7c708-108">When the number of columns changes, the application should rebind data values prior to fetching row results.</span></span> <span data-ttu-id="7c708-109">Para obtener más información sobre cómo administrar la devolución de varios conjuntos de resultados, vea [SQLMoreResults](sqlmoreresults.md).</span><span class="sxs-lookup"><span data-stu-id="7c708-109">For more information about handling multiple result set returns, see [SQLMoreResults](sqlmoreresults.md).</span></span>  
  
 <span data-ttu-id="7c708-110">Las mejoras en el motor de base de datos a partir de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] permiten a SQLNumResultCols obtener descripciones más precisas de los resultados esperados.</span><span class="sxs-lookup"><span data-stu-id="7c708-110">Improvements in the database engine starting with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] allow SQLNumResultCols to obtain more accurate descriptions of the expected results.</span></span> <span data-ttu-id="7c708-111">Estos resultados más precisos pueden diferir de los valores devueltos por SQLNumResultCols en versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7c708-111">These more accurate results may differ from the values returned by SQLNumResultCols in previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7c708-112">Para obtener más información, vea [Detección de metadatos](../native-client/features/metadata-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="7c708-112">For more information, see [Metadata Discovery](../native-client/features/metadata-discovery.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c708-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7c708-113">See Also</span></span>  
 <span data-ttu-id="7c708-114">[SQLNumResultCols función)](https://go.microsoft.com/fwlink/?LinkId=59359) </span><span class="sxs-lookup"><span data-stu-id="7c708-114">[SQLNumResultCols Function](https://go.microsoft.com/fwlink/?LinkId=59359) </span></span>  
 [<span data-ttu-id="7c708-115">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="7c708-115">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
