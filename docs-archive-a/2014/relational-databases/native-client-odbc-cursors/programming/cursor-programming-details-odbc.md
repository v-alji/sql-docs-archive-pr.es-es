---
title: Detalles de programación de cursores (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, cursors
- ODBC applications, cursors
- ODBC cursors, programming
- cursors [ODBC], programming
ms.assetid: 6bae29c4-7f49-419c-8712-90db734f992e
author: rothja
ms.author: jroth
ms.openlocfilehash: 4108e195c16d321578a70852dd990f4f8d658832
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671056"
---
# <a name="cursor-programming-details-odbc"></a><span data-ttu-id="6317c-102">Detalles de la programación de cursores (ODBC)</span><span class="sxs-lookup"><span data-stu-id="6317c-102">Cursor Programming Details (ODBC)</span></span>
  <span data-ttu-id="6317c-103">Elegir el tipo de cursor correcto puede mejorar el rendimiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6317c-103">Choosing the correct cursor type can improve application performance.</span></span> <span data-ttu-id="6317c-104">Bajo ciertas condiciones, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] puede convertir implícitamente un tipo de cursor al ejecutar una instrucción SQL que no es compatible con el tipo de cursor solicitado.</span><span class="sxs-lookup"><span data-stu-id="6317c-104">Under certain conditions, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] may implicitly convert a cursor type when you execute an SQL statement that is not supported by the cursor type you requested.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6317c-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6317c-105">In This Section</span></span>  
  
-   [<span data-ttu-id="6317c-106">Conversiones de cursor implícitas &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="6317c-106">Implicit Cursor Conversions &#40;ODBC&#41;</span></span>](implicit-cursor-conversions-odbc.md)  
  
-   [<span data-ttu-id="6317c-107">Usar la captura automática con cursores ODBC</span><span class="sxs-lookup"><span data-stu-id="6317c-107">Using Autofetch with ODBC Cursors</span></span>](using-autofetch-with-odbc-cursors.md)  
  
-   [<span data-ttu-id="6317c-108">Cursores de solo avance rápido &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="6317c-108">Fast Forward-Only Cursors &#40;ODBC&#41;</span></span>](fast-forward-only-cursors-odbc.md)  
  
## <a name="see-also"></a><span data-ttu-id="6317c-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6317c-109">See Also</span></span>  
 [<span data-ttu-id="6317c-110">Usar cursores &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="6317c-110">Using Cursors &#40;ODBC&#41;</span></span>](../using-cursors-odbc.md)  
  
  
