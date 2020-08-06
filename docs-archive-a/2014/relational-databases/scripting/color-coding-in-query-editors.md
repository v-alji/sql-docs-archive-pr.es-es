---
title: Codificación de colores en el Editor de consultas
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Query Editor [SQL Server Management Studio], color coding
- color coding [Query Editor]
ms.assetid: 802882dc-c997-4e3f-8a01-994bb43169ae
author: rothja
ms.author: jroth
ms.openlocfilehash: f23b37cec051b52082cdb310a134a4603423b8c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671443"
---
# <a name="color-coding-in-query-editors"></a><span data-ttu-id="a1bd7-102">Codificación de colores en el Editor de consultas</span><span class="sxs-lookup"><span data-stu-id="a1bd7-102">Color Coding in Query Editors</span></span>
  <span data-ttu-id="a1bd7-103">El texto especificado en los editores de código se asigna a una categoría; cada categoría está identificada por un color.</span><span class="sxs-lookup"><span data-stu-id="a1bd7-103">The text entered in the code editors is assigned a category; each category is identified by a color.</span></span> <span data-ttu-id="a1bd7-104">Los colores ayudan a encontrar texto rápidamente en el código.</span><span class="sxs-lookup"><span data-stu-id="a1bd7-104">The colors help you quickly find text in your code.</span></span> <span data-ttu-id="a1bd7-105">Por ejemplo, los comentarios se resaltan en verde oscuro.</span><span class="sxs-lookup"><span data-stu-id="a1bd7-105">For example, comments stand out in dark green.</span></span> <span data-ttu-id="a1bd7-106">En la tabla siguiente se muestran los colores más comunes.</span><span class="sxs-lookup"><span data-stu-id="a1bd7-106">The following table lists the most common colors.</span></span> <span data-ttu-id="a1bd7-107">Puede ver la lista completa de colores y sus categorías, así como configurar una combinación de colores personalizada, usando el menú **Herramientas**, **Opciones** .</span><span class="sxs-lookup"><span data-stu-id="a1bd7-107">You can view the whole list of colors and their categories, and configure a custom color scheme by using the **Tools**, **Options** menu.</span></span> <span data-ttu-id="a1bd7-108">Para obtener más información sobre cómo cambiar los colores predeterminados, vea [Change Font Color, Size, and Style](change-font-color-size-and-style.md).</span><span class="sxs-lookup"><span data-stu-id="a1bd7-108">For more information about how to change the default colors, see [Change Font Color, Size, and Style](change-font-color-size-and-style.md).</span></span>  
  
## <a name="default-code-colors"></a><span data-ttu-id="a1bd7-109">Colores predeterminados para el código</span><span class="sxs-lookup"><span data-stu-id="a1bd7-109">Default Code Colors</span></span>  
  
|<span data-ttu-id="a1bd7-110">Color</span><span class="sxs-lookup"><span data-stu-id="a1bd7-110">Color</span></span>|<span data-ttu-id="a1bd7-111">Category</span><span class="sxs-lookup"><span data-stu-id="a1bd7-111">Category</span></span>|  
|-----------|--------------|  
|<span data-ttu-id="a1bd7-112">Rojo</span><span class="sxs-lookup"><span data-stu-id="a1bd7-112">Red</span></span>|<span data-ttu-id="a1bd7-113">Cadena de SQL</span><span class="sxs-lookup"><span data-stu-id="a1bd7-113">SQL string</span></span>|  
|<span data-ttu-id="a1bd7-114">Verde oscuro</span><span class="sxs-lookup"><span data-stu-id="a1bd7-114">Dark green</span></span>|<span data-ttu-id="a1bd7-115">Comentario</span><span class="sxs-lookup"><span data-stu-id="a1bd7-115">Comment</span></span>|  
|<span data-ttu-id="a1bd7-116">Negro sobre fondo plateado</span><span class="sxs-lookup"><span data-stu-id="a1bd7-116">Black on silver background</span></span>|<span data-ttu-id="a1bd7-117">Comando SQLCMD</span><span class="sxs-lookup"><span data-stu-id="a1bd7-117">SQLCMD command</span></span>|  
|<span data-ttu-id="a1bd7-118">Fucsia</span><span class="sxs-lookup"><span data-stu-id="a1bd7-118">Magenta</span></span>|<span data-ttu-id="a1bd7-119">Función del sistema</span><span class="sxs-lookup"><span data-stu-id="a1bd7-119">System function</span></span>|  
|<span data-ttu-id="a1bd7-120">Verde</span><span class="sxs-lookup"><span data-stu-id="a1bd7-120">Green</span></span>|<span data-ttu-id="a1bd7-121">Tabla, vista o función con valores de tabla del sistema.</span><span class="sxs-lookup"><span data-stu-id="a1bd7-121">System table, view, or table-valued function.</span></span> <span data-ttu-id="a1bd7-122">También, los esquemas del sistema sys e INFORMATION_SCHEMA.</span><span class="sxs-lookup"><span data-stu-id="a1bd7-122">Also, the system schemas sys and INFORMATION_SCHEMA.</span></span>|  
|<span data-ttu-id="a1bd7-123">Azul</span><span class="sxs-lookup"><span data-stu-id="a1bd7-123">Blue</span></span>|<span data-ttu-id="a1bd7-124">Palabra clave</span><span class="sxs-lookup"><span data-stu-id="a1bd7-124">Keyword</span></span>|  
|<span data-ttu-id="a1bd7-125">Verde azulado</span><span class="sxs-lookup"><span data-stu-id="a1bd7-125">Teal</span></span>|<span data-ttu-id="a1bd7-126">Números de línea o parámetro de plantilla</span><span class="sxs-lookup"><span data-stu-id="a1bd7-126">Line numbers or template parameter</span></span>|  
|<span data-ttu-id="a1bd7-127">Rojo oscuro</span><span class="sxs-lookup"><span data-stu-id="a1bd7-127">Maroon</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a1bd7-128">procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="a1bd7-128">stored procedure</span></span>|  
|<span data-ttu-id="a1bd7-129">Gris oscuro</span><span class="sxs-lookup"><span data-stu-id="a1bd7-129">Dark gray</span></span>|<span data-ttu-id="a1bd7-130">Operadores</span><span class="sxs-lookup"><span data-stu-id="a1bd7-130">Operators</span></span>|  
  
## <a name="status-bar"></a><span data-ttu-id="a1bd7-131">Barra de estado</span><span class="sxs-lookup"><span data-stu-id="a1bd7-131">Status Bar</span></span>  
 <span data-ttu-id="a1bd7-132">Puede configurar que servidores registrados o servidores de [!INCLUDE[ssDE](../../includes/ssde-md.md)] en el Explorador de objetos tengan distintos colores en la barra de estado del editor de consultas de [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a1bd7-132">You can configure registered servers or [!INCLUDE[ssDE](../../includes/ssde-md.md)] servers in Object Explorer to have different colors in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor status bar.</span></span> <span data-ttu-id="a1bd7-133">Esto ayuda a identificar a qué servidor está conectada cada ventana del editor cuando se tienen muchas ventanas abiertas al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="a1bd7-133">This helps you identify which server each editor window is connected to when you have many windows open at the same time.</span></span> <span data-ttu-id="a1bd7-134">Para obtener más información sobre cómo establecer colores de la barra de estado, vea [Barra de estado &#40;Editor de consultas del motor de base de datos&#41;](status-bar-database-engine-query-editor.md).</span><span class="sxs-lookup"><span data-stu-id="a1bd7-134">For more information about setting status bar colors, see [Status Bar &#40;Database Engine Query Editor&#41;](status-bar-database-engine-query-editor.md).</span></span>  
  
 <span data-ttu-id="a1bd7-135">Algunos tipos de editores no muestran la barra de estado o no admiten varios colores.</span><span class="sxs-lookup"><span data-stu-id="a1bd7-135">Some types of editors do not display the status bar, or do not support multiple colors.</span></span>  
  
  
