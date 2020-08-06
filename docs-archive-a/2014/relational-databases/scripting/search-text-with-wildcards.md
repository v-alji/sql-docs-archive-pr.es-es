---
title: Buscar texto con caracteres comodín
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- vswildcardsbuilder
helpviewer_keywords:
- searches [SQL Server Management Studio], wildcards
- Query Editor [SQL Server Management Studio], wildcard searches
- wildcard options [SQL Server Management Studio]
ms.assetid: 449600f8-cc87-4b3f-878a-59c158a88a40
author: rothja
ms.author: jroth
ms.openlocfilehash: cc4e24c3dce73e46350b0c106429c42ab5f0edb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677515"
---
# <a name="search-text-with-wildcards"></a><span data-ttu-id="96267-102">Buscar texto con caracteres comodín</span><span class="sxs-lookup"><span data-stu-id="96267-102">Search Text with Wildcards</span></span>
  <span data-ttu-id="96267-103">Las expresiones siguientes pueden reemplazar a caracteres o dígitos en el campo **Buscar** del cuadro de diálogo [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] **Buscar y reemplazar**.</span><span class="sxs-lookup"><span data-stu-id="96267-103">The following expressions can replace characters or digits in the **Find what** field of the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] **Find and Replace** dialog box.</span></span>  
  
#### <a name="to-search-using-wildcards"></a><span data-ttu-id="96267-104">Para buscar mediante caracteres comodín</span><span class="sxs-lookup"><span data-stu-id="96267-104">To search using wildcards</span></span>  
  
1.  <span data-ttu-id="96267-105">Para habilitar el uso de caracteres comodín en el campo **Buscar** en operaciones de **Búsqueda rápida**, **Buscar en archivos**, **Reemplazo rápido** o **Reemplazar en archivos** , active la opción **Usar** de **Opciones de búsqueda**y, a continuación, elija Caracteres comodín.</span><span class="sxs-lookup"><span data-stu-id="96267-105">To enable the use of wildcards in the **Find what** field during Quick Find, **Find in Files**, **Quick Replace**, or **Replace in Files** operations, select the **Use** option under **Find Options** and then choose **Wildcards**.</span></span>  
  
2.  <span data-ttu-id="96267-106">El botón triangular de la **Lista de referencia** situado junto al campo **Buscar** se activa.</span><span class="sxs-lookup"><span data-stu-id="96267-106">The triangular **Reference List** button next to the **Find what** field then becomes available.</span></span> <span data-ttu-id="96267-107">Haga clic en este botón para obtener una lista de los caracteres comodín disponibles.</span><span class="sxs-lookup"><span data-stu-id="96267-107">Click this button to display a list of the available wildcards.</span></span> <span data-ttu-id="96267-108">Al elegir alguno de los elementos del **Generador de expresiones**, éste se inserta en la cadena **Buscar** .</span><span class="sxs-lookup"><span data-stu-id="96267-108">When you choose any item from the **Reference List**, it is inserted into the **Find what** string.</span></span>  
  
 <span data-ttu-id="96267-109">En la tabla siguiente se describen los caracteres comodín disponibles en la **Lista de referencias**.</span><span class="sxs-lookup"><span data-stu-id="96267-109">The following table describes the wildcards available in the **Reference List**.</span></span>  
  
|<span data-ttu-id="96267-110">Expression</span><span class="sxs-lookup"><span data-stu-id="96267-110">Expression</span></span>|<span data-ttu-id="96267-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="96267-111">Syntax</span></span>|<span data-ttu-id="96267-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="96267-112">Description</span></span>|  
|----------------|------------|-----------------|  
|<span data-ttu-id="96267-113">Un carácter cualquiera</span><span class="sxs-lookup"><span data-stu-id="96267-113">Any single character</span></span>|<span data-ttu-id="96267-114">?</span><span class="sxs-lookup"><span data-stu-id="96267-114">?</span></span>|<span data-ttu-id="96267-115">Coincidencia con cualquier carácter individual.</span><span class="sxs-lookup"><span data-stu-id="96267-115">Matches any single character.</span></span>|  
|<span data-ttu-id="96267-116">Un dígito cualquiera</span><span class="sxs-lookup"><span data-stu-id="96267-116">Any single digit</span></span>|#|<span data-ttu-id="96267-117">Coincidencia con cualquier dígito individual.</span><span class="sxs-lookup"><span data-stu-id="96267-117">Matches any single digit.</span></span> <span data-ttu-id="96267-118">Por ejemplo, 7# devuelve números que incluyen un 7 seguido de otro número, como 71, pero no 17.</span><span class="sxs-lookup"><span data-stu-id="96267-118">For example, 7# matches numbers that include 7 followed by another number, such as 71, but not 17.</span></span>|  
|<span data-ttu-id="96267-119">Un carácter cualquiera no perteneciente al conjunto</span><span class="sxs-lookup"><span data-stu-id="96267-119">Characters not in set</span></span>|<span data-ttu-id="96267-120">[!</span><span class="sxs-lookup"><span data-stu-id="96267-120">[!</span></span> <span data-ttu-id="96267-121">]</span><span class="sxs-lookup"><span data-stu-id="96267-121">]</span></span>|<span data-ttu-id="96267-122">Coincidencia con cualquier carácter que no se haya especificado en el juego de caracteres.</span><span class="sxs-lookup"><span data-stu-id="96267-122">Matches any one character that is not specified in the set.</span></span>|  
|<span data-ttu-id="96267-123">Cero o más caracteres cualesquiera</span><span class="sxs-lookup"><span data-stu-id="96267-123">One or more characters</span></span>|*|<span data-ttu-id="96267-124">Coincidencia con uno o más caracteres.</span><span class="sxs-lookup"><span data-stu-id="96267-124">Matches any one or more characters.</span></span> <span data-ttu-id="96267-125">Por ejemplo, new\* devuelve cualquier texto que incluya "new", como newfile.txt.</span><span class="sxs-lookup"><span data-stu-id="96267-125">For example, new\* matches any text that includes "new", such as newfile.txt.</span></span>|  
|<span data-ttu-id="96267-126">Un carácter cualquiera del conjunto</span><span class="sxs-lookup"><span data-stu-id="96267-126">Set of characters</span></span>|<span data-ttu-id="96267-127">[ ]</span><span class="sxs-lookup"><span data-stu-id="96267-127">[ ]</span></span>|<span data-ttu-id="96267-128">Coincidencia con cualquier carácter especificado en el juego de caracteres.</span><span class="sxs-lookup"><span data-stu-id="96267-128">Matches any one of the characters specified in the set.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="96267-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="96267-129">See Also</span></span>  
 <span data-ttu-id="96267-130">[Buscar y reemplazar](search-and-replace.md) </span><span class="sxs-lookup"><span data-stu-id="96267-130">[Search and Replace](search-and-replace.md) </span></span>  
 [<span data-ttu-id="96267-131">Buscar texto mediante expresiones regulares</span><span class="sxs-lookup"><span data-stu-id="96267-131">Search Text with Regular Expressions</span></span>](search-text-with-regular-expressions.md)  
