---
title: Comportamientos de los cursores | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- scrollable cursors [SQL Server]
- SQL Server Native Client ODBC driver, cursors
- version-based optimistic concurrency
- cursors [ODBC], cursor behaviors
- ODBC applications, cursors
- SQL_ATTR_CURSOR_SENSITIVITY option
- SQL_ATTR_CURSOR_SCROLLABLE option
- sensitivity behavior of cursor
- ODBC cursors, cursor behaviors
ms.assetid: 742ddcd2-232b-4aa1-9212-027df120ad35
author: rothja
ms.author: jroth
ms.openlocfilehash: 89c7c4e9a8dcffe03dd12f8013d5ed43810547f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672936"
---
# <a name="cursor-behaviors"></a><span data-ttu-id="529e7-102">Comportamientos de los cursores</span><span class="sxs-lookup"><span data-stu-id="529e7-102">Cursor Behaviors</span></span>
  <span data-ttu-id="529e7-103">ODBC admite las opciones ISO para especificar el comportamiento de los cursores especificando su capacidad de desplazamiento y sensibilidad.</span><span class="sxs-lookup"><span data-stu-id="529e7-103">ODBC supports the ISO options for specifying the behavior of cursors by specifying their scrollability and sensitivity.</span></span> <span data-ttu-id="529e7-104">Estos comportamientos se especifican estableciendo las opciones SQL_ATTR_CURSOR_SCROLLABLE y SQL_ATTR_CURSOR_SENSITIVITY en una llamada a [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="529e7-104">These behaviors are specified by setting the SQL_ATTR_CURSOR_SCROLLABLE and SQL_ATTR_CURSOR_SENSITIVITY options on a call to [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md).</span></span> <span data-ttu-id="529e7-105">El controlador ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client implementa estas opciones solicitando cursores de servidor con las siguientes características.</span><span class="sxs-lookup"><span data-stu-id="529e7-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver implements these options by requesting server cursors with the following characteristics.</span></span>  
  
|<span data-ttu-id="529e7-106">Valores de comportamiento de cursor</span><span class="sxs-lookup"><span data-stu-id="529e7-106">Cursor behavior settings</span></span>|<span data-ttu-id="529e7-107">Características de cursor de servidor solicitadas</span><span class="sxs-lookup"><span data-stu-id="529e7-107">Server cursor characteristics requested</span></span>|  
|------------------------------|---------------------------------------------|  
|<span data-ttu-id="529e7-108">SQL_SCROLLABLE y SQL_SENSITIVE</span><span class="sxs-lookup"><span data-stu-id="529e7-108">SQL_SCROLLABLE and SQL_SENSITIVE</span></span>|<span data-ttu-id="529e7-109">Cursor controlado por conjunto de claves y simultaneidad optimista basada en las versiones</span><span class="sxs-lookup"><span data-stu-id="529e7-109">Keyset-driven cursor and version-based optimistic concurrency</span></span>|  
|<span data-ttu-id="529e7-110">SQL_SCROLLABLE y SQL_INSENSITIVE</span><span class="sxs-lookup"><span data-stu-id="529e7-110">SQL_SCROLLABLE and SQL_INSENSITIVE</span></span>|<span data-ttu-id="529e7-111">Cursor estático y simultaneidad de solo lectura</span><span class="sxs-lookup"><span data-stu-id="529e7-111">Static cursor and read-only concurrency</span></span>|  
|<span data-ttu-id="529e7-112">SQL_SCROLLABLE y SQL_UNSPECIFIED</span><span class="sxs-lookup"><span data-stu-id="529e7-112">SQL_SCROLLABLE and SQL_UNSPECIFIED</span></span>|<span data-ttu-id="529e7-113">Cursor estático y simultaneidad de solo lectura</span><span class="sxs-lookup"><span data-stu-id="529e7-113">Static cursor and read-only concurrency</span></span>|  
|<span data-ttu-id="529e7-114">SQL_NONSCROLLABLE y SQL_SENSITIVE</span><span class="sxs-lookup"><span data-stu-id="529e7-114">SQL_NONSCROLLABLE and SQL_SENSITIVE</span></span>|<span data-ttu-id="529e7-115">Cursor de solo avance y simultaneidad optimista basada en las versiones</span><span class="sxs-lookup"><span data-stu-id="529e7-115">Forward-only cursor and version-based optimistic concurrency</span></span>|  
|<span data-ttu-id="529e7-116">SQL_NONSCROLLABLE y SQL_INSENSITIVE</span><span class="sxs-lookup"><span data-stu-id="529e7-116">SQL_NONSCROLLABLE and SQL_INSENSITIVE</span></span>|<span data-ttu-id="529e7-117">Conjunto de resultados predeterminado (solo avance, solo lectura)</span><span class="sxs-lookup"><span data-stu-id="529e7-117">Default result set (forward-only, read-only)</span></span>|  
|<span data-ttu-id="529e7-118">SQL_NONSCROLLABLE y SQL_UNSPECIFIED</span><span class="sxs-lookup"><span data-stu-id="529e7-118">SQL_NONSCROLLABLE and SQL_UNSPECIFIED</span></span>|<span data-ttu-id="529e7-119">Conjunto de resultados predeterminado (solo avance, solo lectura)</span><span class="sxs-lookup"><span data-stu-id="529e7-119">Default result set (forward-only, read-only)</span></span>|  
  
 <span data-ttu-id="529e7-120">La simultaneidad optimista basada en la versión requiere una columna **timestamp** en la tabla subyacente.</span><span class="sxs-lookup"><span data-stu-id="529e7-120">Version-based optimistic concurrency requires a **timestamp** column in the underlying table.</span></span> <span data-ttu-id="529e7-121">Si se solicita el control de simultaneidad optimista basado en versiones en una tabla que no tiene una columna de **marca** de tiempo, el servidor usa la simultaneidad optimista basada en valores.</span><span class="sxs-lookup"><span data-stu-id="529e7-121">If version-based optimistic concurrency control is requested on a table that does not have a **timestamp** column, the server uses values-based optimistic concurrency.</span></span>  
  
## <a name="scrollability"></a><span data-ttu-id="529e7-122">Desplazamiento</span><span class="sxs-lookup"><span data-stu-id="529e7-122">Scrollability</span></span>  
 <span data-ttu-id="529e7-123">Cuando SQL_ATTR_CURSOR_SCROLLABLE se establece en SQL_SCROLLABLE, el cursor admite todos los valores diferentes para el parámetro *FetchOrientation* de [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md).</span><span class="sxs-lookup"><span data-stu-id="529e7-123">When SQL_ATTR_CURSOR_SCROLLABLE is set to SQL_SCROLLABLE, the cursor supports all the different values for the *FetchOrientation* parameter of [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md).</span></span> <span data-ttu-id="529e7-124">Cuando SQL_ATTR_CURSOR_SCROLLABLE se establece en SQL_NONSCROLLABLE, el cursor solo admite un valor de *FetchOrientation* de SQL_FETCH_NEXT.</span><span class="sxs-lookup"><span data-stu-id="529e7-124">When SQL_ATTR_CURSOR_SCROLLABLE is set to SQL_NONSCROLLABLE, the cursor only supports a *FetchOrientation* value of SQL_FETCH_NEXT.</span></span>  
  
## <a name="sensitivity"></a><span data-ttu-id="529e7-125">Sensibilidad</span><span class="sxs-lookup"><span data-stu-id="529e7-125">Sensitivity</span></span>  
 <span data-ttu-id="529e7-126">Si SQL_ATTR_CURSOR_SENSITIVITY está establecido en SQL_SENSITIVE, el cursor refleja modificaciones de datos realizadas por el usuario actual o confirmadas por otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="529e7-126">When SQL_ATTR_CURSOR_SENSITIVITY is set to SQL_SENSITIVE, the cursor reflects data modifications made by the current user or committed by other users.</span></span> <span data-ttu-id="529e7-127">Si SQL_ATTR_CURSOR_SENSITIVITY está establecido en SQL_INSENSITIVE, el cursor no refleja las modificaciones de datos.</span><span class="sxs-lookup"><span data-stu-id="529e7-127">When SQL_ATTR_CURSOR_SENSITIVITY is set to SQL_INSENSITIVE, the cursor does not reflect data modifications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="529e7-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="529e7-128">See Also</span></span>  
 [<span data-ttu-id="529e7-129">Usar cursores &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="529e7-129">Using Cursors &#40;ODBC&#41;</span></span>](using-cursors-odbc.md)  
  
  
