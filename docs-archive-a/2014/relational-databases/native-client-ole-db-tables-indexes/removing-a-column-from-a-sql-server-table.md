---
title: Eliminación de una columna de una tabla de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- columns [OLE DB]
- removing columns
- DropColumn function
- SQL Server Native Client OLE DB provider, columns
ms.assetid: 210811b7-cbd6-421e-bc6e-df9482236768
author: rothja
ms.author: jroth
ms.openlocfilehash: 8f40c466910aae7e0d349cd4a65ab265282bc8eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674077"
---
# <a name="removing-a-column-from-a-sql-server-table"></a><span data-ttu-id="bd63e-102">Quitar una columna de una tabla de SQL Server</span><span class="sxs-lookup"><span data-stu-id="bd63e-102">Removing a Column from a SQL Server Table</span></span>
  <span data-ttu-id="bd63e-103">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client expone la función **ITableDefinition::D ropcolumn** .</span><span class="sxs-lookup"><span data-stu-id="bd63e-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **ITableDefinition::DropColumn** function.</span></span> <span data-ttu-id="bd63e-104">Esto permite que los consumidores puedan quitar una columna de una tabla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd63e-104">This allows consumers to remove a column from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="bd63e-105">Los consumidores especifican el nombre de la tabla como una cadena de caracteres Unicode en el miembro *pwszName* de la unión *uName* en el parámetro *pTableID*.</span><span class="sxs-lookup"><span data-stu-id="bd63e-105">Consumers specify the table name as a Unicode character string in the *pwszName*member of the *uName* union in the *pTableID* parameter.</span></span> <span data-ttu-id="bd63e-106">El miembro *eKind* de *pTableID* debe ser DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="bd63e-106">The *eKind*member of *pTableID* must be DBKIND_NAME.</span></span>  
  
 <span data-ttu-id="bd63e-107">El consumidor indica un nombre de columna en el miembro *pwszName* de la unión *uName* en el parámetro *pColumnID*.</span><span class="sxs-lookup"><span data-stu-id="bd63e-107">The consumer indicates a column name in the *pwszName*member of the *uName* union in the *pColumnID* parameter.</span></span> <span data-ttu-id="bd63e-108">El nombre de la columna es una cadena de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="bd63e-108">The column name is a Unicode character string.</span></span> <span data-ttu-id="bd63e-109">El miembro *eKind* de *pColumnID* debe ser DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="bd63e-109">The *eKind* member of *pColumnID* must be DBKIND_NAME.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd63e-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bd63e-110">Example</span></span>  
  
### <a name="code"></a><span data-ttu-id="bd63e-111">Código</span><span class="sxs-lookup"><span data-stu-id="bd63e-111">Code</span></span>  
  
```  
DBID TableID;  
DBID ColumnID;  
HRESULT hr;  
  
TableID.eKind = DBKIND_NAME;  
TableID.uName.pwszName = L"MyTableName";  
  
ColumnID.eKind = DBKIND_NAME;  
ColumnID.uName.pwszName = L"MyColumnName";  
  
hr = m_pITableDefinition->DropColumn(&TableID, &ColumnID);  
```  
  
## <a name="see-also"></a><span data-ttu-id="bd63e-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bd63e-112">See Also</span></span>  
 [<span data-ttu-id="bd63e-113">Tablas e índices</span><span class="sxs-lookup"><span data-stu-id="bd63e-113">Tables and Indexes</span></span>](tables-and-indexes.md)  
  
  
