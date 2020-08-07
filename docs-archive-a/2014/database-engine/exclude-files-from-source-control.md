---
title: Excluir archivos del control de código fuente | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- excluding files from source control
- source controls [SQL Server Management Studio], file exclusions
ms.assetid: 7dcb6514-db5c-49eb-8b5a-2c766ce39aa7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 9fb3c5ccb4fcaad062236eec6d04f995557dc2b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746428"
---
# <a name="exclude-files-from-source-control"></a><span data-ttu-id="e1bb2-102">Excluir archivos desde el control de código fuente</span><span class="sxs-lookup"><span data-stu-id="e1bb2-102">Exclude Files from Source Control</span></span>
  <span data-ttu-id="e1bb2-103">Si la solución en la que está trabajando contiene archivos que no requieren servicios de control de código fuente, puede usar el comando **excluir del control de código** fuente para excluir el archivo del control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="e1bb2-103">If the solution you are working on contains files that do not require source control services, you can use the **Exclude from Source Control** command to exclude the file from source control.</span></span> <span data-ttu-id="e1bb2-104">Al hacer esto, el archivo permanece en la base de datos de [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe, aunque ya no se protege ni desprotege con el proyecto.</span><span class="sxs-lookup"><span data-stu-id="e1bb2-104">When you do this, the file remains in the [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe database, but it is no longer checked in or out with the project.</span></span>  
  
 <span data-ttu-id="e1bb2-105">Debe usar el comando **excluir del control de código fuente** solo en los archivos generados.</span><span class="sxs-lookup"><span data-stu-id="e1bb2-105">You should use the **Exclude from Source Control** command only on generated files.</span></span> <span data-ttu-id="e1bb2-106">Un archivo generado es aquél que puede volver a crearse por completo [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] según el contenido de otro archivo de la solución.</span><span class="sxs-lookup"><span data-stu-id="e1bb2-106">A generated file is one that can be entirely re-created by [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] based on the contents of another file in the solution.</span></span>  
  
### <a name="to-exclude-a-file-from-source-control"></a><span data-ttu-id="e1bb2-107">Para excluir un archivo del control de código fuente</span><span class="sxs-lookup"><span data-stu-id="e1bb2-107">To exclude a file from source control</span></span>  
  
1.  <span data-ttu-id="e1bb2-108">En el Explorador de soluciones, seleccione el archivo que desea excluir.</span><span class="sxs-lookup"><span data-stu-id="e1bb2-108">In Solution Explorer, select the file to exclude.</span></span>  
  
2.  <span data-ttu-id="e1bb2-109">En el menú **archivo** , seleccione **control de código fuente**y, a continuación, haga clic en **excluir** *\<file name>* **del control de código fuente**.</span><span class="sxs-lookup"><span data-stu-id="e1bb2-109">On the **File** menu, point to **Source Control**, and then click **Exclude** *\<file name>* **from Source Control**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1bb2-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e1bb2-110">See Also</span></span>  
 <span data-ttu-id="e1bb2-111">[Aspectos básicos del control de código fuente](../../2014/database-engine/source-control-basics.md) </span><span class="sxs-lookup"><span data-stu-id="e1bb2-111">[Source Control Basics](../../2014/database-engine/source-control-basics.md) </span></span>  
 <span data-ttu-id="e1bb2-112">[Establecer opciones de control de código fuente](../../2014/database-engine/set-source-control-options.md) </span><span class="sxs-lookup"><span data-stu-id="e1bb2-112">[Set Source Control Options](../../2014/database-engine/set-source-control-options.md) </span></span>  
 [<span data-ttu-id="e1bb2-113">Cambiar las conexiones del control de código fuente</span><span class="sxs-lookup"><span data-stu-id="e1bb2-113">Change Source Control Connections</span></span>](../../2014/database-engine/change-source-control-connections.md)  
  
  
