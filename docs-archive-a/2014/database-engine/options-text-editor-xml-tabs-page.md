---
title: 'Opciones (editor de texto: XML: Página tabulaciones) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.XML.Tabs
ms.assetid: 13bf5f8c-aba3-4c05-b8bb-eb475797c9bd
author: rothja
ms.author: jroth
ms.openlocfilehash: 3047d6c05ffb88d07a4bf2e5b1d4143412046c04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743618"
---
# <a name="options-text-editorxmltabs-page"></a><span data-ttu-id="ea727-102">Opciones (Editor de texto: XML: página Pestañas)</span><span class="sxs-lookup"><span data-stu-id="ea727-102">Options (Text Editor:XML:Tabs Page)</span></span>
  <span data-ttu-id="ea727-103">Este cuadro de diálogo permite cambiar el comportamiento del tabulador del Editor XML, que se usa para editar documentos XML.</span><span class="sxs-lookup"><span data-stu-id="ea727-103">This dialog box lets you change the tabbing behavior of the XML Editor, which is used to edit XML documents.</span></span> <span data-ttu-id="ea727-104">Para mostrar estas opciones de configuración, haga clic en **Opciones** en el menú **Herramientas** , expanda la carpeta **Editor de texto** , expanda la subcarpeta **XML** y, a continuación, haga clic en **Tabulaciones**.</span><span class="sxs-lookup"><span data-stu-id="ea727-104">To display these settings, click **Options** on the **Tools** menu, expand the **Text Editor** folder, expand the **XML** subfolder and then click **Tabs**.</span></span>  
  
## <a name="setting-options-in-multiple-locations"></a><span data-ttu-id="ea727-105">Establecer opciones en varias ubicaciones</span><span class="sxs-lookup"><span data-stu-id="ea727-105">Setting Options in Multiple Locations</span></span>  
 <span data-ttu-id="ea727-106">Las opciones del Editor XML también se pueden establecer en el cuadro de diálogo **Todos los idiomas** de la página General.</span><span class="sxs-lookup"><span data-stu-id="ea727-106">Options for the XML Editor can also be set in the **All Languages General** dialog.</span></span> <span data-ttu-id="ea727-107">Si usa los cuadros de diálogo **todos los lenguajes** para establecer diferentes opciones para los demás [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] editores, como los editores de DMX o MDX, debe restablecer las opciones del editor XML mediante este cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ea727-107">If you use the **All Languages** dialogs to set different options for the other [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] editors, such as the DMX or MDX editors, you must reset the XML Editor options using this dialog.</span></span>  
  
## <a name="indenting"></a><span data-ttu-id="ea727-108">Sangrías</span><span class="sxs-lookup"><span data-stu-id="ea727-108">Indenting</span></span>  
 <span data-ttu-id="ea727-109">**None**</span><span class="sxs-lookup"><span data-stu-id="ea727-109">**None**</span></span>  
 <span data-ttu-id="ea727-110">Cuando se selecciona esta opción, no se aplica ninguna sangría a la nueva línea que se crea al presionar ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="ea727-110">When this option is selected, the new line created when you press ENTER is not indented.</span></span> <span data-ttu-id="ea727-111">El cursor se coloca en la primera columna de la nueva línea.</span><span class="sxs-lookup"><span data-stu-id="ea727-111">The cursor is placed at the first column of the new line.</span></span>  
  
 <span data-ttu-id="ea727-112">**Bloquear**</span><span class="sxs-lookup"><span data-stu-id="ea727-112">**Block**</span></span>  
 <span data-ttu-id="ea727-113">Cuando se selecciona esta opción, se aplica una sangría de forma automática a la nueva línea que se crea al presionar ENTRAR, a la misma distancia que la línea anterior.</span><span class="sxs-lookup"><span data-stu-id="ea727-113">When this option is selected, the new line created when you press ENTER is automatically indented the same distance as the previous line.</span></span>  
  
 <span data-ttu-id="ea727-114">**Automática**</span><span class="sxs-lookup"><span data-stu-id="ea727-114">**Smart**</span></span>  
 <span data-ttu-id="ea727-115">Cuando se selecciona esta opción, la nueva línea que se crea al presionar ENTRAR se coloca conforme al contexto.</span><span class="sxs-lookup"><span data-stu-id="ea727-115">When this option is selected, the new line created when you press ENTER is positioned according to the context.</span></span> <span data-ttu-id="ea727-116">Por ejemplo, después de una llave de apertura ({), se aplicará automáticamente una sangría con una tabulación adicional a las líneas incluidas.</span><span class="sxs-lookup"><span data-stu-id="ea727-116">For example, after an opening brace ({), the included lines are automatically indented an extra tab stop.</span></span> <span data-ttu-id="ea727-117">La llave de cierre (}) se volverá a alinear con la llave de apertura correspondiente.</span><span class="sxs-lookup"><span data-stu-id="ea727-117">The matching closing brace (}) is realigned with its opening brace.</span></span>  
  
## <a name="tabs"></a><span data-ttu-id="ea727-118">Pestañas</span><span class="sxs-lookup"><span data-stu-id="ea727-118">Tabs</span></span>  
 <span data-ttu-id="ea727-119">**Tamaño de tabulación**</span><span class="sxs-lookup"><span data-stu-id="ea727-119">**Tab size**</span></span>  
 <span data-ttu-id="ea727-120">Establece la distancia en espacios entre las tabulaciones.</span><span class="sxs-lookup"><span data-stu-id="ea727-120">Sets the distance in spaces between tab stops.</span></span> <span data-ttu-id="ea727-121">El valor predeterminado es cuatro espacios.</span><span class="sxs-lookup"><span data-stu-id="ea727-121">The default is four spaces.</span></span>  
  
 <span data-ttu-id="ea727-122">**Tamaño de sangría**</span><span class="sxs-lookup"><span data-stu-id="ea727-122">**Indent size**</span></span>  
 <span data-ttu-id="ea727-123">Establece el tamaño en espacios de una sangría automática.</span><span class="sxs-lookup"><span data-stu-id="ea727-123">Sets the size in spaces of an automatic indentation.</span></span> <span data-ttu-id="ea727-124">El valor predeterminado es cuatro espacios.</span><span class="sxs-lookup"><span data-stu-id="ea727-124">The default is four spaces.</span></span> <span data-ttu-id="ea727-125">Se insertan caracteres de tabulación, de espacio o ambos para rellenar el tamaño especificado.</span><span class="sxs-lookup"><span data-stu-id="ea727-125">Tab characters, space characters, or both are inserted to fill the specified size.</span></span>  
  
 <span data-ttu-id="ea727-126">**Insertar espacios**</span><span class="sxs-lookup"><span data-stu-id="ea727-126">**Insert spaces**</span></span>  
 <span data-ttu-id="ea727-127">Cuando se selecciona esta opción, las operaciones de aplicación de sangrías solo insertan caracteres de espacio, pero no caracteres de tabulación.</span><span class="sxs-lookup"><span data-stu-id="ea727-127">When this option is selected, indent operations insert only space characters, not tab characters.</span></span> <span data-ttu-id="ea727-128">Si **tamaño de sangría** se establece en 5, por ejemplo, se insertarán cinco caracteres de espacio cada vez que se presione la tecla TAB o se haga clic en el botón **aumentar sangría** en la barra de herramientas de la [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] ventana principal.</span><span class="sxs-lookup"><span data-stu-id="ea727-128">If **Indent size** is set to 5, for example, then five space characters are inserted whenever you press the TAB key or click the **Increase Indent** button on the toolbar in the main [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] window.</span></span>  
  
 <span data-ttu-id="ea727-129">**Mantener tabulaciones**</span><span class="sxs-lookup"><span data-stu-id="ea727-129">**Keep tabs**</span></span>  
 <span data-ttu-id="ea727-130">Cuando se selecciona esta opción, las operaciones de aplicación de sangrías insertan todos los caracteres de tabulación posibles.</span><span class="sxs-lookup"><span data-stu-id="ea727-130">When this option is selected, indent operations insert as many tab characters as possible.</span></span> <span data-ttu-id="ea727-131">Cada carácter de tabulación rellena el número de espacios especificados en **Tamaño de tabulación**.</span><span class="sxs-lookup"><span data-stu-id="ea727-131">Each tab character fills the number of spaces specified in **Tab size**.</span></span> <span data-ttu-id="ea727-132">Si **Tamaño de sangría** no es un múltiplo par de **Tamaño de tabulación**, se agregarán caracteres de espacio para rellenar la diferencia.</span><span class="sxs-lookup"><span data-stu-id="ea727-132">If **Indent size** is not an even multiple of **Tab size**, space characters are added to fill in the difference.</span></span>  
  
  
