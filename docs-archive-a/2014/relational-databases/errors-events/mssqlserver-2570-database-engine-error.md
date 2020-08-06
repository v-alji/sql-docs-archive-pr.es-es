---
title: MSSQLSERVER_2570 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2570 (Database Engine error)
ms.assetid: 29800aa9-81aa-4371-992c-487dbb617f46
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 79137d0f70c05c6aa7b758f7e073d152681a14b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744712"
---
# <a name="mssqlserver_2570"></a><span data-ttu-id="7ea38-102">MSSQLSERVER_2570</span><span class="sxs-lookup"><span data-stu-id="7ea38-102">MSSQLSERVER_2570</span></span>
    
## <a name="details"></a><span data-ttu-id="7ea38-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="7ea38-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7ea38-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="7ea38-104">Product Name</span></span>|<span data-ttu-id="7ea38-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7ea38-105">SQL Server</span></span>|  
|<span data-ttu-id="7ea38-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="7ea38-106">Event ID</span></span>|<span data-ttu-id="7ea38-107">2570</span><span class="sxs-lookup"><span data-stu-id="7ea38-107">2570</span></span>|  
|<span data-ttu-id="7ea38-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="7ea38-108">Event Source</span></span>|<span data-ttu-id="7ea38-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7ea38-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7ea38-110">Componente</span><span class="sxs-lookup"><span data-stu-id="7ea38-110">Component</span></span>|<span data-ttu-id="7ea38-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7ea38-111">SQLEngine</span></span>|  
|<span data-ttu-id="7ea38-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="7ea38-112">Symbolic Name</span></span>|<span data-ttu-id="7ea38-113">DBCC_COLUMN_VALUE_OUT_OF_RANGE</span><span class="sxs-lookup"><span data-stu-id="7ea38-113">DBCC_COLUMN_VALUE_OUT_OF_RANGE</span></span>|  
|<span data-ttu-id="7ea38-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="7ea38-114">Message Text</span></span>|<span data-ttu-id="7ea38-115">Página P_ID, zona S_ID en el Id. de objeto O_ID, Id. de índice I_ID, Id. de partición PN_ID, Id. de unidad de asignación A_ID (tipo TYPE).</span><span class="sxs-lookup"><span data-stu-id="7ea38-115">Page P_ID, slot S_ID in object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span> <span data-ttu-id="7ea38-116">El valor de la columna COLUMN_NAME está fuera del intervalo del tipo de datos "DATATYPE".</span><span class="sxs-lookup"><span data-stu-id="7ea38-116">Column COLUMN_NAME value is out of range for data type "DATATYPE".</span></span> <span data-ttu-id="7ea38-117">Actualice la columna de forma que contenga un valor válido.</span><span class="sxs-lookup"><span data-stu-id="7ea38-117">Update column to a legal value.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7ea38-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="7ea38-118">Explanation</span></span>  
 <span data-ttu-id="7ea38-119">El valor de columna incluido en la columna especificada está fuera del intervalo de valores posibles del tipo de datos de columna.</span><span class="sxs-lookup"><span data-stu-id="7ea38-119">The column value that is contained in the specified column is outside the range of possible values for the column data type.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7ea38-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="7ea38-120">User Action</span></span>  
 <span data-ttu-id="7ea38-121">Este error es irreparable.</span><span class="sxs-lookup"><span data-stu-id="7ea38-121">The error is not repairable.</span></span> <span data-ttu-id="7ea38-122">Actualice la columna con un valor que se encuentre dentro del intervalo del tipo de datos de la columna y vuelva a ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="7ea38-122">Update the column to a value within the range for the data type of the column and run the command again.</span></span>  <span data-ttu-id="7ea38-123">Para obtener más información, vea este artículo de KB [923247](https://support.microsoft.com/kb/923247).</span><span class="sxs-lookup"><span data-stu-id="7ea38-123">For more information, see this KB article [923247](https://support.microsoft.com/kb/923247).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ea38-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7ea38-124">See Also</span></span>  
 <span data-ttu-id="7ea38-125">[UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7ea38-125">[UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql) </span></span>  
 [<span data-ttu-id="7ea38-126">Tipos de datos &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7ea38-126">Data Types &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/data-types-transact-sql)  
  
  
