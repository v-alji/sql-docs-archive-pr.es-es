---
title: Determinar si el motor de base de datos está instalado y se ha iniciado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- SQL Server, determining if installed
- verifying Database Engine installation
- viewing Database Engine installation
- installed Database Engine verification [SQL Server]
ms.assetid: babb02e4-3521-4b75-b5df-e09205594375
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0a912cf4a89f208543605cc84f480b63955214ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749469"
---
# <a name="determine-whether-the-database-engine-is-installed-and-started"></a><span data-ttu-id="604a9-102">Determinar si el motor de base de datos está instalado y se ha iniciado</span><span class="sxs-lookup"><span data-stu-id="604a9-102">Determine Whether the Database Engine Is Installed and Started</span></span>
  <span data-ttu-id="604a9-103">En una instalación correcta de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] se instalan archivos en el sistema de archivos, se crean entradas en el Registro y se instalan varias herramientas.</span><span class="sxs-lookup"><span data-stu-id="604a9-103">A successful installation of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] installs files to the file system, creates entries in the registry, and installs several tools.</span></span> <span data-ttu-id="604a9-104">En este tema se describe cómo determinar si el [!INCLUDE[ssDE](../../includes/ssde-md.md)] se instala e inicia en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="604a9-104">This topic describes how to determine whether the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is installed and started in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="604a9-105">Usar el Administrador de configuración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="604a9-105">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="how-to-view-and-start-the-database-engine-by-using-sql-server-configuration-manager"></a><span data-ttu-id="604a9-106">Cómo ver e iniciar el motor de base de datos con el Administrador de configuración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="604a9-106">How to view and start the Database Engine by using SQL Server Configuration Manager</span></span>  
  
1.  <span data-ttu-id="604a9-107">En el menú **Inicio**, seleccione **Todos los programas**, **Microsoft SQL Server**, **Herramientas de configuración**y, finalmente, **Administrador de configuración de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="604a9-107">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
     <span data-ttu-id="604a9-108">Si no tiene estas entradas en el menú **Inicio** , [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no está instalado correctamente.</span><span class="sxs-lookup"><span data-stu-id="604a9-108">If you do not have these entries on the **Start** menu, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not correctly installed.</span></span> <span data-ttu-id="604a9-109">Ejecute el programa de instalación para instalar [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="604a9-109">Run Setup to install the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="604a9-110">En el panel izquierdo del **Administrador de configuración de SQL Server**, haga clic en **Servicios de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="604a9-110">In **SQL Server Configuration Manager**, on the left pane, click **SQL Server Services**.</span></span> <span data-ttu-id="604a9-111">En el panel derecho se muestran varios servicios que están relacionados con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="604a9-111">The right pane lists several services that are related to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="604a9-112">Si [!INCLUDE[ssDE](../../includes/ssde-md.md)] está instalado, el servicio [!INCLUDE[ssDE](../../includes/ssde-md.md)] aparece como **SQL Server (MSSQLSERVER)** si se trata de la instancia predeterminada, o bien como **SQL Server (** \<*instance_name*> **)** , si [!INCLUDE[ssDE](../../includes/ssde-md.md)] está instalado como una instancia con nombre.</span><span class="sxs-lookup"><span data-stu-id="604a9-112">If the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is installed, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] service is listed as **SQL Server (MSSQLSERVER)** if it is the default instance; or **SQL Server (**\<*instance_name*>**)**, if the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is installed as a named instance.</span></span> <span data-ttu-id="604a9-113">A menos que se cambie el nombre de la instancia, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] se instala como una instancia con nombre y con el nombre **SQLEXPRESS**.</span><span class="sxs-lookup"><span data-stu-id="604a9-113">Unless the instance name is changed, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] installs as a named instance with the name **SQLEXPRESS**.</span></span> <span data-ttu-id="604a9-114">Un icono con un triángulo verde indica que [!INCLUDE[ssDE](../../includes/ssde-md.md)] se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="604a9-114">A green triangle icon indicates that the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is running.</span></span> <span data-ttu-id="604a9-115">Un icono con un cuadrado rojo indica que [!INCLUDE[ssDE](../../includes/ssde-md.md)] está detenido.</span><span class="sxs-lookup"><span data-stu-id="604a9-115">A red square icon indicates that the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is stopped.</span></span>  
  
3.  <span data-ttu-id="604a9-116">Para iniciar [!INCLUDE[ssDE](../../includes/ssde-md.md)], en el panel derecho, haga clic con el botón derecho en [!INCLUDE[ssDE](../../includes/ssde-md.md)]y haga clic en **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="604a9-116">To start the [!INCLUDE[ssDE](../../includes/ssde-md.md)], in the right pane, right-click the [!INCLUDE[ssDE](../../includes/ssde-md.md)], and then click **Start**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="604a9-117">Durante la instalación, el usuario puede seleccionar una ubicación en la que instalar los archivos de programa y de base de datos.</span><span class="sxs-lookup"><span data-stu-id="604a9-117">During setup, the user can select a location in which to install the program files and the database files.</span></span> <span data-ttu-id="604a9-118">Si el usuario acepta la ubicación predeterminada, los archivos se instalan en [!INCLUDE[ssInstallPath](../../includes/ssinstallpath-md.md)] y C:\Archivos de programa\Microsoft SQL Server\MSSQL.*x*, donde *x* es un número.</span><span class="sxs-lookup"><span data-stu-id="604a9-118">If the user accepts the default location, the files are installed to [!INCLUDE[ssInstallPath](../../includes/ssinstallpath-md.md)] and C:\Program Files\Microsoft SQL Server\MSSQL.*x*, where *x* is a number.</span></span>  
  
  
