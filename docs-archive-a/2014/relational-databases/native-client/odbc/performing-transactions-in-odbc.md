---
title: Transacciones en ODBC | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, transactions
- transactions [ODBC]
- ODBC, transactions
ms.assetid: c5a87fa5-827a-4e6f-a0d9-924bac881eb0
author: rothja
ms.author: jroth
ms.openlocfilehash: 386b248edfdb6e0ac5eb97b3aeb6c0bbc505a5a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670347"
---
# <a name="transactions-in-odbc"></a><span data-ttu-id="6ce9d-102">Transacciones en ODBC</span><span class="sxs-lookup"><span data-stu-id="6ce9d-102">Transactions in ODBC</span></span>
  <span data-ttu-id="6ce9d-103">Las transacciones en ODBC se administran en las conexiones.</span><span class="sxs-lookup"><span data-stu-id="6ce9d-103">Transactions in ODBC are managed at the connection level.</span></span> <span data-ttu-id="6ce9d-104">Cuando una aplicación completa una transacción, confirma o revierte todo el trabajo completado a través de todos los identificadores de instrucciones de dicha conexión.</span><span class="sxs-lookup"><span data-stu-id="6ce9d-104">When an application completes a transaction, it commits or rolls back all work completed through all statement handles on that connection.</span></span> <span data-ttu-id="6ce9d-105">Para confirmar o revertir una transacción, las aplicaciones deberían llamar a [SQLEndTran](../../native-client-odbc-api/sqlendtran.md) en lugar de enviar una instrucción COMMIT o ROLLBACK.</span><span class="sxs-lookup"><span data-stu-id="6ce9d-105">To commit or roll back a transaction, applications should call [SQLEndTran](../../native-client-odbc-api/sqlendtran.md) instead of submitting a COMMIT or ROLLBACK statement.</span></span>  
  
 <span data-ttu-id="6ce9d-106">Una aplicación llama a [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) para intercambiar entre los dos modos ODBC de administrar transacciones:</span><span class="sxs-lookup"><span data-stu-id="6ce9d-106">An application calls [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) to switch between the two ODBC modes of managing transactions:</span></span>  
  
-   <span data-ttu-id="6ce9d-107">Modo de confirmación automática</span><span class="sxs-lookup"><span data-stu-id="6ce9d-107">Autocommit mode</span></span>  
  
     <span data-ttu-id="6ce9d-108">Todas las instrucciones se confirman automáticamente cuando se completan correctamente.</span><span class="sxs-lookup"><span data-stu-id="6ce9d-108">Each statement is automatically committed when it is completed successfully.</span></span> <span data-ttu-id="6ce9d-109">Cuando se ejecuta en modo de confirmación automática, no se requiere ninguna otra función de administración de transacciones.</span><span class="sxs-lookup"><span data-stu-id="6ce9d-109">When you run in autocommit mode, no other transaction management functions are required.</span></span>  
  
-   <span data-ttu-id="6ce9d-110">Modo de confirmación manual</span><span class="sxs-lookup"><span data-stu-id="6ce9d-110">Manual-commit mode</span></span>  
  
     <span data-ttu-id="6ce9d-111">Todos las instrucciones ejecutadas se incluyen en la misma transacción hasta que se detenga específicamente llamando a **SQLEndTran**.</span><span class="sxs-lookup"><span data-stu-id="6ce9d-111">All executed statements are included in the same transaction until it is specifically stopped by calling **SQLEndTran**.</span></span>  
  
 <span data-ttu-id="6ce9d-112">El modo de confirmación automática es el modo de transacción para ODBC.</span><span class="sxs-lookup"><span data-stu-id="6ce9d-112">Autocommit mode is the default transaction mode for ODBC.</span></span> <span data-ttu-id="6ce9d-113">Cuando se realiza una conexión, se encuentra en modo de confirmación automática hasta que se llame a **SQLSetConnectAttr** para pasar al modo de confirmación manual desactivando el modo de confirmación automática.</span><span class="sxs-lookup"><span data-stu-id="6ce9d-113">When a connection is made, it is in autocommit mode until **SQLSetConnectAttr** is called to switch to manual-commit mode by setting autocommit mode off.</span></span> <span data-ttu-id="6ce9d-114">Cuando una aplicación desactiva la confirmación automática, la siguiente instrucción enviada a la base de datos inicia una transacción.</span><span class="sxs-lookup"><span data-stu-id="6ce9d-114">When an application turns autocommit off, the next statement sent to the database starts a transaction.</span></span> <span data-ttu-id="6ce9d-115">A continuación, la transacción permanece activa hasta que la aplicación llama a **SQLEndTran** con las opciones SQL_COMMIT o SQL_ROLLBACK.</span><span class="sxs-lookup"><span data-stu-id="6ce9d-115">The transaction then remains in effect until the application calls **SQLEndTran** with either the SQL_COMMIT or SQL_ROLLBACK options.</span></span> <span data-ttu-id="6ce9d-116">El comando enviado a la base de datos después de que **SQLEndTran** inicia la siguiente transacción.</span><span class="sxs-lookup"><span data-stu-id="6ce9d-116">The command sent to the database after **SQLEndTran** starts the next transaction.</span></span>  
  
 <span data-ttu-id="6ce9d-117">Si una aplicación pasa del modo de confirmación manual al modo de confirmación automática, el controlador confirma cualquier transacción actualmente abierta en la conexión.</span><span class="sxs-lookup"><span data-stu-id="6ce9d-117">If an application switches from manual-commit to autocommit mode, the driver commits any transactions currently open on the connection.</span></span>  
  
 <span data-ttu-id="6ce9d-118">Las aplicaciones ODBC no deberían usar instrucciones de transacción de Transact-SQL como BEGIN TRANSACTION, COMMIT TRANSACTION o ROLLBACK TRANSACTION porque esto puede producir un comportamiento indeterminado en el controlador.</span><span class="sxs-lookup"><span data-stu-id="6ce9d-118">ODBC applications should not use Transact-SQL transaction statements such as BEGIN TRANSACTION, COMMIT TRANSACTION, or ROLLBACK TRANSACTION because this can cause indeterminate behavior in the driver.</span></span> <span data-ttu-id="6ce9d-119">Una aplicación ODBC se debería ejecutar en modo de confirmación automática y no usar instrucciones o funciones de administración de transacciones o bien, ejecutarse en el modo de confirmación manual y usar la función **SQLEndTran** ODBC para confirmar o revertir transacciones.</span><span class="sxs-lookup"><span data-stu-id="6ce9d-119">An ODBC application should run in autocommit mode and not use any transaction management functions or statements, or run in manual-commit mode and use the ODBC **SQLEndTran** function to either commit or roll back transactions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ce9d-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6ce9d-120">See Also</span></span>  
 [<span data-ttu-id="6ce9d-121">Realizar transacciones &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="6ce9d-121">Performing Transactions &#40;ODBC&#41;</span></span>](../../../database-engine/dev-guide/performing-transactions-odbc.md)  
  
  
