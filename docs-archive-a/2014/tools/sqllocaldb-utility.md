---
title: SqlLocalDB (utilidad) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- SqlLocalDB utility [SQL Server]
- local database runtime utility
- LocalDB, SqlLocalDB Utility
ms.assetid: d785cdb7-1ea0-4871-bde9-1ae7881190f5
author: stevestein
ms.author: sstein
ms.openlocfilehash: bfb95cea4365d56c296d14fcc09046cd7eddc0c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743736"
---
# <a name="sqllocaldb-utility"></a><span data-ttu-id="777e3-102">SqlLocalDB (utilidad)</span><span class="sxs-lookup"><span data-stu-id="777e3-102">SqlLocalDB Utility</span></span>
  <span data-ttu-id="777e3-103">Use la `SqlLocalDB` utilidad para crear una instancia de [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssExpCurrent](../includes/ssexpcurrent-md.md)] **LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="777e3-103">Use the `SqlLocalDB` utility to create an instance of [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssExpCurrent](../includes/ssexpcurrent-md.md)]**LocalDB**.</span></span> <span data-ttu-id="777e3-104">La `SqlLocalDB` utilidad (SqlLocalDB.exe) es una herramienta de línea de comandos simple que permite a los usuarios y desarrolladores crear y administrar una instancia de [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] **LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="777e3-104">The `SqlLocalDB` utility (SqlLocalDB.exe) is a simple command line tool to enable users and developers to create and manage an instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span></span> <span data-ttu-id="777e3-105">Para obtener información acerca de cómo usar **LocalDB**, vea [SQL Server 2014 Express LocalDB](../database-engine/configure-windows/sql-server-2016-express-localdb.md).</span><span class="sxs-lookup"><span data-stu-id="777e3-105">For information about how to use **LocalDB**, see [SQL Server 2014 Express LocalDB](../database-engine/configure-windows/sql-server-2016-express-localdb.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="777e3-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="777e3-106">Syntax</span></span>  
  
```  
SqlLocalDB.exe   
{  
      [ create   | c ] <instance-name><instance-version> [-s ]  
    | [ delete   | d ] <instance-name>  
    | [ start    | s ] <instance-name>  
    | [ stop     | p ] <instance-name>  [ -i ] [ -k ]  
    | [ share    | h ] ["<user_SID>" | "<user_account>" ] "<private-name>""<shared-name>"  
    | [ unshare  | u ] "<shared-name>"  
    | [ info     | i ] <instance-name>  
    | [ versions | v ]  
    | [ trace    | t ] [ on | off ]  
    | [ help     | -? ]  
}  
```  
  
## <a name="arguments"></a><span data-ttu-id="777e3-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="777e3-107">Arguments</span></span>  
 <span data-ttu-id="777e3-108">[ **create** | **c** ] *\<instance-name>* *\<instance-version>* [ **-s** ]</span><span class="sxs-lookup"><span data-stu-id="777e3-108">[ **create** | **c** ] *\<instance-name>* *\<instance-version>* [**-s** ]</span></span>  
 <span data-ttu-id="777e3-109">Crea una instancia de [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="777e3-109">Creates a new of instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span></span> <span data-ttu-id="777e3-110">`SqlLocalDB`usa la versión de los [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] archivos binarios especificada por *\<instance-version>* argument.</span><span class="sxs-lookup"><span data-stu-id="777e3-110">`SqlLocalDB` uses the version of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] binaries specified by *\<instance-version>* argument.</span></span> <span data-ttu-id="777e3-111">El número de versión se especifica en formato numérico con al menos un decimal.</span><span class="sxs-lookup"><span data-stu-id="777e3-111">The version number is specified in numeric format with at least one decimal.</span></span> <span data-ttu-id="777e3-112">Los números de versión secundaria (Service Pack) son opcionales.</span><span class="sxs-lookup"><span data-stu-id="777e3-112">The minor version numbers (service packs) are optional.</span></span> <span data-ttu-id="777e3-113">Como los siguientes dos números de versión son aceptables: 11.0 u 11.0.1186.</span><span class="sxs-lookup"><span data-stu-id="777e3-113">For example the following two version numbers are both acceptable: 11.0, or 11.0.1186.</span></span> <span data-ttu-id="777e3-114">La versión especificada se debe instalar en el equipo.</span><span class="sxs-lookup"><span data-stu-id="777e3-114">The specified version must be installed on the computer.</span></span> <span data-ttu-id="777e3-115">Si no se especifica, el número de versión tiene como valor predeterminado la versión de la `SqlLocalDB` utilidad.</span><span class="sxs-lookup"><span data-stu-id="777e3-115">If not specified, the version number defaults to the version of the `SqlLocalDB` utility.</span></span> <span data-ttu-id="777e3-116">Al agregar **-s**, se inicia la nueva instancia de **LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="777e3-116">Adding **-s** starts the new instance of **LocalDB**.</span></span>  
  
 <span data-ttu-id="777e3-117">[ **share** | **h** ]</span><span class="sxs-lookup"><span data-stu-id="777e3-117">[ **share** | **h** ]</span></span>  
 <span data-ttu-id="777e3-118">Comparte la instancia privada especificada de **LocalDB** por medio del nombre compartido especificado.</span><span class="sxs-lookup"><span data-stu-id="777e3-118">Shares the specified private instance of **LocalDB** using the specified shared name.</span></span> <span data-ttu-id="777e3-119">Si se omite el SID del usuario o el nombre de la cuenta, usa de forma predeterminada el usuario actual.</span><span class="sxs-lookup"><span data-stu-id="777e3-119">If the user SID or account name is omitted, it defaults to the current user.</span></span>  
  
 <span data-ttu-id="777e3-120">[ **unshared** | **u** ]</span><span class="sxs-lookup"><span data-stu-id="777e3-120">[ **unshared** | **u** ]</span></span>  
 <span data-ttu-id="777e3-121">Detiene el uso compartido de la instancia compartida especificada de **LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="777e3-121">Stops the sharing of the specified shared instance of **LocalDB**.</span></span>  
  
 <span data-ttu-id="777e3-122">[ **delete** | **d** ] *\<instance-name>*</span><span class="sxs-lookup"><span data-stu-id="777e3-122">[ **delete** | **d** ] *\<instance-name>*</span></span>  
 <span data-ttu-id="777e3-123">Elimina la instancia especificada de [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="777e3-123">Deletes the specified instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span></span>  
  
 <span data-ttu-id="777e3-124">[ **start** | **s** ] " *\<instance-name>* "</span><span class="sxs-lookup"><span data-stu-id="777e3-124">[ **start** | **s** ] "*\<instance-name>*"</span></span>  
 <span data-ttu-id="777e3-125">Inicia la instancia especificada de [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="777e3-125">Starts the specified instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span></span> <span data-ttu-id="777e3-126">Cuando se realiza correctamente, la instrucción devuelve la dirección de la canalización con nombre de **LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="777e3-126">When successful the statement returns the named pipe address of the **LocalDB**.</span></span>  
  
 <span data-ttu-id="777e3-127">[ **stop** | **p** ] *\<instance-name>* [ **-i** ] [ **-k** ]</span><span class="sxs-lookup"><span data-stu-id="777e3-127">[ **stop** | **p** ] *\<instance-name>* [**-i** ] [**-k** ]</span></span>  
 <span data-ttu-id="777e3-128">Detiene la instancia especificada de [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="777e3-128">Stops the specified instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span></span> <span data-ttu-id="777e3-129">Al agregar **-i se** solicita el cierre de la instancia con la `NOWAIT` opción.</span><span class="sxs-lookup"><span data-stu-id="777e3-129">Adding **-i** requests the instance shutdown with the `NOWAIT` option.</span></span> <span data-ttu-id="777e3-130">Al agregar **-k**, se elimina el proceso de la instancia sin ponerse en contacto con ella.</span><span class="sxs-lookup"><span data-stu-id="777e3-130">Adding **-k** kills the instance process without contacting it.</span></span>  
  
 <span data-ttu-id="777e3-131">[ **info** | **i** ] [ *\<instance-name>* ]</span><span class="sxs-lookup"><span data-stu-id="777e3-131">[ **info** | **i** ] [ *\<instance-name>* ]</span></span>  
 <span data-ttu-id="777e3-132">Muestra toda la instancia de [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB** que pertenece al usuario actual.</span><span class="sxs-lookup"><span data-stu-id="777e3-132">Lists all instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB** owned by the current user.</span></span>  
  
 <span data-ttu-id="777e3-133">*\<instance-name>* devuelve el nombre, la versión, el estado (En ejecución o Detenido), la última hora de inicio de la instancia especificada de [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB** y el nombre de la canalización local de **LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="777e3-133">*\<instance-name>* returns the name, version, state (Running or Stopped), last start time for the specified instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**, and the local pipe name of the **LocalDB**.</span></span>  
  
 <span data-ttu-id="777e3-134">[ **trace** | **t** ] **on** | **off**</span><span class="sxs-lookup"><span data-stu-id="777e3-134">[ **trace** | **t** ] **on** | **off**</span></span>  
 <span data-ttu-id="777e3-135">**Trace on** habilita el seguimiento de las `SqlLocalDB` llamadas de API para el usuario actual.</span><span class="sxs-lookup"><span data-stu-id="777e3-135">**trace on** enables tracing for the `SqlLocalDB` API calls for the current user.</span></span> <span data-ttu-id="777e3-136">**trace off** deshabilita el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="777e3-136">**trace off** disables tracing.</span></span>  
  
 <span data-ttu-id="777e3-137">**-?**</span><span class="sxs-lookup"><span data-stu-id="777e3-137">**-?**</span></span>  
 <span data-ttu-id="777e3-138">Devuelve breves descripciones de cada `SqlLocalDB` opción.</span><span class="sxs-lookup"><span data-stu-id="777e3-138">Returns brief descriptions of each `SqlLocalDB` option.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="777e3-139">Observaciones</span><span class="sxs-lookup"><span data-stu-id="777e3-139">Remarks</span></span>  
 <span data-ttu-id="777e3-140">El argumento *instance name* debe cumplir las reglas de los identificadores de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] o debe incluirse entre comillas.</span><span class="sxs-lookup"><span data-stu-id="777e3-140">The *instance name* argument must follow the rules for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] identifiers or it must be enclosed in double quotes.</span></span>  
  
 <span data-ttu-id="777e3-141">La ejecución de SqlLocalDB sin argumentos devuelve el texto de ayuda.</span><span class="sxs-lookup"><span data-stu-id="777e3-141">Executing SqlLocalDB without arguments returns the help text.</span></span>  
  
 <span data-ttu-id="777e3-142">Las operaciones distintas de la operación de inicio solo se pueden realizar en una instancia perteneciente al usuario que ha iniciado la sesión.</span><span class="sxs-lookup"><span data-stu-id="777e3-142">Operations other than start can only be performed on an instance belonging to currently logged in user.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="777e3-143">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="777e3-143">Examples</span></span>  
  
### <a name="a-creating-an-instance-of-localdb"></a><span data-ttu-id="777e3-144">A.</span><span class="sxs-lookup"><span data-stu-id="777e3-144">A.</span></span> <span data-ttu-id="777e3-145">Crear una instancia de LocalDB</span><span class="sxs-lookup"><span data-stu-id="777e3-145">Creating an Instance of LocalDB</span></span>  
 <span data-ttu-id="777e3-146">En el ejemplo siguiente se crea una instancia de [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB** denominada `DEPARTMENT` utilizando los binarios de [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] y se inicia la instancia.</span><span class="sxs-lookup"><span data-stu-id="777e3-146">The following example creates an instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB** named `DEPARTMENT` using the [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] binaries and starts the instance.</span></span>  
  
```  
SqlLocalDB.exe create "DEPARTMENT" 12.0 -s  
```  
  
### <a name="b-working-with-a-shared-instance-of-localdb"></a><span data-ttu-id="777e3-147">B.</span><span class="sxs-lookup"><span data-stu-id="777e3-147">B.</span></span> <span data-ttu-id="777e3-148">Trabajar con una instancia compartida de LocalDB</span><span class="sxs-lookup"><span data-stu-id="777e3-148">Working with a Shared Instance of LocalDB</span></span>  
 <span data-ttu-id="777e3-149">Abra un símbolo del sistema utilizando los permisos de administrador.</span><span class="sxs-lookup"><span data-stu-id="777e3-149">Open a command prompt using Administrator privileges.</span></span>  
  
```  
SqlLocalDB.exe create "DeptLocalDB"  
SqlLocalDB.exe share "DeptLocalDB" "DeptSharedLocalDB"  
SqlLocalDB.exe start "DeptLocalDB"  
SqlLocalDB.exe info "DeptLocalDB"  
REM The previous statement outputs the Instance pipe name for the next step  
sqlcmd -S np:\\.\pipe\LOCALDB#<use your pipe name>\tsql\query  
CREATE LOGIN NewLogin WITH PASSWORD = 'Passw0rd!!@52';   
GO  
CREATE USER NewLogin;  
GO  
EXIT  
```  
  
 <span data-ttu-id="777e3-150">Ejecute el código siguiente para conectarse a la instancia compartida de **LocalDB** mediante el inicio de sesión de `NewLogin` .</span><span class="sxs-lookup"><span data-stu-id="777e3-150">Execute the following code to connect to the shared instance of **LocalDB** using the `NewLogin` login.</span></span>  
  
```  
sqlcmd -S (localdb)\.\DeptSharedLocalDB -U NewLogin -P Passw0rd!!@52  
```  
  
## <a name="see-also"></a><span data-ttu-id="777e3-151">Consulte también</span><span class="sxs-lookup"><span data-stu-id="777e3-151">See Also</span></span>  
 [<span data-ttu-id="777e3-152">SQL Server 2014 Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="777e3-152">SQL Server 2014 Express LocalDB</span></span>](../database-engine/configure-windows/sql-server-2016-express-localdb.md)  
  
  
