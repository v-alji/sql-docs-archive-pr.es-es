---
title: Importar desde Analysis Services (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b9a21b23-3a06-4ef8-bc06-9c79cdc54870
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7d6c3d226e46cdb4101bc8db52830046d27b0706
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744371"
---
# <a name="import-from-analysis-services-ssas-tabular"></a><span data-ttu-id="e10b2-102">Importar desde Analysis Services (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="e10b2-102">Import from Analysis Services (SSAS Tabular)</span></span>
  <span data-ttu-id="e10b2-103">Este tema explica cómo crear un proyecto de modelos tabulares importando los metadatos de un modelo tabular existente mediante la plantilla de proyecto Importar del servidor de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e10b2-103">This topic describes how to create a new tabular model project by importing the metadata from an existing tabular model by using the Import from Server project template in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="create-a-new-model-by-importing-metadata-from-an-existing-model-in-analysis-services"></a><span data-ttu-id="e10b2-104">Crear un nuevo modelo importando metadatos de un modelo existente de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="e10b2-104">Create a new model by importing metadata from an existing model in Analysis Services</span></span>  
 <span data-ttu-id="e10b2-105">Puede usar la plantilla de proyecto Importar del servidor para crear un nuevo proyecto de modelos tabulares copiando los metadatos de un modelo tabular existente en un servidor de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="e10b2-105">You can use the Import from Server project template to create a new tabular model project by copying the metadata from an existing tabular model on an Analysis Services server.</span></span> <span data-ttu-id="e10b2-106">El nuevo proyecto se creará con las mismas conexiones de origen de datos, tablas, relaciones, medidas, KPI, roles, jerarquías, perspectivas y particiones que el modelo del que se importó.</span><span class="sxs-lookup"><span data-stu-id="e10b2-106">The new project will be created with the same data source connections, tables, relationships, measures, KPIs, roles, hierarchies, perspectives, and partitions as the model it was imported from.</span></span> <span data-ttu-id="e10b2-107">Sin embargo, los datos no se copian del modelo existente al área de trabajo del nuevo modelo.</span><span class="sxs-lookup"><span data-stu-id="e10b2-107">The data, however, is not copied from the existing model to the new model workspace.</span></span> <span data-ttu-id="e10b2-108">Una vez que el proceso de importación se haya completado, y se haya creado el nuevo proyecto de modelos, deberá ejecutar una operación Procesar todo para cargar los datos de los orígenes de datos en la base de datos del área de trabajo del nuevo proyecto de modelos.</span><span class="sxs-lookup"><span data-stu-id="e10b2-108">Once the import process has completed, and the new model project created, you must run a Process All to load the data from the data sources into the new model project workspace database.</span></span>  
  
#### <a name="to-create-a-new-model-by-importing-metadata-from-an-existing-model"></a><span data-ttu-id="e10b2-109">Para crear un nuevo modelo importando metadatos de un modelo existente</span><span class="sxs-lookup"><span data-stu-id="e10b2-109">To create a new model by importing metadata from an existing model</span></span>  
  
1.  <span data-ttu-id="e10b2-110">En [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], en el menú **Archivo** , haga clic en **Nuevo**y, a continuación, en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="e10b2-110">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], on the **File** menu, click **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="e10b2-111">En el cuadro de diálogo **Nuevo proyecto** , debajo de **Plantillas instaladas**, haga clic en **Business Intelligence**y, a continuación, en **Importar del servidor**.</span><span class="sxs-lookup"><span data-stu-id="e10b2-111">In the **New Project** dialog box, under **Installed Templates**, click **Business Intelligence**, and then click **Import from Server**.</span></span>  
  
3.  <span data-ttu-id="e10b2-112">En **Nombre**, escriba un nombre para el proyecto, después especifique una ubicación y un nombre de solución, y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e10b2-112">In **Name**, type a name for the project, then specify a location and solution name, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="e10b2-113">En el cuadro de diálogo **Importar desde Analysis Services** , en **Nombre de servidor**, especifique el nombre del servidor de Analysis Services que contiene los metadatos del modelo que desea importar.</span><span class="sxs-lookup"><span data-stu-id="e10b2-113">In the **Import from Analysis Services** dialog box, in **Server Name**, specify the name of the Analysis Services server that contains the model metadata you want to import.</span></span>  
  
5.  <span data-ttu-id="e10b2-114">En **Nombre de la base de datos**, seleccione la base de datos del modelo tabular que contiene los metadatos del modelo que desea importar y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e10b2-114">In **Database Name**, select the tabular model database that contains the model metadata you want to import, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e10b2-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e10b2-115">See Also</span></span>  
 [<span data-ttu-id="e10b2-116">Propiedades del proyecto &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="e10b2-116">Project Properties &#40;SSAS Tabular&#41;</span></span>](properties-ssas-tabular.md)  
  
  
