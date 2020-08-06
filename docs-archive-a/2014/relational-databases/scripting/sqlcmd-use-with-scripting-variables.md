---
title: Usar sqlcmd con variables de script
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- scripts [SQL Server], sqlcmd utility
- variables [SQL Server], scripts
- scripting variables [SQL Server]
- sqlcmd utility, scripts
- setvar command
ms.assetid: 793495ca-cfc9-498d-8276-c44a5d09a92c
author: rothja
ms.author: jroth
ms.openlocfilehash: 8443cb400dc099726ba75bfcec2d38cee4ee2dff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675803"
---
# <a name="use-sqlcmd-with-scripting-variables"></a><span data-ttu-id="5bd5b-102">Usar sqlcmd con variables de script</span><span class="sxs-lookup"><span data-stu-id="5bd5b-102">Use sqlcmd with Scripting Variables</span></span>
  <span data-ttu-id="5bd5b-103">Las variables que se usan en scripts se denominan variables de scripting.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-103">Variables that are used in scripts are called scripting variables.</span></span> <span data-ttu-id="5bd5b-104">Las variables de scripting posibilitan el uso de un script en varias situaciones.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-104">Scripting variables enable one script to be used in multiple scenarios.</span></span> <span data-ttu-id="5bd5b-105">Por ejemplo, si desea ejecutar un script en varios servidores, en lugar de modificar el script para cada servidor, puede usar una variable de scripting para el nombre del servidor.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-105">For example, if you want to run one script against multiple servers, instead of modifying the script for each server, you can use a scripting variable for the server name.</span></span> <span data-ttu-id="5bd5b-106">Al cambiar el nombre del servidor proporcionado a la variable de scripting, el mismo script puede ejecutarse en diferentes servidores.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-106">By changing the server name supplied to the scripting variable, the same script can be executed on different servers.</span></span>  
  
 <span data-ttu-id="5bd5b-107">Las variables de scripting pueden definirse explícitamente mediante el comando **setvar** o implícitamente mediante la opción **sqlcmd-v** .</span><span class="sxs-lookup"><span data-stu-id="5bd5b-107">Scripting variables can be defined explicitly by using the **setvar** command, or implicitly by using the **sqlcmd-v** option.</span></span>  
  
 <span data-ttu-id="5bd5b-108">Además, en este tema se proporcionan ejemplos en los que se definen variables de entorno en el símbolo del sistema Cmd.exe mediante **SET**.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-108">This topic also includes examples defining environmental variables at the Cmd.exe command prompt by using **SET**.</span></span>  
  
## <a name="setting-scripting-variables-by-using-the-setvar-command"></a><span data-ttu-id="5bd5b-109">Definir variables de scripting mediante el comando setvar</span><span class="sxs-lookup"><span data-stu-id="5bd5b-109">Setting Scripting Variables by Using the setvar Command</span></span>  
 <span data-ttu-id="5bd5b-110">El comando **setvar** se usa para definir variables de scripting.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-110">The **setvar** command is used to define scripting variables.</span></span> <span data-ttu-id="5bd5b-111">Las variables que se definen mediante el comando **setvar** se almacenan internamente.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-111">Variables that are defined by using the **setvar** command are stored internally.</span></span> <span data-ttu-id="5bd5b-112">Las variables de scripting no deben confundirse con las variables de entorno que se definen en el símbolo del sistema mediante **SET**.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-112">Scripting variables should not be confused with environment variables that are defined at the command prompt by using **SET**.</span></span> <span data-ttu-id="5bd5b-113">Si un script hace referencia a una variable que no es de entorno o que no está definida mediante **setvar**, aparece un mensaje de error y se detiene la ejecución del script.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-113">If a script references a variable that is not an environment variable or is not defined by using **setvar**, an error message is returned and the execution of the script will stop.</span></span> <span data-ttu-id="5bd5b-114">Para obtener más información, vea la opción **-b** en [sqlcmd Utility](../../tools/sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="5bd5b-114">For more information, see the **-b** option in [sqlcmd Utility](../../tools/sqlcmd-utility.md).</span></span>  
  
## <a name="variable-precedence-low-to-high"></a><span data-ttu-id="5bd5b-115">Precedencia de variables (menor a mayor)</span><span class="sxs-lookup"><span data-stu-id="5bd5b-115">Variable Precedence (Low to High)</span></span>  
 <span data-ttu-id="5bd5b-116">Si hay más de un tipo de variable con el mismo nombre, se usa la variable que tenga la prioridad más alta.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-116">If more than one type of variable has the same name, the variable with the highest precedence is used.</span></span>  
  
1.  <span data-ttu-id="5bd5b-117">Variables de entorno del nivel del sistema</span><span class="sxs-lookup"><span data-stu-id="5bd5b-117">System level environmental variables</span></span>  
  
2.  <span data-ttu-id="5bd5b-118">Variables de entorno del nivel del usuario</span><span class="sxs-lookup"><span data-stu-id="5bd5b-118">User level environmental variables</span></span>  
  
3.  <span data-ttu-id="5bd5b-119">Shell de comandos (**SET X=Y**) establecido en el símbolo del sistema antes de iniciar **sqlcmd**</span><span class="sxs-lookup"><span data-stu-id="5bd5b-119">Command shell (**SET X=Y**) set at command prompt before starting **sqlcmd**</span></span>  
  
4.  <span data-ttu-id="5bd5b-120">**sqlcmd-v** X=Y</span><span class="sxs-lookup"><span data-stu-id="5bd5b-120">**sqlcmd-v** X=Y</span></span>  
  
5.  <span data-ttu-id="5bd5b-121">**:Setvar** X Y</span><span class="sxs-lookup"><span data-stu-id="5bd5b-121">**:Setvar** X Y</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5bd5b-122">Para ver las variables de entorno, en el **Panel de control**, abra **Sistema**y haga clic en la pestaña **Opciones avanzadas** .</span><span class="sxs-lookup"><span data-stu-id="5bd5b-122">To view the environmental variables, in **Control Panel**, open **System**, and then click the **Advanced** tab.</span></span>  
  
## <a name="implicitly-setting-scripting-variables"></a><span data-ttu-id="5bd5b-123">Definir las variables de scripting implícitamente</span><span class="sxs-lookup"><span data-stu-id="5bd5b-123">Implicitly Setting Scripting Variables</span></span>  
 <span data-ttu-id="5bd5b-124">Al iniciar **sqlcmd** con una opción que tiene una variable **sqlcmd** relacionada, la variable **sqlcmd** se establece implícitamente en el valor especificado mediante la opción.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-124">When you start **sqlcmd** with an option that has a related **sqlcmd** variable, the **sqlcmd** variable is set implicitly to the value that is specified by using the option.</span></span> <span data-ttu-id="5bd5b-125">En el siguiente ejemplo, `sqlcmd` se inicia con la opción `-l` .</span><span class="sxs-lookup"><span data-stu-id="5bd5b-125">In the following example, `sqlcmd` is started with the `-l` option.</span></span> <span data-ttu-id="5bd5b-126">Esto establece implícitamente la variable SQLLOGINTIMEOUT.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-126">This implicitly sets the SQLLOGINTIMEOUT variable.</span></span>  
  
 `c:\> sqlcmd -l 60`  
  
 <span data-ttu-id="5bd5b-127">También puede usar la opción **-v** para establecer una variable de scripting que existe en un script.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-127">You can also use the **-v** option to set a scripting variable that exists in a script.</span></span> <span data-ttu-id="5bd5b-128">En el script siguiente (el nombre de archivo es `testscript.sql`), `ColumnName` es una variable de scripting.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-128">In the following script (the file name is `testscript.sql`), `ColumnName` is a scripting variable.</span></span>  
  
 `USE AdventureWorks2012;`  
  
 `SELECT x.$(ColumnName)`  
  
 `FROM Person.Person x`  
  
 <span data-ttu-id="5bd5b-129">`WHERE c.`BusinessEntityID `< 5;`</span><span class="sxs-lookup"><span data-stu-id="5bd5b-129">`WHERE c.`BusinessEntityID `< 5;`</span></span>  
  
 <span data-ttu-id="5bd5b-130">Después, puede especificar el nombre de la columna que desea que se devuelva mediante la opción `-v` :</span><span class="sxs-lookup"><span data-stu-id="5bd5b-130">You can then specify the name of the column that you want returned by using the `-v` option:</span></span>  
  
 `sqlcmd -v ColumnName ="FirstName" -i c:\testscript.sql`  
  
 <span data-ttu-id="5bd5b-131">Para devolver otra columna usando el mismo script, cambie el valor de la variable de scripting `ColumnName` .</span><span class="sxs-lookup"><span data-stu-id="5bd5b-131">To return a different column by using the same script, change the value of the `ColumnName` scripting variable.</span></span>  
  
 `sqlcmd -v ColumnName ="LastName" -i c:\testscript.sql`  
  
## <a name="guidelines-for-scripting-variable-names-and-values"></a><span data-ttu-id="5bd5b-132">Directrices para los nombres y valores de variable de script</span><span class="sxs-lookup"><span data-stu-id="5bd5b-132">Guidelines for Scripting Variable Names and Values</span></span>  
 <span data-ttu-id="5bd5b-133">Al especificar un nombre para las variables de script, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5bd5b-133">Consider the following guidelines when you name scripting variables:</span></span>  
  
-   <span data-ttu-id="5bd5b-134">Los nombres de variable no deben contener caracteres de espacio en blanco ni comillas.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-134">Variable names must not contain white space characters or quotation marks.</span></span>  
  
-   <span data-ttu-id="5bd5b-135">Los nombres de variable no deben tener la misma forma que una expresión variable, como *$(var)*.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-135">Variable names must not have the same form as a variable expression, such as *$(var)*.</span></span>  
  
-   <span data-ttu-id="5bd5b-136">Las variables de scripting no distinguen entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-136">Scripting variables are case-insensitive</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5bd5b-137">Si no se asigna ningún valor a una variable de entorno **sqlcmd** , se quita la variable.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-137">If no value is assigned to a **sqlcmd** environment variable, the variable is removed.</span></span> <span data-ttu-id="5bd5b-138">Si se usa **:setvar VarName** sin ningún valor, la variable se borra.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-138">Using **:setvar VarName** without a value clears the variable.</span></span>  
  
 <span data-ttu-id="5bd5b-139">Al especificar valores para las variables de scripting, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5bd5b-139">Consider the following guidelines when you specify values for scripting variables:</span></span>  
  
-   <span data-ttu-id="5bd5b-140">Los valores de variable definidos mediante **setvar** o la opción **-v** deben ir entre comillas si el valor de cadena contiene espacios.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-140">Variable values that are defined by using **setvar** or the **-v** option must be enclosed by quotation marks if the string value contains spaces.</span></span>  
  
-   <span data-ttu-id="5bd5b-141">Si las comillas forman parte del valor de variable, es necesario usar un carácter de escape.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-141">If quotation marks are part of the variable value, they must be escaped.</span></span> <span data-ttu-id="5bd5b-142">Por ejemplo: :`setvar MyVar "spac""e"`.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-142">For example: :`setvar MyVar "spac""e"`.</span></span>  
  
## <a name="guidelines-for-cmdexe-set-variable-values-and-names"></a><span data-ttu-id="5bd5b-143">Directrices para los nombres y valores de la variable SET de Cmd.exe</span><span class="sxs-lookup"><span data-stu-id="5bd5b-143">Guidelines for Cmd.exe SET Variable Values and Names</span></span>  
 <span data-ttu-id="5bd5b-144">Las variables que se definen mediante SET forman parte del entorno de Cmd.exe y se puede hacer referencia a ellas mediante **sqlcmd**.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-144">Variables that are defined by using SET are part of the Cmd.exe environment and can be referenced by **sqlcmd**.</span></span> <span data-ttu-id="5bd5b-145">Tenga en cuenta las directrices siguientes:</span><span class="sxs-lookup"><span data-stu-id="5bd5b-145">Consider the following guidelines:</span></span>  
  
-   <span data-ttu-id="5bd5b-146">Los nombres de variable no deben contener caracteres de espacio en blanco ni comillas.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-146">Variable names must not contain white space characters or quotation marks.</span></span>  
  
-   <span data-ttu-id="5bd5b-147">Los valores de variable pueden contener caracteres de espacio en blanco o comillas.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-147">Variable values may contain spaces or quotation marks.</span></span>  
  
## <a name="sqlcmd-scripting-variables"></a><span data-ttu-id="5bd5b-148">Variables de scripting sqlcmd</span><span class="sxs-lookup"><span data-stu-id="5bd5b-148">sqlcmd Scripting Variables</span></span>  
 <span data-ttu-id="5bd5b-149">Las variables definidas mediante **sqlcmd** se denominan variables de scripting.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-149">Variables that are defined by **sqlcmd** are known as scripting variables.</span></span> <span data-ttu-id="5bd5b-150">En la siguiente tabla se enumeran las variables de scripting de **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="5bd5b-150">The following table lists **sqlcmd** scripting variables.</span></span>  
  
|<span data-ttu-id="5bd5b-151">Variable</span><span class="sxs-lookup"><span data-stu-id="5bd5b-151">Variable</span></span>|<span data-ttu-id="5bd5b-152">Opción relacionada</span><span class="sxs-lookup"><span data-stu-id="5bd5b-152">Related option</span></span>|<span data-ttu-id="5bd5b-153">L/E</span><span class="sxs-lookup"><span data-stu-id="5bd5b-153">R/W</span></span>|<span data-ttu-id="5bd5b-154">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="5bd5b-154">Default</span></span>|  
|--------------|--------------------|----------|-------------|  
|<span data-ttu-id="5bd5b-155">SQLCMDUSER\*</span><span class="sxs-lookup"><span data-stu-id="5bd5b-155">SQLCMDUSER\*</span></span>|<span data-ttu-id="5bd5b-156">-U</span><span class="sxs-lookup"><span data-stu-id="5bd5b-156">-U</span></span>|<span data-ttu-id="5bd5b-157">R</span><span class="sxs-lookup"><span data-stu-id="5bd5b-157">R</span></span>|<span data-ttu-id="5bd5b-158">""</span><span class="sxs-lookup"><span data-stu-id="5bd5b-158">""</span></span>|  
|<span data-ttu-id="5bd5b-159">SQLCMDPASSWORD\*</span><span class="sxs-lookup"><span data-stu-id="5bd5b-159">SQLCMDPASSWORD\*</span></span>|<span data-ttu-id="5bd5b-160">-P</span><span class="sxs-lookup"><span data-stu-id="5bd5b-160">-P</span></span>|--|<span data-ttu-id="5bd5b-161">""</span><span class="sxs-lookup"><span data-stu-id="5bd5b-161">""</span></span>|  
|<span data-ttu-id="5bd5b-162">SQLCMDSERVER\*</span><span class="sxs-lookup"><span data-stu-id="5bd5b-162">SQLCMDSERVER\*</span></span>|<span data-ttu-id="5bd5b-163">-S</span><span class="sxs-lookup"><span data-stu-id="5bd5b-163">-S</span></span>|<span data-ttu-id="5bd5b-164">R</span><span class="sxs-lookup"><span data-stu-id="5bd5b-164">R</span></span>|<span data-ttu-id="5bd5b-165">"DefaultLocalInstance"</span><span class="sxs-lookup"><span data-stu-id="5bd5b-165">"DefaultLocalInstance"</span></span>|  
|<span data-ttu-id="5bd5b-166">SQLCMDWORKSTATION</span><span class="sxs-lookup"><span data-stu-id="5bd5b-166">SQLCMDWORKSTATION</span></span>|<span data-ttu-id="5bd5b-167">-H</span><span class="sxs-lookup"><span data-stu-id="5bd5b-167">-H</span></span>|<span data-ttu-id="5bd5b-168">R</span><span class="sxs-lookup"><span data-stu-id="5bd5b-168">R</span></span>|<span data-ttu-id="5bd5b-169">"ComputerName"</span><span class="sxs-lookup"><span data-stu-id="5bd5b-169">"ComputerName"</span></span>|  
|<span data-ttu-id="5bd5b-170">SQLCMDDBNAME</span><span class="sxs-lookup"><span data-stu-id="5bd5b-170">SQLCMDDBNAME</span></span>|<span data-ttu-id="5bd5b-171">-d</span><span class="sxs-lookup"><span data-stu-id="5bd5b-171">-d</span></span>|<span data-ttu-id="5bd5b-172">R</span><span class="sxs-lookup"><span data-stu-id="5bd5b-172">R</span></span>|<span data-ttu-id="5bd5b-173">""</span><span class="sxs-lookup"><span data-stu-id="5bd5b-173">""</span></span>|  
|<span data-ttu-id="5bd5b-174">SQLCMDLOGINTIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5bd5b-174">SQLCMDLOGINTIMEOUT</span></span>|<span data-ttu-id="5bd5b-175">-l</span><span class="sxs-lookup"><span data-stu-id="5bd5b-175">-l</span></span>|<span data-ttu-id="5bd5b-176">L/E</span><span class="sxs-lookup"><span data-stu-id="5bd5b-176">R/W</span></span>|<span data-ttu-id="5bd5b-177">"8" (segundos)</span><span class="sxs-lookup"><span data-stu-id="5bd5b-177">"8" (seconds)</span></span>|  
|<span data-ttu-id="5bd5b-178">SQLCMDSTATTIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5bd5b-178">SQLCMDSTATTIMEOUT</span></span>|<span data-ttu-id="5bd5b-179">-T</span><span class="sxs-lookup"><span data-stu-id="5bd5b-179">-t</span></span>|<span data-ttu-id="5bd5b-180">L/E</span><span class="sxs-lookup"><span data-stu-id="5bd5b-180">R/W</span></span>|<span data-ttu-id="5bd5b-181">"0" = esperar indefinidamente</span><span class="sxs-lookup"><span data-stu-id="5bd5b-181">"0" = wait indefinitely</span></span>|  
|<span data-ttu-id="5bd5b-182">SQLCMDHEADERS</span><span class="sxs-lookup"><span data-stu-id="5bd5b-182">SQLCMDHEADERS</span></span>|<span data-ttu-id="5bd5b-183">-H</span><span class="sxs-lookup"><span data-stu-id="5bd5b-183">-h</span></span>|<span data-ttu-id="5bd5b-184">L/E</span><span class="sxs-lookup"><span data-stu-id="5bd5b-184">R/W</span></span>|<span data-ttu-id="5bd5b-185">"0"</span><span class="sxs-lookup"><span data-stu-id="5bd5b-185">"0"</span></span>|  
|<span data-ttu-id="5bd5b-186">SQLCMDCOLSEP</span><span class="sxs-lookup"><span data-stu-id="5bd5b-186">SQLCMDCOLSEP</span></span>|<span data-ttu-id="5bd5b-187">-S</span><span class="sxs-lookup"><span data-stu-id="5bd5b-187">-s</span></span>|<span data-ttu-id="5bd5b-188">L/E</span><span class="sxs-lookup"><span data-stu-id="5bd5b-188">R/W</span></span>|<span data-ttu-id="5bd5b-189">" "</span><span class="sxs-lookup"><span data-stu-id="5bd5b-189">" "</span></span>|  
|<span data-ttu-id="5bd5b-190">SQLCMDCOLWIDTH</span><span class="sxs-lookup"><span data-stu-id="5bd5b-190">SQLCMDCOLWIDTH</span></span>|<span data-ttu-id="5bd5b-191">-w</span><span class="sxs-lookup"><span data-stu-id="5bd5b-191">-w</span></span>|<span data-ttu-id="5bd5b-192">L/E</span><span class="sxs-lookup"><span data-stu-id="5bd5b-192">R/W</span></span>|<span data-ttu-id="5bd5b-193">"0"</span><span class="sxs-lookup"><span data-stu-id="5bd5b-193">"0"</span></span>|  
|<span data-ttu-id="5bd5b-194">SQLCMDPACKETSIZE</span><span class="sxs-lookup"><span data-stu-id="5bd5b-194">SQLCMDPACKETSIZE</span></span>|<span data-ttu-id="5bd5b-195">-a</span><span class="sxs-lookup"><span data-stu-id="5bd5b-195">-a</span></span>|<span data-ttu-id="5bd5b-196">R</span><span class="sxs-lookup"><span data-stu-id="5bd5b-196">R</span></span>|<span data-ttu-id="5bd5b-197">"4096"</span><span class="sxs-lookup"><span data-stu-id="5bd5b-197">"4096"</span></span>|  
|<span data-ttu-id="5bd5b-198">SQLCMDERRORLEVEL</span><span class="sxs-lookup"><span data-stu-id="5bd5b-198">SQLCMDERRORLEVEL</span></span>|<span data-ttu-id="5bd5b-199">-M</span><span class="sxs-lookup"><span data-stu-id="5bd5b-199">-m</span></span>|<span data-ttu-id="5bd5b-200">L/E</span><span class="sxs-lookup"><span data-stu-id="5bd5b-200">R/W</span></span>|<span data-ttu-id="5bd5b-201">"0"</span><span class="sxs-lookup"><span data-stu-id="5bd5b-201">"0"</span></span>|  
|<span data-ttu-id="5bd5b-202">SQLCMDMAXVARTYPEWIDTH</span><span class="sxs-lookup"><span data-stu-id="5bd5b-202">SQLCMDMAXVARTYPEWIDTH</span></span>|<span data-ttu-id="5bd5b-203">-y</span><span class="sxs-lookup"><span data-stu-id="5bd5b-203">-y</span></span>|<span data-ttu-id="5bd5b-204">L/E</span><span class="sxs-lookup"><span data-stu-id="5bd5b-204">R/W</span></span>|<span data-ttu-id="5bd5b-205">"256"</span><span class="sxs-lookup"><span data-stu-id="5bd5b-205">"256"</span></span>|  
|<span data-ttu-id="5bd5b-206">SQLCMDMAXFIXEDTYPEWIDTH</span><span class="sxs-lookup"><span data-stu-id="5bd5b-206">SQLCMDMAXFIXEDTYPEWIDTH</span></span>|<span data-ttu-id="5bd5b-207">-y</span><span class="sxs-lookup"><span data-stu-id="5bd5b-207">-Y</span></span>|<span data-ttu-id="5bd5b-208">L/E</span><span class="sxs-lookup"><span data-stu-id="5bd5b-208">R/W</span></span>|<span data-ttu-id="5bd5b-209">"0" = ilimitado</span><span class="sxs-lookup"><span data-stu-id="5bd5b-209">"0" = unlimited</span></span>|  
|<span data-ttu-id="5bd5b-210">SQLCMDEDITOR</span><span class="sxs-lookup"><span data-stu-id="5bd5b-210">SQLCMDEDITOR</span></span>||<span data-ttu-id="5bd5b-211">L/E</span><span class="sxs-lookup"><span data-stu-id="5bd5b-211">R/W</span></span>|<span data-ttu-id="5bd5b-212">"edit.com"</span><span class="sxs-lookup"><span data-stu-id="5bd5b-212">"edit.com"</span></span>|  
|<span data-ttu-id="5bd5b-213">SQLCMDINI</span><span class="sxs-lookup"><span data-stu-id="5bd5b-213">SQLCMDINI</span></span>||<span data-ttu-id="5bd5b-214">R</span><span class="sxs-lookup"><span data-stu-id="5bd5b-214">R</span></span>|<span data-ttu-id="5bd5b-215">""</span><span class="sxs-lookup"><span data-stu-id="5bd5b-215">""</span></span>|  
  
 <span data-ttu-id="5bd5b-216">\*SQLCMDUSER, SQLCMDPASSWORD y SQLCMDSERVER se establecen cuando se usa **: Connect** .</span><span class="sxs-lookup"><span data-stu-id="5bd5b-216">\* SQLCMDUSER, SQLCMDPASSWORD and SQLCMDSERVER are set when **:Connect** is used.</span></span>  
  
 <span data-ttu-id="5bd5b-217">L indica que el valor solo puede establecerse una vez durante la inicialización del programa.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-217">R indicates the value can only be set one time during program initialization.</span></span>  
  
 <span data-ttu-id="5bd5b-218">L/E indica que el valor puede volver a definirse mediante el comando **setvar** y los comandos siguientes usarán el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-218">R/W indicates that the value can be reset by using the **setvar** command and subsequent commands will use the new value.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="5bd5b-219">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="5bd5b-219">Examples</span></span>  
  
### <a name="a-using-the-setvar-command-in-a-script"></a><span data-ttu-id="5bd5b-220">A.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-220">A.</span></span> <span data-ttu-id="5bd5b-221">Usar el comando setvar en un script</span><span class="sxs-lookup"><span data-stu-id="5bd5b-221">Using the setvar command in a script</span></span>  
 <span data-ttu-id="5bd5b-222">Muchas opciones de **sqlcmd** pueden controlarse en un script mediante el comando **setvar** .</span><span class="sxs-lookup"><span data-stu-id="5bd5b-222">Many **sqlcmd** options can be controlled in a script by using the **setvar** command.</span></span> <span data-ttu-id="5bd5b-223">En el siguiente ejemplo, se crea el script `test.sql` ; en él, la variable `SQLCMDLOGINTIMEOUT` está establecida en `60` segundos y otra variable de scripting, `server`, está establecida en `testserver`.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-223">In the following example, the script `test.sql` is created in which the `SQLCMDLOGINTIMEOUT` variable is set to `60` seconds and another scripting variable, `server`, is set to `testserver`.</span></span> <span data-ttu-id="5bd5b-224">El siguiente código está en `test.sql`.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-224">The following code is in `test.sql`.</span></span>  
  
 `:setvar SQLCMDLOGINTIMEOUT 60`  
  
 `:setvar server "testserver"`  
  
 `:connect $(server) -l $(SQLCMDLOGINTIMEOUT)`  
  
 `USE AdventureWorks2012;`  
  
 `SELECT FirstName, LastName`  
  
 `FROM Person.Person;`  
  
 `The script is then called by using sqlcmd:`  
  
 `sqlcmd -i c:\test.sql`  
  
### <a name="b-using-the-setvar-command-interactively"></a><span data-ttu-id="5bd5b-225">B.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-225">B.</span></span> <span data-ttu-id="5bd5b-226">Usar el comando setvar interactivamente</span><span class="sxs-lookup"><span data-stu-id="5bd5b-226">Using the setvar command interactively</span></span>  
 <span data-ttu-id="5bd5b-227">En el ejemplo siguiente se muestra cómo establecer una variable de script de manera interactiva mediante el comando `setvar` .</span><span class="sxs-lookup"><span data-stu-id="5bd5b-227">The following example shows how to set a scripting variable interactively by using the `setvar` command.</span></span>  
  
 `sqlcmd`  
  
 `:setvar  MYDATABASE AdventureWorks2012`  
  
 `USE $(MYDATABASE);`  
  
 `GO`  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `Changed database context to 'AdventureWorks2012'`  
  
 `1>`  
  
### <a name="c-using-command-prompt-environment-variables-within-sqlcmd"></a><span data-ttu-id="5bd5b-228">C.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-228">C.</span></span> <span data-ttu-id="5bd5b-229">Usar variables de entorno del símbolo del sistema en sqlcmd</span><span class="sxs-lookup"><span data-stu-id="5bd5b-229">Using command prompt environment variables within sqlcmd</span></span>  
 <span data-ttu-id="5bd5b-230">En el ejemplo siguiente, se establecen cuatro variables de entorno `are` , a las que luego se llama desde `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-230">In the following example, four environment variables `are` set and then called from `sqlcmd`.</span></span>  
  
 `C:\>SET tablename=Person.Person`  
  
 `C:\>SET col1=FirstName`  
  
 `C:\>SET col2=LastName`  
  
 `C:\>SET title=Ms.`  
  
 `C:\>sqlcmd -d AdventureWorks2012`  
  
 `1> SELECT TOP 5 $(col1) + ' ' + $(col2) AS Name`  
  
 `2> FROM $(tablename)`  
  
 `3> WHERE Title ='$(title)'`  
  
 `4> GO`  
  
### <a name="d-using-user-level-environment-variables-within-sqlcmd"></a><span data-ttu-id="5bd5b-231">D.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-231">D.</span></span> <span data-ttu-id="5bd5b-232">Usar variables de entorno de usuario en sqlcmd</span><span class="sxs-lookup"><span data-stu-id="5bd5b-232">Using user-level environment variables within sqlcmd</span></span>  
 <span data-ttu-id="5bd5b-233">En el ejemplo siguiente, se establece la variable de entorno de usuario `%Temp%` en el símbolo del sistema y se pasa al archivo de entrada de `sqlcmd` .</span><span class="sxs-lookup"><span data-stu-id="5bd5b-233">In the following example the user-level environmental variable `%Temp%` is set at the command prompt and passed to the `sqlcmd` input file.</span></span> <span data-ttu-id="5bd5b-234">Para obtener la variable de entorno de nivel de usuario, en el **Panel de control**, haga doble clic en **Sistema**.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-234">To obtain the user-level environment variable, in **Control Panel**, double-click **System**.</span></span> <span data-ttu-id="5bd5b-235">Haga clic en la pestaña **Avanzadas** y, a continuación, en **Variables de entorno**.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-235">Click the **Advance** tab, and then click **Environment Variables**.</span></span>  
  
 <span data-ttu-id="5bd5b-236">El código siguiente se encuentra en el archivo de entrada `c:\testscript.txt`:</span><span class="sxs-lookup"><span data-stu-id="5bd5b-236">The following code is in the input file `c:\testscript.txt`:</span></span>  
  
 `:OUT $(MyTempDirectory)`  
  
 `USE AdventureWorks2012;`  
  
 `SELECT FirstName`  
  
 `FROM AdventureWorks2012.Person.Person`  
  
 <span data-ttu-id="5bd5b-237">`WHERE BusinessEntityID` `< 5;`</span><span class="sxs-lookup"><span data-stu-id="5bd5b-237">`WHERE BusinessEntityID` `< 5;`</span></span>  
  
 <span data-ttu-id="5bd5b-238">El código siguiente se escribe en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="5bd5b-238">This following code is entered at the command prompt:</span></span>  
  
 `C:\ >SET MyTempDirectory=%Temp%\output.txt`  
  
 `C:\ >sqlcmd -i C:\testscript.txt`  
  
 <span data-ttu-id="5bd5b-239">El resultado siguiente se envía al archivo de salida C:\Documents and Settings\\<usuario\>\Local Settings\Temp\output.txt.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-239">The following result is sent to the output file C:\Documents and Settings\\<user\>\Local Settings\Temp\output.txt.</span></span>  
  
 `Changed database context to 'AdventureWorks2012'.`  
  
 `FirstName`  
  
 `--------------------------------------------------`  
  
 `Gustavo`  
  
 `Catherine`  
  
 `Kim`  
  
 `Humberto`  
  
 `(4 rows affected)`  
  
### <a name="e-using-a-startup-script"></a><span data-ttu-id="5bd5b-240">E.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-240">E.</span></span> <span data-ttu-id="5bd5b-241">Usar un script de inicio</span><span class="sxs-lookup"><span data-stu-id="5bd5b-241">Using a startup script</span></span>  
 <span data-ttu-id="5bd5b-242">Un script de inicio **sqlcmd** se ejecuta al iniciar **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="5bd5b-242">A **sqlcmd** startup script is executed when **sqlcmd** is started.</span></span> <span data-ttu-id="5bd5b-243">En el ejemplo siguiente se establece la variable de entorno `SQLCMDINI`.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-243">The following example sets the environment variable `SQLCMDINI`.</span></span> <span data-ttu-id="5bd5b-244">Este es el contenido de `init.sql.`</span><span class="sxs-lookup"><span data-stu-id="5bd5b-244">This is the contents of `init.sql.`</span></span>  
  
 `SET NOCOUNT ON`  
  
 `GO`  
  
 `DECLARE @nt_username nvarchar(128)`  
  
 `SET @nt_username = (SELECT rtrim(convert(nvarchar(128), nt_username))`  
  
 `FROM sys.dm_exec_sessions WHERE spid = @@SPID)`  
  
 `SELECT  @nt_username + ' is connected to ' +`  
  
 `rtrim(CONVERT(nvarchar(20), SERVERPROPERTY('servername'))) +`  
  
 `' (' +`  
  
 `rtrim(CONVERT(nvarchar(20), SERVERPROPERTY('productversion'))) +`  
  
 `')'`  
  
 `:setvar SQLCMDMAXFIXEDTYPEWIDTH 100`  
  
 `SET NOCOUNT OFF`  
  
 `GO`  
  
 `:setvar SQLCMDMAXFIXEDTYPEWIDTH`  
  
 <span data-ttu-id="5bd5b-245">De esta manera, se llama al archivo `init.sql` cuando se inicia `sqlcmd` .</span><span class="sxs-lookup"><span data-stu-id="5bd5b-245">This calls the `init.sql` file when `sqlcmd` is started.</span></span>  
  
 `C:\> SET sqlcmdini=c:\init.sql`  
  
 `>1 Sqlcmd`  
  
 <span data-ttu-id="5bd5b-246">Este es el resultado.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-246">This is the output.</span></span>  
  
 `>1 < user > is connected to < server > (9.00.2047.00)`  
  
> [!NOTE]  
>  <span data-ttu-id="5bd5b-247">La opción **-X** deshabilita la característica de script de inicio.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-247">The **-X** option disables the startup script feature.</span></span>  
  
### <a name="f-variable-expansion"></a><span data-ttu-id="5bd5b-248">F.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-248">F.</span></span> <span data-ttu-id="5bd5b-249">Expansión de variables</span><span class="sxs-lookup"><span data-stu-id="5bd5b-249">Variable expansion</span></span>  
 <span data-ttu-id="5bd5b-250">En el ejemplo siguiente se muestra cómo trabajar con datos que tienen el formato de una variable de **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="5bd5b-250">The following example shows working with data in the form of a **sqlcmd** variable.</span></span>  
  
 `USE AdventureWorks2012;`  
  
 `CREATE TABLE AdventureWorks2012.dbo.VariableTest`  
  
 `(`  
  
 `Col1 nvarchar(50)`  
  
 `);`  
  
 `GO`  
  
 <span data-ttu-id="5bd5b-251">Inserte una fila en la `Col1` de `dbo.VariableTest` que contiene el valor `$(tablename)`.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-251">Insert one row into `Col1` of `dbo.VariableTest` that contains the value `$(tablename)`.</span></span>  
  
 `INSERT INTO AdventureWorks2012.dbo.VariableTest(Col1)`  
  
 `VALUES('$(tablename)');`  
  
 `GO`  
  
 <span data-ttu-id="5bd5b-252">En el símbolo del sistema `sqlcmd` , si no hay ninguna variable con el valor `$(tablename)`, las instrucciones siguientes devuelven la fila.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-252">At the `sqlcmd` prompt, when no variable is set equal to `$(tablename)`, the following statements return the row.</span></span>  
  
 `C:\> sqlcmd`  
  
 `>1 SELECT Col1 FROM dbo.VariableTest WHERE Col1 = '$(tablename)';`  
  
 `>2 GO`  
  
 `>3 SELECT Col1 FROM dbo.VariableTest WHERE Col1 = N'$(tablename)';`  
  
 `>4 GO`  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `>1 Col1`  
  
 `>2 ------------------`  
  
 `>3 $(tablename)`  
  
 `>4`  
  
 `>5 (1 rows affected)`  
  
 <span data-ttu-id="5bd5b-253">Si la variable `MyVar` está establecida en `$(tablename)`.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-253">Given the variable `MyVar` is set to `$(tablename)`.</span></span>  
  
 `>6 :setvar MyVar $(tablename)`  
  
 <span data-ttu-id="5bd5b-254">Estas instrucciones devuelven la fila y, además, un mensaje que indica que "No se definió la variable de script 'nombreDeTabla'".</span><span class="sxs-lookup"><span data-stu-id="5bd5b-254">These statements return the row and also return the message "'tablename' scripting variable not defined."</span></span>  
  
 `>6 SELECT Col1 FROM dbo.VariableTest WHERE Col1 = '$(tablename)';`  
  
 `>7 GO`  
  
 `>1 SELECT Col1 FROM dbo.VariableTest WHERE Col1 = N'$(tablename)';`  
  
 `>2 GO`  
  
 <span data-ttu-id="5bd5b-255">Estas instrucciones devuelven la fila.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-255">These statements return the row.</span></span>  
  
 `>1 SELECT Col1 FROM dbo.VariableTest WHERE Col1 = '$(MyVar)';`  
  
 `>2 GO`  
  
 `>1 SELECT Col1 FROM dbo.VariableTest WHERE Col1 = N'$(MyVar)';`  
  
 `>2 GO`  
  
## <a name="see-also"></a><span data-ttu-id="5bd5b-256">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5bd5b-256">See Also</span></span>  
 <span data-ttu-id="5bd5b-257">[Usar la utilidad sqlcmd](sqlcmd-use-the-utility.md) </span><span class="sxs-lookup"><span data-stu-id="5bd5b-257">[Use the sqlcmd Utility](sqlcmd-use-the-utility.md) </span></span>  
 <span data-ttu-id="5bd5b-258">[sqlcmd (utilidad)](../../tools/sqlcmd-utility.md) </span><span class="sxs-lookup"><span data-stu-id="5bd5b-258">[sqlcmd Utility](../../tools/sqlcmd-utility.md) </span></span>  
 [<span data-ttu-id="5bd5b-259">Referencia de la utilidad del símbolo del sistema &#40;motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="5bd5b-259">Command Prompt Utility Reference &#40;Database Engine&#41;</span></span>](../../tools/command-prompt-utility-reference-database-engine.md)  
  
  
