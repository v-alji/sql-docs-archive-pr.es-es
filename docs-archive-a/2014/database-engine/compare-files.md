---
title: Comparar archivos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- versions [SQL Server], file comparisons
- comparing files
- file comparisons [SQL Server]
ms.assetid: 728811c4-5d7a-4420-abce-f56c5a0994d2
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: f29bf7098f0c73d0b672e20b973b1347349b31f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674352"
---
# <a name="compare-files"></a><span data-ttu-id="ca358-102">Comparar archivos</span><span class="sxs-lookup"><span data-stu-id="ca358-102">Compare Files</span></span>
  <span data-ttu-id="ca358-103">Puede comparar archivos para determinar cómo ha progresado un archivo hasta su estado actual.</span><span class="sxs-lookup"><span data-stu-id="ca358-103">You can compare files to determine how a file has progressed to its present state.</span></span> <span data-ttu-id="ca358-104">Por ejemplo, si se detecta un defecto en una versión del proyecto de código tras haberse protegido una versión concreta del archivo de origen, podrá comparar la versión actual con la anterior. </span><span class="sxs-lookup"><span data-stu-id="ca358-104">For example, if you detect a defect in a build of your code project after a particular source file version is checked in, you can compare the current file version to a previous one.</span></span> <span data-ttu-id="ca358-105">Esto ayuda a identificar el código que ha ocasionado el defecto.</span><span class="sxs-lookup"><span data-stu-id="ca358-105">This helps you to pinpoint the code that introduced the defect.</span></span>  
  
 <span data-ttu-id="ca358-106">Puede utilizar [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para comparar una copia local de un proyecto o un archivo con la versión almacenada en el control de código fuente o para comparar dos archivos locales.</span><span class="sxs-lookup"><span data-stu-id="ca358-106">You can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to compare a local copy of a project or file to the version stored in source control, or to compare two local files.</span></span> <span data-ttu-id="ca358-107">Además, con el comando **History** , puede comparar dos versiones con control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="ca358-107">Also, using the **History** command, you can compare any two source-controlled versions.</span></span>  
  
### <a name="to-compare-files"></a><span data-ttu-id="ca358-108">Para comparar archivos</span><span class="sxs-lookup"><span data-stu-id="ca358-108">To compare files</span></span>  
  
1.  <span data-ttu-id="ca358-109">En el Explorador de soluciones, seleccione un proyecto o uno de los archivos del mismo.</span><span class="sxs-lookup"><span data-stu-id="ca358-109">In Solution Explorer, select either a project or one of the project files.</span></span>  
  
2.  <span data-ttu-id="ca358-110">En el menú **archivo** , seleccione **control de código fuente**y haga clic en **comparar**.</span><span class="sxs-lookup"><span data-stu-id="ca358-110">On the **File** menu, point to **Source Control**, and click **Compare**.</span></span>  
  
3.  <span data-ttu-id="ca358-111">En el cuadro de diálogo **Opciones de diferencia** , seleccione las opciones adecuadas y, a continuación, haga clic en **Informe**.</span><span class="sxs-lookup"><span data-stu-id="ca358-111">In the **Difference Options** dialog box, select the appropriate options, and then click **Report**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca358-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ca358-112">See Also</span></span>  
 <span data-ttu-id="ca358-113">[Establecer y recuperar información de versión](../../2014/database-engine/set-and-retrieve-version-information.md) </span><span class="sxs-lookup"><span data-stu-id="ca358-113">[Set and Retrieve Version Information](../../2014/database-engine/set-and-retrieve-version-information.md) </span></span>  
 <span data-ttu-id="ca358-114">[Ver el historial de archivos](../../2014/database-engine/view-file-history.md) </span><span class="sxs-lookup"><span data-stu-id="ca358-114">[View File History](../../2014/database-engine/view-file-history.md) </span></span>  
 <span data-ttu-id="ca358-115">[Ver el historial del proyecto](../../2014/database-engine/view-project-history.md) </span><span class="sxs-lookup"><span data-stu-id="ca358-115">[View Project History](../../2014/database-engine/view-project-history.md) </span></span>  
 <span data-ttu-id="ca358-116">[Ver el estado del archivo](../../2014/database-engine/view-file-status.md) </span><span class="sxs-lookup"><span data-stu-id="ca358-116">[View File Status](../../2014/database-engine/view-file-status.md) </span></span>  
 [<span data-ttu-id="ca358-117">Recuperar archivos</span><span class="sxs-lookup"><span data-stu-id="ca358-117">Retrieve Files</span></span>](../../2014/database-engine/retrieve-files.md)  
  
  
