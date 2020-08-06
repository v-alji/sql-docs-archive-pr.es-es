---
title: Identificadores de SQL Server de escape | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: 8a73e945-daa6-4e5d-93da-10f000f1f3a2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1821187632aeeea0b7a18bf9c4d51d933e947d43
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673053"
---
# <a name="escape-sql-server-identifiers"></a><span data-ttu-id="3bb4c-102">Identificadores de SQL Server de escape</span><span class="sxs-lookup"><span data-stu-id="3bb4c-102">Escape SQL Server Identifiers</span></span>
  <span data-ttu-id="3bb4c-103">A menudo, se puede usar el carácter de escape de acento invertido (\`) de Windows PowerShell para hacer que se eludan los caracteres que se permiten en los identificadores delimitados de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] pero no en los nombres de ruta de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3bb4c-103">You can often use the Windows PowerShell back-tick escape character (\`) to escape characters that are allowed in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] delimited identifiers but not Windows PowerShell path names.</span></span> <span data-ttu-id="3bb4c-104">Sin embargo, algunos caracteres no se pueden evitar.</span><span class="sxs-lookup"><span data-stu-id="3bb4c-104">Some characters, however, cannot be escaped.</span></span> <span data-ttu-id="3bb4c-105">Por ejemplo, no puede hacer que se eluda el carácter de dos puntos (:) en Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3bb4c-105">For example, you cannot escape the colon character (:) in Windows PowerShell.</span></span> <span data-ttu-id="3bb4c-106">Los identificadores con ese carácter deben codificarse.</span><span class="sxs-lookup"><span data-stu-id="3bb4c-106">Identifiers with that character must be encoded.</span></span> <span data-ttu-id="3bb4c-107">La codificación es más confiable que hacer que el carácter se eluda porque funciona para todos los caracteres.</span><span class="sxs-lookup"><span data-stu-id="3bb4c-107">Encoding is more reliable than escaping because encoding works for all characters.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="3bb4c-108">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="3bb4c-108">Before You Begin</span></span>  
 <span data-ttu-id="3bb4c-109">El carácter de acento invertido (\`) suele estar en la tecla de la parte superior izquierda del teclado, debajo de la tecla ESC.</span><span class="sxs-lookup"><span data-stu-id="3bb4c-109">The back-tick character (\`) is usually on the key in the upper left of the keyboard, under the ESC key.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="3bb4c-110">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3bb4c-110">Examples</span></span>  
 <span data-ttu-id="3bb4c-111">Este es un ejemplo en el que se hace que se eluda un carácter #:</span><span class="sxs-lookup"><span data-stu-id="3bb4c-111">This is an example of escaping a # character:</span></span>  
  
```  
cd SQLSERVER:\SQL\MyComputer\MyInstance\MyDatabase\MySchema\`#MyTempTable  
```  
  
 <span data-ttu-id="3bb4c-112">Este es un ejemplo en el que se hace que se eluda un paréntesis al especificar (local) como nombre de equipo:</span><span class="sxs-lookup"><span data-stu-id="3bb4c-112">This is an example of escaping the parenthesis when specifying (local) as a computer name:</span></span>  
  
```  
Set-Location SQLSERVER:\SQL\`(local`)\DEFAULT  
```  
  
## <a name="see-also"></a><span data-ttu-id="3bb4c-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3bb4c-113">See Also</span></span>  
 <span data-ttu-id="3bb4c-114">[SQL Server identificadores en PowerShell](sql-server-identifiers-in-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="3bb4c-114">[SQL Server Identifiers in PowerShell](sql-server-identifiers-in-powershell.md) </span></span>  
 <span data-ttu-id="3bb4c-115">[Proveedor de SQL Server PowerShell](sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="3bb4c-115">[SQL Server PowerShell Provider](sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="3bb4c-116">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="3bb4c-116">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
  
  
