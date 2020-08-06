---
title: Instalación de Microsoft Connector para 1,1 SAP BW | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 3bfb9023-9597-4f59-9085-4b9057e7702e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0ef96f38054f04e71de72bda0bbb12f8f003ef20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672179"
---
# <a name="installing-the-microsoft-connector-for-11-sap-bw"></a><span data-ttu-id="28ea4-102">Instalar Microsoft Connector for 1.1 SAP BW</span><span class="sxs-lookup"><span data-stu-id="28ea4-102">Installing the Microsoft Connector for 1.1 SAP BW</span></span>
  <span data-ttu-id="28ea4-103">Para instalar el [!INCLUDE[msCoName](../includes/msconame-md.md)] conector 1,1 para SAP BW y su documentación, descargue y ejecute el paquete de Windows Installer desde la página web del Feature Pack de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="28ea4-103">To install the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW and its documentation, download and run the Windows installer package from the SQL Server Feature Pack Web page.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="28ea4-104">La documentación de Microsoft Connector 1.1 for SAP BW da por supuesto que se está familiarizado con el entorno SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="28ea4-104">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="28ea4-105">Para obtener más información acerca de SAP Netweaver BW, o sobre cómo configurar los objetos y los procesos de SAP Netweaver BW, vea la documentación de SAP.</span><span class="sxs-lookup"><span data-stu-id="28ea4-105">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="28ea4-106">La extracción de datos de SAP Netweaver BW requiere una licencia SAP adicional.</span><span class="sxs-lookup"><span data-stu-id="28ea4-106">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="28ea4-107">Póngase en contacto con SAP para comprobar estos requisitos.</span><span class="sxs-lookup"><span data-stu-id="28ea4-107">Check with SAP to verify these requirements.</span></span>  
  
## <a name="required-sap-files"></a><span data-ttu-id="28ea4-108">Archivos necesarios de SAP</span><span class="sxs-lookup"><span data-stu-id="28ea4-108">Required SAP Files</span></span>  
 <span data-ttu-id="28ea4-109">Para usar el [!INCLUDE[msCoName](../includes/msconame-md.md)] conector 1,1 para SAP BW, no tiene que instalar el software de SAP front end (GUI de SAP) en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="28ea4-109">To use the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW, you do not have to install the SAP Front End software (SAP GUI) on the local computer.</span></span>  
  
 <span data-ttu-id="28ea4-110">Sin embargo, debe copiar el archivo del conector .NET de SAP, librfc32.dll, en la subcarpeta del sistema de la carpeta Windows.</span><span class="sxs-lookup"><span data-stu-id="28ea4-110">However you must copy the SAP .NET connector file, librfc32.dll, into the system subfolder in the Windows folder.</span></span> <span data-ttu-id="28ea4-111">(Normalmente, la ubicación de esta carpeta es **C:\Windows\system32**).</span><span class="sxs-lookup"><span data-stu-id="28ea4-111">(Typically, this folder location is **C:\Windows\system32**.)</span></span>  
  
## <a name="considerations-for-64-bit-computers"></a><span data-ttu-id="28ea4-112">Consideraciones para equipos de 64 bits</span><span class="sxs-lookup"><span data-stu-id="28ea4-112">Considerations for 64-bit Computers</span></span>  
 <span data-ttu-id="28ea4-113">El [!INCLUDE[msCoName](../includes/msconame-md.md)] conector 1,1 para SAP BW es totalmente compatible con la versión de 64 bits de [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="28ea4-113">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW fully supports the 64-bit version of [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows.</span></span> <span data-ttu-id="28ea4-114">En un equipo de 64 bits, el [!INCLUDE[msCoName](../includes/msconame-md.md)] conector 1,1 para SAP BW tiene los siguientes requisitos adicionales:</span><span class="sxs-lookup"><span data-stu-id="28ea4-114">On a 64-bit computer, the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW has the following additional requirements:</span></span>  
  
-   <span data-ttu-id="28ea4-115">Para ejecutar paquetes en modo de 64 bits en cualquier sistema operativo Windows de 64 bits, copie la versión de 64 bits del archivo de la GUI de SAP, librfc32.dll, a la carpeta **system32** de la carpeta Windows.</span><span class="sxs-lookup"><span data-stu-id="28ea4-115">To run packages in 64-bit mode on any 64-bit Windows operating system, copy the 64-bit version of the SAP GUI file, librfc32.dll, into the **system32** folder of the Windows folder.</span></span> <span data-ttu-id="28ea4-116">(Normalmente, la ubicación de este archivo es **C:\Windows\system32**).</span><span class="sxs-lookup"><span data-stu-id="28ea4-116">(Typically, this file location is **C:\Windows\system32**.)</span></span>  
  
-   <span data-ttu-id="28ea4-117">Para ejecutar paquetes en modo de 32 bits en cualquier sistema operativo Windows de 64 bits, copie el archivo de la GUI de SAP, librfc32.dll, a la carpeta **SysWow64** de la carpeta Windows.</span><span class="sxs-lookup"><span data-stu-id="28ea4-117">To run packages in 32-bit mode on any 64-bit Windows operating system, copy the SAP GUI file, librfc32.dll, into the **SysWow64** folder of the Windows folder.</span></span> <span data-ttu-id="28ea4-118">(Normalmente, la ubicación de esta carpeta es **C:\Windows\SysWow64**).</span><span class="sxs-lookup"><span data-stu-id="28ea4-118">(Typically, this folder location is **C:\Windows\SysWow64**.)</span></span>  
  
  
