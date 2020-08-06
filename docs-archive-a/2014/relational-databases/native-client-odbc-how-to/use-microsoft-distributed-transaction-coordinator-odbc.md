---
title: Usar Microsoft Coordinador de transacciones distribuidas (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- MS DTC, using
ms.assetid: 12a275e1-8c7e-436d-8a4e-b7bee853b35c
author: rothja
ms.author: jroth
ms.openlocfilehash: f7b7da33066a9f4edd01037738ed91155340e6ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671975"
---
# <a name="use-microsoft-distributed-transaction-coordinator-odbc"></a><span data-ttu-id="0a95a-102">Usar Microsoft DTC (Coordinador de transacciones distribuidas) (ODBC)</span><span class="sxs-lookup"><span data-stu-id="0a95a-102">Use Microsoft Distributed Transaction Coordinator (ODBC)</span></span>
    
### <a name="to-update-two-or-more-sql-servers-by-using-ms-dtc"></a><span data-ttu-id="0a95a-103">Para actualizar dos o más servidores SQL Server mediante MS DTC</span><span class="sxs-lookup"><span data-stu-id="0a95a-103">To update two or more SQL Servers by using MS DTC</span></span>  
  
1.  <span data-ttu-id="0a95a-104">Conéctese a MS DTC utilizando la función OLE DtcGetTransactionManager de MS DTC.</span><span class="sxs-lookup"><span data-stu-id="0a95a-104">Connect to MS DTC by using the MS DTC OLE DtcGetTransactionManager function.</span></span> <span data-ttu-id="0a95a-105">Para obtener información acerca de MS DTC, vea Microsoft DTC (Coordinador de transacciones distribuidas).</span><span class="sxs-lookup"><span data-stu-id="0a95a-105">For information about MS DTC, see Microsoft Distributed Transaction Coordinator.</span></span>  
  
2.  <span data-ttu-id="0a95a-106">Llame a SQL DriverConnect una vez para cada conexión Microsoft SQL Server que desee establecer.</span><span class="sxs-lookup"><span data-stu-id="0a95a-106">Call SQL DriverConnect once for each Microsoft SQL Server connection you want to establish.</span></span>  
  
3.  <span data-ttu-id="0a95a-107">Llame a la función OLE ITransactionDispenser::BeginTransaction de MS DTC para iniciar una transacción MS DTC y obtener un objeto Transaction que represente la transacción.</span><span class="sxs-lookup"><span data-stu-id="0a95a-107">Call the MS DTC OLE ITransactionDispenser::BeginTransaction function to begin an MS DTC transaction and obtain a Transaction object that represents the transaction.</span></span>  
  
4.  <span data-ttu-id="0a95a-108">Llame a [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) una vez o más para cada conexión ODBC que quiera dar de alta en la transacción de MS DTC.</span><span class="sxs-lookup"><span data-stu-id="0a95a-108">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) one or more times for each ODBC connection you want to enlist in the MS DTC transaction.</span></span> <span data-ttu-id="0a95a-109">Es preciso que el segundo parámetro de [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) sea SQL_ATTR_ENLIST_IN_DTC y que el tercer parámetro sea un objeto Transaction (obtenido en el paso 3).</span><span class="sxs-lookup"><span data-stu-id="0a95a-109">[SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) second parameter must be SQL_ATTR_ENLIST_IN_DTC and third parameter must be the Transaction object (obtained in Step 3).</span></span>  
  
5.  <span data-ttu-id="0a95a-110">Llame una vez a [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) para cada servidor SQL Server que quiera actualizar.</span><span class="sxs-lookup"><span data-stu-id="0a95a-110">Call [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) once for each SQL Server you want to update.</span></span>  
  
6.  <span data-ttu-id="0a95a-111">Llame a la función OLE ITransaction::Commit de MS DTC para confirmar la transacción MS DTC.</span><span class="sxs-lookup"><span data-stu-id="0a95a-111">Call the MS DTC OLE ITransaction::Commit function to commit the MS DTC transaction.</span></span> <span data-ttu-id="0a95a-112">El objeto Transaction ya no es válido.</span><span class="sxs-lookup"><span data-stu-id="0a95a-112">The Transaction object is no longer valid.</span></span>  
  
 <span data-ttu-id="0a95a-113">Para realizar una serie de transacciones MS DTC, repita los pasos del 3 al 6.</span><span class="sxs-lookup"><span data-stu-id="0a95a-113">To perform a series of MS DTC transactions, repeat Steps 3 through 6.</span></span>  
  
 <span data-ttu-id="0a95a-114">Para liberar la referencia al objeto Transaction, llame a la función OLE ITransaction::Return de MS DTC.</span><span class="sxs-lookup"><span data-stu-id="0a95a-114">To release the reference to the Transaction object, call the MS DTC OLE ITransaction::Return function.</span></span>  
  
 <span data-ttu-id="0a95a-115">Para usar una conexión ODBC con una transacción MS DTC y, después, usar la misma conexión con una transacción local de SQL Server, llame a [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) con SQL_DTC_DONE.</span><span class="sxs-lookup"><span data-stu-id="0a95a-115">To use an ODBC connection with an MS DTC transaction, and then use the same connection with a local SQL Server transaction, call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_DTC_DONE.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0a95a-116">También puede llamar a [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) y [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) sucesivamente para cada servidor SQL Server en lugar de llamarlos tal y como se sugería anteriormente en los pasos 4 y 5.</span><span class="sxs-lookup"><span data-stu-id="0a95a-116">You can also call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) and [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) in turn for each SQL Server instead of calling them as suggested earlier in Steps 4 and 5.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a95a-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0a95a-117">See Also</span></span>  
 [<span data-ttu-id="0a95a-118">Realizar transacciones &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="0a95a-118">Performing Transactions &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/performing-transactions-odbc.md)  
  
  
