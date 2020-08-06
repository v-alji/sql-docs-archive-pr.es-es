---
title: Nombres de orígenes de datos y sistemas operativos de 64 bits | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: c2f86810-2775-4ddd-8df7-e8373785a7fc
author: rothja
ms.author: jroth
ms.openlocfilehash: ae31584ca3c076919f688d1ef9bdef80706c6940
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670353"
---
# <a name="data-source-names-and-64-bit-operating-systems"></a><span data-ttu-id="a95b9-102">Nombres de origen de datos y sistemas operativos de 64 bits</span><span class="sxs-lookup"><span data-stu-id="a95b9-102">Data Source Names and 64-Bit Operating Systems</span></span>
  <span data-ttu-id="a95b9-103">Para generar y ejecutar una aplicación como una aplicación de 32 bits en un sistema operativo de 64 bits, debe crear el origen de datos ODBC con el Administrador de ODBC de %windir%\SysWOW64\odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="a95b9-103">To build and run an application as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a95b9-104">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a95b9-104">Remarks</span></span>  
 <span data-ttu-id="a95b9-105">Un sistema operativo Windows de 64 bits tiene dos archivos odbcad32.exe:</span><span class="sxs-lookup"><span data-stu-id="a95b9-105">A 64-bit Windows operating system has two odbcad32.exe files:</span></span>  
  
-   <span data-ttu-id="a95b9-106">%SystemRoot%\system32\odbcad32.exe se usa para crear y mantener nombres de origen de datos para las aplicaciones de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="a95b9-106">%SystemRoot%\system32\odbcad32.exe is used to create and maintain data source names for 64-bit applications.</span></span>  
  
-   <span data-ttu-id="a95b9-107">%SystemRoot%\SysWOW64\odbcad32.exe se usa crear y mantener nombres de origen de datos para las aplicaciones de 32 bits, incluso las aplicaciones de 32 bits que se ejecutan en sistemas operativos de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="a95b9-107">%SystemRoot%\SysWOW64\odbcad32.exe is used to create and maintain data source names for 32-bit applications, including 32-bit applications that run on 64-bit operating systems.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a95b9-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a95b9-108">See Also</span></span>  
 [<span data-ttu-id="a95b9-109">SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="a95b9-109">SQL Server Native Client &#40;ODBC&#41;</span></span>](sql-server-native-client-odbc.md)  
  
  
