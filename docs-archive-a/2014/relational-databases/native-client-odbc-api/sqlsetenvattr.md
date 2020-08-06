---
title: SQLSetEnvAttr | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLSetEnvAttr function
ms.assetid: d4114571-feca-4330-b2e4-7bfd1050b812
author: rothja
ms.author: jroth
ms.openlocfilehash: f0dbd4d01de9ca769c46a93f810f0149f5b86981
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677037"
---
# <a name="sqlsetenvattr"></a><span data-ttu-id="a2a36-102">SQLSetEnvAttr</span><span class="sxs-lookup"><span data-stu-id="a2a36-102">SQLSetEnvAttr</span></span>
  <span data-ttu-id="a2a36-103">La [Referencia del programador de ODBC](https://go.microsoft.com/fwlink/?LinkId=45250) define cómo deben interpretar los controladores ODBC las especificaciones del atributo **SQLSetEnvAttr** desde aplicaciones escritas para la API de ODBC 2.*x* u ODBC 3.*x* .</span><span class="sxs-lookup"><span data-stu-id="a2a36-103">The [ODBC Programmer's Reference](https://go.microsoft.com/fwlink/?LinkId=45250) defines how ODBC drivers should interpret the **SQLSetEnvAttr** attribute specifications from applications written to either the ODBC 2.*x* or ODBC 3.*x* API.</span></span> <span data-ttu-id="a2a36-104">El controlador ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client cumple esas reglas.</span><span class="sxs-lookup"><span data-stu-id="a2a36-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver complies with those rules.</span></span>  
  
 <span data-ttu-id="a2a36-105">Uno de los atributos controlado por **SQLSetEnvAttr** es si se utilizará la agrupación de conexiones.</span><span class="sxs-lookup"><span data-stu-id="a2a36-105">One of the attributes controlled by **SQLSetEnvAttr** is whether connection pooling is to be used.</span></span> <span data-ttu-id="a2a36-106">Si se utiliza la agrupación de conexiones con el controlador ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, el parámetro *DriverCompletion* debe estar establecido en SQL_DRIVER_NOPROMPT al conectar con [SQLDriverConnect](sqldriverconnect.md) o **SQLConnect**.</span><span class="sxs-lookup"><span data-stu-id="a2a36-106">If connection pooling is used with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver, the *DriverCompletion* parameter must be set to SQL_DRIVER_NOPROMPT when connecting with either [SQLDriverConnect](sqldriverconnect.md) or **SQLConnect**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2a36-107">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a2a36-107">See Also</span></span>  
 <span data-ttu-id="a2a36-108">[SQLSetEnvAttr función)](https://go.microsoft.com/fwlink/?LinkId=59369) </span><span class="sxs-lookup"><span data-stu-id="a2a36-108">[SQLSetEnvAttr Function](https://go.microsoft.com/fwlink/?LinkId=59369) </span></span>  
 [<span data-ttu-id="a2a36-109">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="a2a36-109">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
