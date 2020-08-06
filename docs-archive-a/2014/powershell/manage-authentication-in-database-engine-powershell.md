---
title: Administración de la autenticación en PowerShell del motor de base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: ab9212a6-6628-4f08-a38c-d3156e05ddea
author: stevestein
ms.author: sstein
ms.openlocfilehash: 018a2698a43148af971622f54c8418bf23c2c781
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744731"
---
# <a name="manage-authentication-in-database-engine-powershell"></a><span data-ttu-id="4e0c8-102">Administrar la autenticación en PowerShell del motor de base de datos</span><span class="sxs-lookup"><span data-stu-id="4e0c8-102">Manage Authentication in Database Engine PowerShell</span></span>
  <span data-ttu-id="4e0c8-103">De forma predeterminada, los componentes PowerShell de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] usan la autenticación de Windows para conectarse a una instancia de [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e0c8-103">By default, the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell components use Windows Authentication when connecting to an instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="4e0c8-104">Puede usar la autenticación de SQL Server definiendo una unidad virtual de PowerShell o especificando los parámetros de `-Username` y de `-Password` para `Invoke-Sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="4e0c8-104">You can use SQL Server Authentication by either defining a PowerShell virtual drive, or by specifying the `-Username` and `-Password` parameters for `Invoke-Sqlcmd`.</span></span>  
  
1.  <span data-ttu-id="4e0c8-105">**Antes de empezar:**  [Permisos](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="4e0c8-105">**Before you begin:**  [Permissions](#Permissions)</span></span>  
  
2.  <span data-ttu-id="4e0c8-106">**Para establecer la autenticación con:**  [Una unidad virtual](#SQLAuthVirtDrv), [Invoke-Sqlcmd](#SQLAuthInvSqlCmd)</span><span class="sxs-lookup"><span data-stu-id="4e0c8-106">**To set authentication, using:**  [A Virtual Drive](#SQLAuthVirtDrv), [Invoke-Sqlcmd](#SQLAuthInvSqlCmd)</span></span>  
  
##  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4e0c8-107">Permisos</span><span class="sxs-lookup"><span data-stu-id="4e0c8-107">Permissions</span></span>  
 <span data-ttu-id="4e0c8-108">Todas las acciones que se pueden realizar en una instancia de [!INCLUDE[ssDE](../includes/ssde-md.md)] se controlan mediante los permisos concedidos a las credenciales de autenticación usadas para conectarse a la instancia.</span><span class="sxs-lookup"><span data-stu-id="4e0c8-108">All actions you can perform in an instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)] are controlled by the permissions granted to the authentication credentials used to connect to the instance.</span></span> <span data-ttu-id="4e0c8-109">De forma predeterminada, el proveedor y los cmdlets de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] usa la cuenta de Windows de ejecución para establecer una conexión de autenticación de Windows con [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e0c8-109">By default, the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider and cmdlets use the Windows account under which it is running to make a Windows Authentication connection to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="4e0c8-110">Para establecer una conexión de autenticación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] debe proporcionar un identificador de inicio de sesión y contraseña de autenticación de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4e0c8-110">To make a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication connection you must supply a SQL Server Authentication login ID and password.</span></span> <span data-ttu-id="4e0c8-111">Al usar el [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] proveedor, debe asociar las [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] credenciales de inicio de sesión a una unidad virtual y, a continuación, usar el comando de cambio de directorio ( `cd` ) para conectarse a esa unidad.</span><span class="sxs-lookup"><span data-stu-id="4e0c8-111">When using the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider, you must associate the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login credentials with a virtual drive, and then use the change directory command (`cd`) to connect to that drive.</span></span> <span data-ttu-id="4e0c8-112">En Windows PowerShell, las credenciales de seguridad solo se pueden asociar con unidades virtuales.</span><span class="sxs-lookup"><span data-stu-id="4e0c8-112">In Windows PowerShell, security credentials can only be associated with virtual drives.</span></span>  
  
##  <a name="sql-server-authentication-using-a-virtual-drive"></a><a name="SQLAuthVirtDrv"></a> <span data-ttu-id="4e0c8-113">Autenticación de SQL Server mediante una unidad virtual</span><span class="sxs-lookup"><span data-stu-id="4e0c8-113">SQL Server Authentication Using a Virtual Drive</span></span>  
 <span data-ttu-id="4e0c8-114">**Para crear una unidad virtual asociada con el inicio de sesión de autenticación de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="4e0c8-114">**To create a virtual drive associated with a SQL Server Authentication login**</span></span>  
  
1.  <span data-ttu-id="4e0c8-115">Crear una función que:</span><span class="sxs-lookup"><span data-stu-id="4e0c8-115">Create a function that:</span></span>  
  
    1.  <span data-ttu-id="4e0c8-116">Tiene parámetros para que el nombre proporcione la unidad virtual, el identificador de inicio de sesión y la ruta de acceso del proveedor para asociarla a la unidad virtual.</span><span class="sxs-lookup"><span data-stu-id="4e0c8-116">Has parameters for the name to give the virtual drive, the login ID, and the provider path to associate with the virtual drive.</span></span>  
  
    2.  <span data-ttu-id="4e0c8-117">Usa `read-host` para solicitar la contraseña al usuario.</span><span class="sxs-lookup"><span data-stu-id="4e0c8-117">Uses `read-host` to prompt the user for the password.</span></span>  
  
    3.  <span data-ttu-id="4e0c8-118">Usa `new-object` para crear un objeto de credenciales.</span><span class="sxs-lookup"><span data-stu-id="4e0c8-118">Uses `new-object` to create a credentials object.</span></span>  
  
    4.  <span data-ttu-id="4e0c8-119">Usa `new-psdrive` para crear una unidad virtual con las credenciales proporcionadas.</span><span class="sxs-lookup"><span data-stu-id="4e0c8-119">Uses `new-psdrive` to create a virtual drive with the supplied credentials.</span></span>  
  
2.  <span data-ttu-id="4e0c8-120">Invocar la función para crear una unidad virtual con las credenciales proporcionadas.</span><span class="sxs-lookup"><span data-stu-id="4e0c8-120">Invoke the function to create a virtual drive with the supplied credentials.</span></span>  
  
### <a name="example-virtual-drive"></a><span data-ttu-id="4e0c8-121">Ejemplo (unidad virtual)</span><span class="sxs-lookup"><span data-stu-id="4e0c8-121">Example (Virtual Drive)</span></span>  
 <span data-ttu-id="4e0c8-122">En este ejemplo se crea una función denominada **sqldrive** que se puede usar para crear una unidad virtual asociada a la instancia e inicio de sesión de la autenticación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] especificados.</span><span class="sxs-lookup"><span data-stu-id="4e0c8-122">This example creates a function named **sqldrive** that you can use to create a virtual drive that is associated with the specified [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication login and instance.</span></span>  
  
 <span data-ttu-id="4e0c8-123">La función **sqldrive** pide que especifique la contraseña para su inicio de sesión, enmascarándola a medida que la escribe.</span><span class="sxs-lookup"><span data-stu-id="4e0c8-123">The **sqldrive** function prompts you to enter the password for your login, masking the password as you type it in.</span></span> <span data-ttu-id="4e0c8-124">Después, siempre que use el comando de cambio de directorio ( `cd` ) para conectarse a una ruta de acceso mediante el nombre de la unidad virtual, todas las operaciones se realizan mediante las [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] credenciales de inicio de sesión de autenticación que proporcionó al crear la unidad.</span><span class="sxs-lookup"><span data-stu-id="4e0c8-124">Then, whenever you use the change directory command (`cd`) to connect to a path by using the virtual drive name, all operations are performed by using the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication login credentials that you supplied when you created the drive.</span></span>  
  
```powershell
## Create a function that specifies the login and prompts for the password.  
  
function sqldrive  
{  
    param( [string]$name, [string]$login = "MyLogin", [string]$root = "SQLSERVER:\SQL\MyComputer\MyInstance" )  
    $pwd = Read-Host -AsSecureString -Prompt "Password"  
    $cred = New-Object System.Management.Automation.PSCredential -argumentlist $login, $pwd  
    New-PSDrive $name -PSProvider SqlServer -Root $root -Credential $cred -Scope 1  
}  
  
## Use the sqldrive function to create a SQLAuth virtual drive.  
sqldrive SQLAuth  
  
## CD to the virtual drive, which invokes the supplied authentication credentials.  
cd SQLAuth  
```  
  
##  <a name="sql-server-authentication-using-invoke-sqlcmd"></a><a name="SQLAuthInvSqlCmd"></a> <span data-ttu-id="4e0c8-125">Autenticación de SQL Server mediante Invoke-Sqlcmd</span><span class="sxs-lookup"><span data-stu-id="4e0c8-125">SQL Server Authentication Using Invoke-Sqlcmd</span></span>  
 <span data-ttu-id="4e0c8-126">**Para usar Invoke-Sqlcmd con la autenticación de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="4e0c8-126">**To use Invoke-Sqlcmd with SQL Server Authentication**</span></span>  
  
1.  <span data-ttu-id="4e0c8-127">Use el parámetro de `-Username` para especificar un identificador de inicio de sesión y el parámetro de `-Password` para especificar la contraseña asociada.</span><span class="sxs-lookup"><span data-stu-id="4e0c8-127">Use the `-Username` parameter to specify a login ID, and the `-Password` parameter to specify the associated password.</span></span>  
  
### <a name="example-invoke-sqlcmd"></a><span data-ttu-id="4e0c8-128">Ejemplo (Invoke-Sqlcmd)</span><span class="sxs-lookup"><span data-stu-id="4e0c8-128">Example (Invoke-Sqlcmd)</span></span>  
 <span data-ttu-id="4e0c8-129">En este ejemplo se usa el cmdlet read-host para pedir al usuario una contraseña, y después se conecta con la autenticación de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4e0c8-129">This example uses the read-host cmdlet to prompt the user for a password, and then connects using SQL Server Authentication.</span></span>  
  
```powershell
## Prompt the user for their password.  
$pwd = Read-Host -AsSecureString -Prompt "Password"  
  
Invoke-Sqlcmd -Query "SELECT GETDATE() AS TimeOfQuery;" -ServerInstance "MyComputer\MyInstance" -Username "MyLogin" -Password $pwd  
```  
  
## <a name="see-also"></a><span data-ttu-id="4e0c8-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4e0c8-130">See Also</span></span>  
 <span data-ttu-id="4e0c8-131">[SQL Server PowerShell](sql-server-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="4e0c8-131">[SQL Server PowerShell](sql-server-powershell.md) </span></span>  
 <span data-ttu-id="4e0c8-132">[Proveedor de SQL Server PowerShell](sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="4e0c8-132">[SQL Server PowerShell Provider](sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="4e0c8-133">cmdlet Invoke-Sqlcmd</span><span class="sxs-lookup"><span data-stu-id="4e0c8-133">Invoke-Sqlcmd cmdlet</span></span>](../database-engine/invoke-sqlcmd-cmdlet.md)  
