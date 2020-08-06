---
title: Usar la utilidad sqlcmd
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- Transact-SQL statements, executing
- command prompt utilities [SQL Server], sqlcmd
- statements [SQL Server], executing
- sqlcmd utility, about sqlcmd utility
ms.assetid: 3ec89119-7314-43ef-9e91-12e72bb63d62
author: rothja
ms.author: jroth
ms.openlocfilehash: 922f9915272fb2d7fc63487ec135ce44ee91e88b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675256"
---
# <a name="use-the-sqlcmd-utility"></a><span data-ttu-id="56dd5-102">Usar la utilidad sqlcmd</span><span class="sxs-lookup"><span data-stu-id="56dd5-102">Use the sqlcmd Utility</span></span>
  <span data-ttu-id="56dd5-103">La utilidad `sqlcmd` es una utilidad de la línea de comandos para la ejecución ad hoc e interactiva de instrucciones y scripts de [!INCLUDE[tsql](../../includes/tsql-md.md)] y para la automatización de tareas de scripting de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="56dd5-103">The `sqlcmd` utility is a command-line utility for ad hoc, interactive execution of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and scripts and for automating [!INCLUDE[tsql](../../includes/tsql-md.md)] scripting tasks.</span></span> <span data-ttu-id="56dd5-104">Para usar `sqlcmd` interactivamente, o para compilar archivos de script que se ejecutan mediante `sqlcmd`, los usuarios deben estar familiarizados con [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="56dd5-104">To use `sqlcmd` interactively, or to build script files to be run using `sqlcmd`, users must understand [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="56dd5-105">La utilidad `sqlcmd` se usa normalmente de las formas siguientes:</span><span class="sxs-lookup"><span data-stu-id="56dd5-105">The `sqlcmd` utility is typically used in the following ways:</span></span>  
  
-   <span data-ttu-id="56dd5-106">Los usuarios escriben instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] interactivamente de una forma similar al modo en que trabajan con el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="56dd5-106">Users interactively enter [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in a manner similar to working at the command prompt.</span></span> <span data-ttu-id="56dd5-107">Los resultados se muestran en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="56dd5-107">The results are displayed at the command prompt.</span></span> <span data-ttu-id="56dd5-108">Para abrir una ventana de símbolo del sistema, haga clic en **Inicio**, **Todo los programas**, seleccione **Accesorios**y haga clic en **Símbolo del sistema**.</span><span class="sxs-lookup"><span data-stu-id="56dd5-108">To open a Command Prompt window, click **Start**, click **All Programs**, point to **Accessories**, and then click **Command Prompt**.</span></span> <span data-ttu-id="56dd5-109">En el símbolo del sistema, escriba `sqlcmd` seguido de una lista de opciones que quiera.</span><span class="sxs-lookup"><span data-stu-id="56dd5-109">At the command prompt, type `sqlcmd` followed by a list of options that you want.</span></span> <span data-ttu-id="56dd5-110">Para obtener una lista completa de las opciones admitidas por `sqlcmd` , vea [sqlcmd (utilidad](../../tools/sqlcmd-utility.md)).</span><span class="sxs-lookup"><span data-stu-id="56dd5-110">For a complete list of the options that are supported by `sqlcmd`, see [sqlcmd Utility](../../tools/sqlcmd-utility.md).</span></span>  
  
-   <span data-ttu-id="56dd5-111">Los usuarios envían un trabajo `sqlcmd` especificando la ejecución de una instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] individual o dirigiendo la utilidad hacia un archivo de texto que contiene las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] que se van a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="56dd5-111">Users submit a `sqlcmd` job either by specifying a single [!INCLUDE[tsql](../../includes/tsql-md.md)] statement to execute, or by pointing the utility to a text file that contains [!INCLUDE[tsql](../../includes/tsql-md.md)] statements to execute.</span></span> <span data-ttu-id="56dd5-112">El resultado se dirige normalmente hacia un archivo de texto, aunque también se puede mostrar en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="56dd5-112">The output is usually directed to a text file, but it can also be displayed at the command prompt.</span></span>  
  
-   <span data-ttu-id="56dd5-113">[Modo SQLCMD](edit-sqlcmd-scripts-with-query-editor.md) en el Editor de consultas de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="56dd5-113">[SQLCMD mode](edit-sqlcmd-scripts-with-query-editor.md) in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor.</span></span>  
  
-   <span data-ttu-id="56dd5-114">Objetos de administración de SQL Server (SMO)</span><span class="sxs-lookup"><span data-stu-id="56dd5-114">SQL Server Management Objects (SMO)</span></span>  
  
-   <span data-ttu-id="56dd5-115">Trabajos CmdExec del Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="56dd5-115">SQL Server Agent CmdExec jobs.</span></span>  
  
## <a name="typically-used-sqlcmd-options"></a><span data-ttu-id="56dd5-116">Opciones de sqlcmd que suelen utilizarse</span><span class="sxs-lookup"><span data-stu-id="56dd5-116">Typically Used sqlcmd Options</span></span>  
 <span data-ttu-id="56dd5-117">Las siguientes opciones se usan con mayor frecuencia:</span><span class="sxs-lookup"><span data-stu-id="56dd5-117">The following options are used most frequently:</span></span>  
  
-   <span data-ttu-id="56dd5-118">La opción del servidor (**-S**) que identifica la instancia de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a la que `sqlcmd` se conecta.</span><span class="sxs-lookup"><span data-stu-id="56dd5-118">The server option (**-S**) that identifies the instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to which `sqlcmd` connects.</span></span>  
  
-   <span data-ttu-id="56dd5-119">Opciones de autenticación (**-E**, **-U**y **-P**) que especifican las credenciales que `sqlcmd` usa para conectarse a la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="56dd5-119">Authentication options (**-E**, **-U**, and **-P**) that specify the credentials that `sqlcmd` uses to connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="56dd5-120">La opción **-E** es la predeterminada, por lo que no es necesario especificarla.</span><span class="sxs-lookup"><span data-stu-id="56dd5-120">The **-E** option is the default and does not have to be specified.</span></span>  
  
-   <span data-ttu-id="56dd5-121">Opciones de entrada (**-q**, **-q**e **-i**) que identifican la ubicación de la entrada en `sqlcmd` .</span><span class="sxs-lookup"><span data-stu-id="56dd5-121">Input options (**-Q**, **-q**, and **-i**) that identify the location of the input to `sqlcmd`.</span></span>  
  
-   <span data-ttu-id="56dd5-122">La opción de salida (**-o**) que especifica el archivo en el que `sqlcmd` se va a colocar la salida.</span><span class="sxs-lookup"><span data-stu-id="56dd5-122">The output option (**-o**) that specifies the file in which `sqlcmd` is to put its output.</span></span>  
  
## <a name="connecting-to-the-sqlcmd-utility"></a><span data-ttu-id="56dd5-123">Conectarse a la utilidad sqlcmd</span><span class="sxs-lookup"><span data-stu-id="56dd5-123">Connecting to the sqlcmd Utility</span></span>  
 <span data-ttu-id="56dd5-124">A continuación se indican los usos más comunes de la utilidad `sqlcmd`:</span><span class="sxs-lookup"><span data-stu-id="56dd5-124">The following are common uses of the `sqlcmd` utility:</span></span>  
  
-   <span data-ttu-id="56dd5-125">Conectarse a la instancia predeterminada mediante la Autenticación de Windows para ejecutar de forma interactiva instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="56dd5-125">Connecting to a default instance by using Windows Authentication to interactively run [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    sqlcmd -S <ComputerName>  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="56dd5-126">En el ejemplo anterior, **-E** no se especifica porque es el valor predeterminado y se `sqlcmd` conecta a la instancia predeterminada mediante la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="56dd5-126">In the previous example, **-E** is not specified because it is the default and `sqlcmd` connects to the default instance by using Windows Authentication.</span></span>  
  
-   <span data-ttu-id="56dd5-127">Conectarse a la instancia con nombre mediante la Autenticación de Windows para ejecutar de forma interactiva instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="56dd5-127">Connecting to a named instance by using Windows Authentication to interactively run [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    sqlcmd -S <ComputerName>\<InstanceName>  
    ```  
  
     <span data-ttu-id="56dd5-128">or</span><span class="sxs-lookup"><span data-stu-id="56dd5-128">or</span></span>  
  
    ```  
    sqlcmd -S .\<InstanceName>  
    ```  
  
-   <span data-ttu-id="56dd5-129">Conectarse a una instancia con nombre mediante la Autenticación de Windows y especificar los archivos de entrada y salida:</span><span class="sxs-lookup"><span data-stu-id="56dd5-129">Connecting to a named instance by using Windows Authentication and specifying input and output files:</span></span>  
  
    ```  
    sqlcmd -S <ComputerName>\<InstanceName> -i <MyScript.sql> -o <MyOutput.rpt>  
    ```  
  
-   <span data-ttu-id="56dd5-130">Conectarse a la instancia predeterminada del equipo local mediante la Autenticación de Windows, ejecutar una consulta y mantener la ejecución de `sqlcmd` hasta la finalización de la consulta:</span><span class="sxs-lookup"><span data-stu-id="56dd5-130">Connecting to the default instance on the local computer by using Windows Authentication, executing a query, and having `sqlcmd` remain running after the query has finished running:</span></span>  
  
    ```  
    sqlcmd -q "SELECT * FROM AdventureWorks2012.Person.Person"  
    ```  
  
-   <span data-ttu-id="56dd5-131">Conectarse a la instancia predeterminada del equipo local mediante la Autenticación de Windows, ejecutar una consulta, dirigir la salida a un archivo y cerrar `sqlcmd` después de la finalización de la consulta:</span><span class="sxs-lookup"><span data-stu-id="56dd5-131">Connecting to the default instance on the local computer by using Windows Authentication, executing a query, directing the output to a file, and having `sqlcmd` exit after the query has finished running:</span></span>  
  
    ```  
    sqlcmd -Q "SELECT * FROM AdventureWorks2012.Person.Person" -o MyOutput.txt  
    ```  
  
-   <span data-ttu-id="56dd5-132">Conectarse a una instancia con nombre mediante la Autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ejecutar interactivamente instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] y hacer que `sqlcmd` solicite una contraseña:</span><span class="sxs-lookup"><span data-stu-id="56dd5-132">Connecting to a named instance using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication to interactively run [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, with `sqlcmd` prompting for a password:</span></span>  
  
    ```  
    sqlcmd -U MyLogin -S <ComputerName>\<InstanceName>  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="56dd5-133">Para obtener una lista de opciones admitidas por la utilidad `sqlcmd`, vea `sqlcmd -?`.</span><span class="sxs-lookup"><span data-stu-id="56dd5-133">To see a list of the options that are supported by the `sqlcmd` utility run: `sqlcmd -?`.</span></span>  
  
## <a name="running-transact-sql-statements-interactively-by-using-sqlcmd"></a><span data-ttu-id="56dd5-134">Ejecutar instrucciones Transact-SQL de forma interactiva mediante sqlcmd</span><span class="sxs-lookup"><span data-stu-id="56dd5-134">Running Transact-SQL Statements Interactively by Using sqlcmd</span></span>  
 <span data-ttu-id="56dd5-135">Se puede usar la utilidad `sqlcmd` de forma interactiva para ejecutar instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] en una ventana del símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="56dd5-135">You can use the `sqlcmd` utility interactively to execute [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in a Command Prompt window.</span></span> <span data-ttu-id="56dd5-136">Para ejecutar de forma interactiva [!INCLUDE[tsql](../../includes/tsql-md.md)] instrucciones mediante `sqlcmd` , ejecute la utilidad sin usar las opciones **-q**, **-Q**, **-Z**o **-i** para especificar archivos de entrada o consultas.</span><span class="sxs-lookup"><span data-stu-id="56dd5-136">To interactively execute [!INCLUDE[tsql](../../includes/tsql-md.md)] statements by using `sqlcmd`, run the utility without using the **-Q**, **-q**, **-Z**, or **-i** options to specify any input files or queries.</span></span> <span data-ttu-id="56dd5-137">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="56dd5-137">For example:</span></span>  
  
 `sqlcmd -S <ComputerName>\<InstanceName>`  
  
 <span data-ttu-id="56dd5-138">Cuando se ejecuta el comando sin archivos de entrada ni consultas, `sqlcmd` se conecta a la instancia especificada de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y, a continuación, muestra una nueva línea con un `1>` seguido de un carácter de subrayado intermitente, denominado símbolo del sistema `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="56dd5-138">When the command is executed without input files or queries, `sqlcmd` connects to the specified instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and then displays a new line with a `1>` followed by a blinking underscore that is named the `sqlcmd` prompt.</span></span> <span data-ttu-id="56dd5-139">El `1` significa que se trata de la primera línea de una instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] y el símbolo del sistema `sqlcmd` es el punto en el que empezará la instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] cuando la escriba.</span><span class="sxs-lookup"><span data-stu-id="56dd5-139">The `1` signifies that this is the first line of a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement, and the `sqlcmd` prompt is the point at which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement will start when you type it in.</span></span>  
  
 <span data-ttu-id="56dd5-140">En el símbolo de sistema `sqlcmd`, puede escribir instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] y comandos de `sqlcmd`, como `GO` y `EXIT`.</span><span class="sxs-lookup"><span data-stu-id="56dd5-140">At the `sqlcmd` prompt, you can type both [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and `sqlcmd` commands, such as `GO` and `EXIT`.</span></span> <span data-ttu-id="56dd5-141">Cada instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] se coloca en un búfer llamado caché de instrucciones.</span><span class="sxs-lookup"><span data-stu-id="56dd5-141">Each [!INCLUDE[tsql](../../includes/tsql-md.md)] statement is put in a buffer called the statement cache.</span></span> <span data-ttu-id="56dd5-142">Estas instrucciones se enviarán a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cuando escriba el comando `GO` y pulse ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="56dd5-142">These statements are sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] after you type the `GO` command and press ENTER.</span></span> <span data-ttu-id="56dd5-143">Para salir `sqlcmd` , escriba `EXIT` o `QUIT` al principio de una nueva línea.</span><span class="sxs-lookup"><span data-stu-id="56dd5-143">To exit `sqlcmd`, type `EXIT` or `QUIT` at the start of a new line.</span></span>  
  
 <span data-ttu-id="56dd5-144">Para borrar la memoria caché de instrucciones, escriba `:RESET`.</span><span class="sxs-lookup"><span data-stu-id="56dd5-144">To clear the statement cache, type `:RESET`.</span></span> <span data-ttu-id="56dd5-145">Escribir `^C` hace `sqlcmd` que salga.</span><span class="sxs-lookup"><span data-stu-id="56dd5-145">Typing `^C` causes `sqlcmd` to exit.</span></span> <span data-ttu-id="56dd5-146">`^C` se puede usar también para detener la ejecución de la memoria caché de instrucciones después de emitir un comando `GO`.</span><span class="sxs-lookup"><span data-stu-id="56dd5-146">`^C` can also be used to stop the execution of the statement cache after a `GO` command has been issued.</span></span>  
  
 [!INCLUDE[tsql](../../includes/tsql-md.md)]<span data-ttu-id="56dd5-147">las instrucciones que se escriben en una sesión interactiva pueden editarse escribiendo el comando **: Ed** y el `sqlcmd` símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="56dd5-147">statements that are entered in an interactive session can edited by entering the **:ED** command and the `sqlcmd` prompt.</span></span> <span data-ttu-id="56dd5-148">Se abrirá el editor y, después de editar la instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] y cerrar el editor, la instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] revisada aparecerá en la ventana de comandos.</span><span class="sxs-lookup"><span data-stu-id="56dd5-148">The editor will open and, after editing the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement and closing the editor, the revised [!INCLUDE[tsql](../../includes/tsql-md.md)] statement will appear in the command window.</span></span> <span data-ttu-id="56dd5-149">Escriba `GO` para ejecutar la instrucción revisada [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="56dd5-149">Enter `GO` to run therevised [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
## <a name="quoted-strings"></a><span data-ttu-id="56dd5-150">Cadenas entre comillas</span><span class="sxs-lookup"><span data-stu-id="56dd5-150">Quoted Strings</span></span>  
 <span data-ttu-id="56dd5-151">Los caracteres que están entre comillas se usan sin ningún procesamiento previo adicional, con la excepción de que las comillas se pueden insertar en una cadena especificando dos comillas consecutivas.</span><span class="sxs-lookup"><span data-stu-id="56dd5-151">Characters that are enclosed in quotation marks are used without any additional preprocessing, except that quotations marks can be inserted into a string by entering two consecutive quotation marks.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="56dd5-152">trata esta secuencia de caracteres como una comilla.</span><span class="sxs-lookup"><span data-stu-id="56dd5-152">treats this character sequence as one quotation mark.</span></span> <span data-ttu-id="56dd5-153">Sin embargo, la traducción se lleva a cabo en el servidor. Las variables de scripting no se expandirán si aparecen en una cadena.</span><span class="sxs-lookup"><span data-stu-id="56dd5-153">(However, the translation occurs in the server.) Scripting variables will not be expanded when they appear within a string.</span></span>  
  
 <span data-ttu-id="56dd5-154">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="56dd5-154">For example:</span></span>  
  
 `sqlcmd`  
  
 `PRINT "Length: 5"" 7'";`  
  
 `GO`  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `Length: 5" 7'`  
  
## <a name="strings-that-span-multiple-lines"></a><span data-ttu-id="56dd5-155">Cadenas que abarcan varias líneas</span><span class="sxs-lookup"><span data-stu-id="56dd5-155">Strings That Span Multiple Lines</span></span>  
 <span data-ttu-id="56dd5-156">`sqlcmd` admite scripts con cadenas que abarcan varias líneas.</span><span class="sxs-lookup"><span data-stu-id="56dd5-156">`sqlcmd` supports scripts that have strings that span multiple lines.</span></span> <span data-ttu-id="56dd5-157">Por ejemplo, la siguiente instrucción `SELECT` abarca varias líneas, pero es una única cadena que se ejecuta cuando se presiona la tecla ENTRAR después de escribir `GO`.</span><span class="sxs-lookup"><span data-stu-id="56dd5-157">For example, the following `SELECT` statement spans multiple lines but is a single string executed when you press the ENTER key after typing `GO`.</span></span>  
  
 `SELECT First line`  
  
 `FROM Second line`  
  
 `WHERE Third line;`  
  
 `GO`  
  
## <a name="interactive-sqlcmd-example"></a><span data-ttu-id="56dd5-158">Ejemplo de sqlcmd interactivo</span><span class="sxs-lookup"><span data-stu-id="56dd5-158">Interactive sqlcmd Example</span></span>  
 <span data-ttu-id="56dd5-159">Este es un ejemplo de lo que se ve cuando se ejecuta `sqlcmd` de forma interactiva.</span><span class="sxs-lookup"><span data-stu-id="56dd5-159">This is an example of what you see when you run `sqlcmd` interactively.</span></span>  
  
 <span data-ttu-id="56dd5-160">Cuando se abre una ventana del símbolo del sistema, solo hay una línea similar a:</span><span class="sxs-lookup"><span data-stu-id="56dd5-160">When you open a Command Prompt window, there is one line similar to:</span></span>  
  
 `C:\> _`  
  
 <span data-ttu-id="56dd5-161">Esto significa que la carpeta `C:\` es la carpeta actual y, si se especifica un nombre de archivo, Windows buscará ese archivo en esa carpeta.</span><span class="sxs-lookup"><span data-stu-id="56dd5-161">This means the folder `C:\` is the current folder, and if you specify a file name, Windows will look for the file in that folder.</span></span>  
  
 <span data-ttu-id="56dd5-162">Escriba `sqlcmd` para conectarse a la instancia predeterminada de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en el equipo local; de esta forma, el contenido de la ventana del símbolo del sistema será:</span><span class="sxs-lookup"><span data-stu-id="56dd5-162">Type `sqlcmd` to connect to the default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on the local computer, and the contents of the Command Prompt window will be:</span></span>  
  
 `C:\>sqlcmd`  
  
 `1> _`  
  
 <span data-ttu-id="56dd5-163">Esto significa que se ha conectado a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y `sqlcmd` está listo para aceptar instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] y comandos de `sqlcmd` .</span><span class="sxs-lookup"><span data-stu-id="56dd5-163">This means you have connected to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and `sqlcmd` is now ready to accept [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and `sqlcmd` commands.</span></span> <span data-ttu-id="56dd5-164">El carácter de subrayado intermitente después de `1>` es el símbolo del sistema `sqlcmd` que marca la ubicación donde se mostrarán las instrucciones y los comandos que se escriban.</span><span class="sxs-lookup"><span data-stu-id="56dd5-164">The flashing underscore after the `1>` is the `sqlcmd` prompt that marks the location at which the statements and commands you type will be displayed.</span></span> <span data-ttu-id="56dd5-165">Ahora, escriba `USE AdventureWorks2012` y presione entrar y, a continuación, escriba `GO` y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="56dd5-165">Now, type `USE AdventureWorks2012` and press ENTER, and then type `GO` and press ENTER.</span></span> <span data-ttu-id="56dd5-166">El contenido de la ventana del símbolo del sistema será:</span><span class="sxs-lookup"><span data-stu-id="56dd5-166">The contents of the Command Prompt window will be:</span></span>  
  
 `sqlcmd`  
  
 `USE AdventureWorks2012;`  
  
 `GO`  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `Changed database context to 'AdventureWorks2012'.`  
  
 `1> _`  
  
 <span data-ttu-id="56dd5-167">Presionar ENTRAR después de escribir `USE AdventureWorks2012` indica a `sqlcmd` que inicie una línea nueva.</span><span class="sxs-lookup"><span data-stu-id="56dd5-167">Pressing ENTER after entering `USE AdventureWorks2012` signaled `sqlcmd` to start a new line.</span></span> <span data-ttu-id="56dd5-168">Al presionar ENTRAR, después de escribir `GO,` , se indicó que `sqlcmd` enviara la instrucción `USE AdventureWorks2012` a la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="56dd5-168">Pressing ENTER, after you type `GO,` signaled `sqlcmd` to send the `USE AdventureWorks2012` statement to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="56dd5-169">`sqlcmd` devuelve un mensaje para indicar que la instrucción `USE` se completó correctamente y muestra un nuevo símbolo del sistema `1>` como señal de que el usuario puede escribir una instrucción o un comando nuevos.</span><span class="sxs-lookup"><span data-stu-id="56dd5-169">`sqlcmd` then returned a message to indicate that the `USE` statement completed successfully and displayed a new `1>` prompt as a signal to enter a new statement or command.</span></span>  
  
 <span data-ttu-id="56dd5-170">En el ejemplo siguiente se muestra qué contiene la ventana del símbolo del sistema si escribe una instrucción `SELECT` , `GO` para ejecutar `SELECT`y `EXIT` para finalizar `sqlcmd`:</span><span class="sxs-lookup"><span data-stu-id="56dd5-170">The following example shows what the Command Prompt window contains if you type a `SELECT` statement, a `GO` to execute the `SELECT`, and an `EXIT` to exit `sqlcmd`:</span></span>  
  
 `sqlcmd`  
  
 `USE AdventureWorks2012;`  
  
 `GO`  
  
 `SELECT TOP (3) BusinessEntityID, FirstName, LastName`  
  
 `FROM Person.Person;`  
  
 `GO`  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `BusinessEntityID   FirstName                 LastName`  
  
 `----------- -------------------------------- -----------`  
  
 `1           Syed                             Abbas`  
  
 `2           Catherine                        Abel`  
  
 `3           Kim                              Abercrombie`  
  
 `(3 rows affected)`  
  
 `1> EXIT`  
  
 `C:\>`  
  
 <span data-ttu-id="56dd5-171">Las líneas posteriores a la línea `3> GO` son la salida de una instrucción `SELECT` .</span><span class="sxs-lookup"><span data-stu-id="56dd5-171">The lines after line `3> GO` are the output of a `SELECT` statement.</span></span> <span data-ttu-id="56dd5-172">Para generar una salida, `sqlcmd` restablece el símbolo de sistema `sqlcmd` y muestra `1>`.</span><span class="sxs-lookup"><span data-stu-id="56dd5-172">After you generate output, `sqlcmd` resets the `sqlcmd` prompt and displays `1>`.</span></span> <span data-ttu-id="56dd5-173">Después de escribir `EXIT` en la línea `1>`, la ventana del símbolo del sistema muestra la misma línea que se mostró cuando se la abrió por primera vez.</span><span class="sxs-lookup"><span data-stu-id="56dd5-173">After entering `EXIT` at line `1>`, the Command Prompt window displays the same line it did when you first opened it.</span></span> <span data-ttu-id="56dd5-174">Esto indica que `sqlcmd` ha finalizado la sesión.</span><span class="sxs-lookup"><span data-stu-id="56dd5-174">This indicates that `sqlcmd` has exited its session.</span></span> <span data-ttu-id="56dd5-175">Ahora ya puede cerrar la ventana del símbolo del sistema escribiendo otro comando `EXIT` .</span><span class="sxs-lookup"><span data-stu-id="56dd5-175">You can now close the Command Prompt window by typing another `EXIT` command.</span></span>  
  
## <a name="running-transact-sql-script-files-by-using-sqlcmd"></a><span data-ttu-id="56dd5-176">Ejecutar archivos de script Transact-SQL mediante sqlcmd</span><span class="sxs-lookup"><span data-stu-id="56dd5-176">Running Transact-SQL Script Files by Using sqlcmd</span></span>  
 <span data-ttu-id="56dd5-177">Puede usar `sqlcmd` para ejecutar los archivos de script de base de datos.</span><span class="sxs-lookup"><span data-stu-id="56dd5-177">You can use `sqlcmd` to execute database script files.</span></span> <span data-ttu-id="56dd5-178">Los archivos de script son archivos de texto que contienen una combinación de [!INCLUDE[tsql](../../includes/tsql-md.md)] instrucciones, `sqlcmd` comandos y variables de scripting.</span><span class="sxs-lookup"><span data-stu-id="56dd5-178">Script files are text files that contain a mix of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, `sqlcmd` commands, and scripting variables.</span></span> <span data-ttu-id="56dd5-179">Para obtener más información sobre cómo incluir variables en scripts, vea [Usar sqlcmd con variables de script](sqlcmd-use-with-scripting-variables.md).</span><span class="sxs-lookup"><span data-stu-id="56dd5-179">For more information about how to script variables, see [Use sqlcmd with Scripting Variables](sqlcmd-use-with-scripting-variables.md).</span></span> <span data-ttu-id="56dd5-180">`sqlcmd` funciona con las instrucciones, los comandos y las variables de scripting en un archivo de script de una forma parecida a como opera con instrucciones y comandos indicados de forma interactiva.</span><span class="sxs-lookup"><span data-stu-id="56dd5-180">`sqlcmd` works with the statements, commands, and scripting variables in a script file in a manner similar to how it works with statements and commands that are entered interactively.</span></span> <span data-ttu-id="56dd5-181">La diferencia principal es que `sqlcmd` lee el archivo de entrada sin pausas, en lugar de esperar a que un usuario indique las instrucciones, los comandos y las variables de scripting.</span><span class="sxs-lookup"><span data-stu-id="56dd5-181">The main difference is that `sqlcmd` reads through the input file without pause instead of waiting for a user to enter the statements, commands, and scripting variables.</span></span>  
  
 <span data-ttu-id="56dd5-182">Hay distintas maneras de crear archivos de script de base de datos:</span><span class="sxs-lookup"><span data-stu-id="56dd5-182">There are different ways to create database script files:</span></span>  
  
-   <span data-ttu-id="56dd5-183">Puede generar y depurar de forma interactiva un conjunto de instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]y, luego, guardar el contenido de la ventana Consulta como archivo de script.</span><span class="sxs-lookup"><span data-stu-id="56dd5-183">You can interactively build and debug a set of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then save the contents of the Query window as a script file.</span></span>  
  
-   <span data-ttu-id="56dd5-184">Puede crear un archivo de texto que contenga instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] usando un editor de texto, como el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="56dd5-184">You can create a text file that contains [!INCLUDE[tsql](../../includes/tsql-md.md)] statements by using a text editor, such as Notepad.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="56dd5-185">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="56dd5-185">Examples</span></span>  
  
### <a name="a-running-a-script-by-using-sqlcmd"></a><span data-ttu-id="56dd5-186">A.</span><span class="sxs-lookup"><span data-stu-id="56dd5-186">A.</span></span> <span data-ttu-id="56dd5-187">Ejecutar un script con sqlcmd</span><span class="sxs-lookup"><span data-stu-id="56dd5-187">Running a script by using sqlcmd</span></span>  
 <span data-ttu-id="56dd5-188">Inicie el Bloc de notas y escriba las siguientes instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="56dd5-188">Start Notepad, and type the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
 `USE AdventureWorks2012;`  
  
 `GO`  
  
 `SELECT TOP (3) BusinessEntityID, FirstName, LastName`  
  
 `FROM Person.Person;`  
  
 `GO`  
  
 <span data-ttu-id="56dd5-189">Cree una carpeta llamada `MyFolder` y guarde el script como el archivo `MyScript.sql` en la carpeta `C:\MyFolder`.</span><span class="sxs-lookup"><span data-stu-id="56dd5-189">Create a folder named `MyFolder` and then save the script as the file `MyScript.sql` in the folder `C:\MyFolder`.</span></span> <span data-ttu-id="56dd5-190">Escriba lo siguiente en el símbolo del sistema para ejecutar el script y coloque la salida en `MyOutput.txt` de `MyFolder`:</span><span class="sxs-lookup"><span data-stu-id="56dd5-190">Enter the following at the command prompt to run the script and put the output in `MyOutput.txt` in `MyFolder`:</span></span>  
  
 `sqlcmd -i C:\MyFolder\MyScript.sql -o C:\MyFolder\MyOutput.txt`  
  
 <span data-ttu-id="56dd5-191">Al mostrar el contenido de `MyOutput.txt` en el Bloc de notas, verá lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="56dd5-191">When you view the contents of `MyOutput.txt` in Notepad, you will see the following:</span></span>  
  
 `Changed database context to 'AdventureWorks2012'.`  
  
 `BusinessEntityID FirstName   LastName`  
  
 `---------------- ----------- -----------`  
  
 `1                Syed        Abbas`  
  
 `2                Catherine   Abel`  
  
 `3                Kim         Abercrombie`  
  
 `(3 rows affected)`  
  
### <a name="b-using-sqlcmd-with-a-dedicated-administrative-connection"></a><span data-ttu-id="56dd5-192">B.</span><span class="sxs-lookup"><span data-stu-id="56dd5-192">B.</span></span> <span data-ttu-id="56dd5-193">Usar sqlcmd con una conexión administrativa dedicada</span><span class="sxs-lookup"><span data-stu-id="56dd5-193">Using sqlcmd with a dedicated administrative connection</span></span>  
 <span data-ttu-id="56dd5-194">En el siguiente ejemplo, se utiliza `sqlcmd` para conectarse a un servidor que tiene un problema de bloqueo mediante la conexión de administrador dedicada (DAC).</span><span class="sxs-lookup"><span data-stu-id="56dd5-194">In the following example, `sqlcmd` is used to connect to a server that has a blocking problem by using the dedicated administrator connection (DAC).</span></span>  
  
 `C:\>sqlcmd -S ServerName -A`  
  
 `1> SELECT blocked FROM sys.dm_exec_requests WHERE blocked <> 0;`  
  
 `2> GO`  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `spid   blocked`  
  
 `------ -------`  
  
 `62       64`  
  
 `(1 rows affected)`  
  
 <span data-ttu-id="56dd5-195">Utilice `sqlcmd` para finalizar el proceso de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="56dd5-195">Use `sqlcmd` to end the blocking process.</span></span>  
  
 `1> KILL 64;`  
  
 `2> GO`  
  
### <a name="c-using-sqlcmd-to-execute-a-stored-procedure"></a><span data-ttu-id="56dd5-196">C.</span><span class="sxs-lookup"><span data-stu-id="56dd5-196">C.</span></span> <span data-ttu-id="56dd5-197">Usar sqlcmd para ejecutar un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="56dd5-197">Using sqlcmd to execute a stored procedure</span></span>  
 <span data-ttu-id="56dd5-198">En el ejemplo siguiente se muestra cómo ejecutar un procedimiento almacenado con `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="56dd5-198">The following example shows how to execute a stored procedure by using `sqlcmd`.</span></span> <span data-ttu-id="56dd5-199">Cree el siguiente procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="56dd5-199">Create the following stored procedure.</span></span>  
  
 `USE AdventureWorks2012;`  
  
 `IF OBJECT_ID ( ' dbo.ContactEmailAddress, 'P' ) IS NOT NULL`  
  
 `DROP PROCEDURE dbo.ContactEmailAddress;`  
  
 `GO`  
  
 `CREATE PROCEDURE dbo.ContactEmailAddress`  
  
 `(`  
  
 `@FirstName nvarchar(50)`  
  
 `,@LastName nvarchar(50)`  
  
 `)`  
  
 `AS`  
  
 `SET NOCOUNT ON`  
  
 `SELECT EmailAddress`  
  
 `FROM Person.Person`  
  
 `WHERE FirstName = @FirstName`  
  
 `AND LastName = @LastName;`  
  
 `SET NOCOUNT OFF`  
  
 <span data-ttu-id="56dd5-200">En el símbolo del sistema `sqlcmd` , escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="56dd5-200">At the `sqlcmd` prompt, enter the following:</span></span>  
  
 `C:\sqlcmd`  
  
 `1> :Setvar FirstName Gustavo`  
  
 `1> :Setvar LastName Achong`  
  
 `1> EXEC dbo.ContactEmailAddress $(Gustavo),$(Achong)`  
  
 `2> GO`  
  
 `EmailAddress`  
  
 `-----------------------------`  
  
 `gustavo0@adventure-works.com`  
  
### <a name="d-using-sqlcmd-for-database-maintenance"></a><span data-ttu-id="56dd5-201">D.</span><span class="sxs-lookup"><span data-stu-id="56dd5-201">D.</span></span> <span data-ttu-id="56dd5-202">Usar sqlcmd para mantenimiento de la base de datos</span><span class="sxs-lookup"><span data-stu-id="56dd5-202">Using sqlcmd for database maintenance</span></span>  
 <span data-ttu-id="56dd5-203">El siguiente ejemplo muestra cómo utilizar `sqlcmd` para una tarea de mantenimiento de base de datos.</span><span class="sxs-lookup"><span data-stu-id="56dd5-203">The following example shows how to use `sqlcmd` for a database maintenance task.</span></span> <span data-ttu-id="56dd5-204">Cree `C:\BackupTemplate.sql` con el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="56dd5-204">Create `C:\BackupTemplate.sql` with the following code.</span></span>  
  
 `USE master;`  
  
 `BACKUP DATABASE [$(db)] TO DISK='$(bakfile)';`  
  
 <span data-ttu-id="56dd5-205">En el símbolo del sistema `sqlcmd` , escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="56dd5-205">At the `sqlcmd` prompt, enter the following:</span></span>  
  
 `C:\ >sqlcmd`  
  
 `1> :connect <server>`  
  
 `Sqlcmd: Successfully connected to server <server>.`  
  
 `1> :setvar db msdb`  
  
 `1> :setvar bakfile c:\msdb.bak`  
  
 `1> :r c:\BackupTemplate.sql`  
  
 `2> GO`  
  
 `Changed database context to 'master'.`  
  
 `Processed 688 pages for database 'msdb', file 'MSDBData' on file 2.`  
  
 `Processed 5 pages for database 'msdb', file 'MSDBLog' on file 2.`  
  
 `BACKUP DATABASE successfully processed 693 pages in 0.725 seconds (7.830 MB/sec)`  
  
### <a name="e-using-sqlcmd-to-execute-code-on-multiple-instances"></a><span data-ttu-id="56dd5-206">E.</span><span class="sxs-lookup"><span data-stu-id="56dd5-206">E.</span></span> <span data-ttu-id="56dd5-207">Usar sqlcmd para ejecutar código en múltiples instancias</span><span class="sxs-lookup"><span data-stu-id="56dd5-207">Using sqlcmd to execute code on multiple instances</span></span>  
 <span data-ttu-id="56dd5-208">El siguiente código en un archivo muestra un script que se conecta a dos instancias.</span><span class="sxs-lookup"><span data-stu-id="56dd5-208">The following code in a file shows a script that connects to two instances.</span></span> <span data-ttu-id="56dd5-209">Observe el comando `GO` antes de la conexión a la segunda instancia.</span><span class="sxs-lookup"><span data-stu-id="56dd5-209">Notice the `GO` before the connection to the second instance.</span></span>  
  
 `:CONNECT <server>\,<instance1>`  
  
 `EXEC dbo.SomeProcedure`  
  
 `GO`  
  
 `:CONNECT <server>\,<instance2>`  
  
 `EXEC dbo.SomeProcedure`  
  
 `GO`  
  
### <a name="e-returning-xml-output"></a><span data-ttu-id="56dd5-210">E.</span><span class="sxs-lookup"><span data-stu-id="56dd5-210">E.</span></span> <span data-ttu-id="56dd5-211">Devolver salida XML</span><span class="sxs-lookup"><span data-stu-id="56dd5-211">Returning XML output</span></span>  
 <span data-ttu-id="56dd5-212">El siguiente ejemplo muestra cómo se devuelve la salida XML sin formato, en un flujo continuo.</span><span class="sxs-lookup"><span data-stu-id="56dd5-212">The following example shows how XML output is returned unformatted, in a continuous stream.</span></span>  
  
 `C:\>sqlcmd -d AdventureWorks2012`  
  
 `1> :XML ON`  
  
 `1> SELECT TOP 3 FirstName + ' ' + LastName + ', '`  
  
 `2> FROM Person.Person`  
  
 `3> GO`  
  
 `Syed Abbas, Catherine Abel, Kim Abercrombie,`  
  
### <a name="f-using-sqlcmd-in-a-windows-script-file"></a><span data-ttu-id="56dd5-213">F.</span><span class="sxs-lookup"><span data-stu-id="56dd5-213">F.</span></span> <span data-ttu-id="56dd5-214">Usar sqlcmd en un archivo de script de Windows</span><span class="sxs-lookup"><span data-stu-id="56dd5-214">Using sqlcmd in a Windows script file</span></span>  
 <span data-ttu-id="56dd5-215">Un `sqlcmd` comando como `sqlcmd -i C:\InputFile.txt -o C:\OutputFile.txt,` se puede ejecutar en un archivo. bat junto con VBScript.</span><span class="sxs-lookup"><span data-stu-id="56dd5-215">A `sqlcmd`command such as `sqlcmd -i C:\InputFile.txt -o C:\OutputFile.txt,` can be executed in a .bat file together with VBScript.</span></span> <span data-ttu-id="56dd5-216">En este caso, no se deben usar opciones interactivas.</span><span class="sxs-lookup"><span data-stu-id="56dd5-216">In this case, do not use interactive options.</span></span> <span data-ttu-id="56dd5-217">`sqlcmd` se debe instalar en el equipo que ejecuta el archivo .bat.</span><span class="sxs-lookup"><span data-stu-id="56dd5-217">`sqlcmd` must be installed on the computer that is executing the .bat file.</span></span>  
  
 <span data-ttu-id="56dd5-218">Primero, cree los siguientes cuatro archivos:</span><span class="sxs-lookup"><span data-stu-id="56dd5-218">First, create the following four files:</span></span>  
  
-   <span data-ttu-id="56dd5-219">C:\badscript.sql</span><span class="sxs-lookup"><span data-stu-id="56dd5-219">C:\badscript.sql</span></span>  
  
    ```  
    SELECT batch_1_this_is_an_error  
    GO  
    SELECT 'batch #2'  
    GO  
    ```  
  
-   <span data-ttu-id="56dd5-220">C:\goodscript.sql</span><span class="sxs-lookup"><span data-stu-id="56dd5-220">C:\goodscript.sql</span></span>  
  
    ```  
    SELECT 'batch #1'  
    GO  
    SELECT 'batch #2'  
    GO  
    ```  
  
-   <span data-ttu-id="56dd5-221">C:\returnvalue.sql</span><span class="sxs-lookup"><span data-stu-id="56dd5-221">C:\returnvalue.sql</span></span>  
  
    ```  
    :exit(select 100)  
    @echo off  
    C:\windowsscript.bat  
    @echo off  
  
    echo Running badscript.sql  
    sqlcmd -i badscript.sql -b -o out.log  
    if not errorlevel 1 goto next1  
    echo == An error occurred   
  
    :next1  
  
    echo Running goodscript.sql  
    sqlcmd -i goodscript.sql -b -o out.log  
    if not errorlevel 1 goto next2  
    echo == An error occurred   
  
    :next2  
    echo Running returnvalue.sql  
    sqlcmd -i returnvalue.sql -o out.log  
    echo SQLCMD returned %errorlevel% to the command shell  
  
    :exit  
    ```  
  
-   <span data-ttu-id="56dd5-222">C:\windowsscript.bat</span><span class="sxs-lookup"><span data-stu-id="56dd5-222">C:\windowsscript.bat</span></span>  
  
    ```  
    @echo off  
  
    echo Running badscript.sql  
    sqlcmd -i badscript.sql -b -o out.log  
    if not errorlevel 1 goto next1  
    echo == An error occurred   
  
    :next1  
  
    echo Running goodscript.sql  
    sqlcmd -i goodscript.sql -b -o out.log  
    if not errorlevel 1 goto next2  
    echo == An error occurred   
  
    :next2  
    echo Running returnvalue.sql  
    sqlcmd -i returnvalue.sql -o out.log  
    echo SQLCMD returned %errorlevel% to the command shell  
  
    :exit  
    ```  
  
 <span data-ttu-id="56dd5-223">Después, en el símbolo del sistema, ejecute `C:\windowsscript.bat`:</span><span class="sxs-lookup"><span data-stu-id="56dd5-223">Then, at the command prompt, run `C:\windowsscript.bat`:</span></span>  
  
 `C:\>windowsscript.bat`  
  
 `Running badscript.sql`  
  
 `== An error occurred`  
  
 `Running goodscript.sql`  
  
 `Running returnvalue.sql`  
  
 `SQLCMD returned 100 to the command shell`  
  
### <a name="g-using-sqlcmd-to-set-encryption-on-azure-sql-database"></a><span data-ttu-id="56dd5-224">G.</span><span class="sxs-lookup"><span data-stu-id="56dd5-224">G.</span></span> <span data-ttu-id="56dd5-225">Usar sqlcmd para establecer el cifrado en Azure SQL Database</span><span class="sxs-lookup"><span data-stu-id="56dd5-225">Using sqlcmd to set encryption on Azure SQL Database</span></span>  
 <span data-ttu-id="56dd5-226">`sqlcmd`Se puede ejecutar en una conexión a los [!INCLUDE[ssSDS](../../includes/sssds-md.md)] datos de para especificar el cifrado y la confianza del certificado.</span><span class="sxs-lookup"><span data-stu-id="56dd5-226">A `sqlcmd`can be executed on a connection to [!INCLUDE[ssSDS](../../includes/sssds-md.md)] data on to specify encryption and certificate trust.</span></span> <span data-ttu-id="56dd5-227">Hay disponibles dos opciones ' SQLCMD ' ' ':</span><span class="sxs-lookup"><span data-stu-id="56dd5-227">Two \`sqlcmd\`\`\`options are available:</span></span>  
  
-   <span data-ttu-id="56dd5-228">El modificador -N lo usa el cliente para solicitar una conexión cifrada.</span><span class="sxs-lookup"><span data-stu-id="56dd5-228">The -N switch is used by the client to request an encrypted connection.</span></span> <span data-ttu-id="56dd5-229">Esta opción es equivalente a ADO.net `ENCRYPT = true`.</span><span class="sxs-lookup"><span data-stu-id="56dd5-229">This option is equivalent to the ADO.net option `ENCRYPT = true`.</span></span>  
  
-   <span data-ttu-id="56dd5-230">El modificador -C lo emplea el cliente para configurarlo implícitamente para el certificado de servidor confiable y no validarlo.</span><span class="sxs-lookup"><span data-stu-id="56dd5-230">The -C switch is used by the client to configure it to implicitly the trust server certificate and not validate it.</span></span> <span data-ttu-id="56dd5-231">Esta opción es equivalente a ADO.net `TRUSTSERVERCERTIFICATE = true`.</span><span class="sxs-lookup"><span data-stu-id="56dd5-231">This option is equivalent to the ADO.net option `TRUSTSERVERCERTIFICATE = true`.</span></span>  
  
 <span data-ttu-id="56dd5-232">El servicio [!INCLUDE[ssSDS](../../includes/sssds-md.md)] no admite todas las opciones disponibles `SET` en una instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="56dd5-232">The [!INCLUDE[ssSDS](../../includes/sssds-md.md)] service does not support all the `SET` options available on a SQL Server instance.</span></span> <span data-ttu-id="56dd5-233">Las siguientes opciones producen un error cuando la opción `SET` correspondiente está establecida en `ON` u `OFF`:</span><span class="sxs-lookup"><span data-stu-id="56dd5-233">The following options throw an error when the corresponding `SET` option is set to `ON` or `OFF`:</span></span>  
  
-   <span data-ttu-id="56dd5-234">SET ANSI_DEFAULTS</span><span class="sxs-lookup"><span data-stu-id="56dd5-234">SET ANSI_DEFAULTS</span></span>  
  
-   <span data-ttu-id="56dd5-235">SET ANSI_NULLS</span><span class="sxs-lookup"><span data-stu-id="56dd5-235">SET ANSI_NULLS</span></span>  
  
-   <span data-ttu-id="56dd5-236">SET REMOTE_PROC_TRANSACTIONS</span><span class="sxs-lookup"><span data-stu-id="56dd5-236">SET REMOTE_PROC_TRANSACTIONS</span></span>  
  
-   <span data-ttu-id="56dd5-237">SET ANSI_NULL_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="56dd5-237">SET ANSI_NULL_DEFAULT</span></span>  
  
 <span data-ttu-id="56dd5-238">Las siguientes opciones de SET no producen excepciones pero no se pueden usar.</span><span class="sxs-lookup"><span data-stu-id="56dd5-238">The following SET options do not throw exceptions but cannot be used.</span></span> <span data-ttu-id="56dd5-239">Se han quedado en desuso:</span><span class="sxs-lookup"><span data-stu-id="56dd5-239">They are deprecated:</span></span>  
  
-   <span data-ttu-id="56dd5-240">SET CONCAT_NULL_YIELDS_NULL</span><span class="sxs-lookup"><span data-stu-id="56dd5-240">SET CONCAT_NULL_YIELDS_NULL</span></span>  
  
-   <span data-ttu-id="56dd5-241">SET ANSI_PADDING</span><span class="sxs-lookup"><span data-stu-id="56dd5-241">SET ANSI_PADDING</span></span>  
  
-   <span data-ttu-id="56dd5-242">SET QUERY_GOVERNOR_COST_LIMIT</span><span class="sxs-lookup"><span data-stu-id="56dd5-242">SET QUERY_GOVERNOR_COST_LIMIT</span></span>  
  
#### <a name="syntax"></a><span data-ttu-id="56dd5-243">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="56dd5-243">Syntax</span></span>  
 <span data-ttu-id="56dd5-244">En los siguientes ejemplos se hace referencia a los casos donde la configuración del proveedor Native Client [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] incluye: `ForceProtocolEncryption = False`, `Trust Server Certificate = No`</span><span class="sxs-lookup"><span data-stu-id="56dd5-244">The following examples refer to cases where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client Provider settings include: `ForceProtocolEncryption = False`, `Trust Server Certificate = No`</span></span>  
  
 <span data-ttu-id="56dd5-245">Conecte usando las credenciales de Windows y cifre la comunicación:</span><span class="sxs-lookup"><span data-stu-id="56dd5-245">Connect using Windows credentials and encrypt communication:</span></span>  
  
```  
SQLCMD -E -N  
  
```  
  
 <span data-ttu-id="56dd5-246">Conecte usando las credenciales de Windows y el certificado de servidor de confianza:</span><span class="sxs-lookup"><span data-stu-id="56dd5-246">Connect using Windows credentials and trust server certificate:</span></span>  
  
```  
SQLCMD -E -C  
  
```  
  
 <span data-ttu-id="56dd5-247">Conecte usando las credenciales de Windows, comunicación cifrada y el certificado de servidor de confianza:</span><span class="sxs-lookup"><span data-stu-id="56dd5-247">Connect using Windows credentials, encrypt communication and trust server certificate:</span></span>  
  
```  
SQLCMD -E -N -C  
  
```  
  
 <span data-ttu-id="56dd5-248">En los siguientes ejemplos se hace referencia a los casos donde la configuración del proveedor Native Client [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] incluye: `ForceProtocolEncryption = True`, `TrustServerCertificate = Yes`.</span><span class="sxs-lookup"><span data-stu-id="56dd5-248">The following examples refer to cases where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client Provider settings include: `ForceProtocolEncryption = True`, `TrustServerCertificate = Yes`.</span></span>  
  
 <span data-ttu-id="56dd5-249">Conecte usando las credenciales de Windows, comunicación cifrada y el certificado de servidor de confianza:</span><span class="sxs-lookup"><span data-stu-id="56dd5-249">Connect using Windows credentials, encrypt communication and trust server certificate:</span></span>  
  
```  
SQLCMD -E  
  
```  
  
 <span data-ttu-id="56dd5-250">Conecte usando las credenciales de Windows, comunicación cifrada y el certificado de servidor de confianza:</span><span class="sxs-lookup"><span data-stu-id="56dd5-250">Connect using Windows credentials, encrypt communication and trust server certificate:</span></span>  
  
```  
SQLCMD -E -N  
  
```  
  
 <span data-ttu-id="56dd5-251">Conecte usando las credenciales de Windows, comunicación cifrada y el certificado de servidor de confianza:</span><span class="sxs-lookup"><span data-stu-id="56dd5-251">Connect using Windows credentials, encrypt communication and trust server certificate:</span></span>  
  
```  
SQLCMD -E -T  
  
```  
  
 <span data-ttu-id="56dd5-252">Conecte usando las credenciales de Windows, comunicación cifrada y el certificado de servidor de confianza:</span><span class="sxs-lookup"><span data-stu-id="56dd5-252">Connect using Windows credentials, encrypt communication and trust server certificate:</span></span>  
  
```  
SQLCMD -E -N -C  
  
```  
  
 <span data-ttu-id="56dd5-253">Si el proveedor especifica `ForceProtocolEncryption = True` se habilita el cifrado aun cuando `Encrypt=No` en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="56dd5-253">If the provider specifies `ForceProtocolEncryption = True` then encryption is enabled even if `Encrypt=No` in the connection string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56dd5-254">Consulte también</span><span class="sxs-lookup"><span data-stu-id="56dd5-254">See Also</span></span>  
 <span data-ttu-id="56dd5-255">[sqlcmd (utilidad)](../../tools/sqlcmd-utility.md) </span><span class="sxs-lookup"><span data-stu-id="56dd5-255">[sqlcmd Utility](../../tools/sqlcmd-utility.md) </span></span>  
 <span data-ttu-id="56dd5-256">[Usar sqlcmd con variables de script](sqlcmd-use-with-scripting-variables.md) </span><span class="sxs-lookup"><span data-stu-id="56dd5-256">[Use sqlcmd with Scripting Variables](sqlcmd-use-with-scripting-variables.md) </span></span>  
 <span data-ttu-id="56dd5-257">[Modificar scripts SQLCMD con el Editor de consultas](edit-sqlcmd-scripts-with-query-editor.md) </span><span class="sxs-lookup"><span data-stu-id="56dd5-257">[Edit SQLCMD Scripts with Query Editor](edit-sqlcmd-scripts-with-query-editor.md) </span></span>  
 <span data-ttu-id="56dd5-258">[Administrar pasos de trabajo](../../ssms/agent/manage-job-steps.md) </span><span class="sxs-lookup"><span data-stu-id="56dd5-258">[Manage Job Steps](../../ssms/agent/manage-job-steps.md) </span></span>  
 [<span data-ttu-id="56dd5-259">Crear un paso de trabajo CmdExec</span><span class="sxs-lookup"><span data-stu-id="56dd5-259">Create a CmdExec Job Step</span></span>](../../ssms/agent/create-a-cmdexec-job-step.md)  
  
  
