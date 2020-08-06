---
title: Tipos de cursor | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, cursors
- ODBC applications, cursors
- cursors [ODBC], types
- ODBC cursors, types
ms.assetid: 3a916cc7-f352-42cb-8b83-f78e06cef991
author: rothja
ms.author: jroth
ms.openlocfilehash: 6937dbb9ce42cd5631201e0c97be42b211742ada
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671071"
---
# <a name="cursor-types"></a><span data-ttu-id="afd47-102">Tipos de cursor</span><span class="sxs-lookup"><span data-stu-id="afd47-102">Cursor Types</span></span>
  <span data-ttu-id="afd47-103">ODBC define cuatro tipos de cursor compatibles con Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] controlador ODBC de Native Client.</span><span class="sxs-lookup"><span data-stu-id="afd47-103">ODBC defines four cursor types supported by Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span> <span data-ttu-id="afd47-104">Estos cursores varían en función de la capacidad de detectar cambios en el conjunto de resultados y en los recursos que consumen, como la memoria y el espacio en **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="afd47-104">These cursors vary in their ability to detect changes to the result set and in the resources they consume, such as memory and space in **tempdb**.</span></span> <span data-ttu-id="afd47-105">Un cursor solamente puede detectar cambios en las filas cuando intenta volver a capturar estas filas; el origen de datos no dispone de ningún método para notificar al cursor los cambios en las filas actualmente capturadas.</span><span class="sxs-lookup"><span data-stu-id="afd47-105">A cursor can detect changes to rows only when it tries to refetch those rows; there is no way for the data source to notify the cursor of changes to the currently fetched rows.</span></span> <span data-ttu-id="afd47-106">El nivel de aislamiento de transacción también afecta la capacidad de un cursor para detectar modificaciones que no se realizaron a través del cursor.</span><span class="sxs-lookup"><span data-stu-id="afd47-106">A cursor's ability to detect changes that were not made through the cursor is also influenced by the transaction isolation level.</span></span>  
  
 <span data-ttu-id="afd47-107">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] admite cuatro tipos de cursor ODBC:</span><span class="sxs-lookup"><span data-stu-id="afd47-107">These are the four ODBC cursor types supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="afd47-108">Los cursores de solo avance no admiten el desplazamiento; solo admiten la captura de filas en serie desde el inicio hasta el final del cursor.</span><span class="sxs-lookup"><span data-stu-id="afd47-108">Forward-only cursors do not support scrolling; they only support fetching rows serially from the start to the end of the cursor.</span></span>  
  
-   <span data-ttu-id="afd47-109">Los cursores estáticos se crean en **tempdb** cuando se abre el cursor.</span><span class="sxs-lookup"><span data-stu-id="afd47-109">Static cursors are built in **tempdb** when the cursor is opened.</span></span> <span data-ttu-id="afd47-110">Siempre muestran el conjunto de resultados tal como estaba al abrir el cursor.</span><span class="sxs-lookup"><span data-stu-id="afd47-110">They always display the result set as it was when the cursor was opened.</span></span> <span data-ttu-id="afd47-111">Nunca reflejan los cambios en los datos.</span><span class="sxs-lookup"><span data-stu-id="afd47-111">They never reflect changes to the data.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="afd47-112">cursores estáticos son siempre de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="afd47-112">static cursors are always read-only.</span></span> <span data-ttu-id="afd47-113">Dado que un cursor de servidor estático se genera como una tabla de trabajo en **tempdb**, el tamaño del conjunto de resultados del cursor no puede superar el tamaño de fila máximo permitido por [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="afd47-113">Because a static server cursor is built as a work table in **tempdb**, the size of the cursor result set cannot exceed the maximum row size allowed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="afd47-114">En los cursores controlados por conjunto de claves, la pertenencia y el orden de las filas del conjunto de resultados se fijan al abrir el cursor.</span><span class="sxs-lookup"><span data-stu-id="afd47-114">Keyset-driven cursors have the membership and order of rows in the result set fixed when the cursor is opened.</span></span> <span data-ttu-id="afd47-115">Los cambios en las columnas sin clave son visibles a través del cursor.</span><span class="sxs-lookup"><span data-stu-id="afd47-115">Changes to nonkey columns are visible through the cursor.</span></span>  
  
-   <span data-ttu-id="afd47-116">Los cursores dinámicos son los opuestos a los cursores estáticos.</span><span class="sxs-lookup"><span data-stu-id="afd47-116">Dynamic cursors are the opposite of static cursors.</span></span> <span data-ttu-id="afd47-117">Reflejan todas las modificaciones realizadas en las filas de su conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="afd47-117">Dynamic cursors reflect all changes made to the rows in their result set.</span></span> <span data-ttu-id="afd47-118">Los valores de datos, el orden y la pertenencia de las filas del conjunto de resultados pueden cambiar con cada captura.</span><span class="sxs-lookup"><span data-stu-id="afd47-118">The data values, order, and membership of the rows in the result set can change on each fetch.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afd47-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="afd47-119">See Also</span></span>  
 [<span data-ttu-id="afd47-120">Usar cursores &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="afd47-120">Using Cursors &#40;ODBC&#41;</span></span>](using-cursors-odbc.md)  
  
  
