---
title: osql (Utilidad) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- statements [SQL Server], command prompt
- QUIT command
- Transact-SQL statements, command prompt
- EXIT command
- operating systems [SQL Server], commands
- osql utility [SQL Server]
- stored procedures [SQL Server], command prompt
- scripts [SQL Server], command prompt
- RESET command
- GO command
- command prompt utilities [SQL Server], osql
- CTRL+C command
ms.assetid: cf530d9e-0609-4528-8975-ab8e08e40b9a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 95782afe0de8567781316e3478d04a090f968ed5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743766"
---
# <a name="osql-utility"></a><span data-ttu-id="119e8-102">osql (utilidad)</span><span class="sxs-lookup"><span data-stu-id="119e8-102">osql Utility</span></span>
  <span data-ttu-id="119e8-103">La utilidad **osql** permite especificar archivos de script, procedimientos del sistema e instrucciones de [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="119e8-103">The **osql** utility allows you to enter [!INCLUDE[tsql](../includes/tsql-md.md)] statements, system procedures, and script files.</span></span> <span data-ttu-id="119e8-104">Esta herramienta utiliza ODBC para comunicarse con el servidor.</span><span class="sxs-lookup"><span data-stu-id="119e8-104">This utility uses ODBC to communicate with the server.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="119e8-105">Esta característica se quitará en una versión futura de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="119e8-105">This feature will be removed in a future version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="119e8-106">Evite utilizar esta característica en los nuevos trabajos de programación y planee modificar las aplicaciones que actualmente la utilizan.</span><span class="sxs-lookup"><span data-stu-id="119e8-106">Avoid using this feature in new development work, and plan to modify applications that currently use the feature.</span></span> <span data-ttu-id="119e8-107">En su lugar, utilice **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="119e8-107">Use **sqlcmd** instead.</span></span> <span data-ttu-id="119e8-108">Para obtener más información, consulte [sqlcmd Utility](sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="119e8-108">For more information, see [sqlcmd Utility](sqlcmd-utility.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="119e8-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="119e8-109">Syntax</span></span>  
  
```  
  
      osql  
[-?] |  
[-L] |  
[  
  {  
     {-Ulogin_id [-Ppassword]} | -E }  
     [-Sserver_name[\instance_name]] [-Hwksta_name] [-ddb_name]  
     [-ltime_out] [-ttime_out] [-hheaders]  
     [-scol_separator] [-wcolumn_width] [-apacket_size]  
     [-e] [-I] [-D data_source_name]  
     [-ccmd_end] [-q "query"] [-Q"query"]  
     [-n] [-merror_level] [-r {0 | 1}]  
     [-iinput_file] [-ooutput_file] [-p]  
     [-b] [-u] [-R] [-O]  
]  
```  
  
## <a name="arguments"></a><span data-ttu-id="119e8-110">Argumentos</span><span class="sxs-lookup"><span data-stu-id="119e8-110">Arguments</span></span>  
 <span data-ttu-id="119e8-111">**-?**</span><span class="sxs-lookup"><span data-stu-id="119e8-111">**-?**</span></span>  
 <span data-ttu-id="119e8-112">Muestra el resumen de la sintaxis de los modificadores de **osql** .</span><span class="sxs-lookup"><span data-stu-id="119e8-112">Displays the syntax summary of **osql** switches.</span></span>  
  
 <span data-ttu-id="119e8-113">**-L**</span><span class="sxs-lookup"><span data-stu-id="119e8-113">**-L**</span></span>  
 <span data-ttu-id="119e8-114">Enumera los servidores configurados localmente y los nombres de los servidores que difunden en la red.</span><span class="sxs-lookup"><span data-stu-id="119e8-114">Lists the locally configured servers and the names of the servers broadcasting on the network.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="119e8-115">Debido a la naturaleza de la difusión en las redes, es posible que **osql** no reciba una respuesta a tiempo de todos los servidores.</span><span class="sxs-lookup"><span data-stu-id="119e8-115">Due to the nature of broadcasting on networks, **osql** may not receive a timely response from all servers.</span></span> <span data-ttu-id="119e8-116">Por lo tanto, la lista de servidores devuelta puede variar para cada invocación de esta opción.</span><span class="sxs-lookup"><span data-stu-id="119e8-116">Therefore the list of servers returned may vary for each invocation of this option.</span></span>  
  
 <span data-ttu-id="119e8-117">**-U** _login_id_</span><span class="sxs-lookup"><span data-stu-id="119e8-117">**-U** _login_id_</span></span>  
 <span data-ttu-id="119e8-118">Es el identificador de inicio de sesión del usuario.</span><span class="sxs-lookup"><span data-stu-id="119e8-118">Is the user login ID.</span></span> <span data-ttu-id="119e8-119">Los identificadores de inicio de sesión distinguen entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="119e8-119">Login IDs are case-sensitive.</span></span>  
  
 <span data-ttu-id="119e8-120">**-P** _password_</span><span class="sxs-lookup"><span data-stu-id="119e8-120">**-P** _password_</span></span>  
 <span data-ttu-id="119e8-121">Es una contraseña especificada por el usuario.</span><span class="sxs-lookup"><span data-stu-id="119e8-121">Is a user-specified password.</span></span> <span data-ttu-id="119e8-122">Si no se usa la opción **-P** , **osql** solicitará una contraseña.</span><span class="sxs-lookup"><span data-stu-id="119e8-122">If the **-P** option is not used, **osql** prompts for a password.</span></span> <span data-ttu-id="119e8-123">Si se usa la opción **-P** al final del símbolo del sistema sin una contraseña, **osql** usará la contraseña predeterminada (NULL).</span><span class="sxs-lookup"><span data-stu-id="119e8-123">If the **-P** option is used at the end of the command prompt without any password, **osql** uses the default password (NULL).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="119e8-124">No utilice una contraseña en blanco.</span><span class="sxs-lookup"><span data-stu-id="119e8-124">Do not use a blank password.</span></span> <span data-ttu-id="119e8-125">Utilice una contraseña segura.</span><span class="sxs-lookup"><span data-stu-id="119e8-125">Use a strong password.</span></span> <span data-ttu-id="119e8-126">Para obtener más información, consulte [Strong Passwords](../relational-databases/security/strong-passwords.md).</span><span class="sxs-lookup"><span data-stu-id="119e8-126">For more information, see [Strong Passwords](../relational-databases/security/strong-passwords.md).</span></span>  
  
 <span data-ttu-id="119e8-127">En las contraseñas se distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="119e8-127">Passwords are case-sensitive.</span></span>  
  
 <span data-ttu-id="119e8-128">La variable de entorno OSQLPASSWORD le permite establecer una contraseña predeterminada para la sesión actual.</span><span class="sxs-lookup"><span data-stu-id="119e8-128">The OSQLPASSWORD environment variable allows you to set a default password for the current session.</span></span> <span data-ttu-id="119e8-129">Por lo tanto, no tiene que codificar una contraseña en archivos por lotes.</span><span class="sxs-lookup"><span data-stu-id="119e8-129">Therefore, you do not have to hard code a password into batch files.</span></span>  
  
 <span data-ttu-id="119e8-130">Si no establece la contraseña con la opción **-P** , **osql** comprueba primero la variable OSQLPASSWORD.</span><span class="sxs-lookup"><span data-stu-id="119e8-130">If you do not specify a password with the **-P** option, **osql** first checks for the OSQLPASSWORD variable.</span></span> <span data-ttu-id="119e8-131">Si no hay ningún valor establecido, **osql** utiliza la contraseña predeterminada, NULL.</span><span class="sxs-lookup"><span data-stu-id="119e8-131">If no value is set, **osql** uses the default password, NULL.</span></span> <span data-ttu-id="119e8-132">En el ejemplo siguiente se especifica la variable OSQLPASSWORD en el símbolo del sistema y, a continuación, se tiene acceso a la utilidad **osql** :</span><span class="sxs-lookup"><span data-stu-id="119e8-132">The following example sets the OSQLPASSWORD variable at a command prompt and then accesses the **osql** utility:</span></span>  
  
```  
C:\>SET OSQLPASSWORD=abracadabra  
C:\>osql   
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="119e8-133">Para enmascarar la contraseña, no especifique la opción **-P** junto con la opción **-U** .</span><span class="sxs-lookup"><span data-stu-id="119e8-133">To mask your password, do not specify the **-P** option along with the **-U** option.</span></span> <span data-ttu-id="119e8-134">En su lugar, después de especificar **osql** con la opción **-U** y otros modificadores (sin especificar **-P**), pulse ENTRAR y **osql** le solicitará una contraseña.</span><span class="sxs-lookup"><span data-stu-id="119e8-134">Instead, after specifying **osql** along with the **-U** option and other switches (do not specify **-P**), press ENTER, and **osql** will prompt you for a password.</span></span> <span data-ttu-id="119e8-135">Este método garantiza que la contraseña se enmascare al especificarla.</span><span class="sxs-lookup"><span data-stu-id="119e8-135">This method ensures that your password will be masked when it is entered.</span></span>  
  
 <span data-ttu-id="119e8-136">**-E**</span><span class="sxs-lookup"><span data-stu-id="119e8-136">**-E**</span></span>  
 <span data-ttu-id="119e8-137">Utiliza una conexión de confianza en lugar de solicitar una contraseña.</span><span class="sxs-lookup"><span data-stu-id="119e8-137">Uses a trusted connection instead of requesting a password.</span></span>  
  
 <span data-ttu-id="119e8-138">**-S** _SERVER_NAME_[ **\\** _instance_name_]</span><span class="sxs-lookup"><span data-stu-id="119e8-138">**-S** _server_name_[ **\\**_instance_name_]</span></span>  
 <span data-ttu-id="119e8-139">Especifica la instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] a la que hay que conectarse.</span><span class="sxs-lookup"><span data-stu-id="119e8-139">Specifies the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to connect to.</span></span> <span data-ttu-id="119e8-140">Especifique *server_name* para conectar con la instancia predeterminada de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] en ese servidor.</span><span class="sxs-lookup"><span data-stu-id="119e8-140">Specify *server_name* to connect to the default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on that server.</span></span> <span data-ttu-id="119e8-141">Especifique _SERVER_NAME_ **\\** _instance_name_ para conectarse a una instancia con nombre de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] en ese servidor.</span><span class="sxs-lookup"><span data-stu-id="119e8-141">Specify _server_name_**\\**_instance_name_ to connect to a named instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on that server.</span></span> <span data-ttu-id="119e8-142">Si no se especifica ningún servidor, **osql** se conecta a la instancia predeterminada de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="119e8-142">If no server is specified, **osql** connects to the default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on the local computer.</span></span> <span data-ttu-id="119e8-143">Esta opción es necesaria cuando se ejecuta **osql** desde un equipo remoto conectado a la red.</span><span class="sxs-lookup"><span data-stu-id="119e8-143">This option is required when executing **osql** from a remote computer on the network.</span></span>  
  
 <span data-ttu-id="119e8-144">**-H** _wksta_name_</span><span class="sxs-lookup"><span data-stu-id="119e8-144">**-H** _wksta_name_</span></span>  
 <span data-ttu-id="119e8-145">Es el nombre de una estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="119e8-145">Is a workstation name.</span></span> <span data-ttu-id="119e8-146">El nombre de la estación de trabajo se almacena en **sysprocesses.hostname** y se muestra mediante **sp_who**.</span><span class="sxs-lookup"><span data-stu-id="119e8-146">The workstation name is stored in **sysprocesses.hostname** and is displayed by **sp_who**.</span></span> <span data-ttu-id="119e8-147">Si no se especifica esta opción, se supone el nombre actual del equipo.</span><span class="sxs-lookup"><span data-stu-id="119e8-147">If this option is not specified, the current computer name is assumed.</span></span>  
  
 <span data-ttu-id="119e8-148">**-d** _db_name_</span><span class="sxs-lookup"><span data-stu-id="119e8-148">**-d** _db_name_</span></span>  
 <span data-ttu-id="119e8-149">Ejecuta una instrucción USE *db_name* al iniciar **osql**.</span><span class="sxs-lookup"><span data-stu-id="119e8-149">Issues a USE *db_name* statement when **osql**is started.</span></span>  
  
 <span data-ttu-id="119e8-150">**-l** _time_out_</span><span class="sxs-lookup"><span data-stu-id="119e8-150">**-l** _time_out_</span></span>  
 <span data-ttu-id="119e8-151">Especifica el número de segundos que tienen que transcurrir antes de que un inicio de sesión de **osql** agote el tiempo de espera. El tiempo de espera predeterminado para el inicio de sesión de **osql** es de ocho segundos.</span><span class="sxs-lookup"><span data-stu-id="119e8-151">Specifies the number of seconds before an **osql** login times out. The default time-out for login to **osql** is eight seconds.</span></span>  
  
 <span data-ttu-id="119e8-152">**-t** _time_out_</span><span class="sxs-lookup"><span data-stu-id="119e8-152">**-t** _time_out_</span></span>  
 <span data-ttu-id="119e8-153">Especifica el número de segundos que tienen que transcurrir antes de que un comando exceda el tiempo de espera. Si no se especifica ningún valor para *time_out* , los comandos no tienen tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="119e8-153">Specifies the number of seconds before a command times out. If a *time_out* value is not specified, commands do not time out.</span></span>  
  
 <span data-ttu-id="119e8-154">**-h** _headers_</span><span class="sxs-lookup"><span data-stu-id="119e8-154">**-h** _headers_</span></span>  
 <span data-ttu-id="119e8-155">Especifica el número de filas que se van a imprimir entre los encabezados de las columnas.</span><span class="sxs-lookup"><span data-stu-id="119e8-155">Specifies the number of rows to print between column headings.</span></span> <span data-ttu-id="119e8-156">La opción predeterminada es imprimir los encabezados una vez para cada conjunto de resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="119e8-156">The default is to print headings one time for each set of query results.</span></span> <span data-ttu-id="119e8-157">Utilice -1 para especificar que no desea imprimir los encabezados.</span><span class="sxs-lookup"><span data-stu-id="119e8-157">Use -1 to specify that no headers will be printed.</span></span> <span data-ttu-id="119e8-158">Si usa -1, no debe dejar espacio entre el parámetro y el valor ( **-h-1**, no **-h -1**).</span><span class="sxs-lookup"><span data-stu-id="119e8-158">If -1 is used, there must be no space between the parameter and the setting (**-h-1**, not **-h -1**).</span></span>  
  
 <span data-ttu-id="119e8-159">**-s** _col_separator_</span><span class="sxs-lookup"><span data-stu-id="119e8-159">**-s** _col_separator_</span></span>  
 <span data-ttu-id="119e8-160">Especifica el carácter separador de columnas que, de forma predeterminada, es un espacio en blanco.</span><span class="sxs-lookup"><span data-stu-id="119e8-160">Specifies the column-separator character, which is a blank space by default.</span></span> <span data-ttu-id="119e8-161">Para usar caracteres que tienen un significado especial para el sistema operativo (por ejemplo, |; & \< > ), incluya el carácter entre comillas dobles (").</span><span class="sxs-lookup"><span data-stu-id="119e8-161">To use characters that have special meaning to the operating system (for example, | ; & \< >), enclose the character in double quotation marks (").</span></span>  
  
 <span data-ttu-id="119e8-162">**-w** _column_width_</span><span class="sxs-lookup"><span data-stu-id="119e8-162">**-w** _column_width_</span></span>  
 <span data-ttu-id="119e8-163">Permite al usuario ajustar el ancho de la pantalla para la salida.</span><span class="sxs-lookup"><span data-stu-id="119e8-163">Allows the user to set the screen width for output.</span></span> <span data-ttu-id="119e8-164">El valor predeterminado es 80 caracteres.</span><span class="sxs-lookup"><span data-stu-id="119e8-164">The default is 80 characters.</span></span> <span data-ttu-id="119e8-165">Cuando una línea de salida ha alcanzado el ancho máximo de pantalla, se divide en varias líneas.</span><span class="sxs-lookup"><span data-stu-id="119e8-165">When an output line has reached its maximum screen width, it is broken into multiple lines.</span></span>  
  
 <span data-ttu-id="119e8-166">**-a** _packet_size_</span><span class="sxs-lookup"><span data-stu-id="119e8-166">**-a** _packet_size_</span></span>  
 <span data-ttu-id="119e8-167">Permite solicitar un paquete de diferente tamaño.</span><span class="sxs-lookup"><span data-stu-id="119e8-167">Allows you to request a different-sized packet.</span></span> <span data-ttu-id="119e8-168">Los valores válidos de *packet_size* son de 512 a 65 535.</span><span class="sxs-lookup"><span data-stu-id="119e8-168">The valid values for *packet_size* are 512 through 65535.</span></span> <span data-ttu-id="119e8-169">El valor predeterminado de **osql** es el servidor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="119e8-169">The default value **osql** is the server default.</span></span> <span data-ttu-id="119e8-170">Si se aumenta el tamaño del paquete, se puede mejorar el rendimiento durante la ejecución de scripts grandes en las que hay muchas instrucciones SQL entre comandos GO.</span><span class="sxs-lookup"><span data-stu-id="119e8-170">Increased packet size can enhance performance on larger script execution where the amount of SQL statements between GO commands is substantial.</span></span> [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="119e8-171">indican que 8192 suele ser la configuración más rápida para operaciones de copia masiva.</span><span class="sxs-lookup"><span data-stu-id="119e8-171">testing indicates that 8192 is typically the fastest setting for bulk copy operations.</span></span> <span data-ttu-id="119e8-172">Se puede solicitar un tamaño mayor para los paquetes, pero **osql** adopta el valor predeterminado para el servidor si no puede cumplirse la solicitud.</span><span class="sxs-lookup"><span data-stu-id="119e8-172">A larger packet size can be requested, but **osql** defaults to the server default if the request cannot be granted.</span></span>  
  
 <span data-ttu-id="119e8-173">**-e**</span><span class="sxs-lookup"><span data-stu-id="119e8-173">**-e**</span></span>  
 <span data-ttu-id="119e8-174">Muestra lo escrito.</span><span class="sxs-lookup"><span data-stu-id="119e8-174">Echoes input.</span></span>  
  
 <span data-ttu-id="119e8-175">**-I**</span><span class="sxs-lookup"><span data-stu-id="119e8-175">**-I**</span></span>  
 <span data-ttu-id="119e8-176">Activa la opción de conexión QUOTED_IDENTIFIER.</span><span class="sxs-lookup"><span data-stu-id="119e8-176">Sets the QUOTED_IDENTIFIER connection option on.</span></span>  
  
 <span data-ttu-id="119e8-177">**-D** _data_source_name_</span><span class="sxs-lookup"><span data-stu-id="119e8-177">**-D** _data_source_name_</span></span>  
 <span data-ttu-id="119e8-178">Conecta a un origen de datos ODBC definido mediante el controlador ODBC de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="119e8-178">Connects to an ODBC data source that is defined using the ODBC driver for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="119e8-179">La conexión **osql** utiliza las opciones especificadas en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="119e8-179">The **osql** connection uses the options specified in the data source.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="119e8-180">Esta opción no funciona con los orígenes de datos definidos para otros controladores.</span><span class="sxs-lookup"><span data-stu-id="119e8-180">This option does not work with data sources defined for other drivers.</span></span>  
  
 <span data-ttu-id="119e8-181">**-c** _cmd_end_</span><span class="sxs-lookup"><span data-stu-id="119e8-181">**-c** _cmd_end_</span></span>  
 <span data-ttu-id="119e8-182">Especifica el terminador del comando.</span><span class="sxs-lookup"><span data-stu-id="119e8-182">Specifies the command terminator.</span></span> <span data-ttu-id="119e8-183">De forma predeterminada, los comandos se terminan y se envían a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] si se escribe GO en una línea aparte.</span><span class="sxs-lookup"><span data-stu-id="119e8-183">By default, commands are terminated and sent to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] by entering GO on a line by itself.</span></span> <span data-ttu-id="119e8-184">Cuando restablezca el terminador del comando, no utilice palabras reservadas de [!INCLUDE[tsql](../includes/tsql-md.md)] ni caracteres que tengan un significado especial para el sistema operativo, vayan o no precedidos por una barra diagonal inversa.</span><span class="sxs-lookup"><span data-stu-id="119e8-184">When you reset the command terminator, do not use [!INCLUDE[tsql](../includes/tsql-md.md)] reserved words or characters that have special meaning to the operating system, whether preceded by a backslash or not.</span></span>  
  
 <span data-ttu-id="119e8-185">**-q "** _query_ **"**</span><span class="sxs-lookup"><span data-stu-id="119e8-185">**-q "** _query_ **"**</span></span>  
 <span data-ttu-id="119e8-186">Ejecuta una consulta cuando se inicia **osql** , pero no sale de **osql** cuando se completa la consulta.</span><span class="sxs-lookup"><span data-stu-id="119e8-186">Executes a query when **osql** starts, but does not exit **osql** when the query completes.</span></span> <span data-ttu-id="119e8-187">(La instrucción de consulta no debe incluir GO.)</span><span class="sxs-lookup"><span data-stu-id="119e8-187">(Note that the query statement should not include GO).</span></span> <span data-ttu-id="119e8-188">Si emite una consulta desde un archivo por lotes, utilice %variables o %variables% de entorno.</span><span class="sxs-lookup"><span data-stu-id="119e8-188">If you issue a query from a batch file, use %variables, or environment %variables%.</span></span> <span data-ttu-id="119e8-189">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="119e8-189">For example:</span></span>  
  
```  
SET table=sys.objects  
osql -E -q "select name, object_id from %table%"  
```  
  
 <span data-ttu-id="119e8-190">Utilice comillas dobles para la consulta y comillas simples en los elementos que incruste en la consulta.</span><span class="sxs-lookup"><span data-stu-id="119e8-190">Use double quotation marks around the query and single quotation marks around anything embedded in the query.</span></span>  
  
 <span data-ttu-id="119e8-191">**-Q"** _query_ **"**</span><span class="sxs-lookup"><span data-stu-id="119e8-191">**-Q"** _query_ **"**</span></span>  
 <span data-ttu-id="119e8-192">Ejecuta una consulta y sale inmediatamente de **osql**.</span><span class="sxs-lookup"><span data-stu-id="119e8-192">Executes a query and immediately exits **osql**.</span></span> <span data-ttu-id="119e8-193">Utilice comillas dobles para la consulta y comillas simples en los elementos que incruste en la consulta.</span><span class="sxs-lookup"><span data-stu-id="119e8-193">Use double quotation marks around the query and single quotation marks around anything embedded in the query.</span></span>  
  
 <span data-ttu-id="119e8-194">**-n**</span><span class="sxs-lookup"><span data-stu-id="119e8-194">**-n**</span></span>  
 <span data-ttu-id="119e8-195">Quita la numeración y el símbolo del sistema (>) de las líneas de entrada.</span><span class="sxs-lookup"><span data-stu-id="119e8-195">Removes numbering and the prompt symbol (>) from input lines.</span></span>  
  
 <span data-ttu-id="119e8-196">**-m** _error_level_</span><span class="sxs-lookup"><span data-stu-id="119e8-196">**-m** _error_level_</span></span>  
 <span data-ttu-id="119e8-197">Personaliza la presentación de los mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="119e8-197">Customizes the display of error messages.</span></span> <span data-ttu-id="119e8-198">Se muestra el nivel de error, estado y número de mensaje en errores con el nivel de gravedad especificado o superior.</span><span class="sxs-lookup"><span data-stu-id="119e8-198">The message number, state, and error level are displayed for errors of the specified severity level or higher.</span></span> <span data-ttu-id="119e8-199">No se mostrarán errores que tengan un nivel de gravedad inferior al nivel especificado.</span><span class="sxs-lookup"><span data-stu-id="119e8-199">Nothing is displayed for errors of levels lower than the specified level.</span></span> <span data-ttu-id="119e8-200">Use **-1** para especificar que se devuelvan todos los encabezados con los mensajes, incluso con los mensajes informativos.</span><span class="sxs-lookup"><span data-stu-id="119e8-200">Use **-1** to specify that all headers are returned with messages, even informational messages.</span></span> <span data-ttu-id="119e8-201">Si usa **-1**, no debe dejar espacio entre el parámetro y los valores ( **-m-1**, no **-m -1**).</span><span class="sxs-lookup"><span data-stu-id="119e8-201">If using **-1**, there must be no space between the parameter and the setting (**-m-1**, not **-m -1**).</span></span>  
  
 <span data-ttu-id="119e8-202">**-r** { **0**| **1**}</span><span class="sxs-lookup"><span data-stu-id="119e8-202">**-r** { **0**| **1**}</span></span>  
 <span data-ttu-id="119e8-203">Redirige la salida del mensaje a la pantalla (**stderr**).</span><span class="sxs-lookup"><span data-stu-id="119e8-203">Redirects message output to the screen (**stderr**).</span></span> <span data-ttu-id="119e8-204">Si no especifica ningún parámetro, o si especifica **0**, solo se redirigirán los mensajes con nivel de gravedad 11 o superior.</span><span class="sxs-lookup"><span data-stu-id="119e8-204">If you do not specify a parameter, or if you specify **0**, only error messages with a severity level 11 or higher are redirected.</span></span> <span data-ttu-id="119e8-205">Si especifica **1**, toda salida de mensaje (incluida "print") se redirigirá.</span><span class="sxs-lookup"><span data-stu-id="119e8-205">If you specify **1**, all message output (including "print") is redirected.</span></span>  
  
 <span data-ttu-id="119e8-206">**-i** _input_file_</span><span class="sxs-lookup"><span data-stu-id="119e8-206">**-i** _input_file_</span></span>  
 <span data-ttu-id="119e8-207">Identifica el archivo que contiene un lote de instrucciones SQL o procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="119e8-207">Identifies the file that contains a batch of SQL statements or stored procedures.</span></span> <span data-ttu-id="119e8-208">Se puede usar el operador de comparación menor que ( **\<** ) en lugar de **-i**.</span><span class="sxs-lookup"><span data-stu-id="119e8-208">The less than (**\<**) comparison operator can be used in place of **-i**.</span></span>  
  
 <span data-ttu-id="119e8-209">**-o** _output_file_</span><span class="sxs-lookup"><span data-stu-id="119e8-209">**-o** _output_file_</span></span>  
 <span data-ttu-id="119e8-210">Identifica el archivo que recibe la salida de **osql**.</span><span class="sxs-lookup"><span data-stu-id="119e8-210">Identifies the file that receives output from **osql**.</span></span> <span data-ttu-id="119e8-211">Se puede usar el operador de comparación mayor que ( **>** ) en lugar de **-o**.</span><span class="sxs-lookup"><span data-stu-id="119e8-211">The greater than (**>**) comparison operator can be used in place of **-o**.</span></span>  
  
 <span data-ttu-id="119e8-212">Si *input_file* no está en formato Unicode y no se especifica **-u** , *output_file* se almacena en formato OEM.</span><span class="sxs-lookup"><span data-stu-id="119e8-212">If *input_file* is not Unicode and **-u** is not specified, *output_file* is stored in OEM format.</span></span> <span data-ttu-id="119e8-213">Si *input_file* está en formato Unicode o se especifica **-u** , *output_file* se almacena en formato Unicode.</span><span class="sxs-lookup"><span data-stu-id="119e8-213">If *input_file* is Unicode or **-u** is specified, *output_file* is stored in Unicode format.</span></span>  
  
 <span data-ttu-id="119e8-214">**-p**</span><span class="sxs-lookup"><span data-stu-id="119e8-214">**-p**</span></span>  
 <span data-ttu-id="119e8-215">Imprime las estadísticas de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="119e8-215">Prints performance statistics.</span></span>  
  
 <span data-ttu-id="119e8-216">**-b**</span><span class="sxs-lookup"><span data-stu-id="119e8-216">**-b**</span></span>  
 <span data-ttu-id="119e8-217">Especifica que **osql** se cierre y devuelva un valor de DOS ERRORLEVEL cuando se produce un error.</span><span class="sxs-lookup"><span data-stu-id="119e8-217">Specifies that **osql** exits and returns a DOS ERRORLEVEL value when an error occurs.</span></span> <span data-ttu-id="119e8-218">El valor que se devuelve a la variable DOS ERRORLEVEL es 1 cuando el mensaje de error de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tiene una gravedad superior a 11; de lo contrario, el valor devuelto es 0.</span><span class="sxs-lookup"><span data-stu-id="119e8-218">The value returned to the DOS ERRORLEVEL variable is 1 when the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] error message has a severity of 11 or greater; otherwise, the value returned is 0.</span></span> [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="119e8-219">Los archivos por lotes de MS-DOS pueden probar el valor de DOS ERRORLEVEL y tratar el error apropiadamente.</span><span class="sxs-lookup"><span data-stu-id="119e8-219">MS-DOS batch files can test the value of DOS ERRORLEVEL and handle the error appropriately.</span></span>  
  
 <span data-ttu-id="119e8-220">**-u**</span><span class="sxs-lookup"><span data-stu-id="119e8-220">**-u**</span></span>  
 <span data-ttu-id="119e8-221">Especifica que el archivo *output_file* se almacene en formato Unicode, independientemente del formato del archivo *input_file*.</span><span class="sxs-lookup"><span data-stu-id="119e8-221">Specifies that *output_file* is stored in Unicode format, regardless of the format of the *input_file*.</span></span>  
  
 <span data-ttu-id="119e8-222">**-R**</span><span class="sxs-lookup"><span data-stu-id="119e8-222">**-R**</span></span>  
 <span data-ttu-id="119e8-223">Especifica que el controlador ODBC de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] debe usar la configuración del cliente cuando realice conversiones de datos de moneda, fecha y hora a datos de caracteres.</span><span class="sxs-lookup"><span data-stu-id="119e8-223">Specifies that the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ODBC driver use client settings when converting currency, date, and time data to character data.</span></span>  
  
 <span data-ttu-id="119e8-224">**-O**</span><span class="sxs-lookup"><span data-stu-id="119e8-224">**-O**</span></span>  
 <span data-ttu-id="119e8-225">Especifica que se desactiven algunas características de **osql** para emular el comportamiento de versiones anteriores de **isql**.</span><span class="sxs-lookup"><span data-stu-id="119e8-225">Specifies that certain **osql** features be deactivated to match the behavior of earlier versions of **isql**.</span></span> <span data-ttu-id="119e8-226">Estas características están desactivadas:</span><span class="sxs-lookup"><span data-stu-id="119e8-226">These features are deactivated:</span></span>  
  
-   <span data-ttu-id="119e8-227">Procesamiento por lotes de final de archivo (EOF)</span><span class="sxs-lookup"><span data-stu-id="119e8-227">EOF batch processing</span></span>  
  
-   <span data-ttu-id="119e8-228">Escala automática de ancho de la consola</span><span class="sxs-lookup"><span data-stu-id="119e8-228">Automatic console width scaling</span></span>  
  
-   <span data-ttu-id="119e8-229">Mensajes detallados</span><span class="sxs-lookup"><span data-stu-id="119e8-229">Wide messages</span></span>  
  
 <span data-ttu-id="119e8-230">También establece -1 como valor predeterminado de ERRORLEVEL de DOS.</span><span class="sxs-lookup"><span data-stu-id="119e8-230">It also sets the default DOS ERRORLEVEL value to -1.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="119e8-231">Las opciones **-n**, **-O** y **-D** han dejado de admitirse en **osql**.</span><span class="sxs-lookup"><span data-stu-id="119e8-231">The **-n**, **-O** and **-D** options are no longer supported by **osql**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="119e8-232">Observaciones</span><span class="sxs-lookup"><span data-stu-id="119e8-232">Remarks</span></span>  
 <span data-ttu-id="119e8-233">La utilidad **osql** se inicia directamente desde el sistema operativo con las opciones en mayúsculas o en minúsculas, tal como se muestran aquí.</span><span class="sxs-lookup"><span data-stu-id="119e8-233">The **osql** utility is started directly from the operating system with the case-sensitive options listed here.</span></span> <span data-ttu-id="119e8-234">Después de iniciar **osql**acepta instrucciones SQL y las envía a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] de forma interactiva.</span><span class="sxs-lookup"><span data-stu-id="119e8-234">After **osql**starts, it accepts SQL statements and sends them to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] interactively.</span></span> <span data-ttu-id="119e8-235">Se da formato a los resultados y se muestran en la pantalla (**stdout**).</span><span class="sxs-lookup"><span data-stu-id="119e8-235">The results are formatted and displayed on the screen (**stdout**).</span></span> <span data-ttu-id="119e8-236">Utilice QUIT o EXIT para salir de **osql**.</span><span class="sxs-lookup"><span data-stu-id="119e8-236">Use QUIT or EXIT to exit from **osql**.</span></span>  
  
 <span data-ttu-id="119e8-237">Si no especifica un nombre de usuario al iniciar **osql**, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] comprueba las variables de entorno y las utiliza, por ejemplo, **osqluser = ( *`user`* )** o **osqlserver = ( *`server`* )**.</span><span class="sxs-lookup"><span data-stu-id="119e8-237">If you do not specify a user name when you start **osql**, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] checks for the environment variables and uses those, for example, **osqluser=(*`user`*)** or **osqlserver=(*`server`*)**.</span></span> <span data-ttu-id="119e8-238">Si no se establecen variables de entorno, se utilizará el nombre de usuario de la estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="119e8-238">If no environment variables are set, the workstation user name is used.</span></span> <span data-ttu-id="119e8-239">Si no especifica un servidor, se utilizará el nombre de la estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="119e8-239">If you do not specify a server, the name of the workstation is used.</span></span>  
  
 <span data-ttu-id="119e8-240">Si no se usan las opciones **-U** ni **-P** , [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] intenta conectarse usando el modo de autenticación de [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="119e8-240">If neither the **-U** or **-P** options are used, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] attempts to connect using [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows Authentication Mode.</span></span> <span data-ttu-id="119e8-241">La autenticación se basa en la cuenta de [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows del usuario que ejecuta **osql**.</span><span class="sxs-lookup"><span data-stu-id="119e8-241">Authentication is based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows account of the user running **osql**.</span></span>  
  
 <span data-ttu-id="119e8-242">La utilidad **osql** utiliza la API de ODBC.</span><span class="sxs-lookup"><span data-stu-id="119e8-242">The **osql** utility uses the ODBC API.</span></span> <span data-ttu-id="119e8-243">La utilidad utiliza la configuración predeterminada del controlador ODBC de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para las opciones de conexión ISO de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="119e8-243">The utility uses the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ODBC driver default settings for the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ISO connection options.</span></span> <span data-ttu-id="119e8-244">Para obtener más información, vea Efectos de las opciones de ANSI.</span><span class="sxs-lookup"><span data-stu-id="119e8-244">For more information, see Effects of ANSI Options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="119e8-245">La utilidad **osql** no admite los tipos de datos definidos por el usuario CLR.</span><span class="sxs-lookup"><span data-stu-id="119e8-245">The **osql** utility does not support CLR user-defined data types.</span></span> <span data-ttu-id="119e8-246">Para procesar estos tipos de datos, debe usar la utilidad **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="119e8-246">To process these data types, you must use the **sqlcmd** utility.</span></span> <span data-ttu-id="119e8-247">Para obtener más información, consulte [sqlcmd Utility](sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="119e8-247">For more information, see [sqlcmd Utility](sqlcmd-utility.md).</span></span>  
  
## <a name="osql-commands"></a><span data-ttu-id="119e8-248">Comandos OSQL</span><span class="sxs-lookup"><span data-stu-id="119e8-248">OSQL Commands</span></span>  
 <span data-ttu-id="119e8-249">Además de las instrucciones de [!INCLUDE[tsql](../includes/tsql-md.md)] de **osql**, los siguientes comandos también están disponibles.</span><span class="sxs-lookup"><span data-stu-id="119e8-249">In addition to [!INCLUDE[tsql](../includes/tsql-md.md)] statements within **osql**, these commands are also available.</span></span>  
  
|<span data-ttu-id="119e8-250">Get-Help</span><span class="sxs-lookup"><span data-stu-id="119e8-250">Command</span></span>|<span data-ttu-id="119e8-251">Descripción</span><span class="sxs-lookup"><span data-stu-id="119e8-251">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="119e8-252">GO</span><span class="sxs-lookup"><span data-stu-id="119e8-252">GO</span></span>|<span data-ttu-id="119e8-253">Ejecuta todas las instrucciones escritas después del último GO.</span><span class="sxs-lookup"><span data-stu-id="119e8-253">Executes all statements entered after the last GO.</span></span>|  
|<span data-ttu-id="119e8-254">RESET</span><span class="sxs-lookup"><span data-stu-id="119e8-254">RESET</span></span>|<span data-ttu-id="119e8-255">Borra cualquier instrucción que haya escrito.</span><span class="sxs-lookup"><span data-stu-id="119e8-255">Clears any statements you have entered.</span></span>|  
|<span data-ttu-id="119e8-256">QUIT o EXIT( )</span><span class="sxs-lookup"><span data-stu-id="119e8-256">QUIT or EXIT( )</span></span>|<span data-ttu-id="119e8-257">Sale de **osql**.</span><span class="sxs-lookup"><span data-stu-id="119e8-257">Exits from **osql**.</span></span>|  
|<span data-ttu-id="119e8-258">CTRL+C</span><span class="sxs-lookup"><span data-stu-id="119e8-258">CTRL+C</span></span>|<span data-ttu-id="119e8-259">Finaliza una consulta sin salir de **osql**.</span><span class="sxs-lookup"><span data-stu-id="119e8-259">Ends a query without exiting from **osql**.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="119e8-260">Los comandos !!</span><span class="sxs-lookup"><span data-stu-id="119e8-260">The !!</span></span> <span data-ttu-id="119e8-261">y ED ya no se admiten en **osql**.</span><span class="sxs-lookup"><span data-stu-id="119e8-261">and ED commands are no longer supported by **osql**.</span></span>  
  
 <span data-ttu-id="119e8-262">Los terminadores del comando GO (predeterminado), RESET EXIT, QUIT y CTRL+C solo se reconocen si aparecen al principio de una línea, inmediatamente después de símbolo del sistema de **osql** .</span><span class="sxs-lookup"><span data-stu-id="119e8-262">The command terminators GO (by default), RESET EXIT, QUIT, and CTRL+C, are recognized only if they appear at the beginning of a line, immediately following the **osql** prompt.</span></span>  
  
 <span data-ttu-id="119e8-263">GO marca tanto el final de un lote como la ejecución de cualquier instrucción de [!INCLUDE[tsql](../includes/tsql-md.md)] almacenada en caché.</span><span class="sxs-lookup"><span data-stu-id="119e8-263">GO signals both the end of a batch and the execution of any cached [!INCLUDE[tsql](../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="119e8-264">Cuando presione INTRO al final de cada línea de entrada, **osql** colocará en caché las instrucciones de esa línea.</span><span class="sxs-lookup"><span data-stu-id="119e8-264">When you press ENTER at the end of each input line, **osql** caches the statements on that line.</span></span> <span data-ttu-id="119e8-265">Al presionar ENTRAR después de escribir GO, todas las instrucciones almacenadas en la caché se enviarán como un lote a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="119e8-265">When you press ENTER after typing GO, all of the currently cached statements are sent as a batch to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="119e8-266">La utilidad **osql** actual funciona como si existiera una instrucción GO al final de cada script que se ejecuta, por lo que se ejecutarán todas las instrucciones del script.</span><span class="sxs-lookup"><span data-stu-id="119e8-266">The current **osql** utility works as if there is an implied GO at the end of any script executed, therefore all statements in the script execute.</span></span>  
  
 <span data-ttu-id="119e8-267">Finalice un comando; para ello, escriba una línea que comience con un terminador de comandos.</span><span class="sxs-lookup"><span data-stu-id="119e8-267">End a command by typing a line beginning with a command terminator.</span></span> <span data-ttu-id="119e8-268">Puede poner un entero después del terminador de comandos para especificar cuántas veces se debe ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="119e8-268">You can follow the command terminator with an integer to specify how many times the command should be run.</span></span> <span data-ttu-id="119e8-269">Por ejemplo, para ejecutar este comando 100 veces, escriba:</span><span class="sxs-lookup"><span data-stu-id="119e8-269">For example, to execute this command 100 times, type:</span></span>  
  
```  
SELECT x = 1  
GO 100  
```  
  
 <span data-ttu-id="119e8-270">Los resultados se imprimen una vez al final de la ejecución.</span><span class="sxs-lookup"><span data-stu-id="119e8-270">The results are printed once at the end of execution.</span></span> <span data-ttu-id="119e8-271">**osql** no acepta más de 1000 caracteres por línea.</span><span class="sxs-lookup"><span data-stu-id="119e8-271">**osql** does not accept more than 1,000 characters per line.</span></span> <span data-ttu-id="119e8-272">Las instrucciones grandes se deben distribuir en varias líneas.</span><span class="sxs-lookup"><span data-stu-id="119e8-272">Large statements should be spread across multiple lines.</span></span>  
  
 <span data-ttu-id="119e8-273">Pueden utilizarse las funciones de recuperación de Windows para recuperar y modificar las instrucciones **osql** .</span><span class="sxs-lookup"><span data-stu-id="119e8-273">The command recall facilities of Windows can be used to recall and modify **osql** statements.</span></span> <span data-ttu-id="119e8-274">El búfer de consulta existente se puede borrar si escribe RESET.</span><span class="sxs-lookup"><span data-stu-id="119e8-274">The existing query buffer can be cleared by typing RESET.</span></span>  
  
 <span data-ttu-id="119e8-275">Cuando se ejecutan procedimientos almacenados, **osql** imprime una línea en blanco entre cada conjunto de resultados de un lote.</span><span class="sxs-lookup"><span data-stu-id="119e8-275">When running stored procedures, **osql** prints a blank line between each set of results in a batch.</span></span> <span data-ttu-id="119e8-276">Además, el mensaje "0 filas afectadas" no aparece cuando no se aplica a la instrucción ejecutada.</span><span class="sxs-lookup"><span data-stu-id="119e8-276">In addition, the "0 rows affected" message does not appear when it does not apply to the statement executed.</span></span>  
  
## <a name="using-osql-interactively"></a><span data-ttu-id="119e8-277">Utilizar osql de forma interactiva</span><span class="sxs-lookup"><span data-stu-id="119e8-277">Using osql Interactively</span></span>  
 <span data-ttu-id="119e8-278">Para usar **osql** de forma interactiva, escriba el comando **osql** (y cualesquiera de las opciones) junto al símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="119e8-278">To use **osql** interactively, type the **osql** command (and any of the options) at a command prompt.</span></span>  
  
 <span data-ttu-id="119e8-279">Puede leer un archivo que contenga una consulta (como Sores.qry) para ejecutarse en **osql** si escribe un comando como este:</span><span class="sxs-lookup"><span data-stu-id="119e8-279">You can read in a file containing a query (such as Stores.qry) for execution by **osql** by typing a command similar to this:</span></span>  
  
```  
osql -E -i stores.qry  
```  
  
 <span data-ttu-id="119e8-280">Puede leer un archivo que contenga una consulta (como Titles.qry) y dirigir el resultado a otro archivo si escribe un comando similar a este:</span><span class="sxs-lookup"><span data-stu-id="119e8-280">You can read in a file containing a query (such as Titles.qry) and direct the results to another file by typing a command similar to this:</span></span>  
  
```  
osql -E -i titles.qry -o titles.res  
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="119e8-281">Siempre que sea posible, use la opción **-E**(conexión de confianza).</span><span class="sxs-lookup"><span data-stu-id="119e8-281">When possible, use the **-E**option (trusted connection).</span></span>  
  
 <span data-ttu-id="119e8-282">Al utilizar **osql** de forma interactiva, puede leer un archivo del sistema operativo en el búfer de comandos con **: r**_file_name_.</span><span class="sxs-lookup"><span data-stu-id="119e8-282">When using **osql** interactively, you can read an operating-system file into the command buffer with **:r**_file_name_.</span></span> <span data-ttu-id="119e8-283">De esta manera, se enviará el script SQL de *file_name* directamente al servidor como un lote único.</span><span class="sxs-lookup"><span data-stu-id="119e8-283">This sends the SQL script in *file_name* directly to the server as a single batch.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="119e8-284">Cuando se usa **osql**, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] trata el separador de lotes GO, si aparece en el archivo de script de SQL, como un error de sintaxis.</span><span class="sxs-lookup"><span data-stu-id="119e8-284">When using **osql**, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] treats the batch separator GO, if it appears in a SQL script file, as a syntax error.</span></span>  
  
## <a name="inserting-comments"></a><span data-ttu-id="119e8-285">Insertar comentarios</span><span class="sxs-lookup"><span data-stu-id="119e8-285">Inserting Comments</span></span>  
 <span data-ttu-id="119e8-286">Puede incluir comentarios en una instrucción Transact-SQL que vaya a enviarse a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] con **osql**.</span><span class="sxs-lookup"><span data-stu-id="119e8-286">You can include comments in a Transact-SQL statement submitted to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] by **osql**.</span></span> <span data-ttu-id="119e8-287">Se permiten dos estilos de comentario: -- y /\*...\*/.</span><span class="sxs-lookup"><span data-stu-id="119e8-287">Two types of commenting styles are allowed: -- and /\*...\*/.</span></span>  
  
## <a name="using-exit-to-return-results-in-osql"></a><span data-ttu-id="119e8-288">Utilizar EXIT para devolver resultados en osql</span><span class="sxs-lookup"><span data-stu-id="119e8-288">Using EXIT to Return Results in osql</span></span>  
 <span data-ttu-id="119e8-289">Puede utilizar el resultado de una instrucción SELECT como valor devuelto de **osql**.</span><span class="sxs-lookup"><span data-stu-id="119e8-289">You can use the result of a SELECT statement as the return value from **osql**.</span></span> <span data-ttu-id="119e8-290">Si es numérica, la primera columna de la última fila del resultado se convierte en un entero de 4 bytes (long).</span><span class="sxs-lookup"><span data-stu-id="119e8-290">If it is numeric, the last column of the last result row is converted to a 4-byte integer (long).</span></span> <span data-ttu-id="119e8-291">MS-DOS pasa el byte bajo al proceso primario o al nivel de errores del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="119e8-291">MS-DOS passes the low byte to the parent process or operating system error level.</span></span> <span data-ttu-id="119e8-292">Windows pasa el entero de 4 bytes completo.</span><span class="sxs-lookup"><span data-stu-id="119e8-292">Windows passes the entire 4-byte integer.</span></span> <span data-ttu-id="119e8-293">La sintaxis es:</span><span class="sxs-lookup"><span data-stu-id="119e8-293">The syntax is:</span></span>  
  
```  
EXIT ( < query > )  
```  
  
 <span data-ttu-id="119e8-294">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="119e8-294">For example:</span></span>  
  
```  
EXIT(SELECT @@ROWCOUNT)  
```  
  
 <span data-ttu-id="119e8-295">También puede incluir el parámetro EXIT como parte de un archivo por lotes.</span><span class="sxs-lookup"><span data-stu-id="119e8-295">You can also include the EXIT parameter as part of a batch file.</span></span> <span data-ttu-id="119e8-296">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="119e8-296">For example:</span></span>  
  
```  
osql -E -Q "EXIT(SELECT COUNT(*) FROM '%1')"  
```  
  
 <span data-ttu-id="119e8-297">La utilidad **osql** pasa al servidor todo lo que haya entre paréntesis **()** , exactamente como se haya escrito.</span><span class="sxs-lookup"><span data-stu-id="119e8-297">The **osql** utility passes everything between the parentheses **()** to the server exactly as entered.</span></span> <span data-ttu-id="119e8-298">Si un procedimiento almacenado del sistema selecciona un conjunto y devuelve un valor, solo se devuelve la selección.</span><span class="sxs-lookup"><span data-stu-id="119e8-298">If a stored system procedure selects a set and returns a value, only the selection is returned.</span></span> <span data-ttu-id="119e8-299">La instrucción EXIT **()** sin nada entre paréntesis ejecuta todo lo que le precede en el lote y luego sale sin ningún valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="119e8-299">The EXIT **()** statement with nothing between the parentheses executes everything preceding it in the batch and then exits with no return value.</span></span>  
  
 <span data-ttu-id="119e8-300">Hay cuatro formatos de EXIT:</span><span class="sxs-lookup"><span data-stu-id="119e8-300">There are four EXIT formats:</span></span>  
  
-   <span data-ttu-id="119e8-301">EXIT</span><span class="sxs-lookup"><span data-stu-id="119e8-301">EXIT</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="119e8-302">No ejecuta el lote; sale de forma inmediata y no devuelve ningún valor.</span><span class="sxs-lookup"><span data-stu-id="119e8-302">Does not execute the batch; quits immediately and returns no value.</span></span>  
  
-   <span data-ttu-id="119e8-303">EXIT **()**</span><span class="sxs-lookup"><span data-stu-id="119e8-303">EXIT **()**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="119e8-304">Ejecuta el lote y, a continuación, sale sin devolver ningún valor.</span><span class="sxs-lookup"><span data-stu-id="119e8-304">Executes the batch, and then quits and returns no value.</span></span>  
  
-   <span data-ttu-id="119e8-305">EXIT **( *`query`* )**</span><span class="sxs-lookup"><span data-stu-id="119e8-305">EXIT **(*`query`*)**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="119e8-306">Ejecuta el lote, incluida la consulta, y, a continuación, sale tras devolver el resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="119e8-306">Executes the batch, including the query, and then quits after returning the results of the query.</span></span>  
  
-   <span data-ttu-id="119e8-307">RAISERROR con un estado de 127</span><span class="sxs-lookup"><span data-stu-id="119e8-307">RAISERROR with a state of 127</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="119e8-308">Si utiliza RAISERROR en un script **osql** y se genera el estado 127, **osql** terminará y devolverá un id. de mensaje al cliente.</span><span class="sxs-lookup"><span data-stu-id="119e8-308">If RAISERROR is used within an **osql** script and a state of 127 is raised, **osql** will quit and return the message ID back to the client.</span></span> <span data-ttu-id="119e8-309">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="119e8-309">For example:</span></span>  
  
```  
RAISERROR(50001, 10, 127)  
```  
  
 <span data-ttu-id="119e8-310">Este error provocará la finalización del script **osql** y se devolverá al cliente un mensaje con el id. 50001.</span><span class="sxs-lookup"><span data-stu-id="119e8-310">This error will cause the **osql** script to end and the message ID 50001 will be returned to the client.</span></span>  
  
 <span data-ttu-id="119e8-311">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]reserva los valores devueltos -1 a -99; **osql** define los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="119e8-311">The return values -1 to -99 are reserved by [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]; **osql** defines these values:</span></span>  
  
-   <span data-ttu-id="119e8-312">-100</span><span class="sxs-lookup"><span data-stu-id="119e8-312">-100</span></span>  
  
     <span data-ttu-id="119e8-313">Error encontrado antes de seleccionar el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="119e8-313">Error encountered prior to selecting return value.</span></span>  
  
-   <span data-ttu-id="119e8-314">-101</span><span class="sxs-lookup"><span data-stu-id="119e8-314">-101</span></span>  
  
     <span data-ttu-id="119e8-315">No se encontró ninguna fila al seleccionar el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="119e8-315">No rows found when selecting return value.</span></span>  
  
-   <span data-ttu-id="119e8-316">-102</span><span class="sxs-lookup"><span data-stu-id="119e8-316">-102</span></span>  
  
     <span data-ttu-id="119e8-317">Error de conversión al seleccionar el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="119e8-317">Conversion error occurred when selecting return value.</span></span>  
  
## <a name="displaying-money-and-smallmoney-data-types"></a><span data-ttu-id="119e8-318">Mostrar tipos de datos money y smallmoney</span><span class="sxs-lookup"><span data-stu-id="119e8-318">Displaying money and smallmoney Data Types</span></span>  
 <span data-ttu-id="119e8-319">**osql** muestra los `money` `smallmoney` tipos de datos y con dos decimales, aunque [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] almacena internamente el valor con cuatro posiciones decimales.</span><span class="sxs-lookup"><span data-stu-id="119e8-319">**osql** displays the `money` and `smallmoney` data types with two decimal places although [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] stores the value internally with four decimal places.</span></span> <span data-ttu-id="119e8-320">Observe el ejemplo:</span><span class="sxs-lookup"><span data-stu-id="119e8-320">Consider the example:</span></span>  
  
```  
SELECT CAST(CAST(10.3496 AS money) AS decimal(6, 4))  
GO  
```  
  
 <span data-ttu-id="119e8-321">Esta instrucción da como resultado `10.3496`, que indica que el valor se almacena con todos los decimales intactos.</span><span class="sxs-lookup"><span data-stu-id="119e8-321">This statement produces a result of `10.3496`, which indicates that the value is stored with all decimal places intact.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="119e8-322">Consulte también</span><span class="sxs-lookup"><span data-stu-id="119e8-322">See Also</span></span>  
 <span data-ttu-id="119e8-323">[Comentario &#40;MDX&#41;](/sql/mdx/comment-mdx) </span><span class="sxs-lookup"><span data-stu-id="119e8-323">[Comment &#40;MDX&#41;](/sql/mdx/comment-mdx) </span></span>  
 <span data-ttu-id="119e8-324">[-- &#40;Comentario&#41; &#40;MDX&#41;](/sql/mdx/comment-mdx) </span><span class="sxs-lookup"><span data-stu-id="119e8-324">[-- &#40;Comment&#41; &#40;MDX&#41;](/sql/mdx/comment-mdx) </span></span>  
 <span data-ttu-id="119e8-325">[CAST y CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="119e8-325">[CAST and CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql) </span></span>  
 [<span data-ttu-id="119e8-326">RAISERROR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="119e8-326">RAISERROR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/raiserror-transact-sql)  
  
  
