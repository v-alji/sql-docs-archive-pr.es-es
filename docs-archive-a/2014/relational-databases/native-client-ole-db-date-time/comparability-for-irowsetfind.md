---
title: Comparabilidad de IRowsetFind | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- IRowsetFind comparability [ODBC]
ms.assetid: 7d148b56-9bbe-4e55-b31f-43f115705402
author: rothja
ms.author: jroth
ms.openlocfilehash: 8ad359ca4957b434c3798d1a441eb0fd57644a59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669668"
---
# <a name="comparability-for-irowsetfind"></a><span data-ttu-id="d64de-102">Comparaciones en IRowsetFind</span><span class="sxs-lookup"><span data-stu-id="d64de-102">Comparability for IRowsetFind</span></span>
  <span data-ttu-id="d64de-103">IRowsetFind admite las comparaciones siguientes para los tipos de fecha y hora únicamente:</span><span class="sxs-lookup"><span data-stu-id="d64de-103">For date/time types only, IRowsetFind supports the following comparisons:</span></span>  
  
-   <span data-ttu-id="d64de-104">LT</span><span class="sxs-lookup"><span data-stu-id="d64de-104">LT</span></span>  
  
-   <span data-ttu-id="d64de-105">LE</span><span class="sxs-lookup"><span data-stu-id="d64de-105">LE</span></span>  
  
-   <span data-ttu-id="d64de-106">EQ</span><span class="sxs-lookup"><span data-stu-id="d64de-106">EQ</span></span>  
  
-   <span data-ttu-id="d64de-107">GE</span><span class="sxs-lookup"><span data-stu-id="d64de-107">GE</span></span>  
  
-   <span data-ttu-id="d64de-108">GT</span><span class="sxs-lookup"><span data-stu-id="d64de-108">GT</span></span>  
  
-   <span data-ttu-id="d64de-109">NE</span><span class="sxs-lookup"><span data-stu-id="d64de-109">NE</span></span>  
  
-   <span data-ttu-id="d64de-110">IGNORE</span><span class="sxs-lookup"><span data-stu-id="d64de-110">IGNORE</span></span>  
  
 <span data-ttu-id="d64de-111">Si se intenta realizar cualquier otra comparación, se obtiene DB_E_BADCOMPAREOP.</span><span class="sxs-lookup"><span data-stu-id="d64de-111">If any other comparison is attempted, DB_E_BADCOMPAREOP is returned.</span></span> <span data-ttu-id="d64de-112">Esto es coherente con la especificación OLE DB.</span><span class="sxs-lookup"><span data-stu-id="d64de-112">This is consistent with the OLE DB specification.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d64de-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d64de-113">See Also</span></span>  
 [<span data-ttu-id="d64de-114">Mejoras de fecha y hora &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="d64de-114">Date and Time Improvements &#40;OLE DB&#41;</span></span>](date-and-time-improvements-ole-db.md)  
  
  
