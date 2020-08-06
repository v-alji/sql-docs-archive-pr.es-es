---
title: MSSQLSERVER_7916 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7916 (Database Engine error)
ms.assetid: 9bac3536-de14-4e98-84c2-bde9a59ba0d1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 21b31eedf61369d9c4d1cfdfd5f53eebd3f5341c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673707"
---
# <a name="mssqlserver_7916"></a><span data-ttu-id="4314f-102">MSSQLSERVER_7916</span><span class="sxs-lookup"><span data-stu-id="4314f-102">MSSQLSERVER_7916</span></span>
    
## <a name="details"></a><span data-ttu-id="4314f-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="4314f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4314f-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="4314f-104">Product Name</span></span>|<span data-ttu-id="4314f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4314f-105">SQL Server</span></span>|  
|<span data-ttu-id="4314f-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="4314f-106">Event ID</span></span>|<span data-ttu-id="4314f-107">7916</span><span class="sxs-lookup"><span data-stu-id="4314f-107">7916</span></span>|  
|<span data-ttu-id="4314f-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="4314f-108">Event Source</span></span>|<span data-ttu-id="4314f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4314f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4314f-110">Componente</span><span class="sxs-lookup"><span data-stu-id="4314f-110">Component</span></span>|<span data-ttu-id="4314f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4314f-111">SQLEngine</span></span>|  
|<span data-ttu-id="4314f-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="4314f-112">Symbolic Name</span></span>|<span data-ttu-id="4314f-113">DBCC2_REPAIR_RECORD_DELETED</span><span class="sxs-lookup"><span data-stu-id="4314f-113">DBCC2_REPAIR_RECORD_DELETED</span></span>|  
|<span data-ttu-id="4314f-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="4314f-114">Message Text</span></span>|<span data-ttu-id="4314f-115">Reparación: se ha eliminado el registro para el id. de objeto O_ID, id. de índice I_ID, id. de partición PN_ID, id. de unidad de asignación A_ID (tipo TYPE), en la página P_ID, ranura S_ID.</span><span class="sxs-lookup"><span data-stu-id="4314f-115">Repair: Deleted record for object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE), on page P_ID, slot S_ID.</span></span> <span data-ttu-id="4314f-116">Se volverán a generar los índices.</span><span class="sxs-lookup"><span data-stu-id="4314f-116">Indexes will be rebuilt.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4314f-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="4314f-117">Explanation</span></span>  
 <span data-ttu-id="4314f-118">Este es un mensaje informativo de REPAIR que indica que el registro especificado se eliminó de la página.</span><span class="sxs-lookup"><span data-stu-id="4314f-118">This is an information messages from REPAIR that indicates the specified record was deleted from the page.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4314f-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="4314f-119">User Action</span></span>  
 <span data-ttu-id="4314f-120">None</span><span class="sxs-lookup"><span data-stu-id="4314f-120">None</span></span>  
  
  
