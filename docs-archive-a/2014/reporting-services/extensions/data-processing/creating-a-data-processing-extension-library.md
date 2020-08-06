---
title: Crear una biblioteca de extensión de procesamiento de datos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- data processing extensions [Reporting Services], namespace assignments
- library [Reporting Services]
- assigning namespaces to extensions
ms.assetid: 82f4b71b-dd39-467d-8d8c-6771eb2b12de
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a3c14ed699e94c7d8ed0f6f3d727e9ba6e355b7e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751929"
---
# <a name="creating-a-data-processing-extension-library"></a><span data-ttu-id="2719b-102">Crear una biblioteca de extensión de procesamiento de datos</span><span class="sxs-lookup"><span data-stu-id="2719b-102">Creating a Data Processing Extension Library</span></span>
  <span data-ttu-id="2719b-103">Cada extensión de procesamiento de datos de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] que cree debe tener asignado un espacio de nombres único e integrarse en un archivo de ensamblado o biblioteca.</span><span class="sxs-lookup"><span data-stu-id="2719b-103">Each [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extension you create should be assigned to a unique namespace and built into a library or assembly file.</span></span> <span data-ttu-id="2719b-104">El nombre exacto del espacio de nombres no es importante, pero debe ser único y no compartirse con ninguna otra extensión.</span><span class="sxs-lookup"><span data-stu-id="2719b-104">The exact name of the namespace is not important, but it must be unique and not shared with any other extension.</span></span> [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="2719b-105">utiliza el espacio de nombres <xref:Microsoft.ReportingServices.DataProcessing> para las extensiones de procesamiento de datos que se incluyen con [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2719b-105">uses the namespace <xref:Microsoft.ReportingServices.DataProcessing> for the data processing extensions that ship with [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="2719b-106">Debería crear sus propios espacios de nombres únicos para las extensiones de procesamiento de datos de su compañía.</span><span class="sxs-lookup"><span data-stu-id="2719b-106">You should create your own unique namespaces for your company's data processing extensions.</span></span>  
  
 <span data-ttu-id="2719b-107">En el ejemplo siguiente se muestra el código para iniciar una extensión de procesamiento de datos de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] que utiliza los espacios de nombres que contienen las interfaces de procesamiento de datos y algunas clases de utilidades.</span><span class="sxs-lookup"><span data-stu-id="2719b-107">The following example shows the code to begin a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extension, which uses the namespaces that contain the data processing interfaces and any utility classes.</span></span>  
  
```vb  
Imports System  
Imports Microsoft.ReportingServices.DataProcessing  
Imports Microsoft.ReportingServices.Interfaces  
  
Namespace CompanyName.ExtensionName  
   ...  
```  
  
```csharp  
using System;  
using Microsoft.ReportingServices.DataProcessing;  
using Microsoft.ReportingServices.Interfaces;  
  
namespace CompanyName.ExtensionName  
{  
   ...  
```  
  
 <span data-ttu-id="2719b-108">Al compilar una extensión de procesamiento de datos de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], debe proporcionar al compilador una referencia a Microsoft.ReportingServices.Interfaces.dll, porque allí están contenidas las interfaces de extensión de procesamiento de datos.</span><span class="sxs-lookup"><span data-stu-id="2719b-108">When compiling a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extension, you must supply to the compiler a reference to Microsoft.ReportingServices.Interfaces.dll, because the data processing extension interfaces are contained there.</span></span> <span data-ttu-id="2719b-109">El espacio de nombres <xref:Microsoft.ReportingServices.DataProcessing> es necesario para implementar las interfaces de extensión de procesamiento de datos mientras que el espacio de nombres <xref:Microsoft.ReportingServices.Interfaces> es necesario para implementar la interfaz <xref:Microsoft.ReportingServices.Interfaces.IExtension>.</span><span class="sxs-lookup"><span data-stu-id="2719b-109">The <xref:Microsoft.ReportingServices.DataProcessing> namespace is needed to implement the data processing extension interfaces, and the <xref:Microsoft.ReportingServices.Interfaces> namespace is needed to implement the <xref:Microsoft.ReportingServices.Interfaces.IExtension> interface.</span></span> <span data-ttu-id="2719b-110">Por ejemplo, si todos los archivos que contienen el código para implementar una extensión de entrega de procesamiento de datos de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] escrita en C# estuvieran en un directorio único con la extensión .cs, el comando siguiente se ejecutaría desde ese directorio para compilar los archivos almacenados en CompanyName.ExtensionName.dll.</span><span class="sxs-lookup"><span data-stu-id="2719b-110">For example, if all the files containing the code to implement a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extension written in C# were in a single directory with the extension .cs, the following command would be issued from that directory to compile the files stored in CompanyName.ExtensionName.dll.</span></span>  
  
```csharp  
csc /t:library /out:CompanyName.ExtensionName.dll *.cs /r:System.dll /r:Microsoft.ReportingServices.Interfaces.dll  
```  
  
 <span data-ttu-id="2719b-111">En el ejemplo de código siguiente se muestra el comando que se usaría para los archivos de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] con la extensión .vb.</span><span class="sxs-lookup"><span data-stu-id="2719b-111">The following code example shows the command that would be used for [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] files with the extension .vb.</span></span>  
  
```vb  
vbc /t:library /out:CompanyName.ExtensionName.dll *.vb /r:System.dll /r:Microsoft.ReportingServices.Interfaces.dll  
```  
  
> [!NOTE]  
>  <span data-ttu-id="2719b-112">También puede diseñar, desarrollar y generar su extensión de procesamiento de datos mediante [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2719b-112">You can also design, develop, and build your data processing extension using [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="2719b-113">Para obtener más información sobre cómo desarrollar ensamblados en [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], vea la documentación de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2719b-113">For more information about developing assemblies in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], see your [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2719b-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2719b-114">See Also</span></span>  
 <span data-ttu-id="2719b-115">[Extensiones de Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="2719b-115">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="2719b-116">[Implementar una extensión de procesamiento de datos](implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="2719b-116">[Implementing a Data Processing Extension](implementing-a-data-processing-extension.md) </span></span>  
 [<span data-ttu-id="2719b-117">Biblioteca de extensiones de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="2719b-117">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
