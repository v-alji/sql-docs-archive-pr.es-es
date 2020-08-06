---
title: Integración de CLR y transacciones | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- ADO.NET [CLR integration]
- common language runtime [SQL Server], ADO.NET
- managed code [SQL Server], transactions
- common language runtime [SQL Server], transactions
- System.Transactions namespace
- transactions [CLR integration]
ms.assetid: 381d206e-06e2-48d0-8206-295fcf06ac98
author: rothja
ms.author: jroth
ms.openlocfilehash: de72a2113aeb568decbdc9b5ee0174160cc0d3ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751198"
---
# <a name="clr-integration-and-transactions"></a><span data-ttu-id="995a9-102">Integración CLR y transacciones</span><span class="sxs-lookup"><span data-stu-id="995a9-102">CLR Integration and Transactions</span></span>
  <span data-ttu-id="995a9-103">El espacio de nombres `System.Transactions` proporciona un nuevo marco de transacciones totalmente integrado con ADO.NET y la característica de integración con Common Language Runtime (CLR) en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="995a9-103">The `System.Transactions` namespace provides a transaction framework that is fully integrated with ADO.NET and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] common language runtime (CLR) integration.</span></span> <span data-ttu-id="995a9-104">`System.Transactions` y ADO.NET trabajan en conjunto para extender y simplificar el uso de transacciones locales y distribuidas en aplicaciones administradas.</span><span class="sxs-lookup"><span data-stu-id="995a9-104">`System.Transactions` and ADO.NET work together to extend and simplify the use of local and distributed transactions in managed applications.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="995a9-105">Un procedimiento definido por el usuario (UDP) CLR no puede establecer una conexión al mismo servidor donde se ejecuta (una conexión de bucle invertido) ni darse de alta en la misma transacción.</span><span class="sxs-lookup"><span data-stu-id="995a9-105">A CLR user-defined procedure (UDP) cannot establish a connection to the same server it is running on (a loopback connection) and enlist in the same transaction.</span></span> <span data-ttu-id="995a9-106">Si se intenta efectuar la conexión, ésta se bloqueará y no se devolverá el control al UDP.</span><span class="sxs-lookup"><span data-stu-id="995a9-106">If this is attempted, the connection attempt will be blocked and control will not be passed back to the UDP.</span></span> <span data-ttu-id="995a9-107">Esto producirá un error de tiempo de espera (mensaje 1206) en el UDP.</span><span class="sxs-lookup"><span data-stu-id="995a9-107">This will result in a timeout error (Msg 1206) on the UDP.</span></span>  
  
 <span data-ttu-id="995a9-108">Para obtener más información sobre las transacciones y .NET Framework, vea los temas sobre la realización de transacciones y el aprovechamiento de las transacciones en .NET Framework SDK.</span><span class="sxs-lookup"><span data-stu-id="995a9-108">For more information about transactions and the .NET Framework, see "Performing Transactions" and "Leveraging Transactions" in the .NET Framework SDK.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="995a9-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="995a9-109">In This Section</span></span>  
 [<span data-ttu-id="995a9-110">Promoción de transacciones</span><span class="sxs-lookup"><span data-stu-id="995a9-110">Transaction Promotion</span></span>](transaction-promotion.md)  
 <span data-ttu-id="995a9-111">Describe la capacidad de promover transacciones y cómo utilizar esta característica.</span><span class="sxs-lookup"><span data-stu-id="995a9-111">Describes the ability to promote transactions, and how to use this feature.</span></span>  
  
 [<span data-ttu-id="995a9-112">Obtener acceso a la transacción actual</span><span class="sxs-lookup"><span data-stu-id="995a9-112">Accessing the Current Transaction</span></span>](accessing-the-current-transaction.md)  
 <span data-ttu-id="995a9-113">Describe cómo tener acceso a una transacción que se ejecuta actualmente en proceso en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="995a9-113">Describes how to access a transaction currently running in-process on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="995a9-114">Utilizar System.Transactions</span><span class="sxs-lookup"><span data-stu-id="995a9-114">Using System.Transactions</span></span>](../native-client-ole-db-transactions/transactions.md)  
 <span data-ttu-id="995a9-115">Describe cómo utilizar la interfaz de programación de aplicaciones (API) `System.Transactions` en la aplicación administrada.</span><span class="sxs-lookup"><span data-stu-id="995a9-115">Describes how to use the `System.Transactions` application programming interface (API) in your managed application.</span></span>  
  
 [<span data-ttu-id="995a9-116">Período de duración de las transacciones</span><span class="sxs-lookup"><span data-stu-id="995a9-116">Transaction Lifetimes</span></span>](transaction-lifetimes.md)  
 <span data-ttu-id="995a9-117">Describe la diferencia en duración entre las transacciones iniciadas en procedimientos almacenados de [!INCLUDE[tsql](../../includes/tsql-md.md)] y las transacciones iniciadas en aplicaciones CLR.</span><span class="sxs-lookup"><span data-stu-id="995a9-117">Describes the difference in lifetime between transactions started in [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures and transactions started in CLR applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="995a9-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="995a9-118">See Also</span></span>  
 [<span data-ttu-id="995a9-119">Acceso a datos de objetos de base de datos de CLR</span><span class="sxs-lookup"><span data-stu-id="995a9-119">Data Access from CLR Database Objects</span></span>](../clr-integration/data-access/data-access-from-clr-database-objects.md)  
  
  
