---
title: MSSQLSERVER_8992 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8992 (Database Engine error)
ms.assetid: 68467e6a-09d8-478f-8bd9-3bb09453ada3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: adcf914accab43202cf148fe852b334c9b078287
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678190"
---
# <a name="mssqlserver_8992"></a><span data-ttu-id="ec180-102">MSSQLSERVER_8992</span><span class="sxs-lookup"><span data-stu-id="ec180-102">MSSQLSERVER_8992</span></span>
    
## <a name="details"></a><span data-ttu-id="ec180-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="ec180-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ec180-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="ec180-104">Product Name</span></span>|<span data-ttu-id="ec180-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ec180-105">SQL Server</span></span>|  
|<span data-ttu-id="ec180-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ec180-106">Event ID</span></span>|<span data-ttu-id="ec180-107">8992</span><span class="sxs-lookup"><span data-stu-id="ec180-107">8992</span></span>|  
|<span data-ttu-id="ec180-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="ec180-108">Event Source</span></span>|<span data-ttu-id="ec180-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ec180-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ec180-110">Componente</span><span class="sxs-lookup"><span data-stu-id="ec180-110">Component</span></span>|<span data-ttu-id="ec180-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ec180-111">SQLEngine</span></span>|  
|<span data-ttu-id="ec180-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ec180-112">Symbolic Name</span></span>|<span data-ttu-id="ec180-113">DBCC3_CHECK_CATALOG</span><span class="sxs-lookup"><span data-stu-id="ec180-113">DBCC3_CHECK_CATALOG</span></span>|  
|<span data-ttu-id="ec180-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ec180-114">Message Text</span></span>|<span data-ttu-id="ec180-115">Mensaje de comprobación del catálogo ERROR, nivel LEVEL, estado STATE: MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="ec180-115">Check Catalog Msg ERROR Level LEVEL State STATE: MESSAGE.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ec180-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="ec180-116">Explanation</span></span>  
 <span data-ttu-id="ec180-117">DBCC CHECKCATALOG o DBCC CHECKDB encontró una incoherencia en las tablas de metadatos de sistema para el objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="ec180-117">DBCC CHECKCATALOG or DBCC CHECKDB found an inconsistency in the system metadata tables for the specified object.</span></span> <span data-ttu-id="ec180-118">Es decir, hay una incoherencia entre el identificador de objeto registrado y el objeto especificado en el mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="ec180-118">That is, there is an inconsistency between the recorded object ID and the object specified in error message.</span></span>  
  
 <span data-ttu-id="ec180-119">Este error se puede producir cuando una o más tablas del sistema se han actualizado manualmente de una manera que crea una incoherencia en los metadatos del sistema.</span><span class="sxs-lookup"><span data-stu-id="ec180-119">This error can occur when one or more system tables has been manually updated in a way that creates an inconsistency in the system metadata.</span></span> <span data-ttu-id="ec180-120">Por ejemplo, un usuario puede haber eliminado de forma manual un objeto de la tabla **sysobjects** sin quitar las filas asociadas de otras tablas como **sysindexes** y **syscolumns**.</span><span class="sxs-lookup"><span data-stu-id="ec180-120">For example, a user may have manually deleted an object from the **sysobjects** table without removing associated rows in other tables such as **sysindexes** and **syscolumns**.</span></span>  
  
 <span data-ttu-id="ec180-121">Este error se puede producir al ejecutar DBCC CHECKDB contra una base de datos actualizada de SQL Server 2000 a SQL Server 2005 o posterior.</span><span class="sxs-lookup"><span data-stu-id="ec180-121">This error can occur when running DBCC CHECKDB against a database that has been upgraded from SQL Server 2000 to SQL Server 2005 or later.</span></span> <span data-ttu-id="ec180-122">En SQL Server 2000, DBCC CHECKDB no incluía la funcionalidad de DBCC CHECKCATALOG, de modo que el error no se detectara antes de la actualización a menos que DBCC CHECKCATALOG se ejecutara específicamente contra la base de datos en SQL Server 2000.</span><span class="sxs-lookup"><span data-stu-id="ec180-122">In SQL Server 2000, DBCC CHECKDB did not include DBCC CHECKCATALOG functionality, so the error would not be caught before upgrade unless DBCC CHECKCATALOG was specifically executed against the database in SQL Server 2000.</span></span>  
  
 <span data-ttu-id="ec180-123">Puede ver alguno de los errores siguientes junto con el error 8992:</span><span class="sxs-lookup"><span data-stu-id="ec180-123">You may see any of the following errors in conjunction with error 8992:</span></span>  
  
 <span data-ttu-id="ec180-124">Msg 3851 - Se encontró una fila no válida (%ls) en la tabla del sistema sys.%ls%ls.</span><span class="sxs-lookup"><span data-stu-id="ec180-124">Msg 3851 - An invalid row (%ls) was found in the system table sys.%ls%ls.</span></span>  
  
 <span data-ttu-id="ec180-125">Msg 3852 - La fila (%ls) de sys.%ls%ls no tiene una fila coincidente (%ls) en sys.%ls%ls.</span><span class="sxs-lookup"><span data-stu-id="ec180-125">Msg 3852 - Row (%ls) in sys.%ls%ls does not have a matching row (%ls) in sys.%ls%ls.</span></span>  
  
 <span data-ttu-id="ec180-126">3853 - El atributo (%ls) de la fila (%ls) de sys.%ls%ls no tiene una fila coincidente (%ls) en sys.%ls%ls.</span><span class="sxs-lookup"><span data-stu-id="ec180-126">3853 - Attribute (%ls) of row (%ls) in sys.%ls%ls does not have a matching row (%ls) in sys.%ls%ls.</span></span>  
  
 <span data-ttu-id="ec180-127">3854 - El atributo (%ls) de la fila (%ls) de sys.%ls%ls tiene una fila coincidente (%ls) en sys.%ls%ls que no es válida.</span><span class="sxs-lookup"><span data-stu-id="ec180-127">3854 - Attribute (%ls) of row (%ls) in sys.%ls%ls has a matching row (%ls) in sys.%ls%ls that is invalid.</span></span>  
  
 <span data-ttu-id="ec180-128">3855 - El atributo (%ls) existe sin una fila (%ls) in sys.%ls%ls.</span><span class="sxs-lookup"><span data-stu-id="ec180-128">3855 - Attribute (%ls) exists without a row (%ls) in sys.%ls%ls.</span></span>  
  
 <span data-ttu-id="ec180-129">3856 - El atributo (%ls) existe (aunque no debería) para una fila (%ls) de sys.%ls%ls.</span><span class="sxs-lookup"><span data-stu-id="ec180-129">3856 - Attribute (%ls) exists but should not for row (%ls) in sys.%ls%ls.</span></span>  
  
 <span data-ttu-id="ec180-130">3857 - El atributo (%ls) requerido falta en una fila (%ls) de sys.%ls%ls.</span><span class="sxs-lookup"><span data-stu-id="ec180-130">3857 - The attribute (%ls) is required but is missing for row (%ls) in sys.%ls%ls.</span></span>  
  
 <span data-ttu-id="ec180-131">3858 - El atributo (%ls) de la fila (%ls) de sys.%ls%ls tiene un valor no válido.</span><span class="sxs-lookup"><span data-stu-id="ec180-131">3858 - The attribute (%ls) of row (%ls) in sys.%ls%ls has an invalid value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ec180-132">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ec180-132">User Action</span></span>  
  
### <a name="drop-and-re-create-the-specified-object"></a><span data-ttu-id="ec180-133">Quite y vuelva a crear el objeto especificado</span><span class="sxs-lookup"><span data-stu-id="ec180-133">Drop and Re-create the Specified Object</span></span>  
 <span data-ttu-id="ec180-134">Si es posible, quite y vuelva a crear el objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="ec180-134">If possible, drop and recreate the specified object.</span></span> <span data-ttu-id="ec180-135">Por ejemplo, si el objeto es un procedimiento almacenado o un tipo definido por el usuario, al volver a crearlo, puede que se resuelva el problema.</span><span class="sxs-lookup"><span data-stu-id="ec180-135">For example, if the object is a stored procedure or user-defined type, recreating the object may resolve the problem.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="ec180-136">Restaure mediante la copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="ec180-136">Restore from Backup</span></span>  
 <span data-ttu-id="ec180-137">Si el problema no está relacionado con el hardware y tiene una copia de seguridad limpia disponible, úsela para restaurar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ec180-137">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span> <span data-ttu-id="ec180-138">Esta acción solo es aplicable si la copia de seguridad no contiene el error de los metadatos.</span><span class="sxs-lookup"><span data-stu-id="ec180-138">This action is only applicable if the backup does not contain the metadata error.</span></span>  
  
### <a name="export-the-data-to-a-new-database"></a><span data-ttu-id="ec180-139">Exporte los datos a una nueva base de datos</span><span class="sxs-lookup"><span data-stu-id="ec180-139">Export the Data to a New Database</span></span>  
 <span data-ttu-id="ec180-140">Si la copia de seguridad también contiene la incoherencia de metadatos, debe crear una nueva base de datos y exportar el contenido de la base de datos existente a la nueva.</span><span class="sxs-lookup"><span data-stu-id="ec180-140">If the backup also contains the metadata inconsistency, you need to create a new database and export the contents of the existing database to the new database.</span></span>  
  
### <a name="dbcc-checkdb-cannot-repair-this-error"></a><span data-ttu-id="ec180-141">DBCC CHECKDB no puede reparar este error</span><span class="sxs-lookup"><span data-stu-id="ec180-141">DBCC CHECKDB Cannot Repair This Error</span></span>  
 <span data-ttu-id="ec180-142">Este error no se puede reparar.</span><span class="sxs-lookup"><span data-stu-id="ec180-142">This error cannot be repaired.</span></span>  <span data-ttu-id="ec180-143">Si no puede restaurar la base de datos a partir de una copia de seguridad, póngase en contacto con el servicio de soporte técnico y atención al cliente (CSS) de [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ec180-143">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
### <a name="do-not-manually-update-system-tables"></a><span data-ttu-id="ec180-144">No actualice manualmente las tablas del sistema</span><span class="sxs-lookup"><span data-stu-id="ec180-144">Do Not Manually Update System Tables</span></span>  
 <span data-ttu-id="ec180-145">No realice actualizaciones manuales de las tablas del sistema.</span><span class="sxs-lookup"><span data-stu-id="ec180-145">Do not make manual updates to system tables.</span></span> <span data-ttu-id="ec180-146">SQL Server no admite los cambios manuales en las bases de datos del sistema.</span><span class="sxs-lookup"><span data-stu-id="ec180-146">SQL Server does not support any manual changes to system databases.</span></span> <span data-ttu-id="ec180-147">Si actualiza una tabla del sistema de una base de datos de SQL Server, se registran dos eventos (identificadores de evento 17659 y 3859).</span><span class="sxs-lookup"><span data-stu-id="ec180-147">If you update a system table in a SQL Server database, two events (event ID 17659 and event ID 3859) are logged.</span></span> <span data-ttu-id="ec180-148">Para obtener más información, vea el artículo 2688307 de KB, "Se registran los identificadores de evento 17659 y 3859 al actualizar tablas del sistema en una base de datos de SQL Server".</span><span class="sxs-lookup"><span data-stu-id="ec180-148">For more information, see KB article 2688307, "Event ID 17659 and event ID 3859 are logged when you update system tables in a SQL Server database".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec180-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ec180-149">See Also</span></span>  
 [<span data-ttu-id="ec180-150">Se registran los identificadores de evento 17659 y 3859 al actualizar tablas del sistema en una base de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="ec180-150">Event ID 17659 and event ID 3859 are logged when you update system tables in a SQL Server database</span></span>](https://support.microsoft.com/kb/2688307/EN-US)  
  
  
