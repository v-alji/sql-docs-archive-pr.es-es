---
title: Implementar una extensión de procesamiento de datos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- data processing extensions [Reporting Services], deploying
- Extension element
- deploying [Reporting Services], extensions
ms.assetid: e5c0b5a9-1386-47cb-aade-96653ecfaa54
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 84fc2d2853ce7a6aae77f313ef0f4026ad2f35cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750502"
---
# <a name="deploying-a-data-processing-extension"></a><span data-ttu-id="66e50-102">Implementar una extensión de procesamiento de datos</span><span class="sxs-lookup"><span data-stu-id="66e50-102">Deploying a Data Processing Extension</span></span>
  <span data-ttu-id="66e50-103">Después de escribir y compilar la extensión de procesamiento de datos de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] en una biblioteca de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], es necesario hacer que el servidor de informes y el Diseñador de informes la puedan detectar.</span><span class="sxs-lookup"><span data-stu-id="66e50-103">Once you have written and compiled your [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extension into a [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] library, you need to make it discoverable by the report server and by Report Designer.</span></span> <span data-ttu-id="66e50-104">Esto es tan fácil como copiar la extensión en los directorios adecuados y agregar entradas a los archivos de configuración de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] correspondientes.</span><span class="sxs-lookup"><span data-stu-id="66e50-104">This is as easy as copying the extension to the appropriate directories and adding entries to the appropriate [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] configuration files.</span></span>  
  
## <a name="configuration-file-extension-element"></a><span data-ttu-id="66e50-105">Elemento de extension de archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="66e50-105">Configuration-File Extension Element</span></span>  
 <span data-ttu-id="66e50-106">Las extensiones de procesamiento de datos que implementa en el servidor de informes o el Diseñador de informes tienen que escribirse como elementos **Extension** en los archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="66e50-106">Data processing extensions that you deploy to the report server or Report Designer need to be entered as **Extension** elements in the configuration files.</span></span> <span data-ttu-id="66e50-107">Estos archivos son RSReportServer.config para el servidor de informes y RSReportDesigner.config para el Diseñador de informes.</span><span class="sxs-lookup"><span data-stu-id="66e50-107">These files are RSReportServer.config for the report server and RSReportDesigner.config for Report Designer.</span></span>  
  
 <span data-ttu-id="66e50-108">En la tabla siguiente se describen los atributos del elemento **Extension** correspondientes a las extensiones de procesamiento de datos.</span><span class="sxs-lookup"><span data-stu-id="66e50-108">The following table describes the attributes for the **Extension** element for data processing extensions.</span></span>  
  
|<span data-ttu-id="66e50-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="66e50-109">Attribute</span></span>|<span data-ttu-id="66e50-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="66e50-110">Description</span></span>|  
|---------------|-----------------|  
|`Name`|<span data-ttu-id="66e50-111">Un nombre único para la extensión, por ejemplo "SQL" para la extensión de procesamiento de datos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] u "OLEDB" para la extensión de procesamiento de datos de OLE DB.</span><span class="sxs-lookup"><span data-stu-id="66e50-111">A unique name for the extension, for example, "SQL" for the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data processing extension or "OLEDB" for the OLE DB data processing extension.</span></span> <span data-ttu-id="66e50-112">La longitud máxima para el atributo `Name` es de 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="66e50-112">The maximum length for the `Name` attribute is 255 characters.</span></span> <span data-ttu-id="66e50-113">El nombre debe ser único entre todas las entradas en el elemento **Extension** del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="66e50-113">The name must be unique among all entries within the **Extension** element of a configuration file.</span></span>|  
|`Type`|<span data-ttu-id="66e50-114">Lista separada por comas que incluye el espacio de nombres completo junto con el nombre del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="66e50-114">A comma-separated list that includes the fully qualified namespace along with the name of the assembly.</span></span>|  
|`Visible`|<span data-ttu-id="66e50-115">El valor `false` indica que la extensión de procesamiento de datos no debería estar visible en las interfaces de usuario.</span><span class="sxs-lookup"><span data-stu-id="66e50-115">A value of `false` indicates that the data processing extension should not be visible in user interfaces.</span></span> <span data-ttu-id="66e50-116">Si el atributo no está incluido, el valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="66e50-116">If the attribute is not included, the default value is `true`.</span></span>|  
  
 <span data-ttu-id="66e50-117">Para más información sobre los archivos RSReportServer.config o RSReportDesigner.config, vea [Archivos de configuración de Reporting Services](../../report-server/reporting-services-configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="66e50-117">For more information about the RSReportServer.config or RSReportDesigner.config files, see [Reporting Services Configuration Files](../../report-server/reporting-services-configuration-files.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="66e50-118">En esta sección</span><span class="sxs-lookup"><span data-stu-id="66e50-118">In This Section</span></span>  
  
|<span data-ttu-id="66e50-119">Tema</span><span class="sxs-lookup"><span data-stu-id="66e50-119">Topic</span></span>|<span data-ttu-id="66e50-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="66e50-120">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="66e50-121">Procedimientos: Implementar una extensión de procesamiento de datos en un servidor de informes</span><span class="sxs-lookup"><span data-stu-id="66e50-121">How to: Deploy a Data Processing Extension to a Report Server</span></span>](deploying-a-data-processing-extension-to-a-report-server.md)|<span data-ttu-id="66e50-122">Describe cómo implementar la extensión de procesamiento de datos para un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="66e50-122">Describes how to deploy your data processing extension to a report server.</span></span>|  
|[<span data-ttu-id="66e50-123">Procedimientos: Implementar una extensión de procesamiento de datos en el Diseñador de informes</span><span class="sxs-lookup"><span data-stu-id="66e50-123">How to: Deploy a Data Processing Extension to Report Designer</span></span>](deploying-a-data-processing-extension-to-report-designer.md)|<span data-ttu-id="66e50-124">Describe cómo implementar la extensión de procesamiento de datos para el Diseñador de informes.</span><span class="sxs-lookup"><span data-stu-id="66e50-124">Describes how to deploy your data processing extension to Report Designer.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="66e50-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="66e50-125">See Also</span></span>  
 <span data-ttu-id="66e50-126">[Extensiones de Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="66e50-126">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="66e50-127">[Implementar una extensión de procesamiento de datos](implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="66e50-127">[Implementing a Data Processing Extension](implementing-a-data-processing-extension.md) </span></span>  
 [<span data-ttu-id="66e50-128">Biblioteca de extensiones de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="66e50-128">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
