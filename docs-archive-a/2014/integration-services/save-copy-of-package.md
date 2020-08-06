---
title: Guardar copia del paquete | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.savecopyas.f1
helpviewer_keywords:
- Save Copy of Package dialog box
ms.assetid: 7b44c0d7-d8fa-4491-8836-0899f621d3a8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f0a685d8b38299e1ba1d03c4ec8c1052cc957dbb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748835"
---
# <a name="save-copy-of-package"></a><span data-ttu-id="847db-102">Guardar copia del paquete</span><span class="sxs-lookup"><span data-stu-id="847db-102">Save Copy of Package</span></span>
  <span data-ttu-id="847db-103">Utilice el cuadro de diálogo **Guardar copia del paquete** , disponible en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], para guardar una copia de un paquete de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] desde [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] en una ubicación diferente y, opcionalmente, modificar el nivel de protección del paquete.</span><span class="sxs-lookup"><span data-stu-id="847db-103">Use the **Save Copy of Package** dialog box, available in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], to save a copy of an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package from [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to a different location and, optionally, modify the protection level of the package.</span></span>  
  
## <a name="options"></a><span data-ttu-id="847db-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="847db-104">Options</span></span>  
 <span data-ttu-id="847db-105">**Ubicación del paquete**</span><span class="sxs-lookup"><span data-stu-id="847db-105">**Package location**</span></span>  
 <span data-ttu-id="847db-106">Seleccione el tipo de ubicación de almacenamiento en que desea guardar la copia del paquete.</span><span class="sxs-lookup"><span data-stu-id="847db-106">Select the type of storage location in which to save the package copy.</span></span> <span data-ttu-id="847db-107">Están disponibles las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="847db-107">The following options are available:</span></span>  
  
 <span data-ttu-id="847db-108">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="847db-108">**SQL Server**</span></span>  
  
 <span data-ttu-id="847db-109">**Sistema de archivos**</span><span class="sxs-lookup"><span data-stu-id="847db-109">**File System**</span></span>  
  
 <span data-ttu-id="847db-110">**Almacén de paquetes SSIS**</span><span class="sxs-lookup"><span data-stu-id="847db-110">**SSIS Package Store**</span></span>  
  
 <span data-ttu-id="847db-111">**Server**</span><span class="sxs-lookup"><span data-stu-id="847db-111">**Server**</span></span>  
 <span data-ttu-id="847db-112">Escriba un nombre de servidor o seleccione un servidor de la lista.</span><span class="sxs-lookup"><span data-stu-id="847db-112">Type a server name or select a server from the list.</span></span> <span data-ttu-id="847db-113">Esta opción está disponible solo si la ubicación de almacenamiento es **SQL Server** o **Almacén de paquetes SSIS**.</span><span class="sxs-lookup"><span data-stu-id="847db-113">This option is available only if the storage location is **SQL Server** or **SSIS Package Store**.</span></span>  
  
 <span data-ttu-id="847db-114">**Autenticación**</span><span class="sxs-lookup"><span data-stu-id="847db-114">**Authentication**</span></span>  
 <span data-ttu-id="847db-115">Seleccione Autenticación de Windows o Autenticación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="847db-115">Select Windows Authentication or [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="847db-116">Esta opción solo está disponible si la ubicación de almacenamiento es [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="847db-116">This option is available only if the storage location is [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="847db-117">Siempre que sea posible, use la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="847db-117">Whenever possible use Windows Authentication.</span></span>  
  
 <span data-ttu-id="847db-118">**Tipo de autenticación**</span><span class="sxs-lookup"><span data-stu-id="847db-118">**Authentication type**</span></span>  
 <span data-ttu-id="847db-119">Seleccione un tipo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="847db-119">Select an authentication type.</span></span>  
  
 <span data-ttu-id="847db-120">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="847db-120">**User name**</span></span>  
 <span data-ttu-id="847db-121">Si usa la autenticación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , proporcione un nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="847db-121">If using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a user name.</span></span>  
  
 <span data-ttu-id="847db-122">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="847db-122">**Password**</span></span>  
 <span data-ttu-id="847db-123">Si está usando la autenticación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , proporcione una contraseña.</span><span class="sxs-lookup"><span data-stu-id="847db-123">If using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a password.</span></span>  
  
 <span data-ttu-id="847db-124">**Ruta de acceso del paquete**</span><span class="sxs-lookup"><span data-stu-id="847db-124">**Package path**</span></span>  
 <span data-ttu-id="847db-125">Escriba la ruta de acceso del paquete o haga clic en el botón examinar **(...)** y busque la carpeta en la que desea almacenar el paquete.</span><span class="sxs-lookup"><span data-stu-id="847db-125">Type the package path, or click the browse **(...)** button and locate the folder in which to store the package.</span></span>  
  
 <span data-ttu-id="847db-126">**Nivel de protección**</span><span class="sxs-lookup"><span data-stu-id="847db-126">**Protection level**</span></span>  
 <span data-ttu-id="847db-127">Haga clic en el botón examinar **(...)** y actualice el nivel de protección en el cuadro de diálogo **nivel de protección de paquetes** .</span><span class="sxs-lookup"><span data-stu-id="847db-127">Click the browse **(...)** button and update the protection level in the **Package Protection Level** dialog box.</span></span> <span data-ttu-id="847db-128">Para obtener más información, vea [Nivel de protección de paquetes y del proyecto, cuadro de diálogo](../../2014/integration-services/package-and-project-protection-level-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="847db-128">For more information, see [Package and Project Protection Level Dialog Box](../../2014/integration-services/package-and-project-protection-level-dialog-box.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="847db-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="847db-129">See Also</span></span>  
 <span data-ttu-id="847db-130">[Referencia de la interfaz de usuario del cuadro de diálogo Importar paquete](../../2014/integration-services/import-package-dialog-box-ui-reference.md) </span><span class="sxs-lookup"><span data-stu-id="847db-130">[Import Package Dialog Box UI Reference](../../2014/integration-services/import-package-dialog-box-ui-reference.md) </span></span>  
 <span data-ttu-id="847db-131">[Referencia de la interfaz de usuario del cuadro de diálogo Exportar paquete](../../2014/integration-services/export-package-dialog-box-ui-reference.md) </span><span class="sxs-lookup"><span data-stu-id="847db-131">[Export Package Dialog Box UI Reference](../../2014/integration-services/export-package-dialog-box-ui-reference.md) </span></span>  
 <span data-ttu-id="847db-132">[Guardar paquetes](save-packages.md) </span><span class="sxs-lookup"><span data-stu-id="847db-132">[Save Packages](save-packages.md) </span></span>  
 [<span data-ttu-id="847db-133">Importar y exportar paquetes &#40;servicio SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="847db-133">Import and Export Packages &#40;SSIS Service&#41;</span></span>](../../2014/integration-services/import-and-export-packages-ssis-service.md)  
  
  
