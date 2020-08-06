---
title: Información de parámetros (IntelliSense)
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Parameter Info option [IntelliSense]
- stored function parameter completion [Intellisense]
- language references [SQL Server]
- IntelliSense [SQL Server], Parameter Info option
ms.assetid: 56c2aac9-c65c-4679-b62c-d9f689876dde
author: rothja
ms.author: jroth
ms.openlocfilehash: b7e5e7496753006808f75378182db0d3cb606d4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676453"
---
# <a name="parameter-info-intellisense"></a><span data-ttu-id="86ba2-102">Información de parámetros (IntelliSense)</span><span class="sxs-lookup"><span data-stu-id="86ba2-102">Parameter Info (IntelliSense)</span></span>
  <span data-ttu-id="86ba2-103">La opción [!INCLUDE[msCoName](../../includes/msconame-md.md)] Información de parámetros **de** IntelliSense abre una lista de parámetros que proporciona información sobre el número, los nombres y los tipos de parámetros necesarios para una función o un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="86ba2-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] IntelliSense **Parameter Info** option opens a parameters list that provides information about the number, names, and types of the parameters that are required by a function or stored procedure.</span></span> <span data-ttu-id="86ba2-104">El parámetro en negrita indica el siguiente parámetro que se necesita al escribir una función o un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="86ba2-104">The parameter in bold indicates the next parameter that is required as you type a function or stored procedure.</span></span>  
  
 <span data-ttu-id="86ba2-105">La lista de parámetros también aparece para las funciones anidadas.</span><span class="sxs-lookup"><span data-stu-id="86ba2-105">The parameter list is also displayed for nested functions.</span></span> <span data-ttu-id="86ba2-106">Si se escribe una función como parámetro de otra función, la lista de parámetros muestra los parámetros de la función interna.</span><span class="sxs-lookup"><span data-stu-id="86ba2-106">If you type a function as a parameter to another function, the parameter list displays the parameters for the inner function.</span></span> <span data-ttu-id="86ba2-107">Así, cuando la lista de parámetros de la función interna está completa, pasa a mostrar los parámetros de la función externa.</span><span class="sxs-lookup"><span data-stu-id="86ba2-107">Then, when the inner function parameter list is complete, the parameter list reverts to displaying the outer function parameters.</span></span>  
  
#### <a name="to-view-parameter-info-for-functions-or-stored-procedures"></a><span data-ttu-id="86ba2-108">Para ver la información de parámetros de funciones o procedimientos almacenados del sistema</span><span class="sxs-lookup"><span data-stu-id="86ba2-108">To view Parameter Info for functions or stored procedures</span></span>  
  
1.  <span data-ttu-id="86ba2-109">Tras el nombre de una función, escriba un paréntesis de apertura como haría para abrir la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="86ba2-109">After the name of a function, type an open parenthesis as you usually type to open the parameters list.</span></span> <span data-ttu-id="86ba2-110">Después de escribir el nombre de un procedimiento almacenado, escriba un espacio como haría para obtener información sobre los parámetros del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="86ba2-110">After you type the name of a stored procedure, type a space as you usually type to obtain information about the procedure parameters.</span></span>  
  
     <span data-ttu-id="86ba2-111">IntelliSense muestra la declaración completa de la función o los parámetros del procedimiento almacenado en una ventana emergente situada bajo el punto de inserción.</span><span class="sxs-lookup"><span data-stu-id="86ba2-111">IntelliSense displays the complete declaration for the function or the parameters for a stored procedure in a pop-up window just under the insertion point.</span></span> <span data-ttu-id="86ba2-112">El primer parámetro de la lista aparece en negrita.</span><span class="sxs-lookup"><span data-stu-id="86ba2-112">The first parameter in the list appears in bold.</span></span>  
  
2.  <span data-ttu-id="86ba2-113">A medida que escribe los parámetros, el formato en negrita cambia para reflejar el siguiente parámetro que hay que especificar.</span><span class="sxs-lookup"><span data-stu-id="86ba2-113">As you type the parameters, the bold font changes to reflect the next parameter that you need to enter.</span></span>  
  
3.  <span data-ttu-id="86ba2-114">Presione ESC en cualquier momento para cerrar la lista o siga escribiendo hasta que haya completado la función.</span><span class="sxs-lookup"><span data-stu-id="86ba2-114">Press ESC at any time to close the list, or continue typing until you have completed the function.</span></span>  
  
     <span data-ttu-id="86ba2-115">En una función, al escribir el paréntesis de cierre se cierra también la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="86ba2-115">For a function, if you type the closing parenthesis you also close the parameter list.</span></span>  
  
#### <a name="to-manually-start-parameter-info"></a><span data-ttu-id="86ba2-116">Para iniciar manualmente Información de parámetros</span><span class="sxs-lookup"><span data-stu-id="86ba2-116">To manually start Parameter Info</span></span>  
  
1.  <span data-ttu-id="86ba2-117">En el menú **Edición** , seleccione **IntelliSense** y, a continuación, seleccione **Información de parámetros**.</span><span class="sxs-lookup"><span data-stu-id="86ba2-117">On the **Edit** menu, select **IntelliSense** and then select **Parameter Info**.</span></span>  
  
2.  <span data-ttu-id="86ba2-118">Presione las teclas del método abreviado CTRL+MAYÚS+ESPACIO.</span><span class="sxs-lookup"><span data-stu-id="86ba2-118">Press the CTRL+SHIFT+SPACE keyboard shortcut.</span></span>  
  
 <span data-ttu-id="86ba2-119">Para obtener más información, vea [Configurar IntelliSense &#40;SQL Server Management Studio&#41;](configure-intellisense-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="86ba2-119">For more information, see [Configure IntelliSense &#40;SQL Server Management Studio&#41;](configure-intellisense-sql-server-management-studio.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="86ba2-120">La opción **Información de parámetros** solo está disponible para el Editor de consultas de [!INCLUDE[ssDE](../../includes/ssde-md.md)] y el Editor de consultas XML.</span><span class="sxs-lookup"><span data-stu-id="86ba2-120">The **Parameter Info** option is available only for the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor and the XML Query Editor.</span></span>  
  
  
