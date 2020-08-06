---
title: Base de datos Resource | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- system objects [SQL Server]
- read-only databases
- mssqlsystemresource.mdf file
- Resource database [SQL Server]
ms.assetid: d592b2b4-bc36-4eb9-9385-8fe4dff0dced
author: stevestein
ms.author: sstein
ms.openlocfilehash: cca2f9e1ff6069a608beb1df1880b37e15f4e869
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672089"
---
# <a name="resource-database"></a><span data-ttu-id="07b8f-102">Base de datos Resource</span><span class="sxs-lookup"><span data-stu-id="07b8f-102">Resource Database</span></span>
  <span data-ttu-id="07b8f-103">La base de datos Resource es de solo lectura y contiene todos los objetos del sistema que se incluyen con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="07b8f-103">The Resource database is a read-only database that contains all the system objects that are included with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="07b8f-104">objetos del sistema, tales como sys.objects, persisten físicamente en la base de datos Resource, pero aparecen lógicamente en el esquema sys de cada base de datos.</span><span class="sxs-lookup"><span data-stu-id="07b8f-104">system objects, such as sys.objects, are physically persisted in the Resource database, but they logically appear in the sys schema of every database.</span></span> <span data-ttu-id="07b8f-105">La base de datos Resource no contiene datos o metadatos del usuario.</span><span class="sxs-lookup"><span data-stu-id="07b8f-105">The Resource database does not contain user data or user metadata.</span></span>  
  
 <span data-ttu-id="07b8f-106">La base de datos de recursos hace que el procedimiento de actualizar a una versión nueva de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sea más rápido y sencillo.</span><span class="sxs-lookup"><span data-stu-id="07b8f-106">The Resource database makes upgrading to a new version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] an easier and faster procedure.</span></span> <span data-ttu-id="07b8f-107">En versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], la actualización requiere quitar y crear los objetos del sistema.</span><span class="sxs-lookup"><span data-stu-id="07b8f-107">In earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], upgrading required dropping and creating system objects.</span></span> <span data-ttu-id="07b8f-108">Como el archivo de la base de datos Resource contiene todos los objetos del sistema, ahora para realizar una actualización basta con copiar el único archivo de base de datos Resource en el servidor local.</span><span class="sxs-lookup"><span data-stu-id="07b8f-108">Because the Resource database file contains all system objects, an upgrade is now accomplished simply by copying the single Resource database file to the local server.</span></span>  
  
## <a name="physical-properties-of-resource"></a><span data-ttu-id="07b8f-109">Propiedades físicas de recurso</span><span class="sxs-lookup"><span data-stu-id="07b8f-109">Physical Properties of Resource</span></span>  
 <span data-ttu-id="07b8f-110">Los nombres de archivos físicos de la base de datos de recursos son mssqlsystemresource.mdf y mssqlsystemresource.ldf.</span><span class="sxs-lookup"><span data-stu-id="07b8f-110">The physical file names of the Resource database are mssqlsystemresource.mdf and mssqlsystemresource.ldf.</span></span> <span data-ttu-id="07b8f-111">Estos archivos se encuentran en \<*drive*>:\Archivos de programa\Microsoft SQL Server\MSSQL\<version>.\<*instance_name*>\MSSQL\Binn\ y no deben cambiarse.</span><span class="sxs-lookup"><span data-stu-id="07b8f-111">These files are located in \<*drive*>:\Program Files\Microsoft SQL Server\MSSQL\<version>.\<*instance_name*>\MSSQL\Binn\ and should not be moved.</span></span> <span data-ttu-id="07b8f-112">Cada instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tiene un solo archivo mssqlsystemresource.mdf asociado y las instancias no lo comparten.</span><span class="sxs-lookup"><span data-stu-id="07b8f-112">Each instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has one and only one associated mssqlsystemresource.mdf file, and instances do not share this file.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="07b8f-113">En ocasiones, las actualizaciones y los paquetes de servicios ofrecen una base de datos de nuevos recursos, que se instala en la carpeta BINN.</span><span class="sxs-lookup"><span data-stu-id="07b8f-113">Upgrades and service packs sometimes provide a new resource database which is installed to the BINN folder.</span></span> <span data-ttu-id="07b8f-114">No es compatible ni recomendable cambiar la ubicación de la base de datos de recursos.</span><span class="sxs-lookup"><span data-stu-id="07b8f-114">Changing the location of the resource database is not supported or recommended.</span></span>  
  
## <a name="backing-up-and-restoring-the-resource-database"></a><span data-ttu-id="07b8f-115">Realizar copias de seguridad y restaurar la base de datos Resource</span><span class="sxs-lookup"><span data-stu-id="07b8f-115">Backing Up and Restoring the Resource Database</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="07b8f-116">no puede hacer una copia de seguridad de la base de datos de recursos.</span><span class="sxs-lookup"><span data-stu-id="07b8f-116">cannot back up the Resource database.</span></span> <span data-ttu-id="07b8f-117">Puede realizar su propia copia de seguridad basada en archivos o en un disco si trata el archivo mssqlsystemresource.mdf como si fuera binario (.EXE), en lugar de un archivo de base de datos, pero no puede utilizar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para restaurar las copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="07b8f-117">You can perform your own file-based or a disk-based backup by treating the mssqlsystemresource.mdf file as if it were a binary (.EXE) file, rather than a database file, but you cannot use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to restore your backups.</span></span> <span data-ttu-id="07b8f-118">La restauración de una copia de seguridad de mssqlsystemresource.mdf solo se puede hacer de forma manual y hay que tener cuidado de no sobrescribir la base de datos Resource actual con una versión desusada potencialmente insegura.</span><span class="sxs-lookup"><span data-stu-id="07b8f-118">Restoring a backup copy of mssqlsystemresource.mdf can only be done manually, and you must be careful not to overwrite the current Resource database with an out-of-date or potentially insecure version.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="07b8f-119">Después de restaurar una copia de seguridad de mssqlsystemresource.mdf, debe volver a aplicar cualquier actualización posterior.</span><span class="sxs-lookup"><span data-stu-id="07b8f-119">After restoring a backup of mssqlsystemresource.mdf, you must reapply any subsequent updates.</span></span>  
  
## <a name="accessing-the-resource-database"></a><span data-ttu-id="07b8f-120">Acceso a la base de datos Resource</span><span class="sxs-lookup"><span data-stu-id="07b8f-120">Accessing the Resource Database</span></span>  
 <span data-ttu-id="07b8f-121">Solo un experto de los Servicios de soporte al cliente (CSS) de Microsoft debe modificar o dirigir la modificación de la base de datos Resource.</span><span class="sxs-lookup"><span data-stu-id="07b8f-121">The Resource database should only be modified by or at the direction of a Microsoft Customer Support Services (CSS) specialist.</span></span> <span data-ttu-id="07b8f-122">El identificador de la base de datos Resource siempre es 32767.</span><span class="sxs-lookup"><span data-stu-id="07b8f-122">The ID of the Resource database is always 32767.</span></span> <span data-ttu-id="07b8f-123">Otros valores importantes asociados a la base de datos Resource son el número de versión y la última vez que se actualizó la base de datos.</span><span class="sxs-lookup"><span data-stu-id="07b8f-123">Other important values associated with the Resource database are the version number and the last time that the database was updated.</span></span>  
  
 <span data-ttu-id="07b8f-124">**Para determinar el número de versión de la base de datos** Resource **utilice**:</span><span class="sxs-lookup"><span data-stu-id="07b8f-124">**To determine the version number of the** Resource **database, use**:</span></span>  
  
```  
SELECT SERVERPROPERTY('ResourceVersion');  
GO  
```  
  
 <span data-ttu-id="07b8f-125">**Para determinar cuándo se actualizó por última vez la base de datos** Resource **, utilice**:</span><span class="sxs-lookup"><span data-stu-id="07b8f-125">**To determine when the** Resource **database was last updated, use**:</span></span>  
  
```  
SELECT SERVERPROPERTY('ResourceLastUpdateDateTime');  
GO  
```  
  
 <span data-ttu-id="07b8f-126">**Para obtener acceso a definiciones SQL de objetos del sistema, use la función OBJECT_DEFINITION:**</span><span class="sxs-lookup"><span data-stu-id="07b8f-126">**To access SQL definitions of system objects, use the OBJECT_DEFINITION function:**</span></span>  
  
```  
SELECT OBJECT_DEFINITION(OBJECT_ID('sys.objects'));  
GO  
```  
  
## <a name="related-content"></a><span data-ttu-id="07b8f-127">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="07b8f-127">Related Content</span></span>  
 [<span data-ttu-id="07b8f-128">Bases de datos del sistema</span><span class="sxs-lookup"><span data-stu-id="07b8f-128">System Databases</span></span>](system-databases.md)  
  
 [<span data-ttu-id="07b8f-129">Conexión de diagnóstico para administradores de bases de datos</span><span class="sxs-lookup"><span data-stu-id="07b8f-129">Diagnostic Connection for Database Administrators</span></span>](../../database-engine/configure-windows/diagnostic-connection-for-database-administrators.md)  
  
 [<span data-ttu-id="07b8f-130">OBJECT_DEFINITION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="07b8f-130">OBJECT_DEFINITION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/object-definition-transact-sql)  
  
 [<span data-ttu-id="07b8f-131">SERVERPROPERTY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="07b8f-131">SERVERPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/serverproperty-transact-sql)  
  
 [<span data-ttu-id="07b8f-132">Iniciar SQL Server en modo de usuario único</span><span class="sxs-lookup"><span data-stu-id="07b8f-132">Start SQL Server in Single-User Mode</span></span>](../../database-engine/configure-windows/start-sql-server-in-single-user-mode.md)  
  
  
