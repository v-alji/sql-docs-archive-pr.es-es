---
title: Columnas de dimensiones de variación lenta (Asistente para dimensiones de variación lenta) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.loaddimwizard.scdsupport.f1
ms.assetid: 36de99d5-5368-48e0-b876-17e9c6862c6c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6283887cbddb9844e0ac769281184f588dc2a94d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744212"
---
# <a name="slowly-changing-dimension-columns-slowly-changing-dimension-wizard"></a><span data-ttu-id="26ad7-102">Columnas de dimensión variable lenta (Asistente para dimensiones variables)</span><span class="sxs-lookup"><span data-stu-id="26ad7-102">Slowly Changing Dimension Columns (Slowly Changing Dimension Wizard)</span></span>
  <span data-ttu-id="26ad7-103">Utilice el cuadro de diálogo **Columnas de dimensión variable** para seleccionar un tipo de cambio para cada una de las columnas de dimensión variable lenta.</span><span class="sxs-lookup"><span data-stu-id="26ad7-103">Use the **Slowly Changing Dimensions Columns** dialog box to select a change type for each slowly changing dimension column.</span></span>  
  
 <span data-ttu-id="26ad7-104">Para obtener más información acerca de este asistente, vea [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="26ad7-104">To learn more about this wizard, see [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="26ad7-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="26ad7-105">Options</span></span>  
 <span data-ttu-id="26ad7-106">**Columnas de dimensión**</span><span class="sxs-lookup"><span data-stu-id="26ad7-106">**Dimension Columns**</span></span>  
 <span data-ttu-id="26ad7-107">Seleccione una columna de dimensión de la lista.</span><span class="sxs-lookup"><span data-stu-id="26ad7-107">Select a dimension column from the list.</span></span>  
  
 <span data-ttu-id="26ad7-108">**Tipo de cambio**</span><span class="sxs-lookup"><span data-stu-id="26ad7-108">**Change Type**</span></span>  
 <span data-ttu-id="26ad7-109">Seleccione un **Atributo fijo**o seleccione uno de los dos tipos de atributos variables.</span><span class="sxs-lookup"><span data-stu-id="26ad7-109">Select a **Fixed Attribute**, or select one of the two types of changing attributes.</span></span> <span data-ttu-id="26ad7-110">Utilice **Atributo fijo** cuando el valor de una columna no tenga que cambiar; [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] tratará entonces los cambios como errores.</span><span class="sxs-lookup"><span data-stu-id="26ad7-110">Use **Fixed Attribute** when the value in a column should not change; [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] then treats changes as errors.</span></span> <span data-ttu-id="26ad7-111">Utilice **Atributo variable** para sobrescribir los valores existentes con los valores modificados.</span><span class="sxs-lookup"><span data-stu-id="26ad7-111">Use **Changing Attribute** to overwrite existing values with changed values.</span></span> <span data-ttu-id="26ad7-112">Utilice **Atributo histórico** para guardar los valores modificados en nuevos registros, al tiempo que los registros anteriores quedan marcados como desusados.</span><span class="sxs-lookup"><span data-stu-id="26ad7-112">Use **Historical Attribute** to save changed values in new records, while marking previous records as outdated.</span></span>  
  
 <span data-ttu-id="26ad7-113">**Remove**</span><span class="sxs-lookup"><span data-stu-id="26ad7-113">**Remove**</span></span>  
 <span data-ttu-id="26ad7-114">Seleccione una columna de dimensión y quítela de la lista de columnas asignadas haciendo clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="26ad7-114">Select a dimension column, and remove it from the list of mapped columns by clicking **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26ad7-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="26ad7-115">See Also</span></span>  
 [<span data-ttu-id="26ad7-116">Configuración de salidas con el Asistente para dimensiones de variación lenta</span><span class="sxs-lookup"><span data-stu-id="26ad7-116">Configure Outputs Using the Slowly Changing Dimension Wizard</span></span>](configure-outputs-using-the-slowly-changing-dimension-wizard.md)  
  
  
