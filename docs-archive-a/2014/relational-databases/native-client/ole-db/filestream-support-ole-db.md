---
title: Compatibilidad con FILESTREAM (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB [FILESTREAM support]
- FILESTREAM [SQL Server], OLE DB
ms.assetid: c2bd3dfd-6103-43d1-859e-8ed8d19c58d3
author: rothja
ms.author: jroth
ms.openlocfilehash: cde3c2cd1b72773cfcf17eacedeb3276dd2f63da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674786"
---
# <a name="filestream-support-ole-db"></a><span data-ttu-id="696cd-102">Compatibilidad con FILESTREAM (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="696cd-102">FILESTREAM Support (OLE DB)</span></span>
  <span data-ttu-id="696cd-103">A partir de [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] y [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 10,0, OLE DB admite la característica FileStream mejorada.</span><span class="sxs-lookup"><span data-stu-id="696cd-103">Beginning with [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 10.0, OLE DB supports the enhanced FILESTREAM feature.</span></span> <span data-ttu-id="696cd-104">Para obtener más información acerca de esta característica, vea [compatibilidad de FileStream](../features/filestream-support.md).</span><span class="sxs-lookup"><span data-stu-id="696cd-104">For more information about this feature, see [FILESTREAM Support](../features/filestream-support.md).</span></span> <span data-ttu-id="696cd-105">Para ver ejemplos, consulte [FileStream y OLE DB](../../native-client-ole-db-how-to/filestream/filestream-and-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="696cd-105">For samples, see [Filestream and OLE DB](../../native-client-ole-db-how-to/filestream/filestream-and-ole-db.md).</span></span>  
  
 <span data-ttu-id="696cd-106">Para enviar y recibir valores `varbinary(max)` mayores de 2 GB, una aplicación usa `DBTYPE_IUNKNOWN` en enlaces de resultados y parámetros.</span><span class="sxs-lookup"><span data-stu-id="696cd-106">To send and receive `varbinary(max)` values greater than 2 GB, an application uses `DBTYPE_IUNKNOWN` in parameter and result bindings.</span></span> <span data-ttu-id="696cd-107">En el caso de los parámetros, el proveedor debe llamar a IUnknown::QueryInterface para ISequentialStream y para los resultados que devuelven ISequentialStream.</span><span class="sxs-lookup"><span data-stu-id="696cd-107">For parameters the provider must call IUnknown::QueryInterface for ISequentialStream and for results that return ISequentialStream.</span></span>  
  
 <span data-ttu-id="696cd-108">Para OLE DB, la comprobación relacionada con los valores ISequentialStream será menos estricta.</span><span class="sxs-lookup"><span data-stu-id="696cd-108">For OLE DB, checking related to ISequentialStream values will be relaxed.</span></span> <span data-ttu-id="696cd-109">Cuando *wType* está `DBTYPE_IUNKNOWN` en el `DBBINDING` struct, la comprobación de longitud se puede deshabilitar omitiendo `DBPART_LENGTH` en *dwPart* o estableciendo la longitud de los datos (en el desplazamiento *obLength* en el búfer de datos) en ~ 0.</span><span class="sxs-lookup"><span data-stu-id="696cd-109">When *wType* is `DBTYPE_IUNKNOWN` in the `DBBINDING` struct, length checking can be disabled either by omitting `DBPART_LENGTH` from *dwPart* or by setting the length of the data (at offset *obLength* in the data buffer) to ~0.</span></span> <span data-ttu-id="696cd-110">En este caso, el proveedor no comprobará la longitud del valor y solicitará y devolverá todos los datos disponibles a través del flujo.</span><span class="sxs-lookup"><span data-stu-id="696cd-110">In this case, the provider will not check the length of the value and will request and return all of the data available through the stream.</span></span> <span data-ttu-id="696cd-111">Este cambio se aplicará a todos los tipos de objeto grandes (LOB) y XML, pero solo cuando se realice la conexión a los servidores [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] (o posteriores).</span><span class="sxs-lookup"><span data-stu-id="696cd-111">This change will be applied to all large object (LOB) types and XML, but only when connected to [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] (or later) servers.</span></span> <span data-ttu-id="696cd-112">Esto proporcionará mayor flexibilidad para los programadores, a la vez que se mantendrá la coherencia y la compatibilidad con versiones anteriores para las aplicaciones existentes y los servidores de nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="696cd-112">This will provide greater flexibility for developers, while maintaining consistency and backwards compatibility for existing applications and downlevel servers.</span></span>  
  
 <span data-ttu-id="696cd-113">Este cambio afecta a todas las interfaces que transfieren datos, principalmente IRowset::GetData, ICommand::Execute y IRowsetFastLoad::InsertRow.</span><span class="sxs-lookup"><span data-stu-id="696cd-113">This change affects all interfaces that transfer data, principally IRowset::GetData, ICommand::Execute, and IRowsetFastLoad::InsertRow.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="696cd-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="696cd-114">See Also</span></span>  
 [<span data-ttu-id="696cd-115">Programación de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="696cd-115">SQL Server Native Client Programming</span></span>](../sql-server-native-client-programming.md)  
  
  
