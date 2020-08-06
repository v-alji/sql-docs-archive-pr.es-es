---
title: Intercalación (cuadro de diálogo, Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.definecolumncollation
- vdtsql.chm:65561
ms.assetid: e4020f79-7abf-4839-b9b2-984ef7049817
author: stevestein
ms.author: sstein
ms.openlocfilehash: d551b2ae7ca27250c144afedf13038efd78ad6ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677985"
---
# <a name="collation-dialog-box-visual-database-tools"></a><span data-ttu-id="8b07e-102">Intercalación (cuadro de diálogo, Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="8b07e-102">Collation Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="8b07e-103">Este cuadro de diálogo permite especificar una secuencia de intercalación para la columna.</span><span class="sxs-lookup"><span data-stu-id="8b07e-103">This dialog box lets you specify a collation sequence for the column.</span></span> <span data-ttu-id="8b07e-104">La secuencia de intercalación de una columna se utiliza en cualquier operación que compare los valores de la columna con otra columna o con valores constantes.</span><span class="sxs-lookup"><span data-stu-id="8b07e-104">A column's collation sequence is used in any operation that compares values of the column to another column or to constant values.</span></span> <span data-ttu-id="8b07e-105">También afecta al comportamiento de algunas funciones de cadena, como SUBSTRING y CHARINDEX.</span><span class="sxs-lookup"><span data-stu-id="8b07e-105">It also affects the behavior of some string functions, such as SUBSTRING and CHARINDEX.</span></span> <span data-ttu-id="8b07e-106">Para obtener una lista completa de los efectos del valor de intercalación de una columna, vea la documentación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8b07e-106">For a complete list of the effects of a column's collation setting, see the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] documentation.</span></span>  
  
 <span data-ttu-id="8b07e-107">Este cuadro de diálogo aparece en las situaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="8b07e-107">This dialog box appears:</span></span>  
  
-   <span data-ttu-id="8b07e-108">Si se escribe un nombre del intercalación no válido en el campo **Intercalación** de la pestaña **Propiedades de columna** .</span><span class="sxs-lookup"><span data-stu-id="8b07e-108">If you enter an invalid collation name in the **Collation** field on the **Column Properties** tab.</span></span>  
  
-   <span data-ttu-id="8b07e-109">Si hace clic en el campo **Intercalación** de la pestaña **Propiedades de columna** y, luego, hace clic en el botón de puntos suspensivos ( **...** ) que aparece a la derecha del campo.</span><span class="sxs-lookup"><span data-stu-id="8b07e-109">If you click in the **Collation** field on the **Column Properties** tab, and then click the ellipsis button (**...**) to the right of the field.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8b07e-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="8b07e-110">Options</span></span>  
 <span data-ttu-id="8b07e-111">**Intercalación de SQL**</span><span class="sxs-lookup"><span data-stu-id="8b07e-111">**SQL Collation**</span></span>  
 <span data-ttu-id="8b07e-112">Elija una de las secuencias de intercalación que define [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="8b07e-112">Choose among the collation sequences defined by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the drop-down list.</span></span>  
  
 <span data-ttu-id="8b07e-113">**Intercalación de Windows**</span><span class="sxs-lookup"><span data-stu-id="8b07e-113">**Windows Collation**</span></span>  
 <span data-ttu-id="8b07e-114">Elija una de las secuencias de intercalación que define Windows en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="8b07e-114">Choose among the collation sequences defined by Windows from the drop-down list.</span></span>  
  
 <span data-ttu-id="8b07e-115">**Orden binario**</span><span class="sxs-lookup"><span data-stu-id="8b07e-115">**Binary Sort**</span></span>  
 <span data-ttu-id="8b07e-116">Utilice los códigos binarios de valores de caracteres para la comparación.</span><span class="sxs-lookup"><span data-stu-id="8b07e-116">Use the binary codes of character values for comparisons.</span></span> <span data-ttu-id="8b07e-117">Si activa esta opción, no estarán disponibles determinadas opciones de comparación alfabética.</span><span class="sxs-lookup"><span data-stu-id="8b07e-117">If you select this option, certain alphabetic comparison options become unavailable.</span></span> <span data-ttu-id="8b07e-118">Por ejemplo, la posibilidad de distinguir entre mayúsculas y minúsculas no estará disponible, puesto que las letras mayúsculas y las minúsculas tienen codificaciones binarias diferentes.</span><span class="sxs-lookup"><span data-stu-id="8b07e-118">For example, case-insensitive comparisons become unavailable because uppercase letters and lowercase letters have different binary encodings.</span></span> <span data-ttu-id="8b07e-119">Solo se aplica si se selecciona **Intercalación de Windows**.</span><span class="sxs-lookup"><span data-stu-id="8b07e-119">Applies only if you select **Windows collation**.</span></span>  
  
 <span data-ttu-id="8b07e-120">**Orden del diccionario**</span><span class="sxs-lookup"><span data-stu-id="8b07e-120">**Dictionary Sort**</span></span>  
 <span data-ttu-id="8b07e-121">Utilice las opciones de comparación alfabética.</span><span class="sxs-lookup"><span data-stu-id="8b07e-121">Use alphabetic comparison options.</span></span> <span data-ttu-id="8b07e-122">Solo se aplica si se selecciona **Intercalación de Windows**.</span><span class="sxs-lookup"><span data-stu-id="8b07e-122">Applies only if you select **Windows collation**.</span></span> <span data-ttu-id="8b07e-123">Las opciones de comparación alfabética son:</span><span class="sxs-lookup"><span data-stu-id="8b07e-123">The alphabetic comparisons options are:</span></span>  
  
-   <span data-ttu-id="8b07e-124">**Distinguir mayúsculas de minúsculas** Seleccione esta opción si desea distinguir las letras mayúsculas de las minúsculas en las comparaciones.</span><span class="sxs-lookup"><span data-stu-id="8b07e-124">**Case Sensitive** Select this if you want comparisons to consider uppercase and lowercase letters to be unequal.</span></span>  
  
-   <span data-ttu-id="8b07e-125">**Distinguir acentos** Seleccione esta opción si desea distinguir entre letras acentuadas y no acentuadas en las comparaciones.</span><span class="sxs-lookup"><span data-stu-id="8b07e-125">**Accent Sensitive** Select this if you want comparisons to consider accented and unaccented letters to be unequal.</span></span> <span data-ttu-id="8b07e-126">Si selecciona esta opción, también se distinguirán letras con distintos tipos de acento en las comparaciones.</span><span class="sxs-lookup"><span data-stu-id="8b07e-126">If you select this, comparisons will also consider differently accented letters to be unequal.</span></span>  
  
-   <span data-ttu-id="8b07e-127">**Distinguir Kana** Seleccione esta opción si desea distinguir entre las sílabas japonesas katakana e hiragana en las comparaciones.</span><span class="sxs-lookup"><span data-stu-id="8b07e-127">**Kana Sensitive** Select this if you want comparisons to consider katakana and hiragana Japanese syllables to be unequal.</span></span>  
  
-   <span data-ttu-id="8b07e-128">**Distinguir ancho** Seleccione esta opción si desea distinguir entre caracteres de ancho medio y completo en las comparaciones.</span><span class="sxs-lookup"><span data-stu-id="8b07e-128">**Width Sensitive** Select this if you want comparisons to consider half-width and full-width characters to be unequal.</span></span>  
  
 <span data-ttu-id="8b07e-129">**Restaurar valores predeterminados (Botón)**</span><span class="sxs-lookup"><span data-stu-id="8b07e-129">**Restore Default Button**</span></span>  
 <span data-ttu-id="8b07e-130">Aplica a la columna la secuencia de intercalación predeterminada para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="8b07e-130">Apply the default collation sequence for the database to the column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b07e-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8b07e-131">See Also</span></span>  
 [<span data-ttu-id="8b07e-132">Trabajar con columnas en consultas de funciones agregadas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="8b07e-132">Work with Columns in Aggregate Queries &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
