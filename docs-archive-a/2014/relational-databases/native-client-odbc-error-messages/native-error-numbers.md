---
title: Números de error nativos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC error handling, native error numbers
- SQL Server Native Client ODBC driver, errors
- native error numbers [SQL Server Native Client]
- messages [ODBC], native error numbers
- errors [ODBC], native error numbers
ms.assetid: 77cbc826-f47f-4803-8e7a-223d6df069b1
author: rothja
ms.author: jroth
ms.openlocfilehash: 7232a921027246c3ceb7d0ae1ffd5efbd3672895
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745288"
---
# <a name="native-error-numbers"></a><span data-ttu-id="1b617-102">Números de errores nativos</span><span class="sxs-lookup"><span data-stu-id="1b617-102">Native Error Numbers</span></span>
  <span data-ttu-id="1b617-103">En el caso de los errores que se producen en el origen de datos (devuelto por [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ), el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] controlador ODBC de Native Client devuelve el número de error nativo que devuelve [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1b617-103">For errors that occur in the data source (returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]), the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver returns the native error number returned to it by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1b617-104">En el caso de los errores detectados por el controlador, el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] controlador ODBC de Native Client devuelve un número de error nativo de 0.</span><span class="sxs-lookup"><span data-stu-id="1b617-104">For errors detected by the driver, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver returns a native error number of 0.</span></span> <span data-ttu-id="1b617-105">Para obtener más información acerca de una lista de números de error nativos, vea la columna error de la tabla del sistema **sysmessages** en la base de datos **maestra** de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1b617-105">For more information about a list of native error numbers, see the error column of the **sysmessages** system table in the **master** database in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="1b617-106">Para obtener información acerca de los códigos de error de estado, consulte [SQLSTATE &#40;códigos de error ODBC&#41;](sqlstate-odbc-error-codes.md).</span><span class="sxs-lookup"><span data-stu-id="1b617-106">For information about the state error codes, see [SQLSTATE &#40;ODBC Error Codes&#41;](sqlstate-odbc-error-codes.md).</span></span> <span data-ttu-id="1b617-107">Para los errores devueltos por la Biblioteca de red, el número de error nativo es del software de red subyacente.</span><span class="sxs-lookup"><span data-stu-id="1b617-107">For errors returned by the Net-Library, the native error number is from the underlying network software.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b617-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1b617-108">See Also</span></span>  
 [<span data-ttu-id="1b617-109">Controlar errores y mensajes</span><span class="sxs-lookup"><span data-stu-id="1b617-109">Handling Errors and Messages</span></span>](handling-errors-and-messages.md)  
  
  
