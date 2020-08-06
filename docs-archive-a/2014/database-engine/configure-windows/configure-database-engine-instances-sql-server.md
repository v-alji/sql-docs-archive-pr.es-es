---
title: Configurar instancias del motor de base de datos (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 84e36fcb-2c78-48e8-8e4b-bf784a3ee557
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: af7408ff66d1f0e41369ba095ce51ea590d316e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677889"
---
# <a name="configure-database-engine-instances-sql-server"></a><span data-ttu-id="8be93-102">Configurar instancias del motor de base de datos (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="8be93-102">Configure Database Engine Instances (SQL Server)</span></span>
  <span data-ttu-id="8be93-103">Cada instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)] debe configurarse satisfacer los requisitos de rendimiento y disponibilidad definidos para las bases de datos hospedadas por la instancia.</span><span class="sxs-lookup"><span data-stu-id="8be93-103">Each instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] must be configured to meet the performance and availability requirements defined for the databases hosted by the instance.</span></span> <span data-ttu-id="8be93-104">El [!INCLUDE[ssDE](../../includes/ssde-md.md)] incluye opciones de configuración que controlan comportamientos como el uso de recursos y la disponibilidad de características como la los comportamientos de control como el uso de los recursos y la disponibilidad de características como auditoría o recursividad de desencadenador.</span><span class="sxs-lookup"><span data-stu-id="8be93-104">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] includes configuration options that control behaviors such as resource usage and the availability of features such as auditing or trigger recursion.</span></span>  
  
## <a name="instance-configuration"></a><span data-ttu-id="8be93-105">Configuración de instancia</span><span class="sxs-lookup"><span data-stu-id="8be93-105">Instance Configuration</span></span>  
 <span data-ttu-id="8be93-106">Cuando una base de datos se implementa en producción a menudo hay un contrato de nivel de servicio (SLA) que define áreas como los niveles de rendimiento requeridos a partir de la base de datos y el nivel de disponibilidad necesario de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="8be93-106">When a database is deployed into production there is often a service level agreement (SLA) defining areas such as the levels of performance required from the database and the required availability level of the database.</span></span> <span data-ttu-id="8be93-107">Los términos del SLA controlan normalmente los requisitos de configuración para la instancia.</span><span class="sxs-lookup"><span data-stu-id="8be93-107">The terms of the SLA typically drive configuration requirements for the instance.</span></span>  
  
 <span data-ttu-id="8be93-108">Una instancia se configura normalmente inmediatamente después de que ha instalado.</span><span class="sxs-lookup"><span data-stu-id="8be93-108">An instance is usually configured immediately after it has been installed.</span></span> <span data-ttu-id="8be93-109">La configuración inicial se determina normalmente por los requisitos del SLA de los tipos de bases de datos planeadas para implementarse en la instancia.</span><span class="sxs-lookup"><span data-stu-id="8be93-109">The initial configuration is usually determined by the SLA requirements of the types of databases planned to be deployed to the instance.</span></span> <span data-ttu-id="8be93-110">Una vez implementadas las bases de datos, los administradores de bases de datos supervisan el rendimiento de la instancia y ajustan la configuración según sea necesaria si las métricas de rendimiento muestran que la instancia no cumple los requisitos del SLA.</span><span class="sxs-lookup"><span data-stu-id="8be93-110">After the databases have been deployed, the database administrators monitor the performance of the instance and adjust the configuration settings as needed if the performance metrics show the instance is not meeting the SLA requirements.</span></span>  
  
## <a name="configuration-tasks"></a><span data-ttu-id="8be93-111">Tareas de configuración</span><span class="sxs-lookup"><span data-stu-id="8be93-111">Configuration Tasks</span></span>  
  
|<span data-ttu-id="8be93-112">Descripción de la tarea</span><span class="sxs-lookup"><span data-stu-id="8be93-112">Task Description</span></span>|<span data-ttu-id="8be93-113">Tema</span><span class="sxs-lookup"><span data-stu-id="8be93-113">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="8be93-114">Describe las distintas opciones de configuración de la instancia y cómo se pueden ver o cambiar estas opciones.</span><span class="sxs-lookup"><span data-stu-id="8be93-114">Describes the various instance configuration options and how to view or change these options.</span></span>|[<span data-ttu-id="8be93-115">Opciones de configuración de servidor &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8be93-115">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)|  
|<span data-ttu-id="8be93-116">Describe cómo ver y configurar las ubicaciones predeterminadas de los archivos de datos y registro nuevos en la instancia.</span><span class="sxs-lookup"><span data-stu-id="8be93-116">Describes how to view and configure the default locations of new data and log files in the instance.</span></span>|[<span data-ttu-id="8be93-117">Ver o cambiar las ubicaciones predeterminadas de los archivos de datos y registro &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="8be93-117">View or Change the Default Locations for Data and Log Files &#40;SQL Server Management Studio&#41;</span></span>](view-or-change-the-default-locations-for-data-and-log-files.md)|  
|<span data-ttu-id="8be93-118">Describe cómo configurar SQL Server para que use soft-NUMA.</span><span class="sxs-lookup"><span data-stu-id="8be93-118">Describes how to configure SQL Server to use soft-NUMA.</span></span>|[<span data-ttu-id="8be93-119">Configure SQL Server para usar &#40;de Soft-NUMA SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8be93-119">Configure SQL Server to Use Soft-NUMA &#40;SQL Server&#41;</span></span>](soft-numa-sql-server.md)|  
|<span data-ttu-id="8be93-120">Describe cómo asignar un puerto TCP/IP a la afinidad del nodo de acceso a memoria no uniforme (NUMA).</span><span class="sxs-lookup"><span data-stu-id="8be93-120">Describes how to map a TCP/IP port to non-uniform memory access (NUMA) node affinity.</span></span>|[<span data-ttu-id="8be93-121">Asignación de puertos TCP/IP a nodos NUMA &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8be93-121">Map TCP IP Ports to NUMA Nodes &#40;SQL Server&#41;</span></span>](map-tcp-ip-ports-to-numa-nodes-sql-server.md)|  
|<span data-ttu-id="8be93-122">Describe cómo habilitar la directiva de Bloquear páginas en memoria de Windows.</span><span class="sxs-lookup"><span data-stu-id="8be93-122">Describes how to enable the Windows Lock Pages In Memory policy.</span></span> <span data-ttu-id="8be93-123">Esta directiva determina qué cuentas pueden usar un proceso que mantiene los datos en memoria física, impidiendo que el sistema lleve los datos a páginas de memoria virtual (disco).</span><span class="sxs-lookup"><span data-stu-id="8be93-123">This policy determines which accounts can use a process to keep data in physical memory, preventing the system from paging the data to virtual memory on disk.</span></span>|[<span data-ttu-id="8be93-124">Habilitar la opción Bloquear páginas en la memoria &#40;Windows&#41;</span><span class="sxs-lookup"><span data-stu-id="8be93-124">Enable the Lock Pages in Memory Option &#40;Windows&#41;</span></span>](enable-the-lock-pages-in-memory-option-windows.md)|  
  
## <a name="see-also"></a><span data-ttu-id="8be93-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8be93-125">See Also</span></span>  
 [<span data-ttu-id="8be93-126">Instancias del motor de base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8be93-126">Database Engine Instances &#40;SQL Server&#41;</span></span>](database-engine-instances-sql-server.md)  
  
  