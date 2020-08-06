---
title: Asignación de un identificador de entorno | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, environment handles
- ODBC applications, connections
- handles [SQL Server Native Client]
- environment handles [SQLNCLI]
ms.assetid: 15c1b428-ea6d-4672-894c-f0e289e2da3f
author: rothja
ms.author: jroth
ms.openlocfilehash: 1c655b5e9a406c3e1881c9dd199a92666377918f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674097"
---
# <a name="allocating-an-environment-handle"></a><span data-ttu-id="a06bd-102">Asignar un identificador de entorno</span><span class="sxs-lookup"><span data-stu-id="a06bd-102">Allocating an Environment Handle</span></span>
  <span data-ttu-id="a06bd-103">Para que una aplicación pueda llamar a cualquier función ODBC, debe inicializar el entorno ODBC y asignar un identificador de entorno.</span><span class="sxs-lookup"><span data-stu-id="a06bd-103">Before an application can call any ODBC function, it must initialize the ODBC environment and allocate an environment handle.</span></span> <span data-ttu-id="a06bd-104">Se trata del identificador de contexto global y marcador de posición del resto de los identificadores de ODBC.</span><span class="sxs-lookup"><span data-stu-id="a06bd-104">This is the global context handle and placeholder for the other handles in ODBC.</span></span> <span data-ttu-id="a06bd-105">Para ello, debe llamar a **SQLAllocHandle** con el parámetro *HandleType* establecido en SQL_HANDLE_ENV y *InputHandle* establecido en SQL_NULL_HANDLE.</span><span class="sxs-lookup"><span data-stu-id="a06bd-105">You do this by calling **SQLAllocHandle** with the *HandleType* parameter set to SQL_HANDLE_ENV and *InputHandle* set to SQL_NULL_HANDLE.</span></span>  
  
 <span data-ttu-id="a06bd-106">Después de asignar el identificador de entorno, la aplicación debe establecer atributos de entorno para indicar qué versión de las llamadas a funciones de ODBC va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="a06bd-106">After allocating the environment handle, the application must set environment attributes to indicate which version of ODBC function calls it will be using.</span></span> <span data-ttu-id="a06bd-107">Para usar ODBC 3. funciones *x* , llame a [SQLSetEnvAttr](../native-client-odbc-api/sqlsetenvattr.md) con el parámetro de *atributo* establecido en SQL_ATTR_ODBC_VERSION y *ValuePtr* establecido en SQL_OV_ODBC3.</span><span class="sxs-lookup"><span data-stu-id="a06bd-107">To use the ODBC 3.*x* functions, call [SQLSetEnvAttr](../native-client-odbc-api/sqlsetenvattr.md) with the *Attribute* parameter set to SQL_ATTR_ODBC_VERSION and *ValuePtr* set to SQL_OV_ODBC3.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a06bd-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a06bd-108">See Also</span></span>  
 [<span data-ttu-id="a06bd-109">Comunicarse con SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="a06bd-109">Communicating with SQL Server &#40;ODBC&#41;</span></span>](communicating-with-sql-server-odbc.md)  
  
  
