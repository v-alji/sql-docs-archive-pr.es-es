---
title: Cambios en el comportamiento de string-length y substring | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 2119b7ba-2e52-44bf-ac57-82c2d46a48ff
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 1188823a877b4c5dc9cef13431492dfe3b303e23
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672510"
---
# <a name="changes-to-behavior-of-string-length-and-substring"></a><span data-ttu-id="b1df1-102">Cambios en el comportamiento de longitud de cadena y subcadena</span><span class="sxs-lookup"><span data-stu-id="b1df1-102">Changes to behavior of string-length and substring</span></span>
  <span data-ttu-id="b1df1-103">La [función de longitud de cadena &#40;&#41;XQuery](/sql/xquery/functions-on-string-values-string-length) y la [función Substring &#40;funciones&#41;XQuery](/sql/xquery/functions-on-string-values-substring) pueden devolver resultados diferentes cuando se utilizan con bases de datos XML que contienen caracteres suplentes.</span><span class="sxs-lookup"><span data-stu-id="b1df1-103">The [string-length Function &#40;XQuery&#41;](/sql/xquery/functions-on-string-values-string-length) and [substring Function &#40;XQuery&#41;](/sql/xquery/functions-on-string-values-substring) functions may return different results when used with XML databases that contain surrogate characters.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b1df1-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="b1df1-104">Description</span></span>  
 <span data-ttu-id="b1df1-105">Cuando una base de datos está configurada para ser compatible con [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , el comportamiento de la [función de longitud de cadena &#40;&#41;XQuery](/sql/xquery/functions-on-string-values-string-length) y la [función Substring &#40;](/sql/xquery/functions-on-string-values-substring) los cambios en las funciones&#41;de XQuery cuando se trabaja con caracteres adicionales de Unicode.</span><span class="sxs-lookup"><span data-stu-id="b1df1-105">When a database is set to be compatible with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], the behavior of the [string-length Function &#40;XQuery&#41;](/sql/xquery/functions-on-string-values-string-length) and [substring Function &#40;XQuery&#41;](/sql/xquery/functions-on-string-values-substring) functions changes when dealing with Unicode supplementary characters.</span></span> <span data-ttu-id="b1df1-106">Estas funciones consideran cada carácter suplementario Unicode, que se define por tener un punto de código superior a U+FFFF, como un carácter en lugar de dos, como sucedía en versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="b1df1-106">Each Unicode supplementary character, which is defined by having a code point larger than U+FFFF, is counted as one character by these functions rather than two, as it was in previous versions.</span></span>  
  
 <span data-ttu-id="b1df1-107">Para obtener más información sobre los caracteres suplentes, vea el tema sobre [caracteres suplementarios y suplentes](https://go.microsoft.com/fwlink/?LinkId=178317).</span><span class="sxs-lookup"><span data-stu-id="b1df1-107">For more information about surrogate characters, see [Surrogates and Supplementary Characters](https://go.microsoft.com/fwlink/?LinkId=178317).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1df1-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b1df1-108">See Also</span></span>  
 <span data-ttu-id="b1df1-109">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="b1df1-109">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="b1df1-110">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="b1df1-110">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](https://docs.microsoft.com/sql/sql-server/install/sql-server-2014-upgrade-advisor)  
  
  
