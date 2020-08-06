---
title: Conexión de SQL Server para la creación de instancias | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 81d0e7e2-d8f0-4bd9-9565-218ce996f28e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cdff17b763257c2a3280981c1f5c16040cc61413
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669807"
---
# <a name="sql-server-connection-for-instance-creation"></a><span data-ttu-id="2da33-102">Conexión de SQL Server para la creación de instancias</span><span class="sxs-lookup"><span data-stu-id="2da33-102">SQL Server Connection for Instance Creation</span></span>
  <span data-ttu-id="2da33-103">Uno de los primeros pasos para crear una instancia CDC de Oracle es la creación de una base de datos CDC en la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino.</span><span class="sxs-lookup"><span data-stu-id="2da33-103">One of the first steps when creating an Oracle CDC Instance is the creation of a CDC database on the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="2da33-104">Esta base de datos CDC está habilitada para CDC de SQL Server y esta habilitación necesita un inicio de sesión que sea miembro del rol fijo de servidor `sysadmin` .</span><span class="sxs-lookup"><span data-stu-id="2da33-104">This CDC database is enabled for SQL Server CDC and this enablement requires a login that is a member of the `sysadmin` fixed-server role.</span></span>  
  
 <span data-ttu-id="2da33-105">Cuando un usuario que inicia el asistente **Crear una instancia CDC de Oracle** no es miembro del rol fijo de servidor `sysadmin` , se abre el cuadro de diálogo **Conectar con SQL Server** , que pide las credenciales para un miembro del rol `sysadmin` para realizar la tarea Habilitar la base de datos para CDC de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2da33-105">When a user that starts the **Create an Oracle CDC Instance** wizard is not a member of the `sysadmin` fixed-server role, the **Connect to SQL Server** dialog box opens and requests the credentials for a member of the `sysadmin` role to carry out the Enable the database for SQL Server CDC task.</span></span> <span data-ttu-id="2da33-106">Cuando se crea la base de datos CDC, el inicio de sesión `sysadmin` se descarta y se reanuda el trabajo con el inicio de sesión original de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usado cuando se entró en la Consola del diseñador de Oracle.</span><span class="sxs-lookup"><span data-stu-id="2da33-106">When the CDC database is created, the `sysadmin` login is discarded and work resumes with the original [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login used when the Oracle Designer Console was entered.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="2da33-107">Lista de tareas</span><span class="sxs-lookup"><span data-stu-id="2da33-107">Task List</span></span>  
 <span data-ttu-id="2da33-108">Escriba la información siguiente en el cuadro de diálogo **Conectar con SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="2da33-108">Enter the following information in the **Connect to SQL Server** dialog box.</span></span>  
  
 <span data-ttu-id="2da33-109">**Nombre de servidor**</span><span class="sxs-lookup"><span data-stu-id="2da33-109">**Server Name**</span></span>  
 <span data-ttu-id="2da33-110">Escriba el nombre del servidor donde se encuentra [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2da33-110">Type the name of the server where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is located.</span></span>  
  
 <span data-ttu-id="2da33-111">**Autenticación**</span><span class="sxs-lookup"><span data-stu-id="2da33-111">**Authentication**</span></span>  
 <span data-ttu-id="2da33-112">Seleccione uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="2da33-112">Select one of the following:</span></span>  
  
-   <span data-ttu-id="2da33-113">**Autenticación de Windows**</span><span class="sxs-lookup"><span data-stu-id="2da33-113">**Windows Authentication**</span></span>  
  
-   <span data-ttu-id="2da33-114">**Autenticación de SQL Server**: si selecciona esta opción, es necesario que escriba el **inicio de sesión** y la **contraseña** del usuario de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] al que se va a conectar.</span><span class="sxs-lookup"><span data-stu-id="2da33-114">**SQL Server Authentication**: If you select this option, you must type the **Login** and **Password** for the user in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you are connecting to.</span></span>  
  
 <span data-ttu-id="2da33-115">El inicio de sesión debe tener un rol de base de datos que permita el acceso a la base de datos MSXCDCDB.</span><span class="sxs-lookup"><span data-stu-id="2da33-115">The login must have a database role that allows access to the MSXCDCDB database.</span></span> <span data-ttu-id="2da33-116">Se recomienda que el inicio de sesión tenga acceso también a cualquier base de datos adicional que se esté usando; de lo contrario, el usuario no podrá ver los datos de esas bases de datos.</span><span class="sxs-lookup"><span data-stu-id="2da33-116">It is recommended that the login also have access to any additional databases being used or the user will not be able to view the data in those databases.</span></span>  
  
 <span data-ttu-id="2da33-117">**Opciones**</span><span class="sxs-lookup"><span data-stu-id="2da33-117">**Options**</span></span>  
 <span data-ttu-id="2da33-118">Haga clic en la flecha para ver las opciones disponibles que se pueden configurar.</span><span class="sxs-lookup"><span data-stu-id="2da33-118">Click the arrow to view available options to be configured.</span></span> <span data-ttu-id="2da33-119">Puede elegir dejar estas opciones con el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="2da33-119">You can choose to leave these options with their default value.</span></span> <span data-ttu-id="2da33-120">Las opciones disponibles son:</span><span class="sxs-lookup"><span data-stu-id="2da33-120">The available options are:</span></span>  
  
-   <span data-ttu-id="2da33-121">**Tiempo de espera de la conexión**: Escriba el tiempo (en segundos) que el servicio CDC para Oracle espera una conexión con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] antes de agotarse el tiempo de espera. El valor predeterminado es **15**.</span><span class="sxs-lookup"><span data-stu-id="2da33-121">**Connection Timeout**: Type the time (in seconds) that the CDC Service for Oracle waits for a connection to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before timing out. The default value is **15**.</span></span>  
  
-   <span data-ttu-id="2da33-122">**Tiempo de espera de ejecución**: Escriba el tiempo (en segundos) que el servicio de Windows CDC de Oracle espera que se ejecute un comando antes de agotarse el tiempo de espera. El valor predeterminado es **30**.</span><span class="sxs-lookup"><span data-stu-id="2da33-122">**Execution Timeout**: Type the time (in seconds) that the Oracle CDC Windows Service waits for a command to execute before timing out. The default value is **30**.</span></span>  
  
-   <span data-ttu-id="2da33-123">**Cifrar conexión**: seleccione **Cifrar conexión** para que la comunicación entre el servicio CDC de Oracle y la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino se realice mediante una conexión cifrada.</span><span class="sxs-lookup"><span data-stu-id="2da33-123">**Encrypt Connection**: Select **Encrypt Connection** for communication between the Oracle CDC Service and the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance using an encrypted connection.</span></span>  
  
-   <span data-ttu-id="2da33-124">**Avanzadas**: Haga clic en **Avanzadas** y escriba cualquier propiedad de conexión adicional en el cuadro de diálogo Propiedades avanzadas de conexión, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="2da33-124">**Advanced**: Click **Advanced** and type any additional connection properties into the Advanced Connection Properties dialog box, if necessary.</span></span>  
  
     <span data-ttu-id="2da33-125">Para obtener información sobre el cuadro de diálogo Propiedades avanzadas de conexión, vea [Propiedades avanzadas de conexión](advanced-connection-properties.md).</span><span class="sxs-lookup"><span data-stu-id="2da33-125">For information about the Advanced Connection Properties dialog box, see [Advanced Connection Properties](advanced-connection-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2da33-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2da33-126">See Also</span></span>  
 <span data-ttu-id="2da33-127">[Crear la base de datos de cambios de SQL Server](create-the-sql-server-change-database.md) </span><span class="sxs-lookup"><span data-stu-id="2da33-127">[Create the SQL Server Change Database](create-the-sql-server-change-database.md) </span></span>  
 [<span data-ttu-id="2da33-128">Permisos necesarios de conexión con SQL Server para el Diseñador CDC</span><span class="sxs-lookup"><span data-stu-id="2da33-128">SQL Server Connection Required Permissions for the CDC Designer</span></span>](sql-server-connection-required-permissions-for-the-cdc-designer.md)  
  
  
