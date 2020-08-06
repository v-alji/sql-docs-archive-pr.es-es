---
title: Preparar SQL Server para CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- prepSqlSrv
ms.assetid: 20b51dbf-a545-4234-87ae-4228268a0fb2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dafa29d9bdb0c27decb605398a6d1cfe383427e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669809"
---
# <a name="prepare-sql-server-for-cdc"></a><span data-ttu-id="0de59-102">Preparar SQL Server para CDC</span><span class="sxs-lookup"><span data-stu-id="0de59-102">Prepare SQL Server for CDC</span></span>
  <span data-ttu-id="0de59-103">El servicio CDC de Oracle necesita que todas las instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino contengan la base de datos MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="0de59-103">The Oracle CDC service requires all target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances to contain the MSXDBCDC database.</span></span> <span data-ttu-id="0de59-104">Esta base de datos se crea mediante la acción Preparar SQL Server de la Consola de configuración del servicio CDC.</span><span class="sxs-lookup"><span data-stu-id="0de59-104">You create this database using the Prepare SQL Server action in the CDC Service Configuration Console.</span></span> <span data-ttu-id="0de59-105">Esto crea un script especial que se ejecuta para crear las tablas, los procedimientos almacenados y otros artefactos necesarios para esta base de datos.</span><span class="sxs-lookup"><span data-stu-id="0de59-105">This creates a special script that is run to create the required tables, stored procedures, and other required artifacts for this database.</span></span> <span data-ttu-id="0de59-106">Esta tarea solo se realiza una vez para cada instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino.</span><span class="sxs-lookup"><span data-stu-id="0de59-106">This task is done one time only for each target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
 <span data-ttu-id="0de59-107">Para obtener más información acerca de la base de datos MSXDBCDC, vea La base de datos MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="0de59-107">For more information about the MSXDBCDC database, see The MSXDBCDC Database.</span></span>  
  
 <span data-ttu-id="0de59-108">En la Consola de configuración del servicio CDC, haga clic en **Preparar SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="0de59-108">In the CDC Service Configuration Console, click **Prepare SQL Server**.</span></span> <span data-ttu-id="0de59-109">Si esta opción no está disponible, asegúrese de que esté seleccionado **Servicios CDC locales** en el panel izquierdo de la consola.</span><span class="sxs-lookup"><span data-stu-id="0de59-109">If this option is not available, make sure that **Local CDC Services** is selected in the left pane of the console.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0de59-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="0de59-110">Options</span></span>  
  
### <a name="server-name"></a><span data-ttu-id="0de59-111">Nombre del servidor</span><span class="sxs-lookup"><span data-stu-id="0de59-111">Server Name</span></span>  
 <span data-ttu-id="0de59-112">Escriba el nombre del servidor donde se encuentra [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0de59-112">Type the name of the server where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is located.</span></span>  
  
### <a name="authentication"></a><span data-ttu-id="0de59-113">Authentication</span><span class="sxs-lookup"><span data-stu-id="0de59-113">Authentication</span></span>  
 <span data-ttu-id="0de59-114">Seleccione uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="0de59-114">Select one of the following:</span></span>  
  
-   <span data-ttu-id="0de59-115">**Autenticación de Windows**</span><span class="sxs-lookup"><span data-stu-id="0de59-115">**Windows Authentication**</span></span>  
  
-   <span data-ttu-id="0de59-116">**Autenticación de SQL Server**: si selecciona esta opción, debe escribir los valores de **Nombre de usuario** y **Contraseña** del usuario de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a la que se va a conectar.</span><span class="sxs-lookup"><span data-stu-id="0de59-116">**SQL Server Authentication**: If you select this option, you must type the **User Name** and **Password** for the user in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you are connecting to.</span></span>  
  
 <span data-ttu-id="0de59-117">Para preparar la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para CDC de Oracle, el inicio de sesión debe tener permiso de escritura para la base de datos MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="0de59-117">To prepare the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance for Oracle CDC, the login must have write permission to the MSXDBCDC database.</span></span> <span data-ttu-id="0de59-118">Escriba las credenciales para un inicio de sesión que tenga permiso de escritura para la base de datos MSXDBCDC, como un miembro del rol `sysasmin` .</span><span class="sxs-lookup"><span data-stu-id="0de59-118">Enter the credentials for a login that has write permission to the MSXDBCDC database, such as a member of the `sysasmin` role.</span></span>  
  
### <a name="options"></a><span data-ttu-id="0de59-119">Opciones</span><span class="sxs-lookup"><span data-stu-id="0de59-119">Options</span></span>  
 <span data-ttu-id="0de59-120">Haga clic en la flecha para ver las opciones disponibles que se pueden configurar.</span><span class="sxs-lookup"><span data-stu-id="0de59-120">Click the arrow to view available options to be configured.</span></span> <span data-ttu-id="0de59-121">Puede elegir dejar estas opciones con el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0de59-121">You can choose to leave these options with their default value.</span></span> <span data-ttu-id="0de59-122">Las opciones disponibles son:</span><span class="sxs-lookup"><span data-stu-id="0de59-122">The available options are:</span></span>  
  
-   <span data-ttu-id="0de59-123">**Tiempo de espera de la conexión**: Escriba el tiempo (en segundos) que el servicio CDC para Oracle espera una conexión con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] antes de agotarse el tiempo de espera. El valor predeterminado es **15**.</span><span class="sxs-lookup"><span data-stu-id="0de59-123">**Connection Timeout**: Type the time (in seconds) that the CDC Service for Oracle waits for a connection to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before timing out. The default value is **15**.</span></span>  
  
-   <span data-ttu-id="0de59-124">**Tiempo de espera de ejecución**: Escriba el tiempo (en segundos) que el servicio de Windows CDC de Oracle espera que se ejecute un comando antes de agotarse el tiempo de espera. El valor predeterminado es **30**.</span><span class="sxs-lookup"><span data-stu-id="0de59-124">**Execution Timeout**: Type the time (in seconds) that the Oracle CDC Windows Service waits for a command to execute before timing out. The default value is **30**.</span></span>  
  
-   <span data-ttu-id="0de59-125">**Cifrar conexión**: seleccione **Cifrar conexión** para que la comunicación entre el servicio CDC de Oracle y la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino se realice mediante una conexión cifrada.</span><span class="sxs-lookup"><span data-stu-id="0de59-125">**Encrypt Connection**: Select **Encrypt Connection** for communication between the Oracle CDC Service and the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance using an encrypted connection.</span></span>  
  
-   <span data-ttu-id="0de59-126">**Avanzadas**: escriba cualquier propiedad de conexión adicional, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="0de59-126">**Advanced**: Type any additional connection properties, if necessary.</span></span>  
  
### <a name="view-script"></a><span data-ttu-id="0de59-127">Ver script</span><span class="sxs-lookup"><span data-stu-id="0de59-127">View Script</span></span>  
 <span data-ttu-id="0de59-128">Haga clic en **Ver script** para ver una versión de solo lectura del script de configuración.</span><span class="sxs-lookup"><span data-stu-id="0de59-128">Click **View Script** to view a read-only version of the setup script.</span></span> <span data-ttu-id="0de59-129">Un administrador del sistema de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] puede copiar este script en la consola de administración de SQL Server para editarlo, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="0de59-129">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator can copy this script into the SQL Server Management Console to edit it, if necessary.</span></span> <span data-ttu-id="0de59-130">Para obtener más información sobre el script para preparar SQL Server, vea [Preparar SQL Server para CDC de Oracle (Ver script)](prepare-sql-server-for-oracle-cdc-view-script.md).</span><span class="sxs-lookup"><span data-stu-id="0de59-130">For more information about the Prepare SQL Server Script, see [Prepare SQL Server for Oracle CDC-View Script](prepare-sql-server-for-oracle-cdc-view-script.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0de59-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0de59-131">See Also</span></span>  
 <span data-ttu-id="0de59-132">[Cómo trabajar con servicios CDC](work-with-cdc-services.md) </span><span class="sxs-lookup"><span data-stu-id="0de59-132">[How to Work with CDC Services](work-with-cdc-services.md) </span></span>  
 [<span data-ttu-id="0de59-133">Cómo preparar SQL Server para CDC</span><span class="sxs-lookup"><span data-stu-id="0de59-133">How to Prepare SQL Server for CDC</span></span>](prepare-sql-server-for-cdc.md)  
  
  
