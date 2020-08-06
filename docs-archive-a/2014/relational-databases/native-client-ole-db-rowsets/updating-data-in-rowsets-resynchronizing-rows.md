---
title: Resincronización de filas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- synchronization [OLE DB]
- IRowsetResynch interface
- resynchronizing rows
- data updates [SQL Server], OLE DB
ms.assetid: d2d30505-a878-4aa9-b821-53d8118a45a5
author: rothja
ms.author: jroth
ms.openlocfilehash: 47c628ae583f3e635f422d5146f64508372a1114
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670367"
---
# <a name="resynchronizing-rows"></a><span data-ttu-id="2f493-102">Volver a sincronizar filas</span><span class="sxs-lookup"><span data-stu-id="2f493-102">Resynchronizing Rows</span></span>
  <span data-ttu-id="2f493-103">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client admite **IRowsetResynch** [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] solo en conjuntos de filas admitidos por el cursor.</span><span class="sxs-lookup"><span data-stu-id="2f493-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports **IRowsetResynch** on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cursor-supported rowsets only.</span></span> <span data-ttu-id="2f493-104">**IRowsetResynch** no está disponible a petición.</span><span class="sxs-lookup"><span data-stu-id="2f493-104">**IRowsetResynch** is not available on demand.</span></span> <span data-ttu-id="2f493-105">El consumidor debe solicitar la interfaz antes de abrir el conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="2f493-105">The consumer must request the interface before opening the rowset.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f493-106">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2f493-106">See Also</span></span>  
 [<span data-ttu-id="2f493-107">Actualizar datos en conjuntos de filas</span><span class="sxs-lookup"><span data-stu-id="2f493-107">Updating Data in Rowsets</span></span>](updating-data-in-rowsets.md)  
  
  
