---
title: Abrir, ver e imprimir un archivo de interbloqueo (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- deadlocks [SQL Server], printing files
- deadlocks [SQL Server], opening files
- opening deadlock files
- printing deadlock files
ms.assetid: 5061b13f-2cb7-457a-b8d0-fbd437b510ab
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 08bacd7a99e45e10163216c69057b167088441ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674779"
---
# <a name="open-view-and-print-a-deadlock-file-sql-server-management-studio"></a><span data-ttu-id="1b610-102">Abrir, ver e imprimir un archivo de interbloqueo (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="1b610-102">Open, View, and Print a Deadlock File (SQL Server Management Studio)</span></span>
  <span data-ttu-id="1b610-103">Cuando [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] genera un interbloqueo, puede capturar y guardar la información de interbloqueo en un archivo.</span><span class="sxs-lookup"><span data-stu-id="1b610-103">When [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] generates a deadlock, you can capture and save the deadlock information to a file.</span></span> <span data-ttu-id="1b610-104">Después de guardar el archivo de interbloqueo, puede abrirlo en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para verlo o imprimirlo.</span><span class="sxs-lookup"><span data-stu-id="1b610-104">After you have saved the deadlock file, you can open it in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to view or print.</span></span>  
  
### <a name="to-open-and-view-a-deadlock-file"></a><span data-ttu-id="1b610-105">Para abrir y ver un archivo de interbloqueo</span><span class="sxs-lookup"><span data-stu-id="1b610-105">To open and view a deadlock file</span></span>  
  
1.  <span data-ttu-id="1b610-106">En el menú **archivo** de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , seleccione **abrir**y, a continuación, haga clic en **archivo**.</span><span class="sxs-lookup"><span data-stu-id="1b610-106">On the **File** menu in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], point to **Open**, and then click **File**.</span></span>  
  
2.  <span data-ttu-id="1b610-107">En el cuadro de diálogo **Abrir archivo** , en **Archivos de tipo** , seleccione el tipo de archivo .xdl.</span><span class="sxs-lookup"><span data-stu-id="1b610-107">In the **Open File** dialog box, select the .xdl file type in the **Files of type** box.</span></span> <span data-ttu-id="1b610-108">Se mostrará una lista filtrada en la que solo aparecerán archivos de interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="1b610-108">You will now have a filtered list of only deadlock files.</span></span>  
  
### <a name="to-print-a-deadlock-file"></a><span data-ttu-id="1b610-109">Para imprimir un archivo de interbloqueo</span><span class="sxs-lookup"><span data-stu-id="1b610-109">To print a deadlock file</span></span>  
  
1.  <span data-ttu-id="1b610-110">En **, en el menú** Archivo [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], seleccione **Abrir** y haga clic en **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="1b610-110">On the **File** menu in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], point to **Open,** and then click **File**.</span></span>  
  
2.  <span data-ttu-id="1b610-111">En el cuadro de diálogo **Abrir archivo** , en **Archivos de tipo** , seleccione el tipo de archivo .xdl.</span><span class="sxs-lookup"><span data-stu-id="1b610-111">In the **Open File** dialog box, select the .xdl file type in the **Files of type** box.</span></span> <span data-ttu-id="1b610-112">Se mostrará una lista filtrada en la que solo aparecerán archivos de interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="1b610-112">You will now have a filtered list of only deadlock files.</span></span>  
  
3.  <span data-ttu-id="1b610-113">Seleccione el archivo de interbloqueo que desee imprimir y haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="1b610-113">Select the deadlock file you want to print, and click **Open**.</span></span>  
  
4.  <span data-ttu-id="1b610-114">En el menú **Archivo** , haga clic en **Imprimir**.</span><span class="sxs-lookup"><span data-stu-id="1b610-114">On the **File** menu, click **Print.**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b610-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1b610-115">See Also</span></span>  
 [<span data-ttu-id="1b610-116">Guardar gráficos de interbloqueo &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="1b610-116">Save Deadlock Graphs &#40;SQL Server Profiler&#41;</span></span>](save-deadlock-graphs-sql-server-profiler.md)  
  
  
