---
title: Conexión con SQL Server para eliminación | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 030b10c2-6b88-4c2c-bf67-22994be25a60
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f5f069f7686e8b6fa9176f92c9e2f47be5f2c71a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669811"
---
# <a name="connection-to-sql-server-for-delete"></a><span data-ttu-id="93207-102">Conexión con SQL Server para eliminación</span><span class="sxs-lookup"><span data-stu-id="93207-102">Connection to SQL Server for Delete</span></span>
  <span data-ttu-id="93207-103">Cuando un inicio de sesión sin un rol de base de datos que incluye el permiso de escritura (por ejemplo, el rol **db_owner** ) para la base de datos MSXDBCDC intenta eliminar una instancia CDC de Oracle, se muestra el cuadro de diálogo Conectar con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="93207-103">When a login without a database role that includes write permission (for example the **db_owner** role) to the MSXDBCDC database attempts to delete an Oracle CDC instance, the Connect to SQL Server dialog box is displayed.</span></span>  
  
 <span data-ttu-id="93207-104">En este cuadro de diálogo debe especificar las credenciales para un inicio de sesión que tenga permiso de escritura para la base de datos MSXDBCDC, como el rol de base de datos **db_owner** para eliminar la instancia CDC de Oracle.</span><span class="sxs-lookup"><span data-stu-id="93207-104">In this dialog box you must enter the credentials for a login that has write permission to the MSXDBCDC database, such the **db_owner** database role to delete the Oracle CDC instance.</span></span>  
  
 <span data-ttu-id="93207-105">Escriba la información siguiente en el cuadro de diálogo Conectar con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="93207-105">Enter the following information in the Connect to SQL Server dialog box.</span></span>  
  
 <span data-ttu-id="93207-106">**Nombre de servidor**</span><span class="sxs-lookup"><span data-stu-id="93207-106">**Server Name**</span></span>  
 <span data-ttu-id="93207-107">Escriba el nombre del servidor donde se encuentra [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="93207-107">Type the name of the server where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is located.</span></span>  
  
 <span data-ttu-id="93207-108">**Autenticación**</span><span class="sxs-lookup"><span data-stu-id="93207-108">**Authentication**</span></span>  
 <span data-ttu-id="93207-109">Seleccione uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="93207-109">Select one of the following:</span></span>  
  
-   <span data-ttu-id="93207-110">**Autenticación de Windows**</span><span class="sxs-lookup"><span data-stu-id="93207-110">**Windows Authentication**</span></span>  
  
-   <span data-ttu-id="93207-111">**Autenticación de SQL Server**: si selecciona esta opción, es necesario que escriba el **Inicio de sesión** y la **Contraseña** del usuario de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] al que se conecta.</span><span class="sxs-lookup"><span data-stu-id="93207-111">**SQL Server Authentication**: If you select this option, you must type the **Login** and **Password** for the user in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you are connecting to.</span></span>  
  
 <span data-ttu-id="93207-112">**Opciones**</span><span class="sxs-lookup"><span data-stu-id="93207-112">**Options**</span></span>  
 <span data-ttu-id="93207-113">Haga clic en la flecha para ver las opciones disponibles que se pueden configurar.</span><span class="sxs-lookup"><span data-stu-id="93207-113">Click the arrow to view available options to be configured.</span></span> <span data-ttu-id="93207-114">Puede elegir dejar estas opciones con el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="93207-114">You can choose to leave these options with their default value.</span></span> <span data-ttu-id="93207-115">Las opciones disponibles son:</span><span class="sxs-lookup"><span data-stu-id="93207-115">The available options are:</span></span>  
  
-   <span data-ttu-id="93207-116">**Tiempo de espera de la conexión**: escriba el tiempo (en segundos) que el programa espera hasta que se establezca una conexión con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] antes de producir un error de tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="93207-116">**Connection Timeout**: Type the time (in seconds) the program waits for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection to be established before producing a timeout error.</span></span> <span data-ttu-id="93207-117">El valor predeterminado es **15**.</span><span class="sxs-lookup"><span data-stu-id="93207-117">The default value is **15**.</span></span>  
  
-   <span data-ttu-id="93207-118">**Tiempo de espera de ejecución**: escriba el tiempo (en segundos) que el programa espera hasta que finalice la ejecución de un comando SQL antes de producir un error de tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="93207-118">**Execution Timeout**: Type the time (in seconds) that the program waits for SQL command execution to finish before producing a timeout error.</span></span> <span data-ttu-id="93207-119">El valor predeterminado es **30**.</span><span class="sxs-lookup"><span data-stu-id="93207-119">The default value is **30**.</span></span>  
  
-   <span data-ttu-id="93207-120">**Cifrar conexión**: seleccione **Cifrar conexión** para asegurarse de que la conexión con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que se establece está cifrada para garantizar la privacidad.</span><span class="sxs-lookup"><span data-stu-id="93207-120">**Encrypt Connection**: Select **Encrypt Connection** to ensure that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection that being established is encrypted to guarantee privacy.</span></span>  
  
-   <span data-ttu-id="93207-121">**Avanzadas**: haga clic en **Avanzadas** y escriba cualquier propiedad de conexión adicional en el cuadro de diálogo Propiedades avanzadas de conexión, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="93207-121">**Advanced**: Click **Advanced** and type any additional connection properties into the Advanced Connection Properties dialog box, if necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93207-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="93207-122">See Also</span></span>  
 [<span data-ttu-id="93207-123">Permisos de conexión con SQL Server necesarios para el servicio CDC</span><span class="sxs-lookup"><span data-stu-id="93207-123">SQL Server Connection Required Permissions for the CDC Service</span></span>](sql-server-connection-required-permissions-for-the-cdc-service.md)  
  
  
