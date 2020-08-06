---
title: Quitar una extensión de procesamiento de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- deleting data processing extensions
- data processing extensions [Reporting Services], removing
- removing data processing extensions
ms.assetid: 1d89e32b-0631-44f6-8178-a57fb791d26d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9f5dfd3a6a7615fa3fd91c917bba6dbf0808f0f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750482"
---
# <a name="removing-a-data-processing-extension"></a><span data-ttu-id="24ab0-102">Quitar una extensión de procesamiento de datos</span><span class="sxs-lookup"><span data-stu-id="24ab0-102">Removing a Data Processing Extension</span></span>
  <span data-ttu-id="24ab0-103">Para quitar una extensión de procesamiento de datos, basta con quitar el elemento **Extension** de la extensión de procesamiento de datos del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="24ab0-103">To remove a data processing extension, simply remove the **Extension** element for your data processing extension from the configuration file.</span></span> <span data-ttu-id="24ab0-104">Si ha realizado entradas para un servidor de informes así como para el Diseñador de informes, quite el elemento **Extension** de los archivos RSReportServer.config y RSReportDesigner.config.</span><span class="sxs-lookup"><span data-stu-id="24ab0-104">If you made entries for a report server as well as Report Designer, remove the **Extension** element from both the RSReportServer.config and RSReportDesigner.config files.</span></span> <span data-ttu-id="24ab0-105">Después de quitar la información de configuración, la extensión de procesamiento de datos ya no estará disponible en el componente.</span><span class="sxs-lookup"><span data-stu-id="24ab0-105">After the configuration information is removed, the data processing extension is no longer available to the component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24ab0-106">Consulte también</span><span class="sxs-lookup"><span data-stu-id="24ab0-106">See Also</span></span>  
 <span data-ttu-id="24ab0-107">[Extensiones de Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="24ab0-107">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="24ab0-108">[Implementar una extensión de procesamiento de datos](implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="24ab0-108">[Implementing a Data Processing Extension](implementing-a-data-processing-extension.md) </span></span>  
 [<span data-ttu-id="24ab0-109">Biblioteca de extensiones de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="24ab0-109">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
