---
title: Advertencia sobre el uso del lado cliente de GEOMETRY, Geography y HIERARCHYID | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 500ee6b3-2154-45d2-a3cf-8760166d9413
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 66898aa056800c0a7573b5afa73762785706ff7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672402"
---
# <a name="warning-about-client-side-usage-of-geometry-geography-and-hierarchyid"></a><span data-ttu-id="b14ee-102">Advertencia sobre el uso del lado cliente de GEOMETRY, GEOGRAPHY y HIERARCHYID</span><span class="sxs-lookup"><span data-stu-id="b14ee-102">Warning about client side usage of GEOMETRY, GEOGRAPHY and HIERARCHYID</span></span>
  <span data-ttu-id="b14ee-103">El **Microsoft.SqlServer.Types.dll**de ensamblado, que contiene los tipos de datos espaciales, se ha actualizado de la versión 10,0 a la versión 11,0.</span><span class="sxs-lookup"><span data-stu-id="b14ee-103">The assembly **Microsoft.SqlServer.Types.dll**, which contains the spatial data types, has been upgraded from version 10.0 to version 11.0.</span></span> <span data-ttu-id="b14ee-104">Cuando se cumplan determinadas condiciones, se puede producir un error en las aplicaciones personalizadas que hacen referencia a este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b14ee-104">Custom applications that reference this assembly may fail when certain conditions are true.</span></span>  
  
## <a name="component"></a><span data-ttu-id="b14ee-105">Componente</span><span class="sxs-lookup"><span data-stu-id="b14ee-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="b14ee-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="b14ee-106">Description</span></span>  
 <span data-ttu-id="b14ee-107">El **Microsoft.SqlServer.Types.dll**de ensamblado, que contiene los tipos de datos espaciales, se ha actualizado de la versión 10,0 a la versión 11,0.</span><span class="sxs-lookup"><span data-stu-id="b14ee-107">The assembly **Microsoft.SqlServer.Types.dll**, which contains the spatial data types, has been upgraded from version 10.0 to version 11.0.</span></span> <span data-ttu-id="b14ee-108">Cuando se cumplan las siguientes condiciones, se puede producir un error en las aplicaciones personalizadas que hacen referencia a este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b14ee-108">Custom applications that reference this assembly may fail when the following conditions are true.</span></span>  
  
-   <span data-ttu-id="b14ee-109">Cuando se mueve una aplicación personalizada desde un equipo en el que [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] se instaló en un equipo en el que solo [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] está instalado, se producirá un error en la aplicación porque la versión 10,0 a la que se hace referencia del ensamblado **SqlTypes** no está presente.</span><span class="sxs-lookup"><span data-stu-id="b14ee-109">When you move a custom application from a computer on which [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] was installed to a computer on which only [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] is installed, the application will fail because the referenced version 10.0 of the **SqlTypes** assembly is not present.</span></span> <span data-ttu-id="b14ee-110">Puede aparecer este mensaje de error: `"Could not load file or assembly 'Microsoft.SqlServer.Types, Version=10.0.0.0, Culture=neutral, PublicKeyToken=89845dcd8080cc91' or one of its dependencies. The system cannot find the file specified."`</span><span class="sxs-lookup"><span data-stu-id="b14ee-110">You may see this error message: `"Could not load file or assembly 'Microsoft.SqlServer.Types, Version=10.0.0.0, Culture=neutral, PublicKeyToken=89845dcd8080cc91' or one of its dependencies. The system cannot find the file specified."`</span></span>  
  
-   <span data-ttu-id="b14ee-111">Cuando se hace referencia a la versión 11,0 del ensamblado **SqlTypes** y también se instala la versión 10,0, puede aparecer este mensaje de error:`"System.InvalidCastException: Unable to cast object of type 'Microsoft.SqlServer.Types.SqlGeometry' to type 'Microsoft.SqlServer.Types.SqlGeometry'."`</span><span class="sxs-lookup"><span data-stu-id="b14ee-111">When you reference the **SqlTypes** assembly version 11.0, and version 10.0 is also installed, you may see this error message: `"System.InvalidCastException: Unable to cast object of type 'Microsoft.SqlServer.Types.SqlGeometry' to type 'Microsoft.SqlServer.Types.SqlGeometry'."`</span></span>  
  
-   <span data-ttu-id="b14ee-112">Cuando se hace referencia a la versión 11,0 del ensamblado **SqlTypes** desde una aplicación personalizada que tiene como destino .net 3,5, 4 o 4,5, se producirá un error en la aplicación porque SqlClient by Design carga la versión 10,0 del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b14ee-112">When you reference the **SqlTypes** assembly version 11.0 from a custom application that targets .NET 3.5, 4, or 4.5, the application will fail because SqlClient by design loads version 10.0 of the assembly.</span></span> <span data-ttu-id="b14ee-113">Este error se produce cuando la aplicación llama a uno de los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="b14ee-113">This failure occurs when the application calls one of the following methods:</span></span>  
  
    -   <span data-ttu-id="b14ee-114">método `GetValue` de la clase `SqlDataReader`</span><span class="sxs-lookup"><span data-stu-id="b14ee-114">`GetValue` method of the `SqlDataReader` class</span></span>  
  
    -   <span data-ttu-id="b14ee-115">método `GetValues` de la clase `SqlDataReader`</span><span class="sxs-lookup"><span data-stu-id="b14ee-115">`GetValues` method of the `SqlDataReader` class</span></span>  
  
    -   <span data-ttu-id="b14ee-116">operador de índice de corchete [] de la clase `SqlDataReader`</span><span class="sxs-lookup"><span data-stu-id="b14ee-116">bracket index operator [] of the `SqlDataReader` class</span></span>  
  
    -   <span data-ttu-id="b14ee-117">método `ExecuteScalar` de la clase `SqlCommand`</span><span class="sxs-lookup"><span data-stu-id="b14ee-117">`ExecuteScalar` method of the `SqlCommand` class</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="b14ee-118">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="b14ee-118">Corrective Action</span></span>  
 <span data-ttu-id="b14ee-119">Puede solucionar este problema si usa uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b14ee-119">You can work around this issue by using one of the following methods:</span></span>  
  
-   <span data-ttu-id="b14ee-120">Puede solucionar este problema en el código si llama al método `GetSqlBytes`, en lugar de los métodos Get enumerados anteriormente, para recuperar los tipos de sistema [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de CLR, tal como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b14ee-120">You can work around this issue in your code by calling the `GetSqlBytes` method, instead of the Get methods listed above, to retrieve CLR [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system types, as shown in the following example:</span></span>  
  
    ```csharp  
    string query = "SELECT [SpatialColumn] FROM [SpatialTable]";  
          using (SqlConnection conn = new SqlConnection("..."))  
          {  
                SqlCommand cmd = new SqlCommand(query, conn);  
  
                conn.Open();  
                SqlDataReader reader = cmd.ExecuteReader();  
  
                while (reader.Read())  
                {  
                      // In version 11.0 only  
                      SqlGeometry g =   
    SqlGeometry.Deserialize(reader.GetSqlBytes(0));  
  
                      // In version 10.0 or 11.0  
                      SqlGeometry g2 = new SqlGeometry();  
                      g.Read(new BinaryReader(reader.GetSqlBytes(0).Stream));  
                }  
          }  
    ```  
  
-   <span data-ttu-id="b14ee-121">Puede solucionar este problema mediante el redireccionamiento de ensamblado en el archivo de configuración de la aplicación, tal como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b14ee-121">You can work around this issue by using assembly redirection in the application configuration file, as shown in the following example:</span></span>  
  
    ```xml  
    <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
        ...  
        <dependentAssembly>  
            <assemblyIdentity name="Microsoft.SqlServer.Types" publicKeyToken="89845dcd8080cc91" culture="neutral" />  
            <bindingRedirect oldVersion="10.0.0.0" newVersion="11.0.0.0" />  
        </dependentAssembly>  
        ...  
    </assemblyBinding>  
    ```  
  
-   <span data-ttu-id="b14ee-122">Puede solucionar esta problema en la cadena de conexión si especifica el valor "SQL Server 2012" para el atributo "Type System Version" para forzar que SqlClient cargue la versión 11.0 del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b14ee-122">You can work around this issue in your connection string by specifying a value of "SQL Server 2012" for the "Type System Version" attribute to force SqlClient to load version 11.0 of the assembly.</span></span> <span data-ttu-id="b14ee-123">Este atributo de cadena de conexión solo está disponible en .NET 4.5 y posterior.</span><span class="sxs-lookup"><span data-stu-id="b14ee-123">This connection string attribute is available only in .NET 4.5 and above.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b14ee-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b14ee-124">See Also</span></span>  
 <span data-ttu-id="b14ee-125">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="b14ee-125">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="b14ee-126">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="b14ee-126">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md
)  
  
  
