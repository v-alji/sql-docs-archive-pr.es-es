---
title: MSSQLSERVER_611 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 611 (Database Engine error)
ms.assetid: ac6a213f-5c38-44ad-bc85-a62863786614
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f0caa1c218e8b80059c0c97aac652da7db870af3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677146"
---
# <a name="mssqlserver_611"></a><span data-ttu-id="d14d4-102">MSSQLSERVER_611</span><span class="sxs-lookup"><span data-stu-id="d14d4-102">MSSQLSERVER_611</span></span>
    
## <a name="details"></a><span data-ttu-id="d14d4-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="d14d4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d14d4-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="d14d4-104">Product Name</span></span>|<span data-ttu-id="d14d4-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d14d4-105">SQL Server</span></span>|  
|<span data-ttu-id="d14d4-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="d14d4-106">Event ID</span></span>|<span data-ttu-id="d14d4-107">611</span><span class="sxs-lookup"><span data-stu-id="d14d4-107">611</span></span>|  
|<span data-ttu-id="d14d4-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="d14d4-108">Event Source</span></span>|<span data-ttu-id="d14d4-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d14d4-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d14d4-110">Componente</span><span class="sxs-lookup"><span data-stu-id="d14d4-110">Component</span></span>|<span data-ttu-id="d14d4-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d14d4-111">SQLEngine</span></span>|  
|<span data-ttu-id="d14d4-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="d14d4-112">Symbolic Name</span></span>|<span data-ttu-id="d14d4-113">VAR_SIZE_TOO_BIG</span><span class="sxs-lookup"><span data-stu-id="d14d4-113">VAR_SIZE_TOO_BIG</span></span>|  
|<span data-ttu-id="d14d4-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="d14d4-114">Message Text</span></span>|<span data-ttu-id="d14d4-115">No se puede insertar ni actualizar una fila porque el tamaño total de columna variable, incluida la sobrecarga, es %d bytes más del límite.</span><span class="sxs-lookup"><span data-stu-id="d14d4-115">Cannot insert or update a row because total variable column size, including overhead, is %d bytes more than the limit.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d14d4-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="d14d4-116">Explanation</span></span>  
 <span data-ttu-id="d14d4-117">El tamaño máximo de la columna de variable e es mayor que el permitido por el esquema.</span><span class="sxs-lookup"><span data-stu-id="d14d4-117">The maximum variable column size is more than that allowed by the schema.</span></span> <span data-ttu-id="d14d4-118">El Error 611 se devuelve cuando la columna de variable está por encima del límite en el caso fijo cuando el formato de almacenamiento vardecimal está habilitado, o cuando el tamaño de la columna de variable está por encima del límite permitido en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] para un registro de datos comprimido.</span><span class="sxs-lookup"><span data-stu-id="d14d4-118">Error 611 is returned when the variable column is over the limit in the fixed case when vardecimal storage format is enabled, or when the variable column size is over the limit allowed in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] for a compressed data record.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d14d4-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="d14d4-119">User Action</span></span>  
 <span data-ttu-id="d14d4-120">Reduzca el tamaño del registro.</span><span class="sxs-lookup"><span data-stu-id="d14d4-120">Reduce the size of the record.</span></span>  
  
  
