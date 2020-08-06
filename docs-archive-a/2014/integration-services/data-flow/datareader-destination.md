---
title: Destino de DataReader | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.datareaderdest.f1
helpviewer_keywords:
- DataReader destination
- destinations [Integration Services], DataReader
ms.assetid: 56fcc4bf-c901-42c3-a71d-110039293431
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 40cfe5d99c33eb19d415f204173005a64bde7855
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751361"
---
# <a name="datareader-destination"></a><span data-ttu-id="6299c-102">DataReader, destino</span><span class="sxs-lookup"><span data-stu-id="6299c-102">DataReader Destination</span></span>
  <span data-ttu-id="6299c-103">El destino de DataReader expone los datos en un flujo de datos mediante la interfaz ADO.NET `DataReader`.</span><span class="sxs-lookup"><span data-stu-id="6299c-103">The DataReader destination exposes the data in a data flow by using the ADO.NET `DataReader` interface.</span></span> <span data-ttu-id="6299c-104">En ese momento los datos pueden ser usados por otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="6299c-104">The data can then be consumed by other applications.</span></span> <span data-ttu-id="6299c-105">Por ejemplo, puede configurar el origen de datos de un informe de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] para usar el resultado de la ejecución de un paquete de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6299c-105">For example, you can configure the data source of a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report to use the result of running a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package.</span></span> <span data-ttu-id="6299c-106">Para ello, se crea un flujo de datos que implementa el destino de DataReader.</span><span class="sxs-lookup"><span data-stu-id="6299c-106">To do this, you create a data flow that implements the DataReader destination.</span></span>  
  
 <span data-ttu-id="6299c-107">Para obtener información sobre cómo acceder a valores y leerlos en el destino de DataReader mediante programación, vea [Cargar la salida de un paquete local](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md).</span><span class="sxs-lookup"><span data-stu-id="6299c-107">For information about accessing and reading values in the DataReader destination programmatically, see [Loading the Output of a Local Package](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md).</span></span>  
  
## <a name="configuration-of-the-datareader-destination"></a><span data-ttu-id="6299c-108">Configuración del destino de DataReader</span><span class="sxs-lookup"><span data-stu-id="6299c-108">Configuration of the DataReader Destination</span></span>  
 <span data-ttu-id="6299c-109">Puede especificar un valor de tiempo de espera para el destino de DataReader e indicar si se produce un error en el destino al agotarse el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="6299c-109">You can specify a time-out value for the DataReader destination and indicate whether the destination should fail if a time-out occurs.</span></span> <span data-ttu-id="6299c-110">El tiempo de espera se agota si la aplicación no pide datos dentro del tiempo especificado.</span><span class="sxs-lookup"><span data-stu-id="6299c-110">A time-out occurs if the application does not ask for data within the specified time.</span></span>  
  
 <span data-ttu-id="6299c-111">El destino de DataReader tiene una entrada.</span><span class="sxs-lookup"><span data-stu-id="6299c-111">The DataReader destination has one input.</span></span> <span data-ttu-id="6299c-112">No admite una salida de error.</span><span class="sxs-lookup"><span data-stu-id="6299c-112">It does not support an error output.</span></span>  
  
 <span data-ttu-id="6299c-113">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="6299c-113">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="6299c-114">Para obtener más información acerca de las propiedades que puede establecer a través del cuadro de diálogo **Editor avanzado** o mediante programación, haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="6299c-114">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="6299c-115">Common Properties</span><span class="sxs-lookup"><span data-stu-id="6299c-115">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="6299c-116">Propiedades personalizadas del destino DataReader</span><span class="sxs-lookup"><span data-stu-id="6299c-116">DataReader Destination Custom Properties</span></span>](datareader-destination-custom-properties.md)  
  
 <span data-ttu-id="6299c-117">Para más información sobre cómo establecer propiedades, vea [Establecer las propiedades de un componente de flujo de datos](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="6299c-117">For more information about how to set properties, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
