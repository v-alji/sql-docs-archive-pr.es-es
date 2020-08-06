---
title: Reproducir un script Transact-SQL (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], replaying
- scripts [SQL Server], traces
- replaying traces
ms.assetid: 9c0eb222-e6e3-4bc1-a25f-a41e962d361b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5abf22a1201ac927f12ef9e4cfdd1f6d3026d00a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748412"
---
# <a name="replay-a-transact-sql-script-sql-server-profiler"></a><span data-ttu-id="0d4a6-102">Reproducir un script Transact-SQL (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="0d4a6-102">Replay a Transact-SQL Script (SQL Server Profiler)</span></span>
  <span data-ttu-id="0d4a6-103">Cuando pruebe posibles soluciones para un problema de rendimiento, utilice el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] para reproducir scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] y compare el rendimiento antes y después de los cambios.</span><span class="sxs-lookup"><span data-stu-id="0d4a6-103">When you test possible solutions to a performance problem, use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to replay [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts, and compare performance before and after your changes.</span></span>  
  
### <a name="to-replay-a-transact-sql-script"></a><span data-ttu-id="0d4a6-104">Para reproducir un script Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0d4a6-104">To replay a Transact-SQL script</span></span>  
  
1.  <span data-ttu-id="0d4a6-105">En el menú **Archivo** , seleccione **Abrir**y haga clic en **Archivo de script**.</span><span class="sxs-lookup"><span data-stu-id="0d4a6-105">On the **File** menu, point to **Open**, and then click **Script File**.</span></span>  
  
2.  <span data-ttu-id="0d4a6-106">Seleccione el archivo de script [!INCLUDE[tsql](../../includes/tsql-md.md)] que desee abrir.</span><span class="sxs-lookup"><span data-stu-id="0d4a6-106">Select the [!INCLUDE[tsql](../../includes/tsql-md.md)] script file you want to open.</span></span> <span data-ttu-id="0d4a6-107">Asegúrese de que el script [!INCLUDE[tsql](../../includes/tsql-md.md)] contiene los eventos necesarios para la reproducción.</span><span class="sxs-lookup"><span data-stu-id="0d4a6-107">Make sure that the [!INCLUDE[tsql](../../includes/tsql-md.md)] script contains events necessary for replay.</span></span> <span data-ttu-id="0d4a6-108">Para más información, consulte [Replay Requirements](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d4a6-108">For more information, see [Replay Requirements](replay-requirements.md).</span></span>  
  
3.  <span data-ttu-id="0d4a6-109">En el menú **Reproducir** , haga clic en **Iniciar**y conéctese al servidor en el que desee reproducir el script.</span><span class="sxs-lookup"><span data-stu-id="0d4a6-109">On the **Replay** menu, click **Start**, and connect to the server where you want to replay the script.</span></span>  
  
4.  <span data-ttu-id="0d4a6-110">Compruebe la configuración en el cuadro de diálogo **Configuración de reproducción** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0d4a6-110">In the **Replay Configuration** dialog box, verify the settings, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d4a6-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0d4a6-111">See Also</span></span>  
 <span data-ttu-id="0d4a6-112">[Reproducir seguimientos](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="0d4a6-112">[Replay Traces](replay-traces.md) </span></span>  
 [<span data-ttu-id="0d4a6-113">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="0d4a6-113">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
