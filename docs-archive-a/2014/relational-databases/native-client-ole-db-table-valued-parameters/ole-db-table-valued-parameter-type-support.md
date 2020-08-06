---
title: Compatibilidad con tipos de parámetros con valores de tabla de OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (OLE DB), API support (OLE DB)
ms.assetid: 147036a0-260e-4f81-8b3b-89209e023a32
author: rothja
ms.author: jroth
ms.openlocfilehash: 48d5fd780b2eaa2fc18e39071d3b10fde897b82c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671018"
---
# <a name="ole-db-table-valued-parameter-type-support"></a><span data-ttu-id="818d5-102">Compatibilidad con tipos de parámetros con valores de tablas de OLE DB</span><span class="sxs-lookup"><span data-stu-id="818d5-102">OLE DB Table-Valued Parameter Type Support</span></span>
  <span data-ttu-id="818d5-103">En este tema se describe la compatibilidad de tipos OLE DB para parámetros con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="818d5-103">This topic describes OLE DB type support for table-value parameters.</span></span>  
  
## <a name="table-valued-parameter-rowset-object"></a><span data-ttu-id="818d5-104">Objeto de conjunto de filas de parámetro con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="818d5-104">Table-Valued Parameter Rowset Object</span></span>  
 <span data-ttu-id="818d5-105">Puede crear un objeto de conjunto de filas especializado para parámetros con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="818d5-105">You can create a specialized rowset object for table-valued parameters.</span></span> <span data-ttu-id="818d5-106">El objeto de conjunto de filas de parámetros con valores de tabla se crea mediante ITableDefinitionWithConstraints::CreateTableWithConstraints o IOpenRowset::OpenRowset.</span><span class="sxs-lookup"><span data-stu-id="818d5-106">You create the table-valued parameter rowset object by using ITableDefinitionWithConstraints::CreateTableWithConstraints or IOpenRowset::OpenRowset.</span></span> <span data-ttu-id="818d5-107">Para hacerlo, establezca el miembro *eKind* del parámetro *pTableID* en DBKIND_GUID_NAME y suministre CLSID_ROWSET_INMEMORY como miembro de *guid*.</span><span class="sxs-lookup"><span data-stu-id="818d5-107">To do this, set the *eKind* member of the *pTableID* parameter to DBKIND_GUID_NAME, and provide the CLSID_ROWSET_INMEMORY as the *guid* member.</span></span> <span data-ttu-id="818d5-108">El nombre de tipo de servidor de parámetros con valores de tabla debe especificarse en el miembro *pwszName* de *pTableID* cuando se usa IOpenRowset::OpenRowset.</span><span class="sxs-lookup"><span data-stu-id="818d5-108">The server type name for the table-valued parameter must be specified in the *pwszName* member of *pTableID* when using IOpenRowset::OpenRowset.</span></span> <span data-ttu-id="818d5-109">El objeto de conjunto de filas de parámetro con valores de tabla se comporta como un objeto normal de proveedor OLE DB de SQL Server Native Client.</span><span class="sxs-lookup"><span data-stu-id="818d5-109">The table-valued parameter rowset object behaves like a regular SQL Server Native Client OLE DB Provider object.</span></span>  
  
```  
const GUID CLSID_ROWSET_TVP =   
{0xc7ef28d5, 0x7bee, 0x443f, {0x86, 0xda, 0xe3, 0x98, 0x4f, 0xcd, 0x4d, 0xf9}};  
  
CoType RowsetTVP  
{  
[mandatory] interface IAccessor;  
[mandatory] interface IColumnsInfo;  
[mandatory] interface IConvertType;  
[mandatory] interface IRowset;  
[mandatory] interface IRowsetInfo;  
[optional]  interface IColumnsRowset;  
[optional]  interface IRowsetChange;  
[optional]  interface ISupportErrorInfo;  
};  
```  
  
## <a name="dbtype_table"></a><span data-ttu-id="818d5-110">DBTYPE_TABLE</span><span class="sxs-lookup"><span data-stu-id="818d5-110">DBTYPE_TABLE</span></span>  
 <span data-ttu-id="818d5-111">DBTYPE_TABLE es un nuevo tipo que representa un tipo de tabla.</span><span class="sxs-lookup"><span data-stu-id="818d5-111">A new type, DBTYPE_TABLE, represents a table type.</span></span> <span data-ttu-id="818d5-112">Este tipo especifica los parámetros con valores de tabla de varias interfaces OLE DB donde se requiere un DBTYPE.</span><span class="sxs-lookup"><span data-stu-id="818d5-112">This type specifies table-valued parameters in various OLE DB interfaces where a DBTYPE is required.</span></span>  
  
```  
#define DBTYPE_TABLE (143)  
```  
  
 <span data-ttu-id="818d5-113">DBTYPE_TABLE tiene el mismo formato que DBTYPE_IUNKNOWN.</span><span class="sxs-lookup"><span data-stu-id="818d5-113">DBTYPE_TABLE has the same format as DBTYPE_IUNKNOWN.</span></span> <span data-ttu-id="818d5-114">Es un puntero a un objeto del búfer de datos.</span><span class="sxs-lookup"><span data-stu-id="818d5-114">It is a pointer to an object in the data buffer.</span></span> <span data-ttu-id="818d5-115">Para obtener una especificación completa en los enlaces, el consumidor rellena el búfer DBOBJECT, con *iid* establecido en una de las interfaces del objeto de conjunto de filas (IID_IRowset).</span><span class="sxs-lookup"><span data-stu-id="818d5-115">For complete specification in the bindings, the consumer fills up the DBOBJECT buffer, with *iid* set to one of the rowset object interfaces (IID_IRowset).</span></span> <span data-ttu-id="818d5-116">Si no se especifica DBOBJECT en ninguno de los enlaces, se da por supuesto el uso de IID_IRowset.</span><span class="sxs-lookup"><span data-stu-id="818d5-116">If no DBOBJECT is specified in the bindings, IID_IRowset will be assumed.</span></span>  
  
 <span data-ttu-id="818d5-117">No se admiten conversiones a DBTYPE_TABLE ni desde DBTYPE_TABLE para cualquier otro tipo.</span><span class="sxs-lookup"><span data-stu-id="818d5-117">Conversions to and from DBTYPE_TABLE for any other types are not supported.</span></span> <span data-ttu-id="818d5-118">IConvertType::CanConvert devolverá S_FALSE si no se permite la conversión para cualquier solicitud de conversión que no sea de DBTYPE_TABLE a DBTYPE_TABLE.</span><span class="sxs-lookup"><span data-stu-id="818d5-118">IConvertType::CanConvert will return S_FALSE for unsupported conversion for any request other than DBTYPE_TABLE to DBTYPE_TABLE conversion.</span></span> <span data-ttu-id="818d5-119">Para ello, se da por supuesto el uso de DBCONVERTFLAGS_PARAMETER en el objeto Command.</span><span class="sxs-lookup"><span data-stu-id="818d5-119">This assumes DBCONVERTFLAGS_PARAMETER on the Command object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="818d5-120">Métodos</span><span class="sxs-lookup"><span data-stu-id="818d5-120">Methods</span></span>  
 <span data-ttu-id="818d5-121">Para información sobre los métodos de OLE DB que admiten parámetros con valores de tabla, consulte [Compatibilidad con tipos de parámetro con valores de tabla de OLE DB &#40;métodos&#41;](ole-db-table-valued-parameter-type-support-methods.md).</span><span class="sxs-lookup"><span data-stu-id="818d5-121">For information about OLE DB methods that support table-valued parameters, see [OLE DB Table-Valued Parameter Type Support &#40;Methods&#41;](ole-db-table-valued-parameter-type-support-methods.md).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="818d5-122">Propiedades</span><span class="sxs-lookup"><span data-stu-id="818d5-122">Properties</span></span>  
 <span data-ttu-id="818d5-123">Para información sobre las propiedades de OLE DB que admiten parámetros con valores de tabla, consulte [Compatibilidad con tipos de parámetros con valores de tabla de OLE DB &#40;propiedades&#41;](ole-db-table-valued-parameter-type-support-properties.md).</span><span class="sxs-lookup"><span data-stu-id="818d5-123">For information about OLE DB properties that support table-valued parameters, see [OLE DB Table-Valued Parameter Type Support &#40;Properties&#41;](ole-db-table-valued-parameter-type-support-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="818d5-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="818d5-124">See Also</span></span>  
 <span data-ttu-id="818d5-125">[Parámetros con valores de tabla &#40;OLE DB&#41;](table-valued-parameters-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="818d5-125">[Table-Valued Parameters &#40;OLE DB&#41;](table-valued-parameters-ole-db.md) </span></span>  
 [<span data-ttu-id="818d5-126">Usar parámetros con valores de tabla &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="818d5-126">Use Table-Valued Parameters &#40;OLE DB&#41;</span></span>](../native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md)  
  
  
