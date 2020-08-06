---
title: Cuadro de diálogo convertir al modelo de implementación de paquetes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.bids.converttolegacydeployment.f1
ms.assetid: 9e60a34a-10f7-48d1-966f-b3ff236ab4b7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b52932ad26f8cebd2e67b0025f4b881241119f6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673834"
---
# <a name="convert-to-package-deployment-model-dialog-box"></a><span data-ttu-id="cbfe9-102">Convertir a modelo de implementación de paquetes, cuadro de diálogo</span><span class="sxs-lookup"><span data-stu-id="cbfe9-102">Convert to Package Deployment Model Dialog Box</span></span>
  <span data-ttu-id="cbfe9-103">El comando de **Convertir a modelo de implementación de paquetes** permite convertir un paquete al modelo de implementación de paquetes después de comprobar el proyecto y cada paquete en el proyecto para ver la compatibilidad con ese modelo.</span><span class="sxs-lookup"><span data-stu-id="cbfe9-103">The **Convert to Package Deployment Model** command allows you to convert a package to the package deployment model after checking the project and each package in the project for compatibility with that model.</span></span> <span data-ttu-id="cbfe9-104">Si un paquete usa las características exclusivas del modelo de implementación de proyectos, como los parámetros, el paquete no se podrá convertir.</span><span class="sxs-lookup"><span data-stu-id="cbfe9-104">If a package uses features unique to the project deployment model, such as parameters, then the package cannot be converted.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="cbfe9-105">Lista de tareas</span><span class="sxs-lookup"><span data-stu-id="cbfe9-105">Task List</span></span>  
 <span data-ttu-id="cbfe9-106">Para convertir un paquete al modelo de implementación de paquetes es preciso realizar dos pasos.</span><span class="sxs-lookup"><span data-stu-id="cbfe9-106">Converting a package to the package deployment model requires two steps.</span></span>  
  
1.  <span data-ttu-id="cbfe9-107">Cuando se selecciona el comando **Convertir a modelo de implementación de paquetes** en el menú **Proyecto** , el proyecto y cada paquete se comprueban para ver su compatibilidad con este modelo.</span><span class="sxs-lookup"><span data-stu-id="cbfe9-107">When you select the **Convert to Package Deployment Model** command from the **Project** menu, the project and each package are checked for compatibility with this model.</span></span> <span data-ttu-id="cbfe9-108">Los resultados se muestran en tabla **Resultados** .</span><span class="sxs-lookup"><span data-stu-id="cbfe9-108">The results are displayed in the **Results** table.</span></span>  
  
     <span data-ttu-id="cbfe9-109">Si el proyecto o un paquete no supera la prueba de compatibilidad, haga clic en **Error** en la columna **Resultado** para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="cbfe9-109">If the project or a package fails the compatibility test, click **Failed** in the **Result** column for more information.</span></span> <span data-ttu-id="cbfe9-110">Haga clic en **Guardar informe** para guardar una copia de esta información en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="cbfe9-110">Click **Save Report** to save a copy of this information to a text file.</span></span>  
  
2.  <span data-ttu-id="cbfe9-111">Si el proyecto y todos los paquetes superan la prueba de compatibilidad, haga clic **Aceptar** para convertir el paquete.</span><span class="sxs-lookup"><span data-stu-id="cbfe9-111">If the project and all packages pass the compatibility test, then click **OK** to convert the package.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cbfe9-112">Para convertir un proyecto al modelo de implementación de paquetes, use el **Asistente para conversión de proyectos de Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="cbfe9-112">To convert a project to the project deployment model, use the **Integration Services Project Conversion Wizard**.</span></span> <span data-ttu-id="cbfe9-113">Para más información, consulte [Integration Services Project Conversion Wizard](../../2014/integration-services/integration-services-project-conversion-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="cbfe9-113">For more information, see [Integration Services Project Conversion Wizard](../../2014/integration-services/integration-services-project-conversion-wizard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbfe9-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cbfe9-114">See Also</span></span>  
 <span data-ttu-id="cbfe9-115">[Implementación de proyectos y paquetes](packages/deploy-integration-services-ssis-projects-and-packages.md) </span><span class="sxs-lookup"><span data-stu-id="cbfe9-115">[Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md) </span></span>  
 <span data-ttu-id="cbfe9-116">[Implementación de paquetes &#40;SSIS&#41;](packages/legacy-package-deployment-ssis.md) </span><span class="sxs-lookup"><span data-stu-id="cbfe9-116">[Package Deployment &#40;SSIS&#41;](packages/legacy-package-deployment-ssis.md) </span></span>  
 [<span data-ttu-id="cbfe9-117">Asistente para conversión de proyectos de Integration Services</span><span class="sxs-lookup"><span data-stu-id="cbfe9-117">Integration Services Project Conversion Wizard</span></span>](../../2014/integration-services/integration-services-project-conversion-wizard.md)  
  
  
