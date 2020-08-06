---
title: Prácticas recomendadas para la administración de excepciones de Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- exceptions [Reporting Services], best practices
ms.assetid: 72fecf28-f02e-4338-b50f-0b21f520302d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2e0561c19fbd3e709a0440a55f023f938eabf692
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671930"
---
# <a name="best-practices-for-reporting-services-exception-handling"></a><span data-ttu-id="380af-102">Prácticas recomendadas para la administración de excepciones de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="380af-102">Best Practices for Reporting Services Exception Handling</span></span>
  <span data-ttu-id="380af-103">Al desarrollar aplicaciones de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], hay varias metodologías disponibles para eliminar o reducir la aparición de excepciones.</span><span class="sxs-lookup"><span data-stu-id="380af-103">When developing [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] applications, there are several methodologies you can use to eliminate or reduce the occurrence of exceptions.</span></span> <span data-ttu-id="380af-104">Cuando se producen excepciones, proporcione mensajes de error claros y concisos al usuario, y agregue una administración de excepciones adecuada para evitar que las aplicaciones finalicen inesperadamente.</span><span class="sxs-lookup"><span data-stu-id="380af-104">When exceptions do occur, provide clear and concise error messages to the user, and add adequate exception handling to prevent your applications from ending unexpectedly.</span></span>  
  
 <span data-ttu-id="380af-105">Una aplicación que envía solicitudes al servicio web del servidor de informes debería:</span><span class="sxs-lookup"><span data-stu-id="380af-105">An application that sends requests to the Report Server Web service should do the following:</span></span>  
  
-   <span data-ttu-id="380af-106">Evitar producir excepciones impidiendo tantas solicitudes no válidas como sea posible.</span><span class="sxs-lookup"><span data-stu-id="380af-106">Avoid causing exceptions by preventing as many invalid requests as possible.</span></span>  
  
-   <span data-ttu-id="380af-107">Detectar las excepciones y, siempre que sea posible, proporcionar código de administración de errores específico.</span><span class="sxs-lookup"><span data-stu-id="380af-107">Catch exceptions and provide specific error-handling code whenever possible.</span></span>  
  
-   <span data-ttu-id="380af-108">Tratar los casos de error que no inician excepciones.</span><span class="sxs-lookup"><span data-stu-id="380af-108">Deal with error cases that do not throw exceptions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="380af-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="380af-109">In This Section</span></span>  
  
|<span data-ttu-id="380af-110">Tema</span><span class="sxs-lookup"><span data-stu-id="380af-110">Topic</span></span>|<span data-ttu-id="380af-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="380af-111">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="380af-112">Impedir las solicitudes no válidas</span><span class="sxs-lookup"><span data-stu-id="380af-112">Preventing Invalid Requests</span></span>](preventing-invalid-requests.md)|<span data-ttu-id="380af-113">Describe las técnicas para evitar que las solicitudes que no sean válidas se envíen al servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="380af-113">Describes techniques for preventing requests that are not valid from being sent to the report server.</span></span>|  
|[<span data-ttu-id="380af-114">Uso de los bloques Try y Catch</span><span class="sxs-lookup"><span data-stu-id="380af-114">Using Try and Catch Blocks</span></span>](using-try-and-catch-blocks.md)|<span data-ttu-id="380af-115">Describe cómo mejorar más la confiabilidad de una aplicación con bloques try/catch.</span><span class="sxs-lookup"><span data-stu-id="380af-115">Describes how to further enhance the reliability of your application with try/catch blocks.</span></span>|  
|[<span data-ttu-id="380af-116">Administrar las advertencias y casos que no producen excepciones</span><span class="sxs-lookup"><span data-stu-id="380af-116">Handling Warnings and Cases That Do Not Cause Exceptions</span></span>](handling-warnings-and-cases-that-do-not-cause-exceptions.md)|<span data-ttu-id="380af-117">Explica cómo controlar los errores que no producen ninguna excepción que se inicie a través de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="380af-117">Explains how to handle errors that do not result in an exception being thrown by [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="380af-118">Usar la propiedad Detail para administrar errores concretos</span><span class="sxs-lookup"><span data-stu-id="380af-118">Using the Detail Property to Handle Specific Errors</span></span>](using-the-detail-property-to-handle-specific-errors.md)|<span data-ttu-id="380af-119">Explica cómo administrar mediante programación errores concretos mediante la propiedad **Detail** del objeto **SoapException**.</span><span class="sxs-lookup"><span data-stu-id="380af-119">Explains how to programmatically handle specific errors by using the **Detail** property of the **SoapException** object.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="380af-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="380af-120">See Also</span></span>  
 <span data-ttu-id="380af-121">[Propiedad detail](../soapexception-class/detail-property.md) </span><span class="sxs-lookup"><span data-stu-id="380af-121">[Detail Property](../soapexception-class/detail-property.md) </span></span>  
 <span data-ttu-id="380af-122">[Introducción al control de excepciones en Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="380af-122">[Introducing Exception Handling in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span></span>  
 [<span data-ttu-id="380af-123">Clase SoapException de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="380af-123">Reporting Services SoapException Class</span></span>](../soapexception-class/reporting-services-soapexception-class.md)  
  
  
