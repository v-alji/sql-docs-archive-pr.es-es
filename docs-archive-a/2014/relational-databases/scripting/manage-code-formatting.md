---
title: Administrar formato de código
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- indenting code [SQL Server]
- displaying URLs
- code formatting [SQL Server Management Studio]
- collapsing text
- formats [SQL Server], code formatting in SQL Server Management Studio
- hiding text
- formats [SQL Server]
- text [SQL Server], code formats
- automatic indentation
- converting text to lower case
- Query Editor [SQL Server Management Studio], managing code formats
- URL displayed in code [SQL Server Management Studio]
- converting text to upper case
- text [SQL Server]
- unindenting code
ms.assetid: ddbac4d2-6bdc-4467-a352-e869ec880eed
author: rothja
ms.author: jroth
ms.openlocfilehash: 873848c8aee575b47f7a3d8c31d8392cba5ed12e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677518"
---
# <a name="manage-code-formatting"></a><span data-ttu-id="f20b8-102">Administrar formato de código</span><span class="sxs-lookup"><span data-stu-id="f20b8-102">Manage Code Formatting</span></span>
  <span data-ttu-id="f20b8-103">Con el editor, puede aplicar formato al código mediante sangrías, texto oculto, direcciones URL, etc.</span><span class="sxs-lookup"><span data-stu-id="f20b8-103">With the Editor you can format your code with indenting, hidden text, URLs, and so forth.</span></span> <span data-ttu-id="f20b8-104">También se puede aplicar formato al código automáticamente a medida que se escribe mediante sangrías automáticas.</span><span class="sxs-lookup"><span data-stu-id="f20b8-104">You can also auto-format your code as you type by using Smart Indenting.</span></span>  
  
## <a name="indenting"></a><span data-ttu-id="f20b8-105">Sangrías</span><span class="sxs-lookup"><span data-stu-id="f20b8-105">Indenting</span></span>  
 <span data-ttu-id="f20b8-106">Puede optar entre tres estilos diferentes de sangría de texto.</span><span class="sxs-lookup"><span data-stu-id="f20b8-106">You can choose three different styles of text indenting.</span></span> <span data-ttu-id="f20b8-107">También puede especificar cuántos espacios componen una única sangría o tabulación, y si el editor utiliza tabulaciones o caracteres de espacio al aplicar sangrías.</span><span class="sxs-lookup"><span data-stu-id="f20b8-107">You can also specify how many spaces compose a single indentation or tab, and whether the Editor uses tabs or space characters when indenting.</span></span>  
  
#### <a name="to-choose-an-indenting-style"></a><span data-ttu-id="f20b8-108">Para elegir un estilo de sangría</span><span class="sxs-lookup"><span data-stu-id="f20b8-108">To choose an indenting style</span></span>  
  
1.  <span data-ttu-id="f20b8-109">En el menú **Herramientas** , haga clic en **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="f20b8-109">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="f20b8-110">Haga clic en **Editor de texto**.</span><span class="sxs-lookup"><span data-stu-id="f20b8-110">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="f20b8-111">Seleccione **Todos los lenguajes** para establecer la sangría para todos los lenguajes.</span><span class="sxs-lookup"><span data-stu-id="f20b8-111">Click the folder, and select **All Languages** to set indenting for all languages.</span></span>  
  
4.  <span data-ttu-id="f20b8-112">Haga clic en **Tabulaciones**.</span><span class="sxs-lookup"><span data-stu-id="f20b8-112">Click **Tabs**.</span></span>  
  
5.  <span data-ttu-id="f20b8-113">Haga clic en una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="f20b8-113">Click one of the following options:</span></span>  
  
    -   <span data-ttu-id="f20b8-114">**No**.</span><span class="sxs-lookup"><span data-stu-id="f20b8-114">**None**.</span></span> <span data-ttu-id="f20b8-115">El cursor va al comienzo de la línea siguiente.</span><span class="sxs-lookup"><span data-stu-id="f20b8-115">The cursor goes to the beginning of the next line.</span></span>  
  
    -   <span data-ttu-id="f20b8-116">**Bloqueo**.</span><span class="sxs-lookup"><span data-stu-id="f20b8-116">**Block**.</span></span> <span data-ttu-id="f20b8-117">El cursor alinea la línea siguiente con la anterior.</span><span class="sxs-lookup"><span data-stu-id="f20b8-117">The cursor aligns the next line with the previous line.</span></span>  
  
    -   <span data-ttu-id="f20b8-118">**Inteligente** (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="f20b8-118">**Smart** (Default).</span></span> <span data-ttu-id="f20b8-119">El servicio de lenguaje determina el estilo de sangría adecuado.</span><span class="sxs-lookup"><span data-stu-id="f20b8-119">The language service determines the appropriate indenting style to use.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f20b8-120">Algunos lenguajes no ofrecen las tres opciones de sangría.</span><span class="sxs-lookup"><span data-stu-id="f20b8-120">Some languages do not offer all three indenting options.</span></span>  
  
#### <a name="to-change-indent-tab-settings"></a><span data-ttu-id="f20b8-121">Para cambiar la configuración de las tabulaciones</span><span class="sxs-lookup"><span data-stu-id="f20b8-121">To change indent tab settings</span></span>  
  
1.  <span data-ttu-id="f20b8-122">En el menú **Herramientas** , haga clic en **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="f20b8-122">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="f20b8-123">Haga clic en **Editor de texto**.</span><span class="sxs-lookup"><span data-stu-id="f20b8-123">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="f20b8-124">Seleccione **Todos los lenguajes** para establecer la sangría para todos los lenguajes.</span><span class="sxs-lookup"><span data-stu-id="f20b8-124">Select the folder for **All Languages** to set indenting for all languages.</span></span>  
  
4.  <span data-ttu-id="f20b8-125">Haga clic en **Tabulaciones**.</span><span class="sxs-lookup"><span data-stu-id="f20b8-125">Click **Tabs**.</span></span>  
  
5.  <span data-ttu-id="f20b8-126">Para especificar caracteres de tabulación para las operaciones con tabulaciones y sangrías, haga clic en **Mantener tabulaciones**.</span><span class="sxs-lookup"><span data-stu-id="f20b8-126">To specify tab characters for tab and indent operations, click **Keep tabs**.</span></span> <span data-ttu-id="f20b8-127">Para especificar caracteres de espacio, seleccione **Insertar espacios**.</span><span class="sxs-lookup"><span data-stu-id="f20b8-127">To specify space characters, select **Insert spaces**.</span></span>  
  
     <span data-ttu-id="f20b8-128">Si selecciona **Insertar espacios**, especifique el número de caracteres que representa cada tabulador o sangría en **Tamaño de tabulación** o **Tamaño de sangría**, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="f20b8-128">If you select **Insert Spaces**, enter the number of space characters each tab or indent represents under **Tab Size** or **Indent Size**, respectively.</span></span>  
  
#### <a name="to-indent-code"></a><span data-ttu-id="f20b8-129">Para aplicar sangría al código</span><span class="sxs-lookup"><span data-stu-id="f20b8-129">To indent code</span></span>  
  
1.  <span data-ttu-id="f20b8-130">Seleccione el texto al que desea aplicar sangría.</span><span class="sxs-lookup"><span data-stu-id="f20b8-130">Select the text you want to indent.</span></span>  
  
2.  <span data-ttu-id="f20b8-131">Presione la tecla TAB o haga clic en el botón **Aplicar sangría** de la barra de herramientas Estándar.</span><span class="sxs-lookup"><span data-stu-id="f20b8-131">Press TAB, or click the **Indent** button on the Standard toolbar.</span></span>  
  
#### <a name="to-unindent-code"></a><span data-ttu-id="f20b8-132">Para quitar la sangría del código</span><span class="sxs-lookup"><span data-stu-id="f20b8-132">To unindent code</span></span>  
  
1.  <span data-ttu-id="f20b8-133">Seleccione el texto cuya sangría desea quitar.</span><span class="sxs-lookup"><span data-stu-id="f20b8-133">Select the text you want to unindent.</span></span>  
  
2.  <span data-ttu-id="f20b8-134">Pulse MAYÚS+TAB o haga clic en el botón **Quitar sangría** de la barra de herramientas Estándar.</span><span class="sxs-lookup"><span data-stu-id="f20b8-134">Press SHIFT+TAB, or click the **Unindent** button on the Standard toolbar.</span></span>  
  
#### <a name="to-automatically-indent-all-of-your-code"></a><span data-ttu-id="f20b8-135">Para aplicar sangría automáticamente a todo el código</span><span class="sxs-lookup"><span data-stu-id="f20b8-135">To automatically indent all of your code</span></span>  
  
1.  <span data-ttu-id="f20b8-136">En el menú **Herramientas** , haga clic en **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="f20b8-136">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="f20b8-137">Haga clic en **Editor de texto**.</span><span class="sxs-lookup"><span data-stu-id="f20b8-137">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="f20b8-138">Haga clic en **Todos los lenguajes**.</span><span class="sxs-lookup"><span data-stu-id="f20b8-138">Click **All Languages**.</span></span>  
  
4.  <span data-ttu-id="f20b8-139">Haga clic en **Tabulaciones**.</span><span class="sxs-lookup"><span data-stu-id="f20b8-139">Click **Tabs**.</span></span>  
  
5.  <span data-ttu-id="f20b8-140">Haga clic en **Automática**.</span><span class="sxs-lookup"><span data-stu-id="f20b8-140">Click **Smart**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f20b8-141">La opción **Inteligente** no está disponible en algunos lenguajes.</span><span class="sxs-lookup"><span data-stu-id="f20b8-141">The **Smart** option is not available for some languages.</span></span>  
  
#### <a name="to-convert-white-space-to-tabs"></a><span data-ttu-id="f20b8-142">Para convertir espacios en blanco en tabulaciones</span><span class="sxs-lookup"><span data-stu-id="f20b8-142">To convert white space to tabs</span></span>  
  
1.  <span data-ttu-id="f20b8-143">Seleccione el texto cuyos espacios en blanco desea convertir en tabulaciones.</span><span class="sxs-lookup"><span data-stu-id="f20b8-143">Select the text whose white space you want to convert to tabs.</span></span>  
  
2.  <span data-ttu-id="f20b8-144">En el menú **Editar** , elija **Avanzado**y, a continuación, haga clic en **Aplicar tabulaciones a la selección**.</span><span class="sxs-lookup"><span data-stu-id="f20b8-144">On the **Edit** menu, point to **Advanced**, and click **Tabify Selection**.</span></span>  
  
#### <a name="to-convert-tabs-to-spaces"></a><span data-ttu-id="f20b8-145">Para convertir tabulaciones en espacios</span><span class="sxs-lookup"><span data-stu-id="f20b8-145">To convert tabs to spaces</span></span>  
  
1.  <span data-ttu-id="f20b8-146">Seleccione el texto cuyas tabulaciones desea convertir en espacios.</span><span class="sxs-lookup"><span data-stu-id="f20b8-146">Select the text whose tabs you want to convert to spaces.</span></span>  
  
2.  <span data-ttu-id="f20b8-147">En el menú **Editar** , elija **Avanzado**y, a continuación, haga clic en **No aplicar tabulaciones a la selección**.</span><span class="sxs-lookup"><span data-stu-id="f20b8-147">On the **Edit** menu, point to **Advanced**, and click **Untabify Selection**.</span></span>  
  
 <span data-ttu-id="f20b8-148">El comportamiento de estos comandos depende de la configuración de las tabulaciones en el cuadro de diálogo **Opciones** .</span><span class="sxs-lookup"><span data-stu-id="f20b8-148">The behavior of these commands depends on the tab settings in the **Options** dialog box.</span></span> <span data-ttu-id="f20b8-149">Por ejemplo, si la configuración de las tabulaciones es 4, **Aplicar tabulaciones a la selección** crea una tabulación por cada 4 espacios contiguos. Mientras, **No aplicar tabulaciones a la selección** crea 4 espacios por cada tabulación.</span><span class="sxs-lookup"><span data-stu-id="f20b8-149">For example, if the tab setting is 4, **Tabify Selection** creates a tab for every 4 contiguous spaces, and **Untabify Selection** creates 4 spaces for every tab.</span></span>  
  
## <a name="converting-text-to-upper-and-lower-case"></a><span data-ttu-id="f20b8-150">Convertir texto en mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="f20b8-150">Converting Text to Upper and Lower Case</span></span>  
 <span data-ttu-id="f20b8-151">Puede utilizar comandos para convertir texto en mayúsculas o minúsculas.</span><span class="sxs-lookup"><span data-stu-id="f20b8-151">You can use commands to convert text to all uppercase or lower case.</span></span>  
  
#### <a name="to-switch-text-to-upper-or-lower-case"></a><span data-ttu-id="f20b8-152">Para alternar texto en mayúsculas o minúsculas</span><span class="sxs-lookup"><span data-stu-id="f20b8-152">To switch text to upper or lower case</span></span>  
  
1.  <span data-ttu-id="f20b8-153">Seleccione el texto que desea convertir.</span><span class="sxs-lookup"><span data-stu-id="f20b8-153">Select the text you want to convert.</span></span>  
  
2.  <span data-ttu-id="f20b8-154">Para convertir texto en mayúsculas, pulse CTRL+MAYÚS+U o haga clic en **Poner en mayúsculas** en el submenú **Avanzado** del menú **Editar** .</span><span class="sxs-lookup"><span data-stu-id="f20b8-154">To convert text to uppercase, press CTRL+SHIFT+U, or click **Make Uppercase** on the **Advanced** submenu of the **Edit** menu.</span></span>  
  
3.  <span data-ttu-id="f20b8-155">Para convertir texto en minúsculas, pulse CTRL+MAYÚS+L o haga clic en **Poner en minúsculas** en el submenú **Avanzado** del menú **Editar** .</span><span class="sxs-lookup"><span data-stu-id="f20b8-155">To convert text to lowercase, press CTRL+SHIFT+L, or click **Make Lowercase** on the **Advanced** submenu of the **Edit** menu.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f20b8-156">Para obtener una lista completa de las teclas de método abreviado, vea [Métodos abreviados de teclado de SQL Server Management Studio](../../ssms/sql-server-management-studio-keyboard-shortcuts.md).</span><span class="sxs-lookup"><span data-stu-id="f20b8-156">For a complete list of keyboard shortcut keys, see [SQL Server Management Studio Keyboard Shortcuts](../../ssms/sql-server-management-studio-keyboard-shortcuts.md).</span></span>  
  
## <a name="displaying-and-linking-to-urls"></a><span data-ttu-id="f20b8-157">Mostrar direcciones URL y crear vínculos</span><span class="sxs-lookup"><span data-stu-id="f20b8-157">Displaying and Linking to URLs</span></span>  
 <span data-ttu-id="f20b8-158">En el código, puede crear y mostrar direcciones URL en las que se puede hacer clic.</span><span class="sxs-lookup"><span data-stu-id="f20b8-158">You can create and display clickable URLs in your code.</span></span> <span data-ttu-id="f20b8-159">De manera predeterminada, las direcciones URL:</span><span class="sxs-lookup"><span data-stu-id="f20b8-159">By default, the URLs:</span></span>  
  
-   <span data-ttu-id="f20b8-160">Están subrayadas.</span><span class="sxs-lookup"><span data-stu-id="f20b8-160">Are underlined.</span></span>  
  
-   <span data-ttu-id="f20b8-161">Cambian el puntero del mouse (ratón) a una mano cuando pasa por encima.</span><span class="sxs-lookup"><span data-stu-id="f20b8-161">Change the mouse pointer to a hand when you move over them.</span></span>  
  
-   <span data-ttu-id="f20b8-162">Si la dirección es válida, abren la dirección URL al hacer clic.</span><span class="sxs-lookup"><span data-stu-id="f20b8-162">Open the URL when clicked, if the URL is valid.</span></span>  
  
#### <a name="to-display-a-clickable-url"></a><span data-ttu-id="f20b8-163">Para mostrar una dirección URL en la que se puede hacer clic</span><span class="sxs-lookup"><span data-stu-id="f20b8-163">To display a clickable URL</span></span>  
  
1.  <span data-ttu-id="f20b8-164">En el menú **Herramientas** , haga clic en **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="f20b8-164">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="f20b8-165">Haga clic en **Editor de texto**.</span><span class="sxs-lookup"><span data-stu-id="f20b8-165">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="f20b8-166">Para cambiar la opción para un único lenguaje, haga clic en la carpeta de ese lenguaje y, a continuación, en **General**.</span><span class="sxs-lookup"><span data-stu-id="f20b8-166">To change the option for only one language, click that language folder and then click **General**.</span></span> <span data-ttu-id="f20b8-167">Para cambiar la opción para todos los lenguajes, haga clic en **Todos los lenguajes** y, a continuación, en **General**.</span><span class="sxs-lookup"><span data-stu-id="f20b8-167">To change the option for all languages, click **All Languages** and then click **General**.</span></span>  
  
4.  <span data-ttu-id="f20b8-168">Active **Habilitar la navegación a direcciones URL con un solo clic**.</span><span class="sxs-lookup"><span data-stu-id="f20b8-168">Select **Enable single-click URL navigation**.</span></span>  
  
  
