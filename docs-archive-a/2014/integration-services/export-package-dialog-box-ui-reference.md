---
title: Referencia de la interfaz de usuario del cuadro de diálogo Exportar paquete | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.dtsserver.exportpackage.f1
helpviewer_keywords:
- Export Package dialog box
ms.assetid: 3742fe8a-ef57-444d-b2fb-cb25d16bae97
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8aedb771dc61fca737ba3841e65b8cb8655d173e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752297"
---
# <a name="export-package-dialog-box-ui-reference"></a><span data-ttu-id="20303-102">Referencia de la interfaz de usuario del cuadro de diálogo Exportar paquete</span><span class="sxs-lookup"><span data-stu-id="20303-102">Export Package Dialog Box UI Reference</span></span>
  <span data-ttu-id="20303-103">Utilice el cuadro de diálogo **Exportar paquete** , disponible en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], para exportar un paquete de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] a una ubicación diferente y, opcionalmente, modificar el nivel de protección del paquete.</span><span class="sxs-lookup"><span data-stu-id="20303-103">Use the **Export Package** dialog box, available in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], to export a [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package to a different location and optionally, modify the protection level of the package.</span></span>  
  
## <a name="options"></a><span data-ttu-id="20303-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="20303-104">Options</span></span>  
 <span data-ttu-id="20303-105">**Ubicación del paquete**</span><span class="sxs-lookup"><span data-stu-id="20303-105">**Package location**</span></span>  
 <span data-ttu-id="20303-106">Seleccione el tipo de almacenamiento al que desea exportar el paquete.</span><span class="sxs-lookup"><span data-stu-id="20303-106">Select the type of storage to export the package to.</span></span> <span data-ttu-id="20303-107">Están disponibles las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="20303-107">The following options are available:</span></span>  
  
 <span data-ttu-id="20303-108">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="20303-108">**SQL Server**</span></span>  
  
 <span data-ttu-id="20303-109">**Sistema de archivos**</span><span class="sxs-lookup"><span data-stu-id="20303-109">**File System**</span></span>  
  
 <span data-ttu-id="20303-110">**Almacén de paquetes SSIS**</span><span class="sxs-lookup"><span data-stu-id="20303-110">**SSIS Package Storage**</span></span>  
  
 <span data-ttu-id="20303-111">**Server**</span><span class="sxs-lookup"><span data-stu-id="20303-111">**Server**</span></span>  
 <span data-ttu-id="20303-112">Escriba un nombre de servidor o seleccione un servidor de la lista.</span><span class="sxs-lookup"><span data-stu-id="20303-112">Type a server name or select a server from the list.</span></span>  
  
 <span data-ttu-id="20303-113">**Autenticación**</span><span class="sxs-lookup"><span data-stu-id="20303-113">**Authentication**</span></span>  
 <span data-ttu-id="20303-114">Seleccione Autenticación de Windows o Autenticación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="20303-114">Select Windows Authentication or [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="20303-115">Esta opción solo está disponible si la ubicación de almacenamiento es [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="20303-115">This option is available only if the storage location is [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="20303-116">Siempre que sea posible, utilice la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="20303-116">Whenever possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="20303-117">**Tipo de autenticación**</span><span class="sxs-lookup"><span data-stu-id="20303-117">**Authentication type**</span></span>  
 <span data-ttu-id="20303-118">Seleccione un tipo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="20303-118">Select an authentication type.</span></span>  
  
 <span data-ttu-id="20303-119">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="20303-119">**User name**</span></span>  
 <span data-ttu-id="20303-120">Si usa la autenticación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , proporcione un nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="20303-120">If using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a user name.</span></span>  
  
 <span data-ttu-id="20303-121">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="20303-121">**Password**</span></span>  
 <span data-ttu-id="20303-122">Si está usando la autenticación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , proporcione una contraseña.</span><span class="sxs-lookup"><span data-stu-id="20303-122">If using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a password.</span></span>  
  
 <span data-ttu-id="20303-123">**Ruta de acceso del paquete**</span><span class="sxs-lookup"><span data-stu-id="20303-123">**Package path**</span></span>  
 <span data-ttu-id="20303-124">Escriba la ruta de acceso del paquete, o bien haga clic en el botón Examinar **(…)** y busque la carpeta donde quiera guardar el paquete.</span><span class="sxs-lookup"><span data-stu-id="20303-124">Type the package path, or click the browse button **(...)** and locate the folder in which to store the package.</span></span>  
  
 <span data-ttu-id="20303-125">**Nivel de protección**</span><span class="sxs-lookup"><span data-stu-id="20303-125">**Protection level**</span></span>  
 <span data-ttu-id="20303-126">Haga clic en el botón Examinar **(…)** y actualice el nivel de protección en el cuadro de diálogo **Nivel de protección de paquetes**.</span><span class="sxs-lookup"><span data-stu-id="20303-126">Click the browse button **(...)** and update the protection level in the **Package Protection Level** dialog box.</span></span> <span data-ttu-id="20303-127">Para obtener más información, vea [Nivel de protección de paquetes y del proyecto, cuadro de diálogo](../../2014/integration-services/package-and-project-protection-level-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="20303-127">For more information, see [Package and Project Protection Level Dialog Box](../../2014/integration-services/package-and-project-protection-level-dialog-box.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20303-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="20303-128">See Also</span></span>  
 <span data-ttu-id="20303-129">[Guardar copia del paquete](../../2014/integration-services/save-copy-of-package.md) </span><span class="sxs-lookup"><span data-stu-id="20303-129">[Save Copy of Package](../../2014/integration-services/save-copy-of-package.md) </span></span>  
 <span data-ttu-id="20303-130">[Referencia de la interfaz de usuario del cuadro de diálogo Importar paquete](../../2014/integration-services/import-package-dialog-box-ui-reference.md) </span><span class="sxs-lookup"><span data-stu-id="20303-130">[Import Package Dialog Box UI Reference](../../2014/integration-services/import-package-dialog-box-ui-reference.md) </span></span>  
 <span data-ttu-id="20303-131">[Guardar paquetes](save-packages.md) </span><span class="sxs-lookup"><span data-stu-id="20303-131">[Save Packages](save-packages.md) </span></span>  
 [<span data-ttu-id="20303-132">Importar y exportar paquetes &#40;servicio SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="20303-132">Import and Export Packages &#40;SSIS Service&#41;</span></span>](../../2014/integration-services/import-and-export-packages-ssis-service.md)  
  
  
