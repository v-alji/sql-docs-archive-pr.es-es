---
title: Mezclar particiones (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- merging partitions [XMLA]
- XMLA, partitions
- partitions [Analysis Services], XML for Analysis
- XML for Analysis, partitions
ms.assetid: 657e1d4d-6d50-40f8-a771-7b20c9d865f8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 65840066d3e95571db511a2015a1bee64aa8d922
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671757"
---
# <a name="merging-partitions-xmla"></a><span data-ttu-id="b8661-102">Mezclar particiones (XMLA)</span><span class="sxs-lookup"><span data-stu-id="b8661-102">Merging Partitions (XMLA)</span></span>
  <span data-ttu-id="b8661-103">Si las particiones tienen el mismo diseño y estructura de agregaciones, puede combinar la partición mediante el comando [MergePartitions](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/mergepartitions-element-xmla) en XML for Analysis (XMLA).</span><span class="sxs-lookup"><span data-stu-id="b8661-103">If partitions have the same aggregation design and structure, you can merge the partition by using the [MergePartitions](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/mergepartitions-element-xmla) command in XML for Analysis (XMLA).</span></span> <span data-ttu-id="b8661-104">Combinar particiones es una acción importante que se debe realizar cuando se administran particiones, sobre todo aquellas particiones que contienen datos históricos con particiones por fecha.</span><span class="sxs-lookup"><span data-stu-id="b8661-104">Merging partitions is an important action to perform when you manage partitions, especially those partitions that contain historical data partitioned by date.</span></span>  
  
 <span data-ttu-id="b8661-105">Por ejemplo, un cubo financiero puede usar dos particiones:</span><span class="sxs-lookup"><span data-stu-id="b8661-105">For example, a financial cube may use two partitions:</span></span>  
  
-   <span data-ttu-id="b8661-106">Una partición representa los datos financieros del año en curso, usando la configuración de almacenamiento de OLAP relacional (ROLAP) en tiempo real para el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="b8661-106">One partition represents financial data for the current year, using real-time relational OLAP (ROLAP) storage settings for performance.</span></span>  
  
-   <span data-ttu-id="b8661-107">Otra partición contiene los datos financieros de años anteriores, usando la configuración de almacenamiento de OLAP multidimensional (MOLAP) para el almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="b8661-107">Another partition contains financial data for previous years, using multidimensional OLAP (MOLAP) storage settings for storage.</span></span>  
  
 <span data-ttu-id="b8661-108">Ambas particiones usan valores de almacenamiento diferentes, pero utilizan el mismo diseño de agregaciones.</span><span class="sxs-lookup"><span data-stu-id="b8661-108">Both partitions use different storage settings, but use the same aggregation design.</span></span> <span data-ttu-id="b8661-109">En lugar de procesar el cubo a través de años de datos históricos al final del año, puede usar en su lugar el comando `MergePartitions` para combinar la partición del año en curso en la partición de años anteriores.</span><span class="sxs-lookup"><span data-stu-id="b8661-109">Instead of processing the cube across years of historical data at the end of the year, you can instead use the `MergePartitions` command to merge the partition for the current year into the partition for previous years.</span></span> <span data-ttu-id="b8661-110">Con ello se conservan los datos de agregación sin tener que realizar un proceso completo del cubo que puede requerir mucho tiempo.</span><span class="sxs-lookup"><span data-stu-id="b8661-110">This preserves the aggregation data without requiring a potentially time-consuming full processing of the cube.</span></span>  
  
## <a name="specifying-partitions-to-merge"></a><span data-ttu-id="b8661-111">Especificar particiones para combinar</span><span class="sxs-lookup"><span data-stu-id="b8661-111">Specifying Partitions to Merge</span></span>  
 <span data-ttu-id="b8661-112">Cuando `MergePartitions` se ejecuta el comando, los datos de agregación almacenados en las particiones de origen especificadas en la propiedad de [origen](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/source-element-xmla) se agregan a la partición de destino especificada en la propiedad de [destino](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/target-element-xmla) .</span><span class="sxs-lookup"><span data-stu-id="b8661-112">When the `MergePartitions` command runs, the aggregation data stored in the source partitions specified in the [Source](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/source-element-xmla) property is added to the target partition specified in the [Target](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/target-element-xmla) property.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b8661-113">La propiedad `Source` puede contener más de una referencia de objeto de partición.</span><span class="sxs-lookup"><span data-stu-id="b8661-113">The `Source` property can contain more than one partition object reference.</span></span> <span data-ttu-id="b8661-114">Sin embargo, la propiedad `Target` no puede.</span><span class="sxs-lookup"><span data-stu-id="b8661-114">However, the `Target` property cannot.</span></span>  
  
 <span data-ttu-id="b8661-115">Para que la combinación se realice correctamente, las particiones especificadas tanto en `Source` como en `Target` deben incluirse en del mismo grupo de medida y usar el mismo diseño de agregaciones.</span><span class="sxs-lookup"><span data-stu-id="b8661-115">To be successfully merged, the partitions specified in both the `Source` and `Target` must be contained by the same measure group and use the same aggregation design.</span></span> <span data-ttu-id="b8661-116">De lo contrario, se produce un error.</span><span class="sxs-lookup"><span data-stu-id="b8661-116">Otherwise, an error occurs.</span></span>  
  
 <span data-ttu-id="b8661-117">Se eliminan las particiones especificadas en `Source` una vez que el comando `MergePartitions` se ha completado correctamente.</span><span class="sxs-lookup"><span data-stu-id="b8661-117">The partitions specified in the `Source` are deleted after the `MergePartitions` command is successfully completed.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="b8661-118">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="b8661-118">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="b8661-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="b8661-119">Description</span></span>  
 <span data-ttu-id="b8661-120">En el ejemplo siguiente se combinan todas las particiones del grupo de medida **Customer Counts** del cubo **Adventure Works** de la base de datos de ejemplo **Adventure Works DW** en [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] la partición **Customers_2004** .</span><span class="sxs-lookup"><span data-stu-id="b8661-120">The following example merges all the partitions in the **Customer Counts** measure group of the **Adventure Works** cube in the **Adventure Works DW** sample [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database into the **Customers_2004** partition.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b8661-121">Código</span><span class="sxs-lookup"><span data-stu-id="b8661-121">Code</span></span>  
  
```  
<MergePartitions xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
  <Sources>  
    <Source>  
      <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
      <CubeID>Adventure Works DW</CubeID>  
      <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
      <PartitionID>Internet_Sales_2001</PartitionID>  
    </Source>  
    <Source>  
      <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
      <CubeID>Adventure Works DW</CubeID>  
      <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
      <PartitionID>Internet_Sales_2002</PartitionID>  
    </Source>  
    <Source>  
      <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
      <CubeID>Adventure Works DW</CubeID>  
      <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
      <PartitionID>Internet_Sales_2003</PartitionID>  
    </Source>  
  </Sources>  
  <Target>  
    <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
    <CubeID>Adventure Works DW</CubeID>  
    <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
    <PartitionID>Internet_Sales_2004</PartitionID>  
  </Target>  
</MergePartitions>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b8661-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b8661-122">See Also</span></span>  
 [<span data-ttu-id="b8661-123">Desarrollar con XMLA en Analysis Services</span><span class="sxs-lookup"><span data-stu-id="b8661-123">Developing with XMLA in Analysis Services</span></span>](developing-with-xmla-in-analysis-services.md)  
  
  
