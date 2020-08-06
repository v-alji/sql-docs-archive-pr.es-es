---
title: Cuadro de diálogo de las propiedades de paquete | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.ispackageprop.general.f1
- sql12.ssis.ssms.packageproperties.f1
ms.assetid: a70acbf4-5f5c-4606-8ce4-8eb3684233de
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b386bf4e75ff784cd8d4a96363515786d242d2a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671636"
---
# <a name="package-properties-dialog-box"></a><span data-ttu-id="58f04-102">Propiedades del paquete, cuadro de diálogo</span><span class="sxs-lookup"><span data-stu-id="58f04-102">Package Properties Dialog Box</span></span>
  <span data-ttu-id="58f04-103">Utilice el cuadro de diálogo **Propiedades del paquete** para ver las propiedades de los paquetes almacenados en el servidor de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="58f04-103">Use the **Package Properties** dialog box to view properties for packages that are stored on the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
 <span data-ttu-id="58f04-104">Para obtener más información, vea [Paquetes de Integration Services &#40;SSIS&#41;](integration-services-ssis-server-and-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="58f04-104">For more information, see [Integration Services &#40;SSIS&#41; Server](integration-services-ssis-server-and-catalog.md).</span></span>  
  
 <span data-ttu-id="58f04-105">**¿Qué desea hacer?**</span><span class="sxs-lookup"><span data-stu-id="58f04-105">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="58f04-106">Abrir el cuadro de diálogo Propiedades del paquete</span><span class="sxs-lookup"><span data-stu-id="58f04-106">Open the Package Properties dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="58f04-107">Configurar las opciones</span><span class="sxs-lookup"><span data-stu-id="58f04-107">Configure the Options</span></span>](#options)  
  
##  <a name="open-the-package-properties-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="58f04-108">Abrir el cuadro de diálogo Propiedades del paquete</span><span class="sxs-lookup"><span data-stu-id="58f04-108">Open the Package Properties dialog box</span></span>  
  
1.  <span data-ttu-id="58f04-109">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conéctese al servidor de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="58f04-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="58f04-110">Se conectará a la instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] que hospeda la base de datos SSISDB.</span><span class="sxs-lookup"><span data-stu-id="58f04-110">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the SSISDB database.</span></span>  
  
2.  <span data-ttu-id="58f04-111">En el Explorador de objetos, expanda el árbol para que se muestre el nodo **Catálogos de Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="58f04-111">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="58f04-112">Expanda el nodo **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="58f04-112">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="58f04-113">Expanda la carpeta que contiene el paquete para el que desea ver las propiedades.</span><span class="sxs-lookup"><span data-stu-id="58f04-113">Expand the folder that contains the package you want to view properties for.</span></span>  
  
5.  <span data-ttu-id="58f04-114">Haga clic con el botón derecho en el paquete y, después, seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="58f04-114">Right-click the package, and then select **Properties**.</span></span>  
  
##  <a name="configure-the-options"></a><a name="options"></a> <span data-ttu-id="58f04-115">Configurar las opciones</span><span class="sxs-lookup"><span data-stu-id="58f04-115">Configure the Options</span></span>  
 <span data-ttu-id="58f04-116">Utilice la página **General** para ver las propiedades del paquete seleccionado.</span><span class="sxs-lookup"><span data-stu-id="58f04-116">Use the **General** page to view the properties of the selected package.</span></span>  
  
 <span data-ttu-id="58f04-117">Todas las propiedades que aparecen en la página **General** son de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="58f04-117">All properties on the **General** page are read-only.</span></span>  
  
 <span data-ttu-id="58f04-118">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="58f04-118">**Name**</span></span>  
 <span data-ttu-id="58f04-119">Muestra el nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="58f04-119">Displays the name of the package.</span></span>  
  
 <span data-ttu-id="58f04-120">**Identificador**</span><span class="sxs-lookup"><span data-stu-id="58f04-120">**Identifier**</span></span>  
 <span data-ttu-id="58f04-121">Muestra el identificador del paquete.</span><span class="sxs-lookup"><span data-stu-id="58f04-121">Lists the package ID.</span></span>  
  
 <span data-ttu-id="58f04-122">**Punto de entrada**</span><span class="sxs-lookup"><span data-stu-id="58f04-122">**Entry Point**</span></span>  
 <span data-ttu-id="58f04-123">El valor de `True` indica que el paquete se inicia directamente.</span><span class="sxs-lookup"><span data-stu-id="58f04-123">The value of `True` indicates that the package is started directly.</span></span> <span data-ttu-id="58f04-124">El valor de `False` indica que el paquete debe iniciarse mediante otro paquete con la tarea Ejecutar paquete.</span><span class="sxs-lookup"><span data-stu-id="58f04-124">The value of `False` indicates that the package is started by another package using the Execute Package task.</span></span> <span data-ttu-id="58f04-125">El valor predeterminado es `True`.</span><span class="sxs-lookup"><span data-stu-id="58f04-125">The default value is `True`.</span></span>  
  
 <span data-ttu-id="58f04-126">Puede establecer esta propiedad en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] tanto para el paquete primario como para los paquetes secundarios. Para ello, haga clic con el botón derecho en el paquete en el Explorador de soluciones y, después, haga clic en **Paquete de punto de entrada**.</span><span class="sxs-lookup"><span data-stu-id="58f04-126">You set this property in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] for both the parent package and the child packages by right-clicking the package in Solution Explorer and then clicking **Entry-point Package**.</span></span>  
  
 <span data-ttu-id="58f04-127">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="58f04-127">**Description**</span></span>  
 <span data-ttu-id="58f04-128">Muestra la descripción opcional del paquete.</span><span class="sxs-lookup"><span data-stu-id="58f04-128">Displays the optional description of the package.</span></span>  
  
  
