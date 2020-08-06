---
title: Adición de una columna a una tabla de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- columns [OLE DB]
- AddColumn function
- SQL Server Native Client OLE DB provider, columns
- adding columns
ms.assetid: 22bae18a-bc9d-4617-8660-ed8b17a468d4
author: rothja
ms.author: jroth
ms.openlocfilehash: 97aa2656ccde662a34e1dd80fd662b22f601d4ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749263"
---
# <a name="adding-a-column-to-a-sql-server-table"></a><span data-ttu-id="225fc-102">Agregar una columna a una tabla de SQL Server</span><span class="sxs-lookup"><span data-stu-id="225fc-102">Adding a Column to a SQL Server Table</span></span>
  <span data-ttu-id="225fc-103">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client expone la función **ITableDefinition:: addColumn** .</span><span class="sxs-lookup"><span data-stu-id="225fc-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **ITableDefinition::AddColumn** function.</span></span> <span data-ttu-id="225fc-104">Esto permite que los consumidores agreguen una columna a una tabla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="225fc-104">This allows consumers to add a column to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="225fc-105">Al agregar una columna a una [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabla, el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consumidor del proveedor de OLE DB de Native Client está restringido de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="225fc-105">When you add a column to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer is constrained as follows:</span></span>  
  
-   <span data-ttu-id="225fc-106">Si DBPROP_COL_AUTOINCREMENT es VARIANT_TRUE, DBPROP_COL_NULLABLE debe ser VARIANT_FALSE.</span><span class="sxs-lookup"><span data-stu-id="225fc-106">If DBPROP_COL_AUTOINCREMENT is VARIANT_TRUE, DBPROP_COL_NULLABLE must be VARIANT_FALSE.</span></span>  
  
-   <span data-ttu-id="225fc-107">Si la columna se define mediante el tipo de datos  **timestamp** de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], DBPROP_COL_NULLABLE debe ser VARIANT_FALSE.</span><span class="sxs-lookup"><span data-stu-id="225fc-107">If the column is defined by using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **timestamp** data type, DBPROP_COL_NULLABLE must be VARIANT_FALSE.</span></span>  
  
-   <span data-ttu-id="225fc-108">Para cualquier otra definición de columna, DBPROP_COL_NULLABLE debe ser VARIANT_TRUE.</span><span class="sxs-lookup"><span data-stu-id="225fc-108">For any other column definition, DBPROP_COL_NULLABLE must be VARIANT_TRUE.</span></span>  
  
 <span data-ttu-id="225fc-109">Los consumidores especifican el nombre de tabla como una cadena de caracteres Unicode en el miembro *pwszName* de la unión *uName* en el parámetro *pTableID*.</span><span class="sxs-lookup"><span data-stu-id="225fc-109">Consumers specify the table name as a Unicode character string in the *pwszName* member of the *uName* union in the *pTableID* parameter.</span></span> <span data-ttu-id="225fc-110">El miembro *eKind* de *pTableID* debe ser DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="225fc-110">The *eKind* member of *pTableID* must be DBKIND_NAME.</span></span>  
  
 <span data-ttu-id="225fc-111">El nuevo nombre de columna se especifica como una cadena de caracteres Unicode en el miembro *pwszName* de la unión *uName* en el miembro *dbcid* del parámetro DBCOLUMNDESC *pColumnDesc*.</span><span class="sxs-lookup"><span data-stu-id="225fc-111">The new column name is specified as a Unicode character string in the *pwszName* member of the *uName* union in the *dbcid* member of the DBCOLUMNDESC parameter *pColumnDesc*.</span></span> <span data-ttu-id="225fc-112">El miembro *eKind* debe ser DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="225fc-112">The *eKind* member must be DBKIND_NAME.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="225fc-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="225fc-113">See Also</span></span>  
 <span data-ttu-id="225fc-114">[Tablas e índices](tables-and-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="225fc-114">[Tables and Indexes](tables-and-indexes.md) </span></span>  
 [<span data-ttu-id="225fc-115">ALTER TABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="225fc-115">ALTER TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-table-transact-sql)  
  
  
