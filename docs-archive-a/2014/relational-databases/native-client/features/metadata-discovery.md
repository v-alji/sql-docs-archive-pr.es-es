---
title: Detección de metadatos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: ec3c0f4f-f838-43ce-85f2-cf2761e2aac5
author: rothja
ms.author: jroth
ms.openlocfilehash: 571df9f21ab46a53c8aba7907039ce02afd6ad05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745251"
---
# <a name="metadata-discovery"></a><span data-ttu-id="06ef1-102">Detección de metadatos</span><span class="sxs-lookup"><span data-stu-id="06ef1-102">Metadata Discovery</span></span>
  <span data-ttu-id="06ef1-103">La mejora de la detección de metadatos en [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] permite que las aplicaciones de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client tengan la seguridad de que los metadatos de parámetro o columna que se devuelven de la ejecución de una consulta son idénticos o compatibles con el formato de los metadatos especificados antes de ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="06ef1-103">The metadata discovery improvement in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] allows [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client applications to ensure that column or parameter metadata returned from the execution of a query is identical to or compatible with the metadata format you specified before you executed the query.</span></span> <span data-ttu-id="06ef1-104">Se producirá un error si los metadatos devueltos tras la ejecución de la consulta no son compatibles con el formato de los metadatos especificados antes de la ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="06ef1-104">You will receive an error if the metadata returned after query execution is not compatible with the metadata format you specified before query execution.</span></span>  
  
 <span data-ttu-id="06ef1-105">En el caso de las funciones bcp y ODBC y las interfaces IBCPSession e IBCPSession2, ahora se puede especificar una lectura diferida (detección de metadatos diferida) para evitar la detección de metadatos en operaciones de salida de consulta.</span><span class="sxs-lookup"><span data-stu-id="06ef1-105">In bcp and ODBC functions, and IBCPSession and IBCPSession2 interfaces, you can now specify a delayed read (delayed metadata discovery) to avoid metadata discovery for query out operations.</span></span> <span data-ttu-id="06ef1-106">De este modo, mejora el rendimiento y se eliminan los errores de detección de metadatos.</span><span class="sxs-lookup"><span data-stu-id="06ef1-106">This improves performance and eliminates metadata discovery failures.</span></span>  
  
 <span data-ttu-id="06ef1-107">Si desarrolla una aplicación utilizando [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client de [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] pero se conecta a una versión de servidor anterior a [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], la funcionalidad de detección de metadatos se corresponderá con la versión del servidor.</span><span class="sxs-lookup"><span data-stu-id="06ef1-107">If you develop an application using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] but connect to a server version earlier than [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], metadata discovery functionality will correspond to the version of the server.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06ef1-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="06ef1-108">Remarks</span></span>  
 <span data-ttu-id="06ef1-109">Las funciones bcp siguientes se han perfeccionado en [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] para proporcionar una detección de metadatos mejorada:</span><span class="sxs-lookup"><span data-stu-id="06ef1-109">The following bcp functions have been enhanced in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] to provide improved metadata discovery:</span></span>  
  
-   [<span data-ttu-id="06ef1-110">bcp_columns</span><span class="sxs-lookup"><span data-stu-id="06ef1-110">bcp_columns</span></span>](../../native-client-odbc-extensions-bulk-copy-functions/bcp-columns.md)  
  
-   [<span data-ttu-id="06ef1-111">bcp_control</span><span class="sxs-lookup"><span data-stu-id="06ef1-111">bcp_control</span></span>](../../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md)  
  
-   [<span data-ttu-id="06ef1-112">bcp_getcolfmt</span><span class="sxs-lookup"><span data-stu-id="06ef1-112">bcp_getcolfmt</span></span>](../../native-client-odbc-extensions-bulk-copy-functions/bcp-getcolfmt.md)  
  
-   [<span data-ttu-id="06ef1-113">bcp_readfmt</span><span class="sxs-lookup"><span data-stu-id="06ef1-113">bcp_readfmt</span></span>](../../native-client-odbc-extensions-bulk-copy-functions/bcp-readfmt.md)  
  
-   [<span data-ttu-id="06ef1-114">bcp_setcolfmt</span><span class="sxs-lookup"><span data-stu-id="06ef1-114">bcp_setcolfmt</span></span>](../../native-client-odbc-extensions-bulk-copy-functions/bcp-setcolfmt.md)  
  
 <span data-ttu-id="06ef1-115">También percibirá una mejora del rendimiento si especifica el formato del metadatos utilizando [bcp_setbulkmode](../../native-client-odbc-extensions-bulk-copy-functions/bcp-setbulkmode.md).</span><span class="sxs-lookup"><span data-stu-id="06ef1-115">You will also see a performance improvement when specifying metadata format using [bcp_setbulkmode](../../native-client-odbc-extensions-bulk-copy-functions/bcp-setbulkmode.md).</span></span>  
  
 <span data-ttu-id="06ef1-116">[bcp_control](../../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md) tiene un nuevo *eOption* para controlar el comportamiento de bcp_readfmt: `BCPDELAYREADFMT` .</span><span class="sxs-lookup"><span data-stu-id="06ef1-116">[bcp_control](../../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md) has a new *eOption* to control the behavior of bcp_readfmt: `BCPDELAYREADFMT`.</span></span>  
  
 <span data-ttu-id="06ef1-117">Las funciones ODBC siguientes se han perfeccionado en [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] para proporcionar una detección de metadatos mejorada:</span><span class="sxs-lookup"><span data-stu-id="06ef1-117">The following ODBC functions have been enhanced in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] to provide improved metadata discovery:</span></span>  
  
-   [<span data-ttu-id="06ef1-118">SQLNumResultCols</span><span class="sxs-lookup"><span data-stu-id="06ef1-118">SQLNumResultCols</span></span>](../../native-client-odbc-api/sqlnumresultcols.md)  
  
-   [<span data-ttu-id="06ef1-119">SQLDescribeCol</span><span class="sxs-lookup"><span data-stu-id="06ef1-119">SQLDescribeCol</span></span>](../../native-client-odbc-api/sqldescribecol.md)  
  
-   [<span data-ttu-id="06ef1-120">SQLNumParams</span><span class="sxs-lookup"><span data-stu-id="06ef1-120">SQLNumParams</span></span>](../../native-client-odbc-api/sqlnumparams.md)  
  
-   [<span data-ttu-id="06ef1-121">SQLDescribeParam</span><span class="sxs-lookup"><span data-stu-id="06ef1-121">SQLDescribeParam</span></span>](../../native-client-odbc-api/sqldescribeparam.md)  
  
 <span data-ttu-id="06ef1-122">Las funciones miembro de OLE DB siguientes se han perfeccionado en [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] para proporcionar una detección de metadatos mejorada:</span><span class="sxs-lookup"><span data-stu-id="06ef1-122">The following OLE DB member functions have been enhanced in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] to provide improved metadata discovery:</span></span>  
  
-   <span data-ttu-id="06ef1-123">IColumnsInfo::GetColumnInfo</span><span class="sxs-lookup"><span data-stu-id="06ef1-123">IColumnsInfo::GetColumnInfo</span></span>  
  
-   <span data-ttu-id="06ef1-124">IColumnsRowset::GetColumnsRowset</span><span class="sxs-lookup"><span data-stu-id="06ef1-124">IColumnsRowset::GetColumnsRowset</span></span>  
  
-   <span data-ttu-id="06ef1-125">ICommandWithParameters::GetParameterInfo (consulte [ICommandWithParameters](../../native-client-ole-db-interfaces/icommandwithparameters.md) para más información)</span><span class="sxs-lookup"><span data-stu-id="06ef1-125">ICommandWithParameters::GetParameterInfo (see [ICommandWithParameters](../../native-client-ole-db-interfaces/icommandwithparameters.md) for more information)</span></span>  
  
 <span data-ttu-id="06ef1-126">También percibirá una mejora del rendimiento si especifica el formato de metadatos mediante IBCPSession::BCPSetBulkMode.</span><span class="sxs-lookup"><span data-stu-id="06ef1-126">You will also see a performance improvement when specifying metadata format using IBCPSession::BCPSetBulkMode</span></span>  
  
 <span data-ttu-id="06ef1-127">La detección del metadatos mejorada en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client es posible debido a la unión de dos procedimientos almacenados de [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="06ef1-127">The improved metadata discovery in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client is possible because of the addition of two stored procedures in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)]:</span></span>  
  
-   <span data-ttu-id="06ef1-128">sp_describe_first_result_set</span><span class="sxs-lookup"><span data-stu-id="06ef1-128">sp_describe_first_result_set</span></span>  
  
-   <span data-ttu-id="06ef1-129">sp_describe_undeclared_parameters</span><span class="sxs-lookup"><span data-stu-id="06ef1-129">sp_describe_undeclared_parameters</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06ef1-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="06ef1-130">See Also</span></span>  
 [<span data-ttu-id="06ef1-131">Características de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="06ef1-131">SQL Server Native Client Features</span></span>](sql-server-native-client-features.md)  
  
  
