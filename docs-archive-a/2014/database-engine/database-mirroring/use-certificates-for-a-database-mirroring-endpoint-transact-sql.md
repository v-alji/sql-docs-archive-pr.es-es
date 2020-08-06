---
title: Usar certificados para un punto de conexión de creación de reflejo de la base de datos (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], deployment
- certificates [SQL Server], database mirroring
- authentication [SQL Server], database mirroring
- database mirroring [SQL Server], security
ms.assetid: f7c23cc2-48dc-4b78-b441-89ca29a0bd9e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c159e66e798524c41bf6e653283c299cc8393be5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671673"
---
# <a name="use-certificates-for-a-database-mirroring-endpoint-transact-sql"></a><span data-ttu-id="24e5a-102">Usar certificados para un extremo de creación de reflejo de la base de datos (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="24e5a-102">Use Certificates for a Database Mirroring Endpoint (Transact-SQL)</span></span>
  <span data-ttu-id="24e5a-103">Para habilitar la autenticación de certificados para la creación de reflejos de la base de datos en una instancia determinada del servidor, el administrador del sistema debe configurar cada instancia del servidor para que utilice certificados en las conexiones de entrada y salida.</span><span class="sxs-lookup"><span data-stu-id="24e5a-103">To enable certificate authentication for database mirroring on a given server instance, the system administrator must configure each server instance to use certificates on both outbound and inbound connections.</span></span> <span data-ttu-id="24e5a-104">Las conexiones de salida deben configurarse en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="24e5a-104">Outbound connections must be configured first.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="24e5a-105">Todas las conexiones de creación de reflejo en una instancia de servidor utilizan un único extremo de reflejo de la base de datos; debe especificar el método de autenticación de la instancia de servidor cuando cree el extremo.</span><span class="sxs-lookup"><span data-stu-id="24e5a-105">All mirroring connections on a server instance use a single database mirroring endpoint, and you must specify the authentication method of the server instance when you create the endpoint.</span></span> <span data-ttu-id="24e5a-106">Por tanto, en la creación de reflejo de la base de datos solo puede utilizar un formulario de autenticación por cada instancia de servidor.</span><span class="sxs-lookup"><span data-stu-id="24e5a-106">Therefore, you can use only one form of authentication per server instance for database mirroring.</span></span>  
  
## <a name="configuring-outbound-connections"></a><span data-ttu-id="24e5a-107">Configurar conexiones salientes</span><span class="sxs-lookup"><span data-stu-id="24e5a-107">Configuring Outbound Connections</span></span>  
 <span data-ttu-id="24e5a-108">Siga estos pasos en cada instancia de servidor que configure para la creación de reflejo de la base de datos:</span><span class="sxs-lookup"><span data-stu-id="24e5a-108">Follow these steps on each server instance that you are configuring for database mirroring:</span></span>  
  
1.  <span data-ttu-id="24e5a-109">En la base de datos **maestra** , cree una clave maestra de base de datos.</span><span class="sxs-lookup"><span data-stu-id="24e5a-109">In the **master** database, create a database master key.</span></span>  
  
2.  <span data-ttu-id="24e5a-110">En la base de datos **maestra** , cree un certificado cifrado en la instancia de servidor.</span><span class="sxs-lookup"><span data-stu-id="24e5a-110">In the **master** database, create an encrypted certificate on the server instance.</span></span>  
  
3.  <span data-ttu-id="24e5a-111">Cree un extremo para la instancia de servidor utilizando su certificado.</span><span class="sxs-lookup"><span data-stu-id="24e5a-111">Create an endpoint for the server instance using its certificate.</span></span>  
  
4.  <span data-ttu-id="24e5a-112">Realice una copia de seguridad del certificado en un archivo. A continuación, cópiela de forma segura a los demás sistemas.</span><span class="sxs-lookup"><span data-stu-id="24e5a-112">Back up the certificate to a file and securely copy it to the other system or systems.</span></span>  
  
 <span data-ttu-id="24e5a-113">Debe completar estos pasos para cada asociado y el testigo, si existe.</span><span class="sxs-lookup"><span data-stu-id="24e5a-113">You must complete these steps for each partner and the witness, if there is one.</span></span>  
  
 <span data-ttu-id="24e5a-114">Para obtener más información, vea [Permitir que un punto de conexión de creación de reflejo de la base de datos utilice certificados para las conexiones salientes &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="24e5a-114">For more information, see [Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span></span>  
  
## <a name="configuring-inbound-connections"></a><span data-ttu-id="24e5a-115">Configurar conexiones entrantes</span><span class="sxs-lookup"><span data-stu-id="24e5a-115">Configuring Inbound Connections</span></span>  
 <span data-ttu-id="24e5a-116">A continuación, siga estos pasos para cada asociado que configure para la creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="24e5a-116">Next, follow these steps for each partner that you are configuring for database mirroring.</span></span> <span data-ttu-id="24e5a-117">En la base de datos **maestra** :</span><span class="sxs-lookup"><span data-stu-id="24e5a-117">In the **master** database:</span></span>  
  
1.  <span data-ttu-id="24e5a-118">Cree un inicio de sesión para el otro sistema.</span><span class="sxs-lookup"><span data-stu-id="24e5a-118">Create a login for the other system.</span></span>  
  
2.  <span data-ttu-id="24e5a-119">Cree un usuario para dicho inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="24e5a-119">Create a user for that login.</span></span>  
  
3.  <span data-ttu-id="24e5a-120">Obtenga el certificado para el extremo de reflejo de la otra instancia de servidor.</span><span class="sxs-lookup"><span data-stu-id="24e5a-120">Obtain the certificate for the mirroring endpoint of the other server instance.</span></span>  
  
4.  <span data-ttu-id="24e5a-121">Asociar el certificado al usuario creado en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="24e5a-121">Associate the certificate with the user created in step 2.</span></span>  
  
5.  <span data-ttu-id="24e5a-122">Conceda el permiso CONNECT para el inicio de sesión para el extremo de reflejo.</span><span class="sxs-lookup"><span data-stu-id="24e5a-122">Grant CONNECT permission on the login for that mirroring endpoint.</span></span>  
  
 <span data-ttu-id="24e5a-123">Si existe un testigo, también debe configurar conexiones de entrada para él.</span><span class="sxs-lookup"><span data-stu-id="24e5a-123">If there is a witness, you must also set up inbound connections for it.</span></span> <span data-ttu-id="24e5a-124">Esto requiere la configuración de inicios de sesión, usuarios y certificados para el testigo en los dos asociados y viceversa.</span><span class="sxs-lookup"><span data-stu-id="24e5a-124">This requires setting up logins, users, and certificates for the witness on both of the partners, and vice versa.</span></span>  
  
 <span data-ttu-id="24e5a-125">Para obtener más información, vea [Permitir que un punto de conexión de creación de reflejo de la base de datos utilice certificados para las conexiones entrantes &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="24e5a-125">For more information, see [Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span></span>  
  
## <a name="security"></a><span data-ttu-id="24e5a-126">Seguridad</span><span class="sxs-lookup"><span data-stu-id="24e5a-126">Security</span></span>  
 <span data-ttu-id="24e5a-127">A menos que garantice que su red es segura, se recomienda utilizar el cifrado para las conexiones de creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="24e5a-127">Unless you can guarantee that your network is secure, we recommend that you use encryption for database mirroring connections.</span></span> <span data-ttu-id="24e5a-128">Para obtener más información, vea [El punto de conexión de creación de reflejo de la base de datos &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="24e5a-128">For more information, see [The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md).</span></span>  
  
 <span data-ttu-id="24e5a-129">Cuando copie un certificado en otro sistema, utilice un método de copia seguro.</span><span class="sxs-lookup"><span data-stu-id="24e5a-129">When copying a certificate to another system, use a secure copy method.</span></span> <span data-ttu-id="24e5a-130">Tenga mucho cuidado de mantener todos sus certificados protegidos.</span><span class="sxs-lookup"><span data-stu-id="24e5a-130">Be extremely careful to keep all of your certificates secure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24e5a-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="24e5a-131">See Also</span></span>  
 <span data-ttu-id="24e5a-132">[Crear la clave maestra de una base de datos](../../relational-databases/security/encryption/create-a-database-master-key.md) </span><span class="sxs-lookup"><span data-stu-id="24e5a-132">[Create a Database Master Key](../../relational-databases/security/encryption/create-a-database-master-key.md) </span></span>  
 <span data-ttu-id="24e5a-133">[CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="24e5a-133">[CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql) </span></span>  
 <span data-ttu-id="24e5a-134">[Seguridad de transporte para la creación de reflejo de la base de datos y Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="24e5a-134">[Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span></span>  
 <span data-ttu-id="24e5a-135">[Centro de seguridad para el motor de base de datos SQL Server y la base de datos SQL Azure](../../relational-databases/security/security-center-for-sql-server-database-engine-and-azure-sql-database.md) </span><span class="sxs-lookup"><span data-stu-id="24e5a-135">[Security Center for SQL Server Database Engine and Azure SQL Database](../../relational-databases/security/security-center-for-sql-server-database-engine-and-azure-sql-database.md) </span></span>  
 [<span data-ttu-id="24e5a-136">El punto de conexión de creación de reflejo de la base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="24e5a-136">The Database Mirroring Endpoint &#40;SQL Server&#41;</span></span>](the-database-mirroring-endpoint-sql-server.md)  
  
  
