---
title: Modificar scripts SQLCMD con el Editor de consultas
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- scripts [SQL Server], SQLCMD scripts
- SQLCMD scripts
- modifying scripts
- Query Editor [Database Engine], SQLCMD scripts
- scripts [SQL Server], SQL Server Management Studio
ms.assetid: f77b866d-c330-47c9-9e74-0b8d8dff4b31
author: rothja
ms.author: jroth
ms.openlocfilehash: a3466cfc15ea2f4f0c8de5da42f4a1c24c28a575
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673619"
---
# <a name="edit-sqlcmd-scripts-with-query-editor"></a><span data-ttu-id="dcf68-102">Modificar scripts SQLCMD con el Editor de consultas</span><span class="sxs-lookup"><span data-stu-id="dcf68-102">Edit SQLCMD Scripts with Query Editor</span></span>
  <span data-ttu-id="dcf68-103">Con el Editor de consultas de [!INCLUDE[ssDE](../../includes/ssde-md.md)] de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , es posible escribir y modificar consultas como scripts SQLCMD.</span><span class="sxs-lookup"><span data-stu-id="dcf68-103">By using the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] you can write and edit queries as SQLCMD scripts.</span></span> <span data-ttu-id="dcf68-104">Los scripts SQLCMD se usan cuando es necesario procesar comandos del sistema de Windows e instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] en el mismo script.</span><span class="sxs-lookup"><span data-stu-id="dcf68-104">You use SQLCMD scripts when you have to process Windows System commands and [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the same script.</span></span>  
  
## <a name="sqlcmd-mode"></a><span data-ttu-id="dcf68-105">Modo SQLCMD</span><span class="sxs-lookup"><span data-stu-id="dcf68-105">SQLCMD Mode</span></span>  
 <span data-ttu-id="dcf68-106">Para utilizar el Editor de consultas de [!INCLUDE[ssDE](../../includes/ssde-md.md)] para escribir o modificar scripts SQLCMD, es necesario habilitar el modo de scripting SQLCMD.</span><span class="sxs-lookup"><span data-stu-id="dcf68-106">To use the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor to write or edit SQLCMD scripts, you must enable the SQLCMD scripting mode.</span></span> <span data-ttu-id="dcf68-107">De forma predeterminada, el modo SQLCMD no está habilitado en el Editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="dcf68-107">By default, SQLCMD mode is not enabled in the Query Editor.</span></span> <span data-ttu-id="dcf68-108">Puede habilitar el modo de scripting si hace clic en el icono **Modo SQLCMD** de la barra de herramientas o si selecciona **Modo SQLCMD** en el menú **Consulta** .</span><span class="sxs-lookup"><span data-stu-id="dcf68-108">You can enable scripting mode by clicking the **SQLCMD Mode** icon in the toolbar or by selecting **SQLCMD Mode** from the **Query** menu.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dcf68-109">Al habilitar el modo SQLCMD, se desactiva IntelliSense y el depurador de [!INCLUDE[tsql](../../includes/tsql-md.md)] en el Editor de consultas de [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dcf68-109">Enabling SQLCMD mode turns off IntelliSense and the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor.</span></span>  
  
 <span data-ttu-id="dcf68-110">Los scripts SQLCMD del Editor de consultas pueden utilizar las mismas características que todos los scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dcf68-110">SQLCMD scripts in the Query Editor can use the same features that all [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts use.</span></span> <span data-ttu-id="dcf68-111">Entre estas características figuran las siguientes:</span><span class="sxs-lookup"><span data-stu-id="dcf68-111">These features include the following:</span></span>  
  
-   <span data-ttu-id="dcf68-112">Código de colores</span><span class="sxs-lookup"><span data-stu-id="dcf68-112">Color Coding</span></span>  
  
-   <span data-ttu-id="dcf68-113">Ejecución de scripts</span><span class="sxs-lookup"><span data-stu-id="dcf68-113">Executing Scripts</span></span>  
  
-   <span data-ttu-id="dcf68-114">Control de código fuente</span><span class="sxs-lookup"><span data-stu-id="dcf68-114">Source Control</span></span>  
  
-   <span data-ttu-id="dcf68-115">Análisis de scripts</span><span class="sxs-lookup"><span data-stu-id="dcf68-115">Parsing Scripts</span></span>  
  
-   <span data-ttu-id="dcf68-116">Showplan</span><span class="sxs-lookup"><span data-stu-id="dcf68-116">Showplan</span></span>  
  
## <a name="enable-sqlcmd-scripting-in-query-editor"></a><span data-ttu-id="dcf68-117">Habilitar scripting SQLCMD en el Editor de consultas</span><span class="sxs-lookup"><span data-stu-id="dcf68-117">Enable SQLCMD Scripting in Query Editor</span></span>  
 <span data-ttu-id="dcf68-118">Para activar el modo de scripting SQLCMD para una ventana activa del Editor de consultas de [!INCLUDE[ssDE](../../includes/ssde-md.md)] , utilice el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="dcf68-118">To turn SQLCMD scripting on for an active [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window, use the following procedure.</span></span>  
  
#### <a name="to-switch-a-database-engine-query-editor-window-to-sqlcmd-mode"></a><span data-ttu-id="dcf68-119">Para cambiar una ventana del Editor de consultas de Database Engine al modo SQLCMD</span><span class="sxs-lookup"><span data-stu-id="dcf68-119">To switch a Database Engine Query Editor window to SQLCMD mode</span></span>  
  
1.  <span data-ttu-id="dcf68-120">En el Explorador de objetos, haga clic con el botón derecho en el servidor y, después, haga clic en **Nueva consulta**para abrir una ventana nueva del Editor de consultas de [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dcf68-120">In Object Explorer, right-click the server, and then click **New Query**, to open a new [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window.</span></span>  
  
2.  <span data-ttu-id="dcf68-121">En el menú **Consulta** , haga clic en **Modo SQLCMD**.</span><span class="sxs-lookup"><span data-stu-id="dcf68-121">On the **Query** menu, click **SQLCMD Mode**.</span></span>  
  
     <span data-ttu-id="dcf68-122">El Editor de consultas ejecuta instrucciones **sqlcmd** en el contexto del Editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="dcf68-122">The Query Editor executes **sqlcmd** statements in the context of the Query Editor.</span></span>  
  
3.  <span data-ttu-id="dcf68-123">En la barra de herramientas del **Editor SQL** , en la lista **Bases de datos disponibles** , seleccione [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dcf68-123">On the **SQL Editor** toolbar, in the **Available Databases** list, select [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span>  
  
4.  <span data-ttu-id="dcf68-124">En la ventana Editor de consultas, escriba las siguientes dos instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] y, a continuación, la instrucción `!!DIR` **sqlcmd**:</span><span class="sxs-lookup"><span data-stu-id="dcf68-124">In the Query Editor window, type the following two [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and the `!!DIR` **sqlcmd** statement:</span></span>  
  
    ```  
    SELECT DISTINCT Type FROM Sales.SpecialOffer;  
    GO  
    !!DIR  
    GO  
    SELECT ProductCategoryID, Name FROM Production.ProductCategory;  
    GO  
    ```  
  
5.  <span data-ttu-id="dcf68-125">Presione F5 para ejecutar toda la sección de instrucciones mixtas [!INCLUDE[tsql](../../includes/tsql-md.md)] y MS-DOS.</span><span class="sxs-lookup"><span data-stu-id="dcf68-125">Press F5 to execute the whole section of mixed [!INCLUDE[tsql](../../includes/tsql-md.md)] and MS-DOS statements.</span></span>  
  
     <span data-ttu-id="dcf68-126">Observe los paneles de resultados SQL de la primera y tercera instrucciones.</span><span class="sxs-lookup"><span data-stu-id="dcf68-126">Notice the two SQL result panes from the first and third statements.</span></span>  
  
6.  <span data-ttu-id="dcf68-127">En el panel **Resultados** , haga clic en la pestaña **Mensajes** para ver los mensajes de las tres instrucciones:</span><span class="sxs-lookup"><span data-stu-id="dcf68-127">In the **Results** pane, click the **Messages** tab to see the messages from all three statements:</span></span>  
  
    -   <span data-ttu-id="dcf68-128">(6 filas afectadas)</span><span class="sxs-lookup"><span data-stu-id="dcf68-128">(6 row(s) affected)</span></span>  
  
    -   \<The directory information>  
  
    -   <span data-ttu-id="dcf68-129">(4 filas afectadas)</span><span class="sxs-lookup"><span data-stu-id="dcf68-129">(4 row(s) affected)</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="dcf68-130">Cuando se ejecuta desde la línea de comandos, la utilidad **sqlcmd** permite una interacción total con el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="dcf68-130">When executed from the command line, the **sqlcmd** utility permits full interaction with the operating system.</span></span> <span data-ttu-id="dcf68-131">Al usar el Editor de consultas en **Modo SQLCMD**, debe tener cuidado de no ejecutar instrucciones interactivas.</span><span class="sxs-lookup"><span data-stu-id="dcf68-131">When you use the Query Editor in **SQLCMD Mode**, you must be careful not to execute interactive statements.</span></span> <span data-ttu-id="dcf68-132">El Editor de consultas no puede responder a comandos del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="dcf68-132">The Query Editor cannot respond to operating system prompts.</span></span>  
  
 <span data-ttu-id="dcf68-133">Para obtener más información acerca de cómo ejecutar SQLCMD, vea [sqlcmd Utility](../../tools/sqlcmd-utility.md)o realice el tutorial de SQLCMD.</span><span class="sxs-lookup"><span data-stu-id="dcf68-133">For more information about how to run SQLCMD, see [sqlcmd Utility](../../tools/sqlcmd-utility.md), or take the SQLCMD tutorial.</span></span>  
  
## <a name="enable-sqlcmd-scripting-by-default"></a><span data-ttu-id="dcf68-134">Habilitar scripting SQLCMD de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="dcf68-134">Enable SQLCMD Scripting by Default</span></span>  
 <span data-ttu-id="dcf68-135">Para activar scripting SQLCMD de forma predeterminada, seleccione **Opciones** en el menú **Herramientas**, expanda **Ejecución de la consulta**y **SQL Server**, haga clic en la página **General** y, a continuación, active la casilla **De forma predeterminada, abrir nuevas consultas en modo SQLCMD** .</span><span class="sxs-lookup"><span data-stu-id="dcf68-135">To turn SQLCMD scripting on by default, on the **Tools** menu select **Options**, expand **Query Execution**, and **SQL Server**, click the **General** page, and then check the **By default open new queries in SQLCMD Mode** box.</span></span>  
  
## <a name="writing-and-editing-sqlcmd-scripts"></a><span data-ttu-id="dcf68-136">Escribir y modificar scripts SQLCMD</span><span class="sxs-lookup"><span data-stu-id="dcf68-136">Writing and Editing SQLCMD Scripts</span></span>  
 <span data-ttu-id="dcf68-137">Tras habilitar el modo de scripting, puede escribir comandos SQLCMD e instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dcf68-137">After enabling scripting mode you may write SQLCMD commands and [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="dcf68-138">Se aplican las reglas siguientes:</span><span class="sxs-lookup"><span data-stu-id="dcf68-138">The following rules apply:</span></span>  
  
-   <span data-ttu-id="dcf68-139">Los comandos SQLCMD deben ser la primera instrucción de una línea.</span><span class="sxs-lookup"><span data-stu-id="dcf68-139">SQLCMD commands must be the first statement on a line.</span></span>  
  
-   <span data-ttu-id="dcf68-140">Solo se admite un comando SQLCMD en cada línea.</span><span class="sxs-lookup"><span data-stu-id="dcf68-140">Only one SQLCMD command is permitted on each line.</span></span>  
  
-   <span data-ttu-id="dcf68-141">Los comandos SQLCMD pueden ir precedidos de comentarios o espacios en blanco.</span><span class="sxs-lookup"><span data-stu-id="dcf68-141">SQLCMD commands can be preceded by comments or white space.</span></span>  
  
-   <span data-ttu-id="dcf68-142">Los comandos SQLCMD dentro de caracteres de comentario no se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="dcf68-142">SQLCMD commands within comment characters are not executed.</span></span>  
  
-   <span data-ttu-id="dcf68-143">Los caracteres de comentario de una única línea son dos guiones (`--)` y deben aparecer al comienzo de una línea.</span><span class="sxs-lookup"><span data-stu-id="dcf68-143">Single line comment characters are two hyphens (`--)` and must appear at the beginning of a line.</span></span>  
  
-   <span data-ttu-id="dcf68-144">Los comandos del sistema operativo deben ir precedidos de dos signos de exclamación de cierre (`!!`).</span><span class="sxs-lookup"><span data-stu-id="dcf68-144">Operating system commands must be preceded by two exclamation points (`!!`).</span></span> <span data-ttu-id="dcf68-145">El comando con dos signos de exclamación de cierre hace que la instrucción que los sigue se ejecute mediante el procesador de comandos `cmd.exe` .</span><span class="sxs-lookup"><span data-stu-id="dcf68-145">The double-exclamation points command causes the statement that follows the exclamation points to be executed using the `cmd.exe` command processor.</span></span> <span data-ttu-id="dcf68-146">El texto situado tras `!!` se pasa como un parámetro a `cmd.exe`, de modo que la línea de comandos final se ejecutará como `"%SystemRoot%\system32\cmd.exe /c <text after !!>"`.</span><span class="sxs-lookup"><span data-stu-id="dcf68-146">The text after `!!` is passed in as a parameter to `cmd.exe`, so the final command line will execute as: `"%SystemRoot%\system32\cmd.exe /c <text after !!>"`.</span></span>  
  
-   <span data-ttu-id="dcf68-147">Para hacer una distinción clara entre los comandos SQLCMD y [!INCLUDE[tsql](../../includes/tsql-md.md)], todos los comandos SQLCMD deben ir precedidos de dos puntos (`:`).</span><span class="sxs-lookup"><span data-stu-id="dcf68-147">To make a clear distinction between SQLCMD commands and [!INCLUDE[tsql](../../includes/tsql-md.md)], all SQLCMD commands, need to be prefixed with a colon (`:`).</span></span>  
  
-   <span data-ttu-id="dcf68-148">El comando `GO` puede ir precedido de `!!:`</span><span class="sxs-lookup"><span data-stu-id="dcf68-148">The `GO` command may be used without preface, or preceded by `!!:`</span></span>  
  
-   <span data-ttu-id="dcf68-149">El Editor de consultas de [!INCLUDE[ssDE](../../includes/ssde-md.md)] es compatible con las variables de entorno y las variables definidas como parte de un script SQLCMD, aunque no es compatible con variables SQLCMD no integradas ni variables **osql** .</span><span class="sxs-lookup"><span data-stu-id="dcf68-149">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor supports environment variables and variables that are defined as part of a SQLCMD script, but does not support built-in SQLCMD or **osql** variables.</span></span> <span data-ttu-id="dcf68-150">El procesamiento de SQLCMD por [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] distingue entre mayúsculas y minúsculas para las variables.</span><span class="sxs-lookup"><span data-stu-id="dcf68-150">SQLCMD processing by [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] is case sensitive for variables.</span></span> <span data-ttu-id="dcf68-151">Por ejemplo, PRINT '$(COMPUTERNAME)' genera el resultado correcto, pero PRINT '$(ComputerName)' devuelve un error.</span><span class="sxs-lookup"><span data-stu-id="dcf68-151">For example, PRINT '$(COMPUTERNAME)' produces the correct result, but PRINT '$(ComputerName)' returns an error.</span></span>  
  
> [!CAUTION]  
>  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="dcf68-152">usa [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]SqlClient para la ejecución en los modos normal y SQLCMD.</span><span class="sxs-lookup"><span data-stu-id="dcf68-152">uses [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]SqlClient for execution in regular and SQLCMD mode.</span></span> <span data-ttu-id="dcf68-153">Cuando se ejecuta desde la línea de comandos, SQLCMD utiliza el proveedor OLE DB.</span><span class="sxs-lookup"><span data-stu-id="dcf68-153">When run from the command line, SQLCMD uses the OLE DB provider.</span></span> <span data-ttu-id="dcf68-154">Puesto que se pueden aplicar diferentes opciones predeterminadas, es posible observar diferentes comportamientos al ejecutar la misma consulta en el modo SQLCMD de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] y en la herramienta SQLCMD.</span><span class="sxs-lookup"><span data-stu-id="dcf68-154">Because different default options may apply, it is possible to get different behavior while executing the same query in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] SQLCMD Mode, and in the SQLCMD utility.</span></span>  
  
## <a name="supported-sqlcmd-syntax"></a><span data-ttu-id="dcf68-155">Sintaxis SQLCMD compatible</span><span class="sxs-lookup"><span data-stu-id="dcf68-155">Supported SQLCMD Syntax</span></span>  
 <span data-ttu-id="dcf68-156">El Editor de consultas de [!INCLUDE[ssDE](../../includes/ssde-md.md)] admite las siguientes palabras clave de script SQLCMD:</span><span class="sxs-lookup"><span data-stu-id="dcf68-156">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor supports the following SQLCMD script keywords:</span></span>  
  
 `[!!:]GO[count]`  
  
 `!! <command>`  
  
 `:exit(statement)`  
  
 `:Quit`  
  
 `:r <filename>`  
  
 `:setvar <var> <value>`  
  
 `:connect server[\instance] [-l login_timeout] [-U user [-P password]]`  
  
 `:on error [ignore|exit]`  
  
 `:error <filename>|stderr|stdout`  
  
 `:out <filename>|stderr|stdout`  
  
> [!NOTE]  
>  <span data-ttu-id="dcf68-157">Tanto para `:error` como para `:out`, `stderr` y `stdout` envían los resultados a la pestaña de mensajes.</span><span class="sxs-lookup"><span data-stu-id="dcf68-157">For both `:error` and `:out`, `stderr` and `stdout` send output to the messages tab.</span></span>  
  
 <span data-ttu-id="dcf68-158">Los comandos SQLCMD que no aparecen en la lista anterior no son compatibles con el Editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="dcf68-158">SQLCMD commands not listed above are not supported in Query Editor.</span></span> <span data-ttu-id="dcf68-159">Cuando se ejecuta un script que contiene palabras clave SQLCMD que no son compatibles, el editor de consultas enviará un mensaje "omitiendo el comando \* \<ignored command*> " al destino para cada palabra clave no admitida.</span><span class="sxs-lookup"><span data-stu-id="dcf68-159">When a script containing SQLCMD keywords that are not supported is executed, the Query Editor will send an "Ignoring command \*\<ignored command*>" message to the destination for each unsupported keyword.</span></span> <span data-ttu-id="dcf68-160">El script se ejecutará correctamente, aunque los comandos no compatibles se omitirán.</span><span class="sxs-lookup"><span data-stu-id="dcf68-160">The script will execute successfully, but the unsupported commands will be ignored.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="dcf68-161">Puesto que no se está iniciando SQLCMD desde la línea de comandos, existen algunas limitaciones al ejecutar el Editor de consultas en modo SQLCMD.</span><span class="sxs-lookup"><span data-stu-id="dcf68-161">Because you are not starting SQLCMD from the command line, there are some limitations when running Query Editor in SQLCMD Mode.</span></span> <span data-ttu-id="dcf68-162">No es posible enviar parámetros de línea de comandos como variables y, dado que el Editor de consultas no puede responder a las solicitudes del sistema operativo, hay que tener cuidado de no ejecutar instrucciones interactivas.</span><span class="sxs-lookup"><span data-stu-id="dcf68-162">You cannot pass in command-line parameters such as variables, and, because the Query Editor does not have the ability to respond to operating system prompts, you must be careful not to execute interactive statements.</span></span>  
  
## <a name="color-coding-in-sqlcmd-scripts"></a><span data-ttu-id="dcf68-163">Código de colores en los scripts SQLCMD</span><span class="sxs-lookup"><span data-stu-id="dcf68-163">Color Coding in SQLCMD Scripts</span></span>  
 <span data-ttu-id="dcf68-164">Con scripting SQLCMD habilitado, los scripts utilizarán códigos de colores.</span><span class="sxs-lookup"><span data-stu-id="dcf68-164">With SQLCMD scripting enabled, scripts will be color coded.</span></span> <span data-ttu-id="dcf68-165">El código de colores de las palabras clave de [!INCLUDE[tsql](../../includes/tsql-md.md)] permanece igual.</span><span class="sxs-lookup"><span data-stu-id="dcf68-165">The color coding for [!INCLUDE[tsql](../../includes/tsql-md.md)] keywords will remain the same.</span></span> <span data-ttu-id="dcf68-166">Los comandos SQLCMD se presentan con un fondo sombreado.</span><span class="sxs-lookup"><span data-stu-id="dcf68-166">SQLCMD commands are presented with a shaded background.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dcf68-167">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dcf68-167">Example</span></span>  
 <span data-ttu-id="dcf68-168">En el siguiente ejemplo se usa una instrucción **sqlcmd** para crear un archivo de salida denominado testoutput.txt y se ejecutan dos instrucciones SELECT de [!INCLUDE[tsql](../../includes/tsql-md.md)] SELECT junto con un comando del sistema operativo (para imprimir el directorio actual).</span><span class="sxs-lookup"><span data-stu-id="dcf68-168">The following example uses a **sqlcmd** statement to create an output file called testoutput.txt, executes two [!INCLUDE[tsql](../../includes/tsql-md.md)] SELECT statements along with one operating system command (to print out the current directory).</span></span> <span data-ttu-id="dcf68-169">El archivo resultante contiene la salida del mensaje de la instrucción `DIR` seguida de la salida de resultados de las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dcf68-169">The resultant file contains the message output from the `DIR` statement, followed by the results output from the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span>  
  
```  
:out C:\testoutput.txt  
SELECT @@VERSION As 'Server Version'  
!!DIR  
!!:GO  
SELECT @@SERVERNAME AS 'Server Name'  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="dcf68-170">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dcf68-170">See Also</span></span>  
 [<span data-ttu-id="dcf68-171">Utilidad sqlcmd</span><span class="sxs-lookup"><span data-stu-id="dcf68-171">sqlcmd Utility</span></span>](../../tools/sqlcmd-utility.md)  
  
  
