---
title: SQL Server Native Client (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, about SQL Server Native Client OLE DB provider
- OLE DB, SQL Server Native Client OLE DB provider
- data access [SQL Server Native Client], OLE DB
- SQLNCLI, OLE DB
- OLE DB
- SQL Server Native Client OLE DB provider
- SQL Server Native Client, OLE DB
ms.assetid: da846da4-ec19-4a4f-81fb-7d5a2b2bf80a
author: rothja
ms.author: jroth
ms.openlocfilehash: 46b948eb1d075edc6000849dcb2d18ea372809d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671507"
---
# <a name="sql-server-native-client-ole-db"></a><span data-ttu-id="5e1fb-102">SQL Server Native Client (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="5e1fb-102">SQL Server Native Client (OLE DB)</span></span>
  <span data-ttu-id="5e1fb-103">El proveedor OLE DB de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client es una API COM de bajo nivel que se utiliza para tener acceso a los datos.</span><span class="sxs-lookup"><span data-stu-id="5e1fb-103">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider is a low-level COM API that is used for accessing data.</span></span> <span data-ttu-id="5e1fb-104">El proveedor OLE DB de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client se recomienda para desarrollar herramientas, utilidades o componentes de bajo nivel que necesitan alto rendimiento.</span><span class="sxs-lookup"><span data-stu-id="5e1fb-104">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider is recommended for developing tools, utilities, or low-level components that need high performance.</span></span> <span data-ttu-id="5e1fb-105">El proveedor OLE DB de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client es un proveedor nativo, de alto rendimiento con acceso directo al protocolo [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Flujo TDS.</span><span class="sxs-lookup"><span data-stu-id="5e1fb-105">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider is a native, high performance provider that accesses the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Tabular Data Stream (TDS) protocol directly.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="5e1fb-106">Native Client proporciona compatibilidad con OLE DB a las aplicaciones que se conectan a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e1fb-106">Native Client provides OLE DB support to applications connecting to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="5e1fb-107">El [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client es un proveedor compatible con la versión 2,0 de OLE DB.</span><span class="sxs-lookup"><span data-stu-id="5e1fb-107">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider is an OLE DB version 2.0-compliant provider.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5e1fb-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5e1fb-108">In This Section</span></span>  
  
-   [<span data-ttu-id="5e1fb-109">Crear una aplicación de proveedor OLE DB de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="5e1fb-109">Creating a SQL Server Native Client OLE DB Provider Application</span></span>](../../native-client-ole-db-provider/creating-a-sql-server-native-client-ole-db-provider-application.md)  
  
-   [<span data-ttu-id="5e1fb-110">Objetos de origen de datos &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="5e1fb-110">Data Source Objects &#40;OLE DB&#41;</span></span>](../../native-client-ole-db-data-source-objects/data-source-objects-ole-db.md)  
  
-   [<span data-ttu-id="5e1fb-111">Comandos</span><span class="sxs-lookup"><span data-stu-id="5e1fb-111">Commands</span></span>](../../native-client-ole-db-commands/commands.md)  
  
-   [<span data-ttu-id="5e1fb-112">Conjuntos de filas</span><span class="sxs-lookup"><span data-stu-id="5e1fb-112">Rowsets</span></span>](../../native-client-ole-db-rowsets/rowsets.md)  
  
-   [<span data-ttu-id="5e1fb-113">Procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="5e1fb-113">Stored Procedures</span></span>](stored-procedures.md)  
  
-   [<span data-ttu-id="5e1fb-114">BLOB y objetos OLE</span><span class="sxs-lookup"><span data-stu-id="5e1fb-114">BLOBs and OLE Objects</span></span>](../../native-client-ole-db-blobs/blobs-and-ole-objects.md)  
  
-   [<span data-ttu-id="5e1fb-115">Tablas e índices</span><span class="sxs-lookup"><span data-stu-id="5e1fb-115">Tables and Indexes</span></span>](../../native-client-ole-db-tables-indexes/tables-and-indexes.md)  
  
-   [<span data-ttu-id="5e1fb-116">Tipos de datos &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="5e1fb-116">Data Types &#40;OLE DB&#41;</span></span>](../../native-client-ole-db-data-types/data-types-ole-db.md)  
  
-   [<span data-ttu-id="5e1fb-117">Compatibilidad con conjuntos de filas de esquema &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="5e1fb-117">Schema Rowset Support &#40;OLE DB&#41;</span></span>](schema-rowset-support-ole-db.md)  
  
-   [<span data-ttu-id="5e1fb-118">Parámetros con valores de tabla &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="5e1fb-118">Table-Valued Parameters &#40;OLE DB&#41;</span></span>](../../native-client-ole-db-table-valued-parameters/table-valued-parameters-ole-db.md)  
  
-   [<span data-ttu-id="5e1fb-119">Mejoras de fecha y hora &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="5e1fb-119">Date and Time Improvements &#40;OLE DB&#41;</span></span>](../../native-client-ole-db-date-time/date-and-time-improvements-ole-db.md)  
  
-   [<span data-ttu-id="5e1fb-120">Tipos definidos por el usuario de CLR de gran tamaño &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="5e1fb-120">Large CLR User-Defined Types &#40;OLE DB&#41;</span></span>](large-clr-user-defined-types-ole-db.md)  
  
-   [<span data-ttu-id="5e1fb-121">Compatibilidad con FILESTREAM &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="5e1fb-121">FILESTREAM Support &#40;OLE DB&#41;</span></span>](filestream-support-ole-db.md)  
  
-   [<span data-ttu-id="5e1fb-122">Transacciones</span><span class="sxs-lookup"><span data-stu-id="5e1fb-122">Transactions</span></span>](../../native-client-ole-db-transactions/transactions.md)  
  
-   [<span data-ttu-id="5e1fb-123">Errores</span><span class="sxs-lookup"><span data-stu-id="5e1fb-123">Errors</span></span>](../../native-client-ole-db-errors/errors.md)  
  
-   [<span data-ttu-id="5e1fb-124">Nombres de entidad de seguridad de servicio &#40;SPNs&#41; en conexiones cliente &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="5e1fb-124">Service Principal Names &#40;SPNs&#41; in Client Connections &#40;OLE DB&#41;</span></span>](service-principal-names-spns-in-client-connections-ole-db.md)  
  
-   [<span data-ttu-id="5e1fb-125">Compatibilidad con columnas dispersas &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="5e1fb-125">Sparse Columns Support &#40;OLE DB&#41;</span></span>](sparse-columns-support-ole-db.md)  
  
-   [<span data-ttu-id="5e1fb-126">Referencia de SQL Server Native Client &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="5e1fb-126">SQL Server Native Client &#40;OLE DB&#41; Reference</span></span>](../../native-client-ole-db-interfaces/sql-server-native-client-ole-db-interfaces.md)  
  
-   [<span data-ttu-id="5e1fb-127">Temas de procedimientos de OLE DB</span><span class="sxs-lookup"><span data-stu-id="5e1fb-127">OLE DB How-to Topics</span></span>](../../native-client-ole-db-how-to/ole-db-how-to-topics.md)  
  
## <a name="see-also"></a><span data-ttu-id="5e1fb-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5e1fb-128">See Also</span></span>  
 [<span data-ttu-id="5e1fb-129">Programación de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="5e1fb-129">SQL Server Native Client Programming</span></span>](../sql-server-native-client-programming.md)  
  
  
