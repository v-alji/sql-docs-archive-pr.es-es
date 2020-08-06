---
title: Copiar un paquete de SQL Server Data Tools | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- packages [Integration Services], copying
- copying packages
- regenerating package GUID
- updating package properties
ms.assetid: 03edc659-e76d-48c0-a749-5f1899b6b507
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bd6ed4dd66ee4755181f5df6f3c1b5466b3f26b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673832"
---
# <a name="copy-a-package-in-sql-server-data-tools"></a><span data-ttu-id="bf694-102">Copiar un paquete en herramientas de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="bf694-102">Copy a Package in SQL Server Data Tools</span></span>
  <span data-ttu-id="bf694-103">Este tema describe cómo crear un nuevo paquete [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] mediante la copia de un paquete existente y cómo actualizar las propiedades `Name` y `GUID` del nuevo paquete.</span><span class="sxs-lookup"><span data-stu-id="bf694-103">This topic describes how to create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package by copying an existing package, and how to update the `Name` and `GUID` properties of the new package.</span></span>  
  
### <a name="to-copy-a-package"></a><span data-ttu-id="bf694-104">Para copiar un paquete</span><span class="sxs-lookup"><span data-stu-id="bf694-104">To copy a package</span></span>  
  
1.  <span data-ttu-id="bf694-105">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete que desea copiar.</span><span class="sxs-lookup"><span data-stu-id="bf694-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package that you want to copy.</span></span>  
  
2.  <span data-ttu-id="bf694-106">En el Explorador de soluciones, haga doble clic en el paquete.</span><span class="sxs-lookup"><span data-stu-id="bf694-106">In Solution Explorer, double-click the package.</span></span>  
  
3.  <span data-ttu-id="bf694-107">Compruebe que el paquete que desea copiar está seleccionado en el Explorador de soluciones o que la pestaña del Diseñador SSIS que contiene el paquete es una pestaña activa.</span><span class="sxs-lookup"><span data-stu-id="bf694-107">Verify either the package to copy is selected in Solution Explorer or the tab in SSIS Designer that contains the package is the active tab</span></span>  
  
4.  <span data-ttu-id="bf694-108">En el menú **Archivo** , haga clic en **Guardar \<package name> como**.</span><span class="sxs-lookup"><span data-stu-id="bf694-108">On the **File** menu, click **Save \<package name> As**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bf694-109">El paquete se debe abrir en el Diseñador SSIS para que la opción **Guardar como** aparezca en el menú **Archivo** .</span><span class="sxs-lookup"><span data-stu-id="bf694-109">The package must be opened in SSIS Designer before the **Save As** option appears on the **File** menu.</span></span>  
  
5.  <span data-ttu-id="bf694-110">También puede examinar una carpeta diferente.</span><span class="sxs-lookup"><span data-stu-id="bf694-110">Optionally, browse to a different folder.</span></span>  
  
6.  <span data-ttu-id="bf694-111">Actualice el nombre del archivo de paquete.</span><span class="sxs-lookup"><span data-stu-id="bf694-111">Update the name of the package file.</span></span> <span data-ttu-id="bf694-112">Asegúrese de mantener la extensión de archivo .dtsx.</span><span class="sxs-lookup"><span data-stu-id="bf694-112">Make sure that you retain the .dtsx file extension.</span></span>  
  
7.  <span data-ttu-id="bf694-113">Haga clic en **Save**(Guardar).</span><span class="sxs-lookup"><span data-stu-id="bf694-113">Click **Save**.</span></span>  
  
8.  <span data-ttu-id="bf694-114">En el símbolo del sistema, elija si desea actualizar el nombre del objeto del paquete para que coincida con el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="bf694-114">At the prompt, choose whether to update the name of the package object to match the file name.</span></span> <span data-ttu-id="bf694-115">Si hace clic en **sí**, `Name` se actualiza la propiedad del paquete.</span><span class="sxs-lookup"><span data-stu-id="bf694-115">If you click **Yes**, the `Name` property of the package is updated.</span></span> <span data-ttu-id="bf694-116">El nuevo paquete se agrega al proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] y se abre en el Diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bf694-116">The new package is added to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project and opened in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
9. <span data-ttu-id="bf694-117">También puede hacer clic en el fondo de la pestaña **Flujo de control** y luego hacer clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="bf694-117">Optionally, click in the background of the **Control Flow** tab, and the click **Properties**.</span></span>  
  
10. <span data-ttu-id="bf694-118">En la ventana Propiedades, haga clic en el valor de la propiedad Id. y luego, en la lista desplegable, haga clic en **\<Generate New ID>** .</span><span class="sxs-lookup"><span data-stu-id="bf694-118">In the Properties window, click the value of the ID property, and then in the drop-down list click **\<Generate New ID>**.</span></span>  
  
11. <span data-ttu-id="bf694-119">En el menú **Archivo** , haga clic en **Guardar los elementos seleccionados** para guardar el nuevo paquete.</span><span class="sxs-lookup"><span data-stu-id="bf694-119">On the **File** menu, click **Save Selected Items** to save the new package.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf694-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bf694-120">See Also</span></span>  
 <span data-ttu-id="bf694-121">[Guardar una copia de un paquete](../../2014/integration-services/save-a-copy-of-a-package.md) </span><span class="sxs-lookup"><span data-stu-id="bf694-121">[Save a Copy of a Package](../../2014/integration-services/save-a-copy-of-a-package.md) </span></span>  
 <span data-ttu-id="bf694-122">[Crear paquetes en SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) </span><span class="sxs-lookup"><span data-stu-id="bf694-122">[Create Packages in SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) </span></span>  
 [<span data-ttu-id="bf694-123">Paquetes de Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="bf694-123">Integration Services &#40;SSIS&#41; Packages</span></span>](../../2014/integration-services/integration-services-ssis-packages.md)  
  
  
