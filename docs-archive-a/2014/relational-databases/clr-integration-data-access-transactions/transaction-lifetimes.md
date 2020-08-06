---
title: Duración de las transacciones | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- lifetimes [SQL Server]
- Transact-SQL vs. managed code
ms.assetid: cb076fda-6488-4959-a6a4-7adaccf3f25c
author: rothja
ms.author: jroth
ms.openlocfilehash: 8c00050ee323cade7493d44c4c296ba4ce6811e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751193"
---
# <a name="transaction-lifetimes"></a><span data-ttu-id="c3b72-102">Período de duración de las transacciones</span><span class="sxs-lookup"><span data-stu-id="c3b72-102">Transaction Lifetimes</span></span>
  <span data-ttu-id="c3b72-103">Hay una diferencia importante entre las transacciones iniciadas en procedimientos almacenados [!INCLUDE[tsql](../../includes/tsql-md.md)] y las iniciadas en código administrado: el código de Common Language Runtime (CLR) no puede desequilibrar el estado de la transacción al entrar o salir de una invocación CLR.</span><span class="sxs-lookup"><span data-stu-id="c3b72-103">There is an important difference between transactions started in [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures and those started in managed code: common language runtime (CLR) code cannot unbalance the transaction state on entry or exit of a CLR invocation.</span></span> <span data-ttu-id="c3b72-104">Tenga en cuenta las implicaciones siguientes de esta diferencia:</span><span class="sxs-lookup"><span data-stu-id="c3b72-104">Be aware of the following implications of this difference:</span></span>  
  
-   <span data-ttu-id="c3b72-105">Una transacción iniciada dentro de un marco CLR se debe confirmar o revertir; de otro modo, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] genera un error cuando se sale del marco.</span><span class="sxs-lookup"><span data-stu-id="c3b72-105">A transaction started inside a CLR frame must be committed or rolled back, or else [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] generates an error when the frame is exited.</span></span>  
  
-   <span data-ttu-id="c3b72-106">Una transacción exterior no se puede confirmar o revertir dentro del código CLR.</span><span class="sxs-lookup"><span data-stu-id="c3b72-106">An outer transaction cannot be committed or rolled back inside the CLR code.</span></span>  
  
-   <span data-ttu-id="c3b72-107">Un intento para confirmar una transacción no iniciada en el mismo procedimiento produce un error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c3b72-107">An attempt to commit a transaction not started in the same procedure causes a run-time error.</span></span>  
  
-   <span data-ttu-id="c3b72-108">Un intento de revertir una transacción no iniciada en el mismo procedimiento hace que la transacción deje de responder (lo que impide que se produzca cualquier otra operación con efectos secundarios).</span><span class="sxs-lookup"><span data-stu-id="c3b72-108">An attempt to roll back a transaction not started in the same procedure causes the transaction to stop responding (preventing any other side-effecting operation from happening).</span></span> <span data-ttu-id="c3b72-109">La transacción se interrumpe hasta que el código CLR se sale del ámbito.</span><span class="sxs-lookup"><span data-stu-id="c3b72-109">The transaction discontinues until the CLR code goes out of scope.</span></span> <span data-ttu-id="c3b72-110">Tenga en cuenta que esto puede resultar útil cuando detecta un error dentro de su procedimiento y desea asegurarse de que toda la transacción finaliza.</span><span class="sxs-lookup"><span data-stu-id="c3b72-110">Note that this can be useful when you detect an error inside your procedure and want to make sure the whole transaction terminates.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3b72-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c3b72-111">See Also</span></span>  
 [<span data-ttu-id="c3b72-112">Integración CLR y transacciones</span><span class="sxs-lookup"><span data-stu-id="c3b72-112">CLR Integration and Transactions</span></span>](../native-client-ole-db-transactions/transactions.md)  
  
  
