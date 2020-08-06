---
title: Niveles de aislamiento (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, transactions
- isolation levels [OLE DB]
- transactions [OLE DB]
- SQL Server Native Client OLE DB provider, transactions
ms.assetid: d70ee72c-6e2a-4bcd-9456-4a697a866361
author: rothja
ms.author: jroth
ms.openlocfilehash: c7f6cbff4e68eaedd3e78a82cddd872ba5f8f19e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674074"
---
# <a name="isolation-levels-ole-db"></a><span data-ttu-id="53cdd-102">Niveles de aislamiento (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="53cdd-102">Isolation Levels (OLE DB)</span></span>
  <span data-ttu-id="53cdd-103">Los clientes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pueden controlar los niveles de aislamiento de la transacción para una conexión.</span><span class="sxs-lookup"><span data-stu-id="53cdd-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] clients can control transaction-isolation levels for a connection.</span></span> <span data-ttu-id="53cdd-104">Para controlar el nivel de aislamiento de transacción, el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consumidor del proveedor de OLE DB de Native Client utiliza:</span><span class="sxs-lookup"><span data-stu-id="53cdd-104">To control transaction-isolation level, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer uses:</span></span>  
  
-   <span data-ttu-id="53cdd-105">DBPROPSET_SESSION propiedad DBPROP_SESS_AUTOCOMMITISOLEVELS para el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] modo de confirmación automática predeterminada del proveedor de OLE DB de Native Client.</span><span class="sxs-lookup"><span data-stu-id="53cdd-105">DBPROPSET_SESSION property DBPROP_SESS_AUTOCOMMITISOLEVELS for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider default autocommit mode.</span></span>  
  
     <span data-ttu-id="53cdd-106">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] valor predeterminado del proveedor de OLE DB de Native Client para el nivel es DBPROPVAL_TI_READCOMMITTED.</span><span class="sxs-lookup"><span data-stu-id="53cdd-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider default for the level is DBPROPVAL_TI_READCOMMITTED.</span></span>  
  
-   <span data-ttu-id="53cdd-107">El parámetro *isoLevel* del método **ITransactionLocal::StartTransaction** para las transacciones locales de confirmación manual.</span><span class="sxs-lookup"><span data-stu-id="53cdd-107">The *isoLevel* parameter of the **ITransactionLocal::StartTransaction** method for local manual-commit transactions.</span></span>  
  
-   <span data-ttu-id="53cdd-108">El parámetro *isoLevel* del método **ITransactionDispenser::BeginTransaction** para las transacciones distribuidas coordinadas por MS DTC.</span><span class="sxs-lookup"><span data-stu-id="53cdd-108">The *isoLevel* parameter of the **ITransactionDispenser::BeginTransaction** method for MS DTC-coordinated distributed transactions.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="53cdd-109">permite el acceso de solo lectura en el nivel de aislamiento de lectura de datos sucios.</span><span class="sxs-lookup"><span data-stu-id="53cdd-109">allows read-only access at the dirty read isolation level.</span></span> <span data-ttu-id="53cdd-110">Todos los demás niveles restringen la simultaneidad aplicando bloqueos a los objetos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="53cdd-110">All other levels restrict concurrency by applying locks to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objects.</span></span> <span data-ttu-id="53cdd-111">Cuando el cliente requiere niveles de simultaneidad mayores, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aplica mayores restricciones al acceso simultáneo a los datos.</span><span class="sxs-lookup"><span data-stu-id="53cdd-111">As the client requires greater concurrency levels, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] applies greater restrictions on concurrent access to data.</span></span> <span data-ttu-id="53cdd-112">Para mantener el máximo nivel de acceso simultáneo a los datos, el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consumidor del proveedor de OLE DB de Native Client debe controlar de forma inteligente sus solicitudes de niveles de simultaneidad específicos.</span><span class="sxs-lookup"><span data-stu-id="53cdd-112">To maintain the highest level of concurrent access to data, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer should intelligently control its requests for specific concurrency levels.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] <span data-ttu-id="53cdd-113">presentó el nivel del aislamiento de instantánea.</span><span class="sxs-lookup"><span data-stu-id="53cdd-113">introduced snapshot isolation level.</span></span> <span data-ttu-id="53cdd-114">Para obtener más información, vea [Trabajar con aislamiento de instantánea](../native-client/features/working-with-snapshot-isolation.md).</span><span class="sxs-lookup"><span data-stu-id="53cdd-114">For more information, see [Working with Snapshot Isolation](../native-client/features/working-with-snapshot-isolation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53cdd-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="53cdd-115">See Also</span></span>  
 [<span data-ttu-id="53cdd-116">Transacciones</span><span class="sxs-lookup"><span data-stu-id="53cdd-116">Transactions</span></span>](transactions.md)  
  
  
