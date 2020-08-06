---
title: Eliminación de una tabla de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- tables [OLE DB]
- deleting tables
- SQL Server Native Client OLE DB provider, tables
- removing tables
- dropping tables
ms.assetid: b6d6c4de-43c6-473e-92aa-34ffddd58cbe
author: rothja
ms.author: jroth
ms.openlocfilehash: 4d7bea98a3afcd0022f66117b6bde2d968a866b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674078"
---
# <a name="dropping-a-sql-server-table"></a><span data-ttu-id="88004-102">Quitar una tabla de SQL Server</span><span class="sxs-lookup"><span data-stu-id="88004-102">Dropping a SQL Server Table</span></span>
  <span data-ttu-id="88004-103">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client expone la función **ITableDefinition::D roptable** .</span><span class="sxs-lookup"><span data-stu-id="88004-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **ITableDefinition::DropTable** function.</span></span> <span data-ttu-id="88004-104">Esto permite a los consumidores quitar una [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabla de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="88004-104">This allows consumers to remove a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table from a database.</span></span>  
  
 <span data-ttu-id="88004-105">Los consumidores especifican el nombre de tabla como una cadena de caracteres Unicode en el miembro *pwszName* de la unión *uName* en el parámetro *pTableID*.</span><span class="sxs-lookup"><span data-stu-id="88004-105">Consumers specify the table name as a Unicode character string in the *pwszName* member of the *uName* union in the *pTableID* parameter.</span></span> <span data-ttu-id="88004-106">El miembro *eKind* de *pTableID* debe ser DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="88004-106">The *eKind* member of *pTableID* must be DBKIND_NAME.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88004-107">Consulte también</span><span class="sxs-lookup"><span data-stu-id="88004-107">See Also</span></span>  
 [<span data-ttu-id="88004-108">Tablas e índices</span><span class="sxs-lookup"><span data-stu-id="88004-108">Tables and Indexes</span></span>](tables-and-indexes.md)  
  
  
