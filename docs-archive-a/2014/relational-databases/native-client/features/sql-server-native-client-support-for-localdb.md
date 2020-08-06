---
title: Compatibilidad de SQL Server Native Client con LocalDB | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 127569d1-a9f7-49bf-a561-c084986a8871
author: rothja
ms.author: jroth
ms.openlocfilehash: b08ea46e8db1b665280116a439b95748f69d03ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670355"
---
# <a name="sql-server-native-client-support-for-localdb"></a><span data-ttu-id="1bda4-102">Compatibilidad de SQL Server Native Client con LocalDB</span><span class="sxs-lookup"><span data-stu-id="1bda4-102">SQL Server Native Client Support for LocalDB</span></span>
  <span data-ttu-id="1bda4-103">A partir de [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], estará disponible una versión ligera de SQL Server, denominada LocalDB.</span><span class="sxs-lookup"><span data-stu-id="1bda4-103">Beginning in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], a lightweight version of SQL Server, called LocalDB, will be available.</span></span> <span data-ttu-id="1bda4-104">En este tema se describe cómo conectarse a una base de datos en una instancia de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="1bda4-104">This topic discusses how to connect to a database in a LocalDB instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1bda4-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1bda4-105">Remarks</span></span>  
 <span data-ttu-id="1bda4-106">Para obtener más información acerca de LocalDB, incluyendo cómo instalarlo y configurar la instancia de LocalDB, vea:</span><span class="sxs-lookup"><span data-stu-id="1bda4-106">For more information about LocalDB, including how to install LocalDB and configure your LocalDB instance, see:</span></span>  
  
-   [<span data-ttu-id="1bda4-107">Referencia de SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="1bda4-107">SQL Server Express LocalDB Reference</span></span>](../../sql-server-express-localdb-reference.md)  
  
-   [<span data-ttu-id="1bda4-108">SQL Server 2014 Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="1bda4-108">SQL Server 2014 Express LocalDB</span></span>](../../../database-engine/configure-windows/sql-server-2016-express-localdb.md)  
  
 <span data-ttu-id="1bda4-109">En resumen, LocalDB permite:</span><span class="sxs-lookup"><span data-stu-id="1bda4-109">To summarize, LocalDB allows you to:</span></span>  
  
-   <span data-ttu-id="1bda4-110">Usar `sqllocaldb.exe i` para detectar el nombre de la instancia predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1bda4-110">Use `sqllocaldb.exe i` to discover the name of the default instance.</span></span>  
  
-   <span data-ttu-id="1bda4-111">Usar la palabra clave de la cadena de conexión de `AttachDBFilename` para especificar a qué el archivo de base de datos se debe adjuntar el servidor.</span><span class="sxs-lookup"><span data-stu-id="1bda4-111">Use the `AttachDBFilename` connection string keyword to specify which database file the server should attach.</span></span> <span data-ttu-id="1bda4-112">Cuando `AttachDBFilename` se usa, si no se especifica el nombre de la base de datos con la palabra clave de la cadena de conexión de **base de datos** , la base de datos se quitará de la instancia de LocalDB cuando se cierre la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1bda4-112">When using `AttachDBFilename`, if you do not specify the name of the database with the **Database** connection string keyword, the database will be removed from the LocalDB instance when the application closes.</span></span>  
  
-   <span data-ttu-id="1bda4-113">Especifique una instancia de LocalDB en la cadena de conexión:</span><span class="sxs-lookup"><span data-stu-id="1bda4-113">Specify a LocalDB instance in your connection string:</span></span>  
  
```  
SERVER=(localdb)\v11.0  
```  
  
 <span data-ttu-id="1bda4-114">Si fuera necesario, puede crear una instancia de LocalDB con sqllocaldb.exe.</span><span class="sxs-lookup"><span data-stu-id="1bda4-114">If necessary, you can create a LocalDB instance with sqllocaldb.exe.</span></span> <span data-ttu-id="1bda4-115">También puede utilizar sqlcmd.exe para agregar y modificar las bases de datos de una instancia de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="1bda4-115">You can also use sqlcmd.exe to add and modify databases in a LocalDB instance.</span></span> <span data-ttu-id="1bda4-116">Por ejemplo, `sqlcmd -S (localdb)\v11.0`.</span><span class="sxs-lookup"><span data-stu-id="1bda4-116">For example, `sqlcmd -S (localdb)\v11.0`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bda4-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1bda4-117">See Also</span></span>  
 [<span data-ttu-id="1bda4-118">Características de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="1bda4-118">SQL Server Native Client Features</span></span>](sql-server-native-client-features.md)  
  
  
