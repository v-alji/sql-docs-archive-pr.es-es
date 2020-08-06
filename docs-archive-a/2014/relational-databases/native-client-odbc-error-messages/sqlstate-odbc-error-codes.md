---
title: SQLSTATE (códigos de error ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, errors
- ODBC error handling, cause information
- messages [ODBC], cause information
- SQLSTATEs
- errors [ODBC], cause information
ms.assetid: 84cce528-edb0-473f-a85f-3eb87fbe2cf3
author: rothja
ms.author: jroth
ms.openlocfilehash: ff3ec0a5cdc8f24f34e42849f7c8f6d1d9d41478
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662006"
---
# <a name="sqlstate-odbc-error-codes"></a><span data-ttu-id="9a95b-102">SQLSTATE (códigos de error ODBC)</span><span class="sxs-lookup"><span data-stu-id="9a95b-102">SQLSTATE (ODBC Error Codes)</span></span>
  <span data-ttu-id="9a95b-103">SQLSTATE proporciona información detallada sobre la causa de una advertencia o error.</span><span class="sxs-lookup"><span data-stu-id="9a95b-103">SQLSTATE provides detailed information about the cause of a warning or error.</span></span> <span data-ttu-id="9a95b-104">En el caso de los errores que se producen en el origen de datos detectado y devuelto por [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] controlador ODBC de Native Client asigna el número de error nativo devuelto al SQLSTATE adecuado.</span><span class="sxs-lookup"><span data-stu-id="9a95b-104">For errors that occur in the data source detected and returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver maps the returned native error number to the appropriate SQLSTATE.</span></span> <span data-ttu-id="9a95b-105">Si un número de error nativo no tiene un código de error ODBC al que asignar, el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] controlador ODBC de Native Client devuelve SQLSTATE 42000 ("error de sintaxis o infracción de acceso").</span><span class="sxs-lookup"><span data-stu-id="9a95b-105">If a native error number does not have an ODBC error code to map to, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver returns SQLSTATE 42000 ("syntax error or access violation").</span></span> <span data-ttu-id="9a95b-106">En el caso de los errores detectados por el controlador, el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] controlador ODBC de Native Client genera el SQLSTATE adecuado.</span><span class="sxs-lookup"><span data-stu-id="9a95b-106">For errors that are detected by the driver, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver generates the appropriate SQLSTATE.</span></span>  
  
 <span data-ttu-id="9a95b-107">Para obtener más información sobre los códigos de error de estado, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="9a95b-107">For more information about the state error codes, see the following topics:</span></span>  
  
-   [<span data-ttu-id="9a95b-108">Apéndice A: Códigos de error de ADO</span><span class="sxs-lookup"><span data-stu-id="9a95b-108">Appendix A: ODBC Error Codes</span></span>](https://go.microsoft.com/fwlink/?LinkId=89356)  
  
-   [<span data-ttu-id="9a95b-109">Asignaciones SQLSTATE</span><span class="sxs-lookup"><span data-stu-id="9a95b-109">SQLSTATE Mappings</span></span>](https://go.microsoft.com/fwlink/?LinkId=89355)  
  
## <a name="see-also"></a><span data-ttu-id="9a95b-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9a95b-110">See Also</span></span>  
 [<span data-ttu-id="9a95b-111">Controlar errores y mensajes</span><span class="sxs-lookup"><span data-stu-id="9a95b-111">Handling Errors and Messages</span></span>](handling-errors-and-messages.md)  
  
  
