---
title: Opciones (editor de texto-XML-Página formato) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 97373178-d288-4127-af37-d9f5fe1b8607
author: rothja
ms.author: jroth
ms.openlocfilehash: dce36142fe9974c0167fca700c509642e05d89b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746408"
---
# <a name="options-text-editor---xml---formatting-page"></a><span data-ttu-id="8810c-102">Opciones (Editor de texto - XML - Página Formato)</span><span class="sxs-lookup"><span data-stu-id="8810c-102">Options (Text Editor - XML - Formatting Page)</span></span>

<span data-ttu-id="8810c-103">Este cuadro de diálogo permite especificar la configuración de formato del Editor XML.</span><span class="sxs-lookup"><span data-stu-id="8810c-103">This dialog box allows you to specify the formatting settings for the XML Editor.</span></span> <span data-ttu-id="8810c-104">Puede tener acceso al cuadro de diálogo **Opciones** desde el menú **Herramientas**.</span><span class="sxs-lookup"><span data-stu-id="8810c-104">You can access the **Options** dialog box from the **Tools** menu.</span></span>  
  
> [!NOTE]  
> <span data-ttu-id="8810c-105">Esta configuración está disponible si selecciona la carpeta **Editor de texto**, la carpeta **XML** y, después, la opción **Formato** del cuadro de diálogo **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="8810c-105">These settings are available when you select the **Text Editor** folder, the **XML** folder, and then the **Formatting** option from the **Options** dialog box.</span></span>  
  
## <a name="attributes"></a><span data-ttu-id="8810c-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="8810c-106">Attributes</span></span>  
 <span data-ttu-id="8810c-107">**Preservar el formato manual de atributos**</span><span class="sxs-lookup"><span data-stu-id="8810c-107">**Preserve manual attribute formatting**</span></span>  
 <span data-ttu-id="8810c-108">No vuelve a dar formato a los atributos.</span><span class="sxs-lookup"><span data-stu-id="8810c-108">Do not reformat attributes.</span></span> <span data-ttu-id="8810c-109">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8810c-109">This is the default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8810c-110">Si los atributos se encuentran en varias líneas, el editor sangra cada línea de atributos para que coincida con el sangrado del elemento primario.</span><span class="sxs-lookup"><span data-stu-id="8810c-110">If the attributes are on multiple lines, the editor indents each line of attributes to match the indentation of the parent element.</span></span>  
  
 <span data-ttu-id="8810c-111">**Alinear los atributos en líneas separadas**</span><span class="sxs-lookup"><span data-stu-id="8810c-111">**Align attributes each on a separate line**</span></span>  
 <span data-ttu-id="8810c-112">Los atributos segundo y siguientes se alinean verticalmente para coincidir con el sangrado del primer atributo.</span><span class="sxs-lookup"><span data-stu-id="8810c-112">Align the second and subsequent attributes vertically to match the indentation of the first attribute.</span></span> <span data-ttu-id="8810c-113">El siguiente texto XML es un ejemplo de alineación de los atributos.</span><span class="sxs-lookup"><span data-stu-id="8810c-113">The following XML text is an example of how the attributes would be aligned.</span></span>  
  
```  
<item id = "123-A"  
      name = "hammer"  
      price = "9.95"  
</item>  
```  
  
## <a name="auto-reformat"></a><span data-ttu-id="8810c-114">Formatear automáticamente</span><span class="sxs-lookup"><span data-stu-id="8810c-114">Auto Reformat</span></span>  
 <span data-ttu-id="8810c-115">**Al pegar desde el portapapeles**</span><span class="sxs-lookup"><span data-stu-id="8810c-115">**On paste from clipboard.**</span></span>  
 <span data-ttu-id="8810c-116">Vuelve a dar formato al texto XML pegado desde el portapapeles.</span><span class="sxs-lookup"><span data-stu-id="8810c-116">Reformat XML text pasted from the clipboard.</span></span>  
  
 <span data-ttu-id="8810c-117">**Al terminar la etiqueta final**</span><span class="sxs-lookup"><span data-stu-id="8810c-117">**On completion of end tag**</span></span>  
 <span data-ttu-id="8810c-118">Vuelve a dar formato al elemento cuando se completa la etiqueta final.</span><span class="sxs-lookup"><span data-stu-id="8810c-118">Reformat the element when the end tag is completed.</span></span>  
  
## <a name="mixed-content"></a><span data-ttu-id="8810c-119">Contenido mixto</span><span class="sxs-lookup"><span data-stu-id="8810c-119">Mixed Content</span></span>  
 <span data-ttu-id="8810c-120">**Formatear contenido mixto de forma predeterminada**</span><span class="sxs-lookup"><span data-stu-id="8810c-120">**Format mixed content by default.**</span></span>  
 <span data-ttu-id="8810c-121">Intenta volver a dar formato al contenido mixto, excepto si se encuentra en un ámbito `xml:space="preserve"`.</span><span class="sxs-lookup"><span data-stu-id="8810c-121">Attempt to reformat mixed content, except when the content is found in an `xml:space="preserve"` scope.</span></span> <span data-ttu-id="8810c-122">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8810c-122">This is the default.</span></span>  
  
 <span data-ttu-id="8810c-123">Si un elemento contiene una mezcla de texto y marcado, el contenido se considera mixto.</span><span class="sxs-lookup"><span data-stu-id="8810c-123">If an element contains a mix of text and markup, the contents are considered to be mixed content.</span></span> <span data-ttu-id="8810c-124">A continuación se incluye un ejemplo de un elemento con contenido mixto.</span><span class="sxs-lookup"><span data-stu-id="8810c-124">Following is an example of an element with mixed content.</span></span>  
  
```  
<dir>c:\data\AlphaProject\  
  <file readOnly="false">test1.txt</file>  
  <file readOnly="false">test2.txt</file>  
```  
  
 \</dir>  
  
## <a name="see-also"></a><span data-ttu-id="8810c-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8810c-125">See Also</span></span>  
 [<span data-ttu-id="8810c-126">Editor XML &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="8810c-126">XML Editor &#40;SQL Server Management Studio&#41;</span></span>](../ssms/sql-server-management-studio-ssms.md)  
