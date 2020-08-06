---
title: Acceso al contexto de la consulta en procedimientos almacenados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- execution context [Analysis Services]
- stored procedures [Analysis Services], query context
- Context object
- query context [Analysis Services]
ms.assetid: bdc7dad8-2f22-4265-aba4-a3a451527840
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9da8ddb223ed03c0208fe524ea5cd7195a039c97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743676"
---
# <a name="accessing-query-context-in-stored-procedures"></a><span data-ttu-id="51bcb-102">Acceder al contexto de la consulta en los procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="51bcb-102">Accessing Query Context in Stored Procedures</span></span>
  <span data-ttu-id="51bcb-103">El contexto de ejecución de un procedimiento almacenado se encuentra disponible dentro del código del procedimiento almacenado como el objeto `Context` del modelo de objeto del servidor ADOMD.NET.</span><span class="sxs-lookup"><span data-stu-id="51bcb-103">The execution context of a stored procedure is available within the code of the stored procedure as the `Context` object of the ADOMD.NET server object model.</span></span> <span data-ttu-id="51bcb-104">Éste es un contexto de solo lectura y no puede ser modificado por el procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="51bcb-104">This is a read-only context and cannot be modified by the stored procedure.</span></span> <span data-ttu-id="51bcb-105">Las propiedades siguientes están disponibles en este objeto.</span><span class="sxs-lookup"><span data-stu-id="51bcb-105">The following properties are available on this object.</span></span>  
  
|<span data-ttu-id="51bcb-106">Propiedad</span><span class="sxs-lookup"><span data-stu-id="51bcb-106">Property</span></span>|<span data-ttu-id="51bcb-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="51bcb-107">Type</span></span>|<span data-ttu-id="51bcb-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="51bcb-108">Description</span></span>|  
|--------------|----------|-----------------|  
|<span data-ttu-id="51bcb-109">**CurrentCube**</span><span class="sxs-lookup"><span data-stu-id="51bcb-109">**CurrentCube**</span></span>|<span data-ttu-id="51bcb-110">Cubo</span><span class="sxs-lookup"><span data-stu-id="51bcb-110">Cube</span></span>|<span data-ttu-id="51bcb-111">El cubo del contexto de consulta actual.</span><span class="sxs-lookup"><span data-stu-id="51bcb-111">The cube for the current query context.</span></span>|  
|<span data-ttu-id="51bcb-112">**CurrentDatabaseName**</span><span class="sxs-lookup"><span data-stu-id="51bcb-112">**CurrentDatabaseName**</span></span>|<span data-ttu-id="51bcb-113">String</span><span class="sxs-lookup"><span data-stu-id="51bcb-113">String</span></span>|<span data-ttu-id="51bcb-114">El identificador de la base de datos actual.</span><span class="sxs-lookup"><span data-stu-id="51bcb-114">The identifier of the current database.</span></span>|  
|<span data-ttu-id="51bcb-115">**CurrentConnection**</span><span class="sxs-lookup"><span data-stu-id="51bcb-115">**CurrentConnection**</span></span>|<span data-ttu-id="51bcb-116">Conexión</span><span class="sxs-lookup"><span data-stu-id="51bcb-116">Connection</span></span>|<span data-ttu-id="51bcb-117">Una referencia al objeto de conexión en el contexto actual.</span><span class="sxs-lookup"><span data-stu-id="51bcb-117">A reference to the connection object in the current context.</span></span>|  
|<span data-ttu-id="51bcb-118">**Correcto**</span><span class="sxs-lookup"><span data-stu-id="51bcb-118">**Pass**</span></span>|<span data-ttu-id="51bcb-119">Entero</span><span class="sxs-lookup"><span data-stu-id="51bcb-119">Integer</span></span>|<span data-ttu-id="51bcb-120">Número de paso del contexto actual.</span><span class="sxs-lookup"><span data-stu-id="51bcb-120">The pass number for the current context.</span></span>|  
  
 <span data-ttu-id="51bcb-121">El objeto `Context` existe cuando el modelo de objetos de expresiones multidimensionales (MDX) se usa en un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="51bcb-121">The `Context` object exists when the Multidimensional Expressions (MDX) object model is used in a stored procedure.</span></span> <span data-ttu-id="51bcb-122">No está disponible cuando el modelo del objeto MDX se usa en un cliente.</span><span class="sxs-lookup"><span data-stu-id="51bcb-122">It is not available when the MDX object model is used on a client.</span></span> <span data-ttu-id="51bcb-123">El objeto `Context` no se pasa explícitamente al procedimiento almacenado, ni es devuelto por él.</span><span class="sxs-lookup"><span data-stu-id="51bcb-123">The `Context` object is not explicitly passed to or returned by the stored procedure.</span></span> <span data-ttu-id="51bcb-124">Se encuentra disponible durante la ejecución del procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="51bcb-124">It is available during the execution of the stored procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51bcb-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="51bcb-125">See Also</span></span>  
 <span data-ttu-id="51bcb-126">[Administración de ensamblados de modelos multidimensionales](../multidimensional-models/multidimensional-model-assemblies-management.md) </span><span class="sxs-lookup"><span data-stu-id="51bcb-126">[Multidimensional Model Assemblies Management](../multidimensional-models/multidimensional-model-assemblies-management.md) </span></span>  
 [<span data-ttu-id="51bcb-127">Definir procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="51bcb-127">Defining Stored Procedures</span></span>](../multidimensional-models-extending-olap-stored-procedures/defining-stored-procedures.md)  
  
  
