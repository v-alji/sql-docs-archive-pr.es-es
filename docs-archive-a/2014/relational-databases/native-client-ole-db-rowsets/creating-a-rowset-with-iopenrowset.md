---
title: Creación de un conjunto de filas con IOpenRowset | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- IOpenRowset interface
- rowsets [OLE DB], creating
- SQL Server Native Client OLE DB provider, rowsets
- OLE DB rowsets, creating
ms.assetid: e8bc3de7-4b97-4de9-8df8-e11947d24045
author: rothja
ms.author: jroth
ms.openlocfilehash: bf74466a698d39f74b9531adaa54c79c75e50ef2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749267"
---
# <a name="creating-a-rowset-with-iopenrowset"></a><span data-ttu-id="b75d8-102">Crear un conjunto de filas con IOpenRowset</span><span class="sxs-lookup"><span data-stu-id="b75d8-102">Creating a Rowset with IOpenRowset</span></span>
  <span data-ttu-id="b75d8-103">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client admite el método **IOpenRowset:: OPENROWSET** con las siguientes restricciones:</span><span class="sxs-lookup"><span data-stu-id="b75d8-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports the **IOpenRowset::OpenRowset** method with the following restrictions:</span></span>  
  
-   <span data-ttu-id="b75d8-104">Debe especificarse una tabla base o una vista en una estructura de identificador de base de datos (DBID) a la que apunte el parámetro *pTableID*.</span><span class="sxs-lookup"><span data-stu-id="b75d8-104">A base table or view must be specified in a database ID (DBID) structure that the *pTableID* parameter points to.</span></span>  
  
-   <span data-ttu-id="b75d8-105">El miembro *eKind* de DBID debe indicar DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="b75d8-105">The DBID *eKind* member must indicate DBKIND_NAME.</span></span>  
  
-   <span data-ttu-id="b75d8-106">El miembro *uName* de DBID debe especificar el nombre de una tabla base existente o una vista como una cadena de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="b75d8-106">The DBID *uName* member must specify the name of an existing base table or a view as a Unicode character string.</span></span>  
  
-   <span data-ttu-id="b75d8-107">El parámetro *pIndexID* de **OpenRowset** debe ser NULL.</span><span class="sxs-lookup"><span data-stu-id="b75d8-107">The *pIndexID* parameter of **OpenRowset** must be NULL.</span></span>  
  
 <span data-ttu-id="b75d8-108">El conjunto de resultados de **IOpenRowset::OpenRowset** contiene un único conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="b75d8-108">The result set of **IOpenRowset::OpenRowset** contains a single rowset.</span></span> <span data-ttu-id="b75d8-109">Los conjuntos de resultados que contienen un único conjunto de filas pueden ser compatibles con los [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cursores.</span><span class="sxs-lookup"><span data-stu-id="b75d8-109">Result sets that contain a single rowset can be supported by [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cursors.</span></span> <span data-ttu-id="b75d8-110">La compatibilidad de cursor permite que el programador utilice mecanismos de simultaneidad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b75d8-110">Cursor support allows the developer to use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] concurrency mechanisms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b75d8-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b75d8-111">See Also</span></span>  
 [<span data-ttu-id="b75d8-112">Conjuntos de filas</span><span class="sxs-lookup"><span data-stu-id="b75d8-112">Rowsets</span></span>](rowsets.md)  
  
  
