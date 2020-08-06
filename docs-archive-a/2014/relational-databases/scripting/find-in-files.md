---
title: Buscar en archivos
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Find in Files dialog box
ms.assetid: bf92770a-33df-43ef-85ad-5a9223649b98
author: rothja
ms.author: jroth
ms.openlocfilehash: a7bd3051817198fb22e2bf7e96393ddf2023b703
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677017"
---
# <a name="find-in-files"></a><span data-ttu-id="76627-102">Buscar en archivos</span><span class="sxs-lookup"><span data-stu-id="76627-102">Find in Files</span></span>
  <span data-ttu-id="76627-103">La pestaña **Buscar en archivos** de la ventana Buscar y reemplazar permite buscar en el código de un conjunto especificado de archivos una cadena o expresión.</span><span class="sxs-lookup"><span data-stu-id="76627-103">The **Find in Files** tab of the Find and Replace window enables you to search the code of a specified set of files for a string or expression.</span></span> <span data-ttu-id="76627-104">Las coincidencias que se encuentran y las acciones que se toman aparecen en la ventana Resultados de la búsqueda seleccionada en **Opciones de resultados**.</span><span class="sxs-lookup"><span data-stu-id="76627-104">The matches found and actions taken are listed in the Find Results window selected in **Result Options**.</span></span>  
  
 <span data-ttu-id="76627-105">También hay botones de la barra de la herramientas y teclas de método abreviado disponibles para abrir el cuadro de diálogo **Buscar y reemplazar** .</span><span class="sxs-lookup"><span data-stu-id="76627-105">Toolbar buttons and shortcut keys are also available to open the **Find and Replace** dialog box.</span></span>  
  
 <span data-ttu-id="76627-106">Las secciones siguientes presentan los controles disponibles en la pestaña **Buscar en archivos** .</span><span class="sxs-lookup"><span data-stu-id="76627-106">The sections that follow list controls available on the **Find in Files** tab.</span></span>  
  
## <a name="find-what"></a><span data-ttu-id="76627-107">Buscar</span><span class="sxs-lookup"><span data-stu-id="76627-107">Find What</span></span>  
 <span data-ttu-id="76627-108">Estos controles de la pestaña **Buscar en archivos** permiten especificar la cadena o expresión que se buscará.</span><span class="sxs-lookup"><span data-stu-id="76627-108">These controls on the **Find in Files** tab enable you to specify the string or expression that will be matched.</span></span>  
  
 <span data-ttu-id="76627-109">**Buscar**</span><span class="sxs-lookup"><span data-stu-id="76627-109">**Find what**</span></span>  
 <span data-ttu-id="76627-110">Escriba el texto que desea buscar.</span><span class="sxs-lookup"><span data-stu-id="76627-110">Type the text to search for.</span></span> <span data-ttu-id="76627-111">El cuadro de diálogo intentará rellenar el texto de búsqueda probable utilizando el texto seleccionado con el cursor antes de abrir el cuadro de diálogo, o bien texto cercano o texto que se haya buscado con anterioridad.</span><span class="sxs-lookup"><span data-stu-id="76627-111">The dialog box attempts to fill in a probable search text, using text selected with the cursor before opening the dialog box, or nearby text, or previously searched-for text.</span></span> <span data-ttu-id="76627-112">Podrá reutilizar una de las últimas 20 cadenas de búsqueda seleccionándola en esta lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="76627-112">You can reuse one of the last 20 search strings by selecting it from this drop-down list.</span></span>  
  
 <span data-ttu-id="76627-113">**[cadena con caracteres comodín]**</span><span class="sxs-lookup"><span data-stu-id="76627-113">**[string with wildcards]**</span></span>  
 <span data-ttu-id="76627-114">Si quiere usar caracteres comodín, como asteriscos (`*`) y signos de interrogación de cierre (`?`), en la cadena de búsqueda, active la casilla **Usar** en **Opciones de búsqueda** y haga clic en **Caracteres comodín**.</span><span class="sxs-lookup"><span data-stu-id="76627-114">If you want to use wildcards such as asterisks (`*`) and question marks (`?`) in your search string, select the **Use** check box under **Find Options** and then click **Wildcards**.</span></span>  
  
 <span data-ttu-id="76627-115">**[expresión regular]**</span><span class="sxs-lookup"><span data-stu-id="76627-115">**[regular expression]**</span></span>  
 <span data-ttu-id="76627-116">Para que el motor de búsqueda interprete la cadena de búsqueda como una expresión regular, active la casilla **Usar** en **Opciones de búsqueda** y haga clic en **Expresiones regulares**.</span><span class="sxs-lookup"><span data-stu-id="76627-116">To cause the search engine to interpret your search string as a regular expression, select the **Use** check box under **Find Options** and then click **Regular expressions**.</span></span>  
  
 <span data-ttu-id="76627-117">**Generador de expresiones**</span><span class="sxs-lookup"><span data-stu-id="76627-117">**Expression Builder**</span></span>  
 <span data-ttu-id="76627-118">Este botón triangular, situado junto al cuadro **Buscar** , estará disponible cuando se active la casilla **Usar** en **Opciones de búsqueda**.</span><span class="sxs-lookup"><span data-stu-id="76627-118">This triangular button next to the **Find what** box becomes available when the **Use** check box is selected in **Find Options**.</span></span> <span data-ttu-id="76627-119">Haga clic en este botón para mostrar una lista de caracteres comodín o expresiones regulares, en función de la opción **Usar** seleccionada.</span><span class="sxs-lookup"><span data-stu-id="76627-119">Click this button to display a list of wildcards or regular expressions, depending upon the **Use** option selected.</span></span> <span data-ttu-id="76627-120">Si elige un elemento de esta lista, se agrega a la cadena de **Buscar** .</span><span class="sxs-lookup"><span data-stu-id="76627-120">Choosing any item from this list adds it to the **Find what** string.</span></span>  
  
## <a name="look-in"></a><span data-ttu-id="76627-121">Buscar en</span><span class="sxs-lookup"><span data-stu-id="76627-121">Look In</span></span>  
 <span data-ttu-id="76627-122">La opción elegida en **Buscar en** determina si **Buscar en archivos** busca únicamente en los archivos activos o en todos los archivos almacenados en determinadas carpetas.</span><span class="sxs-lookup"><span data-stu-id="76627-122">The option chosen from the **Look in** drop-down list determines whether **Find in Files** searches only in currently active files or in all files stored within certain folders.</span></span> <span data-ttu-id="76627-123">Seleccione un ámbito de búsqueda en la lista, escriba una ruta de acceso a una carpeta o haga clic en el botón **Examinar** para mostrar el cuadro de diálogo **Elegir carpetas de búsqueda** y elija un conjunto de carpetas para realizar la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="76627-123">Select a search scope from the list, type a folder path, or click the **Browse** button to display the **Custom Directory Set Dialog Box** and choose a set of folders to search.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="76627-124">Si la opción **Buscar en** seleccionada hace que busque un archivo que ha desprotegido del control de código fuente, solo se buscará en la versión del archivo descargada en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="76627-124">If the **Look in** option selected causes you to search a file that you have checked out from source code control, only the version of that file which has been downloaded to your local computer is searched.</span></span>  
  
 <span data-ttu-id="76627-125">**Look in**</span><span class="sxs-lookup"><span data-stu-id="76627-125">**Look in**</span></span>  
 <span data-ttu-id="76627-126">Seleccione un ámbito predefinido de búsqueda en esta lista, o use el cuadro de diálogo **Elegir carpetas de búsqueda** para escribir su propio grupo de directorios.</span><span class="sxs-lookup"><span data-stu-id="76627-126">Select a predefined search scope from this list, or use the **Custom Directory Set** dialog box to enter your own set of directories.</span></span>  
  
 <span data-ttu-id="76627-127">**Documento actual**</span><span class="sxs-lookup"><span data-stu-id="76627-127">**Current Document**</span></span>  
 <span data-ttu-id="76627-128">Esta opción está disponible cuando se abre un documento en un editor.</span><span class="sxs-lookup"><span data-stu-id="76627-128">This option is available when a document is open in an editor.</span></span> <span data-ttu-id="76627-129">Solo busca la cadena de **Buscar**en el documento activo.</span><span class="sxs-lookup"><span data-stu-id="76627-129">It searches only the active document for the string in **Find what**.</span></span>  
  
 <span data-ttu-id="76627-130">**Todos los documentos abiertos**</span><span class="sxs-lookup"><span data-stu-id="76627-130">**All Open Documents**</span></span>  
 <span data-ttu-id="76627-131">Busca en todos los archivos abiertos actualmente para edición.</span><span class="sxs-lookup"><span data-stu-id="76627-131">Searches all files currently opened for editing.</span></span>  
  
 <span data-ttu-id="76627-132">**Proyecto actual**</span><span class="sxs-lookup"><span data-stu-id="76627-132">**Current Project**</span></span>  
 <span data-ttu-id="76627-133">Busca en todos los archivos del proyecto activo.</span><span class="sxs-lookup"><span data-stu-id="76627-133">Searches all files in the active project.</span></span>  
  
 <span data-ttu-id="76627-134">**Toda la solución**</span><span class="sxs-lookup"><span data-stu-id="76627-134">**Entire Solution**</span></span>  
 <span data-ttu-id="76627-135">Busca en todos los archivos de la solución activa.</span><span class="sxs-lookup"><span data-stu-id="76627-135">Searches all files in the active solution.</span></span>  
  
 <span data-ttu-id="76627-136">**Incluir subcarpetas**</span><span class="sxs-lookup"><span data-stu-id="76627-136">**Include subfolders**</span></span>  
 <span data-ttu-id="76627-137">Especifica que se buscarán las subcarpetas de la carpeta especificada en **Buscar en** .</span><span class="sxs-lookup"><span data-stu-id="76627-137">Specifies that subfolders of the folder specified in **Look in** will be searched.</span></span> <span data-ttu-id="76627-138">Requiere un grupo de directorios personalizados.</span><span class="sxs-lookup"><span data-stu-id="76627-138">It requires a custom directory set.</span></span>  
  
 <span data-ttu-id="76627-139">**Browse**</span><span class="sxs-lookup"><span data-stu-id="76627-139">**Browse**</span></span>  
 <span data-ttu-id="76627-140">Haga clic en este botón para que aparezca el cuadro de diálogo **Elegir carpetas de búsqueda** , donde puede reunir, editar, guardar y seleccionar los grupos de directorios con nombre que se van a usar en el cuadro **Buscar en** .</span><span class="sxs-lookup"><span data-stu-id="76627-140">Click this button to display the **Custom Directory Set** dialog box, where you can assemble, edit, save, and select named sets of directories to enter in the **Look in** box.</span></span>  
  
## <a name="find-options"></a><span data-ttu-id="76627-141">Opciones de búsqueda</span><span class="sxs-lookup"><span data-stu-id="76627-141">Find Options</span></span>  
 <span data-ttu-id="76627-142">Puede expandir y contraer la sección **Opciones de búsqueda** .</span><span class="sxs-lookup"><span data-stu-id="76627-142">You can expand or collapse the **Find Options** section.</span></span> <span data-ttu-id="76627-143">Pueden activarse y desactivarse las siguientes opciones.</span><span class="sxs-lookup"><span data-stu-id="76627-143">The following options can be selected or cleared.</span></span>  
  
 <span data-ttu-id="76627-144">**Coincidir mayúsculas y minúsculas**</span><span class="sxs-lookup"><span data-stu-id="76627-144">**Match case**</span></span>  
 <span data-ttu-id="76627-145">Cuando se active esta casilla, en las ventanas Resultados de la búsqueda solo se mostrarán las instancias de la cadena especificada en **Buscar** que coincidan tanto en contenido como en el uso de mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="76627-145">When this check box is selected, the Find Results windows will only display instances of the string specified in **Find what** that are matched both by content and by case.</span></span> <span data-ttu-id="76627-146">Por ejemplo, una búsqueda de **MiObjeto** con la casilla **Coincidir mayúsculas y minúsculas** activada presentaría en los resultados "MiObjeto", pero no "miobjeto" ni "MIOBJETO".</span><span class="sxs-lookup"><span data-stu-id="76627-146">For example, a search for **MyObject** with the **Match case** check box selected will return "MyObject" but not "myobject" or "MYOBJECT."</span></span>  
  
 <span data-ttu-id="76627-147">**Solo palabras completas**</span><span class="sxs-lookup"><span data-stu-id="76627-147">**Match whole word**</span></span>  
 <span data-ttu-id="76627-148">Cuando esta casilla se activa, las ventanas Resultados de la búsqueda solo mostrarán las instancias de la cadena especificada en **Buscar** cuyas palabras completas coincidan.</span><span class="sxs-lookup"><span data-stu-id="76627-148">When this check box is selected, the Find Results windows will only display instances of the string specified in **Find what** that are matched in complete words.</span></span> <span data-ttu-id="76627-149">Por ejemplo, una búsqueda de **MyObject** devolverá "MyObject", pero no devolverá "CMyObject" ni "MyObjectC".</span><span class="sxs-lookup"><span data-stu-id="76627-149">For example, a search for **MyObject** will return "MyObject" but not "CMyObject" or "MyObjectC."</span></span>  
  
 <span data-ttu-id="76627-150">**Uso**</span><span class="sxs-lookup"><span data-stu-id="76627-150">**Use**</span></span>  
 <span data-ttu-id="76627-151">Indica cómo se interpretan los caracteres especiales especificados en los cuadros de texto **Buscar** o **Reemplazar con** .</span><span class="sxs-lookup"><span data-stu-id="76627-151">Indicates how to interpret special characters entered in the **Find what** or **Replace with** text boxes.</span></span> <span data-ttu-id="76627-152">Esta opción incluye **Caracteres comodín** y **Expresiones regulares**.</span><span class="sxs-lookup"><span data-stu-id="76627-152">The options include **Wildcards** and **Regular Expressions**.</span></span>  
  
 <span data-ttu-id="76627-153">**Regular Expressions**</span><span class="sxs-lookup"><span data-stu-id="76627-153">**Regular Expressions**</span></span>  
 <span data-ttu-id="76627-154">Notaciones especiales que definen patrones de texto a partir de los cuales buscar coincidencias.</span><span class="sxs-lookup"><span data-stu-id="76627-154">Special notations define patterns of text to match.</span></span> <span data-ttu-id="76627-155">Para obtener una lista, vea [Buscar texto mediante expresiones regulares](search-text-with-regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="76627-155">For a list, see [Search Text with Regular Expressions](search-text-with-regular-expressions.md).</span></span>  
  
 <span data-ttu-id="76627-156">**Caracteres comodín**</span><span class="sxs-lookup"><span data-stu-id="76627-156">**Wildcards**</span></span>  
 <span data-ttu-id="76627-157">Caracteres especiales, como asteriscos (`*`) y signos de interrogación de cierre (`?`), que representan uno o varios caracteres.</span><span class="sxs-lookup"><span data-stu-id="76627-157">Special characters such as asterisks (`*`) and question marks (`?`) represent one or more characters.</span></span> <span data-ttu-id="76627-158">Para obtener una lista, vea [Buscar texto con caracteres comodín](search-text-with-wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="76627-158">For a list, see [Search Text with Wildcards](search-text-with-wildcards.md).</span></span>  
  
 <span data-ttu-id="76627-159">**Buscar en estos tipos de archivo**</span><span class="sxs-lookup"><span data-stu-id="76627-159">**Look at these file types**</span></span>  
 <span data-ttu-id="76627-160">Esta lista indica los tipos de archivos que se van a buscar en los directorios especificados en **Buscar en**.</span><span class="sxs-lookup"><span data-stu-id="76627-160">This list indicates the types of files to search through in the directories specified in **Look in**.</span></span> <span data-ttu-id="76627-161">Si el campo se deja en blanco, se busca en todos los archivos de los directorios especificados en **Buscar en** .</span><span class="sxs-lookup"><span data-stu-id="76627-161">If this field is left blank, all of the files in the directories specified in **Look in** will be searched.</span></span>  
  
```  
*.[ext]; *.[ext] (manual)  
```  
  
 <span data-ttu-id="76627-162">Para encontrar archivos de un tipo particular, escriba un carácter comodín asterisco (`*`) para el nombre de archivo, seguido de un punto (`.`) y de la extensión del archivo.</span><span class="sxs-lookup"><span data-stu-id="76627-162">To find files of a particular type, enter an asterisk wildcard (`*`) for the file name, followed by a period (`.`) and the file extension.</span></span> <span data-ttu-id="76627-163">Para encontrar más de un tipo, escriba varias cadenas de búsqueda separadas por un punto y coma (`;`).</span><span class="sxs-lookup"><span data-stu-id="76627-163">To find more than one file type, enter multiple search strings separated by a semicolon (`;`).</span></span>  
  
```  
*.[ext]; *.[ext] (from list)  
```  
  
 <span data-ttu-id="76627-164">Seleccione cualquier elemento de la lista para indicar una cadena de búsqueda preconfigurada que buscará archivos de tipos específicos.</span><span class="sxs-lookup"><span data-stu-id="76627-164">Select any item in the list to enter a preconfigured search string that will find files of particular types.</span></span>  
  
## <a name="result-options"></a><span data-ttu-id="76627-165">Opciones de resultados</span><span class="sxs-lookup"><span data-stu-id="76627-165">Result Options</span></span>  
 <span data-ttu-id="76627-166">Determina la ubicación de los resultados cuando hace clic en **Buscar todos**.</span><span class="sxs-lookup"><span data-stu-id="76627-166">Determines the location of the results when you click **Find All**.</span></span> <span data-ttu-id="76627-167">Puede expandir o contraer la sección **Opciones de resultados** .</span><span class="sxs-lookup"><span data-stu-id="76627-167">You can expand or collapse the **Result Options** section.</span></span> <span data-ttu-id="76627-168">Pueden activarse y desactivarse las siguientes opciones.</span><span class="sxs-lookup"><span data-stu-id="76627-168">The following options can be selected or cleared.</span></span>  
  
 <span data-ttu-id="76627-169">**Ventana Resultados de la búsqueda 1**</span><span class="sxs-lookup"><span data-stu-id="76627-169">**Find Results 1 window**</span></span>  
 <span data-ttu-id="76627-170">Cuando se activa esta casilla, los resultados de la búsqueda actual se anexarán al contenido de la ventana Resultados de la búsqueda 1.</span><span class="sxs-lookup"><span data-stu-id="76627-170">When this check box is selected, the results of the current search will be appended to the content of the Find Results 1 window.</span></span> <span data-ttu-id="76627-171">Esta ventana se abre automáticamente para mostrar los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="76627-171">This window opens automatically to display your search results.</span></span> <span data-ttu-id="76627-172">Para abrir manualmente esta ventana, haga clic en **Otras ventanas** en el menú **Ver** y, a continuación, haga clic en **Resultados de la búsqueda 1**.</span><span class="sxs-lookup"><span data-stu-id="76627-172">To open this window manually, click **Other Windows** on the **View** menu and then click **Find Results 1**.</span></span>  
  
 <span data-ttu-id="76627-173">**Ventana Resultados de la búsqueda 2**</span><span class="sxs-lookup"><span data-stu-id="76627-173">**Find Results 2 window**</span></span>  
 <span data-ttu-id="76627-174">Cuando se activa esta casilla, los resultados de la búsqueda actual se anexarán al contenido de la ventana Resultados de la búsqueda 2.</span><span class="sxs-lookup"><span data-stu-id="76627-174">When this check box is selected, the results of the current search will be appended to the content of the Find Results 2 window.</span></span> <span data-ttu-id="76627-175">Esta ventana se abre automáticamente para mostrar los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="76627-175">This window opens automatically to display your search results.</span></span> <span data-ttu-id="76627-176">Para abrir manualmente esta ventana, haga clic en **Otras ventanas** en el menú **Ver** y, a continuación, haga clic en **Resultados de la búsqueda 2**.</span><span class="sxs-lookup"><span data-stu-id="76627-176">To open this window manually, click **Other Windows** on the **View** menu and then click **Find Results 2**.</span></span>  
  
 <span data-ttu-id="76627-177">**Mostrar solo nombres de archivo**</span><span class="sxs-lookup"><span data-stu-id="76627-177">**Display file names only**</span></span>  
 <span data-ttu-id="76627-178">Muestra una entrada por cada archivo que contiene una coincidencia de búsqueda, en lugar de una entrada por cada coincidencia en la ventana Resultados de la búsqueda 1 o Resultados de la búsqueda 2.</span><span class="sxs-lookup"><span data-stu-id="76627-178">Displays one entry per file containing a search match rather than one entry per search match in either the Find Results 1 or Find Results 2 window.</span></span> <span data-ttu-id="76627-179">Esta opción no está disponible en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76627-179">This option is not available in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="76627-180">**Mantener los archivos modificados abiertos después de Reemplazar todo**</span><span class="sxs-lookup"><span data-stu-id="76627-180">**Keep modified files open after Replace All**</span></span>  
 <span data-ttu-id="76627-181">Cuando se selecciona, deja abiertos todos los archivos en los que se han realizado reemplazos, de forma que puede deshacerlos o cambiarlos.</span><span class="sxs-lookup"><span data-stu-id="76627-181">When selected, leaves open all files in which replacements have been made, so you can undo or save the changes.</span></span> <span data-ttu-id="76627-182">Las restricciones de memoria pueden limitar el número de archivos que pueden permanecer abiertos después de una operación de reemplazo.</span><span class="sxs-lookup"><span data-stu-id="76627-182">Memory constraints might limit the number of files that can remain open after a replace operation.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="76627-183">Puede utilizar **Deshacer** solo en los archivos que permanecen abiertos para edición.</span><span class="sxs-lookup"><span data-stu-id="76627-183">You can use **Undo** only on files that remain open for editing.</span></span> <span data-ttu-id="76627-184">Si no se selecciona esta opción, los archivos que no estén abiertos para edición permanecerán cerrados y no estará disponible la opción **Deshacer** para ellos.</span><span class="sxs-lookup"><span data-stu-id="76627-184">If this option is not selected, files that were not already open for editing will remain closed, and no **Undo** option will be available in those files.</span></span>  
  
## <a name="find-and-replace-views"></a><span data-ttu-id="76627-185">Vistas Buscar y reemplazar</span><span class="sxs-lookup"><span data-stu-id="76627-185">Find and Replace Views</span></span>  
 <span data-ttu-id="76627-186">Las pestañas de la parte superior de la ventana Buscar y reemplazar incluyen menús **Ver** .</span><span class="sxs-lookup"><span data-stu-id="76627-186">The tabs at the top of the Find and Replace window include **View** menus.</span></span> <span data-ttu-id="76627-187">Estos menús le permiten elegir un conjunto de campos para que se muestren en el panel activo.</span><span class="sxs-lookup"><span data-stu-id="76627-187">These menus enable you to choose a set of fields to display in the active pane.</span></span> <span data-ttu-id="76627-188">Puede dejar la ventana Buscar y reemplazar acoplada en una ubicación adecuada y después cambiar de pestaña y de vista para realizar cualquier tipo de operación de búsqueda y reemplazo.</span><span class="sxs-lookup"><span data-stu-id="76627-188">You can leave the Find and Replace window docked in a convenient location and then change from tab to tab and view to view to perform any type of find or replace operation.</span></span>  
  
 <span data-ttu-id="76627-189">**Cambiar a Búsqueda rápida**</span><span class="sxs-lookup"><span data-stu-id="76627-189">**Switch to Quick Find**</span></span>  
 <span data-ttu-id="76627-190">Esta pestaña de la barra de herramientas cambia el cuadro de diálogo a **Búsqueda rápida** .</span><span class="sxs-lookup"><span data-stu-id="76627-190">This toolbar tab changes the dialog box to a **Quick Find** dialog box.</span></span>  
  
 <span data-ttu-id="76627-191">**Cambiar a Buscar en archivos**</span><span class="sxs-lookup"><span data-stu-id="76627-191">**Switch to Find in Files**</span></span>  
 <span data-ttu-id="76627-192">Esta pestaña de la barra de herramientas cambia el cuadro de diálogo a **Buscar en archivos** .</span><span class="sxs-lookup"><span data-stu-id="76627-192">This toolbar tab changes the dialog box to a **Find in Files** dialog box.</span></span>  
  
 <span data-ttu-id="76627-193">**Cambiar a Buscar símbolo**</span><span class="sxs-lookup"><span data-stu-id="76627-193">**Switch to Find Symbols**</span></span>  
 <span data-ttu-id="76627-194">Esta pestaña de la barra de herramientas cambia el cuadro de diálogo a **Find in Symbols (Buscar en símbolos)** .</span><span class="sxs-lookup"><span data-stu-id="76627-194">This toolbar tab changes the dialog box to a **Find in Symbols** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76627-195">Consulte también</span><span class="sxs-lookup"><span data-stu-id="76627-195">See Also</span></span>  
 [<span data-ttu-id="76627-196">Métodos abreviados de teclado de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="76627-196">SQL Server Management Studio Keyboard Shortcuts</span></span>](../../ssms/sql-server-management-studio-keyboard-shortcuts.md)  