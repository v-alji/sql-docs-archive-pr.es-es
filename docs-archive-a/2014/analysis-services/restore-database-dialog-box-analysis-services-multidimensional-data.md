---
title: Cuadro de diálogo restaurar base de datos (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.sqlserverstudio.Restore.f1
ms.assetid: a3990d47-55e2-424e-8eac-87edc937e806
author: minewiskan
ms.author: owend
ms.openlocfilehash: f45a41eb10e81e1cfe1100045cc4d00353cb11fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752425"
---
# <a name="restore-database-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="737bc-102">Cuadro de diálogo Restaurar base de datos (Analysis Services - Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="737bc-102">Restore Database Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="737bc-103">Use el cuadro de diálogo **Restaurar base de datos** de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para restaurar una base de datos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] desde un archivo de copia de seguridad con el formato de copia de seguridad de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] (.abf).</span><span class="sxs-lookup"><span data-stu-id="737bc-103">Use the **Restore Database** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to restore an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database from a backup file using the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Backup File (.abf) format.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="737bc-104">Para cada archivo de copia de seguridad, el usuario que ejecuta el comando de restauración debe tener permiso para leer desde la ubicación de la copia de seguridad especificada.</span><span class="sxs-lookup"><span data-stu-id="737bc-104">For each backup file, the user who runs the restore command must have permission to read from the backup location specified for each file.</span></span> <span data-ttu-id="737bc-105">Para restaurar una base de datos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que no está instalada en el servidor, el usuario también debe ser miembro del rol de servidor para dicha instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="737bc-105">To restore an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database that is not installed on the server, the user must also be a member of the server role for that [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span> <span data-ttu-id="737bc-106">Para sobrescribir una base de datos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , el usuario debe tener uno de los roles siguientes: miembro del rol de servidor para la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] o miembro de un rol de base de datos con permisos de Control total (Administrador) en la base de datos que se va a restaurar.</span><span class="sxs-lookup"><span data-stu-id="737bc-106">To overwrite an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, the user must have one of the following roles: a member of the server role for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance, or a member of a database role with Full Control (Administrator) permissions on the database to be restored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="737bc-107">Después de restaurar una base de datos existente, el usuario que restauró la base de datos podría perder el acceso a la base de datos restaurada.</span><span class="sxs-lookup"><span data-stu-id="737bc-107">After restoring an existing database, the user who restored the database might lose access to the restored database.</span></span> <span data-ttu-id="737bc-108">Esta pérdida de acceso puede producirse si, en el momento en que se realizó la copia de seguridad, el usuario no era miembro del rol de servidor o no era miembro de rol de base de datos con permisos de Control total (Administrador).</span><span class="sxs-lookup"><span data-stu-id="737bc-108">This loss of access can occur if, at the time that the backup was performed, the user was not a member of the server role or was not a member of the database role with Full Control (Administrator) permissions.</span></span>  
  
 <span data-ttu-id="737bc-109">**Para mostrar el cuadro de diálogo Restaurar base de datos**</span><span class="sxs-lookup"><span data-stu-id="737bc-109">**To display the Restore Database dialog box**</span></span>  
  
-   <span data-ttu-id="737bc-110">En [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], haga clic con el botón derecho en la carpeta **Bases de datos** de una instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] o en una base de datos en el **Explorador de objetos**y, después, haga clic en **Restaurar**.</span><span class="sxs-lookup"><span data-stu-id="737bc-110">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], right-click either the **Databases** folder of an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance or a database in **Object Explorer**, and then click **Restore**.</span></span>  
  
 <span data-ttu-id="737bc-111">El cuadro de diálogo **Restaurar base de datos** muestra las páginas siguientes.</span><span class="sxs-lookup"><span data-stu-id="737bc-111">The **Restore Database** dialog box contains the following pages.</span></span>  
  
## <a name="pages"></a><span data-ttu-id="737bc-112">Páginas</span><span class="sxs-lookup"><span data-stu-id="737bc-112">Pages</span></span>  
 <span data-ttu-id="737bc-113">**General**</span><span class="sxs-lookup"><span data-stu-id="737bc-113">**General**</span></span>  
 <span data-ttu-id="737bc-114">Use esta página para seleccionar la base de datos que desea restaurar, el archivo de copia de seguridad desde el que desea restaurar la base de datos y las opciones generales y la contraseña para restaurar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="737bc-114">Use this page to select the database to restore, the backup file from which to restore the database, as well as the general options and password to use while restoring the database.</span></span> <span data-ttu-id="737bc-115">Para obtener más información sobre esta página, vea [General &#40;cuadro de diálogo Restaurar base de datos&#41; &#40;Analysis Services - Datos multidimensionales&#41;](general-restore-database-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="737bc-115">For more information about this page, see [General &#40;Restore Database Dialog Box&#41; &#40;Analysis Services - Multidimensional Data&#41;](general-restore-database-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="737bc-116">**Particiones**</span><span class="sxs-lookup"><span data-stu-id="737bc-116">**Partitions**</span></span>  
 <span data-ttu-id="737bc-117">Use esta página para restaurar las particiones locales en ubicaciones específicas y para restaurar particiones remotas desde archivos de copia de seguridad remotos.</span><span class="sxs-lookup"><span data-stu-id="737bc-117">Use this page to restore local partitions to specified locations, and to restore remote partitions from remote backup files.</span></span> <span data-ttu-id="737bc-118">Para obtener más información sobre esta página, vea [Particiones &#40;cuadro de diálogo Restaurar base de datos&#41; &#40;Analysis Services - Datos multidimensionales&#41;](partitions-restore-database-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="737bc-118">For more information about this page, see [Partitions &#40;Restore Database Dialog Box&#41; &#40;Analysis Services - Multidimensional Data&#41;](partitions-restore-database-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="737bc-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="737bc-119">See Also</span></span>  
 <span data-ttu-id="737bc-120">[Analysis Services diseñadores y cuadros de diálogo &#40;datos multidimensionales&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="737bc-120">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="737bc-121">Realizar una copia de seguridad y restaurar las bases de datos de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="737bc-121">Backup and Restore of Analysis Services Databases</span></span>](multidimensional-models/backup-and-restore-of-analysis-services-databases.md)  
  
  
