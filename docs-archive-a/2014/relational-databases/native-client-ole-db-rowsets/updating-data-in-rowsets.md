---
title: Actualización de datos de conjuntos de filas | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- updating data [SQL Server]
- rowsets [OLE DB], updating data
- SQL Server Native Client OLE DB provider, rowsets
- OLE DB rowsets, updating data
- SQL Server Native Client OLE DB provider, data updates
- data updates [SQL Server], OLE DB
ms.assetid: 37769b1c-c480-419a-8c54-5cc420bf73db
author: rothja
ms.author: jroth
ms.openlocfilehash: 993cfb67d4e6b72eec7cc0537e9b47371e94af10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746975"
---
# <a name="updating-data-in-rowsets"></a><span data-ttu-id="2dbd6-102">Actualizar datos en conjuntos de filas</span><span class="sxs-lookup"><span data-stu-id="2dbd6-102">Updating Data in Rowsets</span></span>
  <span data-ttu-id="2dbd6-103">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client actualiza los [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] datos cuando un consumidor actualiza un conjunto de filas modificable que contiene los datos.</span><span class="sxs-lookup"><span data-stu-id="2dbd6-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider updates [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data when a consumer updates a modifiable rowset that contains that data.</span></span> <span data-ttu-id="2dbd6-104">Se crea un conjunto de filas modificable cuando el consumidor solicita compatibilidad para las interfaces **IRowsetUpdate** o **IRowsetChange**.</span><span class="sxs-lookup"><span data-stu-id="2dbd6-104">A modifiable rowset is created when the consumer requests support for either the **IRowsetChange** or **IRowsetUpdate** interface.</span></span>  
  
 <span data-ttu-id="2dbd6-105">Todos los [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conjuntos de filas modificables del proveedor de OLE DB de Native Client utilizan [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cursores para admitir el conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="2dbd6-105">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider-modifiable rowsets use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cursors to support the rowset.</span></span> <span data-ttu-id="2dbd6-106">La propiedad de conjunto de filas DBPROP_LOCKMODE modifica el comportamiento de control de simultaneidad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en cursores y determina el comportamiento de la captura de filas del conjunto de filas y la generación de errores de integridad de datos en los conjuntos de filas actualizables.</span><span class="sxs-lookup"><span data-stu-id="2dbd6-106">The rowset property DBPROP_LOCKMODE alters [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] concurrency control behavior in cursors and determines the behavior of rowset row fetching and data integrity error generation in updatable rowsets.</span></span>  
  
 <span data-ttu-id="2dbd6-107">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client admite la sincronización de filas antes o después de una actualización.</span><span class="sxs-lookup"><span data-stu-id="2dbd6-107">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports row synchronization before or after an update.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2dbd6-108">IRowChange::SetColumns está disponible para establecer los valores de una o más columnas con nombre de un objeto de fila.</span><span class="sxs-lookup"><span data-stu-id="2dbd6-108">IRowChange::SetColumns is available to set the values of one or more named columns of a row object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2dbd6-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2dbd6-109">In This Section</span></span>  
  
-   [<span data-ttu-id="2dbd6-110">Actualizar datos en cursores de SQL Server</span><span class="sxs-lookup"><span data-stu-id="2dbd6-110">Updating Data in SQL Server Cursors</span></span>](updating-data-in-sql-server-cursors.md)  
  
-   [<span data-ttu-id="2dbd6-111">Volver a sincronizar filas</span><span class="sxs-lookup"><span data-stu-id="2dbd6-111">Resynchronizing Rows</span></span>](updating-data-in-rowsets-resynchronizing-rows.md)  
  
## <a name="see-also"></a><span data-ttu-id="2dbd6-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2dbd6-112">See Also</span></span>  
 [<span data-ttu-id="2dbd6-113">Conjuntos de filas</span><span class="sxs-lookup"><span data-stu-id="2dbd6-113">Rowsets</span></span>](rowsets.md)  
  
  
