---
title: Editor de transformación Unión de todo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.unionalltransformation.f1
helpviewer_keywords:
- Union All Transformation Editor
ms.assetid: 32fbc1c1-da83-4684-9479-31fc3e2df98c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a7e84c106767aa897b2e419b51ca5b5c538501cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669736"
---
# <a name="union-all-transformation-editor"></a><span data-ttu-id="48320-102">Editor de transformación Unión de todo</span><span class="sxs-lookup"><span data-stu-id="48320-102">Union All Transformation Editor</span></span>
  <span data-ttu-id="48320-103">Use el cuadro de diálogo **Editor de transformación Unión de todo** para combinar varios conjuntos de filas de entrada en un solo conjunto de filas de salida.</span><span class="sxs-lookup"><span data-stu-id="48320-103">Use the **Union All Transformation Editor** dialog box to merge several input rowsets into a single output rowset.</span></span> <span data-ttu-id="48320-104">Al incluir la transformación Unión de todo en un flujo de datos, puede combinar datos de varios flujos, crear conjuntos de datos complejos anidando transformaciones Unión de todo y volver a combinar filas después de corregir errores en los datos.</span><span class="sxs-lookup"><span data-stu-id="48320-104">By including the Union All transformation in a data flow, you can merge data from multiple data flows, create complex datasets by nesting Union All transformations, and re-merge rows after you correct errors in the data.</span></span>  
  
 <span data-ttu-id="48320-105">Para obtener más información acerca de la transformación Unión de todo, vea [Union All Transformation](data-flow/transformations/union-all-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="48320-105">To learn more about the Union All transformation, see [Union All Transformation](data-flow/transformations/union-all-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="48320-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="48320-106">Options</span></span>  
 <span data-ttu-id="48320-107">**Nombre de columna de salida**</span><span class="sxs-lookup"><span data-stu-id="48320-107">**Output Column Name**</span></span>  
 <span data-ttu-id="48320-108">Escriba un alias para cada columna.</span><span class="sxs-lookup"><span data-stu-id="48320-108">Type an alias for each column.</span></span> <span data-ttu-id="48320-109">El valor predeterminado es el nombre de la columna de entrada de la primera entrada (referencia); no obstante, puede elegir un nombre descriptivo único.</span><span class="sxs-lookup"><span data-stu-id="48320-109">The default is the name of the input column from the first (reference) input; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="48320-110">**Entrada de Unión de todo 1**</span><span class="sxs-lookup"><span data-stu-id="48320-110">**Union All Input 1**</span></span>  
 <span data-ttu-id="48320-111">Seleccione la primera entrada (referencia) de la lista de columnas de entrada disponibles.</span><span class="sxs-lookup"><span data-stu-id="48320-111">Select from the list of available input columns in the first (reference) input.</span></span> <span data-ttu-id="48320-112">Los metadatos de las columnas asignadas deben coincidir.</span><span class="sxs-lookup"><span data-stu-id="48320-112">The metadata of mapped columns must match.</span></span>  
  
 <span data-ttu-id="48320-113">**Entrada de Unión de todo n**</span><span class="sxs-lookup"><span data-stu-id="48320-113">**Union All Input n**</span></span>  
 <span data-ttu-id="48320-114">Seleccione la segunda entrada y las adicionales de la lista de columnas de entrada disponibles.</span><span class="sxs-lookup"><span data-stu-id="48320-114">Select from the list of available input columns in the second and additional inputs.</span></span> <span data-ttu-id="48320-115">Los metadatos de las columnas asignadas deben coincidir.</span><span class="sxs-lookup"><span data-stu-id="48320-115">The metadata of mapped columns must match.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48320-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="48320-116">See Also</span></span>  
 <span data-ttu-id="48320-117">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="48320-117">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="48320-118">[Combinar datos mediante la transformación Unión de todo](data-flow/transformations/merge-data-by-using-the-union-all-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="48320-118">[Merge Data by Using the Union All Transformation](data-flow/transformations/merge-data-by-using-the-union-all-transformation.md) </span></span>  
 <span data-ttu-id="48320-119">[Transformación Mezclar](data-flow/transformations/merge-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="48320-119">[Merge Transformation](data-flow/transformations/merge-transformation.md) </span></span>  
 [<span data-ttu-id="48320-120">Transformación Combinación de mezcla</span><span class="sxs-lookup"><span data-stu-id="48320-120">Merge Join Transformation</span></span>](data-flow/transformations/merge-join-transformation.md)  
  
  
