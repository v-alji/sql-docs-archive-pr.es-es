---
title: Usar funciones de catálogo | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC, functions
- SQLLinkedCatalogs function
- SQL Server Native Client ODBC driver, catalog functions
- SQLLinkedServers function
- catalog functions [ODBC]
- functions [ODBC]
ms.assetid: 7773fb2e-06b5-4c4b-88e9-0ad9132ad273
author: rothja
ms.author: jroth
ms.openlocfilehash: 6cac35e658343f606c1953f265c752335c70d81f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676473"
---
# <a name="using-catalog-functions"></a><span data-ttu-id="63723-102">Utilizar funciones de catálogo</span><span class="sxs-lookup"><span data-stu-id="63723-102">Using Catalog Functions</span></span>
  <span data-ttu-id="63723-103">Todas las bases de datos tienen una estructura que contiene los datos almacenados en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="63723-103">All databases have a structure containing the data stored in the database.</span></span> <span data-ttu-id="63723-104">Una definición de esta estructura, junto con otra información como permisos, está almacenada en un catálogo (se implementa como un conjunto de tablas del sistema), también conocido como diccionario de datos.</span><span class="sxs-lookup"><span data-stu-id="63723-104">A definition of this structure, along with other information such as permissions, is stored in a catalog (implemented as a set of system tables), also known as a data dictionary.</span></span>  
  
 <span data-ttu-id="63723-105">El [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] controlador ODBC de Native Client permite que una aplicación determine la estructura de la base de datos a través de llamadas a funciones de catálogo de ODBC.</span><span class="sxs-lookup"><span data-stu-id="63723-105">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver enables an application to determine the database structure through calls to ODBC catalog functions.</span></span> <span data-ttu-id="63723-106">Las funciones de catálogo devuelven información en conjuntos de resultados y se implementan utilizando procedimientos almacenados de catálogo para consultar las tablas del sistema en el catálogo.</span><span class="sxs-lookup"><span data-stu-id="63723-106">Catalog functions return information in result sets and are implemented using catalog stored procedures to query the system tables in the catalog.</span></span> <span data-ttu-id="63723-107">Por ejemplo, una aplicación puede solicitar un conjunto de resultados que contenga información sobre todas las tablas del sistema o todas las columnas de una tabla determinada.</span><span class="sxs-lookup"><span data-stu-id="63723-107">For example, an application might request a result set containing information about all the tables on the system or all the columns in a particular table.</span></span> <span data-ttu-id="63723-108">Las funciones de catálogo estándar de ODBC se utilizan para obtener información de catálogo del servidor [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] al que está conectada la aplicación.</span><span class="sxs-lookup"><span data-stu-id="63723-108">The standard ODBC catalog functions are used to get catalog information from the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to which the application connected.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="63723-109">admite consultas distribuidas en las que se tiene acceso a datos de varios orígenes de datos OLE DB heterogéneos en una única consulta.</span><span class="sxs-lookup"><span data-stu-id="63723-109">supports distributed queries in which data from multiple, heterogeneous OLE DB data sources is accessed in a single query.</span></span> <span data-ttu-id="63723-110">Uno de los métodos para tener acceso a un origen de datos OLE DB remoto consiste en definir el origen de datos como un servidor vinculado.</span><span class="sxs-lookup"><span data-stu-id="63723-110">One of the methods of accessing a remote OLE DB data source is to define the data source as a linked server.</span></span> <span data-ttu-id="63723-111">Esto puede realizarse mediante [sp_addlinkedserver](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="63723-111">This can be done by using [sp_addlinkedserver](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql).</span></span> <span data-ttu-id="63723-112">Una vez definido el servidor vinculado, se puede hacer referencia a los objetos de ese servidor en instrucciones Transact-SQL utilizando un nombre con cuatro partes:</span><span class="sxs-lookup"><span data-stu-id="63723-112">After the linked server has been defined, objects in that server can be referenced in Transact-SQL statements by using a four-part name:</span></span>  
  
 <span data-ttu-id="63723-113">*linked_server_name. Catalog. Schema. object_name*.</span><span class="sxs-lookup"><span data-stu-id="63723-113">*linked_server_name.catalog.schema.object_name*.</span></span>  
  
 <span data-ttu-id="63723-114">El controlador ODBC de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client admite dos funciones específicas del controlador que ayudan a obtener información de catálogo de los servidores vinculados:</span><span class="sxs-lookup"><span data-stu-id="63723-114">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver supports two driver-specific functions that help get catalog information from linked servers:</span></span>  
  
-   <span data-ttu-id="63723-115">**SQLLinkedServers**</span><span class="sxs-lookup"><span data-stu-id="63723-115">**SQLLinkedServers**</span></span>  
  
     <span data-ttu-id="63723-116">Devuelve una lista de los servidores vinculados definidos para el servidor local.</span><span class="sxs-lookup"><span data-stu-id="63723-116">Returns a list of the linked servers defined to the local server.</span></span>  
  
-   <span data-ttu-id="63723-117">**SQLLinkedCatalogs**</span><span class="sxs-lookup"><span data-stu-id="63723-117">**SQLLinkedCatalogs**</span></span>  
  
     <span data-ttu-id="63723-118">Devuelve una lista de los catálogos incluidos en un servidor vinculado.</span><span class="sxs-lookup"><span data-stu-id="63723-118">Returns a list of the catalogs contained in a linked server.</span></span>  
  
 <span data-ttu-id="63723-119">Después de tener un nombre de servidor vinculado y un nombre de catálogo, el [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] controlador ODBC de Native Client permite obtener información del catálogo mediante el uso de un nombre de dos partes de _linked_server_name_**.** _Catalog_ para *nombrecatálogo* en las siguientes funciones de catálogo de ODBC:</span><span class="sxs-lookup"><span data-stu-id="63723-119">After you have a linked server name and a catalog name, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver supports getting information from the catalog by using a two-part name of _linked_server_name_**.**_catalog_ for *CatalogName* on the following ODBC catalog functions:</span></span>  
  
-   <span data-ttu-id="63723-120">**SQLColumnPrivileges**</span><span class="sxs-lookup"><span data-stu-id="63723-120">**SQLColumnPrivileges**</span></span>  
  
-   <span data-ttu-id="63723-121">**SQLColumns**</span><span class="sxs-lookup"><span data-stu-id="63723-121">**SQLColumns**</span></span>  
  
-   <span data-ttu-id="63723-122">**SQLPrimaryKeys**</span><span class="sxs-lookup"><span data-stu-id="63723-122">**SQLPrimaryKeys**</span></span>  
  
-   <span data-ttu-id="63723-123">**SQLStatistics**</span><span class="sxs-lookup"><span data-stu-id="63723-123">**SQLStatistics**</span></span>  
  
-   <span data-ttu-id="63723-124">**SQLTablePrivileges**</span><span class="sxs-lookup"><span data-stu-id="63723-124">**SQLTablePrivileges**</span></span>  
  
-   <span data-ttu-id="63723-125">**SQLTables**</span><span class="sxs-lookup"><span data-stu-id="63723-125">**SQLTables**</span></span>  
  
 <span data-ttu-id="63723-126">Linked_server_name de dos partes _linked_server_name_**.** el _Catálogo_ también es compatible con *FKCatalogName* y *PKCatalogName* en [SQLForeignKeys](../../native-client-odbc-api/sqlforeignkeys.md).</span><span class="sxs-lookup"><span data-stu-id="63723-126">The two-part _linked_server_name_**.**_catalog_ is also supported for *FKCatalogName* and *PKCatalogName* on [SQLForeignKeys](../../native-client-odbc-api/sqlforeignkeys.md).</span></span>  
  
 <span data-ttu-id="63723-127">Para utilizar SQLLinkedServers y SQLLinkedCatalogs hacen falta los siguientes archivos:</span><span class="sxs-lookup"><span data-stu-id="63723-127">Using SQLLinkedServers and SQLLinkedCatalogs requires the following files:</span></span>  
  
-   <span data-ttu-id="63723-128">sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="63723-128">sqlncli.h</span></span>  
  
     <span data-ttu-id="63723-129">Incluye prototipos de función y definiciones de constante para las funciones de catálogo del servidor vinculado.</span><span class="sxs-lookup"><span data-stu-id="63723-129">Includes function prototypes and constant definitions for the linked server catalog functions.</span></span> <span data-ttu-id="63723-130">Se debe haber incluido sqlncli.h en la aplicación ODBC y ha de estar en la ruta de inclusión cuando se compile la aplicación.</span><span class="sxs-lookup"><span data-stu-id="63723-130">sqlncli.h must be included in the ODBC application and must be in the include path when the application is compiled.</span></span>  
  
-   <span data-ttu-id="63723-131">sqlncli11.lib</span><span class="sxs-lookup"><span data-stu-id="63723-131">sqlncli11.lib</span></span>  
  
     <span data-ttu-id="63723-132">Debe estar en la ruta de acceso de la biblioteca del vinculador y estar especificado como un archivo que se va a vincular.</span><span class="sxs-lookup"><span data-stu-id="63723-132">Must be in the library path of the linker and specified as a file to be linked.</span></span> <span data-ttu-id="63723-133">sqlncli11.lib se distribuye con el controlador ODBC de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="63723-133">sqlncli11.lib is distributed with the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>  
  
-   <span data-ttu-id="63723-134">sqlncli11.dll</span><span class="sxs-lookup"><span data-stu-id="63723-134">sqlncli11.dll</span></span>  
  
     <span data-ttu-id="63723-135">Debe estar presente en el momento de la ejecución.</span><span class="sxs-lookup"><span data-stu-id="63723-135">Must be present at execution time.</span></span> <span data-ttu-id="63723-136">sqlncli11.dll se distribuye con el controlador ODBC de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="63723-136">sqlncli11.dll is distributed with the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63723-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="63723-137">See Also</span></span>  
 <span data-ttu-id="63723-138">[SQL Server Native Client &#40;ODBC&#41;](sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="63723-138">[SQL Server Native Client &#40;ODBC&#41;](sql-server-native-client-odbc.md) </span></span>  
 <span data-ttu-id="63723-139">[SQLColumnPrivileges](../../native-client-odbc-api/sqlcolumnprivileges.md) </span><span class="sxs-lookup"><span data-stu-id="63723-139">[SQLColumnPrivileges](../../native-client-odbc-api/sqlcolumnprivileges.md) </span></span>  
 <span data-ttu-id="63723-140">[SQLColumns](../../native-client-odbc-api/sqlcolumns.md) </span><span class="sxs-lookup"><span data-stu-id="63723-140">[SQLColumns](../../native-client-odbc-api/sqlcolumns.md) </span></span>  
 <span data-ttu-id="63723-141">[SQLPrimaryKeys](../../native-client-odbc-api/sqlprimarykeys.md) </span><span class="sxs-lookup"><span data-stu-id="63723-141">[SQLPrimaryKeys](../../native-client-odbc-api/sqlprimarykeys.md) </span></span>  
 <span data-ttu-id="63723-142">[SQLTablePrivileges](../../native-client-odbc-api/sqltableprivileges.md) </span><span class="sxs-lookup"><span data-stu-id="63723-142">[SQLTablePrivileges](../../native-client-odbc-api/sqltableprivileges.md) </span></span>  
 <span data-ttu-id="63723-143">[SQLTables](../../native-client-odbc-api/sqltables.md) </span><span class="sxs-lookup"><span data-stu-id="63723-143">[SQLTables](../../native-client-odbc-api/sqltables.md) </span></span>  
 [<span data-ttu-id="63723-144">SQLStatistics</span><span class="sxs-lookup"><span data-stu-id="63723-144">SQLStatistics</span></span>](../../statistics/statistics.md)  
  
  
