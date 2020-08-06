---
title: MSSQLSERVER_948 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "948"
helpviewer_keywords:
- 948 (Database Engine error)
ms.assetid: 95c4ad45-a518-4165-a5c4-6e6b932b0570
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e8461069a3fceb7bdca318b82a522f7f51af83d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672031"
---
# <a name="mssqlserver_948"></a><span data-ttu-id="eda6f-102">MSSQLSERVER_948</span><span class="sxs-lookup"><span data-stu-id="eda6f-102">MSSQLSERVER_948</span></span>
    
## <a name="details"></a><span data-ttu-id="eda6f-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="eda6f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="eda6f-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="eda6f-104">Product Name</span></span>|<span data-ttu-id="eda6f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="eda6f-105">SQL Server</span></span>|  
|<span data-ttu-id="eda6f-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="eda6f-106">Event ID</span></span>|<span data-ttu-id="eda6f-107">948</span><span class="sxs-lookup"><span data-stu-id="eda6f-107">948</span></span>|  
|<span data-ttu-id="eda6f-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="eda6f-108">Event Source</span></span>|<span data-ttu-id="eda6f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="eda6f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="eda6f-110">Componente</span><span class="sxs-lookup"><span data-stu-id="eda6f-110">Component</span></span>|<span data-ttu-id="eda6f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="eda6f-111">SQLEngine</span></span>|  
|<span data-ttu-id="eda6f-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="eda6f-112">Symbolic Name</span></span>|<span data-ttu-id="eda6f-113">N/D</span><span class="sxs-lookup"><span data-stu-id="eda6f-113">NA</span></span>|  
|<span data-ttu-id="eda6f-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="eda6f-114">Message Text</span></span>|<span data-ttu-id="eda6f-115">No se puede abrir la base de datos "%.\*ls" por tener la versión %d.</span><span class="sxs-lookup"><span data-stu-id="eda6f-115">The database '%.\*ls' cannot be opened because it is version %d.</span></span> <span data-ttu-id="eda6f-116">Este servidor es compatible con la versión %d y anteriores.</span><span class="sxs-lookup"><span data-stu-id="eda6f-116">This server supports version %d and earlier.</span></span> <span data-ttu-id="eda6f-117">No se admite esta ruta de actualización.</span><span class="sxs-lookup"><span data-stu-id="eda6f-117">A downgrade path is not supported.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="eda6f-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="eda6f-118">Explanation</span></span>  
 <span data-ttu-id="eda6f-119">Algunas características de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] afectan a la estructura de los archivos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="eda6f-119">Certain features in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] affect the structure of the database files.</span></span> <span data-ttu-id="eda6f-120">Al adjuntar una base de datos a otra instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], es posible que el formato de archivo no sea compatible con una versión distinta de [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eda6f-120">When you attach a database to another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the file format might not be compatible with a different version of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="eda6f-121">Por ejemplo, este error puede deberse al uso del formato de almacenamiento vardecimal en una versión posterior de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y a un intento posterior de adjuntar los archivos de base de datos a una versión anterior al Service Pack 2 de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eda6f-121">For example, this error can be caused by using the vardecimal storage format in a later version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and then trying to attach the database files in a version earlier than [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 2.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="eda6f-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="eda6f-122">User Action</span></span>  
 <span data-ttu-id="eda6f-123">Determine la versión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que está ejecutándose en el servidor de origen.</span><span class="sxs-lookup"><span data-stu-id="eda6f-123">Determine the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is running on the originating server.</span></span> <span data-ttu-id="eda6f-124">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , haga clic con el botón secundario en el servidor y, a continuación, haga clic en **propiedades** o escriba `SELECT @@VERSION` en una ventana de consulta.</span><span class="sxs-lookup"><span data-stu-id="eda6f-124">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], either right-click the server and then click **Properties** or type `SELECT @@VERSION` in a query window.</span></span> <span data-ttu-id="eda6f-125">Abra la base de datos utilizando la versión original de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eda6f-125">Open the database by using the original version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="eda6f-126">Examine las características que están habilitadas en la base de datos original en la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eda6f-126">Investigate the features that are enabled on the original database in the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="eda6f-127">Modifique esta configuración para trabajar con la versión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] donde se adjuntará la base de datos.</span><span class="sxs-lookup"><span data-stu-id="eda6f-127">Modify these settings to work with the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in which the database will be attached.</span></span>  
  
  
