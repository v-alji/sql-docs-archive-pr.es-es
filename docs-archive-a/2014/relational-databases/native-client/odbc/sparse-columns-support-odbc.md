---
title: Compatibilidad con columnas dispersas (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 11ae959f-2fb6-4b85-ac5d-1476a82136d4
author: rothja
ms.author: jroth
ms.openlocfilehash: 076709f3f37e92492f7c3f8c20ee692416d9e867
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746970"
---
# <a name="sparse-columns-support-odbc"></a><span data-ttu-id="b048a-102">Compatibilidad con columnas dispersas (ODBC)</span><span class="sxs-lookup"><span data-stu-id="b048a-102">Sparse Columns Support (ODBC)</span></span>
  <span data-ttu-id="b048a-103">En este tema se describe la compatibilidad ODBC de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client con columnas dispersas.</span><span class="sxs-lookup"><span data-stu-id="b048a-103">This topic describes [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC support for sparse columns.</span></span> <span data-ttu-id="b048a-104">Para ver un ejemplo que muestra la compatibilidad de ODBC con columnas dispersas, consulte [llamar a SQLColumns en una tabla con columnas dispersas](../../native-client-odbc-how-to/call-sqlcolumns-on-a-table-with-sparse-columns.md).</span><span class="sxs-lookup"><span data-stu-id="b048a-104">For a sample demonstrating ODBC support for sparse columns, see [Call SQLColumns on a Table with Sparse Columns](../../native-client-odbc-how-to/call-sqlcolumns-on-a-table-with-sparse-columns.md).</span></span> <span data-ttu-id="b048a-105">Para obtener más información sobre las columnas dispersas, consulte [compatibilidad con columnas dispersas en SQL Server Native Client](../features/sparse-columns-support-in-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="b048a-105">For more information about sparse columns, see [Sparse Columns Support in SQL Server Native Client](../features/sparse-columns-support-in-sql-server-native-client.md).</span></span>  
  
## <a name="statement-metadata"></a><span data-ttu-id="b048a-106">Metadatos de instrucción</span><span class="sxs-lookup"><span data-stu-id="b048a-106">Statement Metadata</span></span>  
 <span data-ttu-id="b048a-107">El campo del descriptor de parámetros de la aplicación (APD) y el atributo de instrucción SQL_SOPT_SS_NAME_SCOPE aceptan los valores adicionales SQL_SS_NAME_SCOPE_EXTENDED y SQL_SS_NAME_SCOPE_SPARSE_COLUMN_SET.</span><span class="sxs-lookup"><span data-stu-id="b048a-107">The application parameter descriptor (APD) descriptor field and SQL_SOPT_SS_NAME_SCOPE statement attribute accepts the additional values SQL_SS_NAME_SCOPE_EXTENDED and SQL_SS_NAME_SCOPE_SPARSE_COLUMN_SET.</span></span> <span data-ttu-id="b048a-108">Estos valores especifican qué columnas se incluyen en el conjunto de resultados devuelto por [SQLColumns](../../native-client-odbc-api/sqlcolumns.md).</span><span class="sxs-lookup"><span data-stu-id="b048a-108">These values specify which columns are included in the result set returned by [SQLColumns](../../native-client-odbc-api/sqlcolumns.md).</span></span> <span data-ttu-id="b048a-109">Para obtener más información acerca de SQL_SOPT_SS_NAME_SCOPE, vea [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="b048a-109">For more information about SQL_SOPT_SS_NAME_SCOPE, see [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span></span>  
  
 <span data-ttu-id="b048a-110">Es posible utilizar un nuevo descriptor de filas de implementación (IRD), un campo SQLSMALLINT de solo lectura denominado SQL_CA_SS_IS_COLUMN_SET, para determinar si una columna es un valor `column_set` XML.</span><span class="sxs-lookup"><span data-stu-id="b048a-110">A new implementation row descriptor (IRD), a read-only SQLSMALLINT field called SQL_CA_SS_IS_COLUMN_SET, can be used to determine if a column is an XML `column_set` value.</span></span> <span data-ttu-id="b048a-111">SQL_CA_SS_IS_COLUMN_SET toma los valores SQL_TRUE y SQL_FALSE.</span><span class="sxs-lookup"><span data-stu-id="b048a-111">SQL_CA_SS_IS_COLUMN_SET takes the values SQL_TRUE and SQL_FALSE.</span></span>  
  
## <a name="catalog-metadata"></a><span data-ttu-id="b048a-112">Metadatos de catálogo</span><span class="sxs-lookup"><span data-stu-id="b048a-112">Catalog Metadata</span></span>  
 <span data-ttu-id="b048a-113">Se han agregado dos columnas específicas de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (SS_IS_SPARSE y SS_IS_COLUMN_SET) al conjunto de resultados de [SQLColumns](../../native-client-odbc-api/sqlcolumns.md).</span><span class="sxs-lookup"><span data-stu-id="b048a-113">Two [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] specific columns (SS_IS_SPARSE and SS_IS_COLUMN_SET) have been added to the result set for [SQLColumns](../../native-client-odbc-api/sqlcolumns.md).</span></span>  
  
## <a name="odbc-function-support-for-sparse-columns"></a><span data-ttu-id="b048a-114">Compatibilidad de funciones ODBC con columnas dispersas</span><span class="sxs-lookup"><span data-stu-id="b048a-114">ODBC Function Support for Sparse Columns</span></span>  
 <span data-ttu-id="b048a-115">Las funciones ODBC que se muestran a continuación se han actualizado para admitir columnas dispersas en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client:</span><span class="sxs-lookup"><span data-stu-id="b048a-115">The following ODBC functions have been updated to support sparse columns in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client:</span></span>  
  
-   [<span data-ttu-id="b048a-116">SQLColAttribute</span><span class="sxs-lookup"><span data-stu-id="b048a-116">SQLColAttribute</span></span>](../../native-client-odbc-api/sqlcolattribute.md)  
  
-   [<span data-ttu-id="b048a-117">SQLColumns</span><span class="sxs-lookup"><span data-stu-id="b048a-117">SQLColumns</span></span>](../../native-client-odbc-api/sqlcolumns.md)  
  
-   [<span data-ttu-id="b048a-118">SQLGetDescField</span><span class="sxs-lookup"><span data-stu-id="b048a-118">SQLGetDescField</span></span>](../../native-client-odbc-api/sqlgetdescfield.md)  
  
-   [<span data-ttu-id="b048a-119">SQLSetDescField</span><span class="sxs-lookup"><span data-stu-id="b048a-119">SQLSetDescField</span></span>](../../native-client-odbc-api/sqlsetdescfield.md)  
  
-   [<span data-ttu-id="b048a-120">SQLSetStmtAttr</span><span class="sxs-lookup"><span data-stu-id="b048a-120">SQLSetStmtAttr</span></span>](../../native-client-odbc-api/sqlsetstmtattr.md)  
  
## <a name="see-also"></a><span data-ttu-id="b048a-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b048a-121">See Also</span></span>  
 [<span data-ttu-id="b048a-122">SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="b048a-122">SQL Server Native Client &#40;ODBC&#41;</span></span>](sql-server-native-client-odbc.md)  
  
  
