---
title: Configuración de SQL Server en SMO | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- SQL Server, configuring
- configuration options [SMO]
ms.assetid: 0a372643-15cb-45a7-8665-04f1215df8ed
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6da1bca0aec650c01553b42bc2f3628b0bf7282e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749221"
---
# <a name="configuring-sql-server-in-smo"></a><span data-ttu-id="c4ea7-102">Configurar SQL Server en SMO</span><span class="sxs-lookup"><span data-stu-id="c4ea7-102">Configuring SQL Server in SMO</span></span>
  <span data-ttu-id="c4ea7-103">En SMO, el <xref:Microsoft.SqlServer.Management.Smo.Information> objeto, el objeto <xref:Microsoft.SqlServer.Management.Smo.Settings> , el <xref:Microsoft.SqlServer.Management.Smo.UserOptions> objeto y el <xref:Microsoft.SqlServer.Management.Smo.Configuration> objeto contienen valores de configuración e información para la instancia de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c4ea7-103">In SMO, the <xref:Microsoft.SqlServer.Management.Smo.Information> object, the <xref:Microsoft.SqlServer.Management.Smo.Settings> object, the <xref:Microsoft.SqlServer.Management.Smo.UserOptions> object, and the <xref:Microsoft.SqlServer.Management.Smo.Configuration> object contain settings and information for the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="c4ea7-104">tiene numerosas propiedades que describen el comportamiento de la instancia instalada.</span><span class="sxs-lookup"><span data-stu-id="c4ea7-104">has numerous properties that describe the behavior of the installed instance.</span></span> <span data-ttu-id="c4ea7-105">Las propiedades describen las opciones de inicio, los valores predeterminados, archivos y directorios del servidor, la información del procesador y del sistema, el producto y las versiones, la información de conexión, las opciones de memoria, la selección del idioma y de intercalación y el modo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="c4ea7-105">The properties describe the startup options, the server defaults, files and directories, system and processor information, product and versions, connection information, memory options, language and collation selections, and the authentication mode.</span></span>  
  
## <a name="sql-server-configuration"></a><span data-ttu-id="c4ea7-106">Configurar SQL Server</span><span class="sxs-lookup"><span data-stu-id="c4ea7-106">SQL Server Configuration</span></span>  
 <span data-ttu-id="c4ea7-107">Las propiedades del objeto <xref:Microsoft.SqlServer.Management.Smo.Information> contienen información sobre la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], como el procesador y plataforma.</span><span class="sxs-lookup"><span data-stu-id="c4ea7-107">The <xref:Microsoft.SqlServer.Management.Smo.Information> object properties contain information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], such as processor and platform.</span></span>  
  
 <span data-ttu-id="c4ea7-108">Las propiedades del objeto <xref:Microsoft.SqlServer.Management.Smo.Settings> contienen información sobre la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c4ea7-108">The <xref:Microsoft.SqlServer.Management.Smo.Settings> object properties contain information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c4ea7-109">Se pueden modificar el archivo y directorio predeterminados de la base de datos además del perfil de correo y la cuenta del servidor.</span><span class="sxs-lookup"><span data-stu-id="c4ea7-109">The default database file and directory can be modified in addition to the Mail Profile and the Server Account.</span></span> <span data-ttu-id="c4ea7-110">Estas propiedades permanecen para la duración de la conexión.</span><span class="sxs-lookup"><span data-stu-id="c4ea7-110">These properties remain for the duration of the connection.</span></span>  
  
 <span data-ttu-id="c4ea7-111">Las propiedades del objeto <xref:Microsoft.SqlServer.Management.Smo.UserOptions> contienen información sobre el comportamiento de las conexiones actuales relacionado con la aritmética, los estándares ANSI y las transacciones.</span><span class="sxs-lookup"><span data-stu-id="c4ea7-111">The <xref:Microsoft.SqlServer.Management.Smo.UserOptions> object properties contain information about the current connections behavior relating to arithmetic, ANSI standards, and transactions.</span></span>  
  
 <span data-ttu-id="c4ea7-112">Hay también un conjunto de opciones de configuración que está representado por el objeto <xref:Microsoft.SqlServer.Management.Smo.Configuration>.</span><span class="sxs-lookup"><span data-stu-id="c4ea7-112">There is also a set of configuration options that is represented by the <xref:Microsoft.SqlServer.Management.Smo.Configuration> object.</span></span> <span data-ttu-id="c4ea7-113">Contiene un conjunto de propiedades que representan las opciones que pueden ser modificadas por el procedimiento almacenado `sp_configure`.</span><span class="sxs-lookup"><span data-stu-id="c4ea7-113">It contains a set of properties that represent the options that can be modified by the `sp_configure` stored procedure.</span></span> <span data-ttu-id="c4ea7-114">Opciones como **aumento de prioridad**, **intervalo de recuperación** y tamaño de paquete de **red**controlan el rendimiento de la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c4ea7-114">Options such as **Priority Boost**, **Recovery Interval** and **Network Packet Size**control the performance of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c4ea7-115">Se pueden cambiar muchas de estas opciones dinámicamente, pero en algunos casos el valor se configura primero y a continuación se cambia cuando se reinicia la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c4ea7-115">Many of these options can be changed dynamically, but in some cases the value is first configured and then changed when the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is restarted.</span></span>  
  
 <span data-ttu-id="c4ea7-116">Hay una propiedad del objeto <xref:Microsoft.SqlServer.Management.Smo.Configuration> para cada opción de configuración.</span><span class="sxs-lookup"><span data-stu-id="c4ea7-116">There is a <xref:Microsoft.SqlServer.Management.Smo.Configuration> object property for every configuration option.</span></span> <span data-ttu-id="c4ea7-117">Con el objeto <xref:Microsoft.SqlServer.Management.Smo.ConfigProperty> puede modificar la configuración global.</span><span class="sxs-lookup"><span data-stu-id="c4ea7-117">Using the <xref:Microsoft.SqlServer.Management.Smo.ConfigProperty> object you can modify the global configuration setting.</span></span> <span data-ttu-id="c4ea7-118">Muchas propiedades tienen valores máximos y mínimos que también se almacenan como propiedades de <xref:Microsoft.SqlServer.Management.Smo.ConfigProperty>.</span><span class="sxs-lookup"><span data-stu-id="c4ea7-118">Many properties have maximum and minimum values that are also stored as <xref:Microsoft.SqlServer.Management.Smo.ConfigProperty> properties.</span></span> <span data-ttu-id="c4ea7-119">Estas propiedades requieren <xref:Microsoft.SqlServer.Management.Smo.ConfigurationBase.Alter%2A> que el método confirme el cambio en la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c4ea7-119">These properties require the <xref:Microsoft.SqlServer.Management.Smo.ConfigurationBase.Alter%2A> method to commit the change to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="c4ea7-120">El administrador del sistema debe cambiar todas las opciones de configuración en el objeto <xref:Microsoft.SqlServer.Management.Smo.Configuration>.</span><span class="sxs-lookup"><span data-stu-id="c4ea7-120">All of the configuration options in the <xref:Microsoft.SqlServer.Management.Smo.Configuration> object must be changed by the system administrator.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="c4ea7-121">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c4ea7-121">Examples</span></span>  
 <span data-ttu-id="c4ea7-122">Para los siguientes ejemplos de código, deberá seleccionar el entorno de programación, la plantilla de programación y el lenguaje de programación en los que crear su aplicación.</span><span class="sxs-lookup"><span data-stu-id="c4ea7-122">For the following code examples, you will have to select the programming environment, programming template and the programming language to create your application.</span></span> <span data-ttu-id="c4ea7-123">Para obtener más información, vea [crear un proyecto de Visual Basic SMO en Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) y [crear un proyecto de Visual C&#35; SMO en Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="c4ea7-123">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) and [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="modifying-sql-server-configuration-options-in-visual-basic"></a><span data-ttu-id="c4ea7-124">Modificar las opciones de configuración de SQL Server en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c4ea7-124">Modifying SQL Server Configuration Options in Visual Basic</span></span>  
 <span data-ttu-id="c4ea7-125">En el ejemplo de código se muestra cómo actualizar una opción de configuración en Visual Basic .NET.</span><span class="sxs-lookup"><span data-stu-id="c4ea7-125">The code example shows how to update a configuration option in Visual Basic .NET.</span></span> <span data-ttu-id="c4ea7-126">También recupera y muestra información sobre los valores máximos y mínimos para la opción de configuración especificada.</span><span class="sxs-lookup"><span data-stu-id="c4ea7-126">It also retrieves and displays information about maximum and minimum values for the specified configuration option.</span></span> <span data-ttu-id="c4ea7-127">Finalmente, el programa notifica al usuario si la modificación se ha realizado dinámicamente o si se almacena hasta que se reinicie la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c4ea7-127">Finally, the program informs the user if the change has been made dynamically, or if it is stored until the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is restarted.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBConfigure2](SMO How to#SMO_VBConfigure2)]  -->  
  
## <a name="modifying-sql-server-settings-in-visual-basic"></a><span data-ttu-id="c4ea7-128">Modificar la configuración de SQL Server en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c4ea7-128">Modifying SQL Server Settings in Visual Basic</span></span>  
 <span data-ttu-id="c4ea7-129">En el ejemplo de código se muestra información sobre la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en <xref:Microsoft.SqlServer.Management.Smo.Information> y <xref:Microsoft.SqlServer.Management.Smo.Settings> , y se modifica la configuración de <xref:Microsoft.SqlServer.Management.Smo.Settings> <xref:Microsoft.SqlServer.Management.Smo.UserOptions> las propiedades del objeto y.</span><span class="sxs-lookup"><span data-stu-id="c4ea7-129">The code example displays information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in <xref:Microsoft.SqlServer.Management.Smo.Information> and <xref:Microsoft.SqlServer.Management.Smo.Settings>, and modifies settings in <xref:Microsoft.SqlServer.Management.Smo.Settings> and <xref:Microsoft.SqlServer.Management.Smo.UserOptions>object properties.</span></span>  
  
 <span data-ttu-id="c4ea7-130">En el ejemplo el objeto <xref:Microsoft.SqlServer.Management.Smo.UserOptions> y el objeto <xref:Microsoft.SqlServer.Management.Smo.Settings> tienen un método <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A>.</span><span class="sxs-lookup"><span data-stu-id="c4ea7-130">In the example the <xref:Microsoft.SqlServer.Management.Smo.UserOptions> object and the <xref:Microsoft.SqlServer.Management.Smo.Settings> object both have an <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> method.</span></span> <span data-ttu-id="c4ea7-131">Puede ejecutar los métodos <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> individualmente para éstos.</span><span class="sxs-lookup"><span data-stu-id="c4ea7-131">You can run the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> methods for these individually.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBConfigure1](SMO How to#SMO_VBConfigure1)]  -->  
  
## <a name="modifying-sql-server-settings-in-visual-c"></a><span data-ttu-id="c4ea7-132">Modificar la configuración de SQL Server en Visual C#</span><span class="sxs-lookup"><span data-stu-id="c4ea7-132">Modifying SQL Server Settings in Visual C#</span></span>  
 <span data-ttu-id="c4ea7-133">En el ejemplo de código se muestra información sobre la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en <xref:Microsoft.SqlServer.Management.Smo.Information> y <xref:Microsoft.SqlServer.Management.Smo.Settings> , y se modifica la configuración de <xref:Microsoft.SqlServer.Management.Smo.Settings> <xref:Microsoft.SqlServer.Management.Smo.UserOptions> las propiedades del objeto y.</span><span class="sxs-lookup"><span data-stu-id="c4ea7-133">The code example displays information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in <xref:Microsoft.SqlServer.Management.Smo.Information> and <xref:Microsoft.SqlServer.Management.Smo.Settings>, and modifies settings in <xref:Microsoft.SqlServer.Management.Smo.Settings> and <xref:Microsoft.SqlServer.Management.Smo.UserOptions>object properties.</span></span>  
  
 <span data-ttu-id="c4ea7-134">En el ejemplo el objeto <xref:Microsoft.SqlServer.Management.Smo.UserOptions> y el objeto <xref:Microsoft.SqlServer.Management.Smo.Settings> tienen un método <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A>.</span><span class="sxs-lookup"><span data-stu-id="c4ea7-134">In the example the <xref:Microsoft.SqlServer.Management.Smo.UserOptions> object and the <xref:Microsoft.SqlServer.Management.Smo.Settings> object both have an <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> method.</span></span> <span data-ttu-id="c4ea7-135">Puede ejecutar los métodos <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> individualmente para éstos.</span><span class="sxs-lookup"><span data-stu-id="c4ea7-135">You can run the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> methods for these individually.</span></span>  
  
 `//Connect to the local, default instance of SQL Server.`  
  
```csharp
{  
            Server srv = new Server();  
            //Display all the configuration options.   
  
            foreach (ConfigProperty p in srv.Configuration.Properties)  
            {  
                Console.WriteLine(p.DisplayName);  
            }  
            Console.WriteLine("There are " + srv.Configuration.Properties.Count.ToString() + " configuration options.");  
            //Display the maximum and minimum values for ShowAdvancedOptions.   
            int min = 0;  
            int max = 0;  
            min = srv.Configuration.ShowAdvancedOptions.Minimum;  
            max = srv.Configuration.ShowAdvancedOptions.Maximum;  
            Console.WriteLine("Minimum and Maximum values are " + min + " and " + max + ".");  
            //Modify the value of ShowAdvancedOptions and run the Alter method.   
            srv.Configuration.ShowAdvancedOptions.ConfigValue = 0;  
            srv.Configuration.Alter();  
            //Display when the change takes place according to the IsDynamic property.   
            if (srv.Configuration.ShowAdvancedOptions.IsDynamic == true)  
            {  
                Console.WriteLine("Configuration option has been updated.");  
            }  
            else  
            {  
                Console.WriteLine("Configuration option will be updated when SQL Server is restarted.");  
            }  
        }  
```  
  
## <a name="modifying-sql-server-settings-in-powershell"></a><span data-ttu-id="c4ea7-136">Modificar la configuración de SQL Server en PowerShell</span><span class="sxs-lookup"><span data-stu-id="c4ea7-136">Modifying SQL Server Settings in PowerShell</span></span>  
 <span data-ttu-id="c4ea7-137">En el ejemplo de código se muestra información sobre la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en <xref:Microsoft.SqlServer.Management.Smo.Information> y <xref:Microsoft.SqlServer.Management.Smo.Settings> , y se modifica la configuración de <xref:Microsoft.SqlServer.Management.Smo.Settings> <xref:Microsoft.SqlServer.Management.Smo.UserOptions> las propiedades del objeto y.</span><span class="sxs-lookup"><span data-stu-id="c4ea7-137">The code example displays information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in <xref:Microsoft.SqlServer.Management.Smo.Information> and <xref:Microsoft.SqlServer.Management.Smo.Settings>, and modifies settings in <xref:Microsoft.SqlServer.Management.Smo.Settings> and <xref:Microsoft.SqlServer.Management.Smo.UserOptions>object properties.</span></span>  
  
 <span data-ttu-id="c4ea7-138">En el ejemplo el objeto <xref:Microsoft.SqlServer.Management.Smo.UserOptions> y el objeto <xref:Microsoft.SqlServer.Management.Smo.Settings> tienen un método <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A>.</span><span class="sxs-lookup"><span data-stu-id="c4ea7-138">In the example the <xref:Microsoft.SqlServer.Management.Smo.UserOptions> object and the <xref:Microsoft.SqlServer.Management.Smo.Settings> object both have an <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> method.</span></span> <span data-ttu-id="c4ea7-139">Puede ejecutar los métodos <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> individualmente para éstos.</span><span class="sxs-lookup"><span data-stu-id="c4ea7-139">You can run the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> methods for these individually.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\  
$srv = Get-Item default  
  
#Display information about the instance of SQL Server in Information and Settings.  
"OS Version = " + $srv.Information.OSVersion  
"State = "+ $srv.Settings.State.ToString()  
  
#Display information specific to the current user in UserOptions.  
"Quoted Identifier support = " + $srv.UserOptions.QuotedIdentifier  
  
#Modify server settings in Settings.  
$srv.Settings.LoginMode = [Microsoft.SqlServer.Management.SMO.ServerLoginMode]::Integrated  
  
#Modify settings specific to the current connection in UserOptions.  
$srv.UserOptions.AbortOnArithmeticErrors = $true  
  
#Run the Alter method to make the changes on the instance of SQL Server.  
$srv.Alter()  
```  
  
## <a name="modifying-sql-server-configuration-options-in-powershell"></a><span data-ttu-id="c4ea7-140">Modificar las opciones de configuración de SQL Server en PowerShell</span><span class="sxs-lookup"><span data-stu-id="c4ea7-140">Modifying SQL Server Configuration Options in PowerShell</span></span>  
 <span data-ttu-id="c4ea7-141">En el ejemplo de código se muestra cómo actualizar una opción de configuración en Visual Basic .NET.</span><span class="sxs-lookup"><span data-stu-id="c4ea7-141">The code example shows how to update a configuration option in Visual Basic .NET.</span></span> <span data-ttu-id="c4ea7-142">También recupera y muestra información sobre los valores máximos y mínimos para la opción de configuración especificada.</span><span class="sxs-lookup"><span data-stu-id="c4ea7-142">It also retrieves and displays information about maximum and minimum values for the specified configuration option.</span></span> <span data-ttu-id="c4ea7-143">Finalmente, el programa notifica al usuario si la modificación se ha realizado dinámicamente o si se almacena hasta que se reinicie la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c4ea7-143">Finally, the program informs the user if the change has been made dynamically, or if it is stored until the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is restarted.</span></span>  
  
```powershell
#Get a server object which corresponds to the default instance replace LocalMachine with the physical server  
cd \sql\LocalMachine  
$svr = Get-Item default  
  
#enumerate its properties  
foreach ($Item in $Svr.Configuration.Properties)   
{  
 $Item.DisplayName  
}  
  
"There are " + $svr.Configuration.Properties.Count.ToString() + " configuration options."  
  
#Display the maximum and minimum values for ShowAdvancedOptions.  
$min = $svr.Configuration.ShowAdvancedOptions.Minimum  
$max = $svr.Configuration.ShowAdvancedOptions.Maximum  
"Minimum and Maximum values are " + $min.ToString() + " and " + $max.ToString() + "."  
  
#Modify the value of ShowAdvancedOptions and run the Alter method.  
$svr.Configuration.ShowAdvancedOptions.ConfigValue = 0  
$svr.Configuration.Alter()  
  
#Display when the change takes place according to the IsDynamic property.  
If ($svr.Configuration.ShowAdvancedOptions.IsDynamic -eq $true)  
 {
   "Configuration option has been updated."  
 }  
Else  
 {  
    "Configuration option will be updated when SQL Server is restarted."  
 }  
```  
