---
title: Uso de IRow::GetColumns | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- fetching rows
- IRow interface
- single row fetching [SQL Server Native Client]
- OLE DB rowsets, fetching
- rowsets [OLE DB], fetching
- GetColumns method
ms.assetid: 1f5d2e03-e6fe-4ea1-b71d-55d02b5d59ae
author: rothja
ms.author: jroth
ms.openlocfilehash: f323dda790946565bc0dbd63c9e1f9d17ac7494b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670362"
---
# <a name="using-irowgetcolumns"></a><span data-ttu-id="ec9b0-102">Usar IRow::GetColumns</span><span class="sxs-lookup"><span data-stu-id="ec9b0-102">Using IRow::GetColumns</span></span>
  <span data-ttu-id="ec9b0-103">La implementación de **IRow** permite el acceso secuencial a las columnas de solo avance.</span><span class="sxs-lookup"><span data-stu-id="ec9b0-103">The **IRow** implementation allows forward-only sequential access to the columns.</span></span> <span data-ttu-id="ec9b0-104">Puede tener acceso a todas las columnas de la fila con una sola llamada a **IRow::GetColumns** o llamar a **IRow::GetColumns** varias veces, cada vez que tenga acceso a varias columnas de la fila.</span><span class="sxs-lookup"><span data-stu-id="ec9b0-104">You can either access all the columns in the row with a single call to **IRow::GetColumns** or call **IRow::GetColumns** multiple times every time that you access several columns in the row.</span></span>  
  
 <span data-ttu-id="ec9b0-105">Se debe evitar que se superpongan varias llamadas a **IRow::GetColumns**.</span><span class="sxs-lookup"><span data-stu-id="ec9b0-105">The multiple calls to **IRow::GetColumns** should not overlap.</span></span> <span data-ttu-id="ec9b0-106">Por ejemplo, si la primera llamada a **IRow::GetColumns** recupera las columnas 1, 2 y 3, la segunda llamada a **IRow::GetColumns** debería recuperar las columnas 4, 5 y 6.</span><span class="sxs-lookup"><span data-stu-id="ec9b0-106">For example, if the first call to **IRow::GetColumns** retrieves columns 1, 2, and 3, the second call to **IRow::GetColumns** should call for columns 4, 5, and 6.</span></span> <span data-ttu-id="ec9b0-107">Si se superponen las llamadas posteriores a **IRow::GetColumns**, la marca de estado (campo dwstatus en DBCOLUMNACCESS) se establece en DBSTATUS_E_UNAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ec9b0-107">If later calls to **IRow::GetColumns** overlap, the status flag (dwstatus field in DBCOLUMNACCESS) is set to DBSTATUS_E_UNAVAILABLE.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec9b0-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ec9b0-108">See Also</span></span>  
 [<span data-ttu-id="ec9b0-109">Capturar una única fila con IRow</span><span class="sxs-lookup"><span data-stu-id="ec9b0-109">Fetching a Single Row with IRow</span></span>](fetching-a-single-row-with-irow.md)  
  
  
