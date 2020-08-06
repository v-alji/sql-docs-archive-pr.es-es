---
title: Guardar paquetes | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services packages, saving
- packages [Integration Services], saving
- saving packages
- SSIS packages, saving
- SQL Server Integration Services packages, saving
ms.assetid: 17c1de2c-637f-45c2-a148-79294bae0af4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 102e2c3eab001c230722bf3485d6ea9731aa99a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748834"
---
# <a name="save-packages"></a><span data-ttu-id="fe7c6-102">Guardar paquetes</span><span class="sxs-lookup"><span data-stu-id="fe7c6-102">Save Packages</span></span>
  <span data-ttu-id="fe7c6-103">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , se generan los paquetes con el Diseñador de [!INCLUDE[ssIS](../includes/ssis-md.md)] y se guardan en el sistema de archivos como archivos XML (archivos .dtsx).</span><span class="sxs-lookup"><span data-stu-id="fe7c6-103">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] you build packages by using [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer and save the packages to the file system as XML files (.dtsx files).</span></span> <span data-ttu-id="fe7c6-104">También puede guardar copias del archivo XML de paquete en la base de datos msdb, en [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , o en el almacén de paquetes.</span><span class="sxs-lookup"><span data-stu-id="fe7c6-104">You can also save copies of the package XML file to the msdb database in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] or to the package store.</span></span> <span data-ttu-id="fe7c6-105">El almacén de paquetes representa las carpetas en la ubicación del sistema de archivos que el servicio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] administra.</span><span class="sxs-lookup"><span data-stu-id="fe7c6-105">The package store represents the folders in the file system location that the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service manages.</span></span>  
  
 <span data-ttu-id="fe7c6-106">Si guarda un paquete en el sistema de archivos, puede usar más tarde el servicio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] para importar el paquete a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] o al almacén de paquetes.</span><span class="sxs-lookup"><span data-stu-id="fe7c6-106">If you save a package to the file system, you can later use the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service to import the package to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] or to the package store.</span></span> <span data-ttu-id="fe7c6-107">Para más información, vea [Importar y exportar paquetes servicio &#40;SSIS&#41;](../../2014/integration-services/import-and-export-packages-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="fe7c6-107">For more information, see [Import and Export Packages &#40;SSIS Service&#41;](../../2014/integration-services/import-and-export-packages-ssis-service.md).</span></span>  
  
 <span data-ttu-id="fe7c6-108">También puede usar una utilidad de símbolo del sistema, **dtutil**, para copiar un paquete entre el sistema de archivos y msdb.</span><span class="sxs-lookup"><span data-stu-id="fe7c6-108">You can also use a command prompt utility, **dtutil**, to copy a package between the file system and msdb.</span></span> <span data-ttu-id="fe7c6-109">Para más información, consulte [dtutil Utility](dtutil-utility.md).</span><span class="sxs-lookup"><span data-stu-id="fe7c6-109">For more information, see [dtutil Utility](dtutil-utility.md).</span></span>  
  
### <a name="to-save-a-package"></a><span data-ttu-id="fe7c6-110">Para guardar un paquete</span><span class="sxs-lookup"><span data-stu-id="fe7c6-110">To save a package</span></span>  
  
-   [<span data-ttu-id="fe7c6-111">Guardar un paquete en el sistema de archivos</span><span class="sxs-lookup"><span data-stu-id="fe7c6-111">Save a Package to the File System</span></span>](../../2014/integration-services/save-a-package-to-the-file-system.md)  
  
-   [<span data-ttu-id="fe7c6-112">Guardar una copia de un paquete</span><span class="sxs-lookup"><span data-stu-id="fe7c6-112">Save a Copy of a Package</span></span>](../../2014/integration-services/save-a-copy-of-a-package.md)  
  
  
