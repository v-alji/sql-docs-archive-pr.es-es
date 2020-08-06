---
title: Establecer opciones globales de seguimiento (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- global trace options [SQL Server]
ms.assetid: 2854608a-c3c7-4eb8-b567-034bfec4b1a9
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2f0809ae11776e1bddf42c189b86f48689ff4859
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663245"
---
# <a name="set-global-trace-options-sql-server-profiler"></a><span data-ttu-id="7b6b4-102">Establecer opciones globales de seguimiento (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="7b6b4-102">Set Global Trace Options (SQL Server Profiler)</span></span>
  <span data-ttu-id="7b6b4-103">En este tema se describe cómo establecer las opciones que se aplican a todos los seguimientos creados con una instancia determinada del [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b6b4-103">This topic describes how to set options that apply to all traces that are created with a specific instance of [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-set-global-trace-options"></a><span data-ttu-id="7b6b4-104">Para establecer opciones globales de seguimiento</span><span class="sxs-lookup"><span data-stu-id="7b6b4-104">To set global trace options</span></span>  
  
1.  <span data-ttu-id="7b6b4-105">En el menú **Herramientas** , haga clic en **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="7b6b4-105">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="7b6b4-106">En el cuadro de diálogo **Opciones generales**haga clic en **Elegir fuente**para modificar las opciones de visualización y luego haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7b6b4-106">In the **General Options**dialog box, click **Choose Font**to modify the display options, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="7b6b4-107">Opcionalmente puede seleccionar **Iniciar la traza inmediatamente tras realizar la conexión**.</span><span class="sxs-lookup"><span data-stu-id="7b6b4-107">Optionally, select **Start tracing immediately after making connection**.</span></span>  
  
4.  <span data-ttu-id="7b6b4-108">Opcionalmente también puede seleccionar **Actualizar definición de seguimiento cuando cambie la versión del proveedor**.</span><span class="sxs-lookup"><span data-stu-id="7b6b4-108">Optionally, select **Update trace definition when provider version changes**.</span></span> <span data-ttu-id="7b6b4-109">Ésta es la opción recomendada y está seleccionada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7b6b4-109">This option is recommended and is selected by default.</span></span> <span data-ttu-id="7b6b4-110">Cuando se selecciona esta opción, la definición del seguimiento se actualiza automáticamente a la versión actual del servidor donde se realiza la traza.</span><span class="sxs-lookup"><span data-stu-id="7b6b4-110">When this option is selected, the trace definition is automatically updated to the current version of the server where tracing is performed.</span></span>  
  
5.  <span data-ttu-id="7b6b4-111">Opcionalmente, puede especificar cómo administra el servidor los archivos de sustitución incremental:</span><span class="sxs-lookup"><span data-stu-id="7b6b4-111">Optionally, specify how the server should manage rollover files:</span></span>  
  
    -   <span data-ttu-id="7b6b4-112">Seleccione **Cargar todos los archivos de sustitución incremental en secuencia sin preguntar** para cargar automáticamente los archivos de sustitución incremental durante la reproducción.</span><span class="sxs-lookup"><span data-stu-id="7b6b4-112">Select **Load all rollover files in sequence without prompting** to automatically load rollover files during replay.</span></span>  
  
    -   <span data-ttu-id="7b6b4-113">Seleccione **Preguntar antes de cargar archivos de sustitución incremental** para controlar los archivos de sustitución incremental durante la reproducción.</span><span class="sxs-lookup"><span data-stu-id="7b6b4-113">Select **Prompt before loading rollover files** to control rollover files during replay.</span></span>  
  
    -   <span data-ttu-id="7b6b4-114">Seleccione **No cargar nunca los archivos siguientes de sustitución incremental** para reproducir solamente un archivo cada vez.</span><span class="sxs-lookup"><span data-stu-id="7b6b4-114">Select **Never load subsequent rollover files** to replay only one file at a time.</span></span>  
  
6.  <span data-ttu-id="7b6b4-115">Opcionalmente, puede establecer las opciones de reproducción:</span><span class="sxs-lookup"><span data-stu-id="7b6b4-115">Optionally, set replay options:</span></span>  
  
    -   <span data-ttu-id="7b6b4-116">**Número predeterminado de subprocesos de reproducción** controla el número de subprocesos de procesador que se van a utilizar durante la reproducción.</span><span class="sxs-lookup"><span data-stu-id="7b6b4-116">**Default number of replay threads** controls the number of processor threads to use during replay.</span></span> <span data-ttu-id="7b6b4-117">Un número elevado de subprocesos permite completar la reproducción con más rapidez, pero degrada el rendimiento del servidor durante la reproducción.</span><span class="sxs-lookup"><span data-stu-id="7b6b4-117">A higher number of threads causes replay to complete faster, but causes server performance to degrade during replay.</span></span> <span data-ttu-id="7b6b4-118">El valor recomendado es **4**.</span><span class="sxs-lookup"><span data-stu-id="7b6b4-118">The recommended setting is **4**.</span></span> <span data-ttu-id="7b6b4-119">En la siguiente tabla se enumeran las opciones disponibles:</span><span class="sxs-lookup"><span data-stu-id="7b6b4-119">The following table lists the available options:</span></span>  
  
        |<span data-ttu-id="7b6b4-120">Value</span><span class="sxs-lookup"><span data-stu-id="7b6b4-120">Value</span></span>|<span data-ttu-id="7b6b4-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="7b6b4-121">Description</span></span>|  
        |-----------|-----------------|  
        |<span data-ttu-id="7b6b4-122">**2**</span><span class="sxs-lookup"><span data-stu-id="7b6b4-122">**2**</span></span>|<span data-ttu-id="7b6b4-123">Valor mínimo.</span><span class="sxs-lookup"><span data-stu-id="7b6b4-123">Minimum value.</span></span> <span data-ttu-id="7b6b4-124">Utilice dos subprocesos para la reproducción.</span><span class="sxs-lookup"><span data-stu-id="7b6b4-124">Use two threads to replay.</span></span>|  
        |<span data-ttu-id="7b6b4-125">**4**</span><span class="sxs-lookup"><span data-stu-id="7b6b4-125">**4**</span></span>|<span data-ttu-id="7b6b4-126">Valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="7b6b4-126">Default value.</span></span>|  
        |<span data-ttu-id="7b6b4-127">**255**</span><span class="sxs-lookup"><span data-stu-id="7b6b4-127">**255**</span></span>|<span data-ttu-id="7b6b4-128">Valor máximo.</span><span class="sxs-lookup"><span data-stu-id="7b6b4-128">Maximum value.</span></span> <span data-ttu-id="7b6b4-129">El uso de un valor máximo bloqueará el rendimiento de otros procesos.</span><span class="sxs-lookup"><span data-stu-id="7b6b4-129">Setting a maximum value will impede performance for other processes.</span></span>|  
  
    -   <span data-ttu-id="7b6b4-130">**Intervalo de espera del monitor de mantenimiento predeterminado (s)** establece el tiempo máximo (en segundos) durante el cual un subproceso de reproducción puede bloquear otro proceso.</span><span class="sxs-lookup"><span data-stu-id="7b6b4-130">**Default health monitor wait interval (sec)** sets the maximum amount of time that a replay thread can block another process in seconds.</span></span> <span data-ttu-id="7b6b4-131">En la siguiente tabla se describen los valores.</span><span class="sxs-lookup"><span data-stu-id="7b6b4-131">The following table explains the values.</span></span>  
  
        |<span data-ttu-id="7b6b4-132">Value</span><span class="sxs-lookup"><span data-stu-id="7b6b4-132">Value</span></span>|<span data-ttu-id="7b6b4-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="7b6b4-133">Description</span></span>|  
        |-----------|-----------------|  
        |<span data-ttu-id="7b6b4-134">**0**</span><span class="sxs-lookup"><span data-stu-id="7b6b4-134">**0**</span></span>|<span data-ttu-id="7b6b4-135">Valor mínimo.</span><span class="sxs-lookup"><span data-stu-id="7b6b4-135">Minimum value.</span></span> <span data-ttu-id="7b6b4-136">El valor **0** indica que el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] nunca detendrá un proceso de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="7b6b4-136">A setting of **0** means that [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] will never stop a blocking process.</span></span>|  
        |<span data-ttu-id="7b6b4-137">**3600**</span><span class="sxs-lookup"><span data-stu-id="7b6b4-137">**3600**</span></span>|<span data-ttu-id="7b6b4-138">Valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="7b6b4-138">Default value.</span></span> <span data-ttu-id="7b6b4-139">Permite los procesos de bloqueo inferiores a **3.600** segundos, o una hora.</span><span class="sxs-lookup"><span data-stu-id="7b6b4-139">Allow blocking processes that do not exceed **3600** seconds, or one hour.</span></span>|  
        |<span data-ttu-id="7b6b4-140">**86400**</span><span class="sxs-lookup"><span data-stu-id="7b6b4-140">**86400**</span></span>|<span data-ttu-id="7b6b4-141">Valor máximo.</span><span class="sxs-lookup"><span data-stu-id="7b6b4-141">Maximum value.</span></span> <span data-ttu-id="7b6b4-142">Permite los procesos de bloqueo inferiores a **86.400** segundos, o un día.</span><span class="sxs-lookup"><span data-stu-id="7b6b4-142">Allow blocking processes that do not exceed **86400** seconds, or one day.</span></span>|  
  
    -   <span data-ttu-id="7b6b4-143">**Intervalo de sondeo del monitor de mantenimiento predeterminado (s)** establece la frecuencia de sondeo de subprocesos de reproducción para bloquear procesos.</span><span class="sxs-lookup"><span data-stu-id="7b6b4-143">**Default health monitor poll interval (sec)** sets the frequency to poll replay threads for blocking processes.</span></span> <span data-ttu-id="7b6b4-144">En la siguiente tabla se describen los valores.</span><span class="sxs-lookup"><span data-stu-id="7b6b4-144">The following table explains the values.</span></span>  
  
        |<span data-ttu-id="7b6b4-145">Value</span><span class="sxs-lookup"><span data-stu-id="7b6b4-145">Value</span></span>|<span data-ttu-id="7b6b4-146">Descripción</span><span class="sxs-lookup"><span data-stu-id="7b6b4-146">Description</span></span>|  
        |-----------|-----------------|  
        |<span data-ttu-id="7b6b4-147">**1**</span><span class="sxs-lookup"><span data-stu-id="7b6b4-147">**1**</span></span>|<span data-ttu-id="7b6b4-148">Valor mínimo.</span><span class="sxs-lookup"><span data-stu-id="7b6b4-148">Minimum value.</span></span> <span data-ttu-id="7b6b4-149">El valor **1** indica que el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] sondeará los procesos de bloqueo una vez por segundo.</span><span class="sxs-lookup"><span data-stu-id="7b6b4-149">A setting of **1** means [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] will poll for blocking processes once per second.</span></span>|  
        |<span data-ttu-id="7b6b4-150">**60**</span><span class="sxs-lookup"><span data-stu-id="7b6b4-150">**60**</span></span>|<span data-ttu-id="7b6b4-151">Valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="7b6b4-151">Default value.</span></span> <span data-ttu-id="7b6b4-152">Sondea los procesos de bloqueo una vez por minuto.</span><span class="sxs-lookup"><span data-stu-id="7b6b4-152">Poll for blocking processes once per minute.</span></span>|  
        |<span data-ttu-id="7b6b4-153">**86400**</span><span class="sxs-lookup"><span data-stu-id="7b6b4-153">**86400**</span></span>|<span data-ttu-id="7b6b4-154">Valor máximo.</span><span class="sxs-lookup"><span data-stu-id="7b6b4-154">Maximum value.</span></span> <span data-ttu-id="7b6b4-155">Sondea los procesos de bloqueo una vez cada **86.400** segundos, o día.</span><span class="sxs-lookup"><span data-stu-id="7b6b4-155">Poll for blocking processes once per **86400** seconds, or one day.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7b6b4-156">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7b6b4-156">See Also</span></span>  
 <span data-ttu-id="7b6b4-157">[Establecer los valores predeterminados de presentación de seguimiento &#40;SQL Server Profiler&#41;](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="7b6b4-157">[Set Trace Display Defaults &#40;SQL Server Profiler&#41;](sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="7b6b4-158">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="7b6b4-158">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
