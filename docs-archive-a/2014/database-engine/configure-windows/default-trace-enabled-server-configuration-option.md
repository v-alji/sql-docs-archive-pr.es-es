---
title: default trace enabled (opción de configuración del servidor) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], traces
- traces [SQL Server], logs
- default trace enabled option
ms.assetid: 1322d668-44f4-469e-8fd6-e0d02a81c8f2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8d40305de7375f2ae10d563871fd40b7acfa463f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749470"
---
# <a name="default-trace-enabled-server-configuration-option"></a><span data-ttu-id="fb6b8-102">default trace enabled (opción de configuración del servidor)</span><span class="sxs-lookup"><span data-stu-id="fb6b8-102">default trace enabled Server Configuration Option</span></span>
  <span data-ttu-id="fb6b8-103">Utilice la opción **default trace enabled** para habilitar o deshabilitar los archivos predeterminados de registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="fb6b8-103">Use the **default trace enabled** option to enable or disable the default trace log files.</span></span> <span data-ttu-id="fb6b8-104">La funcionalidad de registro de seguimiento predeterminado ofrece un registro completo y persistente de la actividad y los cambios principalmente relacionados con las opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="fb6b8-104">The default trace functionality provides a rich, persistent log of activity and changes primarily related to the configuration options.</span></span>  
  
> [!WARNING]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] <span data-ttu-id="fb6b8-105">Use eventos extendidos en su lugar.</span><span class="sxs-lookup"><span data-stu-id="fb6b8-105">Use Extended Events instead.</span></span>  
  
## <a name="purpose"></a><span data-ttu-id="fb6b8-106">Propósito</span><span class="sxs-lookup"><span data-stu-id="fb6b8-106">Purpose</span></span>  
 <span data-ttu-id="fb6b8-107">Los seguimientos predeterminados ofrecen ayuda para la solución de problemas a los administradores de bases de datos al garantizar que disponen de los datos de registro necesarios para diagnosticar los problemas la primera vez que ocurren.</span><span class="sxs-lookup"><span data-stu-id="fb6b8-107">Default trace provides troubleshooting assistance to database administrators by ensuring that they have the log data necessary to diagnose problems the first time they occur.</span></span>  
  
## <a name="viewing"></a><span data-ttu-id="fb6b8-108">Ver</span><span class="sxs-lookup"><span data-stu-id="fb6b8-108">Viewing</span></span>  
 <span data-ttu-id="fb6b8-109">Los registros de seguimiento predeterminados se pueden abrir y examinar mediante [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] o se pueden consultar a través de [!INCLUDE[tsql](../../includes/tsql-md.md)] utilizando la función de sistema `fn_trace_gettable` .</span><span class="sxs-lookup"><span data-stu-id="fb6b8-109">The default trace logs can be opened and examined by [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] or queried with [!INCLUDE[tsql](../../includes/tsql-md.md)] by using the `fn_trace_gettable` system function.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="fb6b8-110">puede abrir los archivos de registro de seguimiento predeterminados igual que si fueran archivos de salida de seguimiento normales.</span><span class="sxs-lookup"><span data-stu-id="fb6b8-110">can open the default trace log files just as it does normal trace output files.</span></span> <span data-ttu-id="fb6b8-111">Los registros de seguimiento predeterminados se almacenan de forma predeterminada en el directorio `\MSSQL\LOG` mediante un archivo de seguimiento de sustitución.</span><span class="sxs-lookup"><span data-stu-id="fb6b8-111">The default trace log is stored by default in the `\MSSQL\LOG` directory using a rollover trace file.</span></span> <span data-ttu-id="fb6b8-112">El nombre base del archivo predeterminado de registro de seguimiento es `log.trc`.</span><span class="sxs-lookup"><span data-stu-id="fb6b8-112">The base file name for the default trace log file is `log.trc`.</span></span> <span data-ttu-id="fb6b8-113">En una instalación estándar de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], el seguimiento predeterminado está habilitado y se transforma por tanto en TraceID 1.</span><span class="sxs-lookup"><span data-stu-id="fb6b8-113">In a typical installation of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the default trace is enabled and thus becomes TraceID 1.</span></span> <span data-ttu-id="fb6b8-114">Si se habilita después de la instalación y después de crear otros seguimientos, el TraceID puede adoptar un número mayor.</span><span class="sxs-lookup"><span data-stu-id="fb6b8-114">If enabled after installation and after creating other traces, the TraceID can become a larger number.</span></span>  
  
 <span data-ttu-id="fb6b8-115">Para obtener más información sobre el uso de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Profiler para ver este archivo de seguimiento, vea [Abrir un archivo de seguimiento &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/open-a-trace-file-sql-server-profiler.md)</span><span class="sxs-lookup"><span data-stu-id="fb6b8-115">For more information about using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Profiler to view this trace file, see [Open a Trace File &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/open-a-trace-file-sql-server-profiler.md)</span></span>  
  
### <a name="example"></a><span data-ttu-id="fb6b8-116">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fb6b8-116">Example:</span></span>  
 <span data-ttu-id="fb6b8-117">La instrucción siguiente abre el registro de seguimiento predeterminado en la ubicación predeterminada:</span><span class="sxs-lookup"><span data-stu-id="fb6b8-117">The following statement opens the default trace log in the default location:</span></span>  
  
```  
SELECT *   
FROM fn_trace_gettable  
('C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\LOG\log.trc', default);  
GO  
  
```  
  
## <a name="configuring"></a><span data-ttu-id="fb6b8-118">Configuración</span><span class="sxs-lookup"><span data-stu-id="fb6b8-118">Configuring</span></span>  
 <span data-ttu-id="fb6b8-119">Si se selecciona el valor 1 para la opción **default trace enabled** , se habilita **Default Trace**.</span><span class="sxs-lookup"><span data-stu-id="fb6b8-119">When set to 1, the **default trace enabled** option enables **Default Trace**.</span></span> <span data-ttu-id="fb6b8-120">El valor predeterminado de esta opción es 1 (ON).</span><span class="sxs-lookup"><span data-stu-id="fb6b8-120">The default setting for this option is 1 (ON).</span></span> <span data-ttu-id="fb6b8-121">El valor 0 desactiva el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="fb6b8-121">A value of 0 turns off the trace.</span></span>  
  
 <span data-ttu-id="fb6b8-122">**default trace enabled** es una opción avanzada.</span><span class="sxs-lookup"><span data-stu-id="fb6b8-122">The **default trace enabled** option is an advanced option.</span></span> <span data-ttu-id="fb6b8-123">Si está usando el procedimiento almacenado del sistema **sp_configure** para cambiar la configuración, solo podrá cambiar la opción **Seguimiento predeterminado habilitado** cuando **Mostrar opciones avanzadas** esté configurado en 1.</span><span class="sxs-lookup"><span data-stu-id="fb6b8-123">If you are using the **sp_configure** system stored procedure to change the setting, you can change the **default trace enabled** option only when **show advanced options** is set to 1.</span></span> <span data-ttu-id="fb6b8-124">La configuración surte efecto inmediatamente, sin necesidad de reiniciar un servidor.</span><span class="sxs-lookup"><span data-stu-id="fb6b8-124">The setting takes effect immediately without a server restart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb6b8-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fb6b8-125">See Also</span></span>  
 <span data-ttu-id="fb6b8-126">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fb6b8-126">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="fb6b8-127">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fb6b8-127">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="fb6b8-128">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fb6b8-128">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
