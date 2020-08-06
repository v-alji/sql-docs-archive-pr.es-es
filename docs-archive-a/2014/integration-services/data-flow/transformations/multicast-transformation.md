---
title: Transformación Multidifusión | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.multicasttrans.f1
helpviewer_keywords:
- multiple outputs
- Multicast transformation
- datasets [Integration Services], multiple outputs
- multiple transformations
ms.assetid: 32194784-1684-40cd-9f91-1aba4d8360d3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7b5c0a38c966c89f426a213f302b45c390b77cfe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752325"
---
# <a name="multicast-transformation"></a><span data-ttu-id="8c094-102">Multidifusión, transformación</span><span class="sxs-lookup"><span data-stu-id="8c094-102">Multicast Transformation</span></span>
  <span data-ttu-id="8c094-103">La transformación Multidifusión distribuye su entrada en una o más salidas.</span><span class="sxs-lookup"><span data-stu-id="8c094-103">The Multicast transformation distributes its input to one or more outputs.</span></span> <span data-ttu-id="8c094-104">Esta transformación es similar a la transformación División condicional.</span><span class="sxs-lookup"><span data-stu-id="8c094-104">This transformation is similar to the Conditional Split transformation.</span></span> <span data-ttu-id="8c094-105">Ambas transformaciones dirigen una entrada a varias salidas.</span><span class="sxs-lookup"><span data-stu-id="8c094-105">Both transformations direct an input to multiple outputs.</span></span> <span data-ttu-id="8c094-106">La diferencia entre las dos es que la transformación Multidifusión dirige cada fila a cada salida, mientras que la División condicional dirige una fila a una sola salida.</span><span class="sxs-lookup"><span data-stu-id="8c094-106">The difference between the two is that the Multicast transformation directs every row to every output, and the Conditional Split directs a row to a single output.</span></span> <span data-ttu-id="8c094-107">Para más información, consulte [Conditional Split Transformation](conditional-split-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="8c094-107">For more information, see [Conditional Split Transformation](conditional-split-transformation.md).</span></span>  
  
 <span data-ttu-id="8c094-108">Para configurar la transformación Multidifusión, debe agregar salidas.</span><span class="sxs-lookup"><span data-stu-id="8c094-108">You configure the Multicast transformation by adding outputs.</span></span>  
  
 <span data-ttu-id="8c094-109">Un paquete puede crear copias lógicas de datos mediante la transformación Multidifusión.</span><span class="sxs-lookup"><span data-stu-id="8c094-109">Using the Multicast transformation, a package can create logical copies of data.</span></span> <span data-ttu-id="8c094-110">Esta capacidad resulta útil cuando el paquete tiene que aplicar varios conjuntos de transformaciones a los mismos datos.</span><span class="sxs-lookup"><span data-stu-id="8c094-110">This capability is useful when the package needs to apply multiple sets of transformations to the same data.</span></span> <span data-ttu-id="8c094-111">Por ejemplo, cuando se agrega una copia de los datos y solo se carga la información de resumen en su destino, mientras otra copia de los datos se extiende con valores de búsqueda y columnas derivadas antes de cargarla en su destino.</span><span class="sxs-lookup"><span data-stu-id="8c094-111">For example, one copy of the data is aggregated and only the summary information is loaded into its destination, while another copy of the data is extended with lookup values and derived columns before it is loaded into its destination.</span></span>  
  
 <span data-ttu-id="8c094-112">Esta transformación tiene una entrada y varias salidas.</span><span class="sxs-lookup"><span data-stu-id="8c094-112">This transformation has one input and multiple outputs.</span></span> <span data-ttu-id="8c094-113">No admite una salida de error.</span><span class="sxs-lookup"><span data-stu-id="8c094-113">It does not support an error output.</span></span>  
  
## <a name="configuration-of-the-multicast-transformation"></a><span data-ttu-id="8c094-114">Configuración de la transformación Multidifusión</span><span class="sxs-lookup"><span data-stu-id="8c094-114">Configuration of the Multicast Transformation</span></span>  
 <span data-ttu-id="8c094-115">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="8c094-115">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="8c094-116">Para obtener más información acerca de las propiedades que puede establecer en el cuadro de diálogo **Editor de transformación Multidifusión** , vea [Multicast Transformation Editor](../../multicast-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="8c094-116">For information about the properties that you can set in the **Multicast Transformation Editor** dialog box, see [Multicast Transformation Editor](../../multicast-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="8c094-117">Para obtener información acerca de las propiedades que puede establecer mediante programación, vea [Common Properties](../../common-properties.md).</span><span class="sxs-lookup"><span data-stu-id="8c094-117">For information about the properties that you can set programmatically, see [Common Properties](../../common-properties.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="8c094-118">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="8c094-118">Related Tasks</span></span>  
 <span data-ttu-id="8c094-119">Para más información sobre cómo establecer las propiedades de este componente, vea [Establecer las propiedades de un componente de flujo de datos](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="8c094-119">For information about how to set properties of this component, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c094-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8c094-120">See Also</span></span>  
 <span data-ttu-id="8c094-121">[Flujo de datos](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="8c094-121">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="8c094-122">Transformaciones de Integration Services</span><span class="sxs-lookup"><span data-stu-id="8c094-122">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
