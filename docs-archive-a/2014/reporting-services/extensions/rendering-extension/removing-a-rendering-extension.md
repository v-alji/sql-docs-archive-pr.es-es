---
title: Quitar una extensión de representación | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- deleting rendering extensions
- removing rendering extensions
- rendering extensions [Reporting Services], removing
ms.assetid: 2abfebfb-065f-45cc-a904-c914394cf900
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 77a8a9ac44b35f338f978913985617e4f264ddb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673524"
---
# <a name="removing-a-rendering-extension"></a><span data-ttu-id="034d5-102">Quitar una extensión de representación</span><span class="sxs-lookup"><span data-stu-id="034d5-102">Removing a Rendering Extension</span></span>
  <span data-ttu-id="034d5-103">Para quitar una [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] extensión de representación, solo tiene que quitar el elemento de la `Extension` extensión de representación del archivo rsreportserver.config, ubicado en **%programfiles%\microsoft SQL Server \ MSRS10_50. \<Instance Name> \Reporting Services\ReportServer** .</span><span class="sxs-lookup"><span data-stu-id="034d5-103">To remove a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] rendering extension, simply remove the `Extension` element for your rendering extension from the rsreportserver.config file, located in **%ProgramFiles%\Microsoft SQL Server\MSRS10_50.\<Instance Name>\Reporting Services\ReportServer** folder.</span></span> <span data-ttu-id="034d5-104">Si ha realizado entradas para un Diseñador de informes, así como un servidor de informes, quite `Extension` también el elemento del [archivo de configuración RSReportDesigner](../../report-server/rsreportdesigner-configuration-file.md) .</span><span class="sxs-lookup"><span data-stu-id="034d5-104">If you made entries for a Report Designer as well as a report server, remove the `Extension` element from the [RSReportDesigner Configuration File](../../report-server/rsreportdesigner-configuration-file.md) as well.</span></span> <span data-ttu-id="034d5-105">Después de quitar la información de configuración, la extensión de representación de datos ya no estará disponible en el componente.</span><span class="sxs-lookup"><span data-stu-id="034d5-105">After the configuration information is removed, the rendering extension is no longer available to the component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="034d5-106">Consulte también</span><span class="sxs-lookup"><span data-stu-id="034d5-106">See Also</span></span>  
 <span data-ttu-id="034d5-107">[Archivos de configuración de Reporting Services](../../report-server/reporting-services-configuration-files.md) </span><span class="sxs-lookup"><span data-stu-id="034d5-107">[Reporting Services Configuration Files](../../report-server/reporting-services-configuration-files.md) </span></span>  
 <span data-ttu-id="034d5-108">[Implementar una extensión de representación](implementing-a-rendering-extension.md) </span><span class="sxs-lookup"><span data-stu-id="034d5-108">[Implementing a Rendering Extension](implementing-a-rendering-extension.md) </span></span>  
 <span data-ttu-id="034d5-109">[Información general de las extensiones de representación](rendering-extensions-overview.md) </span><span class="sxs-lookup"><span data-stu-id="034d5-109">[Rendering Extensions Overview](rendering-extensions-overview.md) </span></span>  
 <span data-ttu-id="034d5-110">[Implementar la interfaz IRenderingExtension](implementing-the-irenderingextension-interface.md) </span><span class="sxs-lookup"><span data-stu-id="034d5-110">[Implementing the IRenderingExtension Interface](implementing-the-irenderingextension-interface.md) </span></span>  
 <span data-ttu-id="034d5-111">[Consideraciones de seguridad para las extensiones](../security-considerations-for-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="034d5-111">[Security Considerations for Extensions](../security-considerations-for-extensions.md) </span></span>  
 [<span data-ttu-id="034d5-112">Implementación de una extensión de representación</span><span class="sxs-lookup"><span data-stu-id="034d5-112">Deploying a Rendering Extension</span></span>](deploying-a-rendering-extension.md)  
  
  
