---
title: MSSQLSERVER_2508 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2508 (Database Engine error)
ms.assetid: c37d40e5-c665-4d66-a727-5cb845634fcc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 11dd1c72c8cae868b7ebcb02e72ef0db81aeafe2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745775"
---
# <a name="mssqlserver_2508"></a><span data-ttu-id="d6b85-102">MSSQLSERVER_2508</span><span class="sxs-lookup"><span data-stu-id="d6b85-102">MSSQLSERVER_2508</span></span>
    
## <a name="details"></a><span data-ttu-id="d6b85-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="d6b85-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d6b85-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="d6b85-104">Product Name</span></span>|<span data-ttu-id="d6b85-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d6b85-105">SQL Server</span></span>|  
|<span data-ttu-id="d6b85-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="d6b85-106">Event ID</span></span>|<span data-ttu-id="d6b85-107">2508</span><span class="sxs-lookup"><span data-stu-id="d6b85-107">2508</span></span>|  
|<span data-ttu-id="d6b85-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="d6b85-108">Event Source</span></span>|<span data-ttu-id="d6b85-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d6b85-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d6b85-110">Componente</span><span class="sxs-lookup"><span data-stu-id="d6b85-110">Component</span></span>|<span data-ttu-id="d6b85-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d6b85-111">SQLEngine</span></span>|  
|<span data-ttu-id="d6b85-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="d6b85-112">Symbolic Name</span></span>|<span data-ttu-id="d6b85-113">DBCC_OUT_OF_DATE_PAGE_OR_ROW_COUNT</span><span class="sxs-lookup"><span data-stu-id="d6b85-113">DBCC_OUT_OF_DATE_PAGE_OR_ROW_COUNT</span></span>|  
|<span data-ttu-id="d6b85-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="d6b85-114">Message Text</span></span>|<span data-ttu-id="d6b85-115">El recuento de %.\*ls para el objeto "%.\*ls", id. de índice %d, id. de partición %I64d, id. de unidad de asignación %I64d (tipo %.\*ls) no es correcto.</span><span class="sxs-lookup"><span data-stu-id="d6b85-115">The %.\*ls count for object "%.\*ls", index ID %d, partition ID %I64d, alloc unit ID %I64d (type %.\*ls) is incorrect.</span></span> <span data-ttu-id="d6b85-116">Ejecute DBCC UPDATEUSAGE.</span><span class="sxs-lookup"><span data-stu-id="d6b85-116">Run DBCC UPDATEUSAGE.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d6b85-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="d6b85-117">Explanation</span></span>  
 <span data-ttu-id="d6b85-118">En las versiones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] anteriores a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], los valores del recuento de filas por tabla y por índice, y del recuento de páginas pueden llegar a ser incorrectos.</span><span class="sxs-lookup"><span data-stu-id="d6b85-118">In versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], the values for the table and index row counts and page counts can become incorrect.</span></span> <span data-ttu-id="d6b85-119">Las bases de datos que se crearon en versiones anteriores a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] pueden contener recuentos incorrectos.</span><span class="sxs-lookup"><span data-stu-id="d6b85-119">Databases that were created on versions prior to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] may contain incorrect counts.</span></span> <span data-ttu-id="d6b85-120">DBCC CHECKDB se ha mejorado para detectar estos errores y devuelve este mensaje de advertencia cuando se encuentra el error.</span><span class="sxs-lookup"><span data-stu-id="d6b85-120">DBCC CHECKDB has been enhanced to detect these errors and returns this warning message when the error encountered.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d6b85-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="d6b85-121">User Action</span></span>  
 <span data-ttu-id="d6b85-122">Ejecute DBCC UPDATEUSAGE con el objeto o índice especificado, o con la base de datos que contiene el objeto para corregir los recuentos no válidos.</span><span class="sxs-lookup"><span data-stu-id="d6b85-122">Run DBCC UPDATEUSAGE against the specified object or index, or against the database in which the object is contained to correct the invalid counts.</span></span>  
  
  
