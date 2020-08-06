---
title: Ejecutar instrucciones (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, statements
- statements [ODBC]
- ODBC applications, statements
- statements [ODBC], executing
ms.assetid: 063fc40d-ff81-490d-9c9b-2faefb729f37
author: rothja
ms.author: jroth
ms.openlocfilehash: 3066a09cb1f5e63105ca3ffe2441f19e4bbe0101
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662875"
---
# <a name="executing-statements-odbc"></a><span data-ttu-id="e8d03-102">Ejecutar instrucciones (ODBC)</span><span class="sxs-lookup"><span data-stu-id="e8d03-102">Executing Statements (ODBC)</span></span>
  <span data-ttu-id="e8d03-103">El [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] controlador ODBC de Native Client ofrece varias maneras de ejecutar instrucciones SQL en una [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] base de datos:</span><span class="sxs-lookup"><span data-stu-id="e8d03-103">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver offers a variety ways to execute SQL statements in a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database:</span></span>  
  
-   <span data-ttu-id="e8d03-104">Ejecución directa</span><span class="sxs-lookup"><span data-stu-id="e8d03-104">Direct execution</span></span>  
  
-   <span data-ttu-id="e8d03-105">Ejecución preparada</span><span class="sxs-lookup"><span data-stu-id="e8d03-105">Prepared execution</span></span>  
  
 <span data-ttu-id="e8d03-106">La ejecución directa implica la creación de una cadena de caracteres que contiene una [!INCLUDE[tsql](../../../includes/tsql-md.md)] instrucción y su envío para su ejecución mediante la función **SQLExecDirect** .</span><span class="sxs-lookup"><span data-stu-id="e8d03-106">Direct execution involves building a character string containing a [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement and submitting it for execution using the **SQLExecDirect** function.</span></span> <span data-ttu-id="e8d03-107">La ejecución preparada implica la creación de una cadena de caracteres que contiene una instrucción [!INCLUDE[tsql](../../../includes/tsql-md.md)] y su posterior ejecución en dos fases.</span><span class="sxs-lookup"><span data-stu-id="e8d03-107">Prepared execution involves building a character string containing a [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement and then executing it in two stages.</span></span> <span data-ttu-id="e8d03-108">En la primera fase se usa la función de [función SQLPrepare](https://go.microsoft.com/fwlink/?LinkId=59360) para analizar y compilar el plan de ejecución de la instrucción en [!INCLUDE[ssDE](../../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e8d03-108">The first stage uses the [SQLPrepare Function](https://go.microsoft.com/fwlink/?LinkId=59360) function to parse and compile the execution plan for the statement in the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span> <span data-ttu-id="e8d03-109">En la segunda fase se usa la función **SQLExecute** para ejecutar el plan de ejecución previamente preparado.</span><span class="sxs-lookup"><span data-stu-id="e8d03-109">The second stage uses the **SQLExecute** function to execute the previously prepared execution plan.</span></span> <span data-ttu-id="e8d03-110">De esta forma, se guarda la sobrecarga de análisis y compilación en cada ejecución.</span><span class="sxs-lookup"><span data-stu-id="e8d03-110">This saves the parsing and compiling overhead on each execution.</span></span> <span data-ttu-id="e8d03-111">Las aplicaciones suelen usar la ejecución preparada para ejecutar repetidamente una misma instrucción SQL parametrizada.</span><span class="sxs-lookup"><span data-stu-id="e8d03-111">Prepared execution is commonly used by applications to repeatedly execute the same, parameterized SQL statement.</span></span>  
  
 <span data-ttu-id="e8d03-112">Tanto en la ejecución directa como en la ejecución preparada puede ejecutarse una única instrucción de [!INCLUDE[tsql](../../../includes/tsql-md.md)] o un lote de instrucciones de SQL, o puede llamarse a un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="e8d03-112">Both direct and prepared execution can execute a single [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement or a batch of SQL statements, or they can call a stored procedure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e8d03-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e8d03-113">In This Section</span></span>  
  
-   [<span data-ttu-id="e8d03-114">Ejecución directa</span><span class="sxs-lookup"><span data-stu-id="e8d03-114">Direct Execution</span></span>](direct-execution.md)  
  
-   [<span data-ttu-id="e8d03-115">Ejecución preparada</span><span class="sxs-lookup"><span data-stu-id="e8d03-115">Prepared Execution</span></span>](prepared-execution.md)  
  
-   [<span data-ttu-id="e8d03-116">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="e8d03-116">Procedures</span></span>](procedures.md)  
  
-   [<span data-ttu-id="e8d03-117">Lotes de instrucciones</span><span class="sxs-lookup"><span data-stu-id="e8d03-117">Batches of Statements</span></span>](batches-of-statements.md)  
  
-   [<span data-ttu-id="e8d03-118">Efectos de las opciones ISO</span><span class="sxs-lookup"><span data-stu-id="e8d03-118">Effects of ISO Options</span></span>](effects-of-iso-options.md)  
  
## <a name="see-also"></a><span data-ttu-id="e8d03-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e8d03-119">See Also</span></span>  
 [<span data-ttu-id="e8d03-120">Ejecutar consultas &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="e8d03-120">Executing Queries &#40;ODBC&#41;</span></span>](../executing-queries-odbc.md)  
  
  
