---
title: Instancia del servidor reflejado (Asistente para la configuración de seguridad de la creación de reflejo de bases de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.configdbmsecurwiz.mirrorsrvr.f1
ms.assetid: 53223432-615e-440f-904d-925d33ec2144
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 889e62af592d8d23f2aca0d752f1c7f535df883a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751453"
---
# <a name="mirror-server-instance-configure-database-mirroring-security-wizard"></a><span data-ttu-id="97a48-102">Instancia del servidor reflejado (Asistente para la configuración de seguridad de la creación de reflejo de bases de datos)</span><span class="sxs-lookup"><span data-stu-id="97a48-102">Mirror Server Instance (Configure Database Mirroring Security Wizard)</span></span>
  <span data-ttu-id="97a48-103">Utilice esta página para especificar la información acerca de la instancia de servidor con la base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="97a48-103">Use this page to specify information about the server instance with the mirror database.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="97a48-104">La instancia del servidor reflejado debe ejecutar la misma edición de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], ya sea Standard o Enterprise, que la instancia del servidor principal.</span><span class="sxs-lookup"><span data-stu-id="97a48-104">The mirror server instance must be running the same edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], either Standard or Enterprise, as the principal server instance.</span></span> <span data-ttu-id="97a48-105">Asimismo, se recomienda encarecidamente que se ejecuten en sistemas comparables que puedan administrar cargas de trabajo idénticas.</span><span class="sxs-lookup"><span data-stu-id="97a48-105">Also, we strongly recommend that they run on comparable systems that can handle identical workloads.</span></span>  
  
 <span data-ttu-id="97a48-106">**Para configurar la creación de reflejo de la base de datos mediante SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="97a48-106">**To configure database mirroring by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="97a48-107">Establecer una sesión de creación de reflejo de la base de datos mediante la autenticación de Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="97a48-107">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="97a48-108">Iniciar el Asistente para la configuración de seguridad de la creación de reflejo de la base de datos &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="97a48-108">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
## <a name="options"></a><span data-ttu-id="97a48-109">Opciones</span><span class="sxs-lookup"><span data-stu-id="97a48-109">Options</span></span>  
 <span data-ttu-id="97a48-110">**Instancia del servidor reflejado**</span><span class="sxs-lookup"><span data-stu-id="97a48-110">**Mirror server instance**</span></span>  
 <span data-ttu-id="97a48-111">Si ya se ha especificado una instancia de servidor reflejado (en la página **Creación de reflejo** del cuadro de diálogo **Propiedades de la base de datos** ), se muestra dicha instancia. Para obtener más información, vea [Propiedades de la base de datos &#40;página Creación de reflejo&#41;](../../relational-databases/databases/database-properties-mirroring-page.md).</span><span class="sxs-lookup"><span data-stu-id="97a48-111">If a mirror server instance is already specified (on the **Mirroring** page of the **Database Properties** dialog box), that instance is displayed; for more information, see [Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md).</span></span>  
  
 <span data-ttu-id="97a48-112">De lo contrario, escriba el nombre de la instancia del servidor reflejado.</span><span class="sxs-lookup"><span data-stu-id="97a48-112">Otherwise, enter the name of the mirror server instance.</span></span> <span data-ttu-id="97a48-113">Observe que la instancia del servidor reflejado no puede ser la misma que la instancia del servidor principal.</span><span class="sxs-lookup"><span data-stu-id="97a48-113">Note that the mirror server instance cannot be the same as the principal server instance.</span></span>  
  
 <span data-ttu-id="97a48-114">**Conexión**</span><span class="sxs-lookup"><span data-stu-id="97a48-114">**Connect**</span></span>  
 <span data-ttu-id="97a48-115">Si no se ha especificado una instancia del servidor reflejado, haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="97a48-115">If a mirror server instance has not been specified, click **Connect**.</span></span> <span data-ttu-id="97a48-116">Aparecerá el cuadro de diálogo **Conectar al servidor** , donde puede especificar la instancia de servidor y establecer una conexión.</span><span class="sxs-lookup"><span data-stu-id="97a48-116">This displays the **Connect to Server** dialog box in which you can specify the server instance and establish a connection.</span></span>  
  
 <span data-ttu-id="97a48-117">Si se ha especificado la instancia, pero el asistente no tiene una conexión con los permisos suficientes para comprobar la existencia del extremo, haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="97a48-117">If the instance has been specified, but the wizard lacks a connection with sufficient permission to check for the existence of the endpoint, click **Connect**.</span></span> <span data-ttu-id="97a48-118">Aparecerá el cuadro de diálogo **Conectar al servidor** con la instancia de servidor preseleccionada y sin cambios.</span><span class="sxs-lookup"><span data-stu-id="97a48-118">This displays the **Connect to Server** dialog box with the server instance pre-selected and unchangeable.</span></span> <span data-ttu-id="97a48-119">Especifique una cuenta de dominio con permisos suficientes y conéctese a la instancia de servidor.</span><span class="sxs-lookup"><span data-stu-id="97a48-119">Specify a domain account with sufficient permission, and connect to the server instance.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="97a48-120">Al conectarse a la instancia del servidor, el Asistente para la configuración de seguridad de la creación de reflejo de bases de datos utiliza las credenciales proporcionadas en el cuadro de diálogo **Conectar al servidor** .</span><span class="sxs-lookup"><span data-stu-id="97a48-120">When connecting to the server instance, the Configure Database Mirroring Security Wizard uses the credentials provided in the **Connect to Server** dialog box.</span></span> <span data-ttu-id="97a48-121">Éstas son diferentes de las credenciales de una sesión de creación de reflejo, que utiliza las credenciales de la cuenta de inicio y cuya instancia del servidor se ejecuta como un servicio.</span><span class="sxs-lookup"><span data-stu-id="97a48-121">These are different from the credentials of a mirroring session, which uses the credentials of the startup account where the server instance is running as a service.</span></span>  
  
 <span data-ttu-id="97a48-122">**Listener Port** (Puerto de escucha)</span><span class="sxs-lookup"><span data-stu-id="97a48-122">**Listener Port**</span></span>  
 <span data-ttu-id="97a48-123">El comportamiento de esta opción depende de la existencia del extremo de reflejo para la instancia de servidor, del modo siguiente:</span><span class="sxs-lookup"><span data-stu-id="97a48-123">The behavior of this option depends on whether the mirroring endpoint exists for this server instance, as follows:</span></span>  
  
-   <span data-ttu-id="97a48-124">Si un puerto de escucha no existe para la instancia de servidor, aparecerá el número de puerto 5022 en el cuadro de texto **Puerto** .</span><span class="sxs-lookup"><span data-stu-id="97a48-124">If a listener port does not exist for the server instance, port number 5022 is displayed in the **Port** text box.</span></span> <span data-ttu-id="97a48-125">Puede escribir cualquier número de puerto disponible, como el 7022.</span><span class="sxs-lookup"><span data-stu-id="97a48-125">You can use any available port number, such as 7022.</span></span>  
  
-   <span data-ttu-id="97a48-126">Cuando ya existe el extremo de reflejo, aparecerá el número de puerto de dicho extremo.</span><span class="sxs-lookup"><span data-stu-id="97a48-126">When the mirroring endpoint already exists, the port number from that endpoint is displayed.</span></span> <span data-ttu-id="97a48-127">Si necesita cambiar el puerto, use un comando ALTER ENDPOINT.</span><span class="sxs-lookup"><span data-stu-id="97a48-127">If you need to change the port, use an ALTER ENDPOINT command.</span></span> <span data-ttu-id="97a48-128">Para obtener más información, vea [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="97a48-128">For more information, see [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="97a48-129">Se requiere un número de puerto.</span><span class="sxs-lookup"><span data-stu-id="97a48-129">A port number is required.</span></span>  
  
 <span data-ttu-id="97a48-130">**Nombre del punto de conexión**</span><span class="sxs-lookup"><span data-stu-id="97a48-130">**Endpoint name**</span></span>  
 <span data-ttu-id="97a48-131">Si el extremo de reflejo existe para esta instancia de servidor, el nombre del extremo aparecerá aquí.</span><span class="sxs-lookup"><span data-stu-id="97a48-131">If the mirroring endpoint exists for this server instance, the endpoint name is displayed here.</span></span> <span data-ttu-id="97a48-132">Si el extremo no existe, puede especificar el nombre del extremo.</span><span class="sxs-lookup"><span data-stu-id="97a48-132">If the endpoint does not exist, you can specify the name of the endpoint.</span></span>  
  
 <span data-ttu-id="97a48-133">**Cifrar datos enviados a través de este extremo**</span><span class="sxs-lookup"><span data-stu-id="97a48-133">**Encrypt data sent through this endpoint**</span></span>  
 <span data-ttu-id="97a48-134">El cifrado está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="97a48-134">By default, encryption is enabled.</span></span> <span data-ttu-id="97a48-135">Cuando se habilita, el cifrado no solo se admite, sino que es necesario y utiliza los valores predeterminados para todas las opciones de cifrado.</span><span class="sxs-lookup"><span data-stu-id="97a48-135">When enabled, encryption is required (not merely supported) and uses the default values for all of the encryption options.</span></span> <span data-ttu-id="97a48-136">Para obtener más información, vea [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="97a48-136">For more information, see [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span></span>  
  
 <span data-ttu-id="97a48-137">Para deshabilitar el cifrado, quite la marca de la casilla.</span><span class="sxs-lookup"><span data-stu-id="97a48-137">To disable encryption, clear the check box.</span></span> <span data-ttu-id="97a48-138">Para volver a habilitar el cifrado, active la casilla.</span><span class="sxs-lookup"><span data-stu-id="97a48-138">To re-enable encryption, select the check box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97a48-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="97a48-139">See Also</span></span>  
 <span data-ttu-id="97a48-140">[El punto de conexión de creación de reflejo de la base de datos &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="97a48-140">[The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="97a48-141">[Propiedades de la base de datos &#40;página Creación de reflejo&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="97a48-141">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 <span data-ttu-id="97a48-142">[Crear un punto de conexión de creación de reflejo de la base de datos para la autenticación de Windows &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="97a48-142">[Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span></span>  
 <span data-ttu-id="97a48-143">[Iniciar el Monitor de creación de reflejo de la base de datos &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="97a48-143">[Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="97a48-144">Creación de reflejo de la base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="97a48-144">Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)  
  
  
