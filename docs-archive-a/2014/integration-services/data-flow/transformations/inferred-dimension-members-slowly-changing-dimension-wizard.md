---
title: Miembros de dimensión deducidos (Asistente para dimensiones de variación lenta) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.loaddimwizard.inferrdim.f1
ms.assetid: 809e395f-2e10-48ff-8860-56403f130628
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dda4345b91c69b134516baab2e5ba9b9990bd6af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676093"
---
# <a name="inferred-dimension-members-slowly-changing-dimension-wizard"></a><span data-ttu-id="9e65b-102">Miembros de dimensión deducidos (Asistente para dimensiones variables)</span><span class="sxs-lookup"><span data-stu-id="9e65b-102">Inferred Dimension Members (Slowly Changing Dimension Wizard)</span></span>
  <span data-ttu-id="9e65b-103">Utilice el cuadro de diálogo **Miembros de dimensión deducidos** para especificar opciones de la utilización de miembros deducidos.</span><span class="sxs-lookup"><span data-stu-id="9e65b-103">Use the **Inferred Dimension Members** dialog box to specify options for using inferred members.</span></span> <span data-ttu-id="9e65b-104">Los miembros deducidos existen cuando una tabla de hechos hace referencia a miembros de dimensión que todavía no se han cargado.</span><span class="sxs-lookup"><span data-stu-id="9e65b-104">Inferred members exist when a fact table references dimension members that are not yet loaded.</span></span> <span data-ttu-id="9e65b-105">Cuando se cargan datos del miembro deducido, se puede actualizar el registro existente en lugar de crear uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="9e65b-105">When data for the inferred member is loaded, you can update the existing record rather than create a new one.</span></span>  
  
 <span data-ttu-id="9e65b-106">Para obtener más información acerca de este asistente, vea [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="9e65b-106">To learn more about this wizard, see [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="9e65b-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="9e65b-107">Options</span></span>  
 <span data-ttu-id="9e65b-108">**Habilitar compatibilidad con miembros deducidos**</span><span class="sxs-lookup"><span data-stu-id="9e65b-108">**Enable inferred member support**</span></span>  
 <span data-ttu-id="9e65b-109">Si decide habilitar el uso de miembros deducidos, debe seleccionar una de las dos opciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="9e65b-109">If you choose to enable inferred members, you must select one of the two options that follow.</span></span>  
  
 <span data-ttu-id="9e65b-110">**Todas las columnas con un tipo de cambio son NULL**</span><span class="sxs-lookup"><span data-stu-id="9e65b-110">**All columns with a change type are null**</span></span>  
 <span data-ttu-id="9e65b-111">Especifique si escribe valores NULL en todas las columnas con un tipo de cambio en el nuevo registro de miembro deducido.</span><span class="sxs-lookup"><span data-stu-id="9e65b-111">Specify whether to enter null values in all columns with a change type in the new inferred member record.</span></span>  
  
 <span data-ttu-id="9e65b-112">**Usar una columna de tipo booleano para indicar si el registro actual es un miembro deducido**</span><span class="sxs-lookup"><span data-stu-id="9e65b-112">**Use a Boolean column to indicate whether the current record is an inferred member**</span></span>  
 <span data-ttu-id="9e65b-113">Especifique si desea utilizar una columna booleana existente para indicar si el registro actual es un miembro deducido.</span><span class="sxs-lookup"><span data-stu-id="9e65b-113">Specify whether to use an existing Boolean column to indicate whether the current record is an inferred member.</span></span>  
  
 <span data-ttu-id="9e65b-114">**Indicador de miembro deducido**</span><span class="sxs-lookup"><span data-stu-id="9e65b-114">**Inferred member indicator**</span></span>  
 <span data-ttu-id="9e65b-115">Si ha elegido utilizar una columna booleana para indicar los miembros deducidos, como se ha descrito en la opción anterior, seleccione la columna en la lista.</span><span class="sxs-lookup"><span data-stu-id="9e65b-115">If you have chosen to use a Boolean column to indicate inferred members as described above, select the column from the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e65b-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9e65b-116">See Also</span></span>  
 [<span data-ttu-id="9e65b-117">Configuración de salidas con el Asistente para dimensiones de variación lenta</span><span class="sxs-lookup"><span data-stu-id="9e65b-117">Configure Outputs Using the Slowly Changing Dimension Wizard</span></span>](configure-outputs-using-the-slowly-changing-dimension-wizard.md)  
  
  
