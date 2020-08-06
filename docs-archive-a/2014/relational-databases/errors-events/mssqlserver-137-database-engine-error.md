---
title: MSSQLSERVER_137 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 137 (Database Engine error)
ms.assetid: 47fb4212-2165-4fec-bc41-6d548465d7be
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e0142cd53006609e9274972e4f5964132f5982c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675960"
---
# <a name="mssqlserver_137"></a><span data-ttu-id="a234e-102">MSSQLSERVER_137</span><span class="sxs-lookup"><span data-stu-id="a234e-102">MSSQLSERVER_137</span></span>
    
## <a name="details"></a><span data-ttu-id="a234e-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="a234e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a234e-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="a234e-104">Product Name</span></span>|<span data-ttu-id="a234e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a234e-105">SQL Server</span></span>|  
|<span data-ttu-id="a234e-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="a234e-106">Event ID</span></span>|<span data-ttu-id="a234e-107">137</span><span class="sxs-lookup"><span data-stu-id="a234e-107">137</span></span>|  
|<span data-ttu-id="a234e-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="a234e-108">Event Source</span></span>|<span data-ttu-id="a234e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a234e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a234e-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a234e-110">Component</span></span>|<span data-ttu-id="a234e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a234e-111">SQLEngine</span></span>|  
|<span data-ttu-id="a234e-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="a234e-112">Symbolic Name</span></span>|<span data-ttu-id="a234e-113">P_SCALAR_VAR_NOTFOUND</span><span class="sxs-lookup"><span data-stu-id="a234e-113">P_SCALAR_VAR_NOTFOUND</span></span>|  
|<span data-ttu-id="a234e-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="a234e-114">Message Text</span></span>|<span data-ttu-id="a234e-115">Debe declarar la variable escalar "%.\*ls".</span><span class="sxs-lookup"><span data-stu-id="a234e-115">Must declare the scalar variable "%.\*ls".</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a234e-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="a234e-116">Explanation</span></span>  
 <span data-ttu-id="a234e-117">Este error se produce cuando una variable se utiliza en un script SQL sin declararla primero.</span><span class="sxs-lookup"><span data-stu-id="a234e-117">This error occurs when a variable is used in a SQL script without first declaring the variable.</span></span> <span data-ttu-id="a234e-118">En el ejemplo siguiente se devuelve el error 137 para las instrucciones SET y SELECT porque **@mycol** no se ha declarado.</span><span class="sxs-lookup"><span data-stu-id="a234e-118">The following example returns error 137 for both the SET and SELECT statements because **@mycol** is not declared.</span></span>  
  
 <span data-ttu-id="a234e-119">SET @mycol = 'ContactName'</span><span class="sxs-lookup"><span data-stu-id="a234e-119">SET @mycol = 'ContactName';</span></span>  
  
 <span data-ttu-id="a234e-120">SELECT @mycol</span><span class="sxs-lookup"><span data-stu-id="a234e-120">SELECT @mycol;</span></span>  
  
 <span data-ttu-id="a234e-121">Una de las causas más complicadas de este error incluye el uso de una variable que se declara fuera de la instrucción EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="a234e-121">One of the more complicated causes of this error includes the use of a variable that is declared outside the EXECUTE statement.</span></span> <span data-ttu-id="a234e-122">Por ejemplo, la variable **@mycol** especificada en la instrucción SELECT es local para la instrucción SELECT; por tanto, está fuera de la instrucción EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="a234e-122">For example, the variable **@mycol** specified in the SELECT statement is local to the SELECT statement; thus it is outside the EXECUTE statement.</span></span>  
  
 <span data-ttu-id="a234e-123">USE AdventureWorks2012;</span><span class="sxs-lookup"><span data-stu-id="a234e-123">USE AdventureWorks2012;</span></span>  
  
 <span data-ttu-id="a234e-124">GO</span><span class="sxs-lookup"><span data-stu-id="a234e-124">GO</span></span>  
  
 <span data-ttu-id="a234e-125">DECLARE @mycol nvarchar(20);</span><span class="sxs-lookup"><span data-stu-id="a234e-125">DECLARE @mycol nvarchar(20);</span></span>  
  
 <span data-ttu-id="a234e-126">SET @mycol = 'Name'</span><span class="sxs-lookup"><span data-stu-id="a234e-126">SET @mycol = 'Name';</span></span>  
  
 <span data-ttu-id="a234e-127">EXECUTE ('SELECT @mycol FROM Production.Product;')</span><span class="sxs-lookup"><span data-stu-id="a234e-127">EXECUTE ('SELECT @mycol FROM Production.Product;');</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a234e-128">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="a234e-128">User Action</span></span>  
 <span data-ttu-id="a234e-129">Compruebe que cualquier variable que se use en un script SQL se declara antes de utilizarse en otra parte del script.</span><span class="sxs-lookup"><span data-stu-id="a234e-129">Verify that any variables used in a SQL script are declared before being used elsewhere in the script.</span></span>  
  
 <span data-ttu-id="a234e-130">Vuelva a escribir el script para que no haga referencia a las variables de la instrucción EXECUTE que se declaran fuera de ella.</span><span class="sxs-lookup"><span data-stu-id="a234e-130">Rewrite the script so that it does not reference variables in the EXECUTE statement that are declared outside of it.</span></span> <span data-ttu-id="a234e-131">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a234e-131">For example:</span></span>  
  
 <span data-ttu-id="a234e-132">USE AdventureWorks2012;</span><span class="sxs-lookup"><span data-stu-id="a234e-132">USE AdventureWorks2012;</span></span>  
  
 <span data-ttu-id="a234e-133">GO</span><span class="sxs-lookup"><span data-stu-id="a234e-133">GO</span></span>  
  
 <span data-ttu-id="a234e-134">DECLARE @mycol nvarchar(20)</span><span class="sxs-lookup"><span data-stu-id="a234e-134">DECLARE @mycol nvarchar(20) ;</span></span>  
  
 <span data-ttu-id="a234e-135">SET @mycol = 'Name'</span><span class="sxs-lookup"><span data-stu-id="a234e-135">SET @mycol = 'Name';</span></span>  
  
 <span data-ttu-id="a234e-136">EXECUTE ('SELECT ' + @mycol + ' FROM Production.Product';)</span><span class="sxs-lookup"><span data-stu-id="a234e-136">EXECUTE ('SELECT ' + @mycol + ' FROM Production.Product';) ;</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a234e-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a234e-137">See Also</span></span>  
 <span data-ttu-id="a234e-138">[EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a234e-138">[EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql) </span></span>  
 <span data-ttu-id="a234e-139">[Instrucciones SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a234e-139">[SET Statements &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statements-transact-sql) </span></span>  
 [<span data-ttu-id="a234e-140">DECLARE @local_variable &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a234e-140">DECLARE @local_variable &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/declare-local-variable-transact-sql)  
  
  
