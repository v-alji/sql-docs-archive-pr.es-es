---
title: Compatibilidad con FILESTREAM | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- FILESTREAM [SQL Server], SQL Server Native Client
- SQL Server Native Client [FILESTREAM support]
ms.assetid: 1ad3400d-7fcd-40c9-87ae-f5afc61e0374
author: rothja
ms.author: jroth
ms.openlocfilehash: 18e9a002bfb205e2c0807234550998fe48120d20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745258"
---
# <a name="filestream-support"></a><span data-ttu-id="9d41d-102">Compatibilidad con FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="9d41d-102">FILESTREAM Support</span></span>
  <span data-ttu-id="9d41d-103">FILESTREAM proporciona un modo de almacenar y obtener acceso a valores binarios grandes, ya sea a través de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] o mediante acceso directo al sistema de archivos de Windows.</span><span class="sxs-lookup"><span data-stu-id="9d41d-103">FILESTREAM provides a way to store and access large binary values, either through [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or by direct access to the Windows file system.</span></span> <span data-ttu-id="9d41d-104">Un valor binario grande es un valor superior a 2 gigabytes (GB).</span><span class="sxs-lookup"><span data-stu-id="9d41d-104">A large binary value is a value larger than 2 gigabytes (GB).</span></span> <span data-ttu-id="9d41d-105">Para obtener más información acerca de la compatibilidad mejorada con FILESTREAM, vea [FILESTREAM &#40;SQL Server&#41;](../../blob/filestream-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9d41d-105">For more information about enhanced FILESTREAM support, see [FILESTREAM &#40;SQL Server&#41;](../../blob/filestream-sql-server.md).</span></span>  
  
 <span data-ttu-id="9d41d-106">Cuando se abra una conexión de base de datos, `@@TEXTSIZE` se establecerá en -1 ("ilimitado") de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9d41d-106">When a database connection is opened, `@@TEXTSIZE` will be set to -1 ("unlimited"), by default.</span></span>  
  
 <span data-ttu-id="9d41d-107">También es posible obtener acceso a columnas FILESTREAM y actualizarlas mediante las API del sistema de archivos de Windows.</span><span class="sxs-lookup"><span data-stu-id="9d41d-107">It is also possible to access and update FILESTREAM columns using Windows file system APIs.</span></span>  
  
 <span data-ttu-id="9d41d-108">Para obtener más información, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="9d41d-108">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="9d41d-109">Compatibilidad con FILESTREAM &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="9d41d-109">FILESTREAM Support &#40;OLE DB&#41;</span></span>](../ole-db/filestream-support-ole-db.md)  
  
-   [<span data-ttu-id="9d41d-110">Compatibilidad de FILESTREAM &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="9d41d-110">FILESTREAM Support &#40;ODBC&#41;</span></span>](../odbc/filestream-support-odbc.md)  
  
-   [<span data-ttu-id="9d41d-111">Obtener acceso a los datos FILESTREAM con OpenSqlFilestream</span><span class="sxs-lookup"><span data-stu-id="9d41d-111">Access FILESTREAM Data with OpenSqlFilestream</span></span>](../../blob/access-filestream-data-with-opensqlfilestream.md)  
  
## <a name="querying-for-filestream-columns"></a><span data-ttu-id="9d41d-112">Consulta de columnas FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="9d41d-112">Querying for FILESTREAM Columns</span></span>  
 <span data-ttu-id="9d41d-113">Los conjuntos de filas de esquema de OLE DB no notificarán si una columna es una columna FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="9d41d-113">Schema rowsets in OLE DB will not report whether a column is a FILESTREAM column.</span></span> <span data-ttu-id="9d41d-114">ITableDefinition de OLE DB no puede utilizarse para crear una columna FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="9d41d-114">ITableDefinition in OLE DB cannot be used to create a FILESTREAM column.</span></span>  
  
 <span data-ttu-id="9d41d-115">Las funciones de catálogo como SQLColumns en ODBC no notificarán si una columna es una columna FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="9d41d-115">Catalog functions such as SQLColumns in ODBC will not report whether a column is a FILESTREAM column.</span></span>  
  
 <span data-ttu-id="9d41d-116">Para crear columnas FILESTREAM o para detectar qué columnas existentes son columnas FILESTREAM, puede usar la `is_filestream` columna de la vista de catálogo [Sys. Columns](/sql/relational-databases/system-catalog-views/sys-columns-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="9d41d-116">To create FILESTREAM columns or to detect which existing columns are FILESTREAM columns, you can use the `is_filestream` column of the [sys.columns](/sql/relational-databases/system-catalog-views/sys-columns-transact-sql) catalog view.</span></span>  
  
 <span data-ttu-id="9d41d-117">A continuación se muestra un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9d41d-117">The following is an example:</span></span>  
  
```  
-- Create a table with a FILESTREAM column.  
CREATE TABLE Bob_01 (GuidCol1 uniqueidentifier ROWGUIDCOL NOT NULL UNIQUE DEFAULT NEWID(), IntCol2 int, varbinaryCol3 varbinary(max) FILESTREAM);  
  
-- Find FILESTREAM columns.  
SELECT name FROM sys.columns WHERE is_filestream=1;  
  
-- Determine whether a column is a FILESTREAM column.  
SELECT is_filestream FROM sys.columns WHERE name = 'varbinaryCol3' AND object_id IN (SELECT object_id FROM sys.tables WHERE name='Bob_01');  
```  
  
## <a name="down-level-compatibility"></a><span data-ttu-id="9d41d-118">Compatibilidad con niveles inferiores</span><span class="sxs-lookup"><span data-stu-id="9d41d-118">Down-Level Compatibility</span></span>  
 <span data-ttu-id="9d41d-119">Si el cliente se compiló con la versión de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client que se incluía con [!INCLUDE[ssVersion2005](../../../includes/sscurrent-md.md)] , el `varbinary(max)` comportamiento será compatible con [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9d41d-119">If your client was compiled using the version of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client that was included with [!INCLUDE[ssVersion2005](../../../includes/sscurrent-md.md)], `varbinary(max)` behavior will be compatible with [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="9d41d-120">Es decir, el tamaño máximo de los datos devueltos se limitará a 2 GB.</span><span class="sxs-lookup"><span data-stu-id="9d41d-120">That is, the maximum size of returned data will be limited to 2 GB.</span></span> <span data-ttu-id="9d41d-121">Los resultados cuyo valor supere los 2 GB, se truncarán, y se devolverá una advertencia de tipo "datos de cadena truncados por la derecha".</span><span class="sxs-lookup"><span data-stu-id="9d41d-121">For result values larger that 2 GB, truncation will occur and a "string data right truncation" warning will be returned.</span></span>  
  
 <span data-ttu-id="9d41d-122">Cuando la compatibilidad de tipo de datos se establezca en 80, el comportamiento del cliente será coherente con el comportamiento del cliente de nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="9d41d-122">When data-type compatibility is set to 80, client behavior will be consistent with down-level client behavior.</span></span>  
  
 <span data-ttu-id="9d41d-123">En el caso de los clientes que usan SQLOLEDB u otros proveedores que se publicaron antes que [!INCLUDE[ssVersion2005](../../../includes/ssnoversion-md.md)] Native Client, se `varbinary(max)` asignarán a la imagen.</span><span class="sxs-lookup"><span data-stu-id="9d41d-123">For clients that use SQLOLEDB or other providers that were released before the [!INCLUDE[ssVersion2005](../../../includes/ssnoversion-md.md)] Native Client, `varbinary(max)` will be mapped to image.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d41d-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9d41d-124">See Also</span></span>  
 [<span data-ttu-id="9d41d-125">Características de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="9d41d-125">SQL Server Native Client Features</span></span>](sql-server-native-client-features.md)  
  
  
