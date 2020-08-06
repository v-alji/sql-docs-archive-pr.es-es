---
title: Crear un extremo de creación de reflejo de la base de datos para Grupos de disponibilidad AlwaysOn (SQL Server PowerShell) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], server instance
- Availability Groups [SQL Server], deploying
- Availability Groups [SQL Server], endpoint
ms.assetid: 6197bbe7-67d4-446d-ba5f-cabfa5df77f1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 56058ff8aa72d2471381dd87fb25a3b68356ed36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752330"
---
# <a name="create-a-database-mirroring-endpoint-for-alwayson-availability-groups-sql-server-powershell"></a><span data-ttu-id="0d91f-102">Crear un extremo de creación de reflejo de la base de datos para grupos de disponibilidad AlwaysOn (SQL Server PowerShell)</span><span class="sxs-lookup"><span data-stu-id="0d91f-102">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups (SQL Server PowerShell)</span></span>
  <span data-ttu-id="0d91f-103">En este tema se describe cómo crear un extremo de creación de reflejo de la base de datos para uso de [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0d91f-103">This topic describes how to create a database mirroring endpoint for use by [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using PowerShell.</span></span>  
  
 <span data-ttu-id="0d91f-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="0d91f-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0d91f-105">**Antes de empezar:**  [Seguridad](#Security)</span><span class="sxs-lookup"><span data-stu-id="0d91f-105">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="0d91f-106">**Para crear un extremo de creación de reflejo de la base de datos utilizando:**  [PowerShell](#PowerShellProcedure)</span><span class="sxs-lookup"><span data-stu-id="0d91f-106">**To create a database mirroring endpoint, using:**  [PowerShell](#PowerShellProcedure)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="0d91f-107">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="0d91f-107">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0d91f-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="0d91f-108">Security</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0d91f-109">El algoritmo RC4 está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="0d91f-109">The RC4 algorithm is deprecated.</span></span> [!INCLUDE[ssNoteDepFutureDontUse](../../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="0d91f-110">Se recomienda utilizar AES.</span><span class="sxs-lookup"><span data-stu-id="0d91f-110">We recommend that you use AES.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0d91f-111">Permisos</span><span class="sxs-lookup"><span data-stu-id="0d91f-111">Permissions</span></span>  
 <span data-ttu-id="0d91f-112">Requiere permiso CREATE ENDPOINT o pertenecer al rol fijo de servidor sysadmin.</span><span class="sxs-lookup"><span data-stu-id="0d91f-112">Requires CREATE ENDPOINT permission, or membership in the sysadmin fixed server role.</span></span> <span data-ttu-id="0d91f-113">Para obtener más información, vea [GRANT &#40;permisos de punto de conexión de Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0d91f-113">For more information, see [GRANT Endpoint Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql).</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="0d91f-114">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="0d91f-114">Using PowerShell</span></span>  
 <span data-ttu-id="0d91f-115">**Para crear un extremo de creación de reflejo de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="0d91f-115">**To create a database mirroring endpoint**</span></span>  
  
1.  <span data-ttu-id="0d91f-116">Cambie el directorio (`cd`) a la instancia del servidor para la que desea crear el extremo de creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0d91f-116">Change directory (`cd`) to the server instance for which you want to create the database mirroring endpoint.</span></span>  
  
2.  <span data-ttu-id="0d91f-117">Utilice el cmdlet `New-SqlHadrEndpoint` para crear el extremo y utilice después `Set-SqlHadrEndpoint` para iniciar el extremo.</span><span class="sxs-lookup"><span data-stu-id="0d91f-117">Use the `New-SqlHadrEndpoint` cmdlet to create the endpoint and then use the `Set-SqlHadrEndpoint` to start the endpoint.</span></span>  
  
###  <a name="example-powershell"></a><a name="PShellExample"></a> <span data-ttu-id="0d91f-118">Ejemplo (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="0d91f-118">Example (PowerShell)</span></span>  
 <span data-ttu-id="0d91f-119">Los siguientes comandos de PowerShell crean un extremo de creación de reflejo de la base de datos en una instancia de SQL Server (instancia de*equipo* \\ *Instance*).</span><span class="sxs-lookup"><span data-stu-id="0d91f-119">The following PowerShell commands create a database mirroring endpoint on an instance of SQL Server (*Machine*\\*Instance*).</span></span> <span data-ttu-id="0d91f-120">El extremo utiliza el puerto 5022.</span><span class="sxs-lookup"><span data-stu-id="0d91f-120">The endpoint uses port 5022.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0d91f-121">Este ejemplo solamente funciona en una instancia de servidor que no disponga actualmente de un extremo de creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0d91f-121">This example works only on a server instance that currently lack a database mirroring endpoint.</span></span>  
  
```powershell
# Create the endpoint.  
$endpoint = New-SqlHadrEndpoint MyMirroringEndpoint -Port 5022 -Path SQLSERVER:\SQL\Machine\Instance  
  
# Start the endpoint  
Set-SqlHadrEndpoint -InputObject $endpoint -State "Started"
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="0d91f-122">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="0d91f-122">Related Tasks</span></span>  
 <span data-ttu-id="0d91f-123">**Para configurar un extremo de creación del reflejo de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="0d91f-123">**To Configure a Database Mirroring Endpoint**</span></span>  
  
-   [<span data-ttu-id="0d91f-124">Crear un punto de conexión de creación de reflejo de la base de datos para la autenticación de Windows &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0d91f-124">Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md)  
  
-   [<span data-ttu-id="0d91f-125">Usar certificados para un punto de conexión de creación de reflejo de la base de datos &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0d91f-125">Use Certificates for a Database Mirroring Endpoint &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/use-certificates-for-a-database-mirroring-endpoint-transact-sql.md)  
  
    -   [<span data-ttu-id="0d91f-126">Permitir que un punto de conexión de creación de reflejo de la base de datos utilice certificados para las conexiones salientes &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0d91f-126">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/database-mirroring-use-certificates-for-outbound-connections.md)  
  
    -   [<span data-ttu-id="0d91f-127">Permitir que un punto de conexión de creación de reflejo de la base de datos use certificados para las conexiones entrantes &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0d91f-127">Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/database-mirroring-use-certificates-for-inbound-connections.md)  
  
-   [<span data-ttu-id="0d91f-128">Especificar una dirección de red de servidor &#40;creación de reflejo de la base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="0d91f-128">Specify a Server Network Address &#40;Database Mirroring&#41;</span></span>](../../database-mirroring/specify-a-server-network-address-database-mirroring.md)  
  
-   [<span data-ttu-id="0d91f-129">Especificar la dirección URL del punto de conexión al agregar o modificar una réplica de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0d91f-129">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
 <span data-ttu-id="0d91f-130">**Para ver información acerca del extremo de creación de reflejo de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="0d91f-130">**To View Information About the Database Mirroring Endpoint**</span></span>  
  
-   [<span data-ttu-id="0d91f-131">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0d91f-131">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="0d91f-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0d91f-132">See Also</span></span>  
 <span data-ttu-id="0d91f-133">[Crear un grupo de disponibilidad &#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="0d91f-133">[Create an Availability Group &#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md) </span></span>  
 [<span data-ttu-id="0d91f-134">Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0d91f-134">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
