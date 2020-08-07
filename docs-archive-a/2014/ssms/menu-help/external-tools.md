---
title: Herramientas externas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- External Tools dialog box
ms.assetid: d7dae88f-0781-4162-96cd-d3a3a4d82035
author: stevestein
ms.author: sstein
ms.openlocfilehash: a39cd0d139e81c02a7d2a58fae4e74221be7f78e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746084"
---
# <a name="external-tools"></a><span data-ttu-id="03a92-102">Herramientas externas</span><span class="sxs-lookup"><span data-stu-id="03a92-102">External Tools</span></span>
  <span data-ttu-id="03a92-103">Utilice este cuadro de diálogo para agregar herramientas externas, como el Administrador de configuración de SQL Server o el Bloc de notas, al menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="03a92-103">Use this dialog box to add external tools, such as SQL Server Configuration Manager or Notepad, to the **Tools** menu.</span></span> <span data-ttu-id="03a92-104">La adición de herramientas externas facilita el inicio de otras aplicaciones mientras se trabaja con [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03a92-104">Adding external tools allows you to easily launch other applications while working in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="03a92-105">Cuando inicie la herramienta, podrá especificar argumentos y un directorio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="03a92-105">You can specify arguments and a working directory when launching the tool.</span></span> <span data-ttu-id="03a92-106">Además, los resultados de algunas herramientas pueden mostrarse en la ventana Resultados.</span><span class="sxs-lookup"><span data-stu-id="03a92-106">In addition, the outputs from some tools can be displayed in the Output window.</span></span> <span data-ttu-id="03a92-107">El cuadro de diálogo **Herramientas externas** está disponible en el menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="03a92-107">The **External Tools** dialog box is available on the **Tools** menu.</span></span>  
  
## <a name="options"></a><span data-ttu-id="03a92-108">Opciones</span><span class="sxs-lookup"><span data-stu-id="03a92-108">Options</span></span>  
 <span data-ttu-id="03a92-109">**Contenido del menú**</span><span class="sxs-lookup"><span data-stu-id="03a92-109">**Menu Contents**</span></span>  
 <span data-ttu-id="03a92-110">Enumera los títulos de los elementos agregados actualmente al menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="03a92-110">Lists the titles of the items currently added to the **Tools** menu.</span></span> <span data-ttu-id="03a92-111">Use las flechas **Subir** y **Bajar** para cambiar el orden de los elementos que aparecen en el menú.</span><span class="sxs-lookup"><span data-stu-id="03a92-111">Use the **Move Up** and **Move Down** arrows to change the order the items that appear on the menu.</span></span> <span data-ttu-id="03a92-112">Use el botón **Eliminar** para quitar un elemento del menú.</span><span class="sxs-lookup"><span data-stu-id="03a92-112">Use the **Delete** button to remove an item from the menu.</span></span>  
  
 <span data-ttu-id="03a92-113">**Subir**</span><span class="sxs-lookup"><span data-stu-id="03a92-113">**Move Up**</span></span>  
 <span data-ttu-id="03a92-114">Mueva la herramienta seleccionada a una posición superior en la lista de herramientas que aparece en el menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="03a92-114">Move the selected tool higher in the list of tools that appear on the **Tools** menu.</span></span>  
  
 <span data-ttu-id="03a92-115">**Bajar**</span><span class="sxs-lookup"><span data-stu-id="03a92-115">**Move Down**</span></span>  
 <span data-ttu-id="03a92-116">Mueva la herramienta seleccionada a una posición inferior en la lista de herramientas que aparece en el menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="03a92-116">Move the selected tool lower in the list of tools that appear on the **Tools** menu.</span></span>  
  
 <span data-ttu-id="03a92-117">**Add (Agregar)**</span><span class="sxs-lookup"><span data-stu-id="03a92-117">**Add**</span></span>  
 <span data-ttu-id="03a92-118">Borra los cuadros de texto de modo que se pueda especificar una herramienta nueva.</span><span class="sxs-lookup"><span data-stu-id="03a92-118">Clear the text boxes so you can specify a new tool.</span></span>  
  
 <span data-ttu-id="03a92-119">**Eliminar**</span><span class="sxs-lookup"><span data-stu-id="03a92-119">**Delete**</span></span>  
 <span data-ttu-id="03a92-120">Quite la herramienta o el comando de la lista **Contenido del menú** y del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="03a92-120">Remove the tool or command from the **Menu Contents** list as well as from the **Tools** menu.</span></span>  
  
 <span data-ttu-id="03a92-121">**Título**</span><span class="sxs-lookup"><span data-stu-id="03a92-121">**Title**</span></span>  
 <span data-ttu-id="03a92-122">Nombre de la herramienta o del comando que aparecerá en el submenú **Herramientas externas** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="03a92-122">The name of the tool or command that will appear on the **External Tools** submenu of the **Tools** menu.</span></span> <span data-ttu-id="03a92-123">Coloque una "y" comercial (&) antes de una letra del nombre de la herramienta para utilizar dicha letra como tecla de aceleración de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="03a92-123">Place an ampersand before a letter in the name of the tool to use that letter as an accelerator key for the tool.</span></span> <span data-ttu-id="03a92-124">Por ejemplo, `&Spy++` aparecería como **Spy++** en el menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="03a92-124">For example, `&Spy++` would display **Spy++** on the **Tools** menu.</span></span>  
  
 <span data-ttu-id="03a92-125">**Comando**</span><span class="sxs-lookup"><span data-stu-id="03a92-125">**Command**</span></span>  
 <span data-ttu-id="03a92-126">Especifica la ruta de acceso al archivo .exe, .com, .pif, .bat, .cmd u otro que se intente iniciar.</span><span class="sxs-lookup"><span data-stu-id="03a92-126">Specify the path to the .exe, .com, .pif, .bat, .cmd, or other file that you intend to launch.</span></span> <span data-ttu-id="03a92-127">Si activa la casilla `.bat`Usar la ventana de resultados `.com`, podrá ver el resultado de los archivos **,** y de otros archivos en la ventana Resultados.</span><span class="sxs-lookup"><span data-stu-id="03a92-127">The output from `.bat`, `.com`, and other files can be viewed in the Output window if you select the **Use output window** check box.</span></span>  
  
 <span data-ttu-id="03a92-128">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="03a92-128">**Arguments**</span></span>  
 <span data-ttu-id="03a92-129">Especifica las variables que pasan a la herramienta cuando ésta se selecciona en el menú.</span><span class="sxs-lookup"><span data-stu-id="03a92-129">Specify the variables that are passed to the tool when the tool is selected on the menu.</span></span> <span data-ttu-id="03a92-130">Los argumentos pueden especificar valores que pasan a la herramienta o el comando cuando estos se inician.</span><span class="sxs-lookup"><span data-stu-id="03a92-130">Arguments can specify values that are passed to the tool or command when it is launched.</span></span> <span data-ttu-id="03a92-131">Por ejemplo, un valor puede especificar un nombre de archivo o un directorio.</span><span class="sxs-lookup"><span data-stu-id="03a92-131">For example, a value can specify a file name or directory.</span></span> <span data-ttu-id="03a92-132">Use el botón de **flecha** para seleccionar entre una lista de argumentos predefinidos.</span><span class="sxs-lookup"><span data-stu-id="03a92-132">Use the **Arrow** button to select from a list of predefined arguments.</span></span> <span data-ttu-id="03a92-133">Es posible agregar más de uno.</span><span class="sxs-lookup"><span data-stu-id="03a92-133">You can add more than one.</span></span> <span data-ttu-id="03a92-134">Para obtener una lista completa de los argumentos predefinidos y sus definiciones, vea [Arguments for External Tools](external-tools.md).</span><span class="sxs-lookup"><span data-stu-id="03a92-134">For a complete list of predefined arguments and their definitions, see [Arguments for External Tools](external-tools.md).</span></span> <span data-ttu-id="03a92-135">También puede escribir argumentos personalizados (modificadores de la línea de comandos, por ejemplo) en función del comando o la herramienta que utilice.</span><span class="sxs-lookup"><span data-stu-id="03a92-135">You can also enter custom arguments (command-prompt switches, for example), depending on the command or tool you use.</span></span>  
  
 <span data-ttu-id="03a92-136">**Directorio inicial**</span><span class="sxs-lookup"><span data-stu-id="03a92-136">**Initial directory**</span></span>  
 <span data-ttu-id="03a92-137">Especifica el directorio de trabajo de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="03a92-137">Specify the working directory of the tool.</span></span> <span data-ttu-id="03a92-138">Use el botón de **flecha** para seleccionar directorios.</span><span class="sxs-lookup"><span data-stu-id="03a92-138">Use the **Arrow** button to select directories.</span></span> <span data-ttu-id="03a92-139">Es posible seleccionar más de uno.</span><span class="sxs-lookup"><span data-stu-id="03a92-139">You can select more than one.</span></span>  
  
 <span data-ttu-id="03a92-140">**Use output Window**</span><span class="sxs-lookup"><span data-stu-id="03a92-140">**Use output Window**</span></span>  
 <span data-ttu-id="03a92-141">Especifique si los resultados de la herramienta se muestran en la ventana Resultados.</span><span class="sxs-lookup"><span data-stu-id="03a92-141">Specify whether or not results from the tool are displayed in the Output window.</span></span> <span data-ttu-id="03a92-142">Esta opción solo está disponible para archivos que generalmente muestran los resultados en la ventana de la línea de comandos, como los archivos .bat y .com.</span><span class="sxs-lookup"><span data-stu-id="03a92-142">This option is only available for files, such as .bat and .com files, that normally display output in the command prompt window.</span></span> <span data-ttu-id="03a92-143">Si está habilitada, esta ventana facilita la administración de ventanas cuando se sigue el progreso de una herramienta.</span><span class="sxs-lookup"><span data-stu-id="03a92-143">When enabled, this option eases window management when you are following the progress of a tool.</span></span>  
  
 <span data-ttu-id="03a92-144">**Solicitar argumentos**</span><span class="sxs-lookup"><span data-stu-id="03a92-144">**Prompt for arguments**</span></span>  
 <span data-ttu-id="03a92-145">Muestra el cuadro de diálogo **Argumentos** , que le permite especificar y modificar valores para los argumentos cada vez que se inicia la herramienta externa.</span><span class="sxs-lookup"><span data-stu-id="03a92-145">Display the **Arguments** dialog box to enable you to enter or edit values for the arguments each time you launch the external tool.</span></span>  
  
 <span data-ttu-id="03a92-146">**Tratar resultado como Unicode**</span><span class="sxs-lookup"><span data-stu-id="03a92-146">**Treat output as Unicode**</span></span>  
 <span data-ttu-id="03a92-147">Permite que la ventana de resultados acepte Unicode.</span><span class="sxs-lookup"><span data-stu-id="03a92-147">Allow the Output window to accept Unicode.</span></span>  
  
 <span data-ttu-id="03a92-148">**Cerrar al salir**</span><span class="sxs-lookup"><span data-stu-id="03a92-148">**Close On Exit**</span></span>  
 <span data-ttu-id="03a92-149">Cierra la ventana abierta por la herramienta cuando ésta se cierra.</span><span class="sxs-lookup"><span data-stu-id="03a92-149">Close the window opened by the tool when the tool is closed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03a92-150">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="03a92-150">Example</span></span>  
  
#### <a name="to-add-sql-server-configuration-manager-to-the-tools-menu"></a><span data-ttu-id="03a92-151">Para agregar Administrador de configuración de SQL Server al menú Herramientas</span><span class="sxs-lookup"><span data-stu-id="03a92-151">To add SQL Server Configuration Manager to the Tools menu</span></span>  
  
1.  <span data-ttu-id="03a92-152">En el menú **Herramientas** , haga clic en **Herramientas externas**.</span><span class="sxs-lookup"><span data-stu-id="03a92-152">On the **Tools** menu, click **External Tools**.</span></span>  
  
2.  <span data-ttu-id="03a92-153">En el cuadro **Título** , escriba **Administrador de configuración de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="03a92-153">In the **Title** box, type **SQL Server Configuration Manager**.</span></span>  
  
3.  <span data-ttu-id="03a92-154">En el cuadro **comando** , escriba la ruta de acceso al [!INCLUDE[msCoName](../../includes/msconame-md.md)] archivo ejecutable de la consola de administración, como`C:\WINNT\system32\mmc.exe`</span><span class="sxs-lookup"><span data-stu-id="03a92-154">In the **Command** box, type the path to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console executable, such as `C:\WINNT\system32\mmc.exe`</span></span>  
  
4.  <span data-ttu-id="03a92-155">En el cuadro **argumentos** , escriba la ruta de acceso al archivo. msc, como`"C:\WINNT\system32\SQLServerManager.msc"`</span><span class="sxs-lookup"><span data-stu-id="03a92-155">In the **Arguments** box, type the path to the .msc file, such as `"C:\WINNT\system32\SQLServerManager.msc"`</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="03a92-156">Vea las propiedades del acceso directo de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] en el menú **Inicio** para confirmar la ubicación de los archivos en el equipo.</span><span class="sxs-lookup"><span data-stu-id="03a92-156">View the properties of the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] shortcut on the **Start** menu to confirm the location of the files on your computer.</span></span>  
