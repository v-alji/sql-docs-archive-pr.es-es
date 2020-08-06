---
title: MSSQLSERVER_3168 | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3168 (Database Engine error)
ms.assetid: 991111d9-1eb3-43e9-9333-a75a775c3200
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 764f456653365c085e9f756a749910bbd03b4259
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673018"
---
# <a name="mssqlserver_3168"></a><span data-ttu-id="8a398-102">MSSQLSERVER_3168</span><span class="sxs-lookup"><span data-stu-id="8a398-102">MSSQLSERVER_3168</span></span>
    
## <a name="details"></a><span data-ttu-id="8a398-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="8a398-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8a398-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="8a398-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="8a398-105">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="8a398-105">Event ID</span></span>|<span data-ttu-id="8a398-106">3168</span><span class="sxs-lookup"><span data-stu-id="8a398-106">3168</span></span>|  
|<span data-ttu-id="8a398-107">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="8a398-107">Event Source</span></span>|<span data-ttu-id="8a398-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8a398-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8a398-109">Componente</span><span class="sxs-lookup"><span data-stu-id="8a398-109">Component</span></span>|<span data-ttu-id="8a398-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8a398-110">SQLEngine</span></span>|  
|<span data-ttu-id="8a398-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="8a398-111">Symbolic Name</span></span>|<span data-ttu-id="8a398-112">LDDB_SYSTEMWRONGVER</span><span class="sxs-lookup"><span data-stu-id="8a398-112">LDDB_SYSTEMWRONGVER</span></span>|  
|<span data-ttu-id="8a398-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="8a398-113">Message Text</span></span>|<span data-ttu-id="8a398-114">No se puede restaurar la copia de seguridad de la base de datos del sistema en el dispositivo %!s! porque se creó con una versión de servidor (%!s!) distinta de la de este servidor (%!s!)</span><span class="sxs-lookup"><span data-stu-id="8a398-114">The backup of the system database on the device %ls cannot be restored because it was created by a different version of the server (%ls) than this server (%ls).</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8a398-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="8a398-115">Explanation</span></span>  
 <span data-ttu-id="8a398-116">No puede restaurar una copia de seguridad de una base de datos del sistema (**master**, **model** o **msdb**) en una compilación de servidor distinta de la compilación en la que se realizó la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8a398-116">You cannot restore a backup of a system database (**master**, **model**, or **msdb**) on a server build that differs from the build on which the backup was originally performed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8a398-117">La instalación de un Service Pack o una compilación de revisión cambia el número de compilación del servidor y las compilaciones de servidor son siempre incrementales.</span><span class="sxs-lookup"><span data-stu-id="8a398-117">Installing a service pack or a hotfix build changes the server build number, and server builds are always incremental.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="8a398-118">Causas posibles</span><span class="sxs-lookup"><span data-stu-id="8a398-118">Possible Causes</span></span>  
 <span data-ttu-id="8a398-119">El esquema de la base de datos para bases de datos del sistema pueda cambiar entre compilaciones de servidor.</span><span class="sxs-lookup"><span data-stu-id="8a398-119">The database schema for system databases may be changed across server builds.</span></span> <span data-ttu-id="8a398-120">Para asegurarse de que un cambio de esquema no crea incoherencias, la instrucción RESTORE compara el número de compilación del servidor en el archivo de copia de seguridad con el del servidor en el que está intentando restaurar la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8a398-120">To make sure that a schema change does not cause inconsistencies, the RESTORE statement compares the server build number on the backup file to the build number of the server on which you are trying to restore the backup.</span></span> <span data-ttu-id="8a398-121">Si las compilaciones son diferentes, la instrucción genera el mensaje de error 3168 y la operación de restauración finaliza de forma anómala.</span><span class="sxs-lookup"><span data-stu-id="8a398-121">If the builds are different, the statement issues the 3168 error message, and the restore operation terminates abnormally.</span></span>  
  
 <span data-ttu-id="8a398-122">Entre los escenarios en los que se puede producir este problema se incluyen:</span><span class="sxs-lookup"><span data-stu-id="8a398-122">Some scenarios in which this problem may occur include the following:</span></span>  
  
-   <span data-ttu-id="8a398-123">Un usuario intenta restaurar una base de datos del sistema en el servidor A desde una copia de seguridad realizada en el servidor B. Los servidores A y B pertenecen a compilaciones de servidor diferentes.</span><span class="sxs-lookup"><span data-stu-id="8a398-123">A user tries to restore a system database on Server A from a backup taken on Server B. Servers A and B are on different server builds.</span></span> <span data-ttu-id="8a398-124">Por ejemplo, el servidor A se encuentra en una compilación de la versión original mientras que el servidor B se encuentra en una compilación del Service Pack 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="8a398-124">For example, Server A might be on the original release version build and Server B might be on a service pack 1 (SP1) build.</span></span>  
  
-   <span data-ttu-id="8a398-125">Un usuario intenta restaurar una base de datos del sistema desde una copia de seguridad efectuada en el mismo servidor.</span><span class="sxs-lookup"><span data-stu-id="8a398-125">A user tries to restore a system database from a backup taken on the same server.</span></span> <span data-ttu-id="8a398-126">Sin embargo, el servidor ejecutaba una compilación diferente cuando se realizó la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8a398-126">However, the server was running a different build when the backup occurred.</span></span> <span data-ttu-id="8a398-127">Es decir, el servidor se actualizó después de realizar la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8a398-127">That is, the server was upgraded since the backup was performed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8a398-128">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="8a398-128">User Action</span></span>  
 <span data-ttu-id="8a398-129">En estas situaciones, el proceso de restauración es muy complicado y solo se utiliza como último recurso.</span><span class="sxs-lookup"><span data-stu-id="8a398-129">The restore process in this situation is fairly involved, and used only as a last resort.</span></span> <span data-ttu-id="8a398-130">Para obtener más información, vea "[No puede restaurar copia de seguridad de base de datos de sistema a una generación distinta de SQL Server](https://support.microsoft.com/kb/264474)".</span><span class="sxs-lookup"><span data-stu-id="8a398-130">For more information, see"[You cannot restore system database backups to a different build of SQL Server](https://support.microsoft.com/kb/264474)".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a398-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8a398-131">See Also</span></span>  
 [<span data-ttu-id="8a398-132">Realizar copias de seguridad y restaurar bases de datos del sistema &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8a398-132">Back Up and Restore of System Databases &#40;SQL Server&#41;</span></span>](../backup-restore/back-up-and-restore-of-system-databases-sql-server.md)  
  
  
