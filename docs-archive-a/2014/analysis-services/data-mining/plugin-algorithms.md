---
title: Algoritmos de complementos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- third-party algorithms [Analysis Services]
- algorithms [data mining], creating
- plugin algorithms [Analysis Services]
ms.assetid: fe364ddc-576e-42fc-9ced-baa399992f92
author: minewiskan
ms.author: owend
ms.openlocfilehash: ebc5e007dcc6de7fb25d59547e21f1e892100570
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747270"
---
# <a name="plugin-algorithms"></a><span data-ttu-id="6d466-102">Algoritmos de complemento</span><span class="sxs-lookup"><span data-stu-id="6d466-102">Plugin Algorithms</span></span>
  <span data-ttu-id="6d466-103">Además de los algoritmos que [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] proporciona, existen muchos otros algoritmos que puede usar para la minería de datos.</span><span class="sxs-lookup"><span data-stu-id="6d466-103">In addition to the algorithms that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] provides, there are many other algorithms that you can use for data mining.</span></span> <span data-ttu-id="6d466-104">Así, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ofrece un mecanismo para que los algoritmos creados por otros fabricantes puedan ser un "complemento".</span><span class="sxs-lookup"><span data-stu-id="6d466-104">Accordingly, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] provides a mechanism for "plugging in" algorithms that are created by third parties.</span></span> <span data-ttu-id="6d466-105">Siempre que el algoritmo cumpla ciertos estándares, podrá utilizarlos en [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] de forma similar a los algoritmos de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6d466-105">As long as the algorithms follow certain standards, you can use them within [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] just as you use the [!INCLUDE[msCoName](../../includes/msconame-md.md)] algorithms.</span></span> <span data-ttu-id="6d466-106">Los algoritmos de complemento tienen todas las capacidades de los algoritmos que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] proporciona.</span><span class="sxs-lookup"><span data-stu-id="6d466-106">Plugin algorithms have all the capabilities of algorithms that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] provides.</span></span>  
  
 <span data-ttu-id="6d466-107">Para obtener una descripción completa de las interfaces que [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] utiliza para comunicarse con algoritmos de complemento, vea los ejemplos para crear un algoritmo y un visor de modelos personalizados que se publiquen en el sitio sitio Web de [CodePlex](https://go.microsoft.com/fwlink/?LinkID=87843) .</span><span class="sxs-lookup"><span data-stu-id="6d466-107">For a full description of the interfaces that [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] uses to communicate with plugin algorithms, see the samples for creating a custom algorithm and custom model viewer that are published on [CodePlex](https://go.microsoft.com/fwlink/?LinkID=87843) Web site.</span></span>  
  
## <a name="algorithm-requirements"></a><span data-ttu-id="6d466-108">Requisitos de los algoritmos</span><span class="sxs-lookup"><span data-stu-id="6d466-108">Algorithm Requirements</span></span>  
 <span data-ttu-id="6d466-109">Para usar un algoritmo de complemento en [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], debe implementar las siguientes interfaces COM:</span><span class="sxs-lookup"><span data-stu-id="6d466-109">To plug an algorithm into [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], you must implement the following COM interfaces:</span></span>  
  
 `IDMAlgorithm`  
 <span data-ttu-id="6d466-110">Implementa un algoritmo que genera modelos e implementa las operaciones de predicción de los modelos resultantes.</span><span class="sxs-lookup"><span data-stu-id="6d466-110">Implements an algorithm that produces models, and implements the prediction operations of the resulting models.</span></span>  
  
 `IDMAlgorithmNavigation`  
 <span data-ttu-id="6d466-111">Habilita el acceso de los exploradores al contenido de los modelos.</span><span class="sxs-lookup"><span data-stu-id="6d466-111">Enables browsers to access the content of the models.</span></span>  
  
 `IDMPersist`  
 <span data-ttu-id="6d466-112">Permite que [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]guarde y cargue los modelos que entrena el algoritmo.</span><span class="sxs-lookup"><span data-stu-id="6d466-112">Enables the models that the algorithm trains to be saved and loaded by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
 `IDMAlgorithmMetadata`  
 <span data-ttu-id="6d466-113">Describe las capacidades y los parámetros de entrada del algoritmo.</span><span class="sxs-lookup"><span data-stu-id="6d466-113">Describes the capabilities and input parameters of the algorithm.</span></span>  
  
 `IDMAlgorithmFactory`  
 <span data-ttu-id="6d466-114">Crea instancias de los objetos que implementan la interfaz del algoritmo y permite que [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] tenga acceso a la interfaz de metadatos del algoritmo.</span><span class="sxs-lookup"><span data-stu-id="6d466-114">Creates instances of the objects that implement the algorithm interface, and provides [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] with access to the algorithm-metadata interface.</span></span>  
  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="6d466-115">utiliza las interfaces COM para comunicarse con los algoritmos de complemento.</span><span class="sxs-lookup"><span data-stu-id="6d466-115">uses these COM interfaces to communicate with plugin algorithms.</span></span> <span data-ttu-id="6d466-116">Aunque los algoritmos de complemento que utilice deben admitir la especificación [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB para minería de datos, no tienen que admitir todas las opciones de minería de datos de la especificación.</span><span class="sxs-lookup"><span data-stu-id="6d466-116">Although plugin algorithms that you use must support the [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB for Data Mining specification, they do not have to support all the data mining options in the specification.</span></span> <span data-ttu-id="6d466-117">Puede usar el conjunto de filas de esquema [MINING_SERVICES](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-services-rowset) para determinar las capacidades del algoritmo.</span><span class="sxs-lookup"><span data-stu-id="6d466-117">You can use the [MINING_SERVICES](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-services-rowset) schema rowset to determine the capabilities of an algorithm.</span></span> <span data-ttu-id="6d466-118">Este conjunto de filas de esquema presenta una lista de las opciones de compatibilidad de la minería de datos con cada proveedor de algoritmos de complemento.</span><span class="sxs-lookup"><span data-stu-id="6d466-118">This schema rowset lists the data mining support options for each plugin algorithm provider.</span></span>  
  
 <span data-ttu-id="6d466-119">Debe registrar los nuevos algoritmos antes de usarlos en [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6d466-119">You must register new algorithms before you use them with [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="6d466-120">Para registrar un algoritmo, incluya la siguiente información en el archivo .ini de la instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en la que desea incluir los algoritmos:</span><span class="sxs-lookup"><span data-stu-id="6d466-120">To register an algorithm, include the following information in the .ini file of the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] on which you want to include the algorithms:</span></span>  
  
-   <span data-ttu-id="6d466-121">El nombre del algoritmo</span><span class="sxs-lookup"><span data-stu-id="6d466-121">The algorithm name</span></span>  
  
-   <span data-ttu-id="6d466-122">ProgID (esto es opcional y solo se incluirá con los algoritmos de complemento)</span><span class="sxs-lookup"><span data-stu-id="6d466-122">ProgID (this is optional and will only be included for plugin algorithms)</span></span>  
  
-   <span data-ttu-id="6d466-123">Una marca que determine si el algoritmo está o no habilitado</span><span class="sxs-lookup"><span data-stu-id="6d466-123">A flag that indicates whether the algorithm is enabled or not</span></span>  
  
 <span data-ttu-id="6d466-124">El siguiente ejemplo de código muestra cómo registrar un algoritmo nuevo:</span><span class="sxs-lookup"><span data-stu-id="6d466-124">The following code sample illustrates how to register a new algorithm:</span></span>  
  
 `<ConfigurationSettings>`  
  
 `...`  
  
 `<DataMining>`  
  
 `...`  
  
 `<Algorithms>`  
  
 `...`  
  
 `<Sample_Plugin_Algorithm>`  
  
 `<Enabled>1</Enabled>`  
  
 `<ProgID>Microsoft.DataMining.SamplePlugInAlgorithm.Factory</ProgID>`  
  
 `</Sample_PlugIn_Algorithm>`  
  
 `...`  
  
 `</Algorithms>`  
  
 `...`  
  
 `</DataMining>`  
  
 `...`  
  
 `</ConfigurationSettings>`  
  
## <a name="see-also"></a><span data-ttu-id="6d466-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6d466-125">See Also</span></span>  
 <span data-ttu-id="6d466-126">[Algoritmos de minería de datos &#40;Analysis Services:&#41;de minería de datos](data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="6d466-126">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="6d466-127">Conjunto de filas DMSCHEMA_MINING_SERVICES</span><span class="sxs-lookup"><span data-stu-id="6d466-127">DMSCHEMA_MINING_SERVICES Rowset</span></span>](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-services-rowset)  
  
  
