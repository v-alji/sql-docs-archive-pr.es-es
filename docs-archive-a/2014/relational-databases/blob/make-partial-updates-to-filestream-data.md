---
title: Realización de actualizaciones parciales de los datos FILESTREAM | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT
- FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT
ms.assetid: d6f7661e-6c14-4d31-9541-4520ca0f82b2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 696c1a6421e14568877e24f015e5094395f1051b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749341"
---
# <a name="make-partial-updates-to-filestream-data"></a><span data-ttu-id="4e129-102">Realizar actualizaciones parciales de los datos FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="4e129-102">Make Partial Updates to FILESTREAM Data</span></span>
  <span data-ttu-id="4e129-103">Una aplicación utiliza FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT para realizar actualizaciones parciales de los datos de FILESTREAM BLOB.</span><span class="sxs-lookup"><span data-stu-id="4e129-103">An application uses FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT to make partial updates to FILESTREAM BLOB data.</span></span> <span data-ttu-id="4e129-104">La función [DeviceIoControl](https://go.microsoft.com/fwlink/?LinkId=105527) pasa este valor y el controlador que [OpenSqlFilestream](access-filestream-data-with-opensqlfilestream.md) devuelve al controlador FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="4e129-104">The [DeviceIoControl](https://go.microsoft.com/fwlink/?LinkId=105527) function passes this value and the handle that is returned from [OpenSqlFilestream](access-filestream-data-with-opensqlfilestream.md) to the FILESTREAM driver.</span></span> <span data-ttu-id="4e129-105">A continuación, el controlador obliga a hacer una copia del lado servidor de los datos FILESTREAM actuales en el archivo al que el controlador hace referencia.</span><span class="sxs-lookup"><span data-stu-id="4e129-105">The driver then forces a server-side copy of the current FILESTREAM data into the file that is referenced by the handle.</span></span> <span data-ttu-id="4e129-106">Si la aplicación emite el valor FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT una vez escrito el controlador, la última operación de escritura se conserva y se pierden las operaciones de escritura anteriores que se realizaron en el controlador.</span><span class="sxs-lookup"><span data-stu-id="4e129-106">If the application issues the FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT value after the handle has been written to, the last write operation persists and previous write operations that were made to the handle are lost.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4e129-107">FILESTREAM se basa en el protocolo [SMB protocol](https://go.microsoft.com/fwlink/?LinkId=112454) para el acceso remoto.</span><span class="sxs-lookup"><span data-stu-id="4e129-107">FILESTREAM relies on the [SMB protocol](https://go.microsoft.com/fwlink/?LinkId=112454) for remote access.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e129-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4e129-108">Example</span></span>  
 <span data-ttu-id="4e129-109">En el ejemplo siguiente se muestra cómo utilizar el valor `FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT` para realizar una actualización parcial de un FILESTREAM BLOB insertado.</span><span class="sxs-lookup"><span data-stu-id="4e129-109">The following example shows you how to use the `FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT` value to perform a partial update of an inserted FILESTREAM BLOB.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4e129-110">Este ejemplo requiere la tabla y la base de datos habilitadas para FILESTREAM que se crean en [Crear una base de datos habilitada para FILESTREAM](create-a-filestream-enabled-database.md) y [Crear una tabla para almacenar datos FILESTREAM](create-a-table-for-storing-filestream-data.md).</span><span class="sxs-lookup"><span data-stu-id="4e129-110">This example requires the FILESTREAM-enabled database and table that are created in [Create a FILESTREAM-Enabled Database](create-a-filestream-enabled-database.md) and [Create a Table for Storing FILESTREAM Data](create-a-table-for-storing-filestream-data.md).</span></span>  
  
 [!code-cpp[FILESTREAM#FS_CPP_FSCTL](../../snippets/tsql/SQL15/tsql/filestream/cpp/filestream.cpp#fs_cpp_fsctl)]  
  
## <a name="see-also"></a><span data-ttu-id="4e129-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4e129-111">See Also</span></span>  
 <span data-ttu-id="4e129-112">[Obtener acceso a los datos FILESTREAM con OpenSqlFilestream](access-filestream-data-with-opensqlfilestream.md) </span><span class="sxs-lookup"><span data-stu-id="4e129-112">[Access FILESTREAM Data with OpenSqlFilestream](access-filestream-data-with-opensqlfilestream.md) </span></span>  
 [<span data-ttu-id="4e129-113">Crear aplicaciones cliente para datos FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="4e129-113">Create Client Applications for FILESTREAM Data</span></span>](create-client-applications-for-filestream-data.md)  
  
  
