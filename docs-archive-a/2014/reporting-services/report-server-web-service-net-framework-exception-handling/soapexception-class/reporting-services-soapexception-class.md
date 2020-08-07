---
title: Clase SoapException de Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- exceptions [Reporting Services], SoapException class
- SoapException class
ms.assetid: 2cec49ee-20b1-40eb-a75b-0908d9c05b34
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6f6efdfac89014116957990ef2db21cf52e76a4f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745665"
---
# <a name="reporting-services-soapexception-class"></a><span data-ttu-id="dfb00-102">Clase SoapException de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="dfb00-102">Reporting Services SoapException Class</span></span>
  <span data-ttu-id="dfb00-103">Debería solucionar cualquier error concreto de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] que podría producirse.</span><span class="sxs-lookup"><span data-stu-id="dfb00-103">You should address specific [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] errors that you know might happen.</span></span> <span data-ttu-id="dfb00-104">Por ejemplo, en una aplicación en la que pida al usuario que cree una carpeta, podría ser posible que el usuario intente crear una que ya exista.</span><span class="sxs-lookup"><span data-stu-id="dfb00-104">For example, in an application where you ask the user to create a folder, it might be possible for the user to try to create a folder that already exists.</span></span> <span data-ttu-id="dfb00-105">Como programador, no tiene control sobre lo que el usuario escribe en los campos de ruta de acceso y nombre de la carpeta de la aplicación, pero tiene puede controlar su experiencia cuando alguien intenta a propósito crear un elemento que ya existe.</span><span class="sxs-lookup"><span data-stu-id="dfb00-105">As the developer, you do not have control over what the user enters in the folder name and path fields of your application, but you do have control over what the user experience is when someone incidentally tries to create an item that already exists.</span></span>  
  
 <span data-ttu-id="dfb00-106">Para facilitar la detección de condiciones de error concretas, [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] clasifica un código de error para la excepción y devuelve la clasificación del error utilizando las propiedades de la clase **SoapException**.</span><span class="sxs-lookup"><span data-stu-id="dfb00-106">To make it easier for you to catch specific error conditions, [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] classifies an error code for the exception and returns the classification of the error using properties from the **SoapException** class.</span></span> <span data-ttu-id="dfb00-107">Para obtener más información, vea "SoapException (clase)" en la [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] documentación del SDK.</span><span class="sxs-lookup"><span data-stu-id="dfb00-107">For more information, see "SoapException Class" in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK documentation.</span></span>  
  
 <span data-ttu-id="dfb00-108">En la siguiente tabla se muestran las propiedades públicas de la clase **SoapException**.</span><span class="sxs-lookup"><span data-stu-id="dfb00-108">The following table lists the public properties of the **SoapException** class.</span></span>  
  
|<span data-ttu-id="dfb00-109">Propiedad pública</span><span class="sxs-lookup"><span data-stu-id="dfb00-109">Public property</span></span>|<span data-ttu-id="dfb00-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="dfb00-110">Description</span></span>|  
|---------------------|-----------------|  
|<span data-ttu-id="dfb00-111">**Actor**</span><span class="sxs-lookup"><span data-stu-id="dfb00-111">**Actor**</span></span>|<span data-ttu-id="dfb00-112">Código que ha producido la excepción.</span><span class="sxs-lookup"><span data-stu-id="dfb00-112">The code that caused the exception.</span></span> <span data-ttu-id="dfb00-113">El valor es la dirección URL del método de servicio web.</span><span class="sxs-lookup"><span data-stu-id="dfb00-113">The value is the URL to the Web service method.</span></span>|  
|<span data-ttu-id="dfb00-114">**Detail**</span><span class="sxs-lookup"><span data-stu-id="dfb00-114">**Detail**</span></span>|<span data-ttu-id="dfb00-115">Información de error específica de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="dfb00-115">Application-specific error information.</span></span> <span data-ttu-id="dfb00-116">El servidor de informes establece el valor y está en formato XML.</span><span class="sxs-lookup"><span data-stu-id="dfb00-116">The value is set by the report server and is in XML format.</span></span> <span data-ttu-id="dfb00-117">Para más información, vea [Propiedad Detail](detail-property.md) y [Usar la propiedad Detail para administrar errores concretos](../best-practices/using-the-detail-property-to-handle-specific-errors.md).</span><span class="sxs-lookup"><span data-stu-id="dfb00-117">For more information, see [Detail Property](detail-property.md) and [Using the Detail Property to Handle Specific Errors](../best-practices/using-the-detail-property-to-handle-specific-errors.md).</span></span>|  
|<span data-ttu-id="dfb00-118">**HelpLink**</span><span class="sxs-lookup"><span data-stu-id="dfb00-118">**HelpLink**</span></span>|<span data-ttu-id="dfb00-119">Una dirección URL o URN a un archivo de Ayuda asociado al error.</span><span class="sxs-lookup"><span data-stu-id="dfb00-119">A URL or URN to a Help file associated with the error.</span></span> <span data-ttu-id="dfb00-120">Normalmente, el servicio web establece el valor y una dirección URL a la Ayuda y soporte técnico de [!INCLUDE[msCoName](../../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dfb00-120">The value is usually set by the Web service and it sets a URL to [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Help and Support.</span></span> <span data-ttu-id="dfb00-121">Dado que [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] admite varios vínculos de ayuda para los errores que se producen, el servidor de informes establece la información del vínculo de la ayuda como parte de la propiedad **Detail**.</span><span class="sxs-lookup"><span data-stu-id="dfb00-121">Because [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] supports multiple help links for errors that occur, the report server sets help link information as part of the **Detail** property.</span></span> <span data-ttu-id="dfb00-122">Para más información, vea [Elemento HelpLink](helplink-element.md).</span><span class="sxs-lookup"><span data-stu-id="dfb00-122">For more information, see [HelpLink Element](helplink-element.md).</span></span>|  
|<span data-ttu-id="dfb00-123">**Message**</span><span class="sxs-lookup"><span data-stu-id="dfb00-123">**Message**</span></span>|<span data-ttu-id="dfb00-124">Mensaje descriptivo y localizado que describe el error.</span><span class="sxs-lookup"><span data-stu-id="dfb00-124">A descriptive, localized message that describes the error.</span></span> <span data-ttu-id="dfb00-125">Este texto podría aparecer en la UI de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="dfb00-125">This text might appear in the application UI.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dfb00-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dfb00-126">See Also</span></span>  
 <span data-ttu-id="dfb00-127">[Introducción al control de excepciones en Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="dfb00-127">[Introducing Exception Handling in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span></span>  
 [<span data-ttu-id="dfb00-128">Tabla de errores de SoapException</span><span class="sxs-lookup"><span data-stu-id="dfb00-128">SoapException Errors Table</span></span>](soapexception-errors-table.md)  
  
  