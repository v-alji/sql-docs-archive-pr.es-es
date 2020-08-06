---
title: Editor de transformación muestreo de fila (página muestreo) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.ROWSAMPLINGTRANSFORMATION.COLUMNS.F1
- sql12.dts.designer.rowsamplingtransformation.f1
helpviewer_keywords:
- Row Sampling Transformation Editor
ms.assetid: 544c7709-6de0-4c08-bda3-759985be9a05
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 26d0c0439e548172225f02220d8f6814a1168ea9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744748"
---
# <a name="row-sampling-transformation-editor-sampling-page"></a><span data-ttu-id="fe13a-102">Editor de transformación Muestreo de fila (página Muestreo)</span><span class="sxs-lookup"><span data-stu-id="fe13a-102">Row Sampling Transformation Editor (Sampling Page)</span></span>
  <span data-ttu-id="fe13a-103">Use el cuadro de diálogo **Editor de transformación Muestreo de fila** para dividir una parte de una entrada en un ejemplo que utilice un número especificado de filas.</span><span class="sxs-lookup"><span data-stu-id="fe13a-103">Use the **Row Sampling Transformation Editor** dialog box to split a portion of an input into a sample using a specified number of rows.</span></span> <span data-ttu-id="fe13a-104">La transformación divide la entrada en dos salidas independientes.</span><span class="sxs-lookup"><span data-stu-id="fe13a-104">This transformation divides the input into two separate outputs.</span></span>  
  
 <span data-ttu-id="fe13a-105">Para obtener más información acerca de la transformación Muestreo de fila, vea [Row Sampling Transformation](data-flow/transformations/row-sampling-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="fe13a-105">To learn more about the Row Sampling transformation, see [Row Sampling Transformation](data-flow/transformations/row-sampling-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="fe13a-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="fe13a-106">Options</span></span>  
 <span data-ttu-id="fe13a-107">**Número de filas**</span><span class="sxs-lookup"><span data-stu-id="fe13a-107">**Number of rows**</span></span>  
 <span data-ttu-id="fe13a-108">Especifique el número de filas de la entrada que se utilizarán como ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fe13a-108">Specify the number of rows from the input to use as a sample.</span></span>  
  
 <span data-ttu-id="fe13a-109">Puede especificar el valor de esta propiedad con una expresión de propiedad.</span><span class="sxs-lookup"><span data-stu-id="fe13a-109">The value of this property can be specified by using a property expression.</span></span>  
  
 <span data-ttu-id="fe13a-110">**Nombre de salida de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="fe13a-110">**Sample output name**</span></span>  
 <span data-ttu-id="fe13a-111">Proporcione un nombre único para la salida que incluirá las filas de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fe13a-111">Provide a unique name for the output that will include the sampled rows.</span></span> <span data-ttu-id="fe13a-112">El nombre que indique se mostrará en el Diseñador SSIS.</span><span class="sxs-lookup"><span data-stu-id="fe13a-112">The name provided will be displayed within SSIS Designer.</span></span>  
  
 <span data-ttu-id="fe13a-113">**Nombre de salida no seleccionado**</span><span class="sxs-lookup"><span data-stu-id="fe13a-113">**Unselected output name**</span></span>  
 <span data-ttu-id="fe13a-114">Proporcione un nombre único para la salida que contendrá las filas excluidas de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fe13a-114">Provide a unique name for the output that will contain the rows excluded from the sampling.</span></span> <span data-ttu-id="fe13a-115">El nombre que indique se mostrará en el Diseñador SSIS.</span><span class="sxs-lookup"><span data-stu-id="fe13a-115">The name provided will be displayed within SSIS Designer.</span></span>  
  
 <span data-ttu-id="fe13a-116">**Utilizar el valor de inicialización aleatorio siguiente**</span><span class="sxs-lookup"><span data-stu-id="fe13a-116">**Use the following random seed**</span></span>  
 <span data-ttu-id="fe13a-117">Especifique el valor de inicialización del ejemplo para el generador de números aleatorios que utiliza la transformación para crear un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fe13a-117">Specify the sampling seed for the random number generator that the transformation uses to create a sample.</span></span> <span data-ttu-id="fe13a-118">Esto solamente se recomienda para desarrollo y pruebas.</span><span class="sxs-lookup"><span data-stu-id="fe13a-118">This is only recommended for development and testing.</span></span> <span data-ttu-id="fe13a-119">La transformación utiliza el contador de Microsoft Windows como valor de inicialización si no se especifica un valor de inicialización aleatorio.</span><span class="sxs-lookup"><span data-stu-id="fe13a-119">The transformation uses the Microsoft Windows tick count as a seed if a random seed is not specified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe13a-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fe13a-120">See Also</span></span>  
 <span data-ttu-id="fe13a-121">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="fe13a-121">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="fe13a-122">Transformación Muestreo de porcentaje</span><span class="sxs-lookup"><span data-stu-id="fe13a-122">Percentage Sampling Transformation</span></span>](data-flow/transformations/percentage-sampling-transformation.md)  
  
  
