---
title: Tablas e índices | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, indexes
- OLE DB, tables
- ITableDefinition interface
- tables [OLE DB]
- IIndexDefinition interface
- SQL Server Native Client OLE DB provider, tables
- SQL Server Native Client OLE DB provider, indexes
- indexes [OLE DB]
ms.assetid: 4217c6d8-8cd2-43dc-b36f-3cfd8a58fabc
author: rothja
ms.author: jroth
ms.openlocfilehash: abc7c314e433eb9f107bd191738d951706f1b50d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674075"
---
# <a name="tables-and-indexes"></a><span data-ttu-id="4ef19-102">Tablas e índices</span><span class="sxs-lookup"><span data-stu-id="4ef19-102">Tables and Indexes</span></span>
  <span data-ttu-id="4ef19-103">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client expone las interfaces **IIndexDefinition** y **ITableDefinition** , lo que permite a los consumidores crear, modificar y quitar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tablas e índices.</span><span class="sxs-lookup"><span data-stu-id="4ef19-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **IIndexDefinition** and **ITableDefinition** interfaces, allowing consumers to create, alter, and drop [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables and indexes.</span></span> <span data-ttu-id="4ef19-104">Las definiciones de tabla e índice válidas dependen de la versión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4ef19-104">Valid table and index definitions depend on the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="4ef19-105">La capacidad de crear o quitar tablas e índices depende de los derechos de acceso a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] del usuario de la aplicación de consumidor.</span><span class="sxs-lookup"><span data-stu-id="4ef19-105">The ability to create or drop tables and indexes depends on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] access rights of the consumer-application user.</span></span> <span data-ttu-id="4ef19-106">La eliminación de una tabla se puede restringir en mayor medida mediante la presencia de restricciones de integridad referencia declarativas u otros factores.</span><span class="sxs-lookup"><span data-stu-id="4ef19-106">Dropping a table can be further constrained by the presence of declarative referential integrity constraints or other factors.</span></span>  
  
 <span data-ttu-id="4ef19-107">La mayoría de las aplicaciones que tienen como destino [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usan SQL-DMO en lugar de estas [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] interfaces de proveedor de OLE DB de Native Client.</span><span class="sxs-lookup"><span data-stu-id="4ef19-107">Most applications targeting [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] use SQL-DMO instead of these [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider interfaces.</span></span> <span data-ttu-id="4ef19-108">SQL-DMO es una colección de objetos de OLE Automation que admite todas las funciones administrativas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4ef19-108">SQL-DMO is a collection of OLE Automation objects that support all the administrative functions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4ef19-109">Las aplicaciones con destino en varios proveedores OLE DB utilizan estas interfaces OLE DB genéricas que admiten los diferentes proveedores OLE DB.</span><span class="sxs-lookup"><span data-stu-id="4ef19-109">Applications targeting multiple OLE DB providers use these generic OLE DB interfaces that are supported by the various OLE DB providers.</span></span>  
  
 <span data-ttu-id="4ef19-110">En el conjunto de propiedades específico de proveedor DBPROPSET_SQLSERVERCOLUMN, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] define la propiedad siguiente.</span><span class="sxs-lookup"><span data-stu-id="4ef19-110">In the provider-specific property set DBPROPSET_SQLSERVERCOLUMN, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] defines the following property.</span></span>  
  
|<span data-ttu-id="4ef19-111">Id. de propiedad</span><span class="sxs-lookup"><span data-stu-id="4ef19-111">Property ID</span></span>|<span data-ttu-id="4ef19-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="4ef19-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="4ef19-113">SSPROP_COL_COLLATIONNAME</span><span class="sxs-lookup"><span data-stu-id="4ef19-113">SSPROP_COL_COLLATIONNAME</span></span>|<span data-ttu-id="4ef19-114">Escriba:  VT_BSTR</span><span class="sxs-lookup"><span data-stu-id="4ef19-114">Type: VT_BSTR</span></span><br /><br /> <span data-ttu-id="4ef19-115">L/E: escritura</span><span class="sxs-lookup"><span data-stu-id="4ef19-115">R/W: Write</span></span><br /><br /> <span data-ttu-id="4ef19-116">Valor predeterminado: NULL</span><span class="sxs-lookup"><span data-stu-id="4ef19-116">Default: Null</span></span><br /><br /> <span data-ttu-id="4ef19-117">Descripción: esta propiedad solo se usa en **ITableDefinition**.</span><span class="sxs-lookup"><span data-stu-id="4ef19-117">Description: This property is used only in **ITableDefinition**.</span></span> <span data-ttu-id="4ef19-118">La cadena especificada en esta propiedad se usa al crear una instrucción [CREATE TABLE](/sql/t-sql/statements/create-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4ef19-118">The string specified in this property is used when creating a [CREATE TABLE](/sql/t-sql/statements/create-table-transact-sql)</span></span><br /><br /> <span data-ttu-id="4ef19-119">.</span><span class="sxs-lookup"><span data-stu-id="4ef19-119">statement.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="4ef19-120">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4ef19-120">In This Section</span></span>  
  
-   [<span data-ttu-id="4ef19-121">Crear tablas de SQL Server</span><span class="sxs-lookup"><span data-stu-id="4ef19-121">Creating SQL Server Tables</span></span>](../../relational-databases/native-client-ole-db-tables-indexes/creating-sql-server-tables.md)  
  
-   [<span data-ttu-id="4ef19-122">Agregar una columna a una tabla de SQL Server</span><span class="sxs-lookup"><span data-stu-id="4ef19-122">Adding a Column to a SQL Server Table</span></span>](../../relational-databases/native-client-ole-db-tables-indexes/adding-a-column-to-a-sql-server-table.md)  
  
-   [<span data-ttu-id="4ef19-123">Quitar una columna de una tabla de SQL Server</span><span class="sxs-lookup"><span data-stu-id="4ef19-123">Removing a Column from a SQL Server Table</span></span>](../../relational-databases/native-client-ole-db-tables-indexes/removing-a-column-from-a-sql-server-table.md)  
  
-   [<span data-ttu-id="4ef19-124">Quitar una tabla de SQL Server</span><span class="sxs-lookup"><span data-stu-id="4ef19-124">Dropping a SQL Server Table</span></span>](../../relational-databases/native-client-ole-db-tables-indexes/dropping-a-sql-server-table.md)  
  
-   [<span data-ttu-id="4ef19-125">Crear índices de SQL Server</span><span class="sxs-lookup"><span data-stu-id="4ef19-125">Creating SQL Server Indexes</span></span>](../../relational-databases/indexes/indexes.md)  
  
-   [<span data-ttu-id="4ef19-126">Quitar un índice de SQL Server</span><span class="sxs-lookup"><span data-stu-id="4ef19-126">Dropping a SQL Server Index</span></span>](../../relational-databases/native-client-ole-db-tables-indexes/dropping-a-sql-server-index.md)  
  
## <a name="see-also"></a><span data-ttu-id="4ef19-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4ef19-127">See Also</span></span>  
 <span data-ttu-id="4ef19-128">[SQL Server Native Client &#40;OLE DB&#41;](../../relational-databases/native-client/ole-db/sql-server-native-client-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="4ef19-128">[SQL Server Native Client &#40;OLE DB&#41;](../../relational-databases/native-client/ole-db/sql-server-native-client-ole-db.md) </span></span>  
 <span data-ttu-id="4ef19-129">[DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4ef19-129">[DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql) </span></span>  
 <span data-ttu-id="4ef19-130">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4ef19-130">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 [<span data-ttu-id="4ef19-131">DROP INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4ef19-131">DROP INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-index-transact-sql)  
  
  
