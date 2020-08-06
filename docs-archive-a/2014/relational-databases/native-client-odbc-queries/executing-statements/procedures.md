---
title: Procedimientos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- stored procedures [ODBC]
- stored procedures [ODBC], about ODBC stored procedures
- ODBC applications, statements
- statements [ODBC], stored procedures
- ODBC applications, stored procedures
ms.assetid: c64d5f3a-376b-48ef-84f3-b6148ac8600a
author: rothja
ms.author: jroth
ms.openlocfilehash: a7ae4678d324ba7d07ae429793b1f75b57bb15e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662869"
---
# <a name="procedures"></a><span data-ttu-id="1f0b4-102">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="1f0b4-102">Procedures</span></span>
  <span data-ttu-id="1f0b4-103">Un procedimiento almacenado es un objeto ejecutable precompilado que contiene una o más instrucciones [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f0b4-103">A stored procedure is a precompiled executable object that contains one or more [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="1f0b4-104">Los procedimientos almacenados pueden tener parámetros de entrada y salida, y también puede generar un código de retorno de tipo entero.</span><span class="sxs-lookup"><span data-stu-id="1f0b4-104">Stored procedures can have input and output parameters and can also put out an integer return code.</span></span> <span data-ttu-id="1f0b4-105">Una aplicación puede enumerar los procedimientos almacenados disponibles mediante funciones de catálogo.</span><span class="sxs-lookup"><span data-stu-id="1f0b4-105">An application can enumerate available stored procedures by using catalog functions.</span></span>  
  
 <span data-ttu-id="1f0b4-106">Las aplicaciones ODBC destinadas a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] solo deberían usar la ejecución directa para llamar a un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="1f0b4-106">ODBC applications that target [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] should only use direct execution to call a stored procedure.</span></span> <span data-ttu-id="1f0b4-107">Cuando se conecta a versiones anteriores de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , el [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] controlador ODBC de Native Client implementa la [función SQLPrepare](https://go.microsoft.com/fwlink/?LinkId=59360) creando un procedimiento almacenado temporal, al que se llama a continuación en **SQLExecute**.</span><span class="sxs-lookup"><span data-stu-id="1f0b4-107">When connected to earlier versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver implements [SQLPrepare Function](https://go.microsoft.com/fwlink/?LinkId=59360) by creating a temporary stored procedure, which is then called on **SQLExecute**.</span></span> <span data-ttu-id="1f0b4-108">Agrega sobrecarga para que **SQLPrepare** cree un procedimiento almacenado temporal que solo llama al procedimiento almacenado de destino, en lugar de ejecutar directamente el procedimiento almacenado de destino.</span><span class="sxs-lookup"><span data-stu-id="1f0b4-108">It adds overhead to have **SQLPrepare** create a temporary stored procedure that only calls the target stored procedure versus directly executing the target stored procedure.</span></span> <span data-ttu-id="1f0b4-109">Incluso al conectarse a una instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], la preparación de una llamada requiere un viaje de ida y vuelta (round trip) adicional por la red y la generación de un plan de ejecución que llama simplemente al plan de ejecución de procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="1f0b4-109">Even when connected to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], preparing a call requires an extra round trip across the network and the building of an execution plan that just calls the stored procedure execution plan.</span></span>  
  
 <span data-ttu-id="1f0b4-110">Las aplicaciones ODBC deberían usar la sintaxis de ODBC CALL al ejecutar un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="1f0b4-110">ODBC applications should use the ODBC CALL syntax when executing a stored procedure.</span></span> <span data-ttu-id="1f0b4-111">El controlador se optimiza para usar un mecanismo de llamada a procedimiento remoto para llamar al procedimiento cuando se usa la sintaxis de ODBC CALL.</span><span class="sxs-lookup"><span data-stu-id="1f0b4-111">The driver is optimized to use a remote procedure call mechanism to call the procedure when the ODBC CALL syntax is used.</span></span> <span data-ttu-id="1f0b4-112">Esto resulta más eficaz que el mecanismo usado para enviar una instrucción [!INCLUDE[tsql](../../../includes/tsql-md.md)] EXECUTE al servidor.</span><span class="sxs-lookup"><span data-stu-id="1f0b4-112">This is more efficient than the mechanism used to send a [!INCLUDE[tsql](../../../includes/tsql-md.md)] EXECUTE statement to the server.</span></span>  
  
 <span data-ttu-id="1f0b4-113">Para obtener más información, vea [Ejecutar procedimientos almacenados](../../native-client-odbc-stored-procedures/running-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="1f0b4-113">For more information, see [Running Stored Procedures](../../native-client-odbc-stored-procedures/running-stored-procedures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f0b4-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1f0b4-114">See Also</span></span>  
 [<span data-ttu-id="1f0b4-115">Ejecutar instrucciones &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="1f0b4-115">Executing Statements &#40;ODBC&#41;</span></span>](executing-statements-odbc.md)  
  
  
