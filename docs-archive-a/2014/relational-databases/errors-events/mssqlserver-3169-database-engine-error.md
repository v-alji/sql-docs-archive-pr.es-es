---
title: MSSQLSERVER_3169 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "3169"
helpviewer_keywords:
- 3169 (Database Engine error)
ms.assetid: 7d4dbed6-bb94-4908-bc03-2040a9cf63bc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8b13d9c1c17eddb34648bc4a536e2fccf371b99a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673017"
---
# <a name="mssqlserver_3169"></a><span data-ttu-id="d0028-102">MSSQLSERVER_3169</span><span class="sxs-lookup"><span data-stu-id="d0028-102">MSSQLSERVER_3169</span></span>
    
## <a name="details"></a><span data-ttu-id="d0028-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="d0028-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d0028-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="d0028-104">Product Name</span></span>|<span data-ttu-id="d0028-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d0028-105">SQL Server</span></span>|  
|<span data-ttu-id="d0028-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="d0028-106">Event ID</span></span>|<span data-ttu-id="d0028-107">3169</span><span class="sxs-lookup"><span data-stu-id="d0028-107">3169</span></span>|  
|<span data-ttu-id="d0028-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="d0028-108">Event Source</span></span>|<span data-ttu-id="d0028-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d0028-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d0028-110">Componente</span><span class="sxs-lookup"><span data-stu-id="d0028-110">Component</span></span>|<span data-ttu-id="d0028-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d0028-111">SQLEngine</span></span>|  
|<span data-ttu-id="d0028-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="d0028-112">Symbolic Name</span></span>|<span data-ttu-id="d0028-113">N/D</span><span class="sxs-lookup"><span data-stu-id="d0028-113">NA</span></span>|  
|<span data-ttu-id="d0028-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="d0028-114">Message Text</span></span>|<span data-ttu-id="d0028-115">Se realizó una copia de seguridad de la base de datos en una versión de servidor %ls.</span><span class="sxs-lookup"><span data-stu-id="d0028-115">The database was backed up on a server running version %ls.</span></span> <span data-ttu-id="d0028-116">Esta versión no es compatible con este servidor, que utiliza la versión %ls.</span><span class="sxs-lookup"><span data-stu-id="d0028-116">That version is incompatible with this server, which is running version %ls.</span></span> <span data-ttu-id="d0028-117">Restaure la base de datos en un servidor que admita la copia de seguridad, o utilice una copia de seguridad que sea compatible con este servidor.</span><span class="sxs-lookup"><span data-stu-id="d0028-117">Either restore the database on a server that supports the backup, or use a backup that is compatible with this server.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d0028-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="d0028-118">Explanation</span></span>  
 <span data-ttu-id="d0028-119">Algunas características de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] afectan a la estructura de los archivos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="d0028-119">Certain features in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] affect the structure of the database files.</span></span> <span data-ttu-id="d0028-120">Al restaurar la base de datos en otra instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], es posible que el formato de archivo no sea compatible con una versión distinta de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d0028-120">When you restore a database to another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the file format might not be compatible with a different version of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
 <span data-ttu-id="d0028-121">Por ejemplo, este error puede deberse al uso del formato de almacenamiento vardecimal en una versión posterior de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y a un intento posterior de restaurar los archivos de base de datos a una versión anterior al Service Pack 2 de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d0028-121">For example, this error can be caused by using the vardecimalstorage format in a later version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and then trying to restore the database files in a version earlier than [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 2.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d0028-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="d0028-122">User Action</span></span>  
 <span data-ttu-id="d0028-123">Determine la versión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que está ejecutándose en el servidor de origen.</span><span class="sxs-lookup"><span data-stu-id="d0028-123">Determine the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is running on the originating server.</span></span> <span data-ttu-id="d0028-124">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , haga clic con el botón secundario en el servidor y, a continuación, haga clic en **propiedades** o escriba `SELECT @@VERSION` en una ventana de consulta.</span><span class="sxs-lookup"><span data-stu-id="d0028-124">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], either right-click the server and then click **Properties** or type `SELECT @@VERSION` in a query window.</span></span> <span data-ttu-id="d0028-125">Abra la base de datos utilizando la versión original de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d0028-125">Open the database by using the original version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d0028-126">Examine las características que están habilitadas en la base de datos original en la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d0028-126">Investigate the features that are enabled on the original database in the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d0028-127">Modifique esta configuración para trabajar con la versión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] donde se restaurará la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d0028-127">Modify these settings to work with the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in which the database will be restored.</span></span>  
  
  
