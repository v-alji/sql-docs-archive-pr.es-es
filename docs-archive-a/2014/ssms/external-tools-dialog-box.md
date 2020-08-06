---
title: Herramientas externas (cuadro de diálogo) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- adding external tools
- external tools [SQL Server Management Studio]
- SQL Server Management Studio [SQL Server], external tools
ms.assetid: ba797203-24d0-4922-9b97-8ab483f1db14
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5789dc150e45c1a0364b7acc0ea7fda443efcf17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746702"
---
# <a name="external-tools-dialog-box"></a><span data-ttu-id="057b3-102">Cuadro de diálogo Herramientas externas</span><span class="sxs-lookup"><span data-stu-id="057b3-102">External Tools Dialog Box</span></span>
  <span data-ttu-id="057b3-103">Use el cuadro de diálogo **Herramientas externas** para agregar herramientas externas como SQLCMD o el Bloc de notas al menú **Herramientas**.</span><span class="sxs-lookup"><span data-stu-id="057b3-103">Use the **External Tools** dialog box to add external tools such as SQLCMD or Notepad to the **Tools** menu.</span></span> <span data-ttu-id="057b3-104">La adición de herramientas externas permite iniciar fácilmente otras aplicaciones mientras se trabaja en el entorno de [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="057b3-104">Adding external tools allows you to easily launch other applications while working in the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] environment.</span></span> <span data-ttu-id="057b3-105">Cuando inicie la herramienta, podrá especificar argumentos y un directorio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="057b3-105">You can specify arguments and a working directory when launching the tool.</span></span> <span data-ttu-id="057b3-106">Además, el resultado de algunas herramientas puede verse en la **Ventana de resultados** .</span><span class="sxs-lookup"><span data-stu-id="057b3-106">In addition, the output from some tools can be displayed in the **Output** window.</span></span> <span data-ttu-id="057b3-107">El cuadro de diálogo **Herramientas externas** está disponible en el menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="057b3-107">The **External Tools** dialog box is available on the **Tools** menu.</span></span>  
  
## <a name="options"></a><span data-ttu-id="057b3-108">Opciones</span><span class="sxs-lookup"><span data-stu-id="057b3-108">Options</span></span>  
 <span data-ttu-id="057b3-109">**Contenido del menú**</span><span class="sxs-lookup"><span data-stu-id="057b3-109">**Menu contents**</span></span>  
 <span data-ttu-id="057b3-110">Enumera los títulos de los elementos agregados actualmente al menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="057b3-110">Lists the titles of the items currently added to the **Tools** menu.</span></span> <span data-ttu-id="057b3-111">Use las flechas **Subir** y **Bajar** para cambiar el orden de los elementos que aparecen en el menú.</span><span class="sxs-lookup"><span data-stu-id="057b3-111">Use the **Move Up** and **Move Down** arrows to change the order the items that appear on the menu.</span></span> <span data-ttu-id="057b3-112">Use el botón **Eliminar** para quitar un elemento del menú.</span><span class="sxs-lookup"><span data-stu-id="057b3-112">Use the **Delete** button to remove an item from the menu.</span></span>  
  
 <span data-ttu-id="057b3-113">**Subir**</span><span class="sxs-lookup"><span data-stu-id="057b3-113">**Move Up**</span></span>  
 <span data-ttu-id="057b3-114">Mueva la herramienta seleccionada a una posición superior en la lista de herramientas que aparece en el menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="057b3-114">Move the selected tool higher in the list of tools that appear on the **Tools** menu.</span></span>  
  
 <span data-ttu-id="057b3-115">**Bajar**</span><span class="sxs-lookup"><span data-stu-id="057b3-115">**Move Down**</span></span>  
 <span data-ttu-id="057b3-116">Mueva la herramienta seleccionada a una posición inferior en la lista de herramientas que aparece en el menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="057b3-116">Move the selected tool lower in the list of tools that appear on the **Tools** menu.</span></span>  
  
 <span data-ttu-id="057b3-117">**Add (Agregar)**</span><span class="sxs-lookup"><span data-stu-id="057b3-117">**Add**</span></span>  
 <span data-ttu-id="057b3-118">Borra los cuadros de texto de modo que se pueda especificar una herramienta nueva.</span><span class="sxs-lookup"><span data-stu-id="057b3-118">Clear the text boxes so you can specify a new tool.</span></span>  
  
 <span data-ttu-id="057b3-119">**Eliminar**</span><span class="sxs-lookup"><span data-stu-id="057b3-119">**Delete**</span></span>  
 <span data-ttu-id="057b3-120">Quite la herramienta o el comando de la lista **Contenido del menú** y del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="057b3-120">Remove the tool or command from the **Menu Contents** list as well as from the **Tools** menu.</span></span>  
  
 <span data-ttu-id="057b3-121">**Título**</span><span class="sxs-lookup"><span data-stu-id="057b3-121">**Title**</span></span>  
 <span data-ttu-id="057b3-122">Especifique el nombre de la herramienta o el comando que aparecerá en el submenú **Herramientas externas** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="057b3-122">Enter the name of the tool or command that will appear on the **External Tools** submenu of the **Tools** menu.</span></span> <span data-ttu-id="057b3-123">Coloque una y comercial (&) antes de una letra del nombre de la herramienta para que esa letra sea un método abreviado de teclado.</span><span class="sxs-lookup"><span data-stu-id="057b3-123">Place an ampersand (&) before a letter in the name of the tool to specify that letter as a keyboard shortcut.</span></span> <span data-ttu-id="057b3-124">Por ejemplo, "&SQLCMD" mostraría SQLCMD en el menú **Herramientas**.</span><span class="sxs-lookup"><span data-stu-id="057b3-124">For example, "&SQLCMD" would display SQLCMD on the **Tools** menu.</span></span>  
  
 <span data-ttu-id="057b3-125">**Comando**</span><span class="sxs-lookup"><span data-stu-id="057b3-125">**Command**</span></span>  
 <span data-ttu-id="057b3-126">Especifique la ruta de acceso al archivo que se va a iniciar.</span><span class="sxs-lookup"><span data-stu-id="057b3-126">Specify the path to the file to launch.</span></span>  
  
 <span data-ttu-id="057b3-127">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="057b3-127">**Arguments**</span></span>  
 <span data-ttu-id="057b3-128">Especifica las variables que pasan a la herramienta cuando ésta se selecciona en el menú.</span><span class="sxs-lookup"><span data-stu-id="057b3-128">Specify the variables that are passed to the tool when the tool is selected on the menu.</span></span> <span data-ttu-id="057b3-129">Los argumentos pueden especificar valores que pasan a la herramienta o el comando cuando estos se inician.</span><span class="sxs-lookup"><span data-stu-id="057b3-129">Arguments can specify values that are passed to the tool or command when it is launched.</span></span> <span data-ttu-id="057b3-130">Por ejemplo, un valor puede especificar un nombre de archivo o un directorio.</span><span class="sxs-lookup"><span data-stu-id="057b3-130">For example, a value can specify a file name or directory.</span></span> <span data-ttu-id="057b3-131">Utilice el botón de flecha para seleccionar entre una lista de argumentos predefinidos.</span><span class="sxs-lookup"><span data-stu-id="057b3-131">Use the arrow button to select from a list of predefined arguments.</span></span> <span data-ttu-id="057b3-132">Es posible agregar más de uno.</span><span class="sxs-lookup"><span data-stu-id="057b3-132">You can add more than one.</span></span> <span data-ttu-id="057b3-133">Para obtener una lista completa de los argumentos predefinidos y sus definiciones, vea [Arguments for External Tools](menu-help/external-tools.md).</span><span class="sxs-lookup"><span data-stu-id="057b3-133">For a complete list of predefined arguments and their definitions, see [Arguments for External Tools](menu-help/external-tools.md).</span></span> <span data-ttu-id="057b3-134">También puede especificar argumentos personalizados (por ejemplo, modificadores de la línea de comandos) según el comando o la herramienta que utilice.</span><span class="sxs-lookup"><span data-stu-id="057b3-134">You can also enter custom arguments (for example, command line switches), depending on the command or tool you use.</span></span>  
  
 <span data-ttu-id="057b3-135">**Usar la ventana de resultados**</span><span class="sxs-lookup"><span data-stu-id="057b3-135">**Use Output window**</span></span>  
 <span data-ttu-id="057b3-136">Abra la ventana de resultados de [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] para mostrar el resultado del comando que se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="057b3-136">Opens the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] Output window to display output of the command being run.</span></span> <span data-ttu-id="057b3-137">No todas las herramientas presentan el resultado en un formato que puede verse en la ventana de resultados.</span><span class="sxs-lookup"><span data-stu-id="057b3-137">Not all tools present output in a format that can be presented in the Output window.</span></span> <span data-ttu-id="057b3-138">Para más información, consulte [Ventana Resultados](../relational-databases/scripting/transact-sql-debugger-output-window.md).</span><span class="sxs-lookup"><span data-stu-id="057b3-138">For more information, see [Output Window](../relational-databases/scripting/transact-sql-debugger-output-window.md).</span></span>  
  
 <span data-ttu-id="057b3-139">**Tratar resultado como Unicode**</span><span class="sxs-lookup"><span data-stu-id="057b3-139">**Treat output as Unicode**</span></span>  
 <span data-ttu-id="057b3-140">Interpreta el resultado como Unicode.</span><span class="sxs-lookup"><span data-stu-id="057b3-140">Interprets the output as Unicode.</span></span>  
  
 <span data-ttu-id="057b3-141">**Directorio inicial**</span><span class="sxs-lookup"><span data-stu-id="057b3-141">**Initial directory**</span></span>  
 <span data-ttu-id="057b3-142">Especifica el directorio de trabajo de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="057b3-142">Specify the working directory of the tool.</span></span> <span data-ttu-id="057b3-143">Utilice el botón de flecha para seleccionar directorios.</span><span class="sxs-lookup"><span data-stu-id="057b3-143">Use the arrow button to select directories.</span></span> <span data-ttu-id="057b3-144">Es posible seleccionar más de uno.</span><span class="sxs-lookup"><span data-stu-id="057b3-144">You can select more than one.</span></span>  
  
 <span data-ttu-id="057b3-145">**Solicitar argumentos**</span><span class="sxs-lookup"><span data-stu-id="057b3-145">**Prompt for arguments**</span></span>  
 <span data-ttu-id="057b3-146">Muestra el cuadro de diálogo **Argumentos** , que permite especificar y modificar valores para los argumentos cada vez que se inicia la herramienta externa.</span><span class="sxs-lookup"><span data-stu-id="057b3-146">Display the **Arguments** dialog box to allow you to enter or edit values for the arguments each time you launch the external tool.</span></span>  
  
 <span data-ttu-id="057b3-147">**Cerrar al salir**</span><span class="sxs-lookup"><span data-stu-id="057b3-147">**Close on exit**</span></span>  
 <span data-ttu-id="057b3-148">Cierra la ventana abierta por la herramienta cuando ésta se cierra.</span><span class="sxs-lookup"><span data-stu-id="057b3-148">Close the window opened by the tool when the tool is closed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="057b3-149">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="057b3-149">Example</span></span>  
 <span data-ttu-id="057b3-150">Al especificar los siguientes valores en el cuadro de diálogo **Herramientas externas** se creará un elemento de menú denominado "DAC" que, cuando se selecciona, abre un símbolo del sistema y ejecuta la utilidad **sqlcmd** con la conexión de administrador dedicada.</span><span class="sxs-lookup"><span data-stu-id="057b3-150">Entering the following values in the **External Tools** dialog box will create a menu item labeled "DAC" that when selected, opens a command prompt and runs the **sqlcmd** utility using the dedicated administrator connection.</span></span>  
  
|<span data-ttu-id="057b3-151">Box</span><span class="sxs-lookup"><span data-stu-id="057b3-151">Box</span></span>|<span data-ttu-id="057b3-152">Value</span><span class="sxs-lookup"><span data-stu-id="057b3-152">Value</span></span>|  
|---------|-----------|  
|<span data-ttu-id="057b3-153">**Título**</span><span class="sxs-lookup"><span data-stu-id="057b3-153">**Title**</span></span>|<span data-ttu-id="057b3-154">DAC</span><span class="sxs-lookup"><span data-stu-id="057b3-154">DAC</span></span>|  
|<span data-ttu-id="057b3-155">**Comando**</span><span class="sxs-lookup"><span data-stu-id="057b3-155">**Command**</span></span>|[!INCLUDE[ssInstallPath](../includes/ssinstallpath-md.md)]<span data-ttu-id="057b3-156">Tools\Binn\SQLCMD.exe</span><span class="sxs-lookup"><span data-stu-id="057b3-156">Tools\Binn\SQLCMD.exe</span></span>|  
|<span data-ttu-id="057b3-157">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="057b3-157">**Arguments**</span></span>|<span data-ttu-id="057b3-158">-A</span><span class="sxs-lookup"><span data-stu-id="057b3-158">-A</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="057b3-159">Consulte también</span><span class="sxs-lookup"><span data-stu-id="057b3-159">See Also</span></span>  
 <span data-ttu-id="057b3-160">[Argumentos para herramientas externas](menu-help/external-tools.md) </span><span class="sxs-lookup"><span data-stu-id="057b3-160">[Arguments for External Tools](menu-help/external-tools.md) </span></span>  
 [<span data-ttu-id="057b3-161">Elementos generales de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="057b3-161">General User Interface Elements</span></span>](general-user-interface-elements.md)  
  
  
