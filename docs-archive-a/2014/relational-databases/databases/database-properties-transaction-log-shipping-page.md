---
title: Propiedades de la base de datos (página Trasvase de registros) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.databaseproperties.logshipping.f1
ms.assetid: 72c4e539-fe11-4d57-b977-65b418d5916f
author: stevestein
ms.author: sstein
ms.openlocfilehash: dd36b3bc56bcd48c53871c9bc1e334d72c80ac78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751125"
---
# <a name="database-properties-transaction-log-shipping-page"></a><span data-ttu-id="f71d9-102">Propiedades de la base de datos (página Trasvase de registros)</span><span class="sxs-lookup"><span data-stu-id="f71d9-102">Database Properties (Transaction Log Shipping Page)</span></span>
  <span data-ttu-id="f71d9-103">Utilice esta página para configurar y modificar las propiedades de trasvase de registros de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="f71d9-103">Use this page to configure and modify the properties of log shipping for a database.</span></span>  
  
 <span data-ttu-id="f71d9-104">Para obtener una explicación de los conceptos relacionados con el trasvase de registros, vea [Acerca del trasvase de registros &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f71d9-104">For an explanation of log shipping concepts, see [About Log Shipping &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="f71d9-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="f71d9-105">Options</span></span>  
 <span data-ttu-id="f71d9-106">**Habilitar ésta como base de datos principal en una configuración de trasvase de registros**</span><span class="sxs-lookup"><span data-stu-id="f71d9-106">**Enable this as a primary database in a log shipping configuration**</span></span>  
 <span data-ttu-id="f71d9-107">Habilita esta base de datos como base de datos principal de trasvase de registros.</span><span class="sxs-lookup"><span data-stu-id="f71d9-107">Enables this database as a log shipping primary database.</span></span> <span data-ttu-id="f71d9-108">Active esta opción y configure las opciones restantes de esta página.</span><span class="sxs-lookup"><span data-stu-id="f71d9-108">Select it and then configure the remaining options on this page.</span></span> <span data-ttu-id="f71d9-109">Si desactiva esta casilla, la configuración de trasvase de registros se quitará de esta base de datos.</span><span class="sxs-lookup"><span data-stu-id="f71d9-109">If you clear this check box, the log shipping configuration will be dropped for this database.</span></span>  
  
 <span data-ttu-id="f71d9-110">**Configuración de copia de seguridad**</span><span class="sxs-lookup"><span data-stu-id="f71d9-110">**Backup Settings**</span></span>  
 <span data-ttu-id="f71d9-111">Haga clic en **Configuración de copia de seguridad** para configurar parámetros de programación, ubicación, alerta y archivado de la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f71d9-111">Click **Backup Settings** to configure backup schedule, location, alert, and archiving parameters.</span></span>  
  
 <span data-ttu-id="f71d9-112">**Programación de copia de seguridad**</span><span class="sxs-lookup"><span data-stu-id="f71d9-112">**Backup schedule**</span></span>  
 <span data-ttu-id="f71d9-113">Muestra la programación de copia de seguridad seleccionada para la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="f71d9-113">Shows the currently selected backup schedule for the primary database.</span></span> <span data-ttu-id="f71d9-114">Haga clic en **Configuración de copia de seguridad** para modificar estos parámetros.</span><span class="sxs-lookup"><span data-stu-id="f71d9-114">Click **Backup Settings** to modify these settings.</span></span>  
  
 <span data-ttu-id="f71d9-115">**Última copia de seguridad creada**</span><span class="sxs-lookup"><span data-stu-id="f71d9-115">**Last backup created**</span></span>  
 <span data-ttu-id="f71d9-116">Indica la fecha y hora de la última copia de seguridad del registro de transacciones de la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="f71d9-116">Indicates the time and date of the last transaction log backup of the primary database.</span></span>  
  
 <span data-ttu-id="f71d9-117">**Instancias de servidores secundarios y bases de datos**</span><span class="sxs-lookup"><span data-stu-id="f71d9-117">**Secondary server instances and databases**</span></span>  
 <span data-ttu-id="f71d9-118">Presenta una lista con los servidores secundarios y bases de datos configurados para esta base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="f71d9-118">Lists the currently configured secondary servers and databases for this primary database.</span></span> <span data-ttu-id="f71d9-119">Resalte una base de datos y haga clic en **...** para modificar los parámetros asociados a esta base de datos secundaria.</span><span class="sxs-lookup"><span data-stu-id="f71d9-119">Highlight a database, and then click **...** to modify the parameters associated with that secondary database.</span></span>  
  
 <span data-ttu-id="f71d9-120">**Add (Agregar)**</span><span class="sxs-lookup"><span data-stu-id="f71d9-120">**Add**</span></span>  
 <span data-ttu-id="f71d9-121">Haga clic en **Agregar** para agregar una base de datos secundaria a la configuración de trasvase de registros de esta base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="f71d9-121">Click **Add** to add a secondary database to the log shipping configuration for this primary database.</span></span>  
  
 <span data-ttu-id="f71d9-122">**Remove**</span><span class="sxs-lookup"><span data-stu-id="f71d9-122">**Remove**</span></span>  
 <span data-ttu-id="f71d9-123">Quita una base de datos seleccionada de esta configuración de trasvase de registros.</span><span class="sxs-lookup"><span data-stu-id="f71d9-123">Removes a selected database from this log shipping configuration.</span></span> <span data-ttu-id="f71d9-124">Seleccione la base de datos y, a continuación, haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="f71d9-124">Select the database first and then click **Remove**.</span></span>  
  
 <span data-ttu-id="f71d9-125">**Utilizar una instancia del servidor de supervisión**</span><span class="sxs-lookup"><span data-stu-id="f71d9-125">**Use a monitor server instance**</span></span>  
 <span data-ttu-id="f71d9-126">Establece una instancia del servidor de supervisión para esta configuración de trasvase de registros.</span><span class="sxs-lookup"><span data-stu-id="f71d9-126">Sets up a monitor server instance for this log shipping configuration.</span></span> <span data-ttu-id="f71d9-127">Active la casilla **Utilizar una instancia del servidor de supervisión** y, a continuación, haga clic en **Configuración** para especificar la instancia.</span><span class="sxs-lookup"><span data-stu-id="f71d9-127">Select the **Use a monitor server instance** check box and then click **Settings** to specify the monitor server instance.</span></span>  
  
 <span data-ttu-id="f71d9-128">**Instancia del servidor de supervisión**</span><span class="sxs-lookup"><span data-stu-id="f71d9-128">**Monitor server instance**</span></span>  
 <span data-ttu-id="f71d9-129">Indica la instancia del servidor de supervisión actual para esta configuración de trasvase de registros.</span><span class="sxs-lookup"><span data-stu-id="f71d9-129">Indicates the currently configured monitor server instance for this log shipping configuration.</span></span>  
  
 <span data-ttu-id="f71d9-130">**Configuración**</span><span class="sxs-lookup"><span data-stu-id="f71d9-130">**Settings**</span></span>  
 <span data-ttu-id="f71d9-131">Configura la instancia del servidor de supervisión para una configuración de trasvase de registros.</span><span class="sxs-lookup"><span data-stu-id="f71d9-131">Configures the monitor server instance for a log shipping configuration.</span></span> <span data-ttu-id="f71d9-132">Haga clic en **Configuración** para configurar esta instancia.</span><span class="sxs-lookup"><span data-stu-id="f71d9-132">Click **Settings** to configure this monitor server instance.</span></span>  
  
 <span data-ttu-id="f71d9-133">**Incluir configuración**</span><span class="sxs-lookup"><span data-stu-id="f71d9-133">**Script Configuration**</span></span>  
 <span data-ttu-id="f71d9-134">Genera un script para configurar el trasvase de registros con los parámetros seleccionados.</span><span class="sxs-lookup"><span data-stu-id="f71d9-134">Generates a script for configuring log shipping with the parameters you have selected.</span></span> <span data-ttu-id="f71d9-135">Haga clic en **Incluir configuración**y, a continuación, elija un destino de salida para el script.</span><span class="sxs-lookup"><span data-stu-id="f71d9-135">Click **Script Configuration**, and then choose an output destination for the script.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f71d9-136">Antes de crear scripts para la configuración de una base de datos secundaria, debe invocarse el cuadro de diálogo **Configuración de base de datos secundaria** .</span><span class="sxs-lookup"><span data-stu-id="f71d9-136">Before scripting settings for a secondary database, you must invoke the **Secondary Database Settings** dialog box.</span></span> <span data-ttu-id="f71d9-137">Al invocar este cuadro de diálogo, se establece una conexión al servidor secundario y se recupera la configuración actual de la base de datos secundaria, que es necesaria para generar el script.</span><span class="sxs-lookup"><span data-stu-id="f71d9-137">Invoking this dialog box connects you to the secondary server and retrieves the current settings of the secondary database that are needed to generate the script.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f71d9-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f71d9-138">See Also</span></span>  
 <span data-ttu-id="f71d9-139">[Procedimientos almacenados del trasvase de registros &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/log-shipping-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f71d9-139">[Log Shipping Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/log-shipping-stored-procedures-transact-sql) </span></span>  
 [<span data-ttu-id="f71d9-140">Tablas de trasvase de registros &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f71d9-140">Log Shipping Tables &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-tables/log-shipping-tables-transact-sql)  
  
  
