---
title: Usar el Asistente para agregar réplica de Azure (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.addreplicawizard.azurereplica.f1
ms.assetid: b89cc41b-07b4-49f3-82cc-bc42b2e793ae
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8f7ee9e80f0511fe23aebb887b15b5e8b7e9cabf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744308"
---
# <a name="use-the-add-azure-replica-wizard-sql-server"></a><span data-ttu-id="02ef2-102">Usar el Asistente para agregar réplica de Azure (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="02ef2-102">Use the Add Azure Replica Wizard (SQL Server)</span></span>
  <span data-ttu-id="02ef2-103">Use el Asistente para agregar una réplica de Azure para ayudarle a crear una nueva máquina virtual de Azure en ti híbrida y configurarla como una réplica secundaria para un grupo de disponibilidad AlwaysOn nuevo o existente.</span><span class="sxs-lookup"><span data-stu-id="02ef2-103">Use the Add Azure Replica Wizard to help you create a new Azure VM in hybrid IT and configure it as a secondary replica for a new or existing AlwaysOn availability group.</span></span>  
  
-   <span data-ttu-id="02ef2-104">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="02ef2-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="02ef2-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="02ef2-105">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="02ef2-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="02ef2-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="02ef2-107">**Para agregar una réplica con:**  [Asistente Agregar réplica de Microsoft Azure (SQL Server Management Studio)](#SSMSProcedure)</span><span class="sxs-lookup"><span data-stu-id="02ef2-107">**To add a replica, using:**  [Add Azure Replica Wizard (SQL Server Management Studio)](#SSMSProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="02ef2-108">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="02ef2-108">Before You Begin</span></span>  
 <span data-ttu-id="02ef2-109">Si nunca ha agregado ninguna réplica de disponibilidad a un grupo de disponibilidad, vea las secciones "instancias del servidor" y "grupos y réplicas de disponibilidad" en [requisitos previos, restricciones y recomendaciones para obtener Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="02ef2-109">If you have never added any availability replica to an availability group, see the "Server instances" and "Availability groups and replicas" sections in [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="02ef2-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="02ef2-110">Prerequisites</span></span>  
  
-   <span data-ttu-id="02ef2-111">Debe estar conectado a la instancia del servidor que hospeda la réplica principal actual.</span><span class="sxs-lookup"><span data-stu-id="02ef2-111">You must be connected to the server instance that hosts the current primary replica.</span></span>  
  
-   <span data-ttu-id="02ef2-112">Debe tener un entorno de tecnologías informáticas híbrido donde la subred local tenga una VPN de sitio a sitio con Azure.</span><span class="sxs-lookup"><span data-stu-id="02ef2-112">You must have a hybrid-IT environment where your on-premise subnet has a site-to-site VPN with Azure.</span></span> <span data-ttu-id="02ef2-113">Para obtener más información, vea [Configurar una VPN de sitio a sitio en el Portal de administración](https://azure.microsoft.com/documentation/articles/vpn-gateway-site-to-site-create).</span><span class="sxs-lookup"><span data-stu-id="02ef2-113">For more information, see [Configure a Site-to-Site VPN in the Management Portal](https://azure.microsoft.com/documentation/articles/vpn-gateway-site-to-site-create).</span></span>  
  
-   <span data-ttu-id="02ef2-114">Es preciso que el grupo de disponibilidad cuente con réplicas locales disponibles.</span><span class="sxs-lookup"><span data-stu-id="02ef2-114">Your availability group must contain on-premise availability replicas.</span></span>  
  
-   <span data-ttu-id="02ef2-115">Los clientes del agente de escucha del grupo de disponibilidad deben disponer de conectividad a Internet si van a mantener la conectividad con el agente de escucha cuando el grupo de disponibilidad haya provocado una conmutación por error en una réplica de Azure.</span><span class="sxs-lookup"><span data-stu-id="02ef2-115">Clients to the availability group listener must have connectivity to the Internet if they want to maintain connectivity with the listener when the availability group is failed over to an Azure replica.</span></span>  
  
-   <span data-ttu-id="02ef2-116">**Requisitos previos para usar la sincronización de datos inicial completa** Deberá especificar un recurso compartido de red para que el asistente cree copias de seguridad y pueda tener acceso a estas.</span><span class="sxs-lookup"><span data-stu-id="02ef2-116">**Prerequisites for using full initial data synchronization** You will need to specify a network share in order for the wizard to create and access backups.</span></span> <span data-ttu-id="02ef2-117">Para la réplica principal, la cuenta usada para iniciar el [!INCLUDE[ssDE](../../../includes/ssde-md.md)] debe tener permisos del sistema de archivos de lectura y escritura en un recurso compartido de red.</span><span class="sxs-lookup"><span data-stu-id="02ef2-117">For the primary replica, the account used to start the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] must have read and write file-system permissions on a network share.</span></span> <span data-ttu-id="02ef2-118">Para las réplicas secundarias, la cuenta debe tener permiso de lectura en el recurso compartido de red.</span><span class="sxs-lookup"><span data-stu-id="02ef2-118">For secondary replicas, the account must have read permission on the network share.</span></span>  
  
     <span data-ttu-id="02ef2-119">Si no puede utilizar el asistente para realizar la sincronización de datos inicial completa, debe preparar las bases de datos secundarias manualmente.</span><span class="sxs-lookup"><span data-stu-id="02ef2-119">If you are unable to use the wizard to perform full initial data synchronization, you need to prepare your secondary databases manually.</span></span> <span data-ttu-id="02ef2-120">Puede hacerlo antes o después de ejecutar el asistente.</span><span class="sxs-lookup"><span data-stu-id="02ef2-120">You can do this before or after running the wizard.</span></span> <span data-ttu-id="02ef2-121">Para obtener más información, vea [Preparar manualmente una base de datos secundaria para un grupo de disponibilidad &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="02ef2-121">For more information, see [Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="02ef2-122">Seguridad</span><span class="sxs-lookup"><span data-stu-id="02ef2-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="02ef2-123">Permisos</span><span class="sxs-lookup"><span data-stu-id="02ef2-123">Permissions</span></span>  
 <span data-ttu-id="02ef2-124">Consulte [Security](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md#Security)</span><span class="sxs-lookup"><span data-stu-id="02ef2-124">See [Security](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md#Security)</span></span>  
  
##  <a name="using-the-add-azure-replica-wizard-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="02ef2-125">Usar el Asistente para agregar réplica de Azure (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="02ef2-125">Using the Add Azure Replica Wizard (SQL Server Management Studio)</span></span>  
 <span data-ttu-id="02ef2-126">El Asistente para agregar réplica de Azure se puede iniciar desde [Especificar la página de réplicas](specify-replicas-page-new-availability-group-wizard-add-replica-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="02ef2-126">The Add Azure Replica Wizard can be launched from the [Specify Replicas Page](specify-replicas-page-new-availability-group-wizard-add-replica-wizard.md).</span></span> <span data-ttu-id="02ef2-127">Hay dos formas de llegar a esta opción:</span><span class="sxs-lookup"><span data-stu-id="02ef2-127">There are two ways to reach this page:</span></span>  
  
-   [<span data-ttu-id="02ef2-128">Usar el Asistente para grupo de disponibilidad &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="02ef2-128">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="02ef2-129">Usar el Asistente para agregar una réplica al grupo de disponibilidad &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="02ef2-129">Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
 <span data-ttu-id="02ef2-130">Una vez que haya iniciado el Asistente para agregar réplica de Azure, siga los pasos a continuación:</span><span class="sxs-lookup"><span data-stu-id="02ef2-130">Once you have launched the Add Azure Replica Wizard, follow the steps below:</span></span>  
  
1.  <span data-ttu-id="02ef2-131">En primer lugar, descargue un certificado de administración para la suscripción de Azure.</span><span class="sxs-lookup"><span data-stu-id="02ef2-131">First, download a management certificate for your Azure subscription.</span></span> <span data-ttu-id="02ef2-132">Haga clic en **Descargar** para abrir la página de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="02ef2-132">Click **Download** to open the sign-in page.</span></span>  
  
2.  <span data-ttu-id="02ef2-133">En la página de inicio de sesión, inicie sesión en su suscripción de Azure.</span><span class="sxs-lookup"><span data-stu-id="02ef2-133">In the sign-in page, sign in to your Azure subscription.</span></span> <span data-ttu-id="02ef2-134">Una vez que haya iniciado sesión, el asistente instala un certificado de administración en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="02ef2-134">Once you are signed in, the wizard installs a management certificate onto your local machine.</span></span> <span data-ttu-id="02ef2-135">Este certificado de administración se cargará automáticamente cuando vuelva a usar este asistente.</span><span class="sxs-lookup"><span data-stu-id="02ef2-135">This management certificate is automatically loaded when you use this wizard again.</span></span> <span data-ttu-id="02ef2-136">Si ha descargado varios certificados de administración, puede hacer clic en el botón **...** para seleccionar el que desea usar.</span><span class="sxs-lookup"><span data-stu-id="02ef2-136">If you have downloaded multiple management certificates, you can click the **...** button to select the one you want to use.</span></span>  
  
3.  <span data-ttu-id="02ef2-137">A continuación, haga clic en **Conectar**para conectarse a su suscripción.</span><span class="sxs-lookup"><span data-stu-id="02ef2-137">Next, connect to your subscription by clicking **Connect**.</span></span> <span data-ttu-id="02ef2-138">Cuando lo haya hecho, las listas desplegables se rellenan con los parámetros de Azure, como **Red virtual** y **Subred de la red virtual**.</span><span class="sxs-lookup"><span data-stu-id="02ef2-138">Once you are connected, the drop-down lists are populated with your Azure parameters, such as **Virtual Network** and **Virtual Network Subnet**.</span></span>  
  
4.  <span data-ttu-id="02ef2-139">Especifique los valores de configuración para la máquina virtual de Azure que hospedará la nueva réplica secundaria:</span><span class="sxs-lookup"><span data-stu-id="02ef2-139">Specify the settings for the Azure VM that will host the new secondary replica:</span></span>  
  
     <span data-ttu-id="02ef2-140">Imagen</span><span class="sxs-lookup"><span data-stu-id="02ef2-140">Image</span></span>  
     <span data-ttu-id="02ef2-141">Nombre de la imagen de SQL Server que se va a usar para la máquina virtual de Azure</span><span class="sxs-lookup"><span data-stu-id="02ef2-141">The name of the SQL Server image to use for the Azure VM</span></span>  
  
     <span data-ttu-id="02ef2-142">Tamaño de VM</span><span class="sxs-lookup"><span data-stu-id="02ef2-142">VM Size</span></span>  
     <span data-ttu-id="02ef2-143">Tamaño de la máquina virtual de Azure</span><span class="sxs-lookup"><span data-stu-id="02ef2-143">The size of the Azure VM</span></span>  
  
     <span data-ttu-id="02ef2-144">Nombre de la máquina virtual</span><span class="sxs-lookup"><span data-stu-id="02ef2-144">VM Name</span></span>  
     <span data-ttu-id="02ef2-145">Nombre DNS de la máquina virtual de Azure</span><span class="sxs-lookup"><span data-stu-id="02ef2-145">The DNS name of the Azure VM</span></span>  
  
     <span data-ttu-id="02ef2-146">Nombre de usuario de VM</span><span class="sxs-lookup"><span data-stu-id="02ef2-146">VM Username</span></span>  
     <span data-ttu-id="02ef2-147">Nombre de usuario del administrador predeterminado para la máquina virtual de Azure</span><span class="sxs-lookup"><span data-stu-id="02ef2-147">The username of the default administrator for the Azure VM</span></span>  
  
     <span data-ttu-id="02ef2-148">Contraseña del administrador de la máquina virtual (y confirmar contraseña)</span><span class="sxs-lookup"><span data-stu-id="02ef2-148">VM Administrator Password (and Confirm Password)</span></span>  
     <span data-ttu-id="02ef2-149">Contraseña del administrador predeterminado para la máquina virtual de Azure</span><span class="sxs-lookup"><span data-stu-id="02ef2-149">The password for the default administrator for the Azure VM</span></span>  
  
     <span data-ttu-id="02ef2-150">Virtual Network</span><span class="sxs-lookup"><span data-stu-id="02ef2-150">Virtual Network</span></span>  
     <span data-ttu-id="02ef2-151">Red virtual en la que estará la máquina virtual de Azure</span><span class="sxs-lookup"><span data-stu-id="02ef2-151">The virtual network in which to place the Azure VM</span></span>  
  
     <span data-ttu-id="02ef2-152">Subred de la red virtual</span><span class="sxs-lookup"><span data-stu-id="02ef2-152">Virtual Network Subnet</span></span>  
     <span data-ttu-id="02ef2-153">Subred de la red virtual en la que estará la máquina virtual de Azure</span><span class="sxs-lookup"><span data-stu-id="02ef2-153">The virtual network subnet in which to place the Azure VM</span></span>  
  
     <span data-ttu-id="02ef2-154">Domain</span><span class="sxs-lookup"><span data-stu-id="02ef2-154">Domain</span></span>  
     <span data-ttu-id="02ef2-155">Dominio de Active Directory (AD) para combinar la máquina virtual de Azure</span><span class="sxs-lookup"><span data-stu-id="02ef2-155">The Active Directory (AD) domain to join the Azure VM</span></span>  
  
     <span data-ttu-id="02ef2-156">Nombre de usuario de dominio</span><span class="sxs-lookup"><span data-stu-id="02ef2-156">Domain Username</span></span>  
     <span data-ttu-id="02ef2-157">Nombre de usuario de AD que se usa para combinar la máquina virtual de Azure con el dominio</span><span class="sxs-lookup"><span data-stu-id="02ef2-157">The AD username used to join the Azure VM to the domain</span></span>  
  
     <span data-ttu-id="02ef2-158">Contraseña</span><span class="sxs-lookup"><span data-stu-id="02ef2-158">Password</span></span>  
     <span data-ttu-id="02ef2-159">Contraseña que se usa para combinar la máquina virtual de Azure con el dominio</span><span class="sxs-lookup"><span data-stu-id="02ef2-159">The password used to join the Azure VM to the domain</span></span>  
  
5.  <span data-ttu-id="02ef2-160">Haga clic en **Aceptar** para confirmar los valores de configuración y salir del Asistente para agregar réplica de Azure.</span><span class="sxs-lookup"><span data-stu-id="02ef2-160">Click **OK** to commit your settings and exit the Add Azure Replica Wizard.</span></span>  
  
6.  <span data-ttu-id="02ef2-161">Continúe con el resto de los pasos de configuración para [Especificar la página de réplicas](specify-replicas-page-new-availability-group-wizard-add-replica-wizard.md) , tal como hace para las réplicas nuevas.</span><span class="sxs-lookup"><span data-stu-id="02ef2-161">Continue with the rest of the configuration steps for [Specify Replicas Page](specify-replicas-page-new-availability-group-wizard-add-replica-wizard.md) as you do for any new replica.</span></span>  
  
     <span data-ttu-id="02ef2-162">Una vez que haya terminado con el Asistente para grupo de disponibilidad o el Asistente para agregar una réplica al grupo de disponibilidad, el proceso de configuración realizará todas las operaciones en Azure para crear la nueva máquina virtual, unirla al dominio de AD, agregarla al clúster de Windows, habilitar la alta disponibilidad de AlwaysOn y agregar la nueva réplica al grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="02ef2-162">Once you are finished with the Availability Group Wizard or the Add Replica to Availability Group Wizard, the configuration process performs all operations in Azure to create the new VM, join it to the AD domain, add it to the Windows cluster, enable AlwaysOn High Availability, and add the new replica to the availability group.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="02ef2-163">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="02ef2-163">Related Tasks</span></span>  
  
-   [<span data-ttu-id="02ef2-164">Agregar una réplica secundaria a un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="02ef2-164">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="02ef2-165">Consulte también</span><span class="sxs-lookup"><span data-stu-id="02ef2-165">See Also</span></span>  
 <span data-ttu-id="02ef2-166">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="02ef2-166">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="02ef2-167">[Requisitos previos, restricciones y recomendaciones para el SQL Server de &#40;de Grupos de disponibilidad AlwaysOn&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="02ef2-167">[Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span></span>  
 [<span data-ttu-id="02ef2-168">Agregar una réplica secundaria a un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="02ef2-168">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
  
