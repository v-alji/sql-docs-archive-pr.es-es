---
title: Crear una biblioteca de extensiones de entrega | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- delivery extensions [Reporting Services], namespace assignments
- library [Reporting Services]
- assigning namespaces to extensions
ms.assetid: 63b32f93-4bab-4b07-bd72-39a47aca1cda
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c9891c2b0c1bb9c7d495b3ab1f8f2267ce04b79f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750469"
---
# <a name="creating-a-delivery-extension-library"></a><span data-ttu-id="f608f-102">Crear la biblioteca de una extensión de entrega</span><span class="sxs-lookup"><span data-stu-id="f608f-102">Creating a Delivery Extension Library</span></span>
  <span data-ttu-id="f608f-103">Cada extensión de entrega de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] que cree debería tener asignado un espacio de nombres único e integrarse en archivo de ensamblado o biblioteca.</span><span class="sxs-lookup"><span data-stu-id="f608f-103">Each [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension you create should be assigned to a unique namespace and built into a library or assembly file.</span></span> <span data-ttu-id="f608f-104">El nombre exacto del espacio de nombres no es importante, pero debe ser único y no compartirse con ninguna otra extensión.</span><span class="sxs-lookup"><span data-stu-id="f608f-104">The exact name of the namespace is not important, but it must be unique and not shared with any other extension.</span></span> <span data-ttu-id="f608f-105">Debería crear sus propios espacios de nombres únicos para las extensiones de entrega de su compañía.</span><span class="sxs-lookup"><span data-stu-id="f608f-105">You should create your own unique namespaces for your company's delivery extensions.</span></span>  
  
 <span data-ttu-id="f608f-106">En el ejemplo siguiente se muestra el código para comenzar una extensión de entrega [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], que utiliza los espacios de nombres que contienen las interfaces de entrega y alguna clase de utilidades.</span><span class="sxs-lookup"><span data-stu-id="f608f-106">The following example shows the code to begin a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension, which uses the namespaces that contain the delivery interfaces and any utility classes.</span></span>  
  
```vb  
Imports System  
Imports Microsoft.ReportingServices.Interfaces  
  
Namespace CompanyName.ExtensionName  
   ...  
```  
  
```csharp  
using System;  
using Microsoft.ReportingServices.Interfaces;  
  
namespace CompanyName.ExtensionName  
{  
   ...  
```  
  
 <span data-ttu-id="f608f-107">Al compilar una extensión de entrega de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], debe proporcionar al compilador una referencia a Microsoft.ReportingServices.Interfaces.dll, porque allí se encuentran las interfaces de extensión de entrega y las clases.</span><span class="sxs-lookup"><span data-stu-id="f608f-107">When compiling a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension, you must supply to the compiler a reference to Microsoft.ReportingServices.Interfaces.dll, because the delivery extension interfaces and classes are contained there.</span></span> <span data-ttu-id="f608f-108">El espacio de nombres <xref:Microsoft.ReportingServices.Interfaces> es necesario para implementar la interfaz <xref:Microsoft.ReportingServices.Interfaces.IExtension>, la interfaz <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> y más.</span><span class="sxs-lookup"><span data-stu-id="f608f-108">The <xref:Microsoft.ReportingServices.Interfaces> namespace is needed to implement the <xref:Microsoft.ReportingServices.Interfaces.IExtension> interface, the <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> interface, and more.</span></span> <span data-ttu-id="f608f-109">Por ejemplo, si todos los archivos que contienen el código para implementar una extensión de entrega de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] escrita en C# estuvieran en un único directorio con la extensión .cs, el comando siguiente se ejecutaría desde ese directorio para compilar los archivos almacenados en CompanyName.ExtensionName.dll.</span><span class="sxs-lookup"><span data-stu-id="f608f-109">For example, if all the files containing the code to implement a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension written in C# were in a single directory with the extension .cs, the following command would be issued from that directory to compile the files stored in CompanyName.ExtensionName.dll.</span></span>  
  
```csharp  
csc /t:library /out:CompanyName.ExtensionName.dll *.cs /r:System.dll   
/r:Microsoft.ReportingServices.Interfaces.dll  
```  
  
 <span data-ttu-id="f608f-110">En el ejemplo de código siguiente se muestra el comando que se usaría para los archivos de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] con la extensión .vb.</span><span class="sxs-lookup"><span data-stu-id="f608f-110">The following code example shows the command that would be used for [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] files with the extension .vb.</span></span>  
  
```vb  
vbc /t:library /out:CompanyName.ExtensionName.dll *.vb /r:System.dll   
/r:Microsoft.ReportingServices.Interfaces.dll  
```  
  
> [!NOTE]  
>  <span data-ttu-id="f608f-111">También puede diseñar, desarrollar y generar su extensión de entrega mediante [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f608f-111">You can also design, develop, and build your delivery extension using [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="f608f-112">Para obtener más información sobre cómo desarrollar ensamblados en [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], vea la documentación de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f608f-112">For more information about developing assemblies in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], see your [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f608f-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f608f-113">See Also</span></span>  
 <span data-ttu-id="f608f-114">[Extensiones de Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="f608f-114">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="f608f-115">[Implementar una extensión de entrega](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="f608f-115">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="f608f-116">Biblioteca de extensiones de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="f608f-116">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
