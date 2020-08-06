---
title: Eliminación de un índice de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- removing indexes
- deleting indexes
- DropIndex function
- dropping indexes
- SQL Server Native Client OLE DB provider, indexes
- indexes [OLE DB]
ms.assetid: add3ba14-10b1-4723-b7c0-3e83689e9fdd
author: rothja
ms.author: jroth
ms.openlocfilehash: 1267cc92645ff8b28757ad2d266e58917fcb4b28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674079"
---
# <a name="dropping-a-sql-server-index"></a><span data-ttu-id="46b9f-102">Quitar un índice de SQL Server</span><span class="sxs-lookup"><span data-stu-id="46b9f-102">Dropping a SQL Server Index</span></span>
  <span data-ttu-id="46b9f-103">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client expone la función **IIndexDefinition::D ropindex** .</span><span class="sxs-lookup"><span data-stu-id="46b9f-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **IIndexDefinition::DropIndex** function.</span></span> <span data-ttu-id="46b9f-104">Esto permite que los consumidores quiten índices de las tablas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46b9f-104">This allows consumers to remove an index from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="46b9f-105">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client expone algunas [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] restricciones PRIMARY KEY y Unique como índices.</span><span class="sxs-lookup"><span data-stu-id="46b9f-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes some [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PRIMARY KEY and UNIQUE constraints as indexes.</span></span> <span data-ttu-id="46b9f-106">El propietario de la tabla, el propietario de la base de datos y algunos miembros con roles administrativos pueden modificar las tablas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], quitando una restricción.</span><span class="sxs-lookup"><span data-stu-id="46b9f-106">The table owner, database owner, and some administrative role members can modify a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table, dropping a constraint.</span></span> <span data-ttu-id="46b9f-107">De forma predeterminada, solo el propietario de la tabla puede quitar un índice existente.</span><span class="sxs-lookup"><span data-stu-id="46b9f-107">By default, only the table owner can drop an existing index.</span></span> <span data-ttu-id="46b9f-108">Por tanto, que **DropIndex** se realice correctamente o no depende no solo de los derechos de acceso del usuario de la aplicación sino también del tipo de índice indicado.</span><span class="sxs-lookup"><span data-stu-id="46b9f-108">Therefore, **DropIndex** success or failure depends not only on the application user's access rights but also on the type of index indicated.</span></span>  
  
 <span data-ttu-id="46b9f-109">Los consumidores especifican el nombre de tabla como una cadena de caracteres Unicode en el miembro *pwszName* de la unión *uName* en el parámetro *pTableID*.</span><span class="sxs-lookup"><span data-stu-id="46b9f-109">Consumers specify the table name as a Unicode character string in the *pwszName* member of the *uName* union in the *pTableID* parameter.</span></span> <span data-ttu-id="46b9f-110">El miembro *eKind* de *pTableID* debe ser DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="46b9f-110">The *eKind* member of *pTableID* must be DBKIND_NAME.</span></span>  
  
 <span data-ttu-id="46b9f-111">Los consumidores especifican el nombre de índice como una cadena de caracteres Unicode en el miembro *pwszName* de la unión *uName* en el parámetro *pIndexID*.</span><span class="sxs-lookup"><span data-stu-id="46b9f-111">Consumers specify the index name as a Unicode character string in the *pwszName* member of the *uName* union in the *pIndexID* parameter.</span></span> <span data-ttu-id="46b9f-112">El miembro *eKind* de *pIndexID* debe ser DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="46b9f-112">The *eKind* member of *pIndexID* must be DBKIND_NAME.</span></span> <span data-ttu-id="46b9f-113">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client no admite la característica OLE DB de quitar todos los índices de una tabla cuando *pIndexID* es NULL.</span><span class="sxs-lookup"><span data-stu-id="46b9f-113">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support the OLE DB feature of dropping all indexes on a table when *pIndexID* is null.</span></span> <span data-ttu-id="46b9f-114">Si *pIndexID* es NULL, se devuelve E_INVALIDARG.</span><span class="sxs-lookup"><span data-stu-id="46b9f-114">If *pIndexID* is null, E_INVALIDARG is returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46b9f-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="46b9f-115">See Also</span></span>  
 <span data-ttu-id="46b9f-116">[Tablas e índices](tables-and-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="46b9f-116">[Tables and Indexes](tables-and-indexes.md) </span></span>  
 <span data-ttu-id="46b9f-117">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="46b9f-117">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span></span>  
 [<span data-ttu-id="46b9f-118">DROP INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="46b9f-118">DROP INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-index-transact-sql)  
  
  
