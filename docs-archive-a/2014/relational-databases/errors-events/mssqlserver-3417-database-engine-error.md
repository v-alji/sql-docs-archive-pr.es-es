---
title: MSSQLSERVER_3417 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3417 (Database Engine error)
ms.assetid: 005829c8-cf57-4828-818a-bbe8ee2e00f0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 680e5a4266c7d0d9aaacb7b3deb9525a002077e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675893"
---
# <a name="mssqlserver_3417"></a><span data-ttu-id="2fa78-102">MSSQLSERVER_3417</span><span class="sxs-lookup"><span data-stu-id="2fa78-102">MSSQLSERVER_3417</span></span>
    
## <a name="details"></a><span data-ttu-id="2fa78-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="2fa78-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2fa78-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="2fa78-104">Product Name</span></span>|<span data-ttu-id="2fa78-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2fa78-105">SQL Server</span></span>|  
|<span data-ttu-id="2fa78-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="2fa78-106">Event ID</span></span>|<span data-ttu-id="2fa78-107">3417</span><span class="sxs-lookup"><span data-stu-id="2fa78-107">3417</span></span>|  
|<span data-ttu-id="2fa78-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="2fa78-108">Event Source</span></span>|<span data-ttu-id="2fa78-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2fa78-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2fa78-110">Componente</span><span class="sxs-lookup"><span data-stu-id="2fa78-110">Component</span></span>|<span data-ttu-id="2fa78-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="2fa78-111">SQLEngine</span></span>|  
|<span data-ttu-id="2fa78-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="2fa78-112">Symbolic Name</span></span>|<span data-ttu-id="2fa78-113">REC_BADMASTER</span><span class="sxs-lookup"><span data-stu-id="2fa78-113">REC_BADMASTER</span></span>|  
|<span data-ttu-id="2fa78-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="2fa78-114">Message Text</span></span>|<span data-ttu-id="2fa78-115">No se puede recuperar la base de datos maestra.</span><span class="sxs-lookup"><span data-stu-id="2fa78-115">Cannot recover the master database.</span></span> <span data-ttu-id="2fa78-116">SQL Server no se puede ejecutar.</span><span class="sxs-lookup"><span data-stu-id="2fa78-116">SQL Server is unable to run.</span></span> <span data-ttu-id="2fa78-117">Restaure la base de datos maestra desde una copia de seguridad completa, repárela o vuelva a crearla.</span><span class="sxs-lookup"><span data-stu-id="2fa78-117">Restore master from a full backup, repair it, or rebuild it.</span></span> <span data-ttu-id="2fa78-118">Para obtener más información acerca de cómo volver a crear la base de datos maestra, vea los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2fa78-118">For more information about how to rebuild the master database, see SQL Server Books Online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2fa78-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="2fa78-119">Explanation</span></span>  
 <span data-ttu-id="2fa78-120">SQL Server no puede iniciar la base de datos **master**.</span><span class="sxs-lookup"><span data-stu-id="2fa78-120">SQL Server cannot start the **master** database.</span></span> <span data-ttu-id="2fa78-121">Si no se pueden poner en línea **master** o **tempdb**, SQL Server no puede ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="2fa78-121">If the **master** or **tempdb** cannot be brought online, SQL Server cannot run.</span></span> <span data-ttu-id="2fa78-122">Este error suele ir precedido de otros errores.</span><span class="sxs-lookup"><span data-stu-id="2fa78-122">This error is usually preceded by other errors.</span></span> <span data-ttu-id="2fa78-123">Revise los registros de errores para localizar el motivo original.</span><span class="sxs-lookup"><span data-stu-id="2fa78-123">Review error logs to find the root cause.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2fa78-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="2fa78-124">User Action</span></span>  
 <span data-ttu-id="2fa78-125">Restaure la copia de seguridad de la base de datos o repare la base de datos.</span><span class="sxs-lookup"><span data-stu-id="2fa78-125">Restore backup of the database or repair the database.</span></span>  
  
  
