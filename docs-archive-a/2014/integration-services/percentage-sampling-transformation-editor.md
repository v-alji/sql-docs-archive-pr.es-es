---
title: Editor de transformación muestreo de porcentaje | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.percentagesamplingtransformation.f1
helpviewer_keywords:
- Percentage Sampling Transformation Editor
ms.assetid: 2c40d804-26a3-4d35-809b-bc923d83d451
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c4dbd96ab952b6c88bdaa7bf56a0a2f1b3585c57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663558"
---
# <a name="percentage-sampling-transformation-editor"></a><span data-ttu-id="b6aed-102">Editor de transformación Muestreo de porcentaje</span><span class="sxs-lookup"><span data-stu-id="b6aed-102">Percentage Sampling Transformation Editor</span></span>
  <span data-ttu-id="b6aed-103">Use el cuadro de diálogo **Editor de transformación Muestreo de porcentaje** para dividir parte de una entrada en un ejemplo utilizando un porcentaje de filas especificado.</span><span class="sxs-lookup"><span data-stu-id="b6aed-103">Use the **Percentage Sampling Transformation Editor** dialog box to split part of an input into a sample using a specified percentage of rows.</span></span> <span data-ttu-id="b6aed-104">La transformación divide la entrada en dos salidas independientes.</span><span class="sxs-lookup"><span data-stu-id="b6aed-104">This transformation divides the input into two separate outputs.</span></span>  
  
 <span data-ttu-id="b6aed-105">Para obtener más información acerca de la transformación Muestreo de porcentaje, vea [Percentage Sampling Transformation](data-flow/transformations/percentage-sampling-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="b6aed-105">To learn more about the percentage sampling transformation, see [Percentage Sampling Transformation](data-flow/transformations/percentage-sampling-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="b6aed-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="b6aed-106">Options</span></span>  
 <span data-ttu-id="b6aed-107">**Porcentaje de filas**</span><span class="sxs-lookup"><span data-stu-id="b6aed-107">**Percentage of rows**</span></span>  
 <span data-ttu-id="b6aed-108">Especifique el porcentaje de filas de la entrada que se utilizarán como ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b6aed-108">Specify the percentage of rows in the input to use as a sample.</span></span>  
  
 <span data-ttu-id="b6aed-109">Puede especificar el valor de esta propiedad con una expresión de propiedad.</span><span class="sxs-lookup"><span data-stu-id="b6aed-109">The value of this property can be specified by using a property expression.</span></span>  
  
 <span data-ttu-id="b6aed-110">**Nombre de salida de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="b6aed-110">**Sample output name**</span></span>  
 <span data-ttu-id="b6aed-111">Proporcione un nombre único para la salida que incluirá las filas de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b6aed-111">Provide a unique name for the output that will include the sampled rows.</span></span> <span data-ttu-id="b6aed-112">El nombre proporcionado se mostrará en el Diseñador de [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b6aed-112">The name provided will be displayed within the [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="b6aed-113">**Nombre de salida no seleccionado**</span><span class="sxs-lookup"><span data-stu-id="b6aed-113">**Unselected output name**</span></span>  
 <span data-ttu-id="b6aed-114">Proporcione un nombre único para la salida que contendrá las filas excluidas de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b6aed-114">Provide a unique name for the output that will contain the rows excluded from the sampling.</span></span> <span data-ttu-id="b6aed-115">El nombre proporcionado se mostrará en el Diseñador de [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b6aed-115">The name provided will be displayed within the [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="b6aed-116">**Utilizar el valor de inicialización aleatorio siguiente**</span><span class="sxs-lookup"><span data-stu-id="b6aed-116">**Use the following random seed**</span></span>  
 <span data-ttu-id="b6aed-117">Especifique el valor de inicialización del ejemplo para el generador de números aleatorios que utiliza la transformación para crear un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b6aed-117">Specify the sampling seed for the random number generator that the transformation uses to create a sample.</span></span> <span data-ttu-id="b6aed-118">Esto solamente se recomienda para desarrollo y pruebas.</span><span class="sxs-lookup"><span data-stu-id="b6aed-118">This is only recommended for development and testing.</span></span> <span data-ttu-id="b6aed-119">La transformación utiliza el contador de Microsoft Windows si no se especifica el valor de inicialización.</span><span class="sxs-lookup"><span data-stu-id="b6aed-119">The transformation uses the Microsoft Windows tick count if a random seed is not specified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6aed-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b6aed-120">See Also</span></span>  
 <span data-ttu-id="b6aed-121">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="b6aed-121">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="b6aed-122">Transformación Muestreo de fila</span><span class="sxs-lookup"><span data-stu-id="b6aed-122">Row Sampling Transformation</span></span>](data-flow/transformations/row-sampling-transformation.md)  
  
  
