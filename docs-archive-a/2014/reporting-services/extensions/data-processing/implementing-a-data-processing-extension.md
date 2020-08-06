---
title: Implementar una extensión de procesamiento de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom data processing extensions [Reporting Services]
- data sources [Reporting Services], data processing extensions
- data processing extensions [Reporting Services]
- extensions [Reporting Services], data processing
ms.assetid: 8dc2b44e-5ad9-411d-a29f-7213e29321a9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5a1b7668f2319e742dcf3f1969fc3c5cc85cd7eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750489"
---
# <a name="implementing-a-data-processing-extension"></a><span data-ttu-id="46192-102">Implementar una extensión de procesamiento de datos</span><span class="sxs-lookup"><span data-stu-id="46192-102">Implementing a Data Processing Extension</span></span>
  <span data-ttu-id="46192-103">Las extensiones de procesamiento de datos de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] permiten conectarse a los orígenes de datos y recuperar los datos.</span><span class="sxs-lookup"><span data-stu-id="46192-103">Data processing extensions in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] enable you to connect to a data source and retrieve data.</span></span> <span data-ttu-id="46192-104">También actúan como puente entre un origen de datos y un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="46192-104">They also serve as a bridge between a data source and a dataset.</span></span> <span data-ttu-id="46192-105">Las extensiones de procesamiento de datos de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] se modelan según un subconjunto de las interfaces del proveedor de datos de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46192-105">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extensions are modeled after a subset of the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] data provider interfaces.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="46192-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="46192-106">In This Section</span></span>  
 [<span data-ttu-id="46192-107">Introducción a las extensiones de procesamiento de datos</span><span class="sxs-lookup"><span data-stu-id="46192-107">Data Processing Extensions Overview</span></span>](data-processing-extensions-overview.md)  
 <span data-ttu-id="46192-108">Explica cómo escribir una extensión de procesamiento de datos personalizada para [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46192-108">Introduces how to write a custom data processing extension for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="46192-109">Preparación de la implementación de una extensión de procesamiento de datos</span><span class="sxs-lookup"><span data-stu-id="46192-109">Preparing to Implement a Data Processing Extension</span></span>](preparing-to-implement-a-data-processing-extension.md)  
 <span data-ttu-id="46192-110">Describe las interfaces disponibles al implementar una extensión de procesamiento de datos de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], así como cuando tiene que implementar una interfaz determinada.</span><span class="sxs-lookup"><span data-stu-id="46192-110">Describes the interfaces available when implementing an [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extension, as well as when you are required to implement a particular interface.</span></span>  
  
 [<span data-ttu-id="46192-111">Creación de una biblioteca de extensión de procesamiento de datos</span><span class="sxs-lookup"><span data-stu-id="46192-111">Creating a Data Processing Extension Library</span></span>](creating-a-data-processing-extension-library.md)  
 <span data-ttu-id="46192-112">Describe cómo asignar un espacio de nombres para la extensión de procesamiento de datos de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] y compilar la extensión de procesamiento de datos en una DLL de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="46192-112">Describes assigning a namespace for your [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extension and compiling your data processing extension into a library DLL.</span></span>  
  
 [<span data-ttu-id="46192-113">Implementación de una clase Connection para una extensión de procesamiento de datos</span><span class="sxs-lookup"><span data-stu-id="46192-113">Implementing a Connection Class for a Data Processing Extension</span></span>](implementing-a-connection-class-for-a-data-processing-extension.md)  
 <span data-ttu-id="46192-114">Describe los atributos de una conexión y cómo implementar una clase propia **Connection** para la extensión de procesamiento de datos.</span><span class="sxs-lookup"><span data-stu-id="46192-114">Describes the attributes of a connection and how to implement your own **Connection** class for your data processing extension.</span></span>  
  
 [<span data-ttu-id="46192-115">Implementación de una clase Command para una extensión de procesamiento de datos</span><span class="sxs-lookup"><span data-stu-id="46192-115">Implementing a Command Class for a Data Processing Extension</span></span>](implementing-a-command-class-for-a-data-processing-extension.md)  
 <span data-ttu-id="46192-116">Describe los atributos de un comando y cómo implementar una clase propia **Command** para la extensión de procesamiento de datos.</span><span class="sxs-lookup"><span data-stu-id="46192-116">Describes the attributes of a command, and how to implement your own **Command** class for your data processing extension.</span></span>  
  
 [<span data-ttu-id="46192-117">Implementación de una clase DataReader para una extensión de procesamiento de datos</span><span class="sxs-lookup"><span data-stu-id="46192-117">Implementing a DataReader Class for a Data Processing Extension</span></span>](implementing-a-datareader-class-for-a-data-processing-extension.md)  
 <span data-ttu-id="46192-118">Describe los atributos de un lector de datos y cómo implementar una clase propia **DataReader** para la extensión de procesamiento de datos.</span><span class="sxs-lookup"><span data-stu-id="46192-118">Describes the attributes of a data reader and how to implement your own **DataReader** class for your data processing extension.</span></span>  
  
 [<span data-ttu-id="46192-119">Uso de un conjunto de datos externo con Reporting Services</span><span class="sxs-lookup"><span data-stu-id="46192-119">Using an External Dataset with Reporting Services</span></span>](using-an-external-dataset-with-reporting-services.md)  
 <span data-ttu-id="46192-120">Describe cómo exponer los objetos **DataSet** personalizados en el servidor de informes para su uso.</span><span class="sxs-lookup"><span data-stu-id="46192-120">Describes how to expose your custom **DataSet** objects to the report server for consumption.</span></span>  
  
 [<span data-ttu-id="46192-121">Implementación de una extensión de procesamiento de datos</span><span class="sxs-lookup"><span data-stu-id="46192-121">Deploying a Data Processing Extension</span></span>](deploying-a-data-processing-extension.md)  
 <span data-ttu-id="46192-122">Describe cómo implementar la extensión de procesamiento de datos.</span><span class="sxs-lookup"><span data-stu-id="46192-122">Describes how to deploy your data processing extension.</span></span>  
  
 [<span data-ttu-id="46192-123">Depuración del código de extensión de procesamiento de datos</span><span class="sxs-lookup"><span data-stu-id="46192-123">Debugging Data Processing Extension Code</span></span>](debugging-data-processing-extension-code.md)  
 <span data-ttu-id="46192-124">Describe cómo depurar el código de las extensiones de procesamiento de datos.</span><span class="sxs-lookup"><span data-stu-id="46192-124">Describes how to debug code in your data processing extensions.</span></span>  
  
 [<span data-ttu-id="46192-125">Quitar una extensión de procesamiento de datos</span><span class="sxs-lookup"><span data-stu-id="46192-125">Removing a Data Processing Extension</span></span>](removing-a-data-processing-extension.md)  
 <span data-ttu-id="46192-126">Describe cómo quitar una extensión de procesamiento de datos de un servidor de informes o del Diseñador de informes.</span><span class="sxs-lookup"><span data-stu-id="46192-126">Describes how to remove a data processing extension from a report server or Report Designer.</span></span>  
  
 <span data-ttu-id="46192-127">Para obtener un ejemplo de una extensión de procesamiento de datos totalmente implementada, vea [Ejemplos del producto SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="46192-127">For a sample of a fully implemented data processing extension, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46192-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="46192-128">See Also</span></span>  
 <span data-ttu-id="46192-129">[Extensiones de Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="46192-129">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 [<span data-ttu-id="46192-130">Biblioteca de extensiones de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="46192-130">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
