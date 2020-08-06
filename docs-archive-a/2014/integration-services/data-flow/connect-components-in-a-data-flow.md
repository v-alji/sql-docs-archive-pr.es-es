---
title: Conectar componentes de un flujo de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- components [Integration Services], connections
- connections [Integration Services], data flow components
ms.assetid: 70616a58-8921-4218-85bf-f3e90c5a9dbf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8fc4a2fa81e9b110c27ea63b16d835d069bf12cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744245"
---
# <a name="connect-components-in-a-data-flow"></a><span data-ttu-id="34d93-102">Conectar componentes de un flujo de datos</span><span class="sxs-lookup"><span data-stu-id="34d93-102">Connect Components in a Data Flow</span></span>
  <span data-ttu-id="34d93-103">Este procedimiento describe cómo conectar la salida de los componentes de un flujo de datos con otros componentes dentro del mismo flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="34d93-103">This procedure describes how to connect the output of components in a data flow to other components within the same data flow.</span></span>  
  
### <a name="to-connect-components-in-a-data-flow"></a><span data-ttu-id="34d93-104">Para conectar los componentes de un flujo de datos</span><span class="sxs-lookup"><span data-stu-id="34d93-104">To connect components in a data flow</span></span>  
  
1.  <span data-ttu-id="34d93-105">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="34d93-105">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="34d93-106">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="34d93-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="34d93-107">Haga clic en la pestaña **Flujo de control** y luego haga doble clic en la tarea Flujo de datos que contiene el flujo de datos donde quiere conectar componentes.</span><span class="sxs-lookup"><span data-stu-id="34d93-107">Click the **Control Flow** tab, and then double-click the Data Flow task that contains the data flow in which you want to connect components.</span></span>  
  
4.  <span data-ttu-id="34d93-108">En la superficie de diseño de la pestaña **Flujo de datos** , seleccione la transformación u origen que desea conectar.</span><span class="sxs-lookup"><span data-stu-id="34d93-108">On the design surface of the **Data Flow** tab, select the transformation or source that you want to connect.</span></span>  
  
5.  <span data-ttu-id="34d93-109">Arrastre la flecha verde de salida de una transformación o un origen a una transformación o a un destino.</span><span class="sxs-lookup"><span data-stu-id="34d93-109">Drag the green output arrow of a transformation or a source to a transformation or to a destination.</span></span> <span data-ttu-id="34d93-110">Algunos componentes de flujo de datos tienen salidas de error que se pueden conectar de la misma manera.</span><span class="sxs-lookup"><span data-stu-id="34d93-110">Some data flow components have error outputs that you can connect in the same way.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="34d93-111">Algunos componentes de flujo de datos pueden tener varias salidas y cada una de ellas se puede conectar con una transformación o destino diferente.</span><span class="sxs-lookup"><span data-stu-id="34d93-111">Some data flow components can have multiple outputs and you can connect each output to a different transformation or destination.</span></span>  
  
6.  <span data-ttu-id="34d93-112">Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados**, en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="34d93-112">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34d93-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="34d93-113">See Also</span></span>  
 <span data-ttu-id="34d93-114">[Agregar o eliminar un componente en un flujo de datos](data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="34d93-114">[Add or Delete a Component in a Data Flow](data-flow.md) </span></span>  
 <span data-ttu-id="34d93-115">[Configurar una salida de error en un componente de flujo de datos](../configure-an-error-output-in-a-data-flow-component.md) </span><span class="sxs-lookup"><span data-stu-id="34d93-115">[Configure an Error Output in a Data Flow Component](../configure-an-error-output-in-a-data-flow-component.md) </span></span>  
 [<span data-ttu-id="34d93-116">Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="34d93-116">Data Flow</span></span>](data-flow.md)  
  
  
