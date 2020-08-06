---
title: Representación de base de datos (tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: 16a233fb-f83b-4ca1-acb5-6186eca0a62c
author: minewiskan
ms.author: owend
ms.openlocfilehash: c327e07685e98e6fa9f992025510e869d909e5ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671224"
---
# <a name="database-representationtabular"></a><span data-ttu-id="88e89-102">Representación de la base de datos (tabular)</span><span class="sxs-lookup"><span data-stu-id="88e89-102">Database Representation(Tabular)</span></span>
  <span data-ttu-id="88e89-103">En el modo tabular, la base de datos es el contenedor de todos los objetos del modelo tabular.</span><span class="sxs-lookup"><span data-stu-id="88e89-103">In Tabular Mode, the database is the container for all objects in the tabular model.</span></span>  
  
## <a name="database-representation"></a><span data-ttu-id="88e89-104">Representación de la base de datos</span><span class="sxs-lookup"><span data-stu-id="88e89-104">Database Representation</span></span>  
 <span data-ttu-id="88e89-105">La base de datos es el lugar donde residen todos los objetos que forman un modelo tabular.</span><span class="sxs-lookup"><span data-stu-id="88e89-105">The database is the place where all objects that form a tabular model reside.</span></span> <span data-ttu-id="88e89-106">Contenidos en la base de datos, el desarrollador encuentra objetos como conexiones, tablas, roles y muchos otros.</span><span class="sxs-lookup"><span data-stu-id="88e89-106">Contained by the database, the developer finds objects like connections, tables, roles and many more.</span></span>  
  
### <a name="database-in-amo"></a><span data-ttu-id="88e89-107">Base de datos en AMO</span><span class="sxs-lookup"><span data-stu-id="88e89-107">Database in AMO</span></span>  
 <span data-ttu-id="88e89-108">Cuando use AMO para administrar una base de datos de modelo tabular, el objeto <xref:Microsoft.AnalysisServices.Database> de AMO coincide de forma unívoca con el objeto lógico de base de datos de un modelo tabular.</span><span class="sxs-lookup"><span data-stu-id="88e89-108">When using AMO to manage a tabular model database, the <xref:Microsoft.AnalysisServices.Database> object in AMO matches one-to-one the database logical object in a tabular model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="88e89-109">Para obtener acceso a un objeto de base de datos, en AMO, el usuario necesita tener acceso a un objeto de servidor y conectarse a él.</span><span class="sxs-lookup"><span data-stu-id="88e89-109">In order to gain access to a database object, in AMO, the user needs to have access to a server object and connect to it.</span></span>  
  
### <a name="database-in-adomdnet"></a><span data-ttu-id="88e89-110">Base de datos en ADOMD.Net</span><span class="sxs-lookup"><span data-stu-id="88e89-110">Database in ADOMD.Net</span></span>  
 <span data-ttu-id="88e89-111">Cuando se usa ADOMD para consultar una base de datos de modelo tabular, la conexión con una base de datos específica se obtiene a través del objeto <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection>.</span><span class="sxs-lookup"><span data-stu-id="88e89-111">When using ADOMD to consult and query a tabular model database, connection to a specific database is obtained through the <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection> object.</span></span>  
  
 <span data-ttu-id="88e89-112">Puede conectarse directamente a una base de datos determinada mediante el fragmento de código siguiente:</span><span class="sxs-lookup"><span data-stu-id="88e89-112">You can connect directly to a certain database using the following code snippet:</span></span>  
  
```csharp  
using ADOMD = Microsoft.AnalysisServices.AdomdClient;  
...  
   ADOMD.AdomdConnection currrentCnx = new ADOMD.AdomdConnection("Data Source=<<server\instance>>;Catalog=<<database>>");  
   currrentCnx.Open();  
...  
  
```  
  
 <span data-ttu-id="88e89-113">Además, en un objeto de conexión existente (que no se ha cerrado) puede cambiar la base de datos actual por otra como se muestra en el fragmento de código siguiente:</span><span class="sxs-lookup"><span data-stu-id="88e89-113">Also, over an existing connection object (that hasn't been closed), you can change the current database to another as shown in the following code snippet:</span></span>  
  
```csharp  
currentCnx.ChangeDatabase("myOtherDatabase");  
  
```  
  
## <a name="database-in-amo"></a><span data-ttu-id="88e89-114">Base de datos en AMO</span><span class="sxs-lookup"><span data-stu-id="88e89-114">Database in AMO</span></span>  
 <span data-ttu-id="88e89-115">Cuando se usa AMO para administrar un objeto de base de datos, comience con un objeto <xref:Microsoft.AnalysisServices.Server>.</span><span class="sxs-lookup"><span data-stu-id="88e89-115">When using AMO to manage a database object, start with a <xref:Microsoft.AnalysisServices.Server> object.</span></span> <span data-ttu-id="88e89-116">Después, busque la base de datos en la colección de bases de datos o cree una nueva base de datos agregando una a la colección.</span><span class="sxs-lookup"><span data-stu-id="88e89-116">Then search for your database in the databases collection or create a new database by adding one to the collection.</span></span>  
  
 <span data-ttu-id="88e89-117">En el siguiente fragmento de código se muestran los pasos para conectarse a un servidor y crear una base de datos vacía, después de comprobar que la base de datos no existe:</span><span class="sxs-lookup"><span data-stu-id="88e89-117">The following code snippet shows the steps to connect to a server and create an empty database, after checking the database doesn't exist:</span></span>  
  
```  
  
AMO.Server CurrentServer = new AMO.Server();  
try  
{  
    CurrentServer.Connect(currentServerName);  
}  
catch (Exception cnxException)  
{  
    MessageBox.Show(string.Format("Error while trying to connect to server: [{0}]\nError message: {1}", currentServerName, cnxException.Message), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
    return;  
}  
newDatabaseName = DatabaseName.Text;  
if (CurrentServer.Databases.Contains(newDatabaseName))  
{  
    return;  
}  
try  
{  
    AMO.Database newDatabase = CurrentServer.Databases.Add(newDatabaseName);  
  
    CurrentServer.Update();  
}  
catch (Exception createDBxc)  
{  
    MessageBox.Show(String.Format("Database [{0}] couldn't be created.\n{1}", newDatabaseName, createDBxc.Message), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
    newDatabaseAvailable = false;  
}  
  
```  
  
 <span data-ttu-id="88e89-118">Para saber de forma práctica cómo usar AMO para crear y tratar representaciones de bases de datos, vea el código fuente del ejemplo AMO 2012 tabular; en concreto, examine el siguiente archivo de código fuente: Database.cs.</span><span class="sxs-lookup"><span data-stu-id="88e89-118">For a practical understanding on how to use AMO to create and manipulate database representations, see source code in the Tabular AMO 2012 sample; specifically check in the following source file: Database.cs.</span></span> <span data-ttu-id="88e89-119">El código de ejemplo se proporciona únicamente como apoyo a los conceptos lógicos explicados aquí y no se debe usar en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="88e89-119">Sample code is provided only as a support to the logical concepts explained here, and should not be used in a production environment.</span></span>  
  
  
