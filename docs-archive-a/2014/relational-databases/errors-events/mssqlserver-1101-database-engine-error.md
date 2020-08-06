---
title: MSSQLSERVER_1101 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1101 (Database Engine error)
ms.assetid: d63b67d5-59f5-4f77-904e-5ba67f2dd850
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 631b0ab1466815cbacfd71b4f9fd714fabd0f7b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675962"
---
# <a name="mssqlserver_1101"></a><span data-ttu-id="cb8c2-102">MSSQLSERVER_1101</span><span class="sxs-lookup"><span data-stu-id="cb8c2-102">MSSQLSERVER_1101</span></span>
    
## <a name="details"></a><span data-ttu-id="cb8c2-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="cb8c2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cb8c2-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="cb8c2-104">Product Name</span></span>|<span data-ttu-id="cb8c2-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="cb8c2-105">SQL Server</span></span>|  
|<span data-ttu-id="cb8c2-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="cb8c2-106">Event ID</span></span>|<span data-ttu-id="cb8c2-107">1101</span><span class="sxs-lookup"><span data-stu-id="cb8c2-107">1101</span></span>|  
|<span data-ttu-id="cb8c2-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="cb8c2-108">Event Source</span></span>|<span data-ttu-id="cb8c2-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="cb8c2-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="cb8c2-110">Componente</span><span class="sxs-lookup"><span data-stu-id="cb8c2-110">Component</span></span>|<span data-ttu-id="cb8c2-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="cb8c2-111">SQLEngine</span></span>|  
|<span data-ttu-id="cb8c2-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="cb8c2-112">Symbolic Name</span></span>|<span data-ttu-id="cb8c2-113">NOALLOCPG</span><span class="sxs-lookup"><span data-stu-id="cb8c2-113">NOALLOCPG</span></span>|  
|<span data-ttu-id="cb8c2-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="cb8c2-114">Message Text</span></span>|<span data-ttu-id="cb8c2-115">No se pudo asignar una nueva página para la base de datos '%.\*ls' porque el grupo de archivos '%.\*ls' tiene espacio insuficiente en el disco.</span><span class="sxs-lookup"><span data-stu-id="cb8c2-115">Could not allocate a new page for database '%.\*ls' because of insufficient disk space in filegroup '%.\*ls'.</span></span> <span data-ttu-id="cb8c2-116">Quite objetos del grupo de archivos, agregue archivos adicionales al grupo de archivos o establezca la opción de crecimiento automático para los archivos existentes en el grupo de archivos con el fin de crear el espacio necesario.</span><span class="sxs-lookup"><span data-stu-id="cb8c2-116">Create the necessary space by dropping objects in the filegroup, adding additional files to the filegroup, or setting autogrowth on for existing files in the filegroup.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cb8c2-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="cb8c2-117">Explanation</span></span>  
 <span data-ttu-id="cb8c2-118">No hay espacio en disco disponible en un grupo de archivos.</span><span class="sxs-lookup"><span data-stu-id="cb8c2-118">No disk space available in a filegroup.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cb8c2-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="cb8c2-119">User Action</span></span>  
 <span data-ttu-id="cb8c2-120">Las siguientes acciones pueden crear espacio disponible en el grupo de archivos.</span><span class="sxs-lookup"><span data-stu-id="cb8c2-120">The following actions may make space available in the filegroup.</span></span>  
  
-   <span data-ttu-id="cb8c2-121">Active AUTOGROW.</span><span class="sxs-lookup"><span data-stu-id="cb8c2-121">Turn on AUTOGROW.</span></span>  
  
-   <span data-ttu-id="cb8c2-122">Agregue más archivos al grupo de archivos.</span><span class="sxs-lookup"><span data-stu-id="cb8c2-122">Add more files to the file group.</span></span>  
  
-   <span data-ttu-id="cb8c2-123">Libere espacio en disco quitando los índices o las tablas que no sean necesarios del grupo de archivos.</span><span class="sxs-lookup"><span data-stu-id="cb8c2-123">Free up disk space by dropping unnecessary indexes or tables in the filegroup.</span></span>  
  
  
