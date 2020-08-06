---
title: Opciones de atributos históricos (Asistente para dimensiones de variación lenta) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.loaddimwizard.histattriboption.f1
ms.assetid: a176ec66-ec39-4c99-99d1-c1afa8450e1e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fad005d6b8f80973abeb47dd881ef02b669d7b27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676103"
---
# <a name="historical-attribute-options-slowly-changing-dimension-wizard"></a><span data-ttu-id="9c038-102">Opciones de atributos históricos (Asistente para dimensiones variables)</span><span class="sxs-lookup"><span data-stu-id="9c038-102">Historical Attribute Options (Slowly Changing Dimension Wizard)</span></span>
  <span data-ttu-id="9c038-103">Utilice el cuadro de diálogo **Opciones de atributos históricos** para mostrar los atributos históricos por fechas de inicio y finalización, o bien para registrar atributos históricos en una columna creada especialmente con este fin.</span><span class="sxs-lookup"><span data-stu-id="9c038-103">Use the **Historical Attributes Options** dialog box to show historical attributes by start and end dates, or to record historical attributes in a column specially created for this purpose.</span></span>  
  
 <span data-ttu-id="9c038-104">Para obtener más información acerca de este asistente, vea [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="9c038-104">To learn more about this wizard, see [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="9c038-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="9c038-105">Options</span></span>  
 <span data-ttu-id="9c038-106">**Utilice una única columna para mostrar los registros actual y expirado**</span><span class="sxs-lookup"><span data-stu-id="9c038-106">**Use a single column to show current and expired records**</span></span>  
 <span data-ttu-id="9c038-107">Si decide utilizar una sola columna para registrar el estado de los atributos históricos, dispone de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="9c038-107">If you choose to use a single column to record the status of historical attributes, the following options are available:</span></span>  
  
|<span data-ttu-id="9c038-108">Opción</span><span class="sxs-lookup"><span data-stu-id="9c038-108">Option</span></span>|<span data-ttu-id="9c038-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="9c038-109">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="9c038-110">**Columna para indicar el registro actual**</span><span class="sxs-lookup"><span data-stu-id="9c038-110">**Column to indicate current record**</span></span>|<span data-ttu-id="9c038-111">Seleccione una columna donde se va a indicar el registro actual.</span><span class="sxs-lookup"><span data-stu-id="9c038-111">Select a column in which to indicate the current record.</span></span>|  
|<span data-ttu-id="9c038-112">**Valor actual**</span><span class="sxs-lookup"><span data-stu-id="9c038-112">**Value when current**</span></span>|<span data-ttu-id="9c038-113">Utilice **True** o **Current** para indicar si el registro es actual.</span><span class="sxs-lookup"><span data-stu-id="9c038-113">Use either **True** or **Current** to show whether the record is current.</span></span>|  
|<span data-ttu-id="9c038-114">**Valor de expiración**</span><span class="sxs-lookup"><span data-stu-id="9c038-114">**Expiration value**</span></span>|<span data-ttu-id="9c038-115">Utilice **False** o **Expired** para indicar si el registro es un valor histórico.</span><span class="sxs-lookup"><span data-stu-id="9c038-115">Use either **False** or **Expired** to show whether the record is a historical value.</span></span>|  
  
 <span data-ttu-id="9c038-116">**Utilice las fechas inicial y final para identificar los registros actual y expirado**</span><span class="sxs-lookup"><span data-stu-id="9c038-116">**Use start and end dates to identify current and expired records**</span></span>  
 <span data-ttu-id="9c038-117">La tabla de dimensiones de esta opción debe incluir una columna de fecha.</span><span class="sxs-lookup"><span data-stu-id="9c038-117">The dimension table for this option must include a date column.</span></span> <span data-ttu-id="9c038-118">Si decide mostrar los atributos históricos por fechas de inicio y finalización, dispone de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="9c038-118">If you choose to show historical attributes by start and end dates, the following options are available:</span></span>  
  
|<span data-ttu-id="9c038-119">Opción</span><span class="sxs-lookup"><span data-stu-id="9c038-119">Option</span></span>|<span data-ttu-id="9c038-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="9c038-120">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="9c038-121">**Columna de fecha inicial**</span><span class="sxs-lookup"><span data-stu-id="9c038-121">**Start date column**</span></span>|<span data-ttu-id="9c038-122">Seleccione en la tabla de dimensiones la columna que contiene la fecha inicial.</span><span class="sxs-lookup"><span data-stu-id="9c038-122">Select the column in the dimension table to contain the start date.</span></span>|  
|<span data-ttu-id="9c038-123">**Columna de fecha final**</span><span class="sxs-lookup"><span data-stu-id="9c038-123">**End date column**</span></span>|<span data-ttu-id="9c038-124">Seleccione en la tabla de dimensiones la columna que contiene la fecha final.</span><span class="sxs-lookup"><span data-stu-id="9c038-124">Select the column in the dimension table to contain the end date.</span></span>|  
|<span data-ttu-id="9c038-125">**Variable para establecer valores de fecha**</span><span class="sxs-lookup"><span data-stu-id="9c038-125">**Variable to set date values**</span></span>|<span data-ttu-id="9c038-126">Seleccione una variable de fecha de la lista.</span><span class="sxs-lookup"><span data-stu-id="9c038-126">Select a date variable from the list.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9c038-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9c038-127">See Also</span></span>  
 [<span data-ttu-id="9c038-128">Configuración de salidas con el Asistente para dimensiones de variación lenta</span><span class="sxs-lookup"><span data-stu-id="9c038-128">Configure Outputs Using the Slowly Changing Dimension Wizard</span></span>](configure-outputs-using-the-slowly-changing-dimension-wizard.md)  
  
  
