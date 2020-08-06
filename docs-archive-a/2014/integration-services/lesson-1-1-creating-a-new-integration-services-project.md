---
title: 'Paso 1: Crear un nuevo proyecto de Integration Services | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: f14521b5-941e-443b-8f5e-385f98e37fbf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d6d16d7febcdecb01eb7a93167c2a18d225a9c2d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673141"
---
# <a name="step-1-creating-a-new-integration-services-project"></a><span data-ttu-id="6b5a3-102">Paso 1: Creación de un proyecto de Integration Services</span><span class="sxs-lookup"><span data-stu-id="6b5a3-102">Step 1: Creating a New Integration Services Project</span></span>
  <span data-ttu-id="6b5a3-103">El primer paso al crear un paquete en [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] es crear un proyecto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6b5a3-103">The first step in creating a package in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] is to create an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span> <span data-ttu-id="6b5a3-104">En este proyecto, se incluyen las plantillas de los objetos (orígenes de datos, vistas de orígenes de datos y paquetes) que se usan en una solución de transformación de datos.</span><span class="sxs-lookup"><span data-stu-id="6b5a3-104">This project includes the templates for the objects - data sources, data source views, and packages - that you use in a data transformation solution.</span></span>  
  
 <span data-ttu-id="6b5a3-105">Los paquetes que creará en este tutorial de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] interpretan los valores de los datos dependientes de la configuración regional.</span><span class="sxs-lookup"><span data-stu-id="6b5a3-105">The packages that you will create in this [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] tutorial interpret the values of locale-sensitive data.</span></span> <span data-ttu-id="6b5a3-106">Si no tiene configurado el equipo para usar la opción de configuración regional Inglés (Estados Unidos), debe establecer propiedades adicionales en el paquete.</span><span class="sxs-lookup"><span data-stu-id="6b5a3-106">If your computer is not configured to use the regional option English (United States), you need to set additional properties in the package.</span></span> <span data-ttu-id="6b5a3-107">Los paquetes utilizados en las lecciones 2 a 5 se copian del paquete creado en la lección 1, y no necesita actualizar las propiedades dependientes de la configuración regional en los paquetes copiados.</span><span class="sxs-lookup"><span data-stu-id="6b5a3-107">The packages that you use in lessons 2 through 5 are copied from the package created in lesson 1, and you need not update locale-sensitive properties in the copied packages.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6b5a3-108">Este tutorial necesita Microsoft SQL Server Data Tools.</span><span class="sxs-lookup"><span data-stu-id="6b5a3-108">This tutorial requires Microsoft SQL Server Data Tools.</span></span>  
>   
>  <span data-ttu-id="6b5a3-109">Para obtener más información sobre cómo instalar SQL Server Data Tools, consulte [Descargar SQL Server Data Tools](https://msdn.microsoft.com/data/hh297027).</span><span class="sxs-lookup"><span data-stu-id="6b5a3-109">For more information on installing the SQL Server Data Tools see [SQL Server Data Tools Download](https://msdn.microsoft.com/data/hh297027).</span></span>  
  
### <a name="to-create-a-new-integration-services-project"></a><span data-ttu-id="6b5a3-110">Para crear un proyecto de Integration Services</span><span class="sxs-lookup"><span data-stu-id="6b5a3-110">To create a new Integration Services project</span></span>  
  
1.  <span data-ttu-id="6b5a3-111">En el menú **Inicio** , elija **Todos los programas**, **Microsoft SQL Server**y, a continuación, haga clic en **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="6b5a3-111">On the **Start** menu, point to **All Programs**, point to **Microsoft SQL Server**, and click **SQL Server Data Tools**.</span></span>  
  
2.  <span data-ttu-id="6b5a3-112">En el menú **Archivo** , seleccione **Nuevo**y haga clic en **Proyecto** para crear un proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6b5a3-112">On the **File** menu, point to **New**, and click **Project** to create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span>  
  
3.  <span data-ttu-id="6b5a3-113">En el cuadro de diálogo **Nuevo proyecto** , expanda el nodo **Business Intelligence** bajo **Plantillas instaladas**y seleccione **Proyecto de Integration Services** en el panel **Plantillas** .</span><span class="sxs-lookup"><span data-stu-id="6b5a3-113">In the **New Project** dialog box, expand the **Business Intelligence** node under **Installed Templates**, and select **Integration Services Project** in the **Templates** pane.</span></span>  
  
4.  <span data-ttu-id="6b5a3-114">En el cuadro **Nombre** , cambie el nombre predeterminado por **SSIS Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="6b5a3-114">In the **Name** box, change the default name to **SSIS Tutorial**.</span></span> <span data-ttu-id="6b5a3-115">Opcionalmente, desactive la casilla **Crear directorio para la solución** .</span><span class="sxs-lookup"><span data-stu-id="6b5a3-115">Optionally, clear the **Create directory for solution** check box.</span></span>  
  
5.  <span data-ttu-id="6b5a3-116">Acepte la ubicación predeterminada o haga clic en **Examinar** para desplazarse a la carpeta que desee utilizar.</span><span class="sxs-lookup"><span data-stu-id="6b5a3-116">Accept the default location, or click **Browse** to browse to locate the folder you want to use.</span></span> <span data-ttu-id="6b5a3-117">En el cuadro de diálogo **Ubicación del proyecto** , haga clic en la carpeta y, a continuación, haga clic en **Seleccionar carpeta**.</span><span class="sxs-lookup"><span data-stu-id="6b5a3-117">In the **Project Location** dialog box, click the folder and click **Select Folder**.</span></span>  
  
6.  <span data-ttu-id="6b5a3-118">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="6b5a3-118">Click **OK**.</span></span>  
  
     <span data-ttu-id="6b5a3-119">De forma predeterminada, se creará un paquete vacío, denominado **Package.dtsx**, que se agregará al proyecto bajo Paquetes SSIS.</span><span class="sxs-lookup"><span data-stu-id="6b5a3-119">By default, an empty package, titled **Package.dtsx**, will be created and added to your project under SSIS Packages.</span></span>  
  
7.  <span data-ttu-id="6b5a3-120">En la barra de herramientas del **Explorador de soluciones** , haga clic con el botón derecho en **Package.dtsx**, haga clic en **Cambiar nombre**y cambie el nombre del paquete predeterminado por **Lesson 1.dtsx**.</span><span class="sxs-lookup"><span data-stu-id="6b5a3-120">In **Solution Explorer** toolbar, right-click **Package.dtsx**, click **Rename**, and rename the default package to **Lesson 1.dtsx**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="6b5a3-121">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="6b5a3-121">Next Task in Lesson</span></span>  
 [<span data-ttu-id="6b5a3-122">Paso 2: Adición y configuración de un administrador de conexiones de archivos planos</span><span class="sxs-lookup"><span data-stu-id="6b5a3-122">Step 2: Adding and Configuring a Flat File Connection Manager</span></span>](lesson-1-2-adding-and-configuring-a-flat-file-connection-manager.md)  
  
  
