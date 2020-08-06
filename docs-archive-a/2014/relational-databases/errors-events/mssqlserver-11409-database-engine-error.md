---
title: MSSQLSERVER_11409 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 11409 (Database Engine error)
ms.assetid: 99b71a1c-a72d-4ca9-9d00-4230c9042ba5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e4249e13a3530f69978c78f2e2ca6e4583eed46a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663003"
---
# <a name="mssqlserver_11409"></a><span data-ttu-id="e8b06-102">MSSQLSERVER_11409</span><span class="sxs-lookup"><span data-stu-id="e8b06-102">MSSQLSERVER_11409</span></span>
    
## <a name="details"></a><span data-ttu-id="e8b06-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="e8b06-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e8b06-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="e8b06-104">Product Name</span></span>|<span data-ttu-id="e8b06-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e8b06-105">SQL Server</span></span>|  
|<span data-ttu-id="e8b06-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="e8b06-106">Event ID</span></span>|<span data-ttu-id="e8b06-107">11409</span><span class="sxs-lookup"><span data-stu-id="e8b06-107">11409</span></span>|  
|<span data-ttu-id="e8b06-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="e8b06-108">Event Source</span></span>|<span data-ttu-id="e8b06-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e8b06-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e8b06-110">Componente</span><span class="sxs-lookup"><span data-stu-id="e8b06-110">Component</span></span>|<span data-ttu-id="e8b06-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e8b06-111">SQLEngine</span></span>|  
|<span data-ttu-id="e8b06-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="e8b06-112">Symbolic Name</span></span>|<span data-ttu-id="e8b06-113">ALTERCOL_COLSET_DROP</span><span class="sxs-lookup"><span data-stu-id="e8b06-113">ALTERCOL_COLSET_DROP</span></span>|  
|<span data-ttu-id="e8b06-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="e8b06-114">Message Text</span></span>|<span data-ttu-id="e8b06-115">No se puede quitar el conjunto de columnas '%.\*ls' de la tabla '%.\*ls' porque la tabla contiene más de 1025 columnas.</span><span class="sxs-lookup"><span data-stu-id="e8b06-115">Cannot drop column set '%.\*ls' in table '%.\*ls' because the table contains more than 1025 columns.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e8b06-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="e8b06-116">Explanation</span></span>  
 <span data-ttu-id="e8b06-117">Las tablas pueden contener 1024 columnas, como máximo, que no estén designadas como dispersas o calculadas.</span><span class="sxs-lookup"><span data-stu-id="e8b06-117">Tables can contain a maximum of 1024 columns that are not designated as sparse, or computed.</span></span> <span data-ttu-id="e8b06-118">Cuando las columnas dispersas hacen que la tabla supere el número de 1024 columnas, se debe definir un conjunto de columnas para la tabla.</span><span class="sxs-lookup"><span data-stu-id="e8b06-118">When sparse columns cause the table to exceed 1024 columns, a column set must be defined for the table.</span></span> <span data-ttu-id="e8b06-119">La tabla a la que se hace referencia tiene más de 1024 columnas y se ha intentado quitar el conjunto de columnas.</span><span class="sxs-lookup"><span data-stu-id="e8b06-119">The table referenced has more than 1024 columns and you have attempted to remove the column set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e8b06-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="e8b06-120">User Action</span></span>  
 <span data-ttu-id="e8b06-121">Con las columnas actuales en la tabla, debe conservar el conjunto de columnas.</span><span class="sxs-lookup"><span data-stu-id="e8b06-121">With the current columns in the table, you must retain the column set.</span></span>  
  
 <span data-ttu-id="e8b06-122">Para quitar el conjunto de columnas, primero debe quitar columnas de la tabla, hasta que haya menos de 1024.</span><span class="sxs-lookup"><span data-stu-id="e8b06-122">To remove the column set, first remove columns from the table, until you have no more than 1024 columns.</span></span> <span data-ttu-id="e8b06-123">A continuación, puede quitar el conjunto de columnas.</span><span class="sxs-lookup"><span data-stu-id="e8b06-123">Then, you can remove the column set.</span></span>  
  
  
