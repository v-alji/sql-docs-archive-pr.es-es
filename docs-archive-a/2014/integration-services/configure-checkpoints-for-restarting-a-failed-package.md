---
title: Configurar puntos de comprobación para reiniciar un paquete con errores | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- checkpoints [Integration Services]
- restarting packages
- starting packages
ms.assetid: 9afffa5a-d803-4653-8afc-386453fc163f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a85354377453e0b24692ab8c2b567cc8998b6b05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748217"
---
# <a name="configure-checkpoints-for-restarting-a-failed-package"></a><span data-ttu-id="d52e8-102">Configurar puntos de comprobación para reiniciar un paquete con error</span><span class="sxs-lookup"><span data-stu-id="d52e8-102">Configure Checkpoints for Restarting a Failed Package</span></span>
  <span data-ttu-id="d52e8-103">Los paquetes de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] se configuran para que se reinicien desde un punto de error, en lugar de volver a ejecutar todo el paquete, estableciendo las propiedades que afectan a los puntos de comprobación.</span><span class="sxs-lookup"><span data-stu-id="d52e8-103">You configure [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages to restart from a point of failure, instead of rerunning the entire package, by setting the properties that apply to checkpoints.</span></span>  
  
### <a name="to-configure-a-package-to-restart"></a><span data-ttu-id="d52e8-104">Para configurar un paquete de modo que se reinicie</span><span class="sxs-lookup"><span data-stu-id="d52e8-104">To configure a package to restart</span></span>  
  
1.  <span data-ttu-id="d52e8-105">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="d52e8-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want to configure.</span></span>  
  
2.  <span data-ttu-id="d52e8-106">En el **Explorador de soluciones**, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="d52e8-106">In **Solution Explorer**, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="d52e8-107">Haga clic en la pestaña **Flujo de control** .</span><span class="sxs-lookup"><span data-stu-id="d52e8-107">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="d52e8-108">Haga clic con el botón derecho en cualquier parte del fondo de la superficie de diseño de flujo de control y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="d52e8-108">Right-click anywhere in the background of the control flow design surface, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="d52e8-109">Establezca la propiedad SaveCheckpoints en `True` .</span><span class="sxs-lookup"><span data-stu-id="d52e8-109">Set the SaveCheckpoints property to `True`.</span></span>  
  
6.  <span data-ttu-id="d52e8-110">Escriba el nombre del archivo de punto de comprobación en la propiedad CheckpointFileName.</span><span class="sxs-lookup"><span data-stu-id="d52e8-110">Type the name of the checkpoint file in the CheckpointFileName property.</span></span>  
  
7.  <span data-ttu-id="d52e8-111">Establezca la propiedad CheckpointUsage en uno de estos dos valores:</span><span class="sxs-lookup"><span data-stu-id="d52e8-111">Set the CheckpointUsage property to one of two values:</span></span>  
  
    -   <span data-ttu-id="d52e8-112">Seleccione `Always` para reiniciar siempre el paquete desde el punto de comprobación.</span><span class="sxs-lookup"><span data-stu-id="d52e8-112">Select `Always` to always restart the package from the checkpoint.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="d52e8-113">Si el archivo de punto de comprobación no está disponible se produce un error.</span><span class="sxs-lookup"><span data-stu-id="d52e8-113">An error occurs if the checkpoint file is not available.</span></span>  
  
    -   <span data-ttu-id="d52e8-114">Seleccione `IfExists` para reiniciar el paquete solo si está disponible el archivo de punto de comprobación.</span><span class="sxs-lookup"><span data-stu-id="d52e8-114">Select `IfExists` to restart the package only if the checkpoint file is available.</span></span>  
  
8.  <span data-ttu-id="d52e8-115">Configure las tareas y contenedores desde los cuales puede reiniciarse el paquete.</span><span class="sxs-lookup"><span data-stu-id="d52e8-115">Configure the tasks and containers from which the package can restart.</span></span>  
  
    -   <span data-ttu-id="d52e8-116">Haga clic con el botón derecho en una tarea o contenedor y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="d52e8-116">Right-click a task or container and click **Properties**.</span></span>  
  
    -   <span data-ttu-id="d52e8-117">Establezca la propiedad FailPackageOnFailure en `True` para cada tarea y contenedor seleccionados.</span><span class="sxs-lookup"><span data-stu-id="d52e8-117">Set the FailPackageOnFailure property to `True` for each selected task and container.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d52e8-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d52e8-118">See Also</span></span>  
 [<span data-ttu-id="d52e8-119">Reiniciar paquetes de usando puntos de comprobación</span><span class="sxs-lookup"><span data-stu-id="d52e8-119">Restart Packages by Using Checkpoints</span></span>](packages/restart-packages-by-using-checkpoints.md)  
  
  
