---
title: Descripción del script de implementación de Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Analysis Services Deployment Wizard, scripts
- deploying [Analysis Services], scripts
- Analysis Services deployments, scripts
- scripts [Analysis Services], deployment
ms.assetid: a63ebee9-9848-48f1-82ad-64ecf2e47019
author: minewiskan
ms.author: owend
ms.openlocfilehash: 25df0b377918316e54a14787d7492a681c81778d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746006"
---
# <a name="understanding-the-analysis-services-deployment-script"></a><span data-ttu-id="21502-102">Descripción del script de implementación de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="21502-102">Understanding the Analysis Services Deployment Script</span></span>
  <span data-ttu-id="21502-103">El script de implementación XMLA generado por el Asistente para la implementación de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] está formado por dos secciones:</span><span class="sxs-lookup"><span data-stu-id="21502-103">The XMLA deployment script generated by the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard consists of two sections:</span></span>  
  
-   <span data-ttu-id="21502-104">La primera parte del script de implementación contiene los comandos necesarios para crear, modificar o eliminar los objetos adecuados [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en la base de datos de destino.</span><span class="sxs-lookup"><span data-stu-id="21502-104">The first part of the deployment script contains the commands required to create, alter, or delete the appropriate [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objects in the destination database.</span></span> <span data-ttu-id="21502-105">De forma predeterminada, los archivos de entrada generados por el proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] se basan en una implementación incremental.</span><span class="sxs-lookup"><span data-stu-id="21502-105">By default, the input files generated by the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project are based on an incremental deployment.</span></span> <span data-ttu-id="21502-106">En consecuencia, el script de implementación XMLA solamente afectará a los objetos que se cambiaron o se eliminaron.</span><span class="sxs-lookup"><span data-stu-id="21502-106">As a result, the XMLA deployment script will only affect those objects that were changed or deleted.</span></span>  
  
-   <span data-ttu-id="21502-107">La segunda parte del script de implementación contiene los comandos necesarios para procesar únicamente los objetos creados o modificados en el servidor de destino (opción Procesar predeterminado) o para procesar completamente la base de datos de destino.</span><span class="sxs-lookup"><span data-stu-id="21502-107">The second part of the deployment script contains the commands required to process only the objects created or altered on the destination server (the Process Default option) or to fully process the destination database.</span></span> <span data-ttu-id="21502-108">Además, puede elegir que el script de implementación no contenga comandos de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="21502-108">You can also choose to have the deployment script contain no processing commands.</span></span>  
  
 <span data-ttu-id="21502-109">El script de implementación completa se puede ejecutar en una única transacción o en varias transacciones.</span><span class="sxs-lookup"><span data-stu-id="21502-109">The entire deployment script can execute in a single transaction or in multiple transactions.</span></span> <span data-ttu-id="21502-110">Si el script se ejecuta en varias transacciones, la primera parte del mismo se ejecuta en una única transacción y cada objeto se procesa en su propia transacción.</span><span class="sxs-lookup"><span data-stu-id="21502-110">If the script executes in multiple transactions, the first part of the script executes as a single transaction, and each object is processed in its own transaction.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="21502-111">El Asistente para la implementación de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] solamente implementa los objetos en una sola base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="21502-111">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard only deploys objects into a single [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="21502-112">No implementa ningún objeto o datos en el nivel de servidor.</span><span class="sxs-lookup"><span data-stu-id="21502-112">It does not deploy any server level objects or data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21502-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="21502-113">See Also</span></span>  
 <span data-ttu-id="21502-114">[Ejecutar el Asistente para la implementación de Analysis Services](running-the-analysis-services-deployment-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="21502-114">[Running the Analysis Services Deployment Wizard](running-the-analysis-services-deployment-wizard.md) </span></span>  
 [<span data-ttu-id="21502-115">Comprender los archivos de entrada utilizados para crear el script de implementación</span><span class="sxs-lookup"><span data-stu-id="21502-115">Understanding the Input Files Used to Create the Deployment Script</span></span>](deployment-script-files-input-used-to-create-deployment-script.md)  
  
  