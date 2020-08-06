---
title: SQLGetCursorName | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLGetCursorName function
ms.assetid: 3a427a23-28ef-49aa-b9ec-6cab0914bdf3
author: rothja
ms.author: jroth
ms.openlocfilehash: 01ce6e42b4e8753d07309ec7ce298d4f743d4a6d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662014"
---
# <a name="sqlgetcursorname"></a><span data-ttu-id="bf9ad-102">SQLGetCursorName</span><span class="sxs-lookup"><span data-stu-id="bf9ad-102">SQLGetCursorName</span></span>
  <span data-ttu-id="bf9ad-103">Si la aplicación no especifica un nombre de cursor, el controlador ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client genera uno para la aplicación en la generación del cursor.</span><span class="sxs-lookup"><span data-stu-id="bf9ad-103">If the application does not specify a cursor name, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver generates one for the application upon cursor generation.</span></span> <span data-ttu-id="bf9ad-104">La aplicación puede utilizar **SQLGetCursorName** para recuperar el nombre del cursor definido por controlador para las instrucciones UPDATE y DELETE posicionadas.</span><span class="sxs-lookup"><span data-stu-id="bf9ad-104">The application can use **SQLGetCursorName** to retrieve the driver-defined cursor name for positioned UPDATE and DELETE statements.</span></span> <span data-ttu-id="bf9ad-105">La aplicación no necesita llamar a **SQLSetCursorName** para sacar provecho de las instrucciones de manipulación de datos posicionadas.</span><span class="sxs-lookup"><span data-stu-id="bf9ad-105">The application does not need to call **SQLSetCursorName** to take advantage of positioned data manipulation statements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf9ad-106">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bf9ad-106">See Also</span></span>  
 <span data-ttu-id="bf9ad-107">[SQLGetCursorName función)](https://go.microsoft.com/fwlink/?LinkId=59349) </span><span class="sxs-lookup"><span data-stu-id="bf9ad-107">[SQLGetCursorName Function](https://go.microsoft.com/fwlink/?LinkId=59349) </span></span>  
 [<span data-ttu-id="bf9ad-108">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="bf9ad-108">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
