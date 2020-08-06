---
title: Siguiente posición de captura | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- fetching rows
- OLE DB rowsets, fetching
- next fetch position
- rowsets [OLE DB], fetching
ms.assetid: 9ef74b3f-c9c0-492f-9b93-d65738a61abd
author: rothja
ms.author: jroth
ms.openlocfilehash: fcc771eef4acf603148bc4b4318e810b1bd72302
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744671"
---
# <a name="next-fetch-position"></a><span data-ttu-id="8824c-102">Posición de captura siguiente</span><span class="sxs-lookup"><span data-stu-id="8824c-102">Next Fetch Position</span></span>
  <span data-ttu-id="8824c-103">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client realiza un seguimiento de la siguiente posición de captura para que una secuencia de llamadas al método **GetNextRows** (sin omitidos, cambios de dirección o llamadas intermedias a los métodos **FindNextRow**, **Seek**o **RestartPosition** ) Lea todo el conjunto de filas sin omitir o repetir ninguna fila.</span><span class="sxs-lookup"><span data-stu-id="8824c-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider keeps track of the next fetch position so that a sequence of calls to the **GetNextRows** method (without skips, changes of direction, or intervening calls to the **FindNextRow**, **Seek**, or **RestartPosition** methods) reads the whole rowset without skipping or repeating any row.</span></span> <span data-ttu-id="8824c-104">La siguiente posición de captura cambia mediante una llamada a **IRowset::GetNextRows**, **IRowset::RestartPosition** o **IRowsetIndex::Seek**, o bien mediante una llamada a **FindNextRow** con un valor *pBookmark* NULL.</span><span class="sxs-lookup"><span data-stu-id="8824c-104">The next fetch position is changed either by calling **IRowset::GetNextRows**, **IRowset::RestartPosition**, or **IRowsetIndex::Seek**, or by calling **FindNextRow** with a null *pBookmark* value.</span></span> <span data-ttu-id="8824c-105">La llamada a **FindNextRow** con un valor *pBookmark* que no sea NULL no afecta a la siguiente posición de captura.</span><span class="sxs-lookup"><span data-stu-id="8824c-105">Calling **FindNextRow** with a nonnull *pBookmark* value does not affect the next fetch position.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8824c-106">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8824c-106">See Also</span></span>  
 [<span data-ttu-id="8824c-107">Capturar filas</span><span class="sxs-lookup"><span data-stu-id="8824c-107">Fetching Rows</span></span>](fetching-rows.md)  
  
  
