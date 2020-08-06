---
title: Compatibilidad con transacciones locales | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, transactions
- autocommit mode
- transactions [OLE DB]
- ITransactionLocal interface
- SQL Server Native Client OLE DB provider, transactions
- local transactions [OLE DB]
ms.assetid: 78f2e5fc-b6fb-4eda-9f71-991a4d6c4902
author: rothja
ms.author: jroth
ms.openlocfilehash: a9bc11a038e56517aa42619117c371c1319b9ffe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675819"
---
# <a name="supporting-local-transactions"></a><span data-ttu-id="0ec9b-102">Compatibilidad con transacciones locales</span><span class="sxs-lookup"><span data-stu-id="0ec9b-102">Supporting Local Transactions</span></span>
  <span data-ttu-id="0ec9b-103">Una sesión delimita el ámbito de la transacción para una [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] transacción local del proveedor de OLE DB de Native Client.</span><span class="sxs-lookup"><span data-stu-id="0ec9b-103">A session delimits transaction scope for a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider local transaction.</span></span> <span data-ttu-id="0ec9b-104">Cuando, en la dirección de un consumidor, el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client envía una solicitud a una instancia conectada de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , la solicitud constituye una unidad de trabajo para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] el proveedor de OLE DB de Native Client.</span><span class="sxs-lookup"><span data-stu-id="0ec9b-104">When, at the direction of a consumer, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider submits a request to a connected instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the request constitutes a unit of work for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span> <span data-ttu-id="0ec9b-105">Las transacciones locales siempre encapsulan una o más unidades de trabajo en una sola [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sesión de proveedor de OLE DB de Native Client.</span><span class="sxs-lookup"><span data-stu-id="0ec9b-105">Local transactions always wrap one or more units of work on a single [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider session.</span></span>  
  
 <span data-ttu-id="0ec9b-106">Mediante el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] modo de confirmación automática del proveedor de OLE DB de Native Client predeterminado, una unidad de trabajo única se trata como el ámbito de una transacción local.</span><span class="sxs-lookup"><span data-stu-id="0ec9b-106">Using the default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider autocommit mode, a single unit of work is treated as the scope of a local transaction.</span></span> <span data-ttu-id="0ec9b-107">Solo una unidad participa en la transacción local.</span><span class="sxs-lookup"><span data-stu-id="0ec9b-107">Only one unit participates in the local transaction.</span></span> <span data-ttu-id="0ec9b-108">Cuando se crea una sesión, el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client inicia una transacción para la sesión.</span><span class="sxs-lookup"><span data-stu-id="0ec9b-108">When a session is created, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider begins a transaction for the session.</span></span> <span data-ttu-id="0ec9b-109">Cuando se completa correctamente una unidad de trabajo, el trabajo se confirma.</span><span class="sxs-lookup"><span data-stu-id="0ec9b-109">Upon successful completion of a work unit, the work is committed.</span></span> <span data-ttu-id="0ec9b-110">En caso de error, cualquier trabajo comenzado se revierte y el error se notifica al consumidor.</span><span class="sxs-lookup"><span data-stu-id="0ec9b-110">On failure, any work begun is rolled back and the error is reported to the consumer.</span></span> <span data-ttu-id="0ec9b-111">En cualquier caso, el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client inicia una nueva transacción local para la sesión de modo que todo el trabajo se lleve a cabo dentro de una transacción.</span><span class="sxs-lookup"><span data-stu-id="0ec9b-111">In either case, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider begins a new local transaction for the session so that all work is conducted within a transaction.</span></span>  
  
 <span data-ttu-id="0ec9b-112">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consumidor del proveedor de OLE DB de Native Client puede dirigir un control más preciso sobre el ámbito de la transacción local mediante la interfaz **ITransactionLocal** .</span><span class="sxs-lookup"><span data-stu-id="0ec9b-112">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer can direct more precise control over local transaction scope by using the **ITransactionLocal** interface.</span></span> <span data-ttu-id="0ec9b-113">Cuando una sesión del consumidor inicia una transacción, todas las unidades de trabajo de la sesión entre el punto de inicio de la transacción y las posibles llamadas a los métodos **Commit** o **Abort** se tratan como una unidad atómica.</span><span class="sxs-lookup"><span data-stu-id="0ec9b-113">When a consumer session initiates a transaction, all session work units between the transaction start point and the eventual **Commit** or **Abort** method calls are treated as an atomic unit.</span></span> <span data-ttu-id="0ec9b-114">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client inicia implícitamente una transacción cuando el consumidor la dirige.</span><span class="sxs-lookup"><span data-stu-id="0ec9b-114">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider implicitly begins a transaction when directed to do so by the consumer.</span></span> <span data-ttu-id="0ec9b-115">Si el consumidor no solicita la retención, la sesión vuelve al comportamiento de nivel de transacción primaria, la mayoría de las veces en modo de confirmación automática.</span><span class="sxs-lookup"><span data-stu-id="0ec9b-115">If the consumer does not request retention, the session reverts to parent transaction-level behavior, most commonly autocommit mode.</span></span>  
  
 <span data-ttu-id="0ec9b-116">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client admite los parámetros **ITransactionLocal:: StartTransaction** como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="0ec9b-116">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports **ITransactionLocal::StartTransaction** parameters as follows.</span></span>  
  
|<span data-ttu-id="0ec9b-117">Parámetro</span><span class="sxs-lookup"><span data-stu-id="0ec9b-117">Parameter</span></span>|<span data-ttu-id="0ec9b-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="0ec9b-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0ec9b-119">*isoLevel*[in]</span><span class="sxs-lookup"><span data-stu-id="0ec9b-119">*isoLevel*[in]</span></span>|<span data-ttu-id="0ec9b-120">Nivel de aislamiento que se va a utilizar con esta transacción.</span><span class="sxs-lookup"><span data-stu-id="0ec9b-120">The isolation level to be used with this transaction.</span></span> <span data-ttu-id="0ec9b-121">En las transacciones locales, el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client admite lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0ec9b-121">In local transactions, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports the following:</span></span><br /><br /> <span data-ttu-id="0ec9b-122">-ISOLATIONLEVEL_UNSPECIFIED</span><span class="sxs-lookup"><span data-stu-id="0ec9b-122">-   ISOLATIONLEVEL_UNSPECIFIED</span></span><br /><span data-ttu-id="0ec9b-123">-ISOLATIONLEVEL_CHAOS</span><span class="sxs-lookup"><span data-stu-id="0ec9b-123">-   ISOLATIONLEVEL_CHAOS</span></span><br /><span data-ttu-id="0ec9b-124">-ISOLATIONLEVEL_READUNCOMMITTED</span><span class="sxs-lookup"><span data-stu-id="0ec9b-124">-   ISOLATIONLEVEL_READUNCOMMITTED</span></span><br /><span data-ttu-id="0ec9b-125">-ISOLATIONLEVEL_READCOMMITTED</span><span class="sxs-lookup"><span data-stu-id="0ec9b-125">-   ISOLATIONLEVEL_READCOMMITTED</span></span><br /><span data-ttu-id="0ec9b-126">-ISOLATIONLEVEL_REPEATABLEREAD</span><span class="sxs-lookup"><span data-stu-id="0ec9b-126">-   ISOLATIONLEVEL_REPEATABLEREAD</span></span><br /><span data-ttu-id="0ec9b-127">-ISOLATIONLEVEL_CURSORSTABILITY</span><span class="sxs-lookup"><span data-stu-id="0ec9b-127">-   ISOLATIONLEVEL_CURSORSTABILITY</span></span><br /><span data-ttu-id="0ec9b-128">-ISOLATIONLEVEL_REPEATABLEREAD</span><span class="sxs-lookup"><span data-stu-id="0ec9b-128">-   ISOLATIONLEVEL_REPEATABLEREAD</span></span><br /><span data-ttu-id="0ec9b-129">-ISOLATIONLEVEL_SERIALIZABLE</span><span class="sxs-lookup"><span data-stu-id="0ec9b-129">-   ISOLATIONLEVEL_SERIALIZABLE</span></span><br /><span data-ttu-id="0ec9b-130">-ISOLATIONLEVEL_ISOLATED</span><span class="sxs-lookup"><span data-stu-id="0ec9b-130">-   ISOLATIONLEVEL_ISOLATED</span></span><br /><span data-ttu-id="0ec9b-131">-ISOLATIONLEVEL_SNAPSHOT **Nota:** a partir de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , ISOLATIONLEVEL_SNAPSHOT es válido para el argumento *isolevel* si el control de versiones está habilitado o no para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0ec9b-131">-   ISOLATIONLEVEL_SNAPSHOT **Note:**  Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], ISOLATIONLEVEL_SNAPSHOT is valid for the *isoLevel* argument whether or not versioning is enabled for the database.</span></span> <span data-ttu-id="0ec9b-132">Sin embargo, se producirá un error si el usuario intenta ejecutar una instrucción y no está habilitado el control de versiones, o si la base de datos no es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="0ec9b-132">However, an error will occur if the user attempts to execute a statement and versioning is not enabled and/or the database is not read-only.</span></span> <span data-ttu-id="0ec9b-133">Además, si se especifica ISOLATIONLEVEL_SNAPSHOT como el valor de *isoLevel* al conectarse a una versión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] anterior a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], se producirá el error XACT_E_ISOLATIONLEVEL.</span><span class="sxs-lookup"><span data-stu-id="0ec9b-133">In addition, the error XACT_E_ISOLATIONLEVEL will occur if ISOLATIONLEVEL_SNAPSHOT is specified as the *isoLevel* when connected to a version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] earlier than [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>|  
|<span data-ttu-id="0ec9b-134">*isoFlags*[in]</span><span class="sxs-lookup"><span data-stu-id="0ec9b-134">*isoFlags*[in]</span></span>|<span data-ttu-id="0ec9b-135">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client devuelve un error para cualquier valor distinto de cero.</span><span class="sxs-lookup"><span data-stu-id="0ec9b-135">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns an error for any value other than zero.</span></span>|  
|<span data-ttu-id="0ec9b-136">*pOtherOptions*[in]</span><span class="sxs-lookup"><span data-stu-id="0ec9b-136">*pOtherOptions*[in]</span></span>|<span data-ttu-id="0ec9b-137">Si no es NULL, el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client solicita el objeto de opciones de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="0ec9b-137">If not NULL, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider requests the options object from the interface.</span></span> <span data-ttu-id="0ec9b-138">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client devuelve XACT_E_NOTIMEOUT si el miembro *ulTimeout* del objeto de opciones no es cero.</span><span class="sxs-lookup"><span data-stu-id="0ec9b-138">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns XACT_E_NOTIMEOUT if the options object's *ulTimeout* member is not zero.</span></span> <span data-ttu-id="0ec9b-139">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client omite el valor del miembro *szDescription* .</span><span class="sxs-lookup"><span data-stu-id="0ec9b-139">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider ignores the value of the *szDescription* member.</span></span>|  
|<span data-ttu-id="0ec9b-140">*pulTransactionLevel*[out]</span><span class="sxs-lookup"><span data-stu-id="0ec9b-140">*pulTransactionLevel*[out]</span></span>|<span data-ttu-id="0ec9b-141">Si no es NULL, el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client devuelve el nivel anidado de la transacción.</span><span class="sxs-lookup"><span data-stu-id="0ec9b-141">If not NULL, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns the nested level of the transaction.</span></span>|  
  
 <span data-ttu-id="0ec9b-142">Para las transacciones locales, el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client implementa los parámetros **ITransaction:: ABORT** como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="0ec9b-142">For local transactions, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider implements **ITransaction::Abort** parameters as follows.</span></span>  
  
|<span data-ttu-id="0ec9b-143">Parámetro</span><span class="sxs-lookup"><span data-stu-id="0ec9b-143">Parameter</span></span>|<span data-ttu-id="0ec9b-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="0ec9b-144">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0ec9b-145">*pboidReason*[in]</span><span class="sxs-lookup"><span data-stu-id="0ec9b-145">*pboidReason*[in]</span></span>|<span data-ttu-id="0ec9b-146">Se omite si está establecido.</span><span class="sxs-lookup"><span data-stu-id="0ec9b-146">Ignored if set.</span></span> <span data-ttu-id="0ec9b-147">Puede ser sin ningún riesgo NULL.</span><span class="sxs-lookup"><span data-stu-id="0ec9b-147">Can safely be NULL.</span></span>|  
|<span data-ttu-id="0ec9b-148">*fRetaining*[in]</span><span class="sxs-lookup"><span data-stu-id="0ec9b-148">*fRetaining*[in]</span></span>|<span data-ttu-id="0ec9b-149">Si es TRUE, se inicia una nueva transacción de forma implícita para la sesión.</span><span class="sxs-lookup"><span data-stu-id="0ec9b-149">When TRUE, a new transaction is implicitly begun for the session.</span></span> <span data-ttu-id="0ec9b-150">La transacción debe ser confirmada o finalizada por el consumidor.</span><span class="sxs-lookup"><span data-stu-id="0ec9b-150">The transaction must be committed or terminated by the consumer.</span></span> <span data-ttu-id="0ec9b-151">Cuando es FALSE, el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client vuelve al modo de confirmación automática para la sesión.</span><span class="sxs-lookup"><span data-stu-id="0ec9b-151">When FALSE, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider reverts to autocommit mode for the session.</span></span>|  
|<span data-ttu-id="0ec9b-152">*fAsync*[in]</span><span class="sxs-lookup"><span data-stu-id="0ec9b-152">*fAsync*[in]</span></span>|<span data-ttu-id="0ec9b-153">El proveedor de OLE DB de Native Client no admite la anulación asincrónica [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0ec9b-153">Asynchronous abort is not supported by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span> <span data-ttu-id="0ec9b-154">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client devuelve XACT_E_NOTSUPPORTED si el valor no es false.</span><span class="sxs-lookup"><span data-stu-id="0ec9b-154">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns XACT_E_NOTSUPPORTED if the value is not FALSE.</span></span>|  
  
 <span data-ttu-id="0ec9b-155">Para las transacciones locales, el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client implementa los parámetros **ITransaction:: commit** como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="0ec9b-155">For local transactions, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider implements **ITransaction::Commit** parameters as follows.</span></span>  
  
|<span data-ttu-id="0ec9b-156">Parámetro</span><span class="sxs-lookup"><span data-stu-id="0ec9b-156">Parameter</span></span>|<span data-ttu-id="0ec9b-157">Descripción</span><span class="sxs-lookup"><span data-stu-id="0ec9b-157">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0ec9b-158">*fRetaining*[in]</span><span class="sxs-lookup"><span data-stu-id="0ec9b-158">*fRetaining*[in]</span></span>|<span data-ttu-id="0ec9b-159">Si es TRUE, se inicia una nueva transacción de forma implícita para la sesión.</span><span class="sxs-lookup"><span data-stu-id="0ec9b-159">When TRUE, a new transaction is implicitly begun for the session.</span></span> <span data-ttu-id="0ec9b-160">La transacción debe ser confirmada o finalizada por el consumidor.</span><span class="sxs-lookup"><span data-stu-id="0ec9b-160">The transaction must be committed or terminated by the consumer.</span></span> <span data-ttu-id="0ec9b-161">Cuando es FALSE, el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client vuelve al modo de confirmación automática para la sesión.</span><span class="sxs-lookup"><span data-stu-id="0ec9b-161">When FALSE, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider reverts to autocommit mode for the session.</span></span>|  
|<span data-ttu-id="0ec9b-162">*grfTC*[in]</span><span class="sxs-lookup"><span data-stu-id="0ec9b-162">*grfTC*[in]</span></span>|<span data-ttu-id="0ec9b-163">El proveedor de OLE DB de Native Client no admite las devoluciones asincrónicas y de fase uno [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0ec9b-163">Asynchronous and phase one returns are not supported by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span> <span data-ttu-id="0ec9b-164">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client devuelve XACT_E_NOTSUPPORTED para cualquier valor distinto de XACTTC_SYNC.</span><span class="sxs-lookup"><span data-stu-id="0ec9b-164">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns XACT_E_NOTSUPPORTED for any value other than XACTTC_SYNC.</span></span>|  
|<span data-ttu-id="0ec9b-165">*grfRM*[in]</span><span class="sxs-lookup"><span data-stu-id="0ec9b-165">*grfRM*[in]</span></span>|<span data-ttu-id="0ec9b-166">Debe ser 0.</span><span class="sxs-lookup"><span data-stu-id="0ec9b-166">Must be 0.</span></span>|  
  
 <span data-ttu-id="0ec9b-167">Los [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conjuntos de filas de proveedor de OLE DB de Native Client en la sesión se conservan en una operación de confirmación o anulación local basada en los valores de las propiedades del conjunto de filas DBPROP_ABORTPRESERVE y DBPROP_COMMITPRESERVE.</span><span class="sxs-lookup"><span data-stu-id="0ec9b-167">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider rowsets on the session are preserved on a local commit or abort operation based on the values of the rowset properties DBPROP_ABORTPRESERVE and DBPROP_COMMITPRESERVE.</span></span> <span data-ttu-id="0ec9b-168">De forma predeterminada, estas propiedades son VARIANT_FALSE y todos los [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conjuntos de filas del proveedor de OLE DB de Native Client de la sesión se pierden después de una operación de anulación o confirmación.</span><span class="sxs-lookup"><span data-stu-id="0ec9b-168">By default, these properties are both VARIANT_FALSE and all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider rowsets on the session are lost following an abort or commit operation.</span></span>  
  
 <span data-ttu-id="0ec9b-169">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client no implementa la interfaz **ITransactionObject** .</span><span class="sxs-lookup"><span data-stu-id="0ec9b-169">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not implement the **ITransactionObject** interface.</span></span> <span data-ttu-id="0ec9b-170">Si el consumidor intenta recuperar una referencia en la interfaz, obtiene E_NOINTERFACE.</span><span class="sxs-lookup"><span data-stu-id="0ec9b-170">A consumer attempt to retrieve a reference on the interface returns E_NOINTERFACE.</span></span>  
  
 <span data-ttu-id="0ec9b-171">En este ejemplo, se usa **ITransactionLocal**.</span><span class="sxs-lookup"><span data-stu-id="0ec9b-171">This example uses **ITransactionLocal**.</span></span>  
  
```  
// Interfaces used in the example.  
IDBCreateSession*   pIDBCreateSession   = NULL;  
ITransaction*       pITransaction       = NULL;  
IDBCreateCommand*   pIDBCreateCommand   = NULL;  
IRowset*            pIRowset            = NULL;  
  
HRESULT             hr;  
  
// Get the command creation and local transaction interfaces for the  
// session.  
if (FAILED(hr = pIDBCreateSession->CreateSession(NULL,  
     IID_IDBCreateCommand, (IUnknown**) &pIDBCreateCommand)))  
    {  
    // Process error from session creation. Release any references and  
    // return.  
    }  
  
if (FAILED(hr = pIDBCreateCommand->QueryInterface(IID_ITransactionLocal,  
    (void**) &pITransaction)))  
    {  
    // Process error. Release any references and return.  
    }  
  
// Start the local transaction.  
if (FAILED(hr = ((ITransactionLocal*) pITransaction)->StartTransaction(  
    ISOLATIONLEVEL_REPEATABLEREAD, 0, NULL, NULL)))  
    {  
    // Process error from StartTransaction. Release any references and  
    // return.  
    }  
  
// Get data into a rowset, then update the data. Functions are not  
// illustrated in this example.  
if (FAILED(hr = ExecuteCommand(pIDBCreateCommand, &pIRowset)))  
    {  
    // Release any references and return.  
    }  
  
// If rowset data update fails, then terminate the transaction, else  
// commit. The example doesn't retain the rowset.  
if (FAILED(hr = UpdateDataInRowset(pIRowset, bDelayedUpdate)))  
    {  
    // Get error from update, then terminate.  
    pITransaction->Abort(NULL, FALSE, FALSE);  
    }  
else  
    {  
    if (FAILED(hr = pITransaction->Commit(FALSE, XACTTC_SYNC, 0)))  
        {  
        // Get error from failed commit.  
        }  
    }  
  
if (FAILED(hr))  
    {  
    // Update of data or commit failed. Release any references and  
    // return.  
    }  
  
// Release any references and continue.  
```  
  
## <a name="see-also"></a><span data-ttu-id="0ec9b-172">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0ec9b-172">See Also</span></span>  
 <span data-ttu-id="0ec9b-173">[Transactions](transactions.md) </span><span class="sxs-lookup"><span data-stu-id="0ec9b-173">[Transactions](transactions.md) </span></span>  
 [<span data-ttu-id="0ec9b-174">Trabajar con aislamiento de instantánea</span><span class="sxs-lookup"><span data-stu-id="0ec9b-174">Working with Snapshot Isolation</span></span>](../native-client/features/working-with-snapshot-isolation.md)  
  
  
