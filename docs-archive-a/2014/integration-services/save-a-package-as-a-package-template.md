---
title: Guardar un paquete como una plantilla de paquete | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- reusing packages
- templates [Integration Services]
ms.assetid: efe66cec-3933-4f6e-8d35-fe3d300de66c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 30bddb5a343e7c7aef279bc66c25be30a2cf1a12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745370"
---
# <a name="save-a-package-as-a-package-template"></a><span data-ttu-id="b1d12-102">guardar un paquete como una plantilla de paquete</span><span class="sxs-lookup"><span data-stu-id="b1d12-102">Save a Package as a Package Template</span></span>
  <span data-ttu-id="b1d12-103">En este tema se describe cómo designar y usar paquetes personalizados como plantillas cuando se crean nuevos paquetes de Integration Services en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1d12-103">This topic describes how to designate and use custom packages as templates when you create new Integration Services packages in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="b1d12-104">De forma predeterminada, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] usa una plantilla de paquetes que crea un paquete vacío cuando se agrega un nuevo paquete a un proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b1d12-104">By default, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] uses a package template that creates an empty package when you add a new package to an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span> <span data-ttu-id="b1d12-105">No puede reemplazar esta plantilla predeterminada, pero puede agregar nuevas plantillas.</span><span class="sxs-lookup"><span data-stu-id="b1d12-105">You cannot replace this default template, but you can add new templates.</span></span>  
  
 <span data-ttu-id="b1d12-106">Puede designar varios paquetes para utilizar como plantillas.</span><span class="sxs-lookup"><span data-stu-id="b1d12-106">You can designate multiple packages to use as templates.</span></span> <span data-ttu-id="b1d12-107">Para poder implementar paquetes personalizados como plantillas, primero debe crear los paquetes.</span><span class="sxs-lookup"><span data-stu-id="b1d12-107">Before you can implement custom packages as templates, you must create the packages.</span></span>  
  
 <span data-ttu-id="b1d12-108">Cuando crea paquetes a partir de paquetes personalizados utilizados como plantillas, los nuevos paquetes tienen el mismo nombre y GUID que la plantilla.</span><span class="sxs-lookup"><span data-stu-id="b1d12-108">When you create package using custom packages as templates, the new packages have the same name and GUID as the template.</span></span> <span data-ttu-id="b1d12-109">Para diferenciar los paquetes, debe actualizar el valor de la propiedad `Name` y generar un nuevo GUID para la propiedad `ID`.</span><span class="sxs-lookup"><span data-stu-id="b1d12-109">To differentiate among packages you should update the value of the `Name` property and generate a new GUID for the `ID` property.</span></span> <span data-ttu-id="b1d12-110">Para más información, vea [Crear paquetes en herramientas de datos de SQL Server](create-packages-in-sql-server-data-tools.md) y [Establecer las propiedades de paquetes](set-package-properties.md).</span><span class="sxs-lookup"><span data-stu-id="b1d12-110">For more information, see [Create Packages in SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) and [Set Package Properties](set-package-properties.md).</span></span>  
  
### <a name="to-designate-a-custom-package-as-a-package-template"></a><span data-ttu-id="b1d12-111">Para designar un paquete personalizado como plantilla de paquetes</span><span class="sxs-lookup"><span data-stu-id="b1d12-111">To designate a custom package as a package template</span></span>  
  
1.  <span data-ttu-id="b1d12-112">En el sistema de archivos, busque el paquete que desea utilizar como plantilla.</span><span class="sxs-lookup"><span data-stu-id="b1d12-112">In the file system, locate the package that you want to use as template.</span></span>  
  
2.  <span data-ttu-id="b1d12-113">Copie el paquete a la carpeta DataTransformationItems.</span><span class="sxs-lookup"><span data-stu-id="b1d12-113">Copy the package to the DataTransformationItems folder.</span></span> <span data-ttu-id="b1d12-114">De forma predeterminada, esta carpeta se encuentra en C:\Archivos de programa\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies\ProjectItems\DataTransformationProject.</span><span class="sxs-lookup"><span data-stu-id="b1d12-114">By default this folder is in C:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies\ProjectItems\DataTransformationProject.</span></span>  
  
3.  <span data-ttu-id="b1d12-115">Repita los pasos 1 y 2 para los demás paquetes que desee utilizar como plantilla.</span><span class="sxs-lookup"><span data-stu-id="b1d12-115">Repeat steps 1 and 2 for each package that you want to use as a template.</span></span>  
  
### <a name="to-use-a-custom-package-as-a-package-template"></a><span data-ttu-id="b1d12-116">Para utilizar un paquete personalizado como plantilla de paquetes</span><span class="sxs-lookup"><span data-stu-id="b1d12-116">To use a custom package as a package template</span></span>  
  
1.  <span data-ttu-id="b1d12-117">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] en el que desea crear un paquete.</span><span class="sxs-lookup"><span data-stu-id="b1d12-117">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project in which you want to create a package.</span></span>  
  
2.  <span data-ttu-id="b1d12-118">En el Explorador de soluciones, haga clic con el botón derecho en el proyecto, seleccione **Agregar** y, después, haga clic en **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="b1d12-118">In Solution Explorer, right-click the project, point to **Add**, and then click **New Item**.</span></span>  
  
3.  <span data-ttu-id="b1d12-119">En el cuadro de diálogo **Agregar nuevo elemento - \<project name>** , haga clic en el paquete que desea usar como plantilla.</span><span class="sxs-lookup"><span data-stu-id="b1d12-119">In the **Add New Item -\<project name>** dialog box, click the package that you want to use as a template.</span></span>  
  
     <span data-ttu-id="b1d12-120">La lista de plantillas incluye la plantilla de paquetes predeterminada denominada Nuevo paquete de SSIS.</span><span class="sxs-lookup"><span data-stu-id="b1d12-120">The list of templates includes the default package template named New SSIS Package.</span></span> <span data-ttu-id="b1d12-121">El icono de paquete identifica plantillas que se pueden utilizar como plantillas de paquetes.</span><span class="sxs-lookup"><span data-stu-id="b1d12-121">The package icon identifies templates that can be used as package templates.</span></span>  
  
4.  <span data-ttu-id="b1d12-122">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b1d12-122">Click **Add**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1d12-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b1d12-123">See Also</span></span>  
 <span data-ttu-id="b1d12-124">[Crear paquetes en SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) </span><span class="sxs-lookup"><span data-stu-id="b1d12-124">[Create Packages in SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) </span></span>  
 [<span data-ttu-id="b1d12-125">Paquetes de Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="b1d12-125">Integration Services &#40;SSIS&#41; Packages</span></span>](../../2014/integration-services/integration-services-ssis-packages.md)  
  
  
