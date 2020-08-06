---
title: Parámetros con valores de tabla (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, table-valued parameters
- table-valued parameters (OLE DB)
ms.assetid: 4298b73d-615b-4d28-9843-03b4d5fc489e
author: rothja
ms.author: jroth
ms.openlocfilehash: 41d125bcb254125d7f7562ca1873e8af03dab929
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748747"
---
# <a name="table-valued-parameters-ole-db"></a><span data-ttu-id="bc061-102">Parámetros con valores de tabla (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="bc061-102">Table-Valued Parameters (OLE DB)</span></span>
  <span data-ttu-id="bc061-103">En esta sección se describe la compatibilidad con parámetros con valores de tabla en el proveedor OLE DB de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="bc061-103">This section describes support for table-valued parameters in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider.</span></span> <span data-ttu-id="bc061-104">Para obtener información general adicional, consulte [parámetros con valores de tabla &#40;SQL Server Native Client&#41;](../native-client/features/table-valued-parameters-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="bc061-104">For additional overview information, see [Table-Valued Parameters &#40;SQL Server Native Client&#41;](../native-client/features/table-valued-parameters-sql-server-native-client.md).</span></span> <span data-ttu-id="bc061-105">Para ver un ejemplo, consulte [Uso de parámetros con valores de tabla &#40;OLE DB&#41;](../native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="bc061-105">For a sample, see [Use Table-Valued Parameters &#40;OLE DB&#41;](../native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc061-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bc061-106">Remarks</span></span>  
 <span data-ttu-id="bc061-107">Actualmente, puede enviar datos de varias filas al servidor como parámetros de un procedimiento con conjuntos de parámetros (el parámetro DBPARAMS en `ICommand::Execute`).</span><span class="sxs-lookup"><span data-stu-id="bc061-107">Currently, you can send multirow data to the server as parameters to a procedure with parameter sets (the DBPARAMS parameter in `ICommand::Execute`).</span></span> <span data-ttu-id="bc061-108">Con los conjuntos de parámetros, cada elemento del conjunto se debe enviar al servidor en una solicitud de llamada a procedimiento remoto (RPC) independiente.</span><span class="sxs-lookup"><span data-stu-id="bc061-108">With parameter sets, every element of the set has to be sent in a separate remote procedure call (RPC) request to the server.</span></span> <span data-ttu-id="bc061-109">Los parámetros con valores de tabla proporcionan una funcionalidad similar, pero existe una mejor integración con el servidor.</span><span class="sxs-lookup"><span data-stu-id="bc061-109">Table-valued parameters provide similar functionality, but there is better integration with the server.</span></span> <span data-ttu-id="bc061-110">Esto reduce el número de solicitudes RPC y habilita las operaciones basadas en conjunto en el servidor.</span><span class="sxs-lookup"><span data-stu-id="bc061-110">This reduces the number of RPC requests and enables set-based operations on the server.</span></span>  
  
 <span data-ttu-id="bc061-111">Los parámetros con valores de tabla se admiten en el proveedor OLE DB de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client como objetos `Rowset` de OLE DB.</span><span class="sxs-lookup"><span data-stu-id="bc061-111">Table-value parameters are supported in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider as OLE DB `Rowset` objects.</span></span> <span data-ttu-id="bc061-112">El consumidor (es decir, la aplicación cliente que utiliza el proveedor OLE DB de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ) puede proporcionar cualquier objeto `Rowset` como un marcador de posición para los parámetros con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="bc061-112">Any `Rowset` object could be provided by the consumer (that is, the client application using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider) as a placeholder for table-valued parameter parameters.</span></span> <span data-ttu-id="bc061-113">Los parámetros con valores de tabla se tratan como otros tipos de parámetros de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc061-113">Table-valued parameters are treated like other [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] parameter types.</span></span> <span data-ttu-id="bc061-114">El proveedor OLE DB de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client proporciona interfaces de creación, detección, especificación, enlace y esquema.</span><span class="sxs-lookup"><span data-stu-id="bc061-114">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider provides creation, discovery, specification, binding and schema interfaces.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bc061-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="bc061-115">In This Section</span></span>  
  
-   [<span data-ttu-id="bc061-116">Creación de conjuntos de filas de parámetros con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="bc061-116">Table-Valued Parameter Rowset Creation</span></span>](table-valued-parameter-rowset-creation.md)  
  
-   [<span data-ttu-id="bc061-117">Detección de tipos de parámetros con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="bc061-117">Table-Valued Parameter Type Discovery</span></span>](../../database-engine/dev-guide/table-valued-parameter-type-discovery.md)  
  
-   [<span data-ttu-id="bc061-118">Ejecutar comandos que contienen parámetros con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="bc061-118">Executing Commands Containing Table-Valued Parameters</span></span>](executing-commands-containing-table-valued-parameters.md)  
  
-   [<span data-ttu-id="bc061-119">Insertar datos en parámetros con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="bc061-119">Inserting Data into Table-Valued Parameters</span></span>](inserting-data-into-table-valued-parameters.md)  
  
-   [<span data-ttu-id="bc061-120">Conjuntos de filas de esquema cambiados para los parámetros con valores de tabla de OLE DB</span><span class="sxs-lookup"><span data-stu-id="bc061-120">Schema Rowsets Changed for OLE DB Table-Valued Parameters</span></span>](schema-rowsets-changed-for-ole-db-table-valued-parameters.md)  
  
-   [<span data-ttu-id="bc061-121">Compatibilidad con tipos de parámetros con valores de tablas de OLE DB</span><span class="sxs-lookup"><span data-stu-id="bc061-121">OLE DB Table-Valued Parameter Type Support</span></span>](ole-db-table-valued-parameter-type-support.md)  
  
-   [<span data-ttu-id="bc061-122">Compatibilidad con tipos de parámetro con valores de tabla de OLE DB &#40;métodos&#41;</span><span class="sxs-lookup"><span data-stu-id="bc061-122">OLE DB Table-Valued Parameter Type Support &#40;Methods&#41;</span></span>](ole-db-table-valued-parameter-type-support-methods.md)  
  
-   [<span data-ttu-id="bc061-123">Compatibilidad con tipos de parámetros con valores de tabla de OLE DB &#40;propiedades&#41;</span><span class="sxs-lookup"><span data-stu-id="bc061-123">OLE DB Table-Valued Parameter Type Support &#40;Properties&#41;</span></span>](ole-db-table-valued-parameter-type-support-properties.md)  
  
## <a name="see-also"></a><span data-ttu-id="bc061-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bc061-124">See Also</span></span>  
 <span data-ttu-id="bc061-125">[SQL Server Native Client &#40;OLE DB&#41;](../native-client/ole-db/sql-server-native-client-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="bc061-125">[SQL Server Native Client &#40;OLE DB&#41;](../native-client/ole-db/sql-server-native-client-ole-db.md) </span></span>  
 [<span data-ttu-id="bc061-126">Usar parámetros con valores de tabla &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="bc061-126">Use Table-Valued Parameters &#40;OLE DB&#41;</span></span>](../native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md)  
  
  
