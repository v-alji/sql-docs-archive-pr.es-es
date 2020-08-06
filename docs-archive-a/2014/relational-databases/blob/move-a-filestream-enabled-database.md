---
title: Movimiento de una base de datos habilitada para FILESTREAM | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], moving a FILESTREAM-enabled database
ms.assetid: dd4d270d-9283-431a-aa6b-e571fced1893
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 79740ee86a89566113650865e3fd6ec54c7cb918
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744143"
---
# <a name="move-a-filestream-enabled-database"></a><span data-ttu-id="ee199-102">Mover una base de datos habilitada para FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="ee199-102">Move a FILESTREAM-Enabled Database</span></span>
  <span data-ttu-id="ee199-103">En este tema se muestra cómo mover una base de datos habilitada para FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="ee199-103">This topic shows how to move a FILESTREAM-enabled database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ee199-104">Los ejemplos de este tema requieren la base de datos Archive que se crea en [Crear una base de datos habilitada para FILESTREAM](create-a-filestream-enabled-database.md).</span><span class="sxs-lookup"><span data-stu-id="ee199-104">The examples in this topic require the Archive database that is created in [Create a FILESTREAM-Enabled Database](create-a-filestream-enabled-database.md).</span></span>  
  
### <a name="to-move-a-filestream-enabled-database"></a><span data-ttu-id="ee199-105">Para mover una base de datos habilitada para FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="ee199-105">To move a FILESTREAM-enabled database</span></span>  
  
1.  <span data-ttu-id="ee199-106">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], haga clic en **Nueva consulta** para abrir el Editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="ee199-106">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], click **New Query** to open the Query Editor.</span></span>  
  
2.  <span data-ttu-id="ee199-107">Copie el siguiente script de [!INCLUDE[tsql](../../includes/tsql-md.md)] en el Editor de consultas y, a continuación, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="ee199-107">Copy the following [!INCLUDE[tsql](../../includes/tsql-md.md)] script into the Query Editor, and then click **Execute**.</span></span> <span data-ttu-id="ee199-108">Este script muestra la ubicación de los archivos de base de datos físicos que usa la base de datos FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="ee199-108">This script displays the location of the physical database files that the FILESTREAM database uses.</span></span>  
  
    ```sql  
    USE Archive  
    GO  
    SELECT type_desc, name, physical_name from sys.database_files  
    ```  
  
3.  <span data-ttu-id="ee199-109">Copie el siguiente script de [!INCLUDE[tsql](../../includes/tsql-md.md)] en el Editor de consultas y, a continuación, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="ee199-109">Copy the following [!INCLUDE[tsql](../../includes/tsql-md.md)] script into the Query Editor, and then click **Execute**.</span></span> <span data-ttu-id="ee199-110">Este código pone la base de datos `Archive` sin conexión.</span><span class="sxs-lookup"><span data-stu-id="ee199-110">This code takes the `Archive` database offline.</span></span>  
  
    ```sql  
    USE master  
    EXEC sp_detach_db Archive  
    GO  
    ```  
  
4.  <span data-ttu-id="ee199-111">Cree la carpeta `C:\moved_location`y, a continuación, mueva a ella los archivos y carpetas que se enumeran en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="ee199-111">Create the folder `C:\moved_location`, and then move the files and folders that are listed in step 2 into it.</span></span>  
  
5.  <span data-ttu-id="ee199-112">Copie el siguiente script de [!INCLUDE[tsql](../../includes/tsql-md.md)] en el Editor de consultas y, a continuación, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="ee199-112">Copy the following [!INCLUDE[tsql](../../includes/tsql-md.md)] script into the Query Editor, and then click **Execute**.</span></span> <span data-ttu-id="ee199-113">Este script establece la base de datos `Archive` en línea.</span><span class="sxs-lookup"><span data-stu-id="ee199-113">This script sets the `Archive` database online.</span></span>  
  
    ```sql  
    CREATE DATABASE Archive ON  
    PRIMARY ( NAME = Arch1,  
        FILENAME = 'c:\moved_location\archdat1.mdf'),  
    FILEGROUP FileStreamGroup1 CONTAINS FILESTREAM( NAME = Arch3,  
        FILENAME = 'c:\moved_location\filestream1')  
    LOG ON  ( NAME = Archlog1,  
        FILENAME = 'c:\moved_location\archlog1.ldf')  
    FOR ATTACH  
    GO  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ee199-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ee199-114">See Also</span></span>  
 [<span data-ttu-id="ee199-115">sp_detach_db &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ee199-115">sp_detach_db &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-detach-db-transact-sql)  
  
  
