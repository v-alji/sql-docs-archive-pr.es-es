---
title: Usar la captura automática con cursores ODBC | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC cursors, autofetch
- autofetch option
- cursors [ODBC], autofetch
ms.assetid: 57bd55f4-8945-4d8d-9f58-d30c81d2a514
author: rothja
ms.author: jroth
ms.openlocfilehash: e3d9374cf9ceab4a7e73cc0059783486f2bf9c41
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675336"
---
# <a name="using-autofetch-with-odbc-cursors"></a><span data-ttu-id="0af28-102">Usar la captura automática con cursores ODBC</span><span class="sxs-lookup"><span data-stu-id="0af28-102">Using Autofetch with ODBC Cursors</span></span>
  <span data-ttu-id="0af28-103">Cuando se conecta a una instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , el [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] controlador ODBC de Native Client admite una opción de captura automática cuando se usa cualquier tipo de cursor de servidor.</span><span class="sxs-lookup"><span data-stu-id="0af28-103">When connected to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver supports an autofetch option when using any server cursor type.</span></span> <span data-ttu-id="0af28-104">Con la captura automática, la función **SQLExecute** o **SQLExecDirect** que abre el cursor también tiene una función [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md)(SQL_FIRST) implícita.</span><span class="sxs-lookup"><span data-stu-id="0af28-104">With autofetch, the **SQLExecute** or **SQLExecDirect** function that opens the cursor also has an implicit [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md)(SQL_FIRST) function.</span></span> <span data-ttu-id="0af28-105">Las filas que componen el primer conjunto de filas se devuelven a las variables de aplicación enlazadas como parte de la ejecución de la instrucción y se ahorra un viaje de ida y vuelta (round trip) de la red al servidor.</span><span class="sxs-lookup"><span data-stu-id="0af28-105">The rows comprising the first rowset are returned to the bound application variables as part of the statement execution, saving another roundtrip across the network to the server.</span></span> <span data-ttu-id="0af28-106">No se admite [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) cuando está habilitada la opción de captura automática; las columnas del conjunto de resultados se deben enlazar a las variables de programa.</span><span class="sxs-lookup"><span data-stu-id="0af28-106">[SQLGetData](../../native-client-odbc-api/sqlgetdata.md) is not supported when the autofetch option is enabled; the result set columns must be bound to program variables.</span></span>  
  
 <span data-ttu-id="0af28-107">Las aplicaciones solicitan la captura automática estableciendo el atributo de la instrucción SQL_SOPT_SS_CURSOR_OPTIONS específica del controlador en SQL_CO_AF.</span><span class="sxs-lookup"><span data-stu-id="0af28-107">Applications request autofetch by setting the driver-specific SQL_SOPT_SS_CURSOR_OPTIONS statement attribute to SQL_CO_AF.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0af28-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0af28-108">See Also</span></span>  
 [<span data-ttu-id="0af28-109">Detalles de la programación de cursores &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="0af28-109">Cursor Programming Details &#40;ODBC&#41;</span></span>](cursor-programming-details-odbc.md)  
  
  
