---
title: Opciones de la cuadrícula de variables | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.variableoptionswindow.f1
helpviewer_keywords:
- Choose Variable Columns dialog box
ms.assetid: 7cccc230-3b20-4074-804f-3448d9616a83
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b90e1a3c69e4eaf1f123603e0082ecb1eda4e893
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669732"
---
# <a name="variable-grid-options"></a><span data-ttu-id="235b0-102">Opciones de la cuadrícula de variables</span><span class="sxs-lookup"><span data-stu-id="235b0-102">Variable Grid Options</span></span>
  <span data-ttu-id="235b0-103">Utilice el cuadro de diálogo **Opciones de la cuadrícula de variables** para seleccionar las columnas que se mostrarán en la ventana **Variables** y seleccionar los filtros para aplicarlos a la lista de variables.</span><span class="sxs-lookup"><span data-stu-id="235b0-103">Use the **Variable Grid Options** dialog box to select the columns that will display in the **Variables** window and to select the filters to apply to the list of variables.</span></span> <span data-ttu-id="235b0-104">Para más información sobre las propiedades de variable correspondientes, vea [Variables de Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="235b0-104">For more information about the corresponding variable properties, see [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md).</span></span>  
  
## <a name="options-for-filter"></a><span data-ttu-id="235b0-105">Opciones del filtro</span><span class="sxs-lookup"><span data-stu-id="235b0-105">Options for Filter</span></span>  
 <span data-ttu-id="235b0-106">**Mostrar variables del sistema**</span><span class="sxs-lookup"><span data-stu-id="235b0-106">**Show system variables**</span></span>  
 <span data-ttu-id="235b0-107">Seleccione para mostrar variables del sistema en la ventana de **Variables** .</span><span class="sxs-lookup"><span data-stu-id="235b0-107">Select to list system variables in the **Variables** window.</span></span> <span data-ttu-id="235b0-108">Las variables del sistema están predefinidas.</span><span class="sxs-lookup"><span data-stu-id="235b0-108">System variables are predefined.</span></span> <span data-ttu-id="235b0-109">Las variables del sistema no se pueden agregar ni eliminar.</span><span class="sxs-lookup"><span data-stu-id="235b0-109">You cannot add or delete system variables.</span></span> <span data-ttu-id="235b0-110">Puede modificar la configuración de propiedades de **RaiseChangedEvent** .</span><span class="sxs-lookup"><span data-stu-id="235b0-110">You can modify the **RaiseChangedEvent** property setting.</span></span>  
  
 <span data-ttu-id="235b0-111">Esta lista está codificada en color.</span><span class="sxs-lookup"><span data-stu-id="235b0-111">This list is color coded.</span></span> <span data-ttu-id="235b0-112">Las variables del sistema son grises y las definidas por el usuario son negras.</span><span class="sxs-lookup"><span data-stu-id="235b0-112">System variables are gray, and user-defined variables are black.</span></span>  
  
 <span data-ttu-id="235b0-113">**Mostrar variables de todos los ámbitos**</span><span class="sxs-lookup"><span data-stu-id="235b0-113">**Show variables of all scopes**</span></span>  
 <span data-ttu-id="235b0-114">Seleccione mostrar las variables en el ámbito del paquete y, en el ámbito de los contenedores, tareas y controladores de eventos en el paquete.</span><span class="sxs-lookup"><span data-stu-id="235b0-114">Select to show variables within the scope the package, and within the scope of containers, tasks, and event handlers in the package.</span></span> <span data-ttu-id="235b0-115">Desactive esta opción para mostrar solo variables en el ámbito del paquete y en el ámbito de un contenedor, una tarea o un controlador de eventos seleccionada.</span><span class="sxs-lookup"><span data-stu-id="235b0-115">Clear this option to show only variables within the scope of the package and within the scope of a selected container, task, or event handler.</span></span>  
  
 <span data-ttu-id="235b0-116">Para más información sobre el ámbito de las variables, vea [Variables de Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="235b0-116">For more information about variable scope, see [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md).</span></span>  
  
## <a name="options-for-columns"></a><span data-ttu-id="235b0-117">Opciones de las columnas</span><span class="sxs-lookup"><span data-stu-id="235b0-117">Options for Columns</span></span>  
 <span data-ttu-id="235b0-118">Seleccione las columnas que desea que aparezcan en la ventana **Variables** .</span><span class="sxs-lookup"><span data-stu-id="235b0-118">Select the columns that you want to appear in the **Variables** window.</span></span>  
  
-   <span data-ttu-id="235b0-119">**Ámbito**</span><span class="sxs-lookup"><span data-stu-id="235b0-119">**Scope**</span></span>  
  
-   <span data-ttu-id="235b0-120">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="235b0-120">**Data type**</span></span>  
  
-   <span data-ttu-id="235b0-121">**Valor**</span><span class="sxs-lookup"><span data-stu-id="235b0-121">**Value**</span></span>  
  
-   <span data-ttu-id="235b0-122">**Espacio de nombres**</span><span class="sxs-lookup"><span data-stu-id="235b0-122">**Namespace**</span></span>  
  
-   <span data-ttu-id="235b0-123">**Desencadenar el evento cuando cambie el valor de la variable**</span><span class="sxs-lookup"><span data-stu-id="235b0-123">**Raise event when variable value changes**</span></span>  
  
-   <span data-ttu-id="235b0-124">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="235b0-124">**Description**</span></span>  
  
-   <span data-ttu-id="235b0-125">**Expression**</span><span class="sxs-lookup"><span data-stu-id="235b0-125">**Expression**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="235b0-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="235b0-126">See Also</span></span>  
 <span data-ttu-id="235b0-127">[Ventana variables](../../2014/integration-services/variables-window.md) </span><span class="sxs-lookup"><span data-stu-id="235b0-127">[Variables Window](../../2014/integration-services/variables-window.md) </span></span>  
 <span data-ttu-id="235b0-128">[Variables de Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="235b0-128">[Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="235b0-129">[Usar variables en paquetes](../../2014/integration-services/use-variables-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="235b0-129">[Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md) </span></span>  
 [<span data-ttu-id="235b0-130">Controladores de eventos de Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="235b0-130">Integration Services &#40;SSIS&#41; Event Handlers</span></span>](integration-services-ssis-event-handlers.md)  
  
  
