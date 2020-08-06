---
title: SQL Server Express la información de encabezado y versión de LocalDB | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_location:
- sqluserinstance.dll
ms.assetid: 506b5161-b902-4894-b87b-9192d7b1664a
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 138081852cf505b03265fd9c5f39eae6ed2af39b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677118"
---
# <a name="sql-server-express-localdb-header-and-version-information"></a><span data-ttu-id="3dacd-102">Información de encabezado y versión de SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="3dacd-102">SQL Server Express LocalDB Header and Version Information</span></span>
  <span data-ttu-id="3dacd-103">No hay ningún archivo de encabezado independiente para la API de instancia de SQL Server Express LocalDB; las firmas de función y los códigos de error de LocalDB se definen en el archivo de encabezado de SQL Server Native Client (sqlncli.h).</span><span class="sxs-lookup"><span data-stu-id="3dacd-103">There is no separate header file for the SQL Server Express LocalDB instance API; the LocalDB function signatures and error codes are defined in the SQL Server Native Client header file (sqlncli.h).</span></span> <span data-ttu-id="3dacd-104">Para utilizar la instancia API de LocalDB, debe incluir el archivo de encabezado sqlncli.h en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="3dacd-104">To use the LocalDB instance API, you must include the sqlncli.h header file in your project.</span></span>  
  
## <a name="localdb-versioning"></a><span data-ttu-id="3dacd-105">Versión de LocalDB</span><span class="sxs-lookup"><span data-stu-id="3dacd-105">LocalDB Versioning</span></span>  
 <span data-ttu-id="3dacd-106">La instalación de LocalDB utiliza un conjunto único de archivos binarios por versión principal de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3dacd-106">The LocalDB installation uses a single set of binaries per major SQL Server version.</span></span> <span data-ttu-id="3dacd-107">Estas versiones de LocalDB se mantienen y se revisan de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="3dacd-107">These LocalDB versions are maintained and patched independently.</span></span> <span data-ttu-id="3dacd-108">Esto significa que el usuario tiene que especificar la versión de línea base de LocalDB (es decir, la versión principal de SQL Server) que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="3dacd-108">This means that the user has to specify which LocalDB baseline release (that is, major SQL Server version) he or she will be using.</span></span> <span data-ttu-id="3dacd-109">La versión se especifica en el formato de versión estándar definido por la clase .NET Framework **System. version** :</span><span class="sxs-lookup"><span data-stu-id="3dacd-109">The version is specified in the standard version format defined by the .NET Framework **System.Version** class:</span></span>  
  
 <span data-ttu-id="3dacd-110">*principal.secundario[.de compilación[.de revisión]]*</span><span class="sxs-lookup"><span data-stu-id="3dacd-110">*major.minor[.build[.revision]]*</span></span>  
  
 <span data-ttu-id="3dacd-111">Los dos primeros números de la cadena de versión (*principal* y *secundaria*) son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="3dacd-111">The first two numbers in the version string (*major* and *minor*) are mandatory.</span></span> <span data-ttu-id="3dacd-112">Los dos últimos números en la cadena de versión (*compilación* y *revisión*) son opcionales y tienen como valor predeterminado cero si el usuario los deja fuera. Esto significa que si el usuario especifica solo "12,2" como número de versión de LocalDB, se tratará como si el usuario hubiera especificado "12.2.0.0".</span><span class="sxs-lookup"><span data-stu-id="3dacd-112">The last two numbers in the version string (*build* and *revision*) are optional and default to zero if the user leaves them out. This means that if the user specifies only "12.2" as the LocalDB version number, it will be treated as if the user specified "12.2.0.0".</span></span>  
  
 <span data-ttu-id="3dacd-113">La versión para la instalación de LocalDB se define en la clave del Registro MSSQLServer\CurrentVersion en la clave del Registro de la instancia de SQL Server, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3dacd-113">The version for the LocalDB installation is defined in the MSSQLServer\CurrentVersion registry key under the SQL Server instance registry key, for example:</span></span>  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\MSSQL12E.LOCALDB\ MSSQLServer\CurrentVersion: "CurrentVersion"="12.0.2531.0"  
```  
  
 <span data-ttu-id="3dacd-114">Si hay varias versiones de LocalDB en la misma estación de trabajo, se admiten en paralelo.</span><span class="sxs-lookup"><span data-stu-id="3dacd-114">Multiple LocalDB versions on the same workstation are supported side-by-side.</span></span> <span data-ttu-id="3dacd-115">Sin embargo, el código de usuario siempre usa la dll de **SQLUserInstance** disponible más reciente en el equipo local para conectarse a las instancias de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="3dacd-115">However, user code always uses the latest available **SQLUserInstance** DLL on the local computer to connect to LocalDB instances.</span></span>  
  
## <a name="locating-the-sqluserinstance-dll"></a><span data-ttu-id="3dacd-116">Localizar la DLL de SQLUserInstance</span><span class="sxs-lookup"><span data-stu-id="3dacd-116">Locating the SQLUserInstance DLL</span></span>  
 <span data-ttu-id="3dacd-117">Para buscar el archivo dll de **SQLUserInstance** , el proveedor de cliente utiliza la siguiente clave del registro:</span><span class="sxs-lookup"><span data-stu-id="3dacd-117">To locate the **SQLUserInstance** DLL, the client provider uses the following registry key:</span></span>  
  
```  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server Local DB\Installed Versions]  
```  
  
 <span data-ttu-id="3dacd-118">En esta clave hay una lista de claves, una para cada versión de LocalDB que se haya instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="3dacd-118">Under this key there is a list of keys, one for each version of LocalDB installed on the computer.</span></span> <span data-ttu-id="3dacd-119">Cada una de estas claves se denomina con el número de versión de LocalDB en el formato *\<major-version>* .*\<minor-version>*</span><span class="sxs-lookup"><span data-stu-id="3dacd-119">Each of these keys is named with the LocalDB version number in the format *\<major-version>*.*\<minor-version>*</span></span> <span data-ttu-id="3dacd-120">(por ejemplo, la clave de [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] se denomina 12,0).</span><span class="sxs-lookup"><span data-stu-id="3dacd-120">(for example, the key for [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] is named 12.0).</span></span> <span data-ttu-id="3dacd-121">En cada clave de la versión hay un par nombre-valor `InstanceAPIPath` que definen la ruta completa al archivo SQLUserInstance.dll que se haya instalado con esa versión.</span><span class="sxs-lookup"><span data-stu-id="3dacd-121">Under each version key there is an `InstanceAPIPath` name-value pair that defines the full path to the SQLUserInstance.dll file installed with that version.</span></span> <span data-ttu-id="3dacd-122">En el siguiente ejemplo se muestran las entradas del Registro para un equipo con las versiones de LocalDB 11.0 y 12.0 instaladas:</span><span class="sxs-lookup"><span data-stu-id="3dacd-122">The following example shows the registry entries for a computer that has LocalDB versions 11.0 and 12.0 installed:</span></span>  
  
```  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server Local DB\Installed Versions\12.0]  
"InstanceAPIPath"="C:\\Program Files\\Microsoft SQL Server\\120\\LocalDB\\Binn\\SqlUserInstance.dll"  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server Local DB\Installed Versions\12.0]  
"InstanceAPIPath"="C:\\Program Files\\Microsoft SQL Server\\120\\LocalDB\\Binn\\SqlUserInstance.dll"]  
```  
  
 <span data-ttu-id="3dacd-123">El proveedor de cliente debe encontrar la última versión entre todas las versiones instaladas y cargar el archivo dll de **SQLUserInstance** desde el `InstanceAPIPath` valor asociado.</span><span class="sxs-lookup"><span data-stu-id="3dacd-123">The client provider must find the latest version among all installed versions and load the **SQLUserInstance** DLL file from the associated `InstanceAPIPath` value.</span></span>  
  
### <a name="wow64-mode-on-64-bit-windows"></a><span data-ttu-id="3dacd-124">Modo WOW64 en Windows de 64 bits</span><span class="sxs-lookup"><span data-stu-id="3dacd-124">WOW64 Mode on 64-bit Windows</span></span>  
 <span data-ttu-id="3dacd-125">Las instalaciones de 64 bits de LocalDB tendrán un conjunto adicional de claves del Registro para que las aplicaciones de 32 bits que se ejecutan en el modo de Windows de 32 bits sobre Windows de 64 bits (WOW64) puedan utilizar LocalDB.</span><span class="sxs-lookup"><span data-stu-id="3dacd-125">64-bit installations of LocalDB will have an additional set of registry keys to allow 32-bit applications running in Windows-32-on-Windows-64 (WOW64) mode to use LocalDB.</span></span> <span data-ttu-id="3dacd-126">Concretamente, en Windows de 64 bits, el MSI de LocalDB creará las claves del Registro siguientes:</span><span class="sxs-lookup"><span data-stu-id="3dacd-126">Specifically, on 64-bit Windows, the LocalDB MSI will create the following registry keys:</span></span>  
  
```  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Wow6432Node\Microsoft SQL Server Local DB\Installed Versions\12.0]  
"InstanceAPIPath"="C:\\Program Files (x86)\\Microsoft SQL Server\\120\\LocalDB\\Binn\\SqlUserInstance.dll"  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Wow6432Node\Microsoft SQL Server Local DB\Installed Versions\12.0]  
"InstanceAPIPath"="C:\\Program Files (x86)\\Microsoft SQL Server\\120\\LocalDB\\Binn\\SqlUserInstance.dll"]  
  
```  
  
 <span data-ttu-id="3dacd-127">los programas de 64 bits que leen la `Installed Versions` clave verán valores que señalan a versiones de 64 bits de la dll de **SQLUserInstance** , mientras que los programas de 32 bits (que se ejecutan en Windows de 64 bits en modo WOW64) se redirigirán automáticamente a una `Installed Versions` clave ubicada en el `Wow6432Node` subárbol.</span><span class="sxs-lookup"><span data-stu-id="3dacd-127">64-bit programs reading the `Installed Versions` key will see values pointing to 64-bit versions of the **SQLUserInstance** DLL, while 32-bit programs (running on 64-bit Windows in WOW64 mode) will be automatically redirected to an `Installed Versions` key located under the `Wow6432Node` hive.</span></span> <span data-ttu-id="3dacd-128">Esta clave contiene valores que apuntan a las versiones de 32 bits de la dll de **SQLUserInstance** .</span><span class="sxs-lookup"><span data-stu-id="3dacd-128">This key contains values pointing to 32-bit versions of the **SQLUserInstance** DLL.</span></span>  
  
## <a name="using-localdb_define_proxy_functions"></a><span data-ttu-id="3dacd-129">Uso de LOCALDB_DEFINE_PROXY_FUNCTIONS</span><span class="sxs-lookup"><span data-stu-id="3dacd-129">Using LOCALDB_DEFINE_PROXY_FUNCTIONS</span></span>  
 <span data-ttu-id="3dacd-130">La API de instancia de LocalDB define una constante denominada LOCALDB_DEFINE_PROXY_FUNCTIONS que automatiza la detección y carga de la dll de **SqlUserInstance** .</span><span class="sxs-lookup"><span data-stu-id="3dacd-130">The LocalDB instance API defines a constant named LOCALDB_DEFINE_PROXY_FUNCTIONS that automates the discovery and loading of the **SqlUserInstance** DLL.</span></span>  
  
 <span data-ttu-id="3dacd-131">La sección de código que se habilita a través de esta constante proporciona una implementación de servidores proxy para cada una de las API de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="3dacd-131">The section of code enabled by this constant provides an implementation of proxies for each of the LocalDB APIs.</span></span> <span data-ttu-id="3dacd-132">Las implementaciones de proxy usan una función común para enlazar con los puntos de entrada del archivo dll de **SqlUserInstance** instalado más reciente y, a continuación, reenviar las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="3dacd-132">The proxy implementations use a common function to bind to entry points in the latest installed **SqlUserInstance** DLL, and then forward the requests.</span></span>  
  
 <span data-ttu-id="3dacd-133">Se habilitan las características del servidor proxy únicamente si la constante LOCALDB_DEFINE_PROXY_FUNCTIONS se ha definido en el código de usuario antes de incluir el archivo sqlncli.h.</span><span class="sxs-lookup"><span data-stu-id="3dacd-133">The proxy functions are enabled only if the constant LOCALDB_DEFINE_PROXY_FUNCTIONS is defined in the user code before including the sqlncli.h file.</span></span> <span data-ttu-id="3dacd-134">La constante debe estar definida en tan solo un módulo de origen (archivo .cpp) porque define los nombres de función externa para todos los puntos de entrada de la API.</span><span class="sxs-lookup"><span data-stu-id="3dacd-134">The constant should be defined in only one source module (.cpp file) because it defines external function names for all of the API entry points.</span></span> <span data-ttu-id="3dacd-135">Proporciona una implementación de servidores proxy para cada una de las API de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="3dacd-135">It provides an implementation of proxies for each of the LocalDB APIs.</span></span>  
  
 <span data-ttu-id="3dacd-136">El ejemplo de código siguiente muestra cómo utilizar la macro a partir de código C++ nativo:</span><span class="sxs-lookup"><span data-stu-id="3dacd-136">The following code example shows how to use the macro from the native C++ code:</span></span>  
  
```  
// Define the LOCALDB_DEFINE_PROXY_FUNCTIONS constant to enable the LocalDB proxy functions   
// The #define has to take place BEFORE the API header file (sqlncli.h) is included  
#define LOCALDB_DEFINE_PROXY_FUNCTIONS  
#include <sqlncli.h>  
...  
HRESULT hr = S_OK;  
  
// Create LocalDB instance by calling the create API proxy function included by macro  
if (FAILED(hr = LocalDBCreateInstance( L"12.0", L"name", 0)))  
{  
...  
}  
...  
  
```  
  
  
