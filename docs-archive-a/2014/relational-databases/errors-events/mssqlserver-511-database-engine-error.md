---
title: MSSQLSERVER_511 | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 511 (Database Engine error)
ms.assetid: 0c85686a-53c1-4180-ba8c-2000e68a0d63
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5b69d2c043997e2947563de119bc4ee89fdf4e32
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745308"
---
# <a name="mssqlserver_511"></a><span data-ttu-id="2bec4-102">MSSQLSERVER_511</span><span class="sxs-lookup"><span data-stu-id="2bec4-102">MSSQLSERVER_511</span></span>
    
## <a name="details"></a><span data-ttu-id="2bec4-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="2bec4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2bec4-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="2bec4-104">Product Name</span></span>|<span data-ttu-id="2bec4-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2bec4-105">SQL Server</span></span>|  
|<span data-ttu-id="2bec4-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="2bec4-106">Event ID</span></span>|<span data-ttu-id="2bec4-107">511</span><span class="sxs-lookup"><span data-stu-id="2bec4-107">511</span></span>|  
|<span data-ttu-id="2bec4-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="2bec4-108">Event Source</span></span>|<span data-ttu-id="2bec4-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2bec4-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2bec4-110">Componente</span><span class="sxs-lookup"><span data-stu-id="2bec4-110">Component</span></span>|<span data-ttu-id="2bec4-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="2bec4-111">SQLEngine</span></span>|  
|<span data-ttu-id="2bec4-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="2bec4-112">Symbolic Name</span></span>|<span data-ttu-id="2bec4-113">ROW_TOOBIG</span><span class="sxs-lookup"><span data-stu-id="2bec4-113">ROW_TOOBIG</span></span>|  
|<span data-ttu-id="2bec4-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="2bec4-114">Message Text</span></span>|<span data-ttu-id="2bec4-115">No se puede crear una fila de tamaño %d que sea mayor que el máximo permitido de %d.</span><span class="sxs-lookup"><span data-stu-id="2bec4-115">Cannot create a row of size %d which is greater than the allowable maximum of %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2bec4-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="2bec4-116">Explanation</span></span>  
 <span data-ttu-id="2bec4-117">La operación que se ha intentado ha superado el tamaño máximo de una fila.</span><span class="sxs-lookup"><span data-stu-id="2bec4-117">The operation you have tried has exceeded the maximum size of a row.</span></span> <span data-ttu-id="2bec4-118">Normalmente, el tamaño máximo de una fila es 8.060 bytes.</span><span class="sxs-lookup"><span data-stu-id="2bec4-118">Usually, the maximum size of a row is 8,060 bytes.</span></span> <span data-ttu-id="2bec4-119">Algunos formatos de almacenamiento contienen una sobrecarga que puede reducir el tamaño de fila disponible para datos.</span><span class="sxs-lookup"><span data-stu-id="2bec4-119">Some storage formats contain overhead that can reduce the row size that is available for data.</span></span> <span data-ttu-id="2bec4-120">Por ejemplo, cuando se utilizan columnas dispersas, el tamaño máximo de una fila es 8.018 bytes.</span><span class="sxs-lookup"><span data-stu-id="2bec4-120">For example, when you use sparse columns, the maximum size of a row is 8,018 bytes.</span></span> <span data-ttu-id="2bec4-121">Algunas operaciones que agregan o quitan filas y algunas operaciones que cambian el tipo de datos de una columna requieren que se vuelva a escribir la fila en la página de datos y, a continuación, se quita la fila original.</span><span class="sxs-lookup"><span data-stu-id="2bec4-121">Some operations that add or remove rows and some operations that change the data type of a column require the row to be rewritten on the data page, and then the original row is removed.</span></span> <span data-ttu-id="2bec4-122">En estas operaciones, el límite real para el tamaño de la fila es la mitad del límite máximo.</span><span class="sxs-lookup"><span data-stu-id="2bec4-122">In these operations, the effective limit to the size of the row is half the maximum limit.</span></span> <span data-ttu-id="2bec4-123">Esto se debe a que la fila original y la fila modificada deben estar en la página de datos durante un breve período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="2bec4-123">This is because the original row and the modified row must both be contained on the data page for a short period.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="2bec4-124">Cada columna **VARCHAR (Max)** o **nvarchar (Max)** que no sea NULL requiere 24 bytes de asignación fija adicional que se recuenton con respecto al límite de filas de 8.060 bytes durante una operación de ordenación.</span><span class="sxs-lookup"><span data-stu-id="2bec4-124">Each non-null  **varchar(max)** or **nvarchar(max)** column requires 24 bytes of additional fixed allocation which counts against the 8,060 byte row limit during a sort operation.</span></span> <span data-ttu-id="2bec4-125">Esto puede crear un límite implícito del número de columnas **VARCHAR (Max)** o **nvarchar (Max** ) no NULL que se pueden crear en una tabla.</span><span class="sxs-lookup"><span data-stu-id="2bec4-125">This can create an implicit limit to the number of non-null **varchar(max)** or **nvarchar(max)** columns that can be created in a table.</span></span> <span data-ttu-id="2bec4-126">No se produce ningún error especial cuando se crea la tabla (más allá de la advertencia habitual de que el tamaño máximo de la fila supera el máximo permitido de 8060 bytes) ni en el momento de la inserción de los datos.</span><span class="sxs-lookup"><span data-stu-id="2bec4-126">No special error is provided when the table is created (beyond the usual warning that the maximum row size exceeds the allowed maximum of 8060 bytes) or at the time of data insertion.</span></span> <span data-ttu-id="2bec4-127">Este tamaño de fila grande puede provocar errores (como el error 512) durante algunas operaciones normales, como una actualización de claves de índices agrupados u ordenaciones del conjunto completo de columnas, que los usuarios no pueden prever hasta que lleven a cabo alguna operación.</span><span class="sxs-lookup"><span data-stu-id="2bec4-127">This large row size can cause errors (such as error 512) during some normal operations, such as a clustered index key update, or sorts of the full column set, which users cannot anticipate until performing an operation.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2bec4-128">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="2bec4-128">User Action</span></span>  
 <span data-ttu-id="2bec4-129">Si es posible, reduzca el tamaño de la fila.</span><span class="sxs-lookup"><span data-stu-id="2bec4-129">If it is possible, reduce the size of the row.</span></span>  
  
 <span data-ttu-id="2bec4-130">Si cree que el problema se debe a una actualización en contexto de la fila, debe cambiar la tabla en varios pasos.</span><span class="sxs-lookup"><span data-stu-id="2bec4-130">If you think the problem is caused by an in-place update of the row, you must change the table in multiple steps.</span></span> <span data-ttu-id="2bec4-131">Cree una tabla nueva y transfiera los datos a dicha tabla.</span><span class="sxs-lookup"><span data-stu-id="2bec4-131">Create a new table, and transfer the data into the new table.</span></span> <span data-ttu-id="2bec4-132">A continuación, elimine la tabla original y cambie el nombre de la nueva tabla; o bien, trunque la tabla original, modifique las filas en ella y, a continuación, vuelva a mover los datos a la citada tabla.</span><span class="sxs-lookup"><span data-stu-id="2bec4-132">Then, either delete the original table and rename the new table, or truncate the original table, modify the rows in the original table, and then move the data back into it.</span></span>  
  
  
