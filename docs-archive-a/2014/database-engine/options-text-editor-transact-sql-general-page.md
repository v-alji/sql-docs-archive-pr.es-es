---
title: Opciones (editor de texto-Transact-SQL-página general) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.SQL.General
dev_langs:
- TSQL
ms.assetid: 7021ecb7-8fb5-4d8c-b984-3d34fcde8be2
author: rothja
ms.author: jroth
ms.openlocfilehash: f008d0d84a15cfbf0bfa988232015e6619f4f5c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674991"
---
# <a name="options-text-editor---transact-sql--general-page"></a><span data-ttu-id="d8e1a-102">Opciones (editor de texto-Transact-SQL-página general)</span><span class="sxs-lookup"><span data-stu-id="d8e1a-102">Options (Text Editor - Transact-SQL- General Page)</span></span>
  <span data-ttu-id="d8e1a-103">Utilice el cuadro de diálogo **General** para cambiar el comportamiento general de la edición del Editor de consultas del [!INCLUDE[ssDE](../includes/ssde-md.md)] , que se utiliza para modificar los scripts de [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8e1a-103">Use the **General** options dialog box to change the general editing behavior of the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor, which is used to edit [!INCLUDE[tsql](../includes/tsql-md.md)] scripts.</span></span> <span data-ttu-id="d8e1a-104">Para mostrar esta configuración, haga clic en **Opciones** en el menú **Herramientas**, expanda la subcarpeta **Transact-SQL** y luego haga clic en **General**.</span><span class="sxs-lookup"><span data-stu-id="d8e1a-104">To display these settings, click **Options** on the **Tools** menu, expand the **Transact-SQL** subfolder, and then click **General**.</span></span>  
  
## <a name="setting-options-in-multiple-locations"></a><span data-ttu-id="d8e1a-105">Establecer opciones en varias ubicaciones</span><span class="sxs-lookup"><span data-stu-id="d8e1a-105">Setting Options in Multiple Locations</span></span>  
 <span data-ttu-id="d8e1a-106">Las opciones del Editor de consultas del [!INCLUDE[ssDE](../includes/ssde-md.md)] también se pueden establecer en el cuadro de diálogo **General de Todos los idiomas** .</span><span class="sxs-lookup"><span data-stu-id="d8e1a-106">Options for the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor can also be set in the **All Languages General** dialog.</span></span> <span data-ttu-id="d8e1a-107">Si utiliza los cuadros de diálogo **Todos los lenguajes** para establecer diferentes opciones para los demás editores de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , como los editores MDX o DMX, debe restablecer las opciones del Editor de consultas del [!INCLUDE[ssDE](../includes/ssde-md.md)] mediante este cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="d8e1a-107">If you use the **All Languages** dialogs to set different options for the other [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] editors, such as the DMX or MDX editors, you must reset the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor options using this dialog.</span></span>  
  
## <a name="statement-completion"></a><span data-ttu-id="d8e1a-108">Finalización de instrucciones</span><span class="sxs-lookup"><span data-stu-id="d8e1a-108">Statement Completion</span></span>  
 <span data-ttu-id="d8e1a-109">**Lista de miembros automática**</span><span class="sxs-lookup"><span data-stu-id="d8e1a-109">**Auto list members**</span></span>  
 <span data-ttu-id="d8e1a-110">Cuando se activa esta casilla, se muestran las listas de objetos de base de datos y de esquema, columnas, funciones con valores de tabla o funciones disponibles a medida que se escribe en el editor.</span><span class="sxs-lookup"><span data-stu-id="d8e1a-110">When this check box is selected, lists of available database and schema objects, columns, table-valued functions, or functions are displayed as you type in the editor.</span></span> <span data-ttu-id="d8e1a-111">Elija cualquier elemento de la lista desplegable para insertarlo en el código.</span><span class="sxs-lookup"><span data-stu-id="d8e1a-111">Choose any item from the pop-up list to insert it into your code.</span></span>  
  
 <span data-ttu-id="d8e1a-112">**Ocultar miembros avanzados**</span><span class="sxs-lookup"><span data-stu-id="d8e1a-112">**Hide advanced members**</span></span>  
 <span data-ttu-id="d8e1a-113">Esta casilla no está disponible.</span><span class="sxs-lookup"><span data-stu-id="d8e1a-113">This check box is unavailable.</span></span>  
  
 <span data-ttu-id="d8e1a-114">**Información del parámetro**</span><span class="sxs-lookup"><span data-stu-id="d8e1a-114">**Parameter information**</span></span>  
 <span data-ttu-id="d8e1a-115">Cuando se selecciona esta casilla, se muestra información sobre los parámetros para una función o un procedimiento almacenado que se encuentre inmediatamente a la izquierda del punto de inserción (cursor).</span><span class="sxs-lookup"><span data-stu-id="d8e1a-115">When this check box is selected, parameter information is displayed for a stored procedure or function that is immediately to the left of the insertion point (cursor).</span></span> <span data-ttu-id="d8e1a-116">Esta información incluye una lista de todos los parámetros disponibles con sus nombres y tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="d8e1a-116">The information includes a list of the available parameters with their names and data types.</span></span>  
  
## <a name="settings"></a><span data-ttu-id="d8e1a-117">Configuración</span><span class="sxs-lookup"><span data-stu-id="d8e1a-117">Settings</span></span>  
 <span data-ttu-id="d8e1a-118">**Habilitar espacio virtual**</span><span class="sxs-lookup"><span data-stu-id="d8e1a-118">**Enable virtual space**</span></span>  
 <span data-ttu-id="d8e1a-119">Cuando esta casilla está activada, puede hacer clic en cualquier parte situada más allá del final de una línea de código y escribir.</span><span class="sxs-lookup"><span data-stu-id="d8e1a-119">When this check box is selected, you can click anywhere beyond the end of a line of code and type.</span></span> <span data-ttu-id="d8e1a-120">Seleccione esta casilla para colocar comentarios en un punto coherente junto al código.</span><span class="sxs-lookup"><span data-stu-id="d8e1a-120">Select this check box to position comments at a consistent point next to your code.</span></span> <span data-ttu-id="d8e1a-121">Si se activa esta casilla, se deshabilita la casilla **Ajuste de línea** .</span><span class="sxs-lookup"><span data-stu-id="d8e1a-121">Selecting this check box disables the **Word wrap** check box.</span></span>  
  
 <span data-ttu-id="d8e1a-122">**Ajuste de palabra**</span><span class="sxs-lookup"><span data-stu-id="d8e1a-122">**Word wrap**</span></span>  
 <span data-ttu-id="d8e1a-123">Cuando se selecciona esta casilla, cualquier parte de una línea que se extienda horizontalmente fuera del área visible del editor se mostrará automáticamente en la siguiente línea.</span><span class="sxs-lookup"><span data-stu-id="d8e1a-123">When this check box is selected, any portion of a line that extends horizontally beyond the viewable editor area is automatically displayed on the next line.</span></span> <span data-ttu-id="d8e1a-124">La activación de esta casilla habilita la casilla **Mostrar glifos visuales para ajuste de línea** y deshabilita la casilla **Habilitar espacio virtual** .</span><span class="sxs-lookup"><span data-stu-id="d8e1a-124">Selecting this check box enables the **Show visual glyphs for word wrap** check box and disables the **Enable virtual space** check box.</span></span>  
  
 <span data-ttu-id="d8e1a-125">**Mostrar glifos visuales para ajuste de línea**</span><span class="sxs-lookup"><span data-stu-id="d8e1a-125">**Show visual glyphs for word wrap**</span></span>  
 <span data-ttu-id="d8e1a-126">Cuando esta casilla está activada, aparecerá un indicador de flecha de retorno donde una línea larga se ajusta respecto a la línea siguiente.</span><span class="sxs-lookup"><span data-stu-id="d8e1a-126">When this check box is selected, a return arrow indicator is displayed where a long line wraps to the next line.</span></span>  
  
 <span data-ttu-id="d8e1a-127">**Aplicar comandos Cortar o Copiar a líneas en blanco si no hay selección**</span><span class="sxs-lookup"><span data-stu-id="d8e1a-127">**Apply Cut/Copy commands to blank lines when there is no selection**</span></span>  
 <span data-ttu-id="d8e1a-128">Esta casilla establece el comportamiento del editor cuando el punto de inserción se coloca en una línea en blanco, no se selecciona nada y se hace clic en **Copiar** o **Cortar**.</span><span class="sxs-lookup"><span data-stu-id="d8e1a-128">This check box sets the behavior of the editor when you place the insertion point on a blank line, select nothing, and then click **Copy** or **Cut**.</span></span>  
  
 <span data-ttu-id="d8e1a-129">Cuando se selecciona esta casilla, se copia o se corta la línea en blanco.</span><span class="sxs-lookup"><span data-stu-id="d8e1a-129">When this check box is selected, the blank line is copied or cut.</span></span> <span data-ttu-id="d8e1a-130">Si luego hace clic en **Pegar**, se insertará una nueva línea en blanco.</span><span class="sxs-lookup"><span data-stu-id="d8e1a-130">If you then click **Paste**, a new, blank line is inserted.</span></span>  
  
 <span data-ttu-id="d8e1a-131">Cuando esta casilla está desactivada, no se copia o se corta nada.</span><span class="sxs-lookup"><span data-stu-id="d8e1a-131">When this check box is cleared, nothing is copied or cut.</span></span> <span data-ttu-id="d8e1a-132">Si luego hace clic en **Pegar**, se pegará el contenido de la última copia.</span><span class="sxs-lookup"><span data-stu-id="d8e1a-132">If you then click **Paste**, the content most recently copied is pasted.</span></span> <span data-ttu-id="d8e1a-133">Si previamente no se ha copiado nada, no se pegará nada.</span><span class="sxs-lookup"><span data-stu-id="d8e1a-133">If nothing has been copied previously, nothing is pasted.</span></span>  
  
 <span data-ttu-id="d8e1a-134">Esta configuración no tiene efecto en **Copiar** o **Cortar** cuando una línea no está en blanco.</span><span class="sxs-lookup"><span data-stu-id="d8e1a-134">This setting has no effect on **Copy** or **Cut** when a line is not blank.</span></span> <span data-ttu-id="d8e1a-135">Si no se selecciona nada, se copia o se corta la línea entera.</span><span class="sxs-lookup"><span data-stu-id="d8e1a-135">If nothing is selected, the entire line is copied or cut.</span></span> <span data-ttu-id="d8e1a-136">Si luego hace clic en **Pegar**, se pegará el texto de toda la línea y su carácter de final de línea.</span><span class="sxs-lookup"><span data-stu-id="d8e1a-136">If you then click **Paste**, the text of the entire line and its end line character are pasted.</span></span>  
  
## <a name="display"></a><span data-ttu-id="d8e1a-137">Pantalla</span><span class="sxs-lookup"><span data-stu-id="d8e1a-137">Display</span></span>  
 <span data-ttu-id="d8e1a-138">**Números de línea**</span><span class="sxs-lookup"><span data-stu-id="d8e1a-138">**Line numbers**</span></span>  
 <span data-ttu-id="d8e1a-139">Cuando se selecciona esta casilla, aparecerá un número de línea junto a cada línea de código.</span><span class="sxs-lookup"><span data-stu-id="d8e1a-139">When this check box is selected, a line number appears next to each line of code.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d8e1a-140">Estos números de línea no se agregan al código y no se imprimen.</span><span class="sxs-lookup"><span data-stu-id="d8e1a-140">These line numbers are not added to your code, and they do not print.</span></span> <span data-ttu-id="d8e1a-141">Solo sirven como referencia.</span><span class="sxs-lookup"><span data-stu-id="d8e1a-141">They are for reference only.</span></span>  
  
 <span data-ttu-id="d8e1a-142">**Habilitar acceso a direcciones URL con un solo clic**</span><span class="sxs-lookup"><span data-stu-id="d8e1a-142">**Enable single-click URL navigation**</span></span>  
 <span data-ttu-id="d8e1a-143">Cuando se selecciona esta casilla, el cursor cambia a una mano cuando pasa por encima de una dirección URL en el editor.</span><span class="sxs-lookup"><span data-stu-id="d8e1a-143">When this check box is selected, the cursor changes to a pointing hand as it passes over a URL in the editor.</span></span> <span data-ttu-id="d8e1a-144">Puede hacer clic en la dirección URL para abrir la página indicada en el explorador web.</span><span class="sxs-lookup"><span data-stu-id="d8e1a-144">You can click the URL to display the indicated page in your Web browser.</span></span>  
  
 <span data-ttu-id="d8e1a-145">**Barra de navegación**</span><span class="sxs-lookup"><span data-stu-id="d8e1a-145">**Navigation bar**</span></span>  
 <span data-ttu-id="d8e1a-146">Esta casilla no está disponible.</span><span class="sxs-lookup"><span data-stu-id="d8e1a-146">This check box is unavailable.</span></span>  
  
  
