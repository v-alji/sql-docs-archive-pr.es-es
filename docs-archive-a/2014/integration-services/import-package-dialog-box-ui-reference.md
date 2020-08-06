---
title: Referencia de la interfaz de usuario del cuadro de diálogo Importar paquete | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.dtsserver.importpackage.f1
helpviewer_keywords:
- Import Package dialog box
ms.assetid: 0e5fb127-c7ff-4dfa-b90e-d9bcf0ce763b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ff20bf8eb221778465a26944280d53b6aab07601
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673189"
---
# <a name="import-package-dialog-box-ui-reference"></a><span data-ttu-id="07735-102">Referencia de la interfaz de usuario del cuadro de diálogo Importar paquete</span><span class="sxs-lookup"><span data-stu-id="07735-102">Import Package Dialog Box UI Reference</span></span>
  <span data-ttu-id="07735-103">Utilice el cuadro de diálogo **Importar paquete** , disponible en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], para importar un paquete de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] y para establecer o modificar el nivel de protección del paquete.</span><span class="sxs-lookup"><span data-stu-id="07735-103">Use the **Import Package** dialog box, available in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], to import a [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package and to set or modify the protection level of the package.</span></span>  
  
## <a name="options"></a><span data-ttu-id="07735-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="07735-104">Options</span></span>  
 <span data-ttu-id="07735-105">**Ubicación del paquete**</span><span class="sxs-lookup"><span data-stu-id="07735-105">**Package location**</span></span>  
 <span data-ttu-id="07735-106">Seleccione el tipo de ubicación de almacenamiento a la que se importará el paquete.</span><span class="sxs-lookup"><span data-stu-id="07735-106">Select the type of storage location to import the package to.</span></span> <span data-ttu-id="07735-107">Están disponibles las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="07735-107">The following options are available:</span></span>  
  
 <span data-ttu-id="07735-108">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="07735-108">**SQL Server**</span></span>  
  
 <span data-ttu-id="07735-109">**Sistema de archivos**</span><span class="sxs-lookup"><span data-stu-id="07735-109">**File System**</span></span>  
  
 <span data-ttu-id="07735-110">**Almacén de paquetes SSIS**</span><span class="sxs-lookup"><span data-stu-id="07735-110">**SSIS Package Store**</span></span>  
  
 <span data-ttu-id="07735-111">**Server**</span><span class="sxs-lookup"><span data-stu-id="07735-111">**Server**</span></span>  
 <span data-ttu-id="07735-112">Escriba un nombre de servidor o seleccione un servidor de la lista.</span><span class="sxs-lookup"><span data-stu-id="07735-112">Type a server name or select a server from the list.</span></span>  
  
 <span data-ttu-id="07735-113">**Autenticación**</span><span class="sxs-lookup"><span data-stu-id="07735-113">**Authentication**</span></span>  
 <span data-ttu-id="07735-114">Seleccione Autenticación de Windows o Autenticación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="07735-114">Select Windows Authentication or [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="07735-115">Esta opción solo está disponible si la ubicación de almacenamiento es [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="07735-115">This option is available only if the storage location is [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="07735-116">Siempre que sea posible, utilice la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="07735-116">Whenever possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="07735-117">**Tipo de autenticación**</span><span class="sxs-lookup"><span data-stu-id="07735-117">**Authentication type**</span></span>  
 <span data-ttu-id="07735-118">Seleccione un tipo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="07735-118">Select an authentication type.</span></span>  
  
 <span data-ttu-id="07735-119">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="07735-119">**User name**</span></span>  
 <span data-ttu-id="07735-120">Si usa la autenticación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , proporcione un nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="07735-120">If using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a user name.</span></span>  
  
 <span data-ttu-id="07735-121">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="07735-121">**Password**</span></span>  
 <span data-ttu-id="07735-122">Si está usando la autenticación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , proporcione una contraseña.</span><span class="sxs-lookup"><span data-stu-id="07735-122">If using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a password.</span></span>  
  
 <span data-ttu-id="07735-123">**Ruta de acceso del paquete**</span><span class="sxs-lookup"><span data-stu-id="07735-123">**Package path**</span></span>  
 <span data-ttu-id="07735-124">Escriba la ruta de acceso del paquete, o bien haga clic en el botón Examinar **(…)** y busque el paquete.</span><span class="sxs-lookup"><span data-stu-id="07735-124">Type the package path, or click the browse button **(...)** and locate the package.</span></span>  
  
 <span data-ttu-id="07735-125">**Nombre del paquete**</span><span class="sxs-lookup"><span data-stu-id="07735-125">**Package name**</span></span>  
 <span data-ttu-id="07735-126">También puede cambiar el nombre del paquete si lo desea.</span><span class="sxs-lookup"><span data-stu-id="07735-126">Optionally, rename the package.</span></span> <span data-ttu-id="07735-127">El nombre predeterminado es el nombre del paquete que se importará.</span><span class="sxs-lookup"><span data-stu-id="07735-127">The default name is the name of the package to import.</span></span>  
  
 <span data-ttu-id="07735-128">**Nivel de protección**</span><span class="sxs-lookup"><span data-stu-id="07735-128">**Protection level**</span></span>  
 <span data-ttu-id="07735-129">Haga clic en el botón Examinar **(…)** y, en el cuadro de diálogo **Nivel de protección de paquetes**, actualice el nivel de protección.</span><span class="sxs-lookup"><span data-stu-id="07735-129">Click the browse button **(...)** and, in the **Package Protection Level** dialog box, update the protection level.</span></span> <span data-ttu-id="07735-130">Para obtener más información, vea [Nivel de protección de paquetes y del proyecto, cuadro de diálogo](../../2014/integration-services/package-and-project-protection-level-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="07735-130">For more information, see [Package and Project Protection Level Dialog Box](../../2014/integration-services/package-and-project-protection-level-dialog-box.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07735-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="07735-131">See Also</span></span>  
 <span data-ttu-id="07735-132">[Guardar copia del paquete](../../2014/integration-services/save-copy-of-package.md) </span><span class="sxs-lookup"><span data-stu-id="07735-132">[Save Copy of Package](../../2014/integration-services/save-copy-of-package.md) </span></span>  
 <span data-ttu-id="07735-133">[Referencia de la interfaz de usuario del cuadro de diálogo Exportar paquete](../../2014/integration-services/export-package-dialog-box-ui-reference.md) </span><span class="sxs-lookup"><span data-stu-id="07735-133">[Export Package Dialog Box UI Reference](../../2014/integration-services/export-package-dialog-box-ui-reference.md) </span></span>  
 <span data-ttu-id="07735-134">[Guardar paquetes](save-packages.md) </span><span class="sxs-lookup"><span data-stu-id="07735-134">[Save Packages](save-packages.md) </span></span>  
 [<span data-ttu-id="07735-135">Importar y exportar paquetes &#40;servicio SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="07735-135">Import and Export Packages &#40;SSIS Service&#41;</span></span>](../../2014/integration-services/import-and-export-packages-ssis-service.md)  
  
  
