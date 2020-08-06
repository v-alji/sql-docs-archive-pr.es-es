---
title: IRowsetFastLoad::Commit (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IRowsetFastLoad::Commit (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- Commit method
ms.assetid: 19de9128-b91a-4626-847f-af721edaa24e
author: rothja
ms.author: jroth
ms.openlocfilehash: cfdf355919f65fd2cedacd09249e2aae59321390
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676482"
---
# <a name="irowsetfastloadcommit-ole-db"></a><span data-ttu-id="503ff-102">IRowsetFastLoad::Commit (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="503ff-102">IRowsetFastLoad::Commit (OLE DB)</span></span>
  <span data-ttu-id="503ff-103">Marca el final de un lote de filas insertadas y escribe las filas en la tabla [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="503ff-103">Marks the end of a batch of inserted rows and writes the rows to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="503ff-104">Para ver ejemplos, consulte [Copiar datos de forma masiva mediante IRowsetFastLoad &#40;OLE DB&#41;](irowsetfastload-ole-db.md) y [Enviar datos BLOB a SQL SERVER mediante IROWSETFASTLOAD e ISEQUENTIALSTREAM &#40;OLE DB&#41;](../native-client-ole-db-how-to/send-blob-data-to-sql-server-using-irowsetfastload-and-isequentialstream-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="503ff-104">For samples, see [Bulk Copy Data Using IRowsetFastLoad &#40;OLE DB&#41;](irowsetfastload-ole-db.md) and [Send BLOB Data to SQL SERVER Using IROWSETFASTLOAD and ISEQUENTIALSTREAM &#40;OLE DB&#41;](../native-client-ole-db-how-to/send-blob-data-to-sql-server-using-irowsetfastload-and-isequentialstream-ole-db.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="503ff-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="503ff-105">Syntax</span></span>  
  
```  
  
HRESULT Commit(  
BOOL   
fDone  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="503ff-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="503ff-106">Arguments</span></span>  
 <span data-ttu-id="503ff-107">*fDone*[in]</span><span class="sxs-lookup"><span data-stu-id="503ff-107">*fDone*[in]</span></span>  
 <span data-ttu-id="503ff-108">Si es FALSE, el conjunto de filas mantiene la validez y el consumidor puede usarlo para una inserción de filas adicional.</span><span class="sxs-lookup"><span data-stu-id="503ff-108">If FALSE, the rowset maintains validity and can be used by the consumer for additional row insertion.</span></span> <span data-ttu-id="503ff-109">Si es TRUE, el conjunto de filas pierde su validez y el consumidor no puede realizar ninguna inserción más.</span><span class="sxs-lookup"><span data-stu-id="503ff-109">If TRUE, the rowset loses validity and no further insertion can be done by the consumer.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="503ff-110">Valores de código de retorno</span><span class="sxs-lookup"><span data-stu-id="503ff-110">Return Code Values</span></span>  
 <span data-ttu-id="503ff-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="503ff-111">S_OK</span></span>  
 <span data-ttu-id="503ff-112">El método se ejecutó correctamente y todos los datos insertados se escribieron en la tabla [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="503ff-112">The method succeeded and all inserted data has been written to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="503ff-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="503ff-113">E_FAIL</span></span>  
 <span data-ttu-id="503ff-114">Se produjo un error específico del proveedor.</span><span class="sxs-lookup"><span data-stu-id="503ff-114">A provider-specific error occurred.</span></span> <span data-ttu-id="503ff-115">Recupere la información de error para el texto de error específico del proveedor.</span><span class="sxs-lookup"><span data-stu-id="503ff-115">Retrieve error information for the specific error text from the provider.</span></span>  
  
 <span data-ttu-id="503ff-116">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="503ff-116">E_UNEXPECTED</span></span>  
 <span data-ttu-id="503ff-117">Se ha llamado al método en un conjunto de filas de copia masiva previamente invalidado por el método **IRowsetFastLoad::Commit**.</span><span class="sxs-lookup"><span data-stu-id="503ff-117">The method was called on a bulk copy rowset previously invalidated by the **IRowsetFastLoad::Commit** method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="503ff-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="503ff-118">Remarks</span></span>  
 <span data-ttu-id="503ff-119">Un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conjunto de filas de copia masiva del proveedor de OLE DB de Native Client se comporta como un conjunto de filas del modo de actualización retrasada.</span><span class="sxs-lookup"><span data-stu-id="503ff-119">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider bulk copy rowset behaves as a delayed-update mode rowset.</span></span> <span data-ttu-id="503ff-120">A medida que el usuario inserta los datos de fila a través del conjunto de filas, las filas insertadas reciben el mismo trato que las inserciones pendientes en un conjunto de filas que admite **IRowsetUpdate**.</span><span class="sxs-lookup"><span data-stu-id="503ff-120">As the user inserts row data through the rowset, inserted rows are treated in the same fashion as pending inserts on a rowset supporting **IRowsetUpdate**.</span></span>  
  
 <span data-ttu-id="503ff-121">El consumidor debe llamar al método **Commit** en el conjunto de filas de copia masiva para escribir las filas insertadas en la tabla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] del mismo modo en que se usa el método **IRowsetUpdate::Update** para enviar las filas pendientes a una instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="503ff-121">The consumer must call the **Commit** method on the bulk copy rowset to write inserted rows to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table in the same way as the **IRowsetUpdate::Update** method is used to submit pending rows to an instance of SQL Server.</span></span>  
  
 <span data-ttu-id="503ff-122">Si el consumidor libera su referencia en el conjunto de filas de copia masiva sin llamar al método **Commit**, se perderán todas las filas insertadas que no se hayan escrito previamente.</span><span class="sxs-lookup"><span data-stu-id="503ff-122">If the consumer releases its reference on the bulk copy rowset without calling the **Commit** method, all inserted rows not previously written are lost.</span></span>  
  
 <span data-ttu-id="503ff-123">El consumidor puede procesar por lotes las filas insertadas mediante una llamada al método **Commit** con el argumento *fDone* establecido en FALSE.</span><span class="sxs-lookup"><span data-stu-id="503ff-123">The consumer can batch inserted rows by calling the **Commit** method with the *fDone* argument set to FALSE.</span></span> <span data-ttu-id="503ff-124">Cuando *fDone* se establece en TRUE, el conjunto de filas deja de ser válido.</span><span class="sxs-lookup"><span data-stu-id="503ff-124">When *fDone*is set to TRUE, the rowset becomes invalid.</span></span> <span data-ttu-id="503ff-125">Un conjunto de filas de copia masiva que no es válido solo admite la interfaz **ISupportErrorInfo** y el método **IRowsetFastLoad::Release**.</span><span class="sxs-lookup"><span data-stu-id="503ff-125">An invalid bulk copy rowset supports only the **ISupportErrorInfo** interface and **IRowsetFastLoad::Release** method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="503ff-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="503ff-126">See Also</span></span>  
 [<span data-ttu-id="503ff-127">IRowsetFastLoad &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="503ff-127">IRowsetFastLoad &#40;OLE DB&#41;</span></span>](irowsetfastload-ole-db.md)  
  
  
