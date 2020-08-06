---
title: Editor de la tarea script (página script) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.scripttask.script.f1
helpviewer_keywords:
- Script Task Editor
ms.assetid: 93da0e0d-83f5-406d-b144-4cce216571cb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4eec491cc689d7d5c616e0819075e1ee5159d4e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744195"
---
# <a name="script-task-editor-script-page"></a><span data-ttu-id="cd995-102">Editor de la tarea Script (página Script)</span><span class="sxs-lookup"><span data-stu-id="cd995-102">Script Task Editor (Script Page)</span></span>
  <span data-ttu-id="cd995-103">Use la página **Script** del cuadro de diálogo **Editor de la tarea Script** para establecer las propiedades del script y para especificar las variables a las que se puede tener acceso desde el mismo.</span><span class="sxs-lookup"><span data-stu-id="cd995-103">Use the **Script** page of the **Script Task Editor** dialog box to set script properties and specify variables that can be accessed by the script.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cd995-104">En [!INCLUDE[ssISversion10](../includes/ssisversion10-md.md)] y versiones posteriores, se recompilan todos los scripts.</span><span class="sxs-lookup"><span data-stu-id="cd995-104">In [!INCLUDE[ssISversion10](../includes/ssisversion10-md.md)] and later versions, all scripts are precompiled.</span></span> <span data-ttu-id="cd995-105">En versiones anteriores, se establece una propiedad **PrecompileScriptIntoBinaryCode** para especificar que se precompiló el script.</span><span class="sxs-lookup"><span data-stu-id="cd995-105">In earlier versions, you set a **PrecompileScriptIntoBinaryCode** property to specify that the script was precompiled.</span></span>  
  
 <span data-ttu-id="cd995-106">Para obtener más información acerca de la tarea Script, vea [Script Task](control-flow/script-task.md) y [Configurar la tarea Script en el editor de la tarea Script](extending-packages-scripting/task/configuring-the-script-task-in-the-script-task-editor.md).</span><span class="sxs-lookup"><span data-stu-id="cd995-106">To learn more about the Script task, see [Script Task](control-flow/script-task.md) and [Configuring the Script Task in the Script Task Editor](extending-packages-scripting/task/configuring-the-script-task-in-the-script-task-editor.md).</span></span> <span data-ttu-id="cd995-107">Para obtener información sobre cómo programar la tarea Script, vea [Extending the Package with the Script Task](extending-packages-scripting/task/extending-the-package-with-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="cd995-107">To learn about programming the Script task, see [Extending the Package with the Script Task](extending-packages-scripting/task/extending-the-package-with-the-script-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="cd995-108">Opciones</span><span class="sxs-lookup"><span data-stu-id="cd995-108">Options</span></span>  
 <span data-ttu-id="cd995-109">**Lenguaje de script**</span><span class="sxs-lookup"><span data-stu-id="cd995-109">**ScriptLanguage**</span></span>  
 <span data-ttu-id="cd995-110">Seleccione el lenguaje de scripting para la tarea, [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual Basic o [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="cd995-110">Select the scripting language for the task, either [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual Basic or [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual C#.</span></span>  
  
 <span data-ttu-id="cd995-111">Una vez haya creado un script para la tarea, no podrá cambiar el valor de la propiedad **ScriptLanguage** .</span><span class="sxs-lookup"><span data-stu-id="cd995-111">After you have created a script for the task, you cannot change the value of the **ScriptLanguage** property.</span></span>  
  
 <span data-ttu-id="cd995-112">Para establecer el lenguaje de scripting predeterminado para la tarea Script, utilice la opción **Lenguaje de scripting** en la página **General** del cuadro de diálogo **Opciones** .</span><span class="sxs-lookup"><span data-stu-id="cd995-112">To set the default scripting language for the Script task, use the **Scripting language** option on **General** page of the **Options** dialog box.</span></span> <span data-ttu-id="cd995-113">Para obtener más información, vea [General Page](general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="cd995-113">For more information, see [General Page](general-page-of-integration-services-designers-options.md).</span></span>  
  
 <span data-ttu-id="cd995-114">**EntryPoint**</span><span class="sxs-lookup"><span data-stu-id="cd995-114">**EntryPoint**</span></span>  
 <span data-ttu-id="cd995-115">Especifique el método que el tiempo de ejecución de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] llama como punto de entrada en el código de la tarea Script.</span><span class="sxs-lookup"><span data-stu-id="cd995-115">Specify the method that the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] runtime calls as the entry point into the code of the Script task.</span></span> <span data-ttu-id="cd995-116">El método especificado debe estar en la clase ScriptMain del [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] proyecto Tools for Applications (VSTA). la clase ScriptMain es la clase predeterminada que generan las plantillas de script.</span><span class="sxs-lookup"><span data-stu-id="cd995-116">The specified method must be in the ScriptMain class of the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Tools for Applications (VSTA) project The ScriptMain class is the default class generated by the script templates.</span></span>  
  
 <span data-ttu-id="cd995-117">Si cambia el nombre del método en el proyecto VSTA, deberá cambiar el valor de la propiedad **EntryPoint** .</span><span class="sxs-lookup"><span data-stu-id="cd995-117">If you change the name of the method in the VSTA project, you must change the value of the **EntryPoint** property.</span></span>  
  
 <span data-ttu-id="cd995-118">**Variables de solo lectura**</span><span class="sxs-lookup"><span data-stu-id="cd995-118">**ReadOnlyVariables**</span></span>  
 <span data-ttu-id="cd995-119">Escriba una lista separada por comas de variables de solo lectura que estén disponibles para el script, o bien haga clic en el botón de puntos suspensivos (**…**) y seleccione las variables en el cuadro de diálogo **Seleccionar variables**.</span><span class="sxs-lookup"><span data-stu-id="cd995-119">Type a comma-separated list of read-only variables that are available to the script, or click the ellipsis (**...**) button and select the variables in the **Select variables** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cd995-120">Los nombres de variables distinguen entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="cd995-120">Variable names are case sensitive.</span></span>  
  
 <span data-ttu-id="cd995-121">**Variables de lectura/escritura**</span><span class="sxs-lookup"><span data-stu-id="cd995-121">**ReadWriteVariables**</span></span>  
 <span data-ttu-id="cd995-122">Escriba una lista separada por comas de variables de lectura y escritura que estén disponibles para el script, o bien haga clic en el botón de puntos suspensivos (**…**) y seleccione las variables en el cuadro de diálogo **Seleccionar variables**.</span><span class="sxs-lookup"><span data-stu-id="cd995-122">Type a comma-separated list of read/write variables that are available to the script, or click the ellipsis (**...**) button and select the variables in the **Select variables** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cd995-123">Los nombres de variables distinguen entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="cd995-123">Variable names are case sensitive.</span></span>  
  
 <span data-ttu-id="cd995-124">**Editar script**</span><span class="sxs-lookup"><span data-stu-id="cd995-124">**Edit Script**</span></span>  
 <span data-ttu-id="cd995-125">Abre la VSTA IDE donde puede crear o modificar el script.</span><span class="sxs-lookup"><span data-stu-id="cd995-125">Opens the VSTA IDE where you can create or modify the script.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd995-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cd995-126">See Also</span></span>  
 <span data-ttu-id="cd995-127">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="cd995-127">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="cd995-128">[Página general](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="cd995-128">[General Page](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="cd995-129">[Editor de la tarea script &#40;página general&#41;](../../2014/integration-services/script-task-editor-general-page.md) </span><span class="sxs-lookup"><span data-stu-id="cd995-129">[Script Task Editor &#40;General Page&#41;](../../2014/integration-services/script-task-editor-general-page.md) </span></span>  
 <span data-ttu-id="cd995-130">[Página Expresiones](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="cd995-130">[Expressions Page](expressions/expressions-page.md) </span></span>  
 <span data-ttu-id="cd995-131">[Ejemplos de tareas de script](extending-packages-scripting-task-examples/script-task-examples.md) </span><span class="sxs-lookup"><span data-stu-id="cd995-131">[Script Task Examples](extending-packages-scripting-task-examples/script-task-examples.md) </span></span>  
 <span data-ttu-id="cd995-132">[Variables de Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="cd995-132">[Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) </span></span>  
 [<span data-ttu-id="cd995-133">Agregar, eliminar, cambiar el ámbito de la variable definida por el usuario en un paquete</span><span class="sxs-lookup"><span data-stu-id="cd995-133">Add, Delete, Change Scope of User-Defined Variable in a Package</span></span>](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md)  
  
  
