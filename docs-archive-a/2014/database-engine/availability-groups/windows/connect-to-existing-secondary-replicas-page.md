---
title: Página conectar a réplicas secundarias existentes (Asistente para agregar réplica y Asistente para agregar bases de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.addreplicawizard.connecttoreplicas.f1
- sql12.swb.adddatabasewizard.connecttoreplicas.f1
ms.assetid: 850f1bc8-d7d0-425c-bd7b-03f0e9d3348e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 80af8dfebd6e23a923ddf67438edabf9ab0e2f65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744872"
---
# <a name="connect-to-existing-secondary-replicas-page-add-replica-wizard-and-add-databases-wizard"></a><span data-ttu-id="87d06-102">Conectarse a la página Réplicas secundarias existentes (Asistente para agregar réplica/Asistente para agregar bases de datos)</span><span class="sxs-lookup"><span data-stu-id="87d06-102">Connect to Existing Secondary Replicas Page (Add Replica Wizard and Add Databases Wizard)</span></span>
  <span data-ttu-id="87d06-103"> En este tema de Ayuda se describen las opciones de la página **Conectar con réplicas secundarias existentes**.</span><span class="sxs-lookup"><span data-stu-id="87d06-103">This help topic describes the options of the **Connect to Existing Secondary Replicas** page.</span></span> <span data-ttu-id="87d06-104">Este tema se usa en [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)] y [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87d06-104">This topic is used by the [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)] and [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="87d06-105">**Columnas de cuadrícula:**</span><span class="sxs-lookup"><span data-stu-id="87d06-105">**Grid columns:**</span></span>  
 <span data-ttu-id="87d06-106">**Instancia del servidor**</span><span class="sxs-lookup"><span data-stu-id="87d06-106">**Server Instance**</span></span>  
 <span data-ttu-id="87d06-107">Muestra el nombre de la instancia del servidor que hospedará la réplica de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="87d06-107">Displays the name of the server instance that will host the availability replica.</span></span>  
  
 <span data-ttu-id="87d06-108">**Conectado como**</span><span class="sxs-lookup"><span data-stu-id="87d06-108">**Connected As**</span></span>  
 <span data-ttu-id="87d06-109">Muestra la cuenta que está conectada a la instancia de servidor, una vez que se ha establecido la conexión.</span><span class="sxs-lookup"><span data-stu-id="87d06-109">Displays the account that is connected to the server instance, once the connection has been established.</span></span> <span data-ttu-id="87d06-110">Si esta columna muestra “**No conectado**” para una instancia de servidor determinada, deberá hacer clic en el botón **Conectar** o **Conectar todo** .</span><span class="sxs-lookup"><span data-stu-id="87d06-110">If this column displays "**Not Connected**" for a given server instance, you will need to click either the **Connect** or **Connect All** button.</span></span>  
  
 <span data-ttu-id="87d06-111">**Conexión**</span><span class="sxs-lookup"><span data-stu-id="87d06-111">**Connect**</span></span>  
 <span data-ttu-id="87d06-112">Haga clic aquí si esta instancia de servidor se ejecuta en una cuenta diferente a las de otras instancias de servidor a las que necesite conectarse.</span><span class="sxs-lookup"><span data-stu-id="87d06-112">Click if this server instance is running under a different account than other server instances to which you need to connect.</span></span>  
  
 <span data-ttu-id="87d06-113">**Conectar todo**</span><span class="sxs-lookup"><span data-stu-id="87d06-113">**Connect All**</span></span>  
 <span data-ttu-id="87d06-114">Haga clic aquí solo si cada instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] a la que se deba conectar se ejecuta como un servicio en la misma cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="87d06-114">Click only if every instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to which you need to connect is running as a service in the same user account.</span></span>  
  
 <span data-ttu-id="87d06-115">**Cancelar**</span><span class="sxs-lookup"><span data-stu-id="87d06-115">**Cancel**</span></span>  
 <span data-ttu-id="87d06-116">Haga clic en esta opción para finalizar el asistente.</span><span class="sxs-lookup"><span data-stu-id="87d06-116">Click to cancel the wizard.</span></span> <span data-ttu-id="87d06-117">En la página **Conectar a la réplica secundaria existente** , al cancelar el asistente se sale sin realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="87d06-117">On the **Connect to Existing Secondary Replica** page, cancelling the wizard cause it to exit without performing any actions.</span></span>  
  

  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="87d06-118">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="87d06-118">Related Tasks</span></span>  
  
-   [<span data-ttu-id="87d06-119">Usar el Asistente para agregar una réplica al grupo de disponibilidad &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="87d06-119">Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="87d06-120">Usar el Asistente para agregar una base de datos al grupo de disponibilidad &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="87d06-120">Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](availability-group-add-database-to-group-wizard.md)  
  

  
## <a name="see-also"></a><span data-ttu-id="87d06-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="87d06-121">See Also</span></span>  
 [<span data-ttu-id="87d06-122">Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="87d06-122">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
