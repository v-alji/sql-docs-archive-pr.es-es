---
title: Desconectar de un origen de datos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC data sources, connections
- data sources [SQL Server Native Client]
- disconnecting [ODBC]
- ODBC applications, disconnecting
- SQLDisconnect function
- ODBC applications, data sources
- connections [SQL Server Native Client]
- SQLFreeHandle function
- ODBC data sources, disconnecting
- SQL Server Native Client ODBC driver, data sources
- ODBC functions
- SQL Server Native Client ODBC driver, connections
ms.assetid: 65b0267d-b2ab-4a59-83f2-436d90cfbf79
author: rothja
ms.author: jroth
ms.openlocfilehash: 5db3b83ab65d854f3a4d2182d9a4a1314e097681
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672940"
---
# <a name="disconnecting-from-a-data-source"></a><span data-ttu-id="744eb-102">Desconectarse de un origen de datos</span><span class="sxs-lookup"><span data-stu-id="744eb-102">Disconnecting from a Data Source</span></span>
  <span data-ttu-id="744eb-103">Cuando una aplicación ha terminado de usar un origen de datos, llama a **SQLDisconnect**.</span><span class="sxs-lookup"><span data-stu-id="744eb-103">When an application has finished using a data source, it calls **SQLDisconnect**.</span></span> <span data-ttu-id="744eb-104">**SQLDisconnect** libera todas las instrucciones que se asignan en la conexión y desconecta el controlador del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="744eb-104">**SQLDisconnect** frees any statements that are allocated on the connection and disconnects the driver from the data source.</span></span> <span data-ttu-id="744eb-105">Después de desconectarse, la aplicación puede llamar a [SQLFreeHandle](../native-client-odbc-api/sqlfreehandle.md) para liberar el identificador de conexión.</span><span class="sxs-lookup"><span data-stu-id="744eb-105">After disconnecting, the application can call [SQLFreeHandle](../native-client-odbc-api/sqlfreehandle.md) to free the connection handle.</span></span> <span data-ttu-id="744eb-106">Antes de salir, una aplicación también llama a **SQLFreeHandle** para liberar el identificador del entorno.</span><span class="sxs-lookup"><span data-stu-id="744eb-106">Before exiting, an application also calls **SQLFreeHandle** to free the environment handle.</span></span>  
  
 <span data-ttu-id="744eb-107">Después de desconectarse, una aplicación puede reutilizar el identificador de conexión asignado, conectarse a un origen de datos diferente o volver a conectarse al mismo origen de datos.</span><span class="sxs-lookup"><span data-stu-id="744eb-107">After disconnecting, an application can reuse the allocated connection handle, either to connect to a different data source or reconnect to the same data source.</span></span> <span data-ttu-id="744eb-108">La decisión de seguir conectado en lugar de desconectarse y volver a conectarse después requiere que el sistema de escritura de la aplicación considere los costes relativos de cada opción.</span><span class="sxs-lookup"><span data-stu-id="744eb-108">The decision to remain connected instead of disconnecting and reconnecting later requires that the application writer consider the relative costs of each option.</span></span> <span data-ttu-id="744eb-109">Conectarse a un origen de datos y seguir conectado puede ser relativamente costoso, dependiendo del medio de conexión.</span><span class="sxs-lookup"><span data-stu-id="744eb-109">Connecting to a data source and remaining connected can be relatively costly, depending on the connection medium.</span></span> <span data-ttu-id="744eb-110">Para realizar un intercambio, la aplicación debe hacer también suposiciones sobre la probabilidad y el control de tiempo de operaciones adicionales en el mismo origen de datos.</span><span class="sxs-lookup"><span data-stu-id="744eb-110">In making a trade-off, the application must also make assumptions about the probability and timing of additional operations on the same data source.</span></span> <span data-ttu-id="744eb-111">Puede que una aplicación tenga que utilizar además más de una conexión.</span><span class="sxs-lookup"><span data-stu-id="744eb-111">An application may also have to use more than one connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="744eb-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="744eb-112">See Also</span></span>  
 [<span data-ttu-id="744eb-113">Comunicarse con SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="744eb-113">Communicating with SQL Server &#40;ODBC&#41;</span></span>](communicating-with-sql-server-odbc.md)  
  
  
