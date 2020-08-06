---
title: Referencia de la biblioteca de proveedores WMI de Reporting Services (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- Reporting Services WMI Provider Library
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- WMI provider [Reporting Services], library
ms.assetid: 17ba711d-7eff-4423-9168-63dc425a3428
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2a98ca22f9d34627e484a698dcf540b31808d07e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671885"
---
# <a name="reporting-services-wmi-provider-library-reference-ssrs"></a><span data-ttu-id="bac73-102">Referencia de la biblioteca de proveedores WMI de Reporting Services (SSRS)</span><span class="sxs-lookup"><span data-stu-id="bac73-102">Reporting Services WMI Provider Library Reference (SSRS)</span></span>
  <span data-ttu-id="bac73-103">El proveedor de Instrumental de administración de Windows (WMI) [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] admite operaciones de WMI que le permiten escribir scripts y código para modificar la configuración del servidor de informes y del Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="bac73-103">The [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Windows Management Instrumentation (WMI) provider supports WMI operations that enable you to write scripts and code to modify settings of the report server and Report Manager.</span></span>  
  
 <span data-ttu-id="bac73-104">Por ejemplo, si quiere cambiar si se usará la seguridad integrada cuando el servidor de informes se conecte a la base de datos del servidor de informes, cree una instancia de la clase MSReportServer_ConfigurationSetting y use la propiedad DatabaseIntegratedSecurity de la instancia del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="bac73-104">For example, if you want to change whether integrated security is used when the report server connects to the report server database, create an instance of the MSReportServer_ConfigurationSetting class and use the DatabaseIntegratedSecurity property of the of the report server instance.</span></span> <span data-ttu-id="bac73-105">Las clases que se muestran en la tabla siguiente representan los componentes  de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bac73-105">The classes shown in the following table represent [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] components.</span></span> <span data-ttu-id="bac73-106">Las clases se definen en los espacios de nombres [!INCLUDE[ssRSWMInmspc](../../includes/ssrswminmspc-md.md)] o [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bac73-106">The classes are defined in either the [!INCLUDE[ssRSWMInmspc](../../includes/ssrswminmspc-md.md)] or the [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)] namespaces.</span></span> <span data-ttu-id="bac73-107">Cada una de las clases admite las operaciones de la lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="bac73-107">Each of the classes support read and write operations.</span></span> <span data-ttu-id="bac73-108">Las operaciones de creación no se admiten.</span><span class="sxs-lookup"><span data-stu-id="bac73-108">Create operations are not supported.</span></span>  
  
## <a name="classes"></a><span data-ttu-id="bac73-109">Clases</span><span class="sxs-lookup"><span data-stu-id="bac73-109">Classes</span></span>  
 [<span data-ttu-id="bac73-110">MSReportServer_Instance, clase</span><span class="sxs-lookup"><span data-stu-id="bac73-110">MSReportServer_Instance Class</span></span>](msreportserver-instance-class.md)  
 <span data-ttu-id="bac73-111">Proporciona la información básica requerida para que un cliente se conecte a un servidor de informes instalado.</span><span class="sxs-lookup"><span data-stu-id="bac73-111">Provides basic information required for a client to connect to an installed report server.</span></span>  
  
 [<span data-ttu-id="bac73-112">Clase MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="bac73-112">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
 <span data-ttu-id="bac73-113">Representa la instalación y los parámetros de tiempo de ejecución de una instancia del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="bac73-113">Represents the installation and run-time parameters of a report server instance.</span></span> <span data-ttu-id="bac73-114">Estos parámetros se guardan en el archivo de configuración del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="bac73-114">These parameters are stored in the configuration file for the report server.</span></span>  
  
 <span data-ttu-id="bac73-115">Para obtener más información acerca de las operaciones WMI, vea la documentación del SDK de WMI que se incluye con el [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK.</span><span class="sxs-lookup"><span data-stu-id="bac73-115">For more information about WMI operations, see the WMI SDK documentation included with the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bac73-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bac73-116">See Also</span></span>  
 <span data-ttu-id="bac73-117">[Acceder al proveedor de Reporting Services WMI](../tools/access-the-reporting-services-wmi-provider.md) </span><span class="sxs-lookup"><span data-stu-id="bac73-117">[Access the Reporting Services WMI Provider](../tools/access-the-reporting-services-wmi-provider.md) </span></span>  
 [<span data-ttu-id="bac73-118">Referencia técnica &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="bac73-118">Technical Reference &#40;SSRS&#41;</span></span>](../technical-reference-ssrs.md)  
  
  
