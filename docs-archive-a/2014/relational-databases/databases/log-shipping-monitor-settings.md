---
title: Configuración del monitor de trasvase de registros | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.databaseproperties.logshipping.settings.monitor.f1
ms.assetid: 45e2ba7d-b3aa-4643-9451-bcb991572314
author: stevestein
ms.author: sstein
ms.openlocfilehash: 162fdc1b8b0ef850a7e58d1380c533426e16539c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751082"
---
# <a name="log-shipping-monitor-settings"></a><span data-ttu-id="5a505-102">Configuración del monitor de trasvase de registros</span><span class="sxs-lookup"><span data-stu-id="5a505-102">Log Shipping Monitor Settings</span></span>
  <span data-ttu-id="5a505-103">Utilice esta página para configurar y modificar las propiedades del servidor del monitor de trasvase de registros.</span><span class="sxs-lookup"><span data-stu-id="5a505-103">Use this page to configure and to modify the properties of the log shipping monitor server.</span></span>  
  
 <span data-ttu-id="5a505-104">Para obtener una explicación de los conceptos relacionados con el trasvase de registros, vea [Acerca del trasvase de registros &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5a505-104">For an explanation of log shipping concepts, see [About Log Shipping &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="5a505-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="5a505-105">Options</span></span>  
 <span data-ttu-id="5a505-106">**Instancia del servidor de supervisión**</span><span class="sxs-lookup"><span data-stu-id="5a505-106">**Monitor server instance**</span></span>  
 <span data-ttu-id="5a505-107">Muestra el nombre de la instancia del servidor configurado actualmente como el servidor de supervisión para la configuración del trasvase de registros.</span><span class="sxs-lookup"><span data-stu-id="5a505-107">Displays the name of the server instance that is currently configured as the monitor server for the log shipping configuration.</span></span>  
  
 <span data-ttu-id="5a505-108">**Conexión**</span><span class="sxs-lookup"><span data-stu-id="5a505-108">**Connect**</span></span>  
 <span data-ttu-id="5a505-109">Elija y conéctese a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que se va a utilizar como servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="5a505-109">Choose and connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to be used as the monitor server.</span></span> <span data-ttu-id="5a505-110">La cuenta utilizada para la conexión debe ser miembro del rol fijo de servidor sysadmin en la instancia de servidor secundario.</span><span class="sxs-lookup"><span data-stu-id="5a505-110">The account used to connect must be a member of the sysadmin fixed server role on the secondary server instance.</span></span>  
  
 <span data-ttu-id="5a505-111">**Mediante la suplantación de la cuenta de proxy del trabajo**</span><span class="sxs-lookup"><span data-stu-id="5a505-111">**By impersonating the proxy account of the job**</span></span>  
 <span data-ttu-id="5a505-112">El trasvase de registros suplanta la cuenta de proxy del Agente SQL Server cuando se conecta a la instancia del servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="5a505-112">Have log shipping impersonate the SQL Server Agent proxy account when connecting to the monitor server instance.</span></span> <span data-ttu-id="5a505-113">Los procesos de copia de seguridad, copia y restauración deben poder conectarse al servidor de supervisión para actualizar el estado de las operaciones de trasvase de registros.</span><span class="sxs-lookup"><span data-stu-id="5a505-113">The backup, copy, and restore processes must be able to connect to the monitor server to update the status of log shipping operations.</span></span>  
  
 <span data-ttu-id="5a505-114">**Mediante el siguiente inicio de sesión de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="5a505-114">**Using the following SQL Server login**</span></span>  
 <span data-ttu-id="5a505-115">Permite que el trasvase de registros utilice un inicio de sesión específico de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cuando se conecta a la instancia del servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="5a505-115">Allow log shipping to use a specific [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login when connecting to the monitor server instance.</span></span> <span data-ttu-id="5a505-116">Los procesos de copia de seguridad, copia y restauración deben poder conectarse al servidor de supervisión para actualizar el estado de las operaciones de trasvase de registros.</span><span class="sxs-lookup"><span data-stu-id="5a505-116">The backup, copy, and restore processes must be able to connect to the monitor server to update the status of log shipping operations.</span></span> <span data-ttu-id="5a505-117">Elija esta opción si desea que el trasvase de registros utilice un inicio de sesión específico de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y luego especifique el inicio de sesión y la contraseña.</span><span class="sxs-lookup"><span data-stu-id="5a505-117">Choose this option if you want log shipping to use a specific [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and then specify the login and password.</span></span>  
  
 <span data-ttu-id="5a505-118">**Eliminar historial después de**</span><span class="sxs-lookup"><span data-stu-id="5a505-118">**Delete history after**</span></span>  
 <span data-ttu-id="5a505-119">Especifica el intervalo de tiempo que desea mantener la información del historial de trasvase de registros en el servidor de supervisión antes de eliminarla.</span><span class="sxs-lookup"><span data-stu-id="5a505-119">Specify the amount of time to retain log shipping history information on the monitor server before it is deleted.</span></span>  
  
 <span data-ttu-id="5a505-120">**Nombre del trabajo**</span><span class="sxs-lookup"><span data-stu-id="5a505-120">**Job name**</span></span>  
 <span data-ttu-id="5a505-121">Indica el nombre del trabajo de alerta del Agente SQL Server que ha utilizado el trasvase de registros para generar alertas cuando se han superado los límites de copia de seguridad y restauración.</span><span class="sxs-lookup"><span data-stu-id="5a505-121">Indicates the name of the SQL Server Agent alert job used by log shipping to raise alerts when backup or restore thresholds have been exceeded.</span></span> <span data-ttu-id="5a505-122">Cuando se crea este trabajo por primera vez, se puede cambiar el nombre escribiéndolo en el cuadro.</span><span class="sxs-lookup"><span data-stu-id="5a505-122">When first creating this job, you can change the name by typing in the box.</span></span>  
  
 <span data-ttu-id="5a505-123">**Programación**</span><span class="sxs-lookup"><span data-stu-id="5a505-123">**Schedule**</span></span>  
 <span data-ttu-id="5a505-124">Indica la programación actual del trabajo de alerta del Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5a505-124">Indicates the current schedule of the SQL Server Agent alert job.</span></span>  
  
 <span data-ttu-id="5a505-125">**Edición**</span><span class="sxs-lookup"><span data-stu-id="5a505-125">**Edit**</span></span>  
 <span data-ttu-id="5a505-126">Modifique los parámetros del trabajo de alerta del Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5a505-126">Modify the SQL Server Agent alert job parameters.</span></span>  
  
 <span data-ttu-id="5a505-127">**Deshabilitar este trabajo**</span><span class="sxs-lookup"><span data-stu-id="5a505-127">**Disable this job**</span></span>  
 <span data-ttu-id="5a505-128">Suspende el trabajo de alerta del Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5a505-128">Suspend the SQL Server Agent alert job.</span></span>  
  
  
