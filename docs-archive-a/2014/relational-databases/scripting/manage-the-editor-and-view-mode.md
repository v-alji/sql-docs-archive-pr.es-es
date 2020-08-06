---
title: Administrar el editor y el modo de vista
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Query Editor [SQL Server Management Studio], managing window behavior
- workbench view modes [SQL Server Management Studio]
- full screen mode [SQL Server Management Studio]
- fonts [SQL Server Management Studio]
- word wraps [SQL Server Management Studio]
- virtual space mode [SQL Server Management Studio]
- splitting document views
- displaying line numbers
- view modes [SQL Server Management Studio]
ms.assetid: 25c58a14-9f94-4296-9770-7d84c6bc3969
author: rothja
ms.author: jroth
ms.openlocfilehash: 36788b1fe831a6c15c4aa0668d1759c088fcaa73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676460"
---
# <a name="manage-the-editor-and-view-mode"></a><span data-ttu-id="39386-102">Administrar el editor y el modo de vista</span><span class="sxs-lookup"><span data-stu-id="39386-102">Manage the Editor and View Mode</span></span>
  <span data-ttu-id="39386-103">El editor permite controlar la vista del código de diferentes maneras.</span><span class="sxs-lookup"><span data-stu-id="39386-103">The Editor gives you a number of ways to control the view of your code.</span></span>  
  
## <a name="changing-the-view-mode"></a><span data-ttu-id="39386-104">Cambiar el modo de vista</span><span class="sxs-lookup"><span data-stu-id="39386-104">Changing the View Mode</span></span>  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="39386-105">incluye un modo de vista denominado **Organización por pestañas**que permite abrir varios editores y documentos al mismo tiempo, y tener acceso a ellos mediante pestañas situadas en la parte superior del editor.</span><span class="sxs-lookup"><span data-stu-id="39386-105">features a view mode called **Tabbed Documents**, which allows you to open multiple editors and documents simultaneously and access them through tabs at the top of the Editor.</span></span> <span data-ttu-id="39386-106">También puede abrir el entorno de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] en modo Interfaz de múltiples documentos (MDI) para unir las ventanas sin las pestañas y poder organizarlas en mosaico, minimizarlas, etc.</span><span class="sxs-lookup"><span data-stu-id="39386-106">You can alternatively open the [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] environment in Multiple Document Interface (MDI) mode, which joins windows without the tabs, and allows each window to be tiled, minimized, and so on.</span></span>  
  
#### <a name="to-switch-between-view-modes"></a><span data-ttu-id="39386-107">Para cambiar de un modo de vista a otro</span><span class="sxs-lookup"><span data-stu-id="39386-107">To switch between view modes</span></span>  
  
1.  <span data-ttu-id="39386-108">En el menú **Herramientas** , haga clic en **Opciones** .</span><span class="sxs-lookup"><span data-stu-id="39386-108">Click **Options** on the **Tools** menu.</span></span>  
  
2.  <span data-ttu-id="39386-109">Haga clic en **Entorno**.</span><span class="sxs-lookup"><span data-stu-id="39386-109">Click **Environment**.</span></span> <span data-ttu-id="39386-110">Haga clic en **General**.</span><span class="sxs-lookup"><span data-stu-id="39386-110">Click **General**.</span></span>  
  
3.  <span data-ttu-id="39386-111">Haga clic en **Organización por pestañas** o **Entorno MDI**.</span><span class="sxs-lookup"><span data-stu-id="39386-111">Click **Tabbed documents** or **MDI environment**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="39386-112">Los cambios no serán efectivos hasta que no se reinicie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="39386-112">The changes will not take effect until [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] is restarted.</span></span>  
  
## <a name="splitting-the-view"></a><span data-ttu-id="39386-113">Dividir la vista</span><span class="sxs-lookup"><span data-stu-id="39386-113">Splitting the View</span></span>  
 <span data-ttu-id="39386-114">Una ventana del editor también se puede dividir en dos partes independientes para facilitar la edición.</span><span class="sxs-lookup"><span data-stu-id="39386-114">An Editor window can be split into two separate parts for easier editing.</span></span>  
  
#### <a name="to-split-a-window"></a><span data-ttu-id="39386-115">Para dividir una ventana</span><span class="sxs-lookup"><span data-stu-id="39386-115">To split a window</span></span>  
  
1.  <span data-ttu-id="39386-116">Haga clic en la barra de división, que está situada encima de la barra de desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="39386-116">Click the splitter bar (located above the scroll bar).</span></span>  
  
2.  <span data-ttu-id="39386-117">Arrastre hacia abajo la barra de división.</span><span class="sxs-lookup"><span data-stu-id="39386-117">Drag the splitter bar downward.</span></span>  
  
3.  <span data-ttu-id="39386-118">Para volver a un solo panel, haga doble clic en la barra de división que divide los dos paneles.</span><span class="sxs-lookup"><span data-stu-id="39386-118">To go back to a single pane, double-click the splitter bar dividing the two panes.</span></span>  
  
 <span data-ttu-id="39386-119">El nuevo panel contiene el mismo documento y cualquier cambio realizado en un panel se refleja en el otro, siempre que muestre el mismo lugar del documento.</span><span class="sxs-lookup"><span data-stu-id="39386-119">The new pane contains the same document, and any changes made to one pane are reflected in the other pane as long as that pane displays the same place in the document.</span></span>  
  
## <a name="word-wrap"></a><span data-ttu-id="39386-120">Ajuste de línea</span><span class="sxs-lookup"><span data-stu-id="39386-120">Word Wrap</span></span>  
 <span data-ttu-id="39386-121">Cuando se activa la opción Ajuste de línea, la barra de desplazamiento horizontal desaparece y las líneas de código que exceden el tamaño de la ventana del editor pasan automáticamente a la línea siguiente en lugar de salirse de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="39386-121">When you activate Word Wrap, the horizontal scrollbar is removed and lines of code that exceed the width of the Editor's window size automatically wraps to the next displayed line rather than scrolling off the side of the window.</span></span>  
  
#### <a name="to-activate-word-wrap"></a><span data-ttu-id="39386-122">Para activar el ajuste de línea</span><span class="sxs-lookup"><span data-stu-id="39386-122">To activate word wrap</span></span>  
  
1.  <span data-ttu-id="39386-123">En el menú **Herramientas** , haga clic en **Opciones** .</span><span class="sxs-lookup"><span data-stu-id="39386-123">Click **Options** on the **Tools** menu.</span></span>  
  
2.  <span data-ttu-id="39386-124">Haga clic en **Editor de texto**.</span><span class="sxs-lookup"><span data-stu-id="39386-124">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="39386-125">Abra la carpeta del idioma correspondiente (o **Todos los idiomas** para seleccionar todos los idiomas).</span><span class="sxs-lookup"><span data-stu-id="39386-125">Open the appropriate language folder (or **All Languages** to affect all languages).</span></span>  
  
4.  <span data-ttu-id="39386-126">Seleccione **Ajuste de línea**.</span><span class="sxs-lookup"><span data-stu-id="39386-126">Select **Word wrap**.</span></span>  
  
## <a name="enabling-virtual-space-mode"></a><span data-ttu-id="39386-127">Habilitar el modo de espacio virtual</span><span class="sxs-lookup"><span data-stu-id="39386-127">Enabling Virtual Space Mode</span></span>  
 <span data-ttu-id="39386-128">En el modo de **espacio virtual** , el editor actúa como si el espacio que hay al final de cada línea estuviera lleno de un número infinito de espacios, de manera que las líneas de código continuaran fuera del área visible de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="39386-128">In **Virtual Space** mode, the Editor acts as if the space past the end of each line is filled with an infinite number of spaces, allowing code lines to continue off the side of the visible screen area.</span></span>  
  
#### <a name="to-enable-virtual-space-mode"></a><span data-ttu-id="39386-129">Para habilitar el modo de espacio virtual</span><span class="sxs-lookup"><span data-stu-id="39386-129">To enable Virtual Space mode</span></span>  
  
1.  <span data-ttu-id="39386-130">En el menú **Herramientas** , haga clic en **Opciones** .</span><span class="sxs-lookup"><span data-stu-id="39386-130">Click **Options** on the **Tools** menu.</span></span>  
  
2.  <span data-ttu-id="39386-131">Haga clic en **Editor de texto**.</span><span class="sxs-lookup"><span data-stu-id="39386-131">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="39386-132">Abra la carpeta del idioma correspondiente (o **Todos los idiomas** para seleccionar todos los idiomas).</span><span class="sxs-lookup"><span data-stu-id="39386-132">Open the appropriate language folder (or **All Languages** to affect all languages).</span></span>  
  
4.  <span data-ttu-id="39386-133">Seleccione **Habilitar espacio virtual**.</span><span class="sxs-lookup"><span data-stu-id="39386-133">Select **Enable virtual space**.</span></span>  
  
 <span data-ttu-id="39386-134">Cuando el modo de espacio virtual no está habilitado, el cursor salta del final de una línea al primer carácter de la siguiente y viceversa.</span><span class="sxs-lookup"><span data-stu-id="39386-134">When Virtual Space mode is not enabled, the cursor wraps from the end of one line to the first character of the next line and vice-versa.</span></span>  
  
## <a name="displaying-line-numbers"></a><span data-ttu-id="39386-135">mostrar números de línea</span><span class="sxs-lookup"><span data-stu-id="39386-135">Displaying Line Numbers</span></span>  
 <span data-ttu-id="39386-136">Se puede activar la numeración de líneas en el código.</span><span class="sxs-lookup"><span data-stu-id="39386-136">You can turn on line numbering in your code.</span></span> <span data-ttu-id="39386-137">Los números de línea son muy útiles para navegar por el código.</span><span class="sxs-lookup"><span data-stu-id="39386-137">Line numbers are useful for navigating code.</span></span> <span data-ttu-id="39386-138">Para obtener más información, vea [Navegar por código y texto](navigate-code-and-text.md).</span><span class="sxs-lookup"><span data-stu-id="39386-138">For more information, see [Navigate Code and Text](navigate-code-and-text.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="39386-139">Aunque se active la numeración de líneas, el documento no se imprimirá con los números de línea.</span><span class="sxs-lookup"><span data-stu-id="39386-139">Turning on line numbering does not mean that the document will print with line numbers.</span></span> <span data-ttu-id="39386-140">Para que se impriman, debe activar la casilla **Números de línea** en el comando **Configurar página** del menú **Archivo** .</span><span class="sxs-lookup"><span data-stu-id="39386-140">For line numbers to print, you must select the **Line numbers** check box in the **Page Setup** command on the **File** menu.</span></span>  
  
#### <a name="to-display-line-numbers-in-code"></a><span data-ttu-id="39386-141">Para mostrar los números de línea en el código</span><span class="sxs-lookup"><span data-stu-id="39386-141">To display line numbers in code</span></span>  
  
1.  <span data-ttu-id="39386-142">En el menú **Herramientas** , haga clic en **Opciones** .</span><span class="sxs-lookup"><span data-stu-id="39386-142">Click **Options** on the **Tools** menu.</span></span>  
  
2.  <span data-ttu-id="39386-143">Haga clic en **Editor de texto**.</span><span class="sxs-lookup"><span data-stu-id="39386-143">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="39386-144">Haga clic en **Todos los lenguajes**.</span><span class="sxs-lookup"><span data-stu-id="39386-144">Click **All Languages**.</span></span>  
  
4.  <span data-ttu-id="39386-145">Haga clic en **General**.</span><span class="sxs-lookup"><span data-stu-id="39386-145">Click **General**.</span></span>  
  
5.  <span data-ttu-id="39386-146">Active **Números de línea**.</span><span class="sxs-lookup"><span data-stu-id="39386-146">Select **Line numbers**.</span></span>  
  
 <span data-ttu-id="39386-147">Para aplicar la numeración de líneas solo a algunos lenguajes de programación, seleccione **Números de línea** en la carpeta correspondiente.</span><span class="sxs-lookup"><span data-stu-id="39386-147">To specify line numbering for only some programming languages, select **Line Numbers** in the appropriate folder.</span></span>  
  
## <a name="enabling-full-screen-mode"></a><span data-ttu-id="39386-148">Habilitar el modo de pantalla completa</span><span class="sxs-lookup"><span data-stu-id="39386-148">Enabling Full Screen Mode</span></span>  
 <span data-ttu-id="39386-149">Habilite el modo Pantalla completa para ocultar todas las ventanas de herramienta y ver solamente las ventanas de documento.</span><span class="sxs-lookup"><span data-stu-id="39386-149">You can choose to hide all tool windows and view only document windows by enabling Full Screen mode.</span></span>  
  
#### <a name="to-enable-full-screen-mode"></a><span data-ttu-id="39386-150">Para habilitar el modo de pantalla completa</span><span class="sxs-lookup"><span data-stu-id="39386-150">To enable Full Screen mode</span></span>  
  
1.  <span data-ttu-id="39386-151">Presione ALT+MAYÚS+ENTRAR para alternar el modo Pantalla completa.</span><span class="sxs-lookup"><span data-stu-id="39386-151">Press ALT+SHIFT+ENTER to toggle Full Screen mode.</span></span>  
  
## <a name="using-auto-hide-all"></a><span data-ttu-id="39386-152">Utilizar la opción Ocultar todo automáticamente</span><span class="sxs-lookup"><span data-stu-id="39386-152">Using Auto Hide All</span></span>  
  
#### <a name="to-hide-all-the-tool-windows-at-once"></a><span data-ttu-id="39386-153">Para ocultar todas las ventanas de herramientas a la vez</span><span class="sxs-lookup"><span data-stu-id="39386-153">To hide all the tool windows at once</span></span>  
  
1.  <span data-ttu-id="39386-154">En el menú **Ventana** , active **Ocultar todo automáticamente** .</span><span class="sxs-lookup"><span data-stu-id="39386-154">Select **Auto Hide All** on the **Window** menu.</span></span>  
  
  
