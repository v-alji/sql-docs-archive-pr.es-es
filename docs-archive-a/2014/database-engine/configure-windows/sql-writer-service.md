---
title: Servicio del objeto de escritura de SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- VDI [SQL Server]
- restoring [SQL Server], SQL Writer Service
- backups [SQL Server], while SQL Server running
- Volume Shadow Copy Service
- volume backups while running [SQL Server]
- Virtual Backup Device Interface [SQL Server]
- SQL Writer Service
- services [SQL Server], SQL Writer
- MSDE Writer
- VSS
ms.assetid: 0f299867-f499-4c2a-ad6f-b2ef1869381d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 310722c6617c7a2c9e0f384ec23ae371ab230536
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663100"
---
# <a name="sql-writer-service"></a><span data-ttu-id="c7973-102">servicio del objeto de escritura de SQL</span><span class="sxs-lookup"><span data-stu-id="c7973-102">SQL Writer Service</span></span>
  <span data-ttu-id="c7973-103">El servicio del objeto de escritura de SQL proporciona otras funciones para la realización de copias de seguridad y restauración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante el marco del Servicio de instantáneas de volumen.</span><span class="sxs-lookup"><span data-stu-id="c7973-103">The SQL Writer Service provides added functionality for backup and restore of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] through the Volume Shadow Copy Service framework.</span></span>  
  
 <span data-ttu-id="c7973-104">El servicio del objeto de escritura de SQL se instala automáticamente.</span><span class="sxs-lookup"><span data-stu-id="c7973-104">The SQL Writer Service is installed automatically.</span></span> <span data-ttu-id="c7973-105">Se debe ejecutar cuando la aplicación Servicio de instantáneas de volumen (VSS) solicita una copia de seguridad o una restauración.</span><span class="sxs-lookup"><span data-stu-id="c7973-105">It must be running when the Volume Shadow Copy Service (VSS) application requests a backup or restore.</span></span> <span data-ttu-id="c7973-106">Para configurar el servicio, utilice el applet Servicios de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="c7973-106">To configure the service, use the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Services applet.</span></span> <span data-ttu-id="c7973-107">El servicio SQL Writer se instala en todos los sistemas operativos.</span><span class="sxs-lookup"><span data-stu-id="c7973-107">The SQL Writer Service installs on all operating systems.</span></span>  
  
## <a name="purpose"></a><span data-ttu-id="c7973-108">Propósito</span><span class="sxs-lookup"><span data-stu-id="c7973-108">Purpose</span></span>  
 <span data-ttu-id="c7973-109">Durante la ejecución, el [!INCLUDE[ssDE](../../includes/ssde-md.md)] bloquea los archivos de datos y tiene acceso exclusivo a estos.</span><span class="sxs-lookup"><span data-stu-id="c7973-109">When running, [!INCLUDE[ssDE](../../includes/ssde-md.md)] locks and has exclusive access to the data files.</span></span> <span data-ttu-id="c7973-110">Cuando no se ejecuta el servicio del objeto de escritura de SQL, los programas de copia de seguridad que se estén ejecutando en Windows no tendrán acceso a los archivos de datos, y se deberán realizar las copias de seguridad mediante [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c7973-110">When the SQL Writer Service is not running, backup programs running in Windows do not have access to the data files, and backups must be performed using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup.</span></span>  
  
 <span data-ttu-id="c7973-111">Utilice el servicio del objeto de escritura de SQL para que los programas de copia de seguridad de Windows puedan copiar archivos de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mientras se ejecuta [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c7973-111">Use the SQL Writer Service to permit Windows backup programs to copy [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data files while [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running.</span></span>  
  
## <a name="volume-shadow-copy-service"></a><span data-ttu-id="c7973-112">Servicio de instantáneas de volumen</span><span class="sxs-lookup"><span data-stu-id="c7973-112">Volume Shadow Copy Service</span></span>  
 <span data-ttu-id="c7973-113">VSS es un conjunto de API COM que implementa un marco para permitir la realización de copias de seguridad de volumen mientras las aplicaciones de un sistema siguen escribiendo en los volúmenes.</span><span class="sxs-lookup"><span data-stu-id="c7973-113">The VSS is a set of COM APIs that implements a framework to allow volume backups to be performed while applications on a system continue to write to the volumes.</span></span> <span data-ttu-id="c7973-114">VSS proporciona una interfaz coherente que permite la coordinación entre las aplicaciones de usuario que actualizan los datos del disco (objetos de escritura) y los que realizan copias de seguridad de las aplicaciones (solicitantes).</span><span class="sxs-lookup"><span data-stu-id="c7973-114">The VSS provides a consistent interface that allows coordination between user applications that update data on disk (writers) and those that back up applications (requestors).</span></span>  
  
 <span data-ttu-id="c7973-115">VSS captura y copia imágenes estables para la creación de copias de seguridad en sistemas en ejecución, especialmente servidores, sin degradar innecesariamente el rendimiento y la estabilidad de los servicios que proporcionan.</span><span class="sxs-lookup"><span data-stu-id="c7973-115">The VSS captures and copies stable images for backup on running systems, particularly servers, without unduly degrading the performance and stability of the services they provide.</span></span> <span data-ttu-id="c7973-116">Para obtener más información acerca de VSS, vea la documentación de Windows.</span><span class="sxs-lookup"><span data-stu-id="c7973-116">For more information on the VSS, see your Windows documentation.</span></span>  
  
## <a name="virtual-backup-device-interface-vdi"></a><span data-ttu-id="c7973-117">Interfaz del dispositivo de copia de seguridad virtual (VDI)</span><span class="sxs-lookup"><span data-stu-id="c7973-117">Virtual Backup Device Interface (VDI)</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c7973-118">ofrece una API denominada interfaz del dispositivo de copia de seguridad virtual (VDI) que permite a los proveedores de software independientes integrar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en sus productos para ofrecer la compatibilidad con las operaciones relativas a las copias de seguridad y restauración.</span><span class="sxs-lookup"><span data-stu-id="c7973-118">provides an API called Virtual Backup Device Interface (VDI) that enables independent software vendors to integrate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] into their products for providing support for backup and restore operations.</span></span> <span data-ttu-id="c7973-119">Estas API están diseñadas para ofrecer una confiabilidad y rendimiento máximos, así como para ser compatibles con todas las funciones relativas a las copias de seguridad y restauración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , incluidas todas las capacidades de copias de seguridad interactivas y de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="c7973-119">These APIs are engineered to provide maximum reliability and performance, and support the full range of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup and restore functionality, including the full range of hot and snapshot backup capabilities.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="c7973-120">Permisos</span><span class="sxs-lookup"><span data-stu-id="c7973-120">Permissions</span></span>  
 <span data-ttu-id="c7973-121">El servicio del objeto de escritura de SQL debe ejecutarse en la cuenta **Sistema local** .</span><span class="sxs-lookup"><span data-stu-id="c7973-121">The SQL Writer service must run under the **Local System** account.</span></span> <span data-ttu-id="c7973-122">El servicio del objeto de escritura de SQL usa el inicio de sesión **NT Service\SQLWriter** para conectarse a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7973-122">The SQL Writer service uses the **NT Service\SQLWriter** login to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c7973-123">El uso del inicio de sesión **NT Service\SQLWriter** permite que el proceso del objeto de escritura de SQL se ejecute en un nivel de privilegios menor en una cuenta designada como **ningún inicio de sesión**, lo que limita la vulnerabilidad.</span><span class="sxs-lookup"><span data-stu-id="c7973-123">Using the **NT Service\SQLWriter** login allows the SQL Writer process to run at a lower privilege level in an account designated as **no login**, which limits vulnerability.</span></span> <span data-ttu-id="c7973-124">Si el servicio del objeto de escritura de SQL está deshabilitado, cualquier utilidad que emplee instantáneas de VSS, como System Center Data Protection Manager, así como otros productos de terceros, dejaría de funcionar, o lo que es peor, con el riesgo de realizar copias de seguridad de bases de datos que no fueran coherentes.</span><span class="sxs-lookup"><span data-stu-id="c7973-124">If the SQL Writer service is disabled, then any utility which in relies on VSS snapshots, such as System Center Data Protection Manager, as well as some other 3rd-party products, would be broken, or worse, at risk of taking backups of databases which were not consistent.</span></span> <span data-ttu-id="c7973-125">Si ni [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], el sistema en el que se ejecuta o el sistema host (en el caso de una máquina virtual) necesitan usar otra cosa que no sea la copia de seguridad de [!INCLUDE[tsql](../../includes/tsql-md.md)] , se puede deshabilitar el servicio del objeto de escritura de SQL y quitar el inicio de sesión de forma segura.</span><span class="sxs-lookup"><span data-stu-id="c7973-125">If neither [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the system it runs on, nor the host system (in the event of a virtual machine), need to use anything besides [!INCLUDE[tsql](../../includes/tsql-md.md)] backup, then the SQL Writer service can be safely disabled and the login removed.</span></span>  <span data-ttu-id="c7973-126">Tenga en cuenta que una copia de seguridad de nivel del sistema o de volumen puede invocar el servicio del objeto de escritura de SQL, tanto si la copia de seguridad se basa directamente en instantáneas como si no.</span><span class="sxs-lookup"><span data-stu-id="c7973-126">Note that the SQL Writer service may be invoked by a system or volume level backup, whether the backup is directly snapshot-based or not.</span></span> <span data-ttu-id="c7973-127">Algunos productos de copia de seguridad del sistema usan VSS para evitar quedar bloqueados por archivos abiertos o bloqueados.</span><span class="sxs-lookup"><span data-stu-id="c7973-127">Some system backup products use VSS to avoid being blocked by open or locked files.</span></span> <span data-ttu-id="c7973-128">El Servicio del objeto de escritura de SQL necesita permisos elevados en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] porque en el transcurso de sus actividades inmoviliza brevemente toda la E/S para la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7973-128">The SQL Writer service needs elevated permissions in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] because in the course of its activities it briefly freezes all I/O for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="features"></a><span data-ttu-id="c7973-129">Características</span><span class="sxs-lookup"><span data-stu-id="c7973-129">Features</span></span>  
 <span data-ttu-id="c7973-130">El objeto de escritura de SQL es compatible con las operaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="c7973-130">SQL Writer supports:</span></span>  
  
-   <span data-ttu-id="c7973-131">Copias de seguridad y restauración completas de la base de datos, incluidos los catálogos de texto completo</span><span class="sxs-lookup"><span data-stu-id="c7973-131">Full database backup and restore including full-text catalogs</span></span>  
  
-   <span data-ttu-id="c7973-132">Copias de seguridad y restauración diferenciales</span><span class="sxs-lookup"><span data-stu-id="c7973-132">Differential backup and restore</span></span>  
  
-   <span data-ttu-id="c7973-133">Restauración con desplazamiento</span><span class="sxs-lookup"><span data-stu-id="c7973-133">Restore with move</span></span>  
  
-   <span data-ttu-id="c7973-134">Cambio de nombre de una base de datos</span><span class="sxs-lookup"><span data-stu-id="c7973-134">Database rename</span></span>  
  
-   <span data-ttu-id="c7973-135">Copia de seguridad de solo copia</span><span class="sxs-lookup"><span data-stu-id="c7973-135">Copy-only backup</span></span>  
  
-   <span data-ttu-id="c7973-136">Recuperación automática de instantánea de base de datos</span><span class="sxs-lookup"><span data-stu-id="c7973-136">Auto-recovery of database snapshot</span></span>  
  
 <span data-ttu-id="c7973-137">El objeto de escritura de SQL no es compatible con las operaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="c7973-137">SQL Writer does not support:</span></span>  
  
-   <span data-ttu-id="c7973-138">Copias de seguridad de registros</span><span class="sxs-lookup"><span data-stu-id="c7973-138">Log backups</span></span>  
  
-   <span data-ttu-id="c7973-139">Copia de seguridad de archivos y grupos de archivos</span><span class="sxs-lookup"><span data-stu-id="c7973-139">File and filegroup backup</span></span>  
  
-   <span data-ttu-id="c7973-140">Restauración de página</span><span class="sxs-lookup"><span data-stu-id="c7973-140">Page restore</span></span>  
  
  
