---
title: Propiedad Detail | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Detail property
- SoapException class
ms.assetid: c1ddaeb6-c540-49fa-b06e-b6359d377ee8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 060fbaba2b8d4f5a5171e8aa7995432622ba2ba0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747457"
---
# <a name="detail-property"></a><span data-ttu-id="af474-102">Propiedad Detail</span><span class="sxs-lookup"><span data-stu-id="af474-102">Detail Property</span></span>
  <span data-ttu-id="af474-103">La propiedad **Detail** de la clase [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] **SoapException** de  tiene la estructura XML siguiente:</span><span class="sxs-lookup"><span data-stu-id="af474-103">The **Detail** property of the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] **SoapException** class has the following XML structure:</span></span>  
  
## <a name="elements"></a><span data-ttu-id="af474-104">Elementos</span><span class="sxs-lookup"><span data-stu-id="af474-104">Elements</span></span>  
 <span data-ttu-id="af474-105">**Detail**</span><span class="sxs-lookup"><span data-stu-id="af474-105">**Detail**</span></span>  
 <span data-ttu-id="af474-106">Elemento de nivel superior que contiene todos los demás elementos de detalle de error.</span><span class="sxs-lookup"><span data-stu-id="af474-106">The top-level element that contains all other error detail elements.</span></span>  
  
 <span data-ttu-id="af474-107">**ErrorCode**</span><span class="sxs-lookup"><span data-stu-id="af474-107">**ErrorCode**</span></span>  
 <span data-ttu-id="af474-108">Código de error específico de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af474-108">The [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]-specific error code.</span></span>  
  
 <span data-ttu-id="af474-109">**HttpStatus**</span><span class="sxs-lookup"><span data-stu-id="af474-109">**HttpStatus**</span></span>  
 <span data-ttu-id="af474-110">Código de estado HTTP.</span><span class="sxs-lookup"><span data-stu-id="af474-110">The HTTP status code.</span></span>  
  
 <span data-ttu-id="af474-111">**Message**</span><span class="sxs-lookup"><span data-stu-id="af474-111">**Message**</span></span>  
 <span data-ttu-id="af474-112">Mensaje de error y código de error asignados por el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="af474-112">The error message and the error code assigned by the report server.</span></span>  
  
 <span data-ttu-id="af474-113">**HelpLink**</span><span class="sxs-lookup"><span data-stu-id="af474-113">**HelpLink**</span></span>  
 <span data-ttu-id="af474-114">Dirección URL del vínculo de Ayuda a un sitio web en el que se puede encontrar más información sobre el error.</span><span class="sxs-lookup"><span data-stu-id="af474-114">The Help link URL to a Web site at which further information about the error can be found.</span></span> <span data-ttu-id="af474-115">Para más información, vea [Elemento HelpLink](helplink-element.md).</span><span class="sxs-lookup"><span data-stu-id="af474-115">For more information, see [HelpLink Element](helplink-element.md).</span></span>  
  
 <span data-ttu-id="af474-116">**LinkID**</span><span class="sxs-lookup"><span data-stu-id="af474-116">**LinkID**</span></span>  
 <span data-ttu-id="af474-117">Identificador asignado al vínculo.</span><span class="sxs-lookup"><span data-stu-id="af474-117">The ID assigned to the link.</span></span>  
  
 <span data-ttu-id="af474-118">**NombreDeProducto**</span><span class="sxs-lookup"><span data-stu-id="af474-118">**ProductName**</span></span>  
 <span data-ttu-id="af474-119">Nombre del producto.</span><span class="sxs-lookup"><span data-stu-id="af474-119">The name of the product.</span></span> <span data-ttu-id="af474-120">El valor predeterminado es **Microsoft SQL Server Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="af474-120">The default value is **Microsoft SQL Server Reporting Services**.</span></span>  
  
 <span data-ttu-id="af474-121">**ProductVersion**</span><span class="sxs-lookup"><span data-stu-id="af474-121">**ProductVersion**</span></span>  
 <span data-ttu-id="af474-122">Versión de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af474-122">The version of [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="af474-123">La longitud máxima es de 15 caracteres.</span><span class="sxs-lookup"><span data-stu-id="af474-123">The maximum length is 15 characters.</span></span> <span data-ttu-id="af474-124">El formato del número de versión debería ser como sigue: 8.00.0xxx.00.</span><span class="sxs-lookup"><span data-stu-id="af474-124">The format of the version number should be as follows: 8.00.0xxx.00.</span></span>  
  
 <span data-ttu-id="af474-125">**ProductLocaleId**</span><span class="sxs-lookup"><span data-stu-id="af474-125">**ProductLocaleId**</span></span>  
 <span data-ttu-id="af474-126">Identificador de configuración regional o de idioma de la DLL INTL de la aplicación (por ejemplo, 0x41A).</span><span class="sxs-lookup"><span data-stu-id="af474-126">The locale ID or language ID of the application's INTL DLL (for example, 0x41A).</span></span>  
  
 <span data-ttu-id="af474-127">**Identifica**</span><span class="sxs-lookup"><span data-stu-id="af474-127">**OperatingSystem**</span></span>  
 <span data-ttu-id="af474-128">Sistema operativo en el que está instalado [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af474-128">The operating system [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] is installed on.</span></span> <span data-ttu-id="af474-129">Los valores válidos incluyen **0** para un sistema operativo independiente, **1** para [!INCLUDE[win2kfamily](../../../includes/win2kfamily-md.md)] y **16** para Windows XP.</span><span class="sxs-lookup"><span data-stu-id="af474-129">Valid values include **0** for operating system independent, **1** for [!INCLUDE[win2kfamily](../../../includes/win2kfamily-md.md)], and **16** for Windows XP.</span></span>  
  
 <span data-ttu-id="af474-130">**CountryLocaleId**</span><span class="sxs-lookup"><span data-stu-id="af474-130">**CountryLocaleId**</span></span>  
 <span data-ttu-id="af474-131">Identificador de configuración regional o de idioma del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="af474-131">The locale ID or language ID of the operating system.</span></span> <span data-ttu-id="af474-132">Por ejemplo, el valor correspondiente a la versión en francés de Windows es 0x040c.</span><span class="sxs-lookup"><span data-stu-id="af474-132">For example, the value for the French version of Windows is 0x040c.</span></span>  
  
 <span data-ttu-id="af474-133">**MoreInformation**</span><span class="sxs-lookup"><span data-stu-id="af474-133">**MoreInformation**</span></span>  
 <span data-ttu-id="af474-134">Cadena XML que contiene las excepciones anidadas que se produjeron mientras el método se ejecutaba.</span><span class="sxs-lookup"><span data-stu-id="af474-134">An XML string that contains nested exceptions that occurred while the method ran.</span></span>  
  
 <span data-ttu-id="af474-135">**Origen**</span><span class="sxs-lookup"><span data-stu-id="af474-135">**Source**</span></span>  
 <span data-ttu-id="af474-136">Elemento secundario de **MoreInformation**.</span><span class="sxs-lookup"><span data-stu-id="af474-136">A child element of **MoreInformation**.</span></span> <span data-ttu-id="af474-137">Origen del error.</span><span class="sxs-lookup"><span data-stu-id="af474-137">The source of the error.</span></span>  
  
 <span data-ttu-id="af474-138">**Message**</span><span class="sxs-lookup"><span data-stu-id="af474-138">**Message**</span></span>  
 <span data-ttu-id="af474-139">Elemento secundario de **MoreInformation**.</span><span class="sxs-lookup"><span data-stu-id="af474-139">A child element of **MoreInformation**.</span></span> <span data-ttu-id="af474-140">Mensaje de error de una excepción anidada.</span><span class="sxs-lookup"><span data-stu-id="af474-140">The error message of a nested exception.</span></span> <span data-ttu-id="af474-141">Este elemento incluye atributos XML para **ErrorCode** y **HelpLink**.</span><span class="sxs-lookup"><span data-stu-id="af474-141">This element includes XML attributes for **ErrorCode** and **HelpLink**.</span></span>  
  
 <span data-ttu-id="af474-142">**Advertencias**</span><span class="sxs-lookup"><span data-stu-id="af474-142">**Warnings**</span></span>  
 <span data-ttu-id="af474-143">Cadena XML que contiene las advertencias que se devolvieron al procesar el informe.</span><span class="sxs-lookup"><span data-stu-id="af474-143">An XML string that contains the warnings returned from report processing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af474-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="af474-144">See Also</span></span>  
 <span data-ttu-id="af474-145">[Introducción al control de excepciones en Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="af474-145">[Introducing Exception Handling in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span></span>  
 <span data-ttu-id="af474-146">[Reporting Services (clase SoapException)](reporting-services-soapexception-class.md) </span><span class="sxs-lookup"><span data-stu-id="af474-146">[Reporting Services SoapException Class](reporting-services-soapexception-class.md) </span></span>  
 [<span data-ttu-id="af474-147">Usar la propiedad Detail para administrar errores concretos</span><span class="sxs-lookup"><span data-stu-id="af474-147">Using the Detail Property to Handle Specific Errors</span></span>](../best-practices/using-the-detail-property-to-handle-specific-errors.md)  
  
  
