---
title: Realización de transacciones distribuidas | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- MS DTC, performing distributed transactions
- SQL Server Native Client ODBC driver, transactions
- distributed transactions [ODBC]
- transactions [ODBC]
- ODBC, transactions
ms.assetid: 2c17fba0-7a3c-453c-91b7-f801e7b39ccb
author: rothja
ms.author: jroth
ms.openlocfilehash: 9ec23fd1883749e35e67f888e26bdf031ccf7fb8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670350"
---
# <a name="performing-distributed-transactions"></a><span data-ttu-id="57f18-102">Realizar transacciones distribuidas</span><span class="sxs-lookup"><span data-stu-id="57f18-102">Performing Distributed Transactions</span></span>
  <span data-ttu-id="57f18-103">Microsoft DTC (Coordinador de transacciones distribuidas) permite que las aplicaciones puedan extender las transacciones en dos o más instancias de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57f18-103">The Microsoft Distributed Transaction Coordinator (MS DTC) allows applications to extend transactions across two or more instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="57f18-104">También permite que las aplicaciones participen en transacciones administradas por administradores de transacciones que obedecen al estándar Open Group DTP XA.</span><span class="sxs-lookup"><span data-stu-id="57f18-104">It also allows applications to participate in transactions managed by transaction managers that comply with the Open Group DTP XA standard.</span></span>  
  
 <span data-ttu-id="57f18-105">Normalmente, todos los comandos de administración de transacción se envían a través del controlador ODBC de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client al servidor.</span><span class="sxs-lookup"><span data-stu-id="57f18-105">Normally, all transaction management commands are sent through the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver to the server.</span></span> <span data-ttu-id="57f18-106">La aplicación inicia una transacción mediante una llamada a [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) con el modo de confirmación automática desactivado.</span><span class="sxs-lookup"><span data-stu-id="57f18-106">The application starts a transaction by calling [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) with the autocommit mode turned off.</span></span> <span data-ttu-id="57f18-107">A continuación, la aplicación realiza las actualizaciones que componen la transacción y llama a [SQLEndTran](../../native-client-odbc-api/sqlendtran.md) con la opción SQL_COMMIT o SQL_ROLLBACK.</span><span class="sxs-lookup"><span data-stu-id="57f18-107">The application then performs the updates comprising the transaction and calls [SQLEndTran](../../native-client-odbc-api/sqlendtran.md) with either the SQL_COMMIT or SQL_ROLLBACK option.</span></span>  
  
 <span data-ttu-id="57f18-108">Sin embargo, cuando se utiliza MS DTC, MS DTC se convierte en el administrador de transacciones y la aplicación ya no usa **SQLEndTran**.</span><span class="sxs-lookup"><span data-stu-id="57f18-108">When using MS DTC, however, MS DTC becomes the transaction manager and the application no longer uses **SQLEndTran**.</span></span>  
  
 <span data-ttu-id="57f18-109">Cuando se da de alta en una transacción distribuida y después en una segunda transacción distribuida, el controlador ODBC de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client se da de baja de la transacción distribuida original y se da de alta en la transacción nueva.</span><span class="sxs-lookup"><span data-stu-id="57f18-109">When enlisted in a distributed transaction, and then enlist in a second distributed transaction, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC Driver defects from the original distributed transaction and enlists in the new transaction.</span></span> <span data-ttu-id="57f18-110">Para obtener más información, vea [Referencia del programador de DTC](https://msdn.microsoft.com/library/ms686108\(VS.85\).aspx).</span><span class="sxs-lookup"><span data-stu-id="57f18-110">For more information, see [DTC Programmer's Reference](https://msdn.microsoft.com/library/ms686108\(VS.85\).aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57f18-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="57f18-111">See Also</span></span>  
 [<span data-ttu-id="57f18-112">Realizar transacciones &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="57f18-112">Performing Transactions &#40;ODBC&#41;</span></span>](../../../database-engine/dev-guide/performing-transactions-odbc.md)  
  
  
