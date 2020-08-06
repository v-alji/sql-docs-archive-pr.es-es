---
title: Administrador de conexiones OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- OLE DB connection manager
- data sources [Integration Services], connections
- connection managers [Integration Services], OLE DB
- connections [Integration Services], OLE DB
ms.assetid: 91e3622e-4b1a-439a-80c7-a00b90d66979
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5431de956a1039c2978688982792f190b0abc544
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674260"
---
# <a name="ole-db-connection-manager"></a><span data-ttu-id="b5af4-102">OLE DB, administrador de conexiones</span><span class="sxs-lookup"><span data-stu-id="b5af4-102">OLE DB Connection Manager</span></span>
  <span data-ttu-id="b5af4-103">Un administrador de conexiones OLE DB permite a un paquete conectarse a un origen de datos mediante un proveedor OLE DB.</span><span class="sxs-lookup"><span data-stu-id="b5af4-103">An OLE DB connection manager enables a package to connect to a data source by using an OLE DB provider.</span></span> <span data-ttu-id="b5af4-104">Por ejemplo, un administrador de conexiones OLE DB que se conecta a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] puede usar el proveedor [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b5af4-104">For example, an OLE DB connection manager that connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can use the [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b5af4-105">El proveedor OLE DB de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client 11.0 no admite las nuevas palabras clave de cadena de conexión (MultiSubnetFailover=True) para la agrupación en clústeres de conmutación por error de varias subredes.</span><span class="sxs-lookup"><span data-stu-id="b5af4-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client 11.0 OLEDB provider does not support the new connection string key words (MultiSubnetFailover=True) for Multi-Subnet Failover Clustering.</span></span> <span data-ttu-id="b5af4-106">Para obtener más información, consulte las notas de la [versión de SQL Server](https://go.microsoft.com/fwlink/?LinkId=247824) y la entrada de blog, [conmutación por error de múltiples subredes AlwaysOn y SSIS](https://www.mattmasson.com/2012/03/alwayson-multi-subnet-failover-and-ssis/), en www.mattmasson.com.</span><span class="sxs-lookup"><span data-stu-id="b5af4-106">For more information, see the [SQL Server Release  Notes](https://go.microsoft.com/fwlink/?LinkId=247824) and the blog post, [AlwaysOn Multi-Subnet Failover and SSIS](https://www.mattmasson.com/2012/03/alwayson-multi-subnet-failover-and-ssis/), on www.mattmasson.com.</span></span>  
  
 <span data-ttu-id="b5af4-107">Varias [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] tareas y componentes de flujo de datos usan un administrador de conexiones de OLE DB.</span><span class="sxs-lookup"><span data-stu-id="b5af4-107">Several [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] tasks and data flow components use an OLE DB connection manager.</span></span> <span data-ttu-id="b5af4-108">Por ejemplo, un origen de OLE DB y un destino de OLE DB usan este administrador de conexiones para extraer y cargar datos, y la tarea Ejecutar SQL puede usar este administrador de conexiones para conectarse a una base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ejecutar consultas.</span><span class="sxs-lookup"><span data-stu-id="b5af4-108">For example, the OLE DB source and OLE DB destination use this connection manager to extract and load data, and the Execute SQL task can use this connection manager to connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database to run queries.</span></span>  
  
 <span data-ttu-id="b5af4-109">El administrador de conexiones OLE DB también se usa para obtener acceso a orígenes de datos OLE DB en tareas personalizadas escritas en código no administrado que usa un lenguaje como, por ejemplo, C++.</span><span class="sxs-lookup"><span data-stu-id="b5af4-109">The OLE DB connection manager is also used to access OLE DB data sources in custom tasks written in unmanaged code that uses a language such as C++.</span></span>  
  
 <span data-ttu-id="b5af4-110">Cuando agrega un administrador de conexiones OLE DB a un paquete, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] crea un administrador de conexiones que se resuelve como una conexión OLE DB en tiempo de ejecución, establece las propiedades del administrador de conexiones y agrega el administrador de conexiones a la colección `Connections` del paquete.</span><span class="sxs-lookup"><span data-stu-id="b5af4-110">When you add an OLE DB connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to an OLE DB connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span>  
  
 <span data-ttu-id="b5af4-111">La propiedad `ConnectionManagerType` del administrador de conexiones se establece en `OLEDB`.</span><span class="sxs-lookup"><span data-stu-id="b5af4-111">The `ConnectionManagerType` property of the connection manager is set to `OLEDB`.</span></span>  
  
 <span data-ttu-id="b5af4-112">El administrador de conexiones OLE DB se puede configurar de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="b5af4-112">The OLE DB connection manager can be configured in the following ways:</span></span>  
  
-   <span data-ttu-id="b5af4-113">Proporcionar una cadena de conexión específica configurada para cumplir con los requisitos del proveedor seleccionado.</span><span class="sxs-lookup"><span data-stu-id="b5af4-113">Provide a specific connection string configured to meet the requirements of the selected provider.</span></span>  
  
-   <span data-ttu-id="b5af4-114">Según el proveedor, incluir el nombre del origen de datos al cual conectarse.</span><span class="sxs-lookup"><span data-stu-id="b5af4-114">Depending on the provider, include the name of the data source to connect to.</span></span>  
  
-   <span data-ttu-id="b5af4-115">Proporcionar credenciales de seguridad según resulte apropiado para el proveedor seleccionado.</span><span class="sxs-lookup"><span data-stu-id="b5af4-115">Provide security credentials as appropriate for the selected provider.</span></span>  
  
-   <span data-ttu-id="b5af4-116">Indicar si la conexión creada desde el administrador de conexiones se conserva en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b5af4-116">Indicate whether the connection that is created from the connection manager is retained at run time.</span></span>  
  
## <a name="logging"></a><span data-ttu-id="b5af4-117">Registro</span><span class="sxs-lookup"><span data-stu-id="b5af4-117">Logging</span></span>  
 <span data-ttu-id="b5af4-118">Puede registrar las llamadas realizadas por el administrador de conexiones OLE DB a proveedores de datos externos.</span><span class="sxs-lookup"><span data-stu-id="b5af4-118">You can log the calls that the OLE DB connection manager makes to external data providers.</span></span> <span data-ttu-id="b5af4-119">Puede utilizar esta capacidad de registro para solucionar problemas relacionados con las conexiones que el administrador de conexiones OLE DB establece con orígenes de datos externos.</span><span class="sxs-lookup"><span data-stu-id="b5af4-119">You can use this logging capability to troubleshoot the connections that the OLE DB connection manager makes to external data sources.</span></span> <span data-ttu-id="b5af4-120">Para registrar las llamadas que el administrador de conexiones OLE DB realiza a proveedores de datos externos, habilite el registro de paquetes y seleccione el evento **Diagnostic** en el nivel de paquete.</span><span class="sxs-lookup"><span data-stu-id="b5af4-120">To log the calls that the OLE DB connection manager makes to external data providers, enable package logging and select the **Diagnostic** event at the package level.</span></span> <span data-ttu-id="b5af4-121">Para más información, vea [Herramientas para solucionar problemas con la ejecución de paquetes](../troubleshooting/troubleshooting-tools-for-package-execution.md).</span><span class="sxs-lookup"><span data-stu-id="b5af4-121">For more information, see [Troubleshooting Tools for Package Execution](../troubleshooting/troubleshooting-tools-for-package-execution.md).</span></span>  
  
## <a name="configuration-of-the-oledb-connection-manager"></a><span data-ttu-id="b5af4-122">Configuración del administrador de conexiones OLE DB</span><span class="sxs-lookup"><span data-stu-id="b5af4-122">Configuration of the OLEDB Connection Manager</span></span>  
 <span data-ttu-id="b5af4-123">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="b5af4-123">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span> <span data-ttu-id="b5af4-124">Para obtener más información sobre las propiedades que puede configurar en el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] , vea [Configurar el administrador de conexiones OLE DB](../configure-ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="b5af4-124">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [Configure OLE DB Connection Manager](../configure-ole-db-connection-manager.md).</span></span> <span data-ttu-id="b5af4-125">Para obtener información acerca de cómo configurar un administrador de conexiones mediante programación, vea la documentación de la clase **T:Microsoft.SqlServer.Dts.Runtime.ConnectionManager** en la Guía del desarrollador.</span><span class="sxs-lookup"><span data-stu-id="b5af4-125">For information about configuring a connection manager programmatically, see the documentation for **T:Microsoft.SqlServer.Dts.Runtime.ConnectionManager** class in the Developer Guide.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="b5af4-126">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="b5af4-126">Related Content</span></span>  
  
-   <span data-ttu-id="b5af4-127">Artículo wiki, [SSIS con conectores de Oracle](https://go.microsoft.com/fwlink/?LinkId=220670) en social.technet.Microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="b5af4-127">Wiki article, [SSIS with Oracle Connectors](https://go.microsoft.com/fwlink/?LinkId=220670) on social.technet.microsoft.com.</span></span>  
  
-   <span data-ttu-id="b5af4-128">Artículo técnico, sobre [cadenas de conexión para proveedores OLE DB](https://go.microsoft.com/fwlink/?LinkId=220744), en carlprothman.net.</span><span class="sxs-lookup"><span data-stu-id="b5af4-128">Technical article, [Connection Strings for OLE DB Providers](https://go.microsoft.com/fwlink/?LinkId=220744), on carlprothman.net.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5af4-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b5af4-129">See Also</span></span>  
 <span data-ttu-id="b5af4-130">[Origen de OLE DB](../data-flow/ole-db-source.md) </span><span class="sxs-lookup"><span data-stu-id="b5af4-130">[OLE DB Source](../data-flow/ole-db-source.md) </span></span>  
 <span data-ttu-id="b5af4-131">[Destino de OLE DB](../data-flow/ole-db-destination.md) </span><span class="sxs-lookup"><span data-stu-id="b5af4-131">[OLE DB Destination](../data-flow/ole-db-destination.md) </span></span>  
 <span data-ttu-id="b5af4-132">[Tarea ejecutar SQL](../control-flow/execute-sql-task.md) </span><span class="sxs-lookup"><span data-stu-id="b5af4-132">[Execute SQL Task](../control-flow/execute-sql-task.md) </span></span>  
 [<span data-ttu-id="b5af4-133">Conexiones de Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="b5af4-133">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
