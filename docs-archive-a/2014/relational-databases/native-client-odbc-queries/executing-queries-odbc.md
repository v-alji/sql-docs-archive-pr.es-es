---
title: Ejecutar consultas (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC applications, executing queries
- SQL Server Native Client ODBC driver, statements
- ODBC applications, statements
- SQL Server Native Client ODBC driver, queries
- queries [ODBC]
ms.assetid: d935bcba-8ce6-4159-8395-6c86431602ad
author: rothja
ms.author: jroth
ms.openlocfilehash: adc51186803148056401f58f1207d3e9a7abf9c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662881"
---
# <a name="executing-queries-odbc"></a><span data-ttu-id="e6442-102">Ejecutar consultas (ODBC)</span><span class="sxs-lookup"><span data-stu-id="e6442-102">Executing Queries (ODBC)</span></span>
  <span data-ttu-id="e6442-103">Después de que una aplicación ODBC inicializa un identificador de conexión y conecta con un origen de datos, asigna uno o más identificadores de instrucciones en el identificador de conexión.</span><span class="sxs-lookup"><span data-stu-id="e6442-103">After an ODBC application initializes a connection handle and connects with a data source, it allocates one or more statement handles on the connection handle.</span></span> <span data-ttu-id="e6442-104">A continuación, la aplicación puede ejecutar [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instrucciones en el identificador de instrucción.</span><span class="sxs-lookup"><span data-stu-id="e6442-104">The application can then execute [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] statements on the statement handle.</span></span> <span data-ttu-id="e6442-105">La secuencia general de eventos para ejecutar una instrucción SQL es:</span><span class="sxs-lookup"><span data-stu-id="e6442-105">The general sequence of events in executing an SQL statement is:</span></span>  
  
1.  <span data-ttu-id="e6442-106">Establezca los atributos de instrucción necesarios.</span><span class="sxs-lookup"><span data-stu-id="e6442-106">Set any required statement attributes.</span></span>  
  
2.  <span data-ttu-id="e6442-107">Construya la instrucción.</span><span class="sxs-lookup"><span data-stu-id="e6442-107">Construct the statement.</span></span>  
  
3.  <span data-ttu-id="e6442-108">Ejecute la instrucción.</span><span class="sxs-lookup"><span data-stu-id="e6442-108">Execute the statement.</span></span>  
  
4.  <span data-ttu-id="e6442-109">Recupere los conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="e6442-109">Retrieve any result sets.</span></span>  
  
 <span data-ttu-id="e6442-110">Después de que una aplicación recupera todas las filas en todos los conjuntos de resultados devueltos por la instrucción SQL, puede ejecutar otra consulta en el mismo identificador de instrucciones.</span><span class="sxs-lookup"><span data-stu-id="e6442-110">After an application retrieves all the rows in all of the result sets returned by the SQL statement, it can execute another query on the same statement handle.</span></span> <span data-ttu-id="e6442-111">Si una aplicación determina que no es necesario recuperar todas las filas de un conjunto de resultados determinado, puede cancelar el resto del conjunto de resultados llamando a [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) o [SQLCloseCursor](../native-client-odbc-api/sqlclosecursor.md).</span><span class="sxs-lookup"><span data-stu-id="e6442-111">If an application determines that it is not required to retrieve all the rows in a particular result set, it can cancel the rest of the result set by calling either [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) or [SQLCloseCursor](../native-client-odbc-api/sqlclosecursor.md).</span></span>  
  
 <span data-ttu-id="e6442-112">Si, en una aplicación ODBC, debe ejecutar varias veces la misma instrucción SQL con datos diferentes, utilice en la construcción de la instrucción SQL un marcador de parámetros denotado por un signo de interrogación (?)</span><span class="sxs-lookup"><span data-stu-id="e6442-112">If, in an ODBC application, you must execute the same SQL statement multiple times with different data, use a parameter marker denoted by a question mark (?) in the construction of an SQL statement:</span></span>  
  
```  
INSERT INTO MyTable VALUES (?, ?, ?)  
```  
  
 <span data-ttu-id="e6442-113">Cada marcador de parámetro se puede enlazar a una variable de programa llamando a [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md).</span><span class="sxs-lookup"><span data-stu-id="e6442-113">Each parameter marker can then be bound to a program variable by calling [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md).</span></span>  
  
 <span data-ttu-id="e6442-114">Una vez ejecutadas todas las instrucciones SQL y procesados sus conjuntos de resultados, la aplicación libera el identificador de instrucción.</span><span class="sxs-lookup"><span data-stu-id="e6442-114">After all SQL statements execute and their result sets process, the application frees the statement handle.</span></span>  
  
 <span data-ttu-id="e6442-115">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] controlador ODBC de Native Client admite varios identificadores de instrucción por cada identificador de conexión.</span><span class="sxs-lookup"><span data-stu-id="e6442-115">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports multiple statement handles per connection handle.</span></span> <span data-ttu-id="e6442-116">Las transacciones se administran en el nivel de conexión, para que todo el trabajo realizado en todos los identificadores de instrucciones de una única conexión se administre como parte de la misma transacción.</span><span class="sxs-lookup"><span data-stu-id="e6442-116">Transactions are managed at the connection level, so that all work performed on all statement handles on a single connection handle are managed as part of the same transaction.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e6442-117">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e6442-117">In This Section</span></span>  
  
-   [<span data-ttu-id="e6442-118">Asignar un identificador de instrucción</span><span class="sxs-lookup"><span data-stu-id="e6442-118">Allocating a Statement Handle</span></span>](allocating-a-statement-handle.md)  
  
-   [<span data-ttu-id="e6442-119">Construir una instrucción SQL &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="e6442-119">Constructing an SQL Statement &#40;ODBC&#41;</span></span>](constructing-an-sql-statement-odbc.md)  
  
-   [<span data-ttu-id="e6442-120">Crear instrucciones SQL para cursores</span><span class="sxs-lookup"><span data-stu-id="e6442-120">Constructing SQL Statements for Cursors</span></span>](constructing-sql-statements-for-cursors.md)  
  
-   [<span data-ttu-id="e6442-121">Usar parámetros de instrucciones</span><span class="sxs-lookup"><span data-stu-id="e6442-121">Using Statement Parameters</span></span>](using-statement-parameters.md)  
  
-   [<span data-ttu-id="e6442-122">Ejecutar instrucciones &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="e6442-122">Executing Statements &#40;ODBC&#41;</span></span>](executing-statements/executing-statements-odbc.md)  
  
-   [<span data-ttu-id="e6442-123">Liberar un identificador de instrucción</span><span class="sxs-lookup"><span data-stu-id="e6442-123">Freeing a Statement Handle</span></span>](freeing-a-statement-handle.md)  
  
## <a name="see-also"></a><span data-ttu-id="e6442-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e6442-124">See Also</span></span>  
 [<span data-ttu-id="e6442-125">SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="e6442-125">SQL Server Native Client &#40;ODBC&#41;</span></span>](../native-client/odbc/sql-server-native-client-odbc.md)  
  
  
