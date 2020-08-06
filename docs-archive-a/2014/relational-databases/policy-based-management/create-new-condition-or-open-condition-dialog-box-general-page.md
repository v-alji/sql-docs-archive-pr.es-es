---
title: Cuadro de diálogo Crear nueva condición o Abrir condición, página General | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.condition.f1
ms.assetid: 106954bf-e4ba-412b-9c1a-907d06153dcd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 72e4a77df553ac8e97609e82bd51c8fd93b64b23
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677597"
---
# <a name="create-new-condition-or-open-condition-dialog-box-general-page"></a><span data-ttu-id="df031-102">Cuadro de diálogo Crear nueva condición o Abrir condición, página General</span><span class="sxs-lookup"><span data-stu-id="df031-102">Create New Condition or Open Condition Dialog Box, General Page</span></span>
  <span data-ttu-id="df031-103">Utilice este cuadro de diálogo para crear o cambiar una condición de la administración basada en directivas.</span><span class="sxs-lookup"><span data-stu-id="df031-103">Use this dialog box to create or change a Policy-Based Management condition.</span></span> <span data-ttu-id="df031-104">Una condición es una expresión booleana que especifica un conjunto de estados permitidos de un destino administrado mediante la administración basada en directivas con respecto a las facetas.</span><span class="sxs-lookup"><span data-stu-id="df031-104">A condition is a Boolean expression that specifies a set of allowed states of a Policy-Based Management managed target with regard to facets.</span></span> <span data-ttu-id="df031-105">Las propiedades que se pueden seleccionar en el cuadro **Expresión/Campo** dependen de la faceta que se use.</span><span class="sxs-lookup"><span data-stu-id="df031-105">The properties that can be selected in the **Expression/Field** box depend upon the facet that is used.</span></span> <span data-ttu-id="df031-106">Para obtener más información sobre cómo se relacionan las condiciones con las facetas y las directivas, vea [Administrar servidores mediante administración basada en directivas](administer-servers-by-using-policy-based-management.md).</span><span class="sxs-lookup"><span data-stu-id="df031-106">For more information about how conditions relate to facets and policies, see [Administer Servers by Using Policy-Based Management](administer-servers-by-using-policy-based-management.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="df031-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="df031-107">Options</span></span>  
 <span data-ttu-id="df031-108">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="df031-108">**Name**</span></span>  
 <span data-ttu-id="df031-109">Si la condición es nueva, escriba un nombre para ella.</span><span class="sxs-lookup"><span data-stu-id="df031-109">For a new condition, type the new condition name.</span></span> <span data-ttu-id="df031-110">Si la condición ya existe, se muestra el nombre.</span><span class="sxs-lookup"><span data-stu-id="df031-110">For an existing condition, the name is displayed.</span></span>  
  
 <span data-ttu-id="df031-111">**Faceta**</span><span class="sxs-lookup"><span data-stu-id="df031-111">**Facet**</span></span>  
 <span data-ttu-id="df031-112">Faceta usada por esta condición.</span><span class="sxs-lookup"><span data-stu-id="df031-112">The facet used by this condition.</span></span>  
  
 <span data-ttu-id="df031-113">**Y/O**</span><span class="sxs-lookup"><span data-stu-id="df031-113">**AndOr**</span></span>  
 <span data-ttu-id="df031-114">Al agregar varias expresiones, indica si las expresiones deben combinarse con **AND** u **OR**.</span><span class="sxs-lookup"><span data-stu-id="df031-114">When you add multiple expressions, indicates whether the expressions should be joined by using **And** or **Or**.</span></span> <span data-ttu-id="df031-115">Permanece en blanco cuando solo hay una expresión.</span><span class="sxs-lookup"><span data-stu-id="df031-115">Remains blank when there is only one expression.</span></span>  
  
 <span data-ttu-id="df031-116">**Campo**</span><span class="sxs-lookup"><span data-stu-id="df031-116">**Field**</span></span>  
 <span data-ttu-id="df031-117">Cada faceta expone una o varias propiedades que se pueden establecer.</span><span class="sxs-lookup"><span data-stu-id="df031-117">Each facet exposes one or more properties that can be set.</span></span> <span data-ttu-id="df031-118">En el cuadro de campo, seleccione una propiedad de la lista de propiedades disponibles para crear una expresión para esta condición.</span><span class="sxs-lookup"><span data-stu-id="df031-118">In the field box, select a property from the list of available properties to create an expression for this condition.</span></span>  
  
 <span data-ttu-id="df031-119">**Operador**</span><span class="sxs-lookup"><span data-stu-id="df031-119">**Operator**</span></span>  
 <span data-ttu-id="df031-120">Seleccione un operador de comparación para esta expresión.</span><span class="sxs-lookup"><span data-stu-id="df031-120">Select a comparison operator for this expression.</span></span> <span data-ttu-id="df031-121">Los operadores son: =, !=, >, >=, <, <=, [NOT]LIKE, [NOT]IN.</span><span class="sxs-lookup"><span data-stu-id="df031-121">Operators are as follows: =, !=, >, >=, <, <=, [NOT]LIKE, [NOT]IN.</span></span> <span data-ttu-id="df031-122">No todos los operadores están disponibles para algunas propiedades.</span><span class="sxs-lookup"><span data-stu-id="df031-122">Not all operators are available for some properties.</span></span>  
  
 <span data-ttu-id="df031-123">**Valor**</span><span class="sxs-lookup"><span data-stu-id="df031-123">**Value**</span></span>  
 <span data-ttu-id="df031-124">Configuración del valor para esta expresión.</span><span class="sxs-lookup"><span data-stu-id="df031-124">The value setting for this expression.</span></span> <span data-ttu-id="df031-125">Los valores permitidos dependen de la faceta.</span><span class="sxs-lookup"><span data-stu-id="df031-125">The allowed values depend on the facet.</span></span> <span data-ttu-id="df031-126">Los valores pueden ser TRUE/FALSE, de tipo cadena o de tipo numérico.</span><span class="sxs-lookup"><span data-stu-id="df031-126">Values can be TRUE/FALSE, string, or numeric.</span></span> <span data-ttu-id="df031-127">Los valores de tipo cadena se deben incluir entre comillas sencillas, por ejemplo: **'AdventureWorks'**.</span><span class="sxs-lookup"><span data-stu-id="df031-127">String values must be enclosed in single quotation marks, for example: **'AdventureWorks'**.</span></span> <span data-ttu-id="df031-128">No todos los operadores están disponibles para algunas propiedades.</span><span class="sxs-lookup"><span data-stu-id="df031-128">Not all operators are available for some properties.</span></span>  
  
## <a name="group-clauses"></a><span data-ttu-id="df031-129">Agrupar cláusulas</span><span class="sxs-lookup"><span data-stu-id="df031-129">Group Clauses</span></span>  
 <span data-ttu-id="df031-130">Las cláusulas se pueden agrupar para que operen como una sola unidad independiente del resto de la consulta; el resultado es similar al que se obtiene colocando unos paréntesis en torno a una expresión en una ecuación matemática o una instrucción lógica.</span><span class="sxs-lookup"><span data-stu-id="df031-130">Clauses can be grouped to operate as a single unit separate from the rest of the query, just like putting parentheses around an expression in a mathematical equation or logic statement.</span></span> <span data-ttu-id="df031-131">La agrupación de cláusulas resulta útil cuando se crean consultas complejas.</span><span class="sxs-lookup"><span data-stu-id="df031-131">Grouping clauses is useful when you are building complex queries.</span></span>  
  
 <span data-ttu-id="df031-132">**Para agrupar cláusulas**</span><span class="sxs-lookup"><span data-stu-id="df031-132">**To group clauses**</span></span>  
  
-   <span data-ttu-id="df031-133">Presione la tecla Mayús o Ctrl, y a continuación haga clic en dos o más cláusulas para seleccionar un intervalo.</span><span class="sxs-lookup"><span data-stu-id="df031-133">Press the SHIFT or CTRL keys, and then click two or more clauses to select a range.</span></span> <span data-ttu-id="df031-134">Haga clic con el botón derecho en el área seleccionada y luego haga clic en **Agrupar cláusulas**.</span><span class="sxs-lookup"><span data-stu-id="df031-134">Right-click the selected area, and then click **Group Clauses**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df031-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="df031-135">See Also</span></span>  
 [<span data-ttu-id="df031-136">Administrar servidores mediante administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="df031-136">Administer Servers by Using Policy-Based Management</span></span>](administer-servers-by-using-policy-based-management.md)  
  
  
