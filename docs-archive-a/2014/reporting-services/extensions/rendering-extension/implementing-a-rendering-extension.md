---
title: Implementar una extensión de representación | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- rendering extensions [Reporting Services]
- custom rendering extensions [Reporting Services]
- transformations [Reporting Services]
- extensions [Reporting Services], rendering
- rendering extensions [Reporting Services], implementing
ms.assetid: 4a5c64f5-2391-4597-ba3f-81d265b23703
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 03deb7c818de8d875f69b585ae6015fc178e707d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673526"
---
# <a name="implementing-a-rendering-extension"></a><span data-ttu-id="3b6ed-102">Implementar una extensión de representación</span><span class="sxs-lookup"><span data-stu-id="3b6ed-102">Implementing a Rendering Extension</span></span>
  <span data-ttu-id="3b6ed-103">Una extensión de representación es un componente o módulo de un servidor de informes que transforma los datos de informes y la información de diseño en un formato específico del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3b6ed-103">A rendering extension is a component or module of a report server that transforms report data and layout information into a device-specific format.</span></span> <span data-ttu-id="3b6ed-104">Reporting Services de SQL Server incluye seis extensiones de representación: HTML, Excel, Word, CSV o Text, XML, Image y PDF.</span><span class="sxs-lookup"><span data-stu-id="3b6ed-104">SQL Server Reporting Services includes six rendering extensions: HTML, Excel, Word, CSV or Text, XML, Image, and PDF.</span></span> <span data-ttu-id="3b6ed-105">Puede crear extensiones de representación adicionales para generar informes en otros formatos.</span><span class="sxs-lookup"><span data-stu-id="3b6ed-105">You can create additional rendering extensions to generate reports in other formats.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3b6ed-106">Para determinar qué extensiones de representación están disponibles, puede ver la lista de extensiones instaladas en el archivo RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="3b6ed-106">To determine which rendering extensions are available, you can view the list of installed extensions in the RSReportServer.config file.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3b6ed-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="3b6ed-107">In This Section</span></span>  
 [<span data-ttu-id="3b6ed-108">Información general de las extensiones de representación</span><span class="sxs-lookup"><span data-stu-id="3b6ed-108">Rendering Extensions Overview</span></span>](rendering-extensions-overview.md)  
 <span data-ttu-id="3b6ed-109">Explica cómo escribir una extensión de representación personalizada para [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b6ed-109">Introduces how to write a custom rendering extension for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="3b6ed-110">Ejecución de la interfaz IRenderingExtension</span><span class="sxs-lookup"><span data-stu-id="3b6ed-110">Implementing the IRenderingExtension Interface</span></span>](implementing-the-irenderingextension-interface.md)  
 <span data-ttu-id="3b6ed-111">Describe los atributos de una extensión de representación.</span><span class="sxs-lookup"><span data-stu-id="3b6ed-111">Describes the attributes of a rendering extension.</span></span>  
  
 [<span data-ttu-id="3b6ed-112">Implementación de una extensión de representación</span><span class="sxs-lookup"><span data-stu-id="3b6ed-112">Deploying a Rendering Extension</span></span>](deploying-a-rendering-extension.md)  
 <span data-ttu-id="3b6ed-113">Describe cómo implementar una extensión de representación en un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="3b6ed-113">Describes how to deploy a rendering extension on a report server.</span></span>  
  
 [<span data-ttu-id="3b6ed-114">Eliminación de una extensión de representación</span><span class="sxs-lookup"><span data-stu-id="3b6ed-114">Removing a Rendering Extension</span></span>](removing-a-rendering-extension.md)  
 <span data-ttu-id="3b6ed-115">Describe cómo quitar una extensión de representación de un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="3b6ed-115">Describes how to remove a rendering extension from a report server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b6ed-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3b6ed-116">See Also</span></span>  
 <span data-ttu-id="3b6ed-117">[Extensiones de Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="3b6ed-117">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 [<span data-ttu-id="3b6ed-118">Biblioteca de extensiones de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="3b6ed-118">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
