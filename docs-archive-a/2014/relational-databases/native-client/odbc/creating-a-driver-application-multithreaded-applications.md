---
title: Aplicaciones multiproceso | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- threads [SQL Server], multithreaded applications
- ODBC applications, multithreaded applications
- asynchronous operations [SQL Server Native Client]
- SQL Server Native Client ODBC driver, multithreaded applications
- multithreaded applications [SQL Server Native Client]
ms.assetid: d352c91a-6e08-4e50-9f3e-a37892d9c2cc
author: rothja
ms.author: jroth
ms.openlocfilehash: b680086f76e0c1a1e8c8cfc2f4ef82099957b3fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675296"
---
# <a name="multithreaded-applications"></a><span data-ttu-id="aa0b9-102">Aplicaciones multiproceso</span><span class="sxs-lookup"><span data-stu-id="aa0b9-102">Multithreaded Applications</span></span>
  <span data-ttu-id="aa0b9-103">El controlador ODBC de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client es un controlador multiproceso.</span><span class="sxs-lookup"><span data-stu-id="aa0b9-103">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver is a multithreaded driver.</span></span> <span data-ttu-id="aa0b9-104">Escribir una aplicación multiproceso es una alternativa al uso de llamadas asincrónicas para procesar varias llamadas ODBC.</span><span class="sxs-lookup"><span data-stu-id="aa0b9-104">Writing a multithreaded application is an alternative to using asynchronous calls to process multiple ODBC calls.</span></span> <span data-ttu-id="aa0b9-105">Un subproceso puede realizar una llamada ODBC sincrónica y otros subprocesos pueden procesar mientras el primero subproceso está bloqueado en espera a la respuesta a su llamada.</span><span class="sxs-lookup"><span data-stu-id="aa0b9-105">A thread can make a synchronous ODBC call, and other threads can process while the first thread is blocked waiting for the response to its call.</span></span> <span data-ttu-id="aa0b9-106">Este modelo es más eficaz que la realización de llamadas asincrónicas porque elimina la sobrecarga como el tráfico de red y la realización de llamadas de función ODBC que comprueban SQL_STILL_EXECUTING.</span><span class="sxs-lookup"><span data-stu-id="aa0b9-106">This model is more efficient than making asynchronous calls because it eliminates overhead such as network traffic and making repeated ODBC function calls testing for SQL_STILL_EXECUTING.</span></span>  
  
 <span data-ttu-id="aa0b9-107">El modo asincrónico todavía es un método efectivo de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="aa0b9-107">Asynchronous mode is still an effective method of processing.</span></span> <span data-ttu-id="aa0b9-108">Las mejoras de rendimiento de un modelo multiproceso no son suficientes para justificar el hecho de sobrescribir aplicaciones asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="aa0b9-108">The performance improvements of a multithreaded model are not enough to justify rewriting asynchronous applications.</span></span> <span data-ttu-id="aa0b9-109">Si los usuarios están convirtiendo aplicaciones de DB-Library que usan el modelo asincrónico de DB-Library, es más fácil convertirlas en el modelo asincrónico de ODBC.</span><span class="sxs-lookup"><span data-stu-id="aa0b9-109">If users are converting DB-Library applications that use the DB-Library asynchronous model, it is easier to convert them to the ODBC asynchronous model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa0b9-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aa0b9-110">See Also</span></span>  
 [<span data-ttu-id="aa0b9-111">Crear una aplicación de controlador ODBC de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="aa0b9-111">Creating a SQL Server Native Client ODBC Driver Application</span></span>](creating-a-driver-application.md)  
  
  
