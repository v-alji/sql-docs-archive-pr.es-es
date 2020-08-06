---
title: Mejorar el acceso a los datos de seguimiento | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Profiler [SQL Server Profiler], space
- SQL Server Profiler, space
- space [SQL Server], SQL Server Profiler
ms.assetid: c260c000-fd53-4831-993f-df6894f3228b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 60e01ad04ddd9f7fe6d858c399abb552716f2bea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745105"
---
# <a name="improve-access-to-trace-data"></a><span data-ttu-id="6004b-102">Mejorar el acceso a los datos de seguimiento</span><span class="sxs-lookup"><span data-stu-id="6004b-102">Improve Access to Trace Data</span></span>
  [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="6004b-103">usa el espacio del directorio **temp** para mejorar el acceso a los datos de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="6004b-103">uses space in the **temp** directory to improve access to trace data.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="6004b-104">requiere al menos 10 megabytes (MB) de espacio libre.</span><span class="sxs-lookup"><span data-stu-id="6004b-104">requires at least 10 megabytes (MB) of free space.</span></span> <span data-ttu-id="6004b-105">Si se redujera la cantidad de espacio disponible a menos de 10 MB mientras se utiliza el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], se detendrían todas las funciones del [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6004b-105">If free space drops below 10 MB while you are using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], all [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] functions stop.</span></span>  
  
 <span data-ttu-id="6004b-106">Cuando el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] utiliza espacio del directorio **temp** , este uso de espacio puede dar lugar a que el directorio **temp** crezca rápidamente.</span><span class="sxs-lookup"><span data-stu-id="6004b-106">When [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] uses space in the **temp** directory, this space usage may cause the **temp** directory to grow rapidly.</span></span> <span data-ttu-id="6004b-107">Para evitar problemas del crecimiento de un archivo, puede colocar el directorio **temp** en una unidad que no pertenezca al sistema si cambia el valor de la variable de entorno TEMP.</span><span class="sxs-lookup"><span data-stu-id="6004b-107">To avoid file-growth problems, you can place the **temp** directory on a drive that is not a system drive by changing the value for the TEMP environment variable.</span></span>  
  
 <span data-ttu-id="6004b-108">El procedimiento siguiente describe cómo cambiar el valor de la variable de entorno TEMP en la mayoría de los sistemas operativos Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="6004b-108">The following procedure describes how to change the value for the TEMP environment variable in most Microsoft Windows operating systems.</span></span> <span data-ttu-id="6004b-109">Para obtener más información acerca del establecimiento de variables de entorno, consulte la documentación del sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="6004b-109">For more information about setting environment variables, see your Windows operating system documentation.</span></span>  
  
### <a name="to-change-the-temp-environment-variable-in-windows-operating-systems"></a><span data-ttu-id="6004b-110">Para cambiar la variable de entorno TEMP en sistemas operativos Windows</span><span class="sxs-lookup"><span data-stu-id="6004b-110">To change the TEMP environment variable in Windows operating systems</span></span>  
  
1.  <span data-ttu-id="6004b-111">En el menú **Inicio** , elija **Panel de control**y haga clic en **Sistema**.</span><span class="sxs-lookup"><span data-stu-id="6004b-111">On the **Start** menu, choose **Control Panel**, and then click **System**.</span></span>  
  
2.  <span data-ttu-id="6004b-112">En el cuadro de diálogo **Propiedades del sistema** , haga clic en la pestaña **Opciones avanzadas** y, a continuación, haga clic en **Variables de entorno**.</span><span class="sxs-lookup"><span data-stu-id="6004b-112">In the **System Properties** dialog box, click the **Advanced** tab, and then click **Environment Variables**.</span></span>  
  
3.  <span data-ttu-id="6004b-113">Desplácese hacia abajo por la lista **Variables del sistema**, seleccione la fila que corresponda a la variable **TEMP** y haga clic en **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="6004b-113">Scroll down the list of **System Variables**, select the row that corresponds to the **TEMP** variable, and click **Edit**.</span></span>  
  
4.  <span data-ttu-id="6004b-114">En el cuadro de diálogo **Modificar la variable del sistema** , especifique la ruta de acceso y el nombre de la unidad y el directorio en los que desea colocar el directorio **temp** .</span><span class="sxs-lookup"><span data-stu-id="6004b-114">In the **Edit System Variable** dialog box, enter the path and name of the drive and directory where you want the **temp** directory to be located.</span></span>  
  
5.  <span data-ttu-id="6004b-115">Haga clic en **Aceptar** para guardar el cambio.</span><span class="sxs-lookup"><span data-stu-id="6004b-115">Click **OK** to save the change.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6004b-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6004b-116">See Also</span></span>  
 <span data-ttu-id="6004b-117">[Iniciar SQL Server Profiler](../../tools/sql-server-profiler/start-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="6004b-117">[Start SQL Server Profiler](../../tools/sql-server-profiler/start-sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="6004b-118">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="6004b-118">SQL Server Profiler</span></span>](../../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
