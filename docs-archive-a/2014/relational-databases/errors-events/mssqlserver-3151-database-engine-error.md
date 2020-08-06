---
title: MSSQLSERVER_3151 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3151 (Database Engine error)
ms.assetid: a8657a91-ec75-4649-a09a-21920e0030ff
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c34414754ea9d25ad89f6aba767197eb1dfc10d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673023"
---
# <a name="mssqlserver_3151"></a><span data-ttu-id="1f551-102">MSSQLSERVER_3151</span><span class="sxs-lookup"><span data-stu-id="1f551-102">MSSQLSERVER_3151</span></span>
    
## <a name="details"></a><span data-ttu-id="1f551-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="1f551-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1f551-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="1f551-104">Product Name</span></span>|<span data-ttu-id="1f551-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1f551-105">SQL Server</span></span>|  
|<span data-ttu-id="1f551-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="1f551-106">Event ID</span></span>|<span data-ttu-id="1f551-107">3151</span><span class="sxs-lookup"><span data-stu-id="1f551-107">3151</span></span>|  
|<span data-ttu-id="1f551-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="1f551-108">Event Source</span></span>|<span data-ttu-id="1f551-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1f551-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1f551-110">Componente</span><span class="sxs-lookup"><span data-stu-id="1f551-110">Component</span></span>|<span data-ttu-id="1f551-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="1f551-111">SQLEngine</span></span>|  
|<span data-ttu-id="1f551-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="1f551-112">Symbolic Name</span></span>|<span data-ttu-id="1f551-113">LDDB_MASTER_LOAD_FAILED</span><span class="sxs-lookup"><span data-stu-id="1f551-113">LDDB_MASTER_LOAD_FAILED</span></span>|  
|<span data-ttu-id="1f551-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="1f551-114">Message Text</span></span>|<span data-ttu-id="1f551-115">No se pudo restaurar la base de datos maestra.</span><span class="sxs-lookup"><span data-stu-id="1f551-115">Failed to restore master database.</span></span> <span data-ttu-id="1f551-116">Cerrando SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1f551-116">Shutting down SQL Server.</span></span> <span data-ttu-id="1f551-117">Compruebe los registros de errores y vuelva a generar la base de datos maestra.</span><span class="sxs-lookup"><span data-stu-id="1f551-117">Check the error logs, and rebuild the master database.</span></span> <span data-ttu-id="1f551-118">Para obtener más información acerca de cómo volver a crear la base de datos maestra, vea los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1f551-118">For more information about how to rebuild the master database, see SQL Server Books Online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1f551-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="1f551-119">Explanation</span></span>  
 <span data-ttu-id="1f551-120">Se trata de un mensaje de error general que indica diversos problemas con la base de datos **maestra**.</span><span class="sxs-lookup"><span data-stu-id="1f551-120">This is a general error message indicating various problems with the **master** database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1f551-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="1f551-121">User Action</span></span>  
 <span data-ttu-id="1f551-122">Consulte los registros de errores para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="1f551-122">Check the error logs for more information.</span></span> <span data-ttu-id="1f551-123">Para crear una base de datos **maestra** utilizable, ejecute Setup.exe con la opción REBUILDDATABASE.</span><span class="sxs-lookup"><span data-stu-id="1f551-123">To create a usable **master** database, run Setup.exe with the REBUILDDATABASE option.</span></span> <span data-ttu-id="1f551-124">Para obtener más información, vea "Procedimientos: Instalar SQL Server desde el símbolo del sistema" en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1f551-124">For more information see "How to: Install SQL Server from the Command Prompt" in SQL Server Books Online.</span></span>  
  
  
