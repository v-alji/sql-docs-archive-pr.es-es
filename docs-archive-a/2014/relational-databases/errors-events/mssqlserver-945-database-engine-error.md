---
title: MSSQLSERVER_945 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 945 (Database Engine error)
ms.assetid: ee501d13-0bd9-4627-896c-ed5b1bdb88b3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 51284cdcf48f1bf713a853f9c87457cb5291cc4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672033"
---
# <a name="mssqlserver_945"></a><span data-ttu-id="deb44-102">MSSQLSERVER_945</span><span class="sxs-lookup"><span data-stu-id="deb44-102">MSSQLSERVER_945</span></span>
    
## <a name="details"></a><span data-ttu-id="deb44-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="deb44-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="deb44-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="deb44-104">Product Name</span></span>|<span data-ttu-id="deb44-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="deb44-105">SQL Server</span></span>|  
|<span data-ttu-id="deb44-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="deb44-106">Event ID</span></span>|<span data-ttu-id="deb44-107">945</span><span class="sxs-lookup"><span data-stu-id="deb44-107">945</span></span>|  
|<span data-ttu-id="deb44-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="deb44-108">Event Source</span></span>|<span data-ttu-id="deb44-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="deb44-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="deb44-110">Componente</span><span class="sxs-lookup"><span data-stu-id="deb44-110">Component</span></span>|<span data-ttu-id="deb44-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="deb44-111">SQLEngine</span></span>|  
|<span data-ttu-id="deb44-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="deb44-112">Symbolic Name</span></span>|<span data-ttu-id="deb44-113">DB_IS_SHUTDOWN</span><span class="sxs-lookup"><span data-stu-id="deb44-113">DB_IS_SHUTDOWN</span></span>|  
|<span data-ttu-id="deb44-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="deb44-114">Message Text</span></span>|<span data-ttu-id="deb44-115">No se puede abrir la base de datos '%.\*ls', porque no es posible tener acceso a archivos, o la memoria o el espacio en disco son insuficientes.</span><span class="sxs-lookup"><span data-stu-id="deb44-115">Database '%.\*ls' cannot be opened due to inaccessible files or insufficient memory or disk space.</span></span>  <span data-ttu-id="deb44-116">Compruebe el registro de errores de SQL Server para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="deb44-116">See the SQL Server error log for details.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="deb44-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="deb44-117">Explanation</span></span>  
 <span data-ttu-id="deb44-118">No se pudo obtener acceso a la base de datos porque faltan archivos u otros recursos.</span><span class="sxs-lookup"><span data-stu-id="deb44-118">The database could not be accessed because files or other resources are missing.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="deb44-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="deb44-119">User Action</span></span>  
 <span data-ttu-id="deb44-120">Compruebe el registro de errores para obtener información adicional acerca del error de memoria, espacio en disco o permiso.</span><span class="sxs-lookup"><span data-stu-id="deb44-120">Check the error log for additional information about memory, disk space, or permission failure.</span></span> <span data-ttu-id="deb44-121">Confirme la ubicación de los archivos .mdf y .ndf de la base de datos afectada y confirme que la cuenta usada por [!INCLUDE[ssDE](../../includes/ssde-md.md)] tiene permiso de acceso a esos archivos.</span><span class="sxs-lookup"><span data-stu-id="deb44-121">Confirm the location of the .mdf and .ndf files for the affected database and confirm that the account used by the [!INCLUDE[ssDE](../../includes/ssde-md.md)] has permission to access those files.</span></span> <span data-ttu-id="deb44-122">Después de corregir el problema, reinicie la base de datos usando ALTER DATABASE para establecerla en ONLINE.</span><span class="sxs-lookup"><span data-stu-id="deb44-122">After correcting the problem, restart the database by using ALTER DATABASE to set it ONLINE.</span></span>  
  
  
