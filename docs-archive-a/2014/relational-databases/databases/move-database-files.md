---
title: Movimiento de archivos de base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- disaster recovery [SQL Server], moving database files
- files [SQL Server], moving
- data files [SQL Server], moving
- file moving [SQL Server]
- moving full-text catalogs
- moving databases
- full-text catalogs [SQL Server], moving
- moving database files
- scheduled disk maintenance [SQL Server]
- moving files
- relocating database files
- planned database relocations [SQL Server]
- databases [SQL Server], moving
ms.assetid: 89f01b10-5fae-4ed8-b0fb-a4b9f540fd28
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5491f3c4dfd47cac4047d0409c78001be80d6f13
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748119"
---
# <a name="move-database-files"></a><span data-ttu-id="ebc6b-102">Mover archivos de base de datos</span><span class="sxs-lookup"><span data-stu-id="ebc6b-102">Move Database Files</span></span>
  <span data-ttu-id="ebc6b-103">En [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], puede mover bases de datos del sistema y del usuario especificando la nueva ubicación de los archivos en la cláusula FILENAME de la instrucción [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="ebc6b-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you can move system and user databases by specifying the new file location in the FILENAME clause of the [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement.</span></span> <span data-ttu-id="ebc6b-104">De este modo se pueden desplazar archivos de datos, registro y catálogo de texto completo.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-104">Data, log, and full-text catalog files can be moved in this way.</span></span> <span data-ttu-id="ebc6b-105">Esto puede resultar útil en las situaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="ebc6b-105">This may be useful in the following situations:</span></span>  
  
-   <span data-ttu-id="ebc6b-106">Recuperación de un error.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-106">Failure recovery.</span></span> <span data-ttu-id="ebc6b-107">Por ejemplo, la base de datos se encuentra en modo sospechoso o se ha cerrado a causa de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-107">For example, the database is in suspect mode or has shut down, because of a hardware failure.</span></span>  
  
-   <span data-ttu-id="ebc6b-108">Reubicación planeada.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-108">Planned relocation.</span></span>  
  
-   <span data-ttu-id="ebc6b-109">Reubicación para el mantenimiento planeado del disco.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-109">Relocation for scheduled disk maintenance.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ebc6b-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ebc6b-110">In This Section</span></span>  
  
|<span data-ttu-id="ebc6b-111">Tema</span><span class="sxs-lookup"><span data-stu-id="ebc6b-111">Topic</span></span>|<span data-ttu-id="ebc6b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="ebc6b-112">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="ebc6b-113">Mover bases de datos de usuario</span><span class="sxs-lookup"><span data-stu-id="ebc6b-113">Move User Databases</span></span>](move-user-databases.md)|<span data-ttu-id="ebc6b-114">Describe los procedimientos para mover archivos de base de datos de usuario y archivos del catálogo de texto completo a una nueva ubicación.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-114">Describes the procedures for moving user database files and full-text catalog files to a new location.</span></span>|  
|[<span data-ttu-id="ebc6b-115">Mover bases de datos del sistema</span><span class="sxs-lookup"><span data-stu-id="ebc6b-115">Move System Databases</span></span>](system-databases.md)|<span data-ttu-id="ebc6b-116">Describe el procedimiento para mover archivos de base de datos del sistema a una nueva ubicación.</span><span class="sxs-lookup"><span data-stu-id="ebc6b-116">Describes the procedures for moving system database files to a new location.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ebc6b-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ebc6b-117">See Also</span></span>  
 <span data-ttu-id="ebc6b-118">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ebc6b-118">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="ebc6b-119">[CREATE DATABASE &#40;Transact-SQL de SQL Server&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ebc6b-119">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 [<span data-ttu-id="ebc6b-120">Adjuntar y separar bases de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ebc6b-120">Database Detach and Attach &#40;SQL Server&#41;</span></span>](database-detach-and-attach-sql-server.md)  
  
  
