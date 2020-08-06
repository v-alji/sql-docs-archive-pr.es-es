---
title: Copia de bases de datos en otros servidores | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- servers [SQL Server], copying databases between
- bulk exporting [SQL Server], between servers
- database copying [SQL Server]
- migrating databases [SQL Server]
- moving databases
- copying databases
- bulk importing [SQL Server], between servers
ms.assetid: 978406d6-a3c8-4902-b1f4-4ced75234be5
author: stevestein
ms.author: sstein
ms.openlocfilehash: bcde6185f25129596b4be7a150d4ee230c54c1a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745818"
---
# <a name="copy-databases-to-other-servers"></a><span data-ttu-id="ee255-102">Copiar bases de datos en otros servidores</span><span class="sxs-lookup"><span data-stu-id="ee255-102">Copy Databases to Other Servers</span></span>
  <span data-ttu-id="ee255-103">En ocasiones resulta útil copiar una base de datos de un equipo a otro para realizar pruebas, comprobar la coherencia, desarrollar software, ejecutar informes, crear una base de datos de reflejo o, quizás, poner la base de datos a disposición de las actividades de oficinas remotas.</span><span class="sxs-lookup"><span data-stu-id="ee255-103">It is sometimes useful to copy a database from one computer to another, whether for testing, checking consistency, developing software, running reports, creating a mirror database, or, possibly, to make the database available to remote-branch operations.</span></span>  
  
 <span data-ttu-id="ee255-104">Hay varias maneras de copiar una base de datos:</span><span class="sxs-lookup"><span data-stu-id="ee255-104">There are several ways to copy a database:</span></span>  
  
-   <span data-ttu-id="ee255-105">Usar el Asistente para copiar bases de datos</span><span class="sxs-lookup"><span data-stu-id="ee255-105">Using the Copy Database Wizard</span></span>  
  
     <span data-ttu-id="ee255-106">Puede usar el Asistente para copiar bases de datos con el fin de copiar o mover bases de datos entre los servidores o actualizar una base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="ee255-106">You can use the Copy Database Wizard to copy or move databases between servers or to upgrade a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database to a later version.</span></span> <span data-ttu-id="ee255-107">Para más información, consulte [Use the Copy Database Wizard](use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="ee255-107">For more information, see [Use the Copy Database Wizard](use-the-copy-database-wizard.md).</span></span>  
  
-   <span data-ttu-id="ee255-108">Restaurar una copia de seguridad de una base de datos</span><span class="sxs-lookup"><span data-stu-id="ee255-108">Restoring a database backup</span></span>  
  
     <span data-ttu-id="ee255-109">Para copiar una base de datos completa, puede utilizar las instrucciones BACKUP y RESTORE de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ee255-109">To copy an entire database, you can use the BACKUP and RESTORE [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="ee255-110">Normalmente, la restauración de una copia de seguridad completa de una base de datos se utiliza para copiar la base de datos de un equipo a otro por varios motivos.</span><span class="sxs-lookup"><span data-stu-id="ee255-110">Typically, restoring a full backup of a database is used to copy the database from one computer to another for a variety of reasons.</span></span> <span data-ttu-id="ee255-111">Para obtener más información sobre el uso de copias de seguridad y restauración para copiar una base de datos, vea [Copiar bases de datos con Copias de seguridad y restauración](copy-databases-with-backup-and-restore.md).</span><span class="sxs-lookup"><span data-stu-id="ee255-111">For information on using backup and restore to copy a database, see [Copy Databases with Backup and Restore](copy-databases-with-backup-and-restore.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ee255-112">Para configurar una base de datos reflejada para la creación de reflejo de la base de datos, debe restaurar la base de datos en el servidor reflejado mediante RESTORE DATABASE *<nombre_de_base_de_datos>* WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="ee255-112">To set up a mirror database for database mirroring, you must restore the database onto the mirror server by using RESTORE DATABASE *<database_name>* WITH NORECOVERY.</span></span> <span data-ttu-id="ee255-113">Para obtener más información, vea [Preparar una base de datos reflejada para la creación de reflejo &#40;SQL Server&#41;](../../database-engine/database-mirroring/prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ee255-113">For more information, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
-   <span data-ttu-id="ee255-114">Utilizar el asistente Generar scripts para publicar bases de datos</span><span class="sxs-lookup"><span data-stu-id="ee255-114">Using the Generate Scripts Wizard to publish databases</span></span>  
  
     <span data-ttu-id="ee255-115">Puede utilizar el asistente Generar scripts para transferir una base de datos de un equipo local a un proveedor de hospedaje web.</span><span class="sxs-lookup"><span data-stu-id="ee255-115">You can use the Generate Scripts Wizard to transfer a database from a local computer to a Web hosting provider.</span></span> <span data-ttu-id="ee255-116">Para obtener más información, vea [Asistente Generar y publicar scripts](../scripting/generate-and-publish-scripts-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="ee255-116">For more information, see [Generate and Publish Scripts Wizard](../scripting/generate-and-publish-scripts-wizard.md).</span></span>  
  
  
