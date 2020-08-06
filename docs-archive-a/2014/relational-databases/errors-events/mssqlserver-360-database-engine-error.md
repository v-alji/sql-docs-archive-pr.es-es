---
title: MSSQLSERVER_360 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 360 (Database Engine error)
ms.assetid: e2b7c1b2-3679-4206-9b25-6bd55ef96a2c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b30311d7f55231c1e7a6d5969d49c5d1bc07a848
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671571"
---
# <a name="mssqlserver_360"></a><span data-ttu-id="24db0-102">MSSQLSERVER_360</span><span class="sxs-lookup"><span data-stu-id="24db0-102">MSSQLSERVER_360</span></span>
    
## <a name="details"></a><span data-ttu-id="24db0-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="24db0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="24db0-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="24db0-104">Product Name</span></span>|<span data-ttu-id="24db0-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="24db0-105">SQL Server</span></span>|  
|<span data-ttu-id="24db0-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="24db0-106">Event ID</span></span>|<span data-ttu-id="24db0-107">360</span><span class="sxs-lookup"><span data-stu-id="24db0-107">360</span></span>|  
|<span data-ttu-id="24db0-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="24db0-108">Event Source</span></span>|<span data-ttu-id="24db0-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="24db0-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="24db0-110">Componente</span><span class="sxs-lookup"><span data-stu-id="24db0-110">Component</span></span>|<span data-ttu-id="24db0-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="24db0-111">SQLEngine</span></span>|  
|<span data-ttu-id="24db0-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="24db0-112">Symbolic Name</span></span>|<span data-ttu-id="24db0-113">DML_UPDATE_SPARSE_AND_COLSET</span><span class="sxs-lookup"><span data-stu-id="24db0-113">DML_UPDATE_SPARSE_AND_COLSET</span></span>|  
|<span data-ttu-id="24db0-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="24db0-114">Message Text</span></span>|<span data-ttu-id="24db0-115">La lista de columnas de destino de una instrucción INSERT, UPDATE o MERGE no puede contener una columna dispersa y el conjunto de columnas que la contiene.</span><span class="sxs-lookup"><span data-stu-id="24db0-115">The target column list of an INSERT, UPDATE, or MERGE statement cannot contain both a sparse column and the column set that contains the sparse column.</span></span> <span data-ttu-id="24db0-116">Escriba de nuevo la instrucción para incluir la columna dispersa o el conjunto de columnas, pero no ambos.</span><span class="sxs-lookup"><span data-stu-id="24db0-116">Rewrite the statement to include either the sparse column or the column set, but not both.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="24db0-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="24db0-117">Explanation</span></span>  
 <span data-ttu-id="24db0-118">Un conjunto de columnas es una representación XML sin tipo que combina algunas columnas de una tabla en una salida estructurada.</span><span class="sxs-lookup"><span data-stu-id="24db0-118">A column set is an untyped XML representation that combines some columns of a table into a structured output.</span></span> <span data-ttu-id="24db0-119">Se ha intentado modificar tanto el conjunto de columnas como una columna incluida en dicho conjunto, produciendo dos referencias a la misma columna.</span><span class="sxs-lookup"><span data-stu-id="24db0-119">An attempt was made to modify both the column set and a column that is included in the column set, causing two references to the same column.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="24db0-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="24db0-120">User Action</span></span>  
 <span data-ttu-id="24db0-121">Vuelva a escribir la instrucción para incluir referencias a la columna o al conjunto de columnas, pero no incluya ambos en la instrucción.</span><span class="sxs-lookup"><span data-stu-id="24db0-121">Rewrite the statement to include references to either the column or the column set, but do not include both in the statement.</span></span>  
  
  
