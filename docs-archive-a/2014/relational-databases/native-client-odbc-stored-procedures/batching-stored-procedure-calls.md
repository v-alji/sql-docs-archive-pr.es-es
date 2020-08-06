---
title: Procesar por lotes las llamadas a procedimientos almacenados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- stored procedures [ODBC], batching
- ODBC, stored procedures
- SQL Server Native Client ODBC driver, stored procedures
- batches [ODBC]
- ODBC CALL escape sequence
ms.assetid: b7f53e11-15f0-4602-8134-b166160888f0
author: rothja
ms.author: jroth
ms.openlocfilehash: a0df58ce59853ee15b863cbc7bce34041c37fee4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750862"
---
# <a name="batching-stored-procedure-calls"></a><span data-ttu-id="fba41-102">Procesar por lotes las llamadas a procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="fba41-102">Batching Stored Procedure Calls</span></span>
  <span data-ttu-id="fba41-103">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] controlador ODBC de Native Client procesa automáticamente las llamadas a procedimientos almacenados en el servidor cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="fba41-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver automatically batches stored procedure calls to the server when appropriate.</span></span> <span data-ttu-id="fba41-104">El controlador solamente hace esto cuando se usa la secuencia de escape ODBC CALL; no lo hace para la instrucción EXECUTE de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fba41-104">The driver only does this when the ODBC CALL escape sequence is used; it does not do this for the [!INCLUDE[tsql](../../includes/tsql-md.md)] EXECUTE statement.</span></span> <span data-ttu-id="fba41-105">El procesamiento por lotes de las llamadas de procedimiento almacenado puede reducir el número de ciclos de ida y vuelta del servidor y aumentar de forma significativa el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="fba41-105">Batching stored procedure calls can reduce the number of round trips to the server and significantly increase performance.</span></span>  
  
 <span data-ttu-id="fba41-106">El controlador procesa por lotes las llamadas de procedimiento al servidor al ejecutar un lote que contiene varias secuencias de escape ODBC CALL.</span><span class="sxs-lookup"><span data-stu-id="fba41-106">The driver batches procedure calls to the server when you execute a batch that contains multiple ODBC CALL escape sequences.</span></span> <span data-ttu-id="fba41-107">También procesa por lotes las llamadas a procedimiento cuando se usan las matrices de parámetros enlazadas con una secuencia de escape ODBC CALL.</span><span class="sxs-lookup"><span data-stu-id="fba41-107">It also batches procedure calls when bound parameter arrays are used with an ODBC CALL escape sequence.</span></span> <span data-ttu-id="fba41-108">Por ejemplo, si utiliza el enlace de parámetro de modo de fila o de modo de columna para enlazar una matriz de cinco elementos a los parámetros de una instrucción SQL CALL de ODBC, cuando se llama a **SQLExecute** o **SQLExecDirect** , el controlador envía un único lote con cinco llamadas de procedimiento al servidor.</span><span class="sxs-lookup"><span data-stu-id="fba41-108">For example, if you use either row-wise or column-wise parameter binding to bind an array with five elements to the parameters of an ODBC CALL SQL statement, when **SQLExecute** or **SQLExecDirect** is called, the driver sends a single batch with five procedure calls to the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fba41-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fba41-109">See Also</span></span>  
 [<span data-ttu-id="fba41-110">Ejecutar procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="fba41-110">Running Stored Procedures</span></span>](running-stored-procedures.md)  
  
  
