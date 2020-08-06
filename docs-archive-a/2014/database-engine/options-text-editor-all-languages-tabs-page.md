---
title: Opciones (editor de texto-todos los idiomas-página tabulaciones) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: bd715d6b-f873-41d4-aa10-57b7098b61cc
author: rothja
ms.author: jroth
ms.openlocfilehash: 13f791e34b2099e8c0492c25886ee6b37ef1a1a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676166"
---
# <a name="options-text-editor---all-languages--tabs-page"></a><span data-ttu-id="03140-102">Opciones (Editor de texto - Todos los idiomas - Página Pestañas)</span><span class="sxs-lookup"><span data-stu-id="03140-102">Options (Text Editor - All Languages -Tabs Page)</span></span>
  <span data-ttu-id="03140-103">Utilice este cuadro de diálogo para establecer el comportamiento de tabulación en los cinco editores de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03140-103">Use this dialog box to set the tabbing behavior in all five of the editors in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="03140-104">Para mostrar estas opciones, haga clic en **Opciones** en el menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="03140-104">To display these options, click **Options** on the **Tools** menu.</span></span> <span data-ttu-id="03140-105">Seleccione la carpeta **Editor de texto**, expanda la carpeta **Todos los lenguajes** y haga clic en **Tabulaciones**.</span><span class="sxs-lookup"><span data-stu-id="03140-105">Select the **Text Editor** folder, expand the **All Languages** folder and then click **Tabs**.</span></span>  
  
## <a name="tabbing-options-by-editor"></a><span data-ttu-id="03140-106">Opciones de tabulación por editor</span><span class="sxs-lookup"><span data-stu-id="03140-106">Tabbing Options by Editor</span></span>  
 <span data-ttu-id="03140-107">Debe usar los cuadros de diálogo de **Todos los lenguajes** para establecer las opciones de los editores DMX, MDX y SQL Server Compact.</span><span class="sxs-lookup"><span data-stu-id="03140-107">You must use the **All Languages** dialogs to set options for the DMX, MDX, and SQL Server Compact editors.</span></span> <span data-ttu-id="03140-108">Las opciones establecidas aquí también se aplican al texto simple, a Transact-SQL y a los editores XML, pero puede establecer opciones por separado para esos editores si expande las subcarpetas correspondientes a esos idiomas y selecciona sus páginas de opciones.</span><span class="sxs-lookup"><span data-stu-id="03140-108">Options set here are also applied to the Plain Text, Transact-SQL, and XML editors, but you can set options separately for those editors by expanding the subfolders for those languages and selecting their option pages.</span></span> <span data-ttu-id="03140-109">Algunos lenguajes no admiten todas las opciones de tabulación.</span><span class="sxs-lookup"><span data-stu-id="03140-109">Some languages do not support all of the tabbing options.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="03140-110">Si establece la opción usar este cuadro de diálogo, pero quiere un valor diferente para el texto simple, Transact-SQL o el editor XML, debe establecer las opciones de esos editores después de aplicar las opciones seleccionadas en el cuadro de diálogo **Todos los lenguajes**.</span><span class="sxs-lookup"><span data-stu-id="03140-110">If you set an option using this dialog, but want a different setting for the Plain Text, Transact-SQL, or XML editors, you must set the options for those editors after applying your selections in the **All Languages** dialog.</span></span>  
  
 <span data-ttu-id="03140-111">El mensaje "Los valores de la sangría (o del tabulador) para formatos de texto individuales están en conflicto entre sí" aparece si se han seleccionado diferentes valores para determinados editores.</span><span class="sxs-lookup"><span data-stu-id="03140-111">The message "The indentation (or tab) settings for individual text formats conflict with each other" is displayed when different settings have been selected for particular editors.</span></span> <span data-ttu-id="03140-112">Por ejemplo, este mensaje aparece si la opción **Bloque** está seleccionada en **Texto simple**, pero se ha seleccionado **Ninguna** en **XML**.</span><span class="sxs-lookup"><span data-stu-id="03140-112">For example, this reminder is displayed if the **Block indenting** option is selected for **Plain Text**, but **None** is selected for **XML**.</span></span>  
  
## <a name="indenting"></a><span data-ttu-id="03140-113">Sangrías</span><span class="sxs-lookup"><span data-stu-id="03140-113">Indenting</span></span>  
 <span data-ttu-id="03140-114">**None**</span><span class="sxs-lookup"><span data-stu-id="03140-114">**None**</span></span>  
 <span data-ttu-id="03140-115">Cuando se selecciona esta opción, no se aplica ninguna sangría a la nueva línea que se crea al presionar ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="03140-115">When this option is selected, the new line created when you press ENTER is not indented.</span></span> <span data-ttu-id="03140-116">El cursor se coloca en la primera columna de la nueva línea.</span><span class="sxs-lookup"><span data-stu-id="03140-116">The cursor is placed at the first column of the new line.</span></span>  
  
 <span data-ttu-id="03140-117">**Bloquear**</span><span class="sxs-lookup"><span data-stu-id="03140-117">**Block**</span></span>  
 <span data-ttu-id="03140-118">Cuando se selecciona esta opción, se aplica una sangría de forma automática a la nueva línea que se crea al presionar ENTRAR, a la misma distancia que la línea anterior.</span><span class="sxs-lookup"><span data-stu-id="03140-118">When this option is selected, the new line created when you press ENTER is automatically indented the same distance as the previous line was indented.</span></span>  
  
 <span data-ttu-id="03140-119">**Automática**</span><span class="sxs-lookup"><span data-stu-id="03140-119">**Smart**</span></span>  
 <span data-ttu-id="03140-120">Cuando se selecciona esta opción, la nueva línea que se crea al presionar ENTRAR se coloca conforme al contexto.</span><span class="sxs-lookup"><span data-stu-id="03140-120">When this option is selected, the new line created when you press ENTER is positioned according to the context.</span></span>  
  
## <a name="tabs"></a><span data-ttu-id="03140-121">Pestañas</span><span class="sxs-lookup"><span data-stu-id="03140-121">Tabs</span></span>  
 <span data-ttu-id="03140-122">**Tamaño de tabulación**</span><span class="sxs-lookup"><span data-stu-id="03140-122">**Tab size**</span></span>  
 <span data-ttu-id="03140-123">Establece la distancia en espacios entre las tabulaciones.</span><span class="sxs-lookup"><span data-stu-id="03140-123">Sets the distance in spaces between tab stops.</span></span> <span data-ttu-id="03140-124">El valor predeterminado es cuatro espacios.</span><span class="sxs-lookup"><span data-stu-id="03140-124">The default is four spaces.</span></span>  
  
 <span data-ttu-id="03140-125">**Tamaño de sangría**</span><span class="sxs-lookup"><span data-stu-id="03140-125">**Indent size**</span></span>  
 <span data-ttu-id="03140-126">Establece el tamaño en espacios de una sangría automática.</span><span class="sxs-lookup"><span data-stu-id="03140-126">Sets the size in spaces of an automatic indentation.</span></span> <span data-ttu-id="03140-127">El valor predeterminado es cuatro espacios.</span><span class="sxs-lookup"><span data-stu-id="03140-127">The default is four spaces.</span></span> <span data-ttu-id="03140-128">Se insertarán caracteres de tabulación, de espacio o ambos para rellenar el tamaño especificado.</span><span class="sxs-lookup"><span data-stu-id="03140-128">Tab characters, space characters, or both will be inserted to fill the specified size.</span></span>  
  
 <span data-ttu-id="03140-129">**Insertar espacios**</span><span class="sxs-lookup"><span data-stu-id="03140-129">**Insert spaces**</span></span>  
 <span data-ttu-id="03140-130">Cuando se selecciona esta opción, las operaciones de aplicación de sangrías solo insertan caracteres de espacio, pero no caracteres de tabulación.</span><span class="sxs-lookup"><span data-stu-id="03140-130">When this option is selected, indent operations insert only space characters, not tab characters.</span></span> <span data-ttu-id="03140-131">Si **Tamaño de sangría** se establece en 5, por ejemplo, se insertarán cinco espacios cada vez que se pulse la tecla TAB o se haga clic en el botón **Aumentar sangría** en la barra de herramientas de la ventana principal de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03140-131">If **Indent size** is set to 5, for example, then five space characters are inserted whenever you press the TAB key or click the **Increase Indent** button on the toolbar of the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] main window.</span></span>  
  
 <span data-ttu-id="03140-132">**Mantener tabulaciones**</span><span class="sxs-lookup"><span data-stu-id="03140-132">**Keep tabs**</span></span>  
 <span data-ttu-id="03140-133">Cuando se selecciona esta opción, las operaciones de aplicación de sangrías insertan todos los caracteres de tabulación posibles.</span><span class="sxs-lookup"><span data-stu-id="03140-133">When this option is selected, indent operations insert as many tab characters as possible.</span></span> <span data-ttu-id="03140-134">Cada carácter de tabulación rellena el número de espacios especificados en **Tamaño de tabulación**.</span><span class="sxs-lookup"><span data-stu-id="03140-134">Each tab character fills the number of spaces specified in **Tab size**.</span></span> <span data-ttu-id="03140-135">Si **Tamaño de sangría** no es un múltiplo par de **Tamaño de tabulación**, se agregarán caracteres de espacio para rellenar la diferencia.</span><span class="sxs-lookup"><span data-stu-id="03140-135">If **Indent size** is not an even multiple of **Tab size**, space characters are added to fill in the difference.</span></span>  
  
  
