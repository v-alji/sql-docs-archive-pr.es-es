---
title: Habilitar/deshabilitar reescritura (cuadro de diálogo) (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitiondesigner.writebackenabledisable.f1
ms.assetid: 2d254393-3f0d-4b70-8b98-87159f9f3639
author: minewiskan
ms.author: owend
ms.openlocfilehash: 54ee4597ee78f45682730bd0e8d7119d204eaf2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677922"
---
# <a name="enable-disable-writeback-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="da913-102">Habilitar/deshabilitar reescritura (cuadro de diálogo) (Analysis Services-datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="da913-102">Enable-Disable Writeback Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="da913-103">El cuadro de diálogo **Habilitar/deshabilitar reescritura** permite habilitar o deshabilitar la reescritura para un grupo de medida en un cubo.</span><span class="sxs-lookup"><span data-stu-id="da913-103">The **Enable/Disable Writeback** dialog box enables or disables writeback for a measure group in a cube.</span></span> <span data-ttu-id="da913-104">Al habilitar la reescritura en un grupo de medida se define una partición de reescritura y se crea una tabla de reescritura para ese grupo de medida.</span><span class="sxs-lookup"><span data-stu-id="da913-104">Enabling writeback on a measure group defines a writeback partition and creates a writeback table for that measure group.</span></span> <span data-ttu-id="da913-105">Al deshabilitar la reescritura en un grupo de medida se quita la partición de reescritura, pero no se elimina la tabla de reescritura a fin de evitar la pérdida imprevista de datos.</span><span class="sxs-lookup"><span data-stu-id="da913-105">Disabling writeback on a measure group removes the writeback partition but does not delete the writeback table, to avoid unanticipated data loss.</span></span> <span data-ttu-id="da913-106">Para mostrar el cuadro de diálogo **Habilitar/deshabilitar reescritura** :</span><span class="sxs-lookup"><span data-stu-id="da913-106">The **Enable/Disable Writeback** dialog box is displayed by:</span></span>  
  
-   <span data-ttu-id="da913-107">En el Diseñador de cubos, haga clic en **Configuración de reescritura** (en el panel **Grupos de medida** de la pestaña **Particiones** ).</span><span class="sxs-lookup"><span data-stu-id="da913-107">Clicking **Writeback Settings** in the **Measure Groups** pane on the **Partitions** tab in Cube Designer.</span></span>  
  
-   <span data-ttu-id="da913-108">En el Diseñador de cubos, haga clic con el botón derecho en una partición de la cuadrícula **Particiones** (en el panel **Grupos de medida** de la pestaña **Particiones** ) y, después, seleccione **Configuración de reescritura** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="da913-108">Right-clicking a partition in the **Partitions** grid in the **Measure Groups** pane on the **Partitions** tab in Cube Designer and selecting **Writeback Settings** from the context menu.</span></span>  
  
## <a name="options"></a><span data-ttu-id="da913-109">Opciones</span><span class="sxs-lookup"><span data-stu-id="da913-109">Options</span></span>  
 <span data-ttu-id="da913-110">**Nombre de la tabla**</span><span class="sxs-lookup"><span data-stu-id="da913-110">**Table name**</span></span>  
 <span data-ttu-id="da913-111">Escriba el nombre de la tabla de reescritura que desea crear para la partición seleccionada.</span><span class="sxs-lookup"><span data-stu-id="da913-111">Type the name of the writeback table to create for the selected partition.</span></span> <span data-ttu-id="da913-112">La tabla de escritura diferida almacena los cambios realizados al grupo de medidas desde una aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="da913-112">The writeback table stores the changes made to the measure group from a client application.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="da913-113">Esta opción está deshabilitada si la reescritura no está habilitada.</span><span class="sxs-lookup"><span data-stu-id="da913-113">This option is disabled if writeback is not enabled.</span></span>  
  
 <span data-ttu-id="da913-114">**Origen de datos**</span><span class="sxs-lookup"><span data-stu-id="da913-114">**Data source**</span></span>  
 <span data-ttu-id="da913-115">Seleccione el origen de datos que contendrá la tabla de reescritura.</span><span class="sxs-lookup"><span data-stu-id="da913-115">Select the data source to contain the writeback table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="da913-116">Esta opción está deshabilitada si la reescritura no está habilitada.</span><span class="sxs-lookup"><span data-stu-id="da913-116">This option is disabled if writeback is not enabled.</span></span>  
  
 <span data-ttu-id="da913-117">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="da913-117">**New**</span></span>  
 <span data-ttu-id="da913-118">Haga clic para mostrar el cuadro de diálogo **Administrador de conexiones** y defina un nuevo origen de datos para que contenga la tabla de reescritura.</span><span class="sxs-lookup"><span data-stu-id="da913-118">Click to display the **Connection Manager** dialog box and define a new data source to contain the writeback table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="da913-119">Esta opción está deshabilitada si la reescritura no está habilitada.</span><span class="sxs-lookup"><span data-stu-id="da913-119">This option is disabled if writeback is not enabled.</span></span>  
  
  
