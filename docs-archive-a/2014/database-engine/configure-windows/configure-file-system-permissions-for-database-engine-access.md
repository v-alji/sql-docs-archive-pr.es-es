---
title: Configurar permisos del sistema de archivos para el acceso al motor de base de datos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- file system permissions
- service account [SQL Server], file system permissions
- permissions [SQL Server], file system
ms.assetid: 78bba43c-4edb-4216-84ac-d6246ae5546d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1d9abbd095f2d5be7415ed28a17fb710ff8ab504
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677888"
---
# <a name="configure-file-system-permissions-for-database-engine-access"></a><span data-ttu-id="9a843-102">Configurar permisos del sistema de archivos para el acceso al motor de base de datos</span><span class="sxs-lookup"><span data-stu-id="9a843-102">Configure File System Permissions for Database Engine Access</span></span>
  <span data-ttu-id="9a843-103">En este tema se describe cómo conceder a [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]acceso al sistema de archivos de la ubicación donde se almacenan los archivos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="9a843-103">This topic describes how to grant the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], file system access to the location where database files are stored.</span></span> <span data-ttu-id="9a843-104">El servicio [!INCLUDE[ssDE](../../includes/ssde-md.md)] debe tener permiso del sistema de archivos de Windows para obtener acceso a la carpeta de archivos donde se almacenan los archivos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="9a843-104">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] service must have permission of the Windows file system to access the file folder where database files are stored.</span></span> <span data-ttu-id="9a843-105">El permiso para tener acceso a la ubicación predeterminada se configura durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="9a843-105">Permission to the default location is configured during setup.</span></span> <span data-ttu-id="9a843-106">Si coloca los archivos de base de datos en una ubicación diferente, es posible que tenga que seguir estos pasos para conceder a [!INCLUDE[ssDE](../../includes/ssde-md.md)] permisos de control total a dicha ubicación.</span><span class="sxs-lookup"><span data-stu-id="9a843-106">If you place your database files in a different location, you might need to follow these steps to grant the [!INCLUDE[ssDE](../../includes/ssde-md.md)] the full control permission to that location.</span></span>  
  
 <span data-ttu-id="9a843-107">A partir de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , se asignan permisos al SID por servicio para cada uno de sus servicios.</span><span class="sxs-lookup"><span data-stu-id="9a843-107">Beginning with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] permissions are assigned to the per-service SID for each of its services.</span></span> <span data-ttu-id="9a843-108">Este sistema ayuda a conseguir el aislamiento del servicio y una defensa optimizada.</span><span class="sxs-lookup"><span data-stu-id="9a843-108">This system helps provide service isolation and defense in depth.</span></span> <span data-ttu-id="9a843-109">El SID por servicio se deriva del nombre del servicio y es único para cada servicio.</span><span class="sxs-lookup"><span data-stu-id="9a843-109">The per-service SID is derived from the service name and is unique to each service.</span></span> <span data-ttu-id="9a843-110">El tema [Configurar los permisos y las cuentas de servicio de Windows](configure-windows-service-accounts-and-permissions.md) describe el SID por servicio y proporciona los nombres en la sección **Derechos y privilegios de Windows**.</span><span class="sxs-lookup"><span data-stu-id="9a843-110">The topic [Configure Windows Service Accounts and Permissions](configure-windows-service-accounts-and-permissions.md) describes the per-service SID and provides the names in the section **Windows Privileges and Rights**.</span></span> <span data-ttu-id="9a843-111">El permiso de acceso en la ubicación de los archivos se debe asignar al SID por servicio.</span><span class="sxs-lookup"><span data-stu-id="9a843-111">It is the per-service SID that must be assigned the access permission on the file location.</span></span>  
  
## <a name="to-grant-file-system-permission-to-the-per-service-sid"></a><span data-ttu-id="9a843-112">Para conceder permisos del sistema de archivos al SID por servicio</span><span class="sxs-lookup"><span data-stu-id="9a843-112">To Grant File System Permission to the Per-service SID</span></span>  
  
1.  <span data-ttu-id="9a843-113">Utilice el Explorador de Windows para navegar a la ubicación del sistema de archivos donde se almacenan los archivos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="9a843-113">Using Windows Explorer, navigate to the file system location where the database files are stored.</span></span> <span data-ttu-id="9a843-114">Haga clic con el botón derecho en la carpeta del sistema de archivos y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="9a843-114">Right-click the file system folder, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="9a843-115">Haga clic en la pestaña **Seguridad** , haga clic en **Editar**y, a continuación, en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="9a843-115">On the **Security** tab, click **Edit**, and then **Add**.</span></span>  
  
3.  <span data-ttu-id="9a843-116">En el cuadro de diálogo **Seleccionar usuarios, equipos, cuentas de servicio o grupos** , haga clic en **Ubicaciones**, seleccione el nombre del equipo en la parte superior de la lista de ubicaciones y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9a843-116">In the **Select Users, Computer, Service Account, or Groups** dialog box, click **Locations**, at the top of the location list, select your computer name, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="9a843-117">En el cuadro **Escriba los nombres de objeto que desea seleccionar** , escriba el nombre del SID por servicio que aparece en el tema de los libros en pantalla **configurar los permisos y las cuentas de servicio de Windows**.</span><span class="sxs-lookup"><span data-stu-id="9a843-117">In the **Enter the object names to select** box, type the name of the per-service SID listed in the Books Online topic **Configure Windows Service Accounts and Permissions**.</span></span> <span data-ttu-id="9a843-118">(Para el [!INCLUDE[ssDE](../../includes/ssde-md.md)] SID por servicio, use **NT SERVICE\MSSQLSERVER** para una instancia predeterminada o **NT SERVICE\MSSQL $ InstanceName** para una instancia con nombre).</span><span class="sxs-lookup"><span data-stu-id="9a843-118">(For the [!INCLUDE[ssDE](../../includes/ssde-md.md)] per service SID, use **NT SERVICE\MSSQLSERVER** for a default instance, or **NT SERVICE\MSSQL$InstanceName** for a named instance.)</span></span>  
  
5.  <span data-ttu-id="9a843-119">Para validar la entrada, haga clic en **Comprobar nombres** .</span><span class="sxs-lookup"><span data-stu-id="9a843-119">Click **Check Names** to validate the entry.</span></span> <span data-ttu-id="9a843-120">A menudo, se produce un error en la validación, y es posible que aparezca un mensaje indicando que no se encontró el nombre.</span><span class="sxs-lookup"><span data-stu-id="9a843-120">The validation often fails, and might advise you that the name was not found.</span></span> <span data-ttu-id="9a843-121">Al hacer clic en **Aceptar**, aparece un cuadro de diálogo **Se encontraron varios nombres** .</span><span class="sxs-lookup"><span data-stu-id="9a843-121">When you click **OK**, a **Multiple Names Found** dialog box appears.</span></span>  
  
6.  <span data-ttu-id="9a843-122">Ahora seleccione el SID por servicio, **MSSQLSERVER** o **NT SERVICE\MSSQL $ InstanceName**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9a843-122">Now select the per-service SID, either **MSSQLSERVER** or **NT SERVICE\MSSQL$InstanceName**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="9a843-123">Vuelva a hacer clic en **Aceptar** para volver al cuadro de diálogo **permisos** .</span><span class="sxs-lookup"><span data-stu-id="9a843-123">Click **OK** again to return to the **Permissions** dialog box.</span></span>  
  
8.  <span data-ttu-id="9a843-124">En el cuadro nombres de **grupos o usuarios** , seleccione el SID por servicio y, a continuación, en el cuadro **permisos para** \<name> , active la casilla **permitir** para **control total**.</span><span class="sxs-lookup"><span data-stu-id="9a843-124">In the **Group or user** names box, select the per-service SID, and then in the **Permissions for** \<name> box, select the **Allow** check box for **Full control**.</span></span>  
  
9. <span data-ttu-id="9a843-125">Haga clic en **Aplicar**y, a continuación, haga clic dos veces en **Aceptar** para salir.</span><span class="sxs-lookup"><span data-stu-id="9a843-125">Click **Apply**, and then click **OK** twice to exit.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a843-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9a843-126">See Also</span></span>  
 <span data-ttu-id="9a843-127">[Administrar el servicio del motor de base de datos](manage-the-database-engine-services.md) </span><span class="sxs-lookup"><span data-stu-id="9a843-127">[Manage the Database Engine Services](manage-the-database-engine-services.md) </span></span>  
 <span data-ttu-id="9a843-128">[Mover bases de datos del sistema](../../relational-databases/databases/system-databases.md) </span><span class="sxs-lookup"><span data-stu-id="9a843-128">[Move System Databases](../../relational-databases/databases/system-databases.md) </span></span>  
 [<span data-ttu-id="9a843-129">Mover bases de datos de usuario</span><span class="sxs-lookup"><span data-stu-id="9a843-129">Move User Databases</span></span>](../../relational-databases/databases/move-user-databases.md)  
  
  
