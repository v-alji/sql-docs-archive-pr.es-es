---
title: Dirigir el flujo CDC según el tipo de cambio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 3afa531e-f425-40a4-a1bf-1c3e1727287e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4a9b4e0c6a196669e4cedafcecf0477b228f3001
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670486"
---
# <a name="direct-the-cdc-stream-according-to-the-type-of-change"></a><span data-ttu-id="fde39-102">Dirigir el flujo CDC según el tipo de cambio</span><span class="sxs-lookup"><span data-stu-id="fde39-102">Direct the CDC Stream According to the Type of Change</span></span>
  <span data-ttu-id="fde39-103">Para agregar y configurar una transformación Divisor CDC, el paquete debe contener por lo menos una tarea Flujo de datos y un origen de CDC.</span><span class="sxs-lookup"><span data-stu-id="fde39-103">To add and configure a CDC splitter Transformation, the package must contain at least one Data Flow task and a CDC source.</span></span>  
  
 <span data-ttu-id="fde39-104">El origen de CDC agregado al paquete debe tener seleccionado un modo de procesamiento de NetCDC.</span><span class="sxs-lookup"><span data-stu-id="fde39-104">The CDC source added to the package must have a NetCDC processing mode selected.</span></span> <span data-ttu-id="fde39-105">Para obtener más información sobre cómo seleccionar los modos de procesamiento, vea [Editor de origen de CDC &#40;página Administrador de conexiones&#41;](../cdc-source-editor-connection-manager-page.md).</span><span class="sxs-lookup"><span data-stu-id="fde39-105">For more information on selecting processing modes, see [CDC Source Editor &#40;Connection Manager Page&#41;](../cdc-source-editor-connection-manager-page.md).</span></span>  
  
### <a name="to-direct-the-cdc-stream-according-to-the-type-of-change"></a><span data-ttu-id="fde39-106">Para dirigir el flujo CDC según el tipo de cambio</span><span class="sxs-lookup"><span data-stu-id="fde39-106">To direct the CDC stream according to the type of change</span></span>  
  
1.  <span data-ttu-id="fde39-107">En [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], abra el proyecto de [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="fde39-107">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="fde39-108">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="fde39-108">In the Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="fde39-109">Haga clic en la pestaña **Flujo de datos** y, a continuación, desde el **cuadro de herramientas**, arrastre el divisor CDC a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="fde39-109">Click the **Data Flow** tab, and then from the **Toolbox**, drag the CDC splitter to the design surface.</span></span>  
  
4.  <span data-ttu-id="fde39-110">Conéctese al origen de CDC que se incluye en el paquete al divisor CDC.</span><span class="sxs-lookup"><span data-stu-id="fde39-110">Connect the CDC source that is included in the package to the CDC Splitter.</span></span>  
  
5.  <span data-ttu-id="fde39-111">Conecte el divisor CDC a uno o varios destinos.</span><span class="sxs-lookup"><span data-stu-id="fde39-111">Connect the CDC splitter to one or more destinations.</span></span> <span data-ttu-id="fde39-112">Puede conectarse hasta a tres salidas diferentes.</span><span class="sxs-lookup"><span data-stu-id="fde39-112">You can connect up to three different outputs.</span></span>  
  
6.  <span data-ttu-id="fde39-113">Seleccione una de las siguientes salidas:</span><span class="sxs-lookup"><span data-stu-id="fde39-113">Select one of the following outputs:</span></span>  
  
    -   <span data-ttu-id="fde39-114">Salida Delete: la salida donde se dirigen las filas de cambios DELETE.</span><span class="sxs-lookup"><span data-stu-id="fde39-114">Delete output: The output where DELETE change rows are directed.</span></span>  
  
    -   <span data-ttu-id="fde39-115">Salida Insert: la salida donde se dirigen las filas de cambios INSERT.</span><span class="sxs-lookup"><span data-stu-id="fde39-115">Insert output: The output where INSERT change rows are directed.</span></span>  
  
    -   <span data-ttu-id="fde39-116">Salida Update: la salida donde se dirigen las filas de cambios UPDATE antes o después y las filas de cambios Merge.</span><span class="sxs-lookup"><span data-stu-id="fde39-116">Update output: The output where before/after UPDATE change rows and Merge change rows are directed.</span></span>  
  
7.  <span data-ttu-id="fde39-117">Opcionalmente, puede configurar las propiedades avanzadas mediante el cuadro de diálogo **Editor avanzado** .</span><span class="sxs-lookup"><span data-stu-id="fde39-117">Optionally, you can configure the advanced properties using the **Advanced Editor** dialog box.</span></span>  
  
     <span data-ttu-id="fde39-118">El cuadro de diálogo **Editor avanzado** contiene las propiedades que se pueden establecer mediante programación.</span><span class="sxs-lookup"><span data-stu-id="fde39-118">The **Advanced Editor** dialog box contains the properties that can be set programmatically.</span></span>  
  
     <span data-ttu-id="fde39-119">Para abrir el cuadro de diálogo **Editor avanzado** :</span><span class="sxs-lookup"><span data-stu-id="fde39-119">To open the **Advanced Editor** dialog box:</span></span>  
  
    -   <span data-ttu-id="fde39-120">En la pantalla **Flujo de datos** del proyecto de [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] , haga clic con el botón secundario en el divisor CDC y seleccione **Mostrar editor avanzado**.</span><span class="sxs-lookup"><span data-stu-id="fde39-120">In the **Data Flow** screen of your [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] project, right click the CDC splitter and select **Show Advanced Editor**.</span></span>  
  
     <span data-ttu-id="fde39-121">Para obtener más información sobre cómo usar el divisor CDC, vea Componentes CDC para Microsoft SQL Server Integration Services.</span><span class="sxs-lookup"><span data-stu-id="fde39-121">For more information about using the CDC splitter see CDC Components for Microsoft SQL Server Integration Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fde39-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fde39-122">See Also</span></span>  
 [<span data-ttu-id="fde39-123">Divisor CDC</span><span class="sxs-lookup"><span data-stu-id="fde39-123">CDC Splitter</span></span>](cdc-splitter.md)  
  
  
