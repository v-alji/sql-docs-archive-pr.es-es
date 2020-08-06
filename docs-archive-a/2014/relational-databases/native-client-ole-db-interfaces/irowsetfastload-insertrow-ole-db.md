---
title: IRowsetFastLoad::InsertRow (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IRowsetFastLoad::InsertRow (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- InsertRow method
ms.assetid: 594d3461-34d2-41e7-8ad4-bd2753601ab6
author: rothja
ms.author: jroth
ms.openlocfilehash: 4e9ea952f27574270ee333919f778814ff3de462
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676478"
---
# <a name="irowsetfastloadinsertrow-ole-db"></a><span data-ttu-id="1080e-102">IRowsetFastLoad::InsertRow (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="1080e-102">IRowsetFastLoad::InsertRow (OLE DB)</span></span>
  <span data-ttu-id="1080e-103">Agrega una fila al conjunto de filas de copia masiva.</span><span class="sxs-lookup"><span data-stu-id="1080e-103">Adds a row to the bulk copy rowset.</span></span> <span data-ttu-id="1080e-104">Para ver ejemplos, consulte [Copiar datos de forma masiva mediante IRowsetFastLoad &#40;OLE DB&#41;](../native-client-ole-db-how-to/bulk-copy-data-using-irowsetfastload-ole-db.md) y [Enviar datos BLOB a SQL SERVER mediante IROWSETFASTLOAD e ISEQUENTIALSTREAM &#40;OLE DB&#41;](../native-client-ole-db-how-to/send-blob-data-to-sql-server-using-irowsetfastload-and-isequentialstream-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="1080e-104">For samples, see [Bulk Copy Data Using IRowsetFastLoad &#40;OLE DB&#41;](../native-client-ole-db-how-to/bulk-copy-data-using-irowsetfastload-ole-db.md) and [Send BLOB Data to SQL SERVER Using IROWSETFASTLOAD and ISEQUENTIALSTREAM &#40;OLE DB&#41;](../native-client-ole-db-how-to/send-blob-data-to-sql-server-using-irowsetfastload-and-isequentialstream-ole-db.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1080e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1080e-105">Syntax</span></span>  
  
```  
  
HRESULT InsertRow(  
HACCESSOR  
hAccessor  
,  
void*  
pData  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="1080e-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="1080e-106">Arguments</span></span>  
 <span data-ttu-id="1080e-107">*hAccessor*[in]</span><span class="sxs-lookup"><span data-stu-id="1080e-107">*hAccessor*[in]</span></span>  
 <span data-ttu-id="1080e-108">El identificador del descriptor de acceso que define los datos de fila para la copia masiva.</span><span class="sxs-lookup"><span data-stu-id="1080e-108">The handle of the accessor defining the row data for bulk copy.</span></span> <span data-ttu-id="1080e-109">El descriptor de acceso al que se hace referencia es un descriptor de acceso de fila, que enlaza la memoria propia del consumidor que contiene los valores de datos.</span><span class="sxs-lookup"><span data-stu-id="1080e-109">The accessor referenced is a row accessor, binding consumer-owned memory containing data values.</span></span>  
  
 <span data-ttu-id="1080e-110">*pData*[in]</span><span class="sxs-lookup"><span data-stu-id="1080e-110">*pData*[in]</span></span>  
 <span data-ttu-id="1080e-111">Puntero a la memoria propia del consumidor que contiene los valores de datos.</span><span class="sxs-lookup"><span data-stu-id="1080e-111">A pointer to the consumer-owned memory containing data values.</span></span> <span data-ttu-id="1080e-112">Para obtener más información, vea [Estructuras DBBINDING](https://go.microsoft.com/fwlink/?LinkId=65955).</span><span class="sxs-lookup"><span data-stu-id="1080e-112">For more information, see [DBBINDING Structures](https://go.microsoft.com/fwlink/?LinkId=65955).</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="1080e-113">Valores de código de retorno</span><span class="sxs-lookup"><span data-stu-id="1080e-113">Return Code Values</span></span>  
 <span data-ttu-id="1080e-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="1080e-114">S_OK</span></span>  
 <span data-ttu-id="1080e-115">El método se ha llevado a cabo de forma correcta.</span><span class="sxs-lookup"><span data-stu-id="1080e-115">The method succeeded.</span></span> <span data-ttu-id="1080e-116">Los valores de estado enlazados de todas las columnas tienen el valor DBSTATUS_S_OK o DBSTATUS_S_NULL.</span><span class="sxs-lookup"><span data-stu-id="1080e-116">Any bound status values for all columns have value DBSTATUS_S_OK or DBSTATUS_S_NULL.</span></span>  
  
 <span data-ttu-id="1080e-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1080e-117">E_FAIL</span></span>  
 <span data-ttu-id="1080e-118">Error.</span><span class="sxs-lookup"><span data-stu-id="1080e-118">An error occurred.</span></span> <span data-ttu-id="1080e-119">Hay información disponible sobre el error en las interfaces de error del conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="1080e-119">Error information is available from the rowset's error interfaces.</span></span>  
  
 <span data-ttu-id="1080e-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="1080e-120">E_INVALIDARG</span></span>  
 <span data-ttu-id="1080e-121">El argumento *pData* se estableció en un puntero NULL.</span><span class="sxs-lookup"><span data-stu-id="1080e-121">The *pData* argument was set to a NULL pointer.</span></span>  
  
 <span data-ttu-id="1080e-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="1080e-122">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="1080e-123">SQLNCLI11 no ha podido asignar la memoria suficiente para completar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="1080e-123">SQLNCLI11 was unable to allocate sufficient memory to complete the request.</span></span>  
  
 <span data-ttu-id="1080e-124">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="1080e-124">E_UNEXPECTED</span></span>  
 <span data-ttu-id="1080e-125">Se ha llamado al método en un conjunto de filas de copia masiva previamente invalidado por el método [IRowsetFastLoad::Commit](irowsetfastload-commit-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="1080e-125">The method was called on a bulk copy rowset previously invalidated by the [IRowsetFastLoad::Commit](irowsetfastload-commit-ole-db.md) method.</span></span>  
  
 <span data-ttu-id="1080e-126">DB_E_BADACCESSORHANDLE</span><span class="sxs-lookup"><span data-stu-id="1080e-126">DB_E_BADACCESSORHANDLE</span></span>  
 <span data-ttu-id="1080e-127">El argumento *hAccessor* proporcionado por el consumidor no era válido.</span><span class="sxs-lookup"><span data-stu-id="1080e-127">The *hAccessor* argument provided by the consumer was invalid.</span></span>  
  
 <span data-ttu-id="1080e-128">DB_E_BADACCESSORTYPE</span><span class="sxs-lookup"><span data-stu-id="1080e-128">DB_E_BADACCESSORTYPE</span></span>  
 <span data-ttu-id="1080e-129">El descriptor de acceso especificado no era un descriptor de acceso de fila o no especificaba la memoria propia del consumidor.</span><span class="sxs-lookup"><span data-stu-id="1080e-129">The specified accessor was not a row accessor or did not specify consumer-owned memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1080e-130">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1080e-130">Remarks</span></span>  
 <span data-ttu-id="1080e-131">Un error al convertir los datos del consumidor al tipo de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de una columna hace que el proveedor OLE DB de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client devuelva E_FAIL.</span><span class="sxs-lookup"><span data-stu-id="1080e-131">An error converting consumer data to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type for a column causes an E_FAIL return from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span> <span data-ttu-id="1080e-132">Los datos se pueden transmitir a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en cualquier método **InsertRow** o solo en el método **Commit**.</span><span class="sxs-lookup"><span data-stu-id="1080e-132">Data can be transmitted to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on any **InsertRow** method or only on **Commit** method.</span></span> <span data-ttu-id="1080e-133">La aplicación de consumidor puede llamar al método **InsertRow** muchas veces con datos erróneos antes de recibir el aviso de que existe un error de conversión de tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="1080e-133">The consumer application can call the **InsertRow** method many times with erroneous data before it receives notice that a data type conversion error exists.</span></span> <span data-ttu-id="1080e-134">Dado que el método **Commit** asegura que el consumidor especifica correctamente todos los datos, este último puede utilizar el método **Commit** adecuadamente para validar los datos según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="1080e-134">Because the **Commit** method ensures that all data is correctly specified by the consumer, the consumer can use the **Commit** method appropriately to validate data as necessary.</span></span>  
  
 <span data-ttu-id="1080e-135">Los conjuntos de filas de copia masiva del proveedor OLE DB de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client son de solo escritura.</span><span class="sxs-lookup"><span data-stu-id="1080e-135">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider bulk copy rowsets are write-only.</span></span> <span data-ttu-id="1080e-136">El proveedor OLE DB de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client no expone ningún método que permita al consumidor consultar el conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="1080e-136">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes no methods allowing consumer query of the rowset.</span></span> <span data-ttu-id="1080e-137">Para finalizar el procesamiento, el consumidor puede liberar su referencia en la interfaz [IRowsetFastLoad](irowsetfastload-ole-db.md) sin llamar al método **Commit**.</span><span class="sxs-lookup"><span data-stu-id="1080e-137">To terminate processing, the consumer can release its reference on the [IRowsetFastLoad](irowsetfastload-ole-db.md) interface without calling the **Commit** method.</span></span> <span data-ttu-id="1080e-138">No hay recursos para obtener acceso a una fila insertada por el consumidor en el conjunto de filas y cambiar sus valores o quitarla individualmente del conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="1080e-138">There are no facilities for accessing a consumer-inserted row in the rowset and changing its values, or removing it individually from the rowset.</span></span>  
  
 <span data-ttu-id="1080e-139">Se da formato a las filas de copia masiva en el servidor para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1080e-139">Bulk copied rows are formatted on the server for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1080e-140">Las opciones que se hayan establecido para la conexión o sesión, como ANSI_PADDING, afectan al formato de fila.</span><span class="sxs-lookup"><span data-stu-id="1080e-140">The row format is affected by any options that may have been set for the connection or session such as ANSI_PADDING.</span></span> <span data-ttu-id="1080e-141">Esta opción está activada de forma predeterminada para las conexiones realizadas a través del proveedor OLE DB de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="1080e-141">This option is set on by default for any connection made through the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1080e-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1080e-142">See Also</span></span>  
 [<span data-ttu-id="1080e-143">IRowsetFastLoad &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="1080e-143">IRowsetFastLoad &#40;OLE DB&#41;</span></span>](irowsetfastload-ole-db.md)  
  
  
