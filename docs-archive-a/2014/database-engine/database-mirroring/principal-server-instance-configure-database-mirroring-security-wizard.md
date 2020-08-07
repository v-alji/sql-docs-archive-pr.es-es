---
title: Instancia de servidor principal (Asistente para la configuración de seguridad de la creación de reflejo de bases de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.configdbmsecurwiz.principalsrvr.f1
ms.assetid: 58af27d7-c5dd-4669-be6b-b472bc2c8ef4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2632b5ffd5355065b4b5c1f905b3b6e5c5b6204d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746508"
---
# <a name="principal-server-instance-configure-database-mirroring-security-wizard"></a><span data-ttu-id="42833-102">Instancia de servidor principal (Asistente para la configuración de seguridad de la creación de reflejo de bases de datos)</span><span class="sxs-lookup"><span data-stu-id="42833-102">Principal Server Instance (Configure Database Mirroring Security Wizard)</span></span>
  <span data-ttu-id="42833-103">Utilice esta página para especificar la información acerca de la instancia de servidor de la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="42833-103">Use this page to specify information about the server instance of the principal database.</span></span> <span data-ttu-id="42833-104">La base de datos principal es la copia de la base de datos que empieza en la sesión de creación de reflejo.</span><span class="sxs-lookup"><span data-stu-id="42833-104">The principal database is the copy of the database that begins the mirroring session.</span></span> <span data-ttu-id="42833-105">Una vez que la sesión ha empezado, la base de datos principal es la copia de la base de datos que acepta los cambios del usuario.</span><span class="sxs-lookup"><span data-stu-id="42833-105">After the session has begun, the principal database is the copy of the database that accepts user changes.</span></span> <span data-ttu-id="42833-106">Cuando se produce una conmutación por error, los roles principales y de creación de reflejo se intercambian, de modo que es posible que la base de datos principal inicial no sea permanente.</span><span class="sxs-lookup"><span data-stu-id="42833-106">(When a failover occurs, the principal and mirroring roles are swapped; therefore, the initial principal database might not remain the principal database.)</span></span>  
  
 <span data-ttu-id="42833-107">**Para configurar la creación de reflejo de la base de datos mediante SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="42833-107">**To configure database mirroring by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="42833-108">Establecer una sesión de creación de reflejo de la base de datos mediante la autenticación de Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="42833-108">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="42833-109">Iniciar el Asistente para la configuración de seguridad de la creación de reflejo de la base de datos &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="42833-109">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
## <a name="options"></a><span data-ttu-id="42833-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="42833-110">Options</span></span>  
 <span data-ttu-id="42833-111">**Instancia de servidor principal**</span><span class="sxs-lookup"><span data-stu-id="42833-111">**Principal server instance**</span></span>  
 <span data-ttu-id="42833-112">Dado que la creación de reflejo de la base de datos en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] siempre se configura desde el servidor principal, la instancia de servidor actual siempre es la instancia de servidor principal.</span><span class="sxs-lookup"><span data-stu-id="42833-112">Because database mirroring in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] is always configured from the principal server, the current server instance is always the principal server instance.</span></span>  
  
 <span data-ttu-id="42833-113">**Listener Port** (Puerto de escucha)</span><span class="sxs-lookup"><span data-stu-id="42833-113">**Listener Port**</span></span>  
 <span data-ttu-id="42833-114">El comportamiento de esta opción depende de la existencia del extremo de reflejo para la instancia de servidor, del modo siguiente:</span><span class="sxs-lookup"><span data-stu-id="42833-114">The behavior of this option depends on whether the mirroring endpoint exists for this server instance, as follows:</span></span>  
  
-   <span data-ttu-id="42833-115">Si el puerto de escucha no existe para esta instancia de servidor, aparecerá el número de puerto 5022 en el cuadro de texto **Puerto** .</span><span class="sxs-lookup"><span data-stu-id="42833-115">If the listener port does not exist for this server instance, port number 5022 is displayed in the **Port** text box.</span></span> <span data-ttu-id="42833-116">Puede escribir cualquier número de puerto disponible, como el 7022.</span><span class="sxs-lookup"><span data-stu-id="42833-116">You can use any available port number, such as, 7022.</span></span>  
  
-   <span data-ttu-id="42833-117">Cuando ya existe el extremo de reflejo, aparecerá el número de puerto del extremo.</span><span class="sxs-lookup"><span data-stu-id="42833-117">When the mirroring endpoint already exists, the port number from the endpoint is displayed.</span></span> <span data-ttu-id="42833-118">Si necesita cambiar el puerto, use un comando ALTER ENDPOINT.</span><span class="sxs-lookup"><span data-stu-id="42833-118">If you need to change the port, use an ALTER ENDPOINT command.</span></span> <span data-ttu-id="42833-119">Para obtener más información, vea [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="42833-119">For more information, see [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="42833-120">Se requiere un número de puerto.</span><span class="sxs-lookup"><span data-stu-id="42833-120">A port number is required.</span></span>  
  
 <span data-ttu-id="42833-121">**Nombre del punto de conexión**</span><span class="sxs-lookup"><span data-stu-id="42833-121">**Endpoint name**</span></span>  
 <span data-ttu-id="42833-122">Si el extremo de reflejo existe para esta instancia de servidor, el nombre del extremo aparecerá aquí.</span><span class="sxs-lookup"><span data-stu-id="42833-122">If the mirroring endpoint exists for this server instance, the endpoint name is displayed here.</span></span> <span data-ttu-id="42833-123">Si el extremo no existe, puede especificar el nombre del extremo.</span><span class="sxs-lookup"><span data-stu-id="42833-123">If the endpoint does not exist, you can specify the name of the endpoint.</span></span>  
  
 <span data-ttu-id="42833-124">**Cifrar datos enviados a través de este extremo**</span><span class="sxs-lookup"><span data-stu-id="42833-124">**Encrypt data sent through this endpoint**</span></span>  
 <span data-ttu-id="42833-125">El cifrado está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="42833-125">By default, encryption is enabled.</span></span> <span data-ttu-id="42833-126">Cuando se habilita, el cifrado no solo se admite, sino que es necesario y utiliza los valores predeterminados para todas las opciones de cifrado.</span><span class="sxs-lookup"><span data-stu-id="42833-126">When enabled, encryption is required (not merely supported) and uses the default values for all of the encryption options.</span></span> <span data-ttu-id="42833-127">Para obtener más información, vea [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="42833-127">For more information, see [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span></span>  
  
 <span data-ttu-id="42833-128">Para deshabilitar el cifrado, quite la marca de la casilla.</span><span class="sxs-lookup"><span data-stu-id="42833-128">To disable encryption, clear the check box.</span></span> <span data-ttu-id="42833-129">Para volver a habilitar el cifrado, active la casilla.</span><span class="sxs-lookup"><span data-stu-id="42833-129">To re-enable encryption, select the check box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42833-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="42833-130">See Also</span></span>  
 <span data-ttu-id="42833-131">[El punto de conexión de creación de reflejo de la base de datos &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="42833-131">[The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="42833-132">[Propiedades de la base de datos &#40;página Creación de reflejo&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="42833-132">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 <span data-ttu-id="42833-133">[Crear un punto de conexión de creación de reflejo de la base de datos para la autenticación de Windows &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="42833-133">[Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span></span>  
 <span data-ttu-id="42833-134">[Iniciar el Monitor de creación de reflejo de la base de datos &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="42833-134">[Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="42833-135">Creación de reflejo de la base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="42833-135">Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)  
  
  
