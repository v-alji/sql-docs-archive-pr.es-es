---
title: IBCPSession (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- IBCPSession interface
ms.assetid: 00d0311f-8b71-4ad6-824d-0e89119347a3
author: rothja
ms.author: jroth
ms.openlocfilehash: 0d32da9c06a200d5924dbae18d6b7513f46c88ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749266"
---
# <a name="ibcpsession-ole-db"></a><span data-ttu-id="649fe-102">IBCPSession (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="649fe-102">IBCPSession (OLE DB)</span></span>
  <span data-ttu-id="649fe-103">La interfaz **IBCPSession** expone compatibilidad con las operaciones de copia masiva basadas en archivos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="649fe-103">The **IBCPSession** interface exposes support for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] file-based bulk copy operations.</span></span> <span data-ttu-id="649fe-104">La interfaz **IBCPSession** se expone en el proveedor OLE DB de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, bajo el mismo nivel que Sessions.</span><span class="sxs-lookup"><span data-stu-id="649fe-104">The **IBCPSession** interface is exposed in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider under the same level as Sessions.</span></span> <span data-ttu-id="649fe-105">En el proveedor OLE DB de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, los objetos de origen de datos son los generadores de los objetos Session y las operaciones de copia masiva se especifican en la propiedad de conexión SSPROP_ENABLEBULKCOPY.</span><span class="sxs-lookup"><span data-stu-id="649fe-105">In the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, data source objects are factories for Session objects, and bulk copy operations are specified in the connection property SSPROP_ENABLEBULKCOPY.</span></span> <span data-ttu-id="649fe-106">Además, la propiedad SSPROP_ENABLEFASTLOAD debe establecerse en True.</span><span class="sxs-lookup"><span data-stu-id="649fe-106">In addition, the SSPROP_ENABLEFASTLOAD property should be set to true.</span></span>  
  
 <span data-ttu-id="649fe-107">Una llamada al método **IDBCreateSession::CreateSession** dará lugar a la creación de un objeto **BulkCopySession** .</span><span class="sxs-lookup"><span data-stu-id="649fe-107">Calling the **IDBCreateSession::CreateSession** method will then result in the creation of a **BulkCopySession** object.</span></span> <span data-ttu-id="649fe-108">Todos los métodos de copia masiva basados en archivos que se expongan a través del objeto **IBCPSession** serán entonces invocables con firmas casi similares en la interfaz **IBCPSession** de este objeto **IBCPSession** .</span><span class="sxs-lookup"><span data-stu-id="649fe-108">All the file-based bulk copy methods exposed through the **IBCPSession** object are then callable with nearly similar signatures on this **IBCPSession** object's **IBCPSession** interface.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="649fe-109">El proveedor OLE DB de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client es compatible con las operaciones de copia masiva basadas en memoria a través de la interfaz [IRowsetFastLoad](irowsetfastload-ole-db.md) .</span><span class="sxs-lookup"><span data-stu-id="649fe-109">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports memory-based bulk copy operations through the [IRowsetFastLoad](irowsetfastload-ole-db.md) interface.</span></span>  
  
 <span data-ttu-id="649fe-110">Para obtener más información sobre el uso del [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client para las operaciones de copia masiva, vea [realizar operaciones de copia masiva](../native-client/features/performing-bulk-copy-operations.md).</span><span class="sxs-lookup"><span data-stu-id="649fe-110">For more information about using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider for bulk copy operations, see [Performing Bulk Copy Operations](../native-client/features/performing-bulk-copy-operations.md).</span></span>  
  
 <span data-ttu-id="649fe-111">Para obtener un ejemplo en que se muestra cómo utilizar la interfaz **IBCPSession**, consulte [IBCPSession::BCPDone &#40;OLE DB&#41;](ibcpsession-bcpdone-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="649fe-111">For a sample showing how to use the **IBCPSession** interface, see [IBCPSession::BCPDone &#40;OLE DB&#41;](ibcpsession-bcpdone-ole-db.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="649fe-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="649fe-112">In This Section</span></span>  
  
|<span data-ttu-id="649fe-113">Método</span><span class="sxs-lookup"><span data-stu-id="649fe-113">Method</span></span>|<span data-ttu-id="649fe-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="649fe-114">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="649fe-115">IBCPSession::BCPColFmt &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="649fe-115">IBCPSession::BCPColFmt &#40;OLE DB&#41;</span></span>](ibcpsession-bcpcolfmt-ole-db.md)|<span data-ttu-id="649fe-116">Crea un enlace entre las variables de programa y las columnas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="649fe-116">Creates a binding between program variables and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] columns.</span></span>|  
|[<span data-ttu-id="649fe-117">IBCPSession::BCPColumns &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="649fe-117">IBCPSession::BCPColumns &#40;OLE DB&#41;</span></span>](ibcpsession-bcpcolumns-ole-db.md)|<span data-ttu-id="649fe-118">Establece el número de campos que van a enlazarse a las columnas en una tabla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="649fe-118">Sets the number of fields that are to be bound to the columns in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>|  
|[<span data-ttu-id="649fe-119">IBCPSession::BCPControl &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="649fe-119">IBCPSession::BCPControl &#40;OLE DB&#41;</span></span>](ibcpsession-bcpcontrol-ole-db.md)|<span data-ttu-id="649fe-120">Establece las opciones de una operación de copia masiva.</span><span class="sxs-lookup"><span data-stu-id="649fe-120">Sets the options for a bulk copy operation.</span></span>|  
|[<span data-ttu-id="649fe-121">IBCPSession::BCPDone &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="649fe-121">IBCPSession::BCPDone &#40;OLE DB&#41;</span></span>](ibcpsession-bcpdone-ole-db.md)|<span data-ttu-id="649fe-122">Confirma las filas restantes que van a enviarse a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="649fe-122">Commits the remaining rows to be sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="649fe-123">IBCPSession::BCPExec &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="649fe-123">IBCPSession::BCPExec &#40;OLE DB&#41;</span></span>](ibcpsession-bcpexec-ole-db.md)|<span data-ttu-id="649fe-124">Realiza la operación de copia masiva.</span><span class="sxs-lookup"><span data-stu-id="649fe-124">Performs the bulk copy operation.</span></span>|  
|[<span data-ttu-id="649fe-125">IBCPSession::BCPInit &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="649fe-125">IBCPSession::BCPInit &#40;OLE DB&#41;</span></span>](ibcpsession-bcpinit-ole-db.md)|<span data-ttu-id="649fe-126">Inicializa la estructura de copia masiva, realiza algunas comprobaciones de errores, comprueba que los datos y los nombres de archivo de formato son correctos y, a continuación, los abre.</span><span class="sxs-lookup"><span data-stu-id="649fe-126">Initializes the bulk copy structure, performs some error checking, verifies that the data and format file names are correct, and then opens them.</span></span>|  
|[<span data-ttu-id="649fe-127">IBCPSession::BCPReadFmt &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="649fe-127">IBCPSession::BCPReadFmt &#40;OLE DB&#41;</span></span>](ibcpsession-bcpreadfmt-ole-db.md)|<span data-ttu-id="649fe-128">Lee la información de formato de cada columna en el archivo de formato.</span><span class="sxs-lookup"><span data-stu-id="649fe-128">Reads format information for each column from the format file.</span></span>|  
|[<span data-ttu-id="649fe-129">IBCPSession::BCPWriteFmt &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="649fe-129">IBCPSession::BCPWriteFmt &#40;OLE DB&#41;</span></span>](ibcpsession-bcpwritefmt-ole-db.md)|<span data-ttu-id="649fe-130">Escribe la información de formato de cada columna en el archivo de formato.</span><span class="sxs-lookup"><span data-stu-id="649fe-130">Writes format information for each column to the format file.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="649fe-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="649fe-131">See Also</span></span>  
 [<span data-ttu-id="649fe-132">Interfaces &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="649fe-132">Interfaces &#40;OLE DB&#41;</span></span>](../../database-engine/dev-guide/interfaces-ole-db.md)  
  
  
