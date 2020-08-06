---
title: Comprobar consultas (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdtsql.chm:100644
helpviewer_keywords:
- verifying queries
- queries [SQL Server], verifying
- checking queries
ms.assetid: 1382c0c0-46dc-45f9-ab38-9bba1d347eea
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7bf24de9bdc0e8b7b7ceb33bb881812b180ce112
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673957"
---
# <a name="verify-queries-visual-database-tools"></a><span data-ttu-id="73fed-102">Comprobar consultas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="73fed-102">Verify Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="73fed-103">Para evitar problemas, puede comprobar la consulta generada con el fin de asegurarse de que su sintaxis es correcta.</span><span class="sxs-lookup"><span data-stu-id="73fed-103">To avoid problems, you can check the query you have built to ensure its syntax is correct.</span></span> <span data-ttu-id="73fed-104">Esta opción será especialmente útil cuando escriba instrucciones en el [panel SQL](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="73fed-104">This option is especially useful when you enter statements in the [SQL pane](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="73fed-105">Conviene tener en cuenta estos aspectos a la hora de comprobar las consultas:</span><span class="sxs-lookup"><span data-stu-id="73fed-105">Some notes to keep in mind about verifying queries:</span></span>  
  
-   <span data-ttu-id="73fed-106">Una instrucción puede ser válida y, por tanto, comprobarse correctamente, aunque no se pueda representar en el **panel Diagrama** ni en el **panel Criterios**.</span><span class="sxs-lookup"><span data-stu-id="73fed-106">A statement can be valid, and therefore be verified successfully, even if it cannot be represented in the **Diagram Pane** and **Criteria Pane**.</span></span>  
  
-   <span data-ttu-id="73fed-107">La comprobación del código SQL puede detectar algunos errores de sintaxis SQL, pero no todos.</span><span class="sxs-lookup"><span data-stu-id="73fed-107">SQL Verification can detect some, but not all SQL errors.</span></span> <span data-ttu-id="73fed-108">Si una consulta contiene un error no detectado durante la comprobación SQL, la base de datos detectará el error cuando ejecute la consulta.</span><span class="sxs-lookup"><span data-stu-id="73fed-108">If a query contains an error not detected during SQL verification, the database will detect the error when you run the query.</span></span>  
  
-   <span data-ttu-id="73fed-109">Las consultas que contienen parámetros no pueden comprobarse.</span><span class="sxs-lookup"><span data-stu-id="73fed-109">Queries that contain parameters cannot be verified.</span></span>  
  
### <a name="to-verify-an-sql-statement"></a><span data-ttu-id="73fed-110">Para comprobar una instrucción SQL</span><span class="sxs-lookup"><span data-stu-id="73fed-110">To verify an SQL statement</span></span>  
  
-   <span data-ttu-id="73fed-111">Haga clic con el botón derecho en el **panel SQL**y seleccione **Comprobar sintaxis SQL** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="73fed-111">Right-click in the **SQL Pane**, and select **Verify SQL Syntax** from the shortcut menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73fed-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="73fed-112">See Also</span></span>  
 <span data-ttu-id="73fed-113">[Ejecutar consultas &#40;Visual Database Tools&#41;](run-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="73fed-113">[Run Queries &#40;Visual Database Tools&#41;](run-queries-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="73fed-114">Realizar operaciones básicas con consultas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="73fed-114">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
