---
title: Asistente para importar proyectos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.importprojectwizard.f1
ms.assetid: 9247ad6c-4bd1-43ab-b347-583181cb9917
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 81a990995d7e98c21b61f484372d31c9a1773102
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673188"
---
# <a name="import-project-wizard"></a><span data-ttu-id="15fc5-102">Asistente para importar proyectos</span><span class="sxs-lookup"><span data-stu-id="15fc5-102">Import Project Wizard</span></span>
  <span data-ttu-id="15fc5-103">Use el Asistente para importar proyectos de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] para crear un nuevo proyecto de Integration Services a partir de otro existente.</span><span class="sxs-lookup"><span data-stu-id="15fc5-103">Use the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Import Project Wizard create a new Integration Services project based on an existing one.</span></span> <span data-ttu-id="15fc5-104">Se usa para importar proyectos que ya se han implementado en el catálogo de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] o para importar proyectos desde un archivo de implementación de proyecto (extensión .ispac).</span><span class="sxs-lookup"><span data-stu-id="15fc5-104">Import projects that have already been deployed to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] catalog or import projects from a project deployment file (.ispac extension).</span></span>  
  
### <a name="to-create-a-project-based-on-a-project-in-ispac-file-or-in-catalog"></a><span data-ttu-id="15fc5-105">Para crear un proyecto basado en un proyecto del archivo .ispac o del catálogo</span><span class="sxs-lookup"><span data-stu-id="15fc5-105">To create a project based on a project in .ispac file or in catalog</span></span>  
  
1.  <span data-ttu-id="15fc5-106">Haga clic en **archivo**, seleccione **nuevo**y haga clic en proyecto.</span><span class="sxs-lookup"><span data-stu-id="15fc5-106">Click **File**, point to **New**, and click Project.</span></span>  
  
2.  <span data-ttu-id="15fc5-107">Expanda **Business Intelligence**y haga clic en **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="15fc5-107">Expand **Business Intelligence**, and click **Integration Services**.</span></span>  
  
3.  <span data-ttu-id="15fc5-108">Seleccione **Asistente para importación de Integration Services** en el panel central, escriba un **nombre** para el proyecto de solución, especifique la **carpeta** del proyecto y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="15fc5-108">Select **Integration Services Import Wizard** in the middle pane, type a **name** for the solution, project, and specify the **folder** for the project, and then click **OK**.</span></span>  
  
     <span data-ttu-id="15fc5-109">Debería aparecer el **Asistente para importar proyectos de Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="15fc5-109">You should see the **Integration Services Import Project Wizard**.</span></span> <span data-ttu-id="15fc5-110">Este asistente crea un nuevo proyecto de Integration Services a partir de otro existente</span><span class="sxs-lookup"><span data-stu-id="15fc5-110">This wizard creates a new Integration Services project based on an existing one</span></span>  
  
4.  <span data-ttu-id="15fc5-111">Haga clic en **Siguiente** en la página **Introducción** para ver la página **Seleccionar origen** .</span><span class="sxs-lookup"><span data-stu-id="15fc5-111">Click **Next** on the **Introduction** page to see the **Select Source** page.</span></span>  
  
5.  <span data-ttu-id="15fc5-112">Especifique si desea importar el proyecto de un archivo .ispac o de un catálogo.</span><span class="sxs-lookup"><span data-stu-id="15fc5-112">Specify whether you want to import project from an .ispac file or from a catalog.</span></span>  
  
    -   <span data-ttu-id="15fc5-113">Si selecciona la opción **Archivo de implementación de proyecto** , especifique la ruta de acceso al archivo .ispac.</span><span class="sxs-lookup"><span data-stu-id="15fc5-113">If you select **Project deployment file** option, specify the path to the .ispac file.</span></span>  
  
    -   <span data-ttu-id="15fc5-114">Si selecciona la opción **Catálogo de Integration Services** , especifique el nombre de la instancia de servidor de bases de datos en la que el catálogo existe, y la ruta de acceso al proyecto en el catálogo.</span><span class="sxs-lookup"><span data-stu-id="15fc5-114">If you select **Integration Services Catalog** option, specify the name of database server instance on which the catalog exists, and the path to the project in the catalog.</span></span>  
  
6.  <span data-ttu-id="15fc5-115">Haga clic en **Siguiente** en la página **Seleccionar origen** para ver la página **Revisar** .</span><span class="sxs-lookup"><span data-stu-id="15fc5-115">Click **Next** on the **Select Source** page to see the **Review** page.</span></span> <span data-ttu-id="15fc5-116">Revise la información mostrada en la página sobre la operación de importación que el asistente va a realizar.</span><span class="sxs-lookup"><span data-stu-id="15fc5-116">Review the information displayed on the page about the import operation the wizard is going to perform.</span></span>  
  
7.  <span data-ttu-id="15fc5-117">Haga clic en **Importar** para crear un nuevo proyecto de Integration Services basado en el que ha seleccionado.</span><span class="sxs-lookup"><span data-stu-id="15fc5-117">Click **Import** to create a new Integration Services project based on the one you selected.</span></span>  
  
8.  <span data-ttu-id="15fc5-118">La página **Resultados** debe mostrar los resultados de la operación de importación que el asistente ha realizado.</span><span class="sxs-lookup"><span data-stu-id="15fc5-118">The **Results** page should display the results from import operation the wizard performed.</span></span> <span data-ttu-id="15fc5-119">Haga clic en **Guardar informe** para guardar el informe en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="15fc5-119">Click **Save Report** to save the report to an XML file.</span></span>  
  
9. <span data-ttu-id="15fc5-120">Haga clic en **Cerrar** para cerrar el asistente.</span><span class="sxs-lookup"><span data-stu-id="15fc5-120">Click **Close** to close the wizard.</span></span>  
  
  
