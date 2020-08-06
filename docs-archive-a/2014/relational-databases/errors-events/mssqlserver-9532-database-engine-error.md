---
title: MSSQLSERVER_9532 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9532 (Database Engine error)
ms.assetid: ab95cce8-4f97-4aea-a746-a73eea7c9aab
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c34ebc7c682d2ffe8bc0205565f5dfd44fdd5b66
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672030"
---
# <a name="mssqlserver_9532"></a><span data-ttu-id="aa025-102">MSSQLSERVER_9532</span><span class="sxs-lookup"><span data-stu-id="aa025-102">MSSQLSERVER_9532</span></span>
    
## <a name="details"></a><span data-ttu-id="aa025-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="aa025-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="aa025-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="aa025-104">Product Name</span></span>|<span data-ttu-id="aa025-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="aa025-105">SQL Server</span></span>|  
|<span data-ttu-id="aa025-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="aa025-106">Event ID</span></span>|<span data-ttu-id="aa025-107">9532</span><span class="sxs-lookup"><span data-stu-id="aa025-107">9532</span></span>|  
|<span data-ttu-id="aa025-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="aa025-108">Event Source</span></span>|<span data-ttu-id="aa025-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="aa025-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="aa025-110">Componente</span><span class="sxs-lookup"><span data-stu-id="aa025-110">Component</span></span>|<span data-ttu-id="aa025-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="aa025-111">SQLEngine</span></span>|  
|<span data-ttu-id="aa025-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="aa025-112">Symbolic Name</span></span>|<span data-ttu-id="aa025-113">XMLERR_COLUMNSET_CANNOT_CONVERT_FROM_TO</span><span class="sxs-lookup"><span data-stu-id="aa025-113">XMLERR_COLUMNSET_CANNOT_CONVERT_FROM_TO</span></span>|  
|<span data-ttu-id="aa025-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="aa025-114">Message Text</span></span>|<span data-ttu-id="aa025-115">En la operación consulta/DML que implica al conjunto de columnas "%.\*ls", no se pudo convertir el tipo de datos "%ls" al tipo "%ls" para la columna "%.\*ls".</span><span class="sxs-lookup"><span data-stu-id="aa025-115">In the query/DML operation involving  column set '%.\*ls', conversion failed when converting from the data type '%ls' to the data type '%ls' for the column '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="aa025-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="aa025-116">Explanation</span></span>  
 <span data-ttu-id="aa025-117">Un conjunto de columnas es una representación XML sin tipo que combina algunas columnas de una tabla en una salida estructurada.</span><span class="sxs-lookup"><span data-stu-id="aa025-117">A column set is an untyped XML representation that combines some of the columns of a table into a structured output.</span></span> <span data-ttu-id="aa025-118">Cuando se insertan o actualizan valores de columnas dispersas mediante el conjunto de columnas XML, los valores que se insertan en las columnas dispersas subyacentes se convierten de manera implícita del tipo de datos `xml`.</span><span class="sxs-lookup"><span data-stu-id="aa025-118">When you are inserting or updating sparse column values through the XML column set, the values that are inserted into the underlying sparse columns are implicitly converted from the `xml` data type.</span></span> <span data-ttu-id="aa025-119">Se proporcionó un valor que no se puede convertir al tipo de datos de la columna.</span><span class="sxs-lookup"><span data-stu-id="aa025-119">A value was provided that cannot be converted to the data type of the column.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="aa025-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="aa025-120">User Action</span></span>  
 <span data-ttu-id="aa025-121">Dado que el valor proporcionado no se pudo convertir de manera implícita, podría ser una entrada no válida.</span><span class="sxs-lookup"><span data-stu-id="aa025-121">Because the value provided could not be implicitly converted, it might be an invalid entry.</span></span> <span data-ttu-id="aa025-122">Corrija el error e inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="aa025-122">Correct the error and retry.</span></span> <span data-ttu-id="aa025-123">Si el valor es correcto, modifique la instrucción para utilizar las columnas individuales en lugar del conjunto de columnas.</span><span class="sxs-lookup"><span data-stu-id="aa025-123">If the value is correct, modify the statement to use the individual columns instead of the column set.</span></span> <span data-ttu-id="aa025-124">Esto permitirá convertir de manera explícita el valor al tipo de datos correcto.</span><span class="sxs-lookup"><span data-stu-id="aa025-124">This will allow you to explicitly cast the value into the correct data type.</span></span>  
  
  
