---
title: Obtener acceso a la Consola del diseñador CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- accMsDes
ms.assetid: b168c64e-c1b5-42d4-a92a-84de1dd0324e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7f4f6e4df0a514cb29e36bcd1270b2537dc3ba68
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750098"
---
# <a name="access-the-cdc-designer-console"></a><span data-ttu-id="796d2-102">Obtener acceso a la Consola del diseñador CDC</span><span class="sxs-lookup"><span data-stu-id="796d2-102">Access the CDC Designer Console</span></span>
  <span data-ttu-id="796d2-103">Puede obtener acceso a la Consola del diseñador CDC desde el equipo en el que instaló la consola.</span><span class="sxs-lookup"><span data-stu-id="796d2-103">You can access the CDC Designer Console from the computer where you installed the console.</span></span> <span data-ttu-id="796d2-104">Para obtener más información acerca de la instalación, vea Instalación.</span><span class="sxs-lookup"><span data-stu-id="796d2-104">For more information about installation, see Installation.</span></span>  
  
 <span data-ttu-id="796d2-105">Cuando abra la Consola del diseñador CDC, se abrirá el cuadro de diálogo Conectar con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="796d2-105">When you open the CDC Designer Console, the Connect to SQL Server dialog box opens.</span></span>  
  
 <span data-ttu-id="796d2-106">El inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que tiene acceso al Diseñador CDC necesita tener permisos UPDATE en la base de datos MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="796d2-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login that accesses the CDC Designer must have UPDATE permissions on the MSXDBCDC database.</span></span> <span data-ttu-id="796d2-107">Además, el inicio de sesión debe tener también el rol fijo de servidor `dbcreator` para crear nuevas instancias CDC de Oracle.</span><span class="sxs-lookup"><span data-stu-id="796d2-107">In addition, the login must also have the `dbcreator` fixed-server role to create new Oracle CDC Instances.</span></span> <span data-ttu-id="796d2-108">Se recomienda que el inicio de sesión tenga también acceso SELECT a las bases de datos CDC que se están usando; de lo contrario, el usuario no podrá ver el estado de esas bases de datos.</span><span class="sxs-lookup"><span data-stu-id="796d2-108">It is recommended that the login also have SELECT access to the CDC databases being used or the user will not be able to view the state of those databases.</span></span>  
  
 <span data-ttu-id="796d2-109">Escriba la información siguiente en el cuadro de diálogo Conectar con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="796d2-109">Enter the following information in the Connect to SQL Server dialog box.</span></span>  
  
### <a name="server-name"></a><span data-ttu-id="796d2-110">Nombre del servidor</span><span class="sxs-lookup"><span data-stu-id="796d2-110">Server Name</span></span>  
 <span data-ttu-id="796d2-111">Escriba el nombre del servidor donde se encuentra [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="796d2-111">Type the name of the server where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is located.</span></span>  
  
### <a name="authentication"></a><span data-ttu-id="796d2-112">Authentication</span><span class="sxs-lookup"><span data-stu-id="796d2-112">Authentication</span></span>  
 <span data-ttu-id="796d2-113">Seleccione uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="796d2-113">Select one of the following:</span></span>  
  
-   <span data-ttu-id="796d2-114">**Autenticación de Windows**</span><span class="sxs-lookup"><span data-stu-id="796d2-114">**Windows Authentication**</span></span>  
  
-   <span data-ttu-id="796d2-115">**Autenticación de SQL Server**: si selecciona esta opción, es necesario que escriba el **inicio de sesión** y la **contraseña** del usuario de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] al que se va a conectar.</span><span class="sxs-lookup"><span data-stu-id="796d2-115">**SQL Server Authentication**: If you select this option, you must type the **Login** and **Password** for the user in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you are connecting to.</span></span>  
  
 <span data-ttu-id="796d2-116">El inicio de sesión debe tener un rol de base de datos que permita el acceso a la base de datos MSXCDCDB.</span><span class="sxs-lookup"><span data-stu-id="796d2-116">The login must have a database role that allows access to the MSXCDCDB database.</span></span> <span data-ttu-id="796d2-117">Se recomienda que el inicio de sesión tenga acceso también a cualquier base de datos adicional que se esté usando; de lo contrario, el usuario no podrá ver los datos de esas bases de datos.</span><span class="sxs-lookup"><span data-stu-id="796d2-117">It is recommended that the login also have access to any additional databases being used or the user will not be able to view the data in those databases.</span></span>  
  
### <a name="options"></a><span data-ttu-id="796d2-118">Opciones</span><span class="sxs-lookup"><span data-stu-id="796d2-118">Options</span></span>  
 <span data-ttu-id="796d2-119">Haga clic en la flecha para ver las opciones disponibles que se pueden configurar.</span><span class="sxs-lookup"><span data-stu-id="796d2-119">Click the arrow to view available options to be configured.</span></span> <span data-ttu-id="796d2-120">Puede elegir dejar estas opciones con el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="796d2-120">You can choose to leave these options with their default value.</span></span> <span data-ttu-id="796d2-121">Las opciones disponibles son:</span><span class="sxs-lookup"><span data-stu-id="796d2-121">The available options are:</span></span>  
  
 <span data-ttu-id="796d2-122">**Tiempo de espera de la conexión**</span><span class="sxs-lookup"><span data-stu-id="796d2-122">**Connection Timeout**</span></span>  
 <span data-ttu-id="796d2-123">Escriba el tiempo (en segundos) que el servicio CDC para Oracle espera una conexión con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] antes de agotarse el tiempo de espera. El valor predeterminado es **15**.</span><span class="sxs-lookup"><span data-stu-id="796d2-123">Type the time (in seconds) that the CDC Service for Oracle waits for a connection to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before timing out. The default value is **15**.</span></span>  
  
 <span data-ttu-id="796d2-124">**Tiempo de espera de ejecución**</span><span class="sxs-lookup"><span data-stu-id="796d2-124">**Execution Timeout**</span></span>  
 <span data-ttu-id="796d2-125">Escriba el tiempo (en segundos) que el servicio de Windows CDC de Oracle espera que se ejecute un comando antes de agotarse el tiempo de espera. El valor predeterminado es **30**.</span><span class="sxs-lookup"><span data-stu-id="796d2-125">Type the time (in seconds) that the Oracle CDC Windows Service waits for a command to execute before timing out. The default value is **30**.</span></span>  
  
 <span data-ttu-id="796d2-126">**Cifrar conexión**</span><span class="sxs-lookup"><span data-stu-id="796d2-126">**Encrypt Connection**</span></span>  
 <span data-ttu-id="796d2-127">Seleccione **Cifrar conexión** para que la comunicación entre el servicio CDC de Oracle y la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino se realice mediante una conexión cifrada.**Avanzadas**: Haga clic en **Avanzadas** y escriba cualquier propiedad de conexión adicional en el cuadro de diálogo Propiedades avanzadas de conexión, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="796d2-127">Select **Encrypt Connection** for communication between the Oracle CDC Service and the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance using an encrypted connection.**Advanced**: Click **Advanced** and type any additional connection properties into the Advanced Connection Properties dialog box, if necessary.</span></span>  
  
 <span data-ttu-id="796d2-128">**Avanzadas**</span><span class="sxs-lookup"><span data-stu-id="796d2-128">**Advanced**</span></span>  
 <span data-ttu-id="796d2-129">Haga clic en **Avanzadas** y escriba cualquier propiedad de conexión adicional en el cuadro de diálogo Propiedades avanzadas de conexión, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="796d2-129">Click **Advanced** and type any additional connection properties into the Advanced Connection Properties dialog box, if necessary.</span></span>  
  
 <span data-ttu-id="796d2-130">Para obtener información sobre el cuadro de diálogo Propiedades avanzadas de conexión, vea [Propiedades avanzadas de conexión](advanced-connection-properties.md).</span><span class="sxs-lookup"><span data-stu-id="796d2-130">For information about the Advanced Connection Properties dialog box, see [Advanced Connection Properties](advanced-connection-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="796d2-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="796d2-131">See Also</span></span>  
 [<span data-ttu-id="796d2-132">Permisos necesarios de conexión con SQL Server para el Diseñador CDC</span><span class="sxs-lookup"><span data-stu-id="796d2-132">SQL Server Connection Required Permissions for the CDC Designer</span></span>](sql-server-connection-required-permissions-for-the-cdc-designer.md)  
  
  
