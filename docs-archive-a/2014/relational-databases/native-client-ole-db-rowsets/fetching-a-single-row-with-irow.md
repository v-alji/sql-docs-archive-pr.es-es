---
title: Captura de una sola fila con IRow | Microsoft Docs
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
- SQL Server Native Client OLE DB provider, fetching
ms.assetid: 07c803ca-299a-42c5-ba02-360b9631d15f
author: rothja
ms.author: jroth
ms.openlocfilehash: b5573fe1fef39f29329e373323f5f8aaf15f2c58
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675824"
---
# <a name="fetching-a-single-row-with-irow"></a><span data-ttu-id="83ff4-102">Capturar una única fila con IRow</span><span class="sxs-lookup"><span data-stu-id="83ff4-102">Fetching a Single Row with IRow</span></span>
  <span data-ttu-id="83ff4-103">La implementación de la interfaz **IRow** en el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client se ha simplificado para aumentar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="83ff4-103">The **IRow** interface implementation in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider is simplified to increase performance.</span></span> <span data-ttu-id="83ff4-104">**IRow** permite un acceso directo a las columnas de un único objeto de fila.</span><span class="sxs-lookup"><span data-stu-id="83ff4-104">**IRow** allows direct access to columns of a single row object.</span></span> <span data-ttu-id="83ff4-105">Si sabe de antemano que el resultado de una ejecución de comandos generará exactamente una fila, **IRow** recuperará las columnas de esa fila.</span><span class="sxs-lookup"><span data-stu-id="83ff4-105">If you know beforehand that the result of a command execution will produce exactly one row, **IRow** will retrieve the columns of that row.</span></span> <span data-ttu-id="83ff4-106">Si el conjunto de resultados incluye varias filas, **IRow** solo expondrá la primera.</span><span class="sxs-lookup"><span data-stu-id="83ff4-106">If the result set includes multiple rows, **IRow** will expose only the first row.</span></span>  
  
 <span data-ttu-id="83ff4-107">La implementación de **IRow** no permite cualquier navegación de la fila.</span><span class="sxs-lookup"><span data-stu-id="83ff4-107">The **IRow** implementation does not allow any navigation of the row.</span></span> <span data-ttu-id="83ff4-108">Solo se obtiene acceso una vez a cada columna de la fila, con una excepción: se puede obtener acceso a una columna una primera vez para buscar el tamaño de la columna y una segunda vez para capturar los datos.</span><span class="sxs-lookup"><span data-stu-id="83ff4-108">Each column in the row is accessed only one time with one exception: A column can be accessed one time to find the column size and again to fetch the data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="83ff4-109">**IRow::Open** solo permite la apertura de objetos de tipo DBGUID_STREAM y DBGUID_NULL.</span><span class="sxs-lookup"><span data-stu-id="83ff4-109">**IRow::Open** supports only DBGUID_STREAM and DBGUID_NULL type of objects to be opened.</span></span>  
  
 <span data-ttu-id="83ff4-110">Para obtener un objeto de fila mediante el método **ICommand::Execute**, tiene que pasarse IID_IRow.</span><span class="sxs-lookup"><span data-stu-id="83ff4-110">To obtain a row object using **ICommand::Execute** method, IID_IRow must be passed.</span></span> <span data-ttu-id="83ff4-111">La interfaz **IMultipleResults** tiene que usarse para controlar varios conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="83ff4-111">The **IMultipleResults** interface must be used to handle multiple result sets.</span></span> <span data-ttu-id="83ff4-112">**IMultipleResults** admite **IRow** e **IRowset**.</span><span class="sxs-lookup"><span data-stu-id="83ff4-112">**IMultipleResults** supports **IRow** and **IRowset**.</span></span> <span data-ttu-id="83ff4-113">**IRowset** se usa para las operaciones masivas.</span><span class="sxs-lookup"><span data-stu-id="83ff4-113">**IRowset** is used for bulk operations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="83ff4-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="83ff4-114">In This Section</span></span>  
  
-   [<span data-ttu-id="83ff4-115">Usar IRow::GetColumns</span><span class="sxs-lookup"><span data-stu-id="83ff4-115">Using IRow::GetColumns</span></span>](using-irow-getcolumns.md)  
  
-   [<span data-ttu-id="83ff4-116">Capturar datos BLOB mediante IRow</span><span class="sxs-lookup"><span data-stu-id="83ff4-116">Fetching BLOB Data Using IRow</span></span>](../../database-engine/dev-guide/fetching-blob-data-using-irow.md)  
  
## <a name="see-also"></a><span data-ttu-id="83ff4-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="83ff4-117">See Also</span></span>  
 [<span data-ttu-id="83ff4-118">Conjuntos de filas</span><span class="sxs-lookup"><span data-stu-id="83ff4-118">Rowsets</span></span>](rowsets.md)  
  
  
