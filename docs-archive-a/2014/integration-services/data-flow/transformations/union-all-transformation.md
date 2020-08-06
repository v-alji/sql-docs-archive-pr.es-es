---
title: Transformación Unión | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.unionalltrans.f1
helpviewer_keywords:
- merging datasets [Integration Services]
- combining datasets
- Union All transformation
- datasets [Integration Services], merging
ms.assetid: 942e4b90-9c41-4e9c-a6f3-80b3afe57f2f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: eaaab1abf2587979e947cc1be24cbedf8f61b6e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676080"
---
# <a name="union-all-transformation"></a><span data-ttu-id="66efd-102">Unión de todo, transformación</span><span class="sxs-lookup"><span data-stu-id="66efd-102">Union All Transformation</span></span>
  <span data-ttu-id="66efd-103">La transformación Unión de todo combina varias entradas en una salida.</span><span class="sxs-lookup"><span data-stu-id="66efd-103">The Union All transformation combines multiple inputs into one output.</span></span> <span data-ttu-id="66efd-104">Por ejemplo, las salidas de cinco orígenes de archivos planos distintos pueden ser entradas de la transformación Unión de todo y combinarse en una salida.</span><span class="sxs-lookup"><span data-stu-id="66efd-104">For example, the outputs from five different Flat File sources can be inputs to the Union All transformation and combined into one output.</span></span>  
  
## <a name="inputs-and-outputs"></a><span data-ttu-id="66efd-105">Entradas y salidas</span><span class="sxs-lookup"><span data-stu-id="66efd-105">Inputs and Outputs</span></span>  
 <span data-ttu-id="66efd-106">Las entradas de la transformación se agregan una detrás de otra a la salida de transformación; las filas no se reordenan.</span><span class="sxs-lookup"><span data-stu-id="66efd-106">The transformation inputs are added to the transformation output one after the other; no reordering of rows occurs.</span></span> <span data-ttu-id="66efd-107">Si el paquete requiere una salida ordenada, debe usar la transformación Combinar en lugar de la transformación Unión de todo.</span><span class="sxs-lookup"><span data-stu-id="66efd-107">If the package requires a sorted output, you should use the Merge transformation instead of the Union All transformation.</span></span>  
  
 <span data-ttu-id="66efd-108">La primera entrada que se puede conectar a la transformación Unión de todo es la entrada a partir de la cual la transformación crea su salida.</span><span class="sxs-lookup"><span data-stu-id="66efd-108">The first input that you connect to the Union All transformation is the input from which the transformation creates the transformation output.</span></span> <span data-ttu-id="66efd-109">Las columnas de las entradas que se conecten posteriormente a la transformación se asignarán a las columnas de la salida de transformación.</span><span class="sxs-lookup"><span data-stu-id="66efd-109">The columns in the inputs you subsequently connect to the transformation are mapped to the columns in the transformation output.</span></span>  
  
 <span data-ttu-id="66efd-110">Para combinar entradas, debe asignar columnas de las entradas a columnas de la salida.</span><span class="sxs-lookup"><span data-stu-id="66efd-110">To merge inputs, you map columns in the inputs to columns in the output.</span></span> <span data-ttu-id="66efd-111">Se debe asignar una columna con al menos una entrada a cada columna de salida.</span><span class="sxs-lookup"><span data-stu-id="66efd-111">A column from at least one input must be mapped to each output column.</span></span> <span data-ttu-id="66efd-112">La asignación entre dos columnas requiere que los metadatos de las columnas coincidan.</span><span class="sxs-lookup"><span data-stu-id="66efd-112">The mapping between two columns requires that the metadata of the columns match.</span></span> <span data-ttu-id="66efd-113">Por ejemplo, las columnas asignadas deben tener el mismo tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="66efd-113">For example, the mapped columns must have the same data type.</span></span>  
  
 <span data-ttu-id="66efd-114">Si las columnas asignadas contienen datos de cadena y la columna de salida es de menor longitud que la columna de entrada, se aumenta automáticamente la longitud de la columna de salida para que pueda contener la columna de entrada.</span><span class="sxs-lookup"><span data-stu-id="66efd-114">If the mapped columns contain string data and the output column is shorter in length than the input column, the output column is automatically increased in length to contain the input column.</span></span> <span data-ttu-id="66efd-115">Las columnas de entrada que no se asignan a columnas de salida se establecen en valores NULL en las columnas de salida.</span><span class="sxs-lookup"><span data-stu-id="66efd-115">Input columns that are not mapped to output columns are set to null values in the output columns.</span></span>  
  
 <span data-ttu-id="66efd-116">Esta transformación tiene varias entradas y una salida.</span><span class="sxs-lookup"><span data-stu-id="66efd-116">This transformation has multiple inputs and one output.</span></span> <span data-ttu-id="66efd-117">No admite una salida de error.</span><span class="sxs-lookup"><span data-stu-id="66efd-117">It does not support an error output.</span></span>  
  
## <a name="configuration-of-the-union-all-transformation"></a><span data-ttu-id="66efd-118">Configuración de la transformación Unión de todo</span><span class="sxs-lookup"><span data-stu-id="66efd-118">Configuration of the Union All Transformation</span></span>  
 <span data-ttu-id="66efd-119">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="66efd-119">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="66efd-120">Para obtener más información acerca de las propiedades que puede establecer en el cuadro de diálogo **Editor de transformación Unión de todo** , vea [Union All Transformation Editor](../../union-all-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="66efd-120">For more information about the properties that you can set in the **Union All Transformation Editor** dialog box, see [Union All Transformation Editor](../../union-all-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="66efd-121">Para obtener más información acerca de las propiedades que puede establecer mediante programación, vea [Common Properties](../../common-properties.md).</span><span class="sxs-lookup"><span data-stu-id="66efd-121">For more information about the properties that you can set programmatically, see [Common Properties](../../common-properties.md).</span></span>  
  
 <span data-ttu-id="66efd-122">Para obtener más información sobre cómo establecer valores de propiedades, haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="66efd-122">For more information about how to set properties, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="66efd-123">Establecer las propiedades de un componente de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="66efd-123">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="66efd-124">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="66efd-124">Related Tasks</span></span>  
 [<span data-ttu-id="66efd-125">Combinar datos mediante la transformación Unión de todo</span><span class="sxs-lookup"><span data-stu-id="66efd-125">Merge Data by Using the Union All Transformation</span></span>](union-all-transformation.md)  
  
  
