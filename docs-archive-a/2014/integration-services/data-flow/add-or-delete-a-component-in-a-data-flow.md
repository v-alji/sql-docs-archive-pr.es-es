---
title: Agregar o eliminar un componente en un flujo de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- adding components
- components [Integration Services], data flow
ms.assetid: d99124f9-0994-4f40-a48e-fdca6a4383e7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a2f041258d2b66e7b8da540a842848ebf70f4ed5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744795"
---
# <a name="add-or-delete-a-component-in-a-data-flow"></a><span data-ttu-id="68ee5-102">Agregar o eliminar un componente en un flujo de datos</span><span class="sxs-lookup"><span data-stu-id="68ee5-102">Add or Delete a Component in a Data Flow</span></span>
  <span data-ttu-id="68ee5-103">Los componentes de flujo de datos son orígenes, destinos y transformaciones de un flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="68ee5-103">Data flow components are sources, destinations, and transformations in a data flow.</span></span> <span data-ttu-id="68ee5-104">Antes de poder agregar componentes a un flujo de datos, el flujo de control del paquete debe incluir una tarea Flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="68ee5-104">Before you can add components to a data flow, the control flow in the package must include a Data Flow task.</span></span>  
  
 <span data-ttu-id="68ee5-105">Los procedimientos siguientes describen cómo agregar o eliminar un componente en el flujo de datos de un paquete.</span><span class="sxs-lookup"><span data-stu-id="68ee5-105">The following procedures describe how to add or delete a component in the data flow of a package.</span></span>  
  
### <a name="to-add-a-component-to-a-data-flow"></a><span data-ttu-id="68ee5-106">Para agregar un componente a un flujo de datos</span><span class="sxs-lookup"><span data-stu-id="68ee5-106">To add a component to a data flow</span></span>  
  
1.  <span data-ttu-id="68ee5-107">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="68ee5-107">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="68ee5-108">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="68ee5-108">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="68ee5-109">Haga clic en la pestaña **Flujo de control** y, después, haga doble clic en la tarea Flujo de datos que contiene el flujo de datos al que quiere agregar un componente.</span><span class="sxs-lookup"><span data-stu-id="68ee5-109">Click the **Control Flow** tab, and then double-click the Data Flow task that contains the data flow to which you want to add a component.</span></span>  
  
4.  <span data-ttu-id="68ee5-110">En el cuadro de herramientas, expanda **Orígenes de flujo de datos**, **Transformaciones de flujo de datos**o **Destinos de flujo de datos**, y luego arrastre un elemento de flujo de datos a la superficie de diseño de la pestaña **Flujo de datos** .</span><span class="sxs-lookup"><span data-stu-id="68ee5-110">In the Toolbox, expand **Data Flow Sources**, **Data Flow Transformations**, or **Data Flow Destinations**, and then drag a data flow item to the design surface of the **Data Flow** tab.</span></span>  
  
5.  <span data-ttu-id="68ee5-111">Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados**, en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="68ee5-111">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-delete-a-component-from-a-data-flow"></a><span data-ttu-id="68ee5-112">Para eliminar un componente de un flujo de datos</span><span class="sxs-lookup"><span data-stu-id="68ee5-112">To delete a component from a data flow</span></span>  
  
1.  <span data-ttu-id="68ee5-113">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="68ee5-113">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="68ee5-114">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="68ee5-114">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="68ee5-115">Haga clic en la pestaña **Flujo de control** y, después, haga doble clic en la tarea Flujo de datos que contiene el flujo de datos del que quiere eliminar un componente.</span><span class="sxs-lookup"><span data-stu-id="68ee5-115">Click the **Control Flow** tab, and then double-click the Data Flow task that contains the data flow from which you want to delete a component.</span></span>  
  
4.  <span data-ttu-id="68ee5-116">Haga clic con el botón derecho en el componente de flujo de datos y, después, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="68ee5-116">Right-click the data flow component, and then click **Delete**.</span></span>  
  
5.  <span data-ttu-id="68ee5-117">Confirme la eliminación.</span><span class="sxs-lookup"><span data-stu-id="68ee5-117">Confirm the delete operation.</span></span>  
  
6.  <span data-ttu-id="68ee5-118">Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados**, en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="68ee5-118">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68ee5-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="68ee5-119">See Also</span></span>  
 <span data-ttu-id="68ee5-120">[Conectar componentes de un flujo de datos](data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="68ee5-120">[Connect Components in a Data Flow](data-flow.md) </span></span>  
 <span data-ttu-id="68ee5-121">[Configurar una salida de error en un componente de flujo de datos](../configure-an-error-output-in-a-data-flow-component.md) </span><span class="sxs-lookup"><span data-stu-id="68ee5-121">[Configure an Error Output in a Data Flow Component](../configure-an-error-output-in-a-data-flow-component.md) </span></span>  
 [<span data-ttu-id="68ee5-122">Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="68ee5-122">Data Flow</span></span>](data-flow.md)  
  
  
