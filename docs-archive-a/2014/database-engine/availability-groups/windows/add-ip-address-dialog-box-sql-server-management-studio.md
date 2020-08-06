---
title: Agregar dirección IP (cuadro de diálogo - SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygrouplistener.addipaddress.f1
ms.assetid: 98c9ad3b-ff3c-4c1d-b344-59a72fca137c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5192e6414b34bee6de09d45a7284f25404235dc7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663724"
---
# <a name="add-ip-address-dialog-box-sql-server-management-studio"></a><span data-ttu-id="a2165-102">Agregar dirección IP (cuadro de diálogo - SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="a2165-102">Add IP Address Dialog Box (SQL Server Management Studio)</span></span>
  <span data-ttu-id="a2165-103"> En este tema de Ayuda F1 se describen las opciones del cuadro de diálogo **Agregar dirección IP**.</span><span class="sxs-lookup"><span data-stu-id="a2165-103">This F1 help topic describes the options of the **Add IP Address** dialog box.</span></span> <span data-ttu-id="a2165-104">Se accede a este cuadro de diálogo desde el cuadro de diálogo **Nuevo agente de escucha del grupo de disponibilidad** y la pestaña **Escucha** de la página **Especificar réplicas** de [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] o [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)] de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a2165-104">This dialog box accessed from the **New Availability Group Listener** dialog box and the **Listener** tab of the **Specify Replicas** page of the [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] or the [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)] of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a2165-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a2165-105">Prerequisites</span></span>  
 <span data-ttu-id="a2165-106">Antes de empezar a agregar subredes un agente de escucha del grupo de disponibilidad, asegúrese de que conoce la dirección IP para cada subred y, para una dirección IPv4, la máscara de subred.</span><span class="sxs-lookup"><span data-stu-id="a2165-106">Before you begin to add subnets to an availability group listener, ensure that know the IP address for each subnet and, for an IPv4 address, the subnet mask.</span></span>  
  
##  <a name="add-ip-address-options"></a><a name="PageOptions"></a> <span data-ttu-id="a2165-107">Agregar las opciones de la dirección IP</span><span class="sxs-lookup"><span data-stu-id="a2165-107">Add IP Address Options</span></span>  
 <span data-ttu-id="a2165-108">**Subred**</span><span class="sxs-lookup"><span data-stu-id="a2165-108">**Subnet**</span></span>  
 <span data-ttu-id="a2165-109">Utilice la lista desplegable para seleccionar una dirección de la subred que va a agregar al agente de escucha del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="a2165-109">Use the drop list to select an address for the subnet that you are adding to the availability group listener.</span></span> <span data-ttu-id="a2165-110">De forma predeterminada, una subred posee una dirección IPv4 como una dirección IPv6.</span><span class="sxs-lookup"><span data-stu-id="a2165-110">By default a subnet possesses both an IPv4 address and an IPv6 address.</span></span> <span data-ttu-id="a2165-111">La primera vez que use el cuadro de diálogo **Agregar dirección IP** , la lista desplegable **Subred** mostrará las dos direcciones de subred para cada subred que hospeda una réplica para el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="a2165-111">The first time you use the **Add IP Address** dialog,  the **Subnet** drop list displays both subnet addresses for each subnet that hosts a replica for the availability group.</span></span> <span data-ttu-id="a2165-112">Para agregar una subred dada al agente de escucha, seleccione una de sus direcciones de subred.</span><span class="sxs-lookup"><span data-stu-id="a2165-112">To add a given subnet to the listener, select one of its subnet addresses.</span></span>  
  
 <span data-ttu-id="a2165-113">Después de completar el cuadro de diálogo **Agregar dirección IP** y hacer clic en **Aceptar** para agregar una dirección de subred seleccionada al agente de escucha, la lista desplegable **Subred** filtrará la dirección de subred.</span><span class="sxs-lookup"><span data-stu-id="a2165-113">After you complete the **Add IP Address** dialog box and click **OK** to add a selected subnet address to the listener, the **Subnet** drop list filters out that subnet address.</span></span> <span data-ttu-id="a2165-114">Todas las direcciones de subred no seleccionadas permanecerán en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="a2165-114">All unselected subnet addresses remain on the drop list.</span></span> <span data-ttu-id="a2165-115">Asegúrese de agregar una y solo una dirección de subred por subred al agente de escucha; de lo contrario, la creación del agente de escucha producirá un error.</span><span class="sxs-lookup"><span data-stu-id="a2165-115">Be sure that you add one and only one subnet address per subnet to the listener, or listener creation will fail.</span></span>  
  
 <span data-ttu-id="a2165-116">**Direcciones**</span><span class="sxs-lookup"><span data-stu-id="a2165-116">**Addresses**</span></span>  
 <span data-ttu-id="a2165-117">Utilice este campo para escribir una dirección IP estática para la dirección de subred seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a2165-117">Use this field to enter a static IP address for the selected subnet address.</span></span> <span data-ttu-id="a2165-118">Póngase en contacto con su administrador de red para esta dirección IP.</span><span class="sxs-lookup"><span data-stu-id="a2165-118">Contact your network administrator for this IP address.</span></span> <span data-ttu-id="a2165-119">Asegúrese de escribir una dirección válida para la dirección de subred seleccionada; de lo contrario, la creación del agente de escucha producirá un error.</span><span class="sxs-lookup"><span data-stu-id="a2165-119">Ensure that you enter a valid address for the selected subnet address, or listener creation will fail.</span></span>  
  
 <span data-ttu-id="a2165-120">**Dirección IPv4**</span><span class="sxs-lookup"><span data-stu-id="a2165-120">**IPv4 Address**</span></span>  
 <span data-ttu-id="a2165-121">Si ha seleccionado una dirección IPv4 de una subred, escriba aquí una dirección estática IPv4 válida.</span><span class="sxs-lookup"><span data-stu-id="a2165-121">If you selected the IPv4 subnet address of a subnet, enter a valid IPv4 static address here.</span></span>  
  
 <span data-ttu-id="a2165-122">**Máscara de subred**</span><span class="sxs-lookup"><span data-stu-id="a2165-122">**Subnet Mask**</span></span>  
 <span data-ttu-id="a2165-123">Para una dirección IPv4, este campo de solo lectura muestra la máscara de subred de la subred seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a2165-123">For an IPv4 address, this read-only field displays the subnet mask of the selected subnet.</span></span>  
  
 <span data-ttu-id="a2165-124">**Dirección IPv6**</span><span class="sxs-lookup"><span data-stu-id="a2165-124">**IPv6 Address**</span></span>  
 <span data-ttu-id="a2165-125">Si ha seleccionado una dirección IPv6 de una subred, escriba aquí una dirección estática IPv6 válida.</span><span class="sxs-lookup"><span data-stu-id="a2165-125">If you selected the IPv6 subnet address of a subnet, enter a valid IPv6 static address here.</span></span>  
  
 <span data-ttu-id="a2165-126">**OK (CORRECTO)**</span><span class="sxs-lookup"><span data-stu-id="a2165-126">**OK**</span></span>  
 <span data-ttu-id="a2165-127">Haga clic para agregar la subred cuya dirección ha seleccionado, junto con la dirección IP estática que ha especificado.</span><span class="sxs-lookup"><span data-stu-id="a2165-127">Click to create add the subnet whose address you selected, along with the static IP address that you specified.</span></span> <span data-ttu-id="a2165-128">Una fila con estos valores se agregará a la cuadrícula de subred del cuadro de diálogo **Nuevo agente de escucha del grupo de disponibilidad** o **Especificar réplicas** .</span><span class="sxs-lookup"><span data-stu-id="a2165-128">A row containing these values will be added to the subnet grid of the **New Availability Group Listener** or **Specify Replicas** dialog box.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a2165-129">El cuadro de diálogo de **Agregar dirección IP** no comprueba la dirección IP.</span><span class="sxs-lookup"><span data-stu-id="a2165-129">The **Add IP Address** dialog does not verify the IP address.</span></span> <span data-ttu-id="a2165-130">Tampoco impide agregar la segunda dirección de subred para una subred ya agregada al agente de escucha del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="a2165-130">Also the dialog does not prevent you from adding the second subnet address for a subnet that you have already added to the availability group listener.</span></span>  
  
 <span data-ttu-id="a2165-131">**Cancelar**</span><span class="sxs-lookup"><span data-stu-id="a2165-131">**Cancel**</span></span>  
 <span data-ttu-id="a2165-132">Haga clic para cancelar las selecciones y volver al cuadro de diálogo **Nuevo agente de escucha de grupo de disponibilidad** o en la pestaña **Escucha** sin agregar una dirección IP estática para una subred.</span><span class="sxs-lookup"><span data-stu-id="a2165-132">Click to cancel your selections, and return to the **New Availability Group Listener** dialog box or **Listener** tab without adding a static IP address for any subnet.</span></span>  
  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="a2165-133">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="a2165-133">Related Tasks</span></span>  
  
-   [<span data-ttu-id="a2165-134">Crear o configurar un agente de escucha de grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a2165-134">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="a2165-135">Usar el cuadro de diálogo Nuevo grupo de disponibilidad &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="a2165-135">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="a2165-136">Usar el Asistente para agregar una réplica al grupo de disponibilidad &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="a2165-136">Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
  
## <a name="see-also"></a><span data-ttu-id="a2165-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a2165-137">See Also</span></span>  
 <span data-ttu-id="a2165-138">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a2165-138">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="a2165-139">[Agentes de escucha de grupo de disponibilidad, conectividad de cliente y conmutación por error de una aplicación &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span><span class="sxs-lookup"><span data-stu-id="a2165-139">[Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span></span>  
 [<span data-ttu-id="a2165-140">Conectividad de cliente de AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a2165-140">AlwaysOn Client Connectivity (SQL Server)</span></span>](always-on-client-connectivity-sql-server.md)  
  
  
