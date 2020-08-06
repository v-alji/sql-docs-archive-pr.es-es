---
title: ISSAbort (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- ISSAbort interface
ms.assetid: 7c4df482-4a83-4da0-802b-3637b507693a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 7195311fefe3f0f1b7b4d6d789aa8d8487bc3bfe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751385"
---
# <a name="issabort-ole-db"></a><span data-ttu-id="6151d-102">ISSAbort (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="6151d-102">ISSAbort (OLE DB)</span></span>
  <span data-ttu-id="6151d-103">La interfaz **ISSAbort** , que se expone en el proveedor OLE DB de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, proporciona el método [ISSAbort::Abort](../../relational-databases/native-client-ole-db-interfaces/issabort-abort-ole-db.md) que se utiliza para cancelar el conjunto de filas actual más los comandos incluidos en el mismo lote que el comando que inicialmente generó el conjunto de filas y que todavía no han completado la ejecución.</span><span class="sxs-lookup"><span data-stu-id="6151d-103">The **ISSAbort** interface, which is exposed in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, provides the [ISSAbort::Abort](../../relational-databases/native-client-ole-db-interfaces/issabort-abort-ole-db.md) method that is used to cancel the current rowset plus any commands batched with the command that initially generated the rowset, and that have not yet completed execution.</span></span>  
  
 <span data-ttu-id="6151d-104">**ISSAbort** es una interfaz específica del proveedor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de Native Client que está disponible cuando se utiliza **QueryInterface** en el objeto **IMultipleResults** devuelto por **ICommand::Execute** o **IOpenRowset::OpenRowset**.</span><span class="sxs-lookup"><span data-stu-id="6151d-104">**ISSAbort** is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client provider-specific interface available by using **QueryInterface** on the **IMultipleResults** object returned by **ICommand::Execute** or **IOpenRowset::OpenRowset**.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6151d-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6151d-105">In This Section</span></span>  
  
|<span data-ttu-id="6151d-106">Método</span><span class="sxs-lookup"><span data-stu-id="6151d-106">Method</span></span>|<span data-ttu-id="6151d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="6151d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6151d-108">ISSAbort:: ABORT &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="6151d-108">ISSAbort::Abort &#40;OLE DB&#41;</span></span>](../../relational-databases/native-client-ole-db-interfaces/issabort-abort-ole-db.md)|<span data-ttu-id="6151d-109">Cancela el conjunto de filas actual y los comandos en lotes asociados al comando actual.</span><span class="sxs-lookup"><span data-stu-id="6151d-109">Cancels the current rowset plus any batched commands associated with the current command.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6151d-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6151d-110">See Also</span></span>  
 [<span data-ttu-id="6151d-111">Interfaces &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="6151d-111">Interfaces &#40;OLE DB&#41;</span></span>](../../../2014/database-engine/dev-guide/interfaces-ole-db.md)  
  
  
