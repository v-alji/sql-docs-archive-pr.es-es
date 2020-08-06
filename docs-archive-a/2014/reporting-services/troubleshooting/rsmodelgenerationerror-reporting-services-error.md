---
title: 'rsModelGenerationError: error de Reporting Services | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- rsModelGenerationError
ms.assetid: 3a0ad63f-87f9-4ca1-b0c2-c85fa991634a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 713de57f0f2957983966f8ef0345bb374c311781
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673452"
---
# <a name="rsmodelgenerationerror---reporting-services-error"></a><span data-ttu-id="8fdce-102">rsModelGenerationError - Error de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="8fdce-102">rsModelGenerationError - Reporting Services Error</span></span>
    
## <a name="details"></a><span data-ttu-id="8fdce-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="8fdce-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8fdce-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="8fdce-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="8fdce-105">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="8fdce-105">Event ID</span></span>|<span data-ttu-id="8fdce-106">rsRenderingError</span><span class="sxs-lookup"><span data-stu-id="8fdce-106">rsRenderingError</span></span>|  
|<span data-ttu-id="8fdce-107">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="8fdce-107">Event Source</span></span>|<span data-ttu-id="8fdce-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span><span class="sxs-lookup"><span data-stu-id="8fdce-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span></span>|  
|<span data-ttu-id="8fdce-109">Componente</span><span class="sxs-lookup"><span data-stu-id="8fdce-109">Component</span></span>|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|<span data-ttu-id="8fdce-110">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="8fdce-110">Message Text</span></span>|<span data-ttu-id="8fdce-111">Error al generar el modelo.</span><span class="sxs-lookup"><span data-stu-id="8fdce-111">An error occurred while generating model.</span></span> <span data-ttu-id="8fdce-112">(rsModelGenerationError) (ReportingServicesLibrary) %1</span><span class="sxs-lookup"><span data-stu-id="8fdce-112">(rsModelGenerationError) (ReportingServicesLibrary) %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8fdce-113">Explicación</span><span class="sxs-lookup"><span data-stu-id="8fdce-113">Explanation</span></span>  
 <span data-ttu-id="8fdce-114">No se puede generar el modelo de informe.</span><span class="sxs-lookup"><span data-stu-id="8fdce-114">The report model could not be generated.</span></span> <span data-ttu-id="8fdce-115">En [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005 SP1 y en versiones anteriores, es más probable que se muestre este error cuando el objeto System.Data.DataSet no puede controlar una tabla o relación del esquema de la base de datos, como cuando, por ejemplo, se definen dos claves externas para la misma columna de una tabla.</span><span class="sxs-lookup"><span data-stu-id="8fdce-115">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]2005 SP1 and earlier versions, this error is most likely displayed when the System.Data.DataSet object cannot handle a table or relationship within the database schema, such as when, for example, two foreign keys are defined on the same column within a table.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8fdce-116">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="8fdce-116">User Action</span></span>  
 <span data-ttu-id="8fdce-117">Para determinar el motivo específico por el que aparece este mensaje de error, revise los archivos de registro del servidor de informes, que se encuentran en \Microsoft SQL Server\\<Instancia de SQL Server\>\Reporting Services\LogFiles.</span><span class="sxs-lookup"><span data-stu-id="8fdce-117">To determine the specific reason that caused this message to appear, review the report server log files, which are located at \Microsoft SQL Server\\<SQL Server Instance\>\Reporting Services\LogFiles.</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="8fdce-118">Solo para uso interno</span><span class="sxs-lookup"><span data-stu-id="8fdce-118">Internal-Only</span></span>  
  
