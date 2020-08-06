---
title: Los archivos de copia de seguridad deben estar en dispositivos independientes de los archivos de base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 7039bebb-1f25-4cf3-81f1-393dfb78da12
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d5eff9cb3139e1e1043f99ba63d11160b1010c27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746528"
---
# <a name="backup-files-must-be-on-separate-devices-from-the-database-files"></a><span data-ttu-id="53985-102">Los archivos de copia de seguridad deben estar en dispositivos independientes de los archivos de base de datos</span><span class="sxs-lookup"><span data-stu-id="53985-102">Backup Files Must Be on Separate Devices from the Database Files</span></span>
  <span data-ttu-id="53985-103">Esta regla comprueba si los archivos de base de datos están en dispositivos independientes de los archivos de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="53985-103">This rule checks whether database files are on devices separate from the backup files.</span></span> <span data-ttu-id="53985-104">Si los archivos de base de datos y los archivos de copia de seguridad están en el mismo dispositivo y este sufre un error, la base de datos y las copias de seguridad no estarán disponibles.</span><span class="sxs-lookup"><span data-stu-id="53985-104">If database files and backup files are on the same device and the device fails, the database and backups will be unavailable.</span></span> <span data-ttu-id="53985-105">Además, al colocar los archivos de base de datos y los archivos de copia de seguridad en dispositivos independientes, mejora el rendimiento de E/S en el uso en producción de la base de datos y en la escritura de las copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="53985-105">Also, putting the database and backup files on the separate devices optimizes the I/O performance for both the production use of the database and the writing of backups.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="53985-106">Prácticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="53985-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="53985-107">Recomendamos encarecidamente que la base de datos y las copias de seguridad se coloquen en dispositivos de copia de seguridad independientes.</span><span class="sxs-lookup"><span data-stu-id="53985-107">We strongly recommend that you put the database and backups on separate backup devices.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="53985-108">Esta directiva no puede detectar dispositivos físicos independientes mediante puntos de montaje.</span><span class="sxs-lookup"><span data-stu-id="53985-108">This policy cannot detect separate physical devices through mount points.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="53985-109">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="53985-109">For More Information</span></span>  
 [<span data-ttu-id="53985-110">Dispositivos de copia de seguridad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="53985-110">Backup Devices &#40;SQL Server&#41;</span></span>](../relational-databases/backup-restore/backup-devices-sql-server.md)  
  
 [<span data-ttu-id="53985-111">Copia de seguridad y restauración de bases de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="53985-111">Back Up and Restore of SQL Server Databases</span></span>](../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md)  
  
## <a name="see-also"></a><span data-ttu-id="53985-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="53985-112">See Also</span></span>  
 [<span data-ttu-id="53985-113">Supervisar y aplicar las prácticas recomendadas usando la administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="53985-113">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](../relational-databases/policy-based-management/monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
