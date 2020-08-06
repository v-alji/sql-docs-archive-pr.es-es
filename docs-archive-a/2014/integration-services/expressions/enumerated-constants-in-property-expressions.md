---
title: Constantes enumeradas en expresiones de propiedad | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- enumerators [Integration Services]
- packages [Integration Services], expressions
- dynamic properties
- updating package properties
- enumerated constants [Integration Services]
- property expressions [Integration Services]
ms.assetid: a4418315-38e2-4ad3-8784-576163b25d6f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b9cb4ae32bf564e98d8cfc843e9497b15222fa79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746389"
---
# <a name="enumerated-constants-in-property-expressions"></a><span data-ttu-id="c4073-102">Constantes enumeradas en expresiones de propiedad</span><span class="sxs-lookup"><span data-stu-id="c4073-102">Enumerated Constants in Property Expressions</span></span>
  <span data-ttu-id="c4073-103">Si las expresiones de propiedad incluyen valores de una lista de miembros enumeradores, la expresión debe utilizar el valor numérico del miembro enumerador en lugar del nombre descriptivo del miembro.</span><span class="sxs-lookup"><span data-stu-id="c4073-103">If property expressions include values from an enumerator member list, the expression must use the numeric value of the enumerator member instead of the friendly name of the member.</span></span> <span data-ttu-id="c4073-104">Por ejemplo, si una expresión establece la propiedad `LoggingMode`, debe utilizar el valor 2 en lugar del nombre descriptivo Deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="c4073-104">For example, if an expression sets the `LoggingMode` property then you must use the numeric value 2 instead of the friendly name Disabled.</span></span>  
  
 <span data-ttu-id="c4073-105">Este tema enumera solo los valores numéricos equivalentes a los nombres descriptivos de los enumeradores cuyos miembros se utilizan generalmente en expresiones de propiedad.</span><span class="sxs-lookup"><span data-stu-id="c4073-105">This topic lists only the numeric values equivalent to friendly names of enumerators whose members are commonly used in property expressions.</span></span> <span data-ttu-id="c4073-106">El modelo de objetos [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] incluye varios enumeradores adicionales que puede utilizar cuando programa el modelo de objetos para generar paquetes mediante programación o elementos de paquete de código personalizado tales como tareas y componentes de flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="c4073-106">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] object model includes many additional enumerators that you use when you program the object model to build packages programmatically or code custom package elements such as tasks and data flow components.</span></span>  
  
 <span data-ttu-id="c4073-107">Además de las propiedades personalizadas de los paquetes y objetos de paquetes, la ventana Propiedades de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] incluye un conjunto de propiedades disponibles para paquetes, tareas, y los contenedores de secuencias, de bucles Foreach y de bucles For.</span><span class="sxs-lookup"><span data-stu-id="c4073-107">In addition to the custom properties for packages and package objects, the Properties window in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] includes a set of properties that are available to packages, tasks, and the Foreach Loop, For Loop, and Sequence containers.</span></span> <span data-ttu-id="c4073-108">Las propiedades comunes que se establecen mediante los valores de enumeradores (, `ForceExecutionResult` `LoggingMode` , `IsolationLevel` y `Transaction Option` ) se enumeran en la sección Propiedades comunes.</span><span class="sxs-lookup"><span data-stu-id="c4073-108">The common properties that are set by values from enumerators-`ForceExecutionResult`, `LoggingMode`, `IsolationLevel`, and `Transaction Option`-are listed in Common Properties section.</span></span>  
  
 <span data-ttu-id="c4073-109">Las siguientes secciones proporcionan información sobre constantes enumeradas:</span><span class="sxs-lookup"><span data-stu-id="c4073-109">The following sections provide information about enumerated constants:</span></span>  
  
 [<span data-ttu-id="c4073-110">Package</span><span class="sxs-lookup"><span data-stu-id="c4073-110">Package</span></span>](#Package)  
  
 [<span data-ttu-id="c4073-111">Enumeradores de bucle Foreach</span><span class="sxs-lookup"><span data-stu-id="c4073-111">Foreach Loop Enumerators</span></span>](#Foreach)  
  
 [<span data-ttu-id="c4073-112">Tareas</span><span class="sxs-lookup"><span data-stu-id="c4073-112">Tasks</span></span>](#Tasks)  
  
 [<span data-ttu-id="c4073-113">Tareas del plan de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="c4073-113">Maintenance Plan Tasks</span></span>](#MaintenancePlanTasks)  
  
 [<span data-ttu-id="c4073-114">Common Properties</span><span class="sxs-lookup"><span data-stu-id="c4073-114">Common Properties</span></span>](#CommonProperties)  
  
##  <a name="package"></a><a name="Package"></a> <span data-ttu-id="c4073-115">Paquete</span><span class="sxs-lookup"><span data-stu-id="c4073-115">Package</span></span>  
 <span data-ttu-id="c4073-116">Las siguientes tablas enumeran los nombres descriptivos y los equivalentes de valores numéricos de las propiedades de paquetes que se establecen utilizando valores de un enumerador.</span><span class="sxs-lookup"><span data-stu-id="c4073-116">The following tables lists the friendly names and the numeric value equivalents for properties of packages that you set by using values from an enumerator.</span></span>  
  
 <span data-ttu-id="c4073-117">`PackageType`propiedad: se establece mediante el uso de valores de la `DTSPackageType` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-117">`PackageType` property-Set by using values from the `DTSPackageType` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-118">Nombre descriptivo en DTSPackageType</span><span class="sxs-lookup"><span data-stu-id="c4073-118">Friendly name in DTSPackageType</span></span>|<span data-ttu-id="c4073-119">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-119">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="c4073-120">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="c4073-120">Default</span></span>|<span data-ttu-id="c4073-121">0</span><span class="sxs-lookup"><span data-stu-id="c4073-121">0</span></span>|  
|<span data-ttu-id="c4073-122">DTSWizard</span><span class="sxs-lookup"><span data-stu-id="c4073-122">DTSWizard</span></span>|<span data-ttu-id="c4073-123">1</span><span class="sxs-lookup"><span data-stu-id="c4073-123">1</span></span>|  
|<span data-ttu-id="c4073-124">DTSDesigner</span><span class="sxs-lookup"><span data-stu-id="c4073-124">DTSDesigner</span></span>|<span data-ttu-id="c4073-125">2</span><span class="sxs-lookup"><span data-stu-id="c4073-125">2</span></span>|  
|<span data-ttu-id="c4073-126">SQLReplication</span><span class="sxs-lookup"><span data-stu-id="c4073-126">SQLReplication</span></span>|<span data-ttu-id="c4073-127">3</span><span class="sxs-lookup"><span data-stu-id="c4073-127">3</span></span>|  
|<span data-ttu-id="c4073-128">DTSDesigner100</span><span class="sxs-lookup"><span data-stu-id="c4073-128">DTSDesigner100</span></span>|<span data-ttu-id="c4073-129">5</span><span class="sxs-lookup"><span data-stu-id="c4073-129">5</span></span>|  
|<span data-ttu-id="c4073-130">SQLDBMaint</span><span class="sxs-lookup"><span data-stu-id="c4073-130">SQLDBMaint</span></span>|<span data-ttu-id="c4073-131">6</span><span class="sxs-lookup"><span data-stu-id="c4073-131">6</span></span>|  
  
 <span data-ttu-id="c4073-132">`CheckpointUsage`propiedad: se establece mediante el uso de valores de la `DTSCheckpointUsage` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-132">`CheckpointUsage` property-Set by using values from the `DTSCheckpointUsage` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-133">Nombre descriptivo en DTSCheckpointUsage</span><span class="sxs-lookup"><span data-stu-id="c4073-133">Friendly name in DTSCheckpointUsage</span></span>|<span data-ttu-id="c4073-134">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-134">Numeric value</span></span>|  
|-----------------------------------------|-------------------|  
|<span data-ttu-id="c4073-135">Nunca</span><span class="sxs-lookup"><span data-stu-id="c4073-135">Never</span></span>|<span data-ttu-id="c4073-136">0</span><span class="sxs-lookup"><span data-stu-id="c4073-136">0</span></span>|  
|<span data-ttu-id="c4073-137">IfExists</span><span class="sxs-lookup"><span data-stu-id="c4073-137">IfExists</span></span>|<span data-ttu-id="c4073-138">1</span><span class="sxs-lookup"><span data-stu-id="c4073-138">1</span></span>|  
|<span data-ttu-id="c4073-139">Siempre</span><span class="sxs-lookup"><span data-stu-id="c4073-139">Always</span></span>|<span data-ttu-id="c4073-140">2</span><span class="sxs-lookup"><span data-stu-id="c4073-140">2</span></span>|  
  
 <span data-ttu-id="c4073-141">`PackagePriorityClass`propiedad: se establece mediante el uso de valores de la `DTSPriorityClass` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-141">`PackagePriorityClass` property-Set by using values from the `DTSPriorityClass` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-142">Nombre descriptivo en DTSPriorityClass</span><span class="sxs-lookup"><span data-stu-id="c4073-142">Friendly name in DTSPriorityClass</span></span>|<span data-ttu-id="c4073-143">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-143">Numeric value</span></span>|  
|---------------------------------------|-------------------|  
|<span data-ttu-id="c4073-144">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="c4073-144">Default</span></span>|<span data-ttu-id="c4073-145">0</span><span class="sxs-lookup"><span data-stu-id="c4073-145">0</span></span>|  
|<span data-ttu-id="c4073-146">AboveNormal</span><span class="sxs-lookup"><span data-stu-id="c4073-146">AboveNormal</span></span>|<span data-ttu-id="c4073-147">1</span><span class="sxs-lookup"><span data-stu-id="c4073-147">1</span></span>|  
|<span data-ttu-id="c4073-148">Normal</span><span class="sxs-lookup"><span data-stu-id="c4073-148">Normal</span></span>|<span data-ttu-id="c4073-149">2</span><span class="sxs-lookup"><span data-stu-id="c4073-149">2</span></span>|  
|<span data-ttu-id="c4073-150">BelowNormal</span><span class="sxs-lookup"><span data-stu-id="c4073-150">BelowNormal</span></span>|<span data-ttu-id="c4073-151">3</span><span class="sxs-lookup"><span data-stu-id="c4073-151">3</span></span>|  
|<span data-ttu-id="c4073-152">Inactivo</span><span class="sxs-lookup"><span data-stu-id="c4073-152">Idle</span></span>|<span data-ttu-id="c4073-153">4</span><span class="sxs-lookup"><span data-stu-id="c4073-153">4</span></span>|  
  
 <span data-ttu-id="c4073-154">`ProtectionLevel`propiedad: se establece mediante el uso de valores de la `DTSProtectionLevel` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-154">`ProtectionLevel` property-Set by using values from the `DTSProtectionLevel` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-155">Nombre descriptivo en DTSProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="c4073-155">Friendly name in DTSProtectionLevel</span></span>|<span data-ttu-id="c4073-156">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-156">Numeric value</span></span>|  
|-----------------------------------------|-------------------|  
|<span data-ttu-id="c4073-157">DontSaveSensitive</span><span class="sxs-lookup"><span data-stu-id="c4073-157">DontSaveSensitive</span></span>|<span data-ttu-id="c4073-158">0</span><span class="sxs-lookup"><span data-stu-id="c4073-158">0</span></span>|  
|<span data-ttu-id="c4073-159">EncryptSensitiveWithUserKey</span><span class="sxs-lookup"><span data-stu-id="c4073-159">EncryptSensitiveWithUserKey</span></span>|<span data-ttu-id="c4073-160">1</span><span class="sxs-lookup"><span data-stu-id="c4073-160">1</span></span>|  
|<span data-ttu-id="c4073-161">EncryptSensitiveWithPassword</span><span class="sxs-lookup"><span data-stu-id="c4073-161">EncryptSensitiveWithPassword</span></span>|<span data-ttu-id="c4073-162">2</span><span class="sxs-lookup"><span data-stu-id="c4073-162">2</span></span>|  
|<span data-ttu-id="c4073-163">EncryptAllWithPassword</span><span class="sxs-lookup"><span data-stu-id="c4073-163">EncryptAllWithPassword</span></span>|<span data-ttu-id="c4073-164">3</span><span class="sxs-lookup"><span data-stu-id="c4073-164">3</span></span>|  
|<span data-ttu-id="c4073-165">EncryptAllWithUserKey</span><span class="sxs-lookup"><span data-stu-id="c4073-165">EncryptAllWithUserKey</span></span>|<span data-ttu-id="c4073-166">4</span><span class="sxs-lookup"><span data-stu-id="c4073-166">4</span></span>|  
|<span data-ttu-id="c4073-167">ServerStorage</span><span class="sxs-lookup"><span data-stu-id="c4073-167">ServerStorage</span></span>|<span data-ttu-id="c4073-168">5</span><span class="sxs-lookup"><span data-stu-id="c4073-168">5</span></span>|  
  
##  <a name="precedence-constraints"></a><a name="PrecedenceConstraints"></a> <span data-ttu-id="c4073-169">Restricciones de precedencia</span><span class="sxs-lookup"><span data-stu-id="c4073-169">Precedence Constraints</span></span>  
 <span data-ttu-id="c4073-170">`EvalOp`propiedad: se establece mediante el uso de valores de la `DTSPrecedenceEvalOp` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-170">`EvalOp` property-Set by using values from the `DTSPrecedenceEvalOp` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-171">Nombre descriptivo en DTSPrecedenceEvalOp</span><span class="sxs-lookup"><span data-stu-id="c4073-171">Friendly name in DTSPrecedenceEvalOp</span></span>|<span data-ttu-id="c4073-172">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-172">Numeric value</span></span>|  
|------------------------------------------|-------------------|  
|<span data-ttu-id="c4073-173">Expression</span><span class="sxs-lookup"><span data-stu-id="c4073-173">Expression</span></span>|<span data-ttu-id="c4073-174">1</span><span class="sxs-lookup"><span data-stu-id="c4073-174">1</span></span>|  
|<span data-ttu-id="c4073-175">Restricción</span><span class="sxs-lookup"><span data-stu-id="c4073-175">Constraint</span></span>|<span data-ttu-id="c4073-176">2</span><span class="sxs-lookup"><span data-stu-id="c4073-176">2</span></span>|  
|<span data-ttu-id="c4073-177">ExpressionAndConstraint</span><span class="sxs-lookup"><span data-stu-id="c4073-177">ExpressionAndConstraint</span></span>|<span data-ttu-id="c4073-178">3</span><span class="sxs-lookup"><span data-stu-id="c4073-178">3</span></span>|  
|<span data-ttu-id="c4073-179">ExpressionOrConstraint</span><span class="sxs-lookup"><span data-stu-id="c4073-179">ExpressionOrConstraint</span></span>|<span data-ttu-id="c4073-180">4</span><span class="sxs-lookup"><span data-stu-id="c4073-180">4</span></span>|  
  
 <span data-ttu-id="c4073-181">`Value`propiedad: se establece mediante el uso de valores de la `DTSExecResult` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-181">`Value` property-Set by using values from the `DTSExecResult` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-182">Nombre descriptivo</span><span class="sxs-lookup"><span data-stu-id="c4073-182">Friendly Name</span></span>|<span data-ttu-id="c4073-183">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-183">Numeric Value</span></span>|  
|-------------------|-------------------|  
|<span data-ttu-id="c4073-184">Correcto</span><span class="sxs-lookup"><span data-stu-id="c4073-184">Success</span></span>|<span data-ttu-id="c4073-185">0</span><span class="sxs-lookup"><span data-stu-id="c4073-185">0</span></span>|  
|<span data-ttu-id="c4073-186">Error</span><span class="sxs-lookup"><span data-stu-id="c4073-186">Failure</span></span>|<span data-ttu-id="c4073-187">1</span><span class="sxs-lookup"><span data-stu-id="c4073-187">1</span></span>|  
|<span data-ttu-id="c4073-188">Completion</span><span class="sxs-lookup"><span data-stu-id="c4073-188">Completion</span></span>|<span data-ttu-id="c4073-189">2</span><span class="sxs-lookup"><span data-stu-id="c4073-189">2</span></span>|  
|<span data-ttu-id="c4073-190">Canceled</span><span class="sxs-lookup"><span data-stu-id="c4073-190">Canceled</span></span>|<span data-ttu-id="c4073-191">3</span><span class="sxs-lookup"><span data-stu-id="c4073-191">3</span></span>|  
  
##  <a name="foreach-loop-enumerators"></a><a name="Foreach"></a> <span data-ttu-id="c4073-192">Enumeradores de bucle Foreach</span><span class="sxs-lookup"><span data-stu-id="c4073-192">Foreach Loop Enumerators</span></span>  
 <span data-ttu-id="c4073-193">El bucle Foreach incluye un conjunto de enumeradores con propiedades que se pueden establecer a partir de expresiones de propiedad.</span><span class="sxs-lookup"><span data-stu-id="c4073-193">The Foreach Loop includes a set of enumerators with properties that can be set by property expressions.</span></span>  
  
### <a name="foreach-ado-enumerator"></a><span data-ttu-id="c4073-194">Enumerador de ADO para Foreach</span><span class="sxs-lookup"><span data-stu-id="c4073-194">Foreach ADO Enumerator</span></span>  
 <span data-ttu-id="c4073-195">`Type`propiedad: se establece mediante el uso de valores de la `ADOEnumerationType` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-195">`Type` property-Set by using values from the `ADOEnumerationType` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-196">Nombre descriptivo en ADOEnumerationType</span><span class="sxs-lookup"><span data-stu-id="c4073-196">Friendly name in ADOEnumerationType</span></span>|<span data-ttu-id="c4073-197">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-197">Numeric value</span></span>|  
|-----------------------------------------|-------------------|  
|<span data-ttu-id="c4073-198">EnumerateTables</span><span class="sxs-lookup"><span data-stu-id="c4073-198">EnumerateTables</span></span>|<span data-ttu-id="c4073-199">0</span><span class="sxs-lookup"><span data-stu-id="c4073-199">0</span></span>|  
|<span data-ttu-id="c4073-200">EnumerateAllRows</span><span class="sxs-lookup"><span data-stu-id="c4073-200">EnumerateAllRows</span></span>|<span data-ttu-id="c4073-201">1</span><span class="sxs-lookup"><span data-stu-id="c4073-201">1</span></span>|  
|<span data-ttu-id="c4073-202">EnumerateRowsInFirstTable</span><span class="sxs-lookup"><span data-stu-id="c4073-202">EnumerateRowsInFirstTable</span></span>|<span data-ttu-id="c4073-203">2</span><span class="sxs-lookup"><span data-stu-id="c4073-203">2</span></span>|  
  
### <a name="foreach-nodelist-enumerator"></a><span data-ttu-id="c4073-204">Enumerador de lista de nodos para Foreach</span><span class="sxs-lookup"><span data-stu-id="c4073-204">Foreach Nodelist Enumerator</span></span>  
 <span data-ttu-id="c4073-205">`SourceDocumentType``InnerXPathStringSourceType`propiedades, y **OuterXPathStringSourceType** : se establece mediante el uso de valores de la `SourceType` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-205">`SourceDocumentType`, `InnerXPathStringSourceType`, and **OuterXPathStringSourceType** properties-Set by using values from the `SourceType` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-206">Nombre descriptivo en SourceType</span><span class="sxs-lookup"><span data-stu-id="c4073-206">Friendly name in SourceType</span></span>|<span data-ttu-id="c4073-207">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-207">Numeric value</span></span>|  
|---------------------------------|-------------------|  
|<span data-ttu-id="c4073-208">FileConnection</span><span class="sxs-lookup"><span data-stu-id="c4073-208">FileConnection</span></span>|<span data-ttu-id="c4073-209">0</span><span class="sxs-lookup"><span data-stu-id="c4073-209">0</span></span>|  
|<span data-ttu-id="c4073-210">Variable</span><span class="sxs-lookup"><span data-stu-id="c4073-210">Variable</span></span>|<span data-ttu-id="c4073-211">1</span><span class="sxs-lookup"><span data-stu-id="c4073-211">1</span></span>|  
|<span data-ttu-id="c4073-212">DirectInput</span><span class="sxs-lookup"><span data-stu-id="c4073-212">DirectInput</span></span>|<span data-ttu-id="c4073-213">2</span><span class="sxs-lookup"><span data-stu-id="c4073-213">2</span></span>|  
  
 <span data-ttu-id="c4073-214">`EnumerationType`propiedad: se establece mediante el uso de valores de la `EnumerationType` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-214">`EnumerationType` property-Set by using values from the `EnumerationType` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-215">Nombre descriptivo en EnumerationType</span><span class="sxs-lookup"><span data-stu-id="c4073-215">Friendly name in EnumerationType</span></span>|<span data-ttu-id="c4073-216">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-216">Numeric value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="c4073-217">Navegador</span><span class="sxs-lookup"><span data-stu-id="c4073-217">Navigator</span></span>|<span data-ttu-id="c4073-218">0</span><span class="sxs-lookup"><span data-stu-id="c4073-218">0</span></span>|  
|<span data-ttu-id="c4073-219">Nodo</span><span class="sxs-lookup"><span data-stu-id="c4073-219">Node</span></span>|<span data-ttu-id="c4073-220">1</span><span class="sxs-lookup"><span data-stu-id="c4073-220">1</span></span>|  
|<span data-ttu-id="c4073-221">NodeText</span><span class="sxs-lookup"><span data-stu-id="c4073-221">NodeText</span></span>|<span data-ttu-id="c4073-222">2</span><span class="sxs-lookup"><span data-stu-id="c4073-222">2</span></span>|  
|<span data-ttu-id="c4073-223">ElementCollection</span><span class="sxs-lookup"><span data-stu-id="c4073-223">ElementCollection</span></span>|<span data-ttu-id="c4073-224">3</span><span class="sxs-lookup"><span data-stu-id="c4073-224">3</span></span>|  
  
 <span data-ttu-id="c4073-225">`InnerElementType`propiedad: se establece mediante el uso de valores de la `InnerElementType` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-225">`InnerElementType` property-Set by using values from the `InnerElementType` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-226">Nombre descriptivo en InnerElementType</span><span class="sxs-lookup"><span data-stu-id="c4073-226">Friendly name in InnerElementType</span></span>|<span data-ttu-id="c4073-227">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-227">Numeric value</span></span>|  
|---------------------------------------|-------------------|  
|<span data-ttu-id="c4073-228">Navegador</span><span class="sxs-lookup"><span data-stu-id="c4073-228">Navigator</span></span>|<span data-ttu-id="c4073-229">0</span><span class="sxs-lookup"><span data-stu-id="c4073-229">0</span></span>|  
|<span data-ttu-id="c4073-230">Nodo</span><span class="sxs-lookup"><span data-stu-id="c4073-230">Node</span></span>|<span data-ttu-id="c4073-231">1</span><span class="sxs-lookup"><span data-stu-id="c4073-231">1</span></span>|  
|<span data-ttu-id="c4073-232">NodeText</span><span class="sxs-lookup"><span data-stu-id="c4073-232">NodeText</span></span>|<span data-ttu-id="c4073-233">2</span><span class="sxs-lookup"><span data-stu-id="c4073-233">2</span></span>|  
  
##  <a name="tasks"></a><a name="Tasks"></a> <span data-ttu-id="c4073-234">Tareas</span><span class="sxs-lookup"><span data-stu-id="c4073-234">Tasks</span></span>  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="c4073-235">incluye numerosas tareas con propiedades que se establecen a partir de expresiones de propiedad.</span><span class="sxs-lookup"><span data-stu-id="c4073-235">includes numerous tasks with properties that can be set by property expressions.</span></span>  
  
### <a name="analysis-services-execute-ddl-task"></a><span data-ttu-id="c4073-236">Tarea Ejecutar DDL de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="c4073-236">Analysis Services Execute DDL Task</span></span>  
 <span data-ttu-id="c4073-237">`SourceType`propiedad: se establece mediante el uso de valores de la `DDLSourceType` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-237">`SourceType` property-Set by using values from the `DDLSourceType` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-238">Nombre descriptivo en DDLSourceType</span><span class="sxs-lookup"><span data-stu-id="c4073-238">Friendly name in DDLSourceType</span></span>|<span data-ttu-id="c4073-239">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-239">Numeric value</span></span>|  
|------------------------------------|-------------------|  
|<span data-ttu-id="c4073-240">DirectInput</span><span class="sxs-lookup"><span data-stu-id="c4073-240">DirectInput</span></span>|<span data-ttu-id="c4073-241">0</span><span class="sxs-lookup"><span data-stu-id="c4073-241">0</span></span>|  
|<span data-ttu-id="c4073-242">FileConnection</span><span class="sxs-lookup"><span data-stu-id="c4073-242">FileConnection</span></span>|<span data-ttu-id="c4073-243">1</span><span class="sxs-lookup"><span data-stu-id="c4073-243">1</span></span>|  
|<span data-ttu-id="c4073-244">Variable</span><span class="sxs-lookup"><span data-stu-id="c4073-244">Variable</span></span>|<span data-ttu-id="c4073-245">2</span><span class="sxs-lookup"><span data-stu-id="c4073-245">2</span></span>|  
  
### <a name="bulk-insert-task"></a><span data-ttu-id="c4073-246">Inserción masiva, tarea</span><span class="sxs-lookup"><span data-stu-id="c4073-246">Bulk Insert Task</span></span>  
 <span data-ttu-id="c4073-247">`DataFileType`propiedad: se establece mediante el uso de valores de la `DTSBulkInsert_DataFileType` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-247">`DataFileType` property-Set by using values from the `DTSBulkInsert_DataFileType` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-248">Nombre descriptivo en DTSBulkInsert_DataFileType</span><span class="sxs-lookup"><span data-stu-id="c4073-248">Friendly name in DTSBulkInsert_DataFileType</span></span>|<span data-ttu-id="c4073-249">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-249">Numeric value</span></span>|  
|--------------------------------------------------|-------------------|  
|<span data-ttu-id="c4073-250">DTSBulkInsert_DataFileType_Char</span><span class="sxs-lookup"><span data-stu-id="c4073-250">DTSBulkInsert_DataFileType_Char</span></span>|<span data-ttu-id="c4073-251">0</span><span class="sxs-lookup"><span data-stu-id="c4073-251">0</span></span>|  
|<span data-ttu-id="c4073-252">DTSBulkInsert_DataFileType_Native</span><span class="sxs-lookup"><span data-stu-id="c4073-252">DTSBulkInsert_DataFileType_Native</span></span>|<span data-ttu-id="c4073-253">1</span><span class="sxs-lookup"><span data-stu-id="c4073-253">1</span></span>|  
|<span data-ttu-id="c4073-254">DTSBulkInsert_DataFileType_WideChar</span><span class="sxs-lookup"><span data-stu-id="c4073-254">DTSBulkInsert_DataFileType_WideChar</span></span>|<span data-ttu-id="c4073-255">2</span><span class="sxs-lookup"><span data-stu-id="c4073-255">2</span></span>|  
|<span data-ttu-id="c4073-256">DTSBulkInsert_DataFileType_WideNative</span><span class="sxs-lookup"><span data-stu-id="c4073-256">DTSBulkInsert_DataFileType_WideNative</span></span>|<span data-ttu-id="c4073-257">3</span><span class="sxs-lookup"><span data-stu-id="c4073-257">3</span></span>|  
  
### <a name="execute-sql-task"></a><span data-ttu-id="c4073-258">Tarea Ejecutar SQL</span><span class="sxs-lookup"><span data-stu-id="c4073-258">Execute SQL Task</span></span>  
 <span data-ttu-id="c4073-259">`ResultSetType`propiedad: se establece mediante el uso de valores de la `ResultSetType` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-259">`ResultSetType` property-Set by using values from the `ResultSetType` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-260">Nombre descriptivo en ResultSetType</span><span class="sxs-lookup"><span data-stu-id="c4073-260">Friendly name in ResultSetType</span></span>|<span data-ttu-id="c4073-261">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-261">Numeric Value</span></span>|  
|------------------------------------|-------------------|  
|<span data-ttu-id="c4073-262">ResultSetType_None</span><span class="sxs-lookup"><span data-stu-id="c4073-262">ResultSetType_None</span></span>|<span data-ttu-id="c4073-263">1</span><span class="sxs-lookup"><span data-stu-id="c4073-263">1</span></span>|  
|<span data-ttu-id="c4073-264">ResultSetType_SingleRow</span><span class="sxs-lookup"><span data-stu-id="c4073-264">ResultSetType_SingleRow</span></span>|<span data-ttu-id="c4073-265">2</span><span class="sxs-lookup"><span data-stu-id="c4073-265">2</span></span>|  
|<span data-ttu-id="c4073-266">ResultSetType_Rowset</span><span class="sxs-lookup"><span data-stu-id="c4073-266">ResultSetType_Rowset</span></span>|<span data-ttu-id="c4073-267">3</span><span class="sxs-lookup"><span data-stu-id="c4073-267">3</span></span>|  
|<span data-ttu-id="c4073-268">ResultSetType_XML</span><span class="sxs-lookup"><span data-stu-id="c4073-268">ResultSetType_XML</span></span>|<span data-ttu-id="c4073-269">4</span><span class="sxs-lookup"><span data-stu-id="c4073-269">4</span></span>|  
  
 <span data-ttu-id="c4073-270">`SqlStatementSourceType`propiedad: se establece mediante el uso de valores de la `SqlStatementSourceType` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-270">`SqlStatementSourceType` property-Set by using values from the `SqlStatementSourceType` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-271">Nombre descriptivo en SqlStatementSourceType</span><span class="sxs-lookup"><span data-stu-id="c4073-271">Friendly name in SqlStatementSourceType</span></span>|<span data-ttu-id="c4073-272">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-272">Numeric Value</span></span>|  
|---------------------------------------------|-------------------|  
|<span data-ttu-id="c4073-273">DirectInput</span><span class="sxs-lookup"><span data-stu-id="c4073-273">DirectInput</span></span>|<span data-ttu-id="c4073-274">1</span><span class="sxs-lookup"><span data-stu-id="c4073-274">1</span></span>|  
|<span data-ttu-id="c4073-275">FileConnection</span><span class="sxs-lookup"><span data-stu-id="c4073-275">FileConnection</span></span>|<span data-ttu-id="c4073-276">2</span><span class="sxs-lookup"><span data-stu-id="c4073-276">2</span></span>|  
|<span data-ttu-id="c4073-277">Variable</span><span class="sxs-lookup"><span data-stu-id="c4073-277">Variable</span></span>|<span data-ttu-id="c4073-278">3</span><span class="sxs-lookup"><span data-stu-id="c4073-278">3</span></span>|  
  
### <a name="file-system-task"></a><span data-ttu-id="c4073-279">Tarea Sistema de archivos</span><span class="sxs-lookup"><span data-stu-id="c4073-279">File System Task</span></span>  
 <span data-ttu-id="c4073-280">`Operation`propiedad: se establece mediante el uso de valores de la `DTSFileSystemOperation` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-280">`Operation` property-Set by using values from the `DTSFileSystemOperation` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-281">Nombre descriptivo en DTSFileSystemOperation</span><span class="sxs-lookup"><span data-stu-id="c4073-281">Friendly name in DTSFileSystemOperation</span></span>|<span data-ttu-id="c4073-282">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-282">Numeric value</span></span>|  
|---------------------------------------------|-------------------|  
|<span data-ttu-id="c4073-283">CopyFile</span><span class="sxs-lookup"><span data-stu-id="c4073-283">CopyFile</span></span>|<span data-ttu-id="c4073-284">0</span><span class="sxs-lookup"><span data-stu-id="c4073-284">0</span></span>|  
|<span data-ttu-id="c4073-285">MoveFile</span><span class="sxs-lookup"><span data-stu-id="c4073-285">MoveFile</span></span>|<span data-ttu-id="c4073-286">1</span><span class="sxs-lookup"><span data-stu-id="c4073-286">1</span></span>|  
|<span data-ttu-id="c4073-287">DeleteFile</span><span class="sxs-lookup"><span data-stu-id="c4073-287">DeleteFile</span></span>|<span data-ttu-id="c4073-288">2</span><span class="sxs-lookup"><span data-stu-id="c4073-288">2</span></span>|  
|<span data-ttu-id="c4073-289">RenameFile</span><span class="sxs-lookup"><span data-stu-id="c4073-289">RenameFile</span></span>|<span data-ttu-id="c4073-290">3</span><span class="sxs-lookup"><span data-stu-id="c4073-290">3</span></span>|  
|<span data-ttu-id="c4073-291">SetAttributes</span><span class="sxs-lookup"><span data-stu-id="c4073-291">SetAttributes</span></span>|<span data-ttu-id="c4073-292">4</span><span class="sxs-lookup"><span data-stu-id="c4073-292">4</span></span>|  
|<span data-ttu-id="c4073-293">CreateDirectory</span><span class="sxs-lookup"><span data-stu-id="c4073-293">CreateDirectory</span></span>|<span data-ttu-id="c4073-294">5</span><span class="sxs-lookup"><span data-stu-id="c4073-294">5</span></span>|  
|<span data-ttu-id="c4073-295">CopyDirectory</span><span class="sxs-lookup"><span data-stu-id="c4073-295">CopyDirectory</span></span>|<span data-ttu-id="c4073-296">6</span><span class="sxs-lookup"><span data-stu-id="c4073-296">6</span></span>|  
|<span data-ttu-id="c4073-297">MoveDirectory</span><span class="sxs-lookup"><span data-stu-id="c4073-297">MoveDirectory</span></span>|<span data-ttu-id="c4073-298">7</span><span class="sxs-lookup"><span data-stu-id="c4073-298">7</span></span>|  
|<span data-ttu-id="c4073-299">DeleteDirectory</span><span class="sxs-lookup"><span data-stu-id="c4073-299">DeleteDirectory</span></span>|<span data-ttu-id="c4073-300">8</span><span class="sxs-lookup"><span data-stu-id="c4073-300">8</span></span>|  
|<span data-ttu-id="c4073-301">DeleteDirectoryContent</span><span class="sxs-lookup"><span data-stu-id="c4073-301">DeleteDirectoryContent</span></span>|<span data-ttu-id="c4073-302">9</span><span class="sxs-lookup"><span data-stu-id="c4073-302">9</span></span>|  
  
 <span data-ttu-id="c4073-303">`Attributes`propiedad: se establece mediante el uso de valores de la `DTSFileSystemAttributes` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-303">`Attributes` property-Set by using values from the `DTSFileSystemAttributes` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-304">Nombre descriptivo en DTSFileSystemAttributes</span><span class="sxs-lookup"><span data-stu-id="c4073-304">Friendly name in DTSFileSystemAttributes</span></span>|<span data-ttu-id="c4073-305">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-305">Numeric value</span></span>|  
|----------------------------------------------|-------------------|  
|<span data-ttu-id="c4073-306">Normal</span><span class="sxs-lookup"><span data-stu-id="c4073-306">Normal</span></span>|<span data-ttu-id="c4073-307">0</span><span class="sxs-lookup"><span data-stu-id="c4073-307">0</span></span>|  
|<span data-ttu-id="c4073-308">Archivar</span><span class="sxs-lookup"><span data-stu-id="c4073-308">Archive</span></span>|<span data-ttu-id="c4073-309">1</span><span class="sxs-lookup"><span data-stu-id="c4073-309">1</span></span>|  
|<span data-ttu-id="c4073-310">Hidden</span><span class="sxs-lookup"><span data-stu-id="c4073-310">Hidden</span></span>|<span data-ttu-id="c4073-311">2</span><span class="sxs-lookup"><span data-stu-id="c4073-311">2</span></span>|  
|<span data-ttu-id="c4073-312">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="c4073-312">ReadOnly</span></span>|<span data-ttu-id="c4073-313">4</span><span class="sxs-lookup"><span data-stu-id="c4073-313">4</span></span>|  
|<span data-ttu-id="c4073-314">Sistema</span><span class="sxs-lookup"><span data-stu-id="c4073-314">System</span></span>|<span data-ttu-id="c4073-315">8</span><span class="sxs-lookup"><span data-stu-id="c4073-315">8</span></span>|  
  
### <a name="ftp-task"></a><span data-ttu-id="c4073-316">Tarea FTP</span><span class="sxs-lookup"><span data-stu-id="c4073-316">FTP Task</span></span>  
 <span data-ttu-id="c4073-317">`Operation`propiedad: se establece mediante el uso de valores de la `DTSFTPOp` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-317">`Operation` property-Set by using values from the `DTSFTPOp` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-318">Nombre descriptivo en DTSFTPOp</span><span class="sxs-lookup"><span data-stu-id="c4073-318">Friendly name in DTSFTPOp</span></span>|<span data-ttu-id="c4073-319">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-319">Numeric value</span></span>|  
|-------------------------------|-------------------|  
|<span data-ttu-id="c4073-320">Envío</span><span class="sxs-lookup"><span data-stu-id="c4073-320">Send</span></span>|<span data-ttu-id="c4073-321">0</span><span class="sxs-lookup"><span data-stu-id="c4073-321">0</span></span>|  
|<span data-ttu-id="c4073-322">Recepción</span><span class="sxs-lookup"><span data-stu-id="c4073-322">Receive</span></span>|<span data-ttu-id="c4073-323">1</span><span class="sxs-lookup"><span data-stu-id="c4073-323">1</span></span>|  
|<span data-ttu-id="c4073-324">DeleteLocal</span><span class="sxs-lookup"><span data-stu-id="c4073-324">DeleteLocal</span></span>|<span data-ttu-id="c4073-325">2</span><span class="sxs-lookup"><span data-stu-id="c4073-325">2</span></span>|  
|<span data-ttu-id="c4073-326">DeleteRemote</span><span class="sxs-lookup"><span data-stu-id="c4073-326">DeleteRemote</span></span>|<span data-ttu-id="c4073-327">3</span><span class="sxs-lookup"><span data-stu-id="c4073-327">3</span></span>|  
|<span data-ttu-id="c4073-328">MakeDirLocal</span><span class="sxs-lookup"><span data-stu-id="c4073-328">MakeDirLocal</span></span>|<span data-ttu-id="c4073-329">4</span><span class="sxs-lookup"><span data-stu-id="c4073-329">4</span></span>|  
|<span data-ttu-id="c4073-330">MakeDirRemote</span><span class="sxs-lookup"><span data-stu-id="c4073-330">MakeDirRemote</span></span>|<span data-ttu-id="c4073-331">5</span><span class="sxs-lookup"><span data-stu-id="c4073-331">5</span></span>|  
|<span data-ttu-id="c4073-332">RemoveDirLocal</span><span class="sxs-lookup"><span data-stu-id="c4073-332">RemoveDirLocal</span></span>|<span data-ttu-id="c4073-333">6</span><span class="sxs-lookup"><span data-stu-id="c4073-333">6</span></span>|  
|<span data-ttu-id="c4073-334">RemoveDirRemote</span><span class="sxs-lookup"><span data-stu-id="c4073-334">RemoveDirRemote</span></span>|<span data-ttu-id="c4073-335">7</span><span class="sxs-lookup"><span data-stu-id="c4073-335">7</span></span>|  
  
### <a name="message-queue-task"></a><span data-ttu-id="c4073-336">Message Queue Task</span><span class="sxs-lookup"><span data-stu-id="c4073-336">Message Queue Task</span></span>  
 <span data-ttu-id="c4073-337">`MessageType`propiedad: se establece mediante el uso de valores de la `MQMessageType` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-337">`MessageType` property-Set by using values from the `MQMessageType` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-338">Nombre descriptivo en MQMessageType</span><span class="sxs-lookup"><span data-stu-id="c4073-338">Friendly name in MQMessageType</span></span>|<span data-ttu-id="c4073-339">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-339">Numeric value</span></span>|  
|------------------------------------|-------------------|  
|<span data-ttu-id="c4073-340">DTSMQMessageType_String</span><span class="sxs-lookup"><span data-stu-id="c4073-340">DTSMQMessageType_String</span></span>|<span data-ttu-id="c4073-341">0</span><span class="sxs-lookup"><span data-stu-id="c4073-341">0</span></span>|  
|<span data-ttu-id="c4073-342">DTSMQMessageType_DataFile</span><span class="sxs-lookup"><span data-stu-id="c4073-342">DTSMQMessageType_DataFile</span></span>|<span data-ttu-id="c4073-343">1</span><span class="sxs-lookup"><span data-stu-id="c4073-343">1</span></span>|  
|<span data-ttu-id="c4073-344">DTSMQMessageType_Variables</span><span class="sxs-lookup"><span data-stu-id="c4073-344">DTSMQMessageType_Variables</span></span>|<span data-ttu-id="c4073-345">2</span><span class="sxs-lookup"><span data-stu-id="c4073-345">2</span></span>|  
|<span data-ttu-id="c4073-346">DTSMQMessagType_StringMessageToVariable</span><span class="sxs-lookup"><span data-stu-id="c4073-346">DTSMQMessagType_StringMessageToVariable</span></span>|<span data-ttu-id="c4073-347">3</span><span class="sxs-lookup"><span data-stu-id="c4073-347">3</span></span>|  
  
 <span data-ttu-id="c4073-348">`StringCompareType`propiedad: se establece mediante el uso de valores de la `MQStringMessageCompare` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-348">`StringCompareType` property-Set by using values from the `MQStringMessageCompare` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-349">Nombre descriptivo en MQStringMessageCompare</span><span class="sxs-lookup"><span data-stu-id="c4073-349">Friendly name in MQStringMessageCompare</span></span>|<span data-ttu-id="c4073-350">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-350">Numeric value</span></span>|  
|---------------------------------------------|-------------------|  
|<span data-ttu-id="c4073-351">DTSMQStringMessageCompare_None</span><span class="sxs-lookup"><span data-stu-id="c4073-351">DTSMQStringMessageCompare_None</span></span>|<span data-ttu-id="c4073-352">0</span><span class="sxs-lookup"><span data-stu-id="c4073-352">0</span></span>|  
|<span data-ttu-id="c4073-353">DTSMQStringMessageCompare_Exact</span><span class="sxs-lookup"><span data-stu-id="c4073-353">DTSMQStringMessageCompare_Exact</span></span>|<span data-ttu-id="c4073-354">1</span><span class="sxs-lookup"><span data-stu-id="c4073-354">1</span></span>|  
|<span data-ttu-id="c4073-355">DTSMQStringMessageCompare_IgnoreCase</span><span class="sxs-lookup"><span data-stu-id="c4073-355">DTSMQStringMessageCompare_IgnoreCase</span></span>|<span data-ttu-id="c4073-356">2</span><span class="sxs-lookup"><span data-stu-id="c4073-356">2</span></span>|  
|<span data-ttu-id="c4073-357">DTSMQStringMessageCompare_Contains</span><span class="sxs-lookup"><span data-stu-id="c4073-357">DTSMQStringMessageCompare_Contains</span></span>|<span data-ttu-id="c4073-358">3</span><span class="sxs-lookup"><span data-stu-id="c4073-358">3</span></span>|  
  
 <span data-ttu-id="c4073-359">`TaskType`propiedad: se establece mediante el uso de valores de la `MQType` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-359">`TaskType` property-Set by using values from the `MQType` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-360">Nombre descriptivo en MQType</span><span class="sxs-lookup"><span data-stu-id="c4073-360">Friendly name in MQType</span></span>|<span data-ttu-id="c4073-361">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-361">Numeric value</span></span>|  
|-----------------------------|-------------------|  
|<span data-ttu-id="c4073-362">DTSMQType_Sender</span><span class="sxs-lookup"><span data-stu-id="c4073-362">DTSMQType_Sender</span></span>|<span data-ttu-id="c4073-363">0</span><span class="sxs-lookup"><span data-stu-id="c4073-363">0</span></span>|  
|<span data-ttu-id="c4073-364">DTSMQType_Receiver</span><span class="sxs-lookup"><span data-stu-id="c4073-364">DTSMQType_Receiver</span></span>|<span data-ttu-id="c4073-365">1</span><span class="sxs-lookup"><span data-stu-id="c4073-365">1</span></span>|  
  
### <a name="send-mail-task"></a><span data-ttu-id="c4073-366">Enviar correo, tarea</span><span class="sxs-lookup"><span data-stu-id="c4073-366">Send Mail Task</span></span>  
 <span data-ttu-id="c4073-367">`MessageSourceType`propiedad: se establece mediante el uso de valores de la `SendMailMessageSourceType` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-367">`MessageSourceType` property-Set by using values from the `SendMailMessageSourceType` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-368">Nombre descriptivo en SendMailMessageSourceType</span><span class="sxs-lookup"><span data-stu-id="c4073-368">Friendly Name in SendMailMessageSourceType</span></span>|<span data-ttu-id="c4073-369">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-369">Numeric Value</span></span>|  
|------------------------------------------------|-------------------|  
|<span data-ttu-id="c4073-370">DirectInput</span><span class="sxs-lookup"><span data-stu-id="c4073-370">DirectInput</span></span>|<span data-ttu-id="c4073-371">0</span><span class="sxs-lookup"><span data-stu-id="c4073-371">0</span></span>|  
|<span data-ttu-id="c4073-372">FileConnection</span><span class="sxs-lookup"><span data-stu-id="c4073-372">FileConnection</span></span>|<span data-ttu-id="c4073-373">1</span><span class="sxs-lookup"><span data-stu-id="c4073-373">1</span></span>|  
|<span data-ttu-id="c4073-374">Variable</span><span class="sxs-lookup"><span data-stu-id="c4073-374">Variable</span></span>|<span data-ttu-id="c4073-375">2</span><span class="sxs-lookup"><span data-stu-id="c4073-375">2</span></span>|  
  
 <span data-ttu-id="c4073-376">`Priority`propiedad: se establece mediante el uso de valores de la `MailPriority` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-376">`Priority` property-Set by using values from the `MailPriority` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-377">Nombre descriptivo en MailPriority</span><span class="sxs-lookup"><span data-stu-id="c4073-377">Friendly Name in MailPriority</span></span>|<span data-ttu-id="c4073-378">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-378">Numeric Value</span></span>|  
|-----------------------------------|-------------------|  
|<span data-ttu-id="c4073-379">Alto</span><span class="sxs-lookup"><span data-stu-id="c4073-379">High</span></span>|<span data-ttu-id="c4073-380">1</span><span class="sxs-lookup"><span data-stu-id="c4073-380">1</span></span>|  
|<span data-ttu-id="c4073-381">Normal</span><span class="sxs-lookup"><span data-stu-id="c4073-381">Normal</span></span>|<span data-ttu-id="c4073-382">3</span><span class="sxs-lookup"><span data-stu-id="c4073-382">3</span></span>|  
|<span data-ttu-id="c4073-383">Bajo</span><span class="sxs-lookup"><span data-stu-id="c4073-383">Low</span></span>|<span data-ttu-id="c4073-384">5</span><span class="sxs-lookup"><span data-stu-id="c4073-384">5</span></span>|  
  
### <a name="transfer-database-task"></a><span data-ttu-id="c4073-385">Tarea Transferir bases de datos</span><span class="sxs-lookup"><span data-stu-id="c4073-385">Transfer Database Task</span></span>  
 <span data-ttu-id="c4073-386">`Action`propiedad: se establece mediante el uso de valores de la `TransferAction` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-386">`Action` property-Set by using values from the `TransferAction` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-387">Nombre descriptivo en TransferAction</span><span class="sxs-lookup"><span data-stu-id="c4073-387">Friendly name in TransferAction</span></span>|<span data-ttu-id="c4073-388">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-388">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="c4073-389">Copiar</span><span class="sxs-lookup"><span data-stu-id="c4073-389">Copy</span></span>|<span data-ttu-id="c4073-390">0</span><span class="sxs-lookup"><span data-stu-id="c4073-390">0</span></span>|  
|<span data-ttu-id="c4073-391">Move</span><span class="sxs-lookup"><span data-stu-id="c4073-391">Move</span></span>|<span data-ttu-id="c4073-392">1</span><span class="sxs-lookup"><span data-stu-id="c4073-392">1</span></span>|  
  
 <span data-ttu-id="c4073-393">`Method`propiedad: se establece mediante el uso de valores de la `TransferMethod` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-393">`Method` property-Set by using values from the `TransferMethod` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-394">Nombre descriptivo en TransferMethod</span><span class="sxs-lookup"><span data-stu-id="c4073-394">Friendly name in TransferMethod</span></span>|<span data-ttu-id="c4073-395">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-395">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="c4073-396">DatabaseOffline</span><span class="sxs-lookup"><span data-stu-id="c4073-396">DatabaseOffline</span></span>|<span data-ttu-id="c4073-397">0</span><span class="sxs-lookup"><span data-stu-id="c4073-397">0</span></span>|  
|<span data-ttu-id="c4073-398">DatabaseOnline</span><span class="sxs-lookup"><span data-stu-id="c4073-398">DatabaseOnline</span></span>|<span data-ttu-id="c4073-399">1</span><span class="sxs-lookup"><span data-stu-id="c4073-399">1</span></span>|  
  
### <a name="transfer-error-messages-task"></a><span data-ttu-id="c4073-400">Tarea Transferir mensajes de error</span><span class="sxs-lookup"><span data-stu-id="c4073-400">Transfer Error Messages Task</span></span>  
 <span data-ttu-id="c4073-401">`IfObjectExists`propiedad: se establece mediante el uso de valores de la `IfObjectExists` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-401">`IfObjectExists` property-Set by using values from the `IfObjectExists` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-402">Nombre descriptivo en IfObjectExists</span><span class="sxs-lookup"><span data-stu-id="c4073-402">Friendly Name in IfObjectExists</span></span>|<span data-ttu-id="c4073-403">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-403">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="c4073-404">FailTask</span><span class="sxs-lookup"><span data-stu-id="c4073-404">FailTask</span></span>|<span data-ttu-id="c4073-405">0</span><span class="sxs-lookup"><span data-stu-id="c4073-405">0</span></span>|  
|<span data-ttu-id="c4073-406">Sobrescribir</span><span class="sxs-lookup"><span data-stu-id="c4073-406">Overwrite</span></span>|<span data-ttu-id="c4073-407">1</span><span class="sxs-lookup"><span data-stu-id="c4073-407">1</span></span>|  
|<span data-ttu-id="c4073-408">Omitir</span><span class="sxs-lookup"><span data-stu-id="c4073-408">Skip</span></span>|<span data-ttu-id="c4073-409">2</span><span class="sxs-lookup"><span data-stu-id="c4073-409">2</span></span>|  
  
### <a name="transfer-jobs-task"></a><span data-ttu-id="c4073-410">Tarea Transferir trabajos</span><span class="sxs-lookup"><span data-stu-id="c4073-410">Transfer Jobs Task</span></span>  
 <span data-ttu-id="c4073-411">`IfObjectExists`propiedad: se establece mediante el uso de valores de la `IfObjectExists` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-411">`IfObjectExists` property-Set by using values from the `IfObjectExists` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-412">Nombre descriptivo en IfObjectExists</span><span class="sxs-lookup"><span data-stu-id="c4073-412">Friendly Name in IfObjectExists</span></span>|<span data-ttu-id="c4073-413">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-413">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="c4073-414">FailTask</span><span class="sxs-lookup"><span data-stu-id="c4073-414">FailTask</span></span>|<span data-ttu-id="c4073-415">0</span><span class="sxs-lookup"><span data-stu-id="c4073-415">0</span></span>|  
|<span data-ttu-id="c4073-416">Sobrescribir</span><span class="sxs-lookup"><span data-stu-id="c4073-416">Overwrite</span></span>|<span data-ttu-id="c4073-417">1</span><span class="sxs-lookup"><span data-stu-id="c4073-417">1</span></span>|  
|<span data-ttu-id="c4073-418">Omitir</span><span class="sxs-lookup"><span data-stu-id="c4073-418">Skip</span></span>|<span data-ttu-id="c4073-419">2</span><span class="sxs-lookup"><span data-stu-id="c4073-419">2</span></span>|  
  
### <a name="transfer-logins-task"></a><span data-ttu-id="c4073-420">Tarea Transferir inicios de sesión</span><span class="sxs-lookup"><span data-stu-id="c4073-420">Transfer Logins Task</span></span>  
 <span data-ttu-id="c4073-421">`IfObjectExists`propiedad: se establece mediante el uso de valores de la `IfObjectExists` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-421">`IfObjectExists` property-Set by using values from the `IfObjectExists` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-422">Nombre descriptivo en IfObjectExists</span><span class="sxs-lookup"><span data-stu-id="c4073-422">Friendly name in IfObjectExists</span></span>|<span data-ttu-id="c4073-423">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-423">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="c4073-424">FailTask</span><span class="sxs-lookup"><span data-stu-id="c4073-424">FailTask</span></span>|<span data-ttu-id="c4073-425">0</span><span class="sxs-lookup"><span data-stu-id="c4073-425">0</span></span>|  
|<span data-ttu-id="c4073-426">Sobrescribir</span><span class="sxs-lookup"><span data-stu-id="c4073-426">Overwrite</span></span>|<span data-ttu-id="c4073-427">1</span><span class="sxs-lookup"><span data-stu-id="c4073-427">1</span></span>|  
|<span data-ttu-id="c4073-428">Omitir</span><span class="sxs-lookup"><span data-stu-id="c4073-428">Skip</span></span>|<span data-ttu-id="c4073-429">2</span><span class="sxs-lookup"><span data-stu-id="c4073-429">2</span></span>|  
  
 <span data-ttu-id="c4073-430">`LoginsToTransfer`propiedad: se establece mediante el uso de valores de la `LoginsToTransfer` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-430">`LoginsToTransfer` property-Set by using values from the `LoginsToTransfer` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-431">Nombre descriptivo en LoginsToTransfer</span><span class="sxs-lookup"><span data-stu-id="c4073-431">Friendly name in LoginsToTransfer</span></span>|<span data-ttu-id="c4073-432">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-432">Numeric value</span></span>|  
|---------------------------------------|-------------------|  
|<span data-ttu-id="c4073-433">AllLogins</span><span class="sxs-lookup"><span data-stu-id="c4073-433">AllLogins</span></span>|<span data-ttu-id="c4073-434">0</span><span class="sxs-lookup"><span data-stu-id="c4073-434">0</span></span>|  
|<span data-ttu-id="c4073-435">SelectedLogins</span><span class="sxs-lookup"><span data-stu-id="c4073-435">SelectedLogins</span></span>|<span data-ttu-id="c4073-436">1</span><span class="sxs-lookup"><span data-stu-id="c4073-436">1</span></span>|  
|<span data-ttu-id="c4073-437">AllLoginsFromSelectedDatabases</span><span class="sxs-lookup"><span data-stu-id="c4073-437">AllLoginsFromSelectedDatabases</span></span>|<span data-ttu-id="c4073-438">2</span><span class="sxs-lookup"><span data-stu-id="c4073-438">2</span></span>|  
  
### <a name="transfer-master-stored-procedures-task"></a><span data-ttu-id="c4073-439">Tarea Transferir procedimientos almacenados principales</span><span class="sxs-lookup"><span data-stu-id="c4073-439">Transfer Master Stored Procedures Task</span></span>  
 <span data-ttu-id="c4073-440">`IfObjectExists`propiedad: se establece mediante el uso de valores de la `IfObjectExists` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-440">`IfObjectExists` property-Set by using values from the `IfObjectExists` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-441">Nombre descriptivo en IfObjectExists</span><span class="sxs-lookup"><span data-stu-id="c4073-441">Friendly name in IfObjectExists</span></span>|<span data-ttu-id="c4073-442">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-442">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="c4073-443">FailTask</span><span class="sxs-lookup"><span data-stu-id="c4073-443">FailTask</span></span>|<span data-ttu-id="c4073-444">0</span><span class="sxs-lookup"><span data-stu-id="c4073-444">0</span></span>|  
|<span data-ttu-id="c4073-445">Sobrescribir</span><span class="sxs-lookup"><span data-stu-id="c4073-445">Overwrite</span></span>|<span data-ttu-id="c4073-446">1</span><span class="sxs-lookup"><span data-stu-id="c4073-446">1</span></span>|  
|<span data-ttu-id="c4073-447">Omitir</span><span class="sxs-lookup"><span data-stu-id="c4073-447">Skip</span></span>|<span data-ttu-id="c4073-448">2</span><span class="sxs-lookup"><span data-stu-id="c4073-448">2</span></span>|  
  
### <a name="transfer-sql-server-objects-task"></a><span data-ttu-id="c4073-449">Tarea Transferir objetos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="c4073-449">Transfer SQL Server Objects Task</span></span>  
 <span data-ttu-id="c4073-450">`ExistingData`propiedad: se establece mediante el uso de valores de la `ExistingData` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-450">`ExistingData` property-Set by using values from the `ExistingData` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-451">Nombre descriptivo en ExistingData</span><span class="sxs-lookup"><span data-stu-id="c4073-451">Friendly name in ExistingData</span></span>|<span data-ttu-id="c4073-452">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-452">Numeric Value</span></span>|  
|-----------------------------------|-------------------|  
|<span data-ttu-id="c4073-453">Replace</span><span class="sxs-lookup"><span data-stu-id="c4073-453">Replace</span></span>|<span data-ttu-id="c4073-454">0</span><span class="sxs-lookup"><span data-stu-id="c4073-454">0</span></span>|  
|<span data-ttu-id="c4073-455">Append</span><span class="sxs-lookup"><span data-stu-id="c4073-455">Append</span></span>|<span data-ttu-id="c4073-456">1</span><span class="sxs-lookup"><span data-stu-id="c4073-456">1</span></span>|  
  
### <a name="web-service-task"></a><span data-ttu-id="c4073-457">Tarea Servicio web</span><span class="sxs-lookup"><span data-stu-id="c4073-457">Web Service Task</span></span>  
 <span data-ttu-id="c4073-458">`OutputType`propiedad: se establece mediante el uso de valores de la `DTSOutputType` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-458">`OutputType` property-Set by using values from the `DTSOutputType` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-459">Nombre descriptivo en DTSOutputType</span><span class="sxs-lookup"><span data-stu-id="c4073-459">Friendly name in DTSOutputType</span></span>|<span data-ttu-id="c4073-460">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-460">Numeric value</span></span>|  
|------------------------------------|-------------------|  
|<span data-ttu-id="c4073-461">Archivo</span><span class="sxs-lookup"><span data-stu-id="c4073-461">File</span></span>|<span data-ttu-id="c4073-462">0</span><span class="sxs-lookup"><span data-stu-id="c4073-462">0</span></span>|  
|<span data-ttu-id="c4073-463">Variable</span><span class="sxs-lookup"><span data-stu-id="c4073-463">Variable</span></span>|<span data-ttu-id="c4073-464">1</span><span class="sxs-lookup"><span data-stu-id="c4073-464">1</span></span>|  
  
### <a name="wmi-data-reader-task"></a><span data-ttu-id="c4073-465">Tarea Lector de datos WMI</span><span class="sxs-lookup"><span data-stu-id="c4073-465">WMI Data Reader Task</span></span>  
 <span data-ttu-id="c4073-466">`OverwriteDestination`propiedad: se establece mediante el uso de valores de la `OverwriteDestination` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-466">`OverwriteDestination` property-Set by using values from the `OverwriteDestination` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-467">Nombre descriptivo en OverwriteDestination</span><span class="sxs-lookup"><span data-stu-id="c4073-467">Friendly name in OverwriteDestination</span></span>|<span data-ttu-id="c4073-468">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-468">Numeric value</span></span>|  
|-------------------------------------------|-------------------|  
|<span data-ttu-id="c4073-469">OverwriteDestination</span><span class="sxs-lookup"><span data-stu-id="c4073-469">OverwriteDestination</span></span>|<span data-ttu-id="c4073-470">0</span><span class="sxs-lookup"><span data-stu-id="c4073-470">0</span></span>|  
|<span data-ttu-id="c4073-471">AppendToDestination</span><span class="sxs-lookup"><span data-stu-id="c4073-471">AppendToDestination</span></span>|<span data-ttu-id="c4073-472">1</span><span class="sxs-lookup"><span data-stu-id="c4073-472">1</span></span>|  
|<span data-ttu-id="c4073-473">KeepOriginal</span><span class="sxs-lookup"><span data-stu-id="c4073-473">KeepOriginal</span></span>|<span data-ttu-id="c4073-474">2</span><span class="sxs-lookup"><span data-stu-id="c4073-474">2</span></span>|  
  
 <span data-ttu-id="c4073-475">`OutputType`propiedad: se establece mediante el uso de valores de la `OutputType` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-475">`OutputType` property-Set by using values from the `OutputType` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-476">Nombre descriptivo en OutputType</span><span class="sxs-lookup"><span data-stu-id="c4073-476">Friendly name in OutputType</span></span>|<span data-ttu-id="c4073-477">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-477">Numeric value</span></span>|  
|---------------------------------|-------------------|  
|<span data-ttu-id="c4073-478">DataTable</span><span class="sxs-lookup"><span data-stu-id="c4073-478">DataTable</span></span>|<span data-ttu-id="c4073-479">0</span><span class="sxs-lookup"><span data-stu-id="c4073-479">0</span></span>|  
|<span data-ttu-id="c4073-480">PropertyValue</span><span class="sxs-lookup"><span data-stu-id="c4073-480">PropertyValue</span></span>|<span data-ttu-id="c4073-481">1</span><span class="sxs-lookup"><span data-stu-id="c4073-481">1</span></span>|  
|<span data-ttu-id="c4073-482">PropertyNameAndValue</span><span class="sxs-lookup"><span data-stu-id="c4073-482">PropertyNameAndValue</span></span>|<span data-ttu-id="c4073-483">2</span><span class="sxs-lookup"><span data-stu-id="c4073-483">2</span></span>|  
  
 <span data-ttu-id="c4073-484">`DestinationType`propiedad: se establece mediante el uso de valores de la `DestinationType` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-484">`DestinationType` property-Set by using values from the `DestinationType` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-485">Nombre descriptivo en DestinationType</span><span class="sxs-lookup"><span data-stu-id="c4073-485">Friendly name in DestinationType</span></span>|<span data-ttu-id="c4073-486">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-486">Numeric value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="c4073-487">FileConnection</span><span class="sxs-lookup"><span data-stu-id="c4073-487">FileConnection</span></span>|<span data-ttu-id="c4073-488">0</span><span class="sxs-lookup"><span data-stu-id="c4073-488">0</span></span>|  
|<span data-ttu-id="c4073-489">Variable</span><span class="sxs-lookup"><span data-stu-id="c4073-489">Variable</span></span>|<span data-ttu-id="c4073-490">1</span><span class="sxs-lookup"><span data-stu-id="c4073-490">1</span></span>|  
  
 <span data-ttu-id="c4073-491">`WqlQuerySourceType`propiedad: se establece mediante el uso de valores de la `QuerySourceType` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-491">`WqlQuerySourceType` property-Set by using values from the `QuerySourceType` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-492">Nombre descriptivo en QuerySourceType</span><span class="sxs-lookup"><span data-stu-id="c4073-492">Friendly Name in QuerySourceType</span></span>|<span data-ttu-id="c4073-493">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-493">Numeric Value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="c4073-494">FileConnection</span><span class="sxs-lookup"><span data-stu-id="c4073-494">FileConnection</span></span>|<span data-ttu-id="c4073-495">0</span><span class="sxs-lookup"><span data-stu-id="c4073-495">0</span></span>|  
|<span data-ttu-id="c4073-496">DirectInput</span><span class="sxs-lookup"><span data-stu-id="c4073-496">DirectInput</span></span>|<span data-ttu-id="c4073-497">1</span><span class="sxs-lookup"><span data-stu-id="c4073-497">1</span></span>|  
|<span data-ttu-id="c4073-498">Variable</span><span class="sxs-lookup"><span data-stu-id="c4073-498">Variable</span></span>|<span data-ttu-id="c4073-499">2</span><span class="sxs-lookup"><span data-stu-id="c4073-499">2</span></span>|  
  
 <span data-ttu-id="c4073-500">Propiedad del monitor de eventos WMI `ActionAtEvent` : se establece mediante el uso de valores de la `ActionAtEvent` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-500">WMI Event Watcher `ActionAtEvent` property-Set by using values from the `ActionAtEvent` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-501">Nombre descriptivo en ActionAtEvent</span><span class="sxs-lookup"><span data-stu-id="c4073-501">Friendly Name in ActionAtEvent</span></span>|<span data-ttu-id="c4073-502">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-502">Numeric Value</span></span>|  
|------------------------------------|-------------------|  
|<span data-ttu-id="c4073-503">LogTheEventAndFireDTSEvent</span><span class="sxs-lookup"><span data-stu-id="c4073-503">LogTheEventAndFireDTSEvent</span></span>|<span data-ttu-id="c4073-504">0</span><span class="sxs-lookup"><span data-stu-id="c4073-504">0</span></span>|  
|<span data-ttu-id="c4073-505">LogTheEvent</span><span class="sxs-lookup"><span data-stu-id="c4073-505">LogTheEvent</span></span>|<span data-ttu-id="c4073-506">1</span><span class="sxs-lookup"><span data-stu-id="c4073-506">1</span></span>|  
  
 <span data-ttu-id="c4073-507">`ActionAtTimeout`propiedad: se establece mediante el uso de valores de la `ActionAtTimeout` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-507">`ActionAtTimeout` property-Set by using values from the `ActionAtTimeout` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-508">Nombre descriptivo en ActionAtTimeout</span><span class="sxs-lookup"><span data-stu-id="c4073-508">Friendly name in ActionAtTimeout</span></span>|<span data-ttu-id="c4073-509">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-509">Numeric value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="c4073-510">LogTimeoutAndFireDTSEvent</span><span class="sxs-lookup"><span data-stu-id="c4073-510">LogTimeoutAndFireDTSEvent</span></span>|<span data-ttu-id="c4073-511">0</span><span class="sxs-lookup"><span data-stu-id="c4073-511">0</span></span>|  
|<span data-ttu-id="c4073-512">LogTimeout</span><span class="sxs-lookup"><span data-stu-id="c4073-512">LogTimeout</span></span>|<span data-ttu-id="c4073-513">1</span><span class="sxs-lookup"><span data-stu-id="c4073-513">1</span></span>|  
  
 <span data-ttu-id="c4073-514">`AfterEvent`propiedad: se establece mediante el uso de valores de la `AfterEvent` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-514">`AfterEvent` property-Set by using values from the `AfterEvent` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-515">Nombre descriptivo en AfterEvent</span><span class="sxs-lookup"><span data-stu-id="c4073-515">Friendly name in AfterEvent</span></span>|<span data-ttu-id="c4073-516">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-516">Numeric value</span></span>|  
|---------------------------------|-------------------|  
|<span data-ttu-id="c4073-517">ReturnWithSuccess</span><span class="sxs-lookup"><span data-stu-id="c4073-517">ReturnWithSuccess</span></span>|<span data-ttu-id="c4073-518">0</span><span class="sxs-lookup"><span data-stu-id="c4073-518">0</span></span>|  
|<span data-ttu-id="c4073-519">ReturnWithFailure</span><span class="sxs-lookup"><span data-stu-id="c4073-519">ReturnWithFailure</span></span>|<span data-ttu-id="c4073-520">1</span><span class="sxs-lookup"><span data-stu-id="c4073-520">1</span></span>|  
|<span data-ttu-id="c4073-521">WatchfortheEventAgain</span><span class="sxs-lookup"><span data-stu-id="c4073-521">WatchfortheEventAgain</span></span>|<span data-ttu-id="c4073-522">2</span><span class="sxs-lookup"><span data-stu-id="c4073-522">2</span></span>|  
  
 <span data-ttu-id="c4073-523">`AfterTimeout`propiedad: se establece mediante el uso de valores de la `AfterTimeout` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-523">`AfterTimeout` property-Set by using values from the `AfterTimeout` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-524">Nombre descriptivo en AfterTimeout</span><span class="sxs-lookup"><span data-stu-id="c4073-524">Friendly name in AfterTimeout</span></span>|<span data-ttu-id="c4073-525">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-525">Numeric value</span></span>|  
|-----------------------------------|-------------------|  
|<span data-ttu-id="c4073-526">ReturnWithSuccess</span><span class="sxs-lookup"><span data-stu-id="c4073-526">ReturnWithSuccess</span></span>|<span data-ttu-id="c4073-527">0</span><span class="sxs-lookup"><span data-stu-id="c4073-527">0</span></span>|  
|<span data-ttu-id="c4073-528">ReturnWithFailure</span><span class="sxs-lookup"><span data-stu-id="c4073-528">ReturnWithFailure</span></span>|<span data-ttu-id="c4073-529">1</span><span class="sxs-lookup"><span data-stu-id="c4073-529">1</span></span>|  
|<span data-ttu-id="c4073-530">WatchfortheEventAgain</span><span class="sxs-lookup"><span data-stu-id="c4073-530">WatchfortheEventAgain</span></span>|<span data-ttu-id="c4073-531">2</span><span class="sxs-lookup"><span data-stu-id="c4073-531">2</span></span>|  
  
 <span data-ttu-id="c4073-532">`WqlQuerySourceType`propiedad: se establece mediante el uso de valores de la `QuerySourceType` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-532">`WqlQuerySourceType` property-Set by using values from the `QuerySourceType` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-533">Nombre descriptivo en QuerySourceType</span><span class="sxs-lookup"><span data-stu-id="c4073-533">Friendly name in QuerySourceType</span></span>|<span data-ttu-id="c4073-534">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-534">Numeric value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="c4073-535">FileConnection</span><span class="sxs-lookup"><span data-stu-id="c4073-535">FileConnection</span></span>|<span data-ttu-id="c4073-536">0</span><span class="sxs-lookup"><span data-stu-id="c4073-536">0</span></span>|  
|<span data-ttu-id="c4073-537">DirectInput</span><span class="sxs-lookup"><span data-stu-id="c4073-537">DirectInput</span></span>|<span data-ttu-id="c4073-538">1</span><span class="sxs-lookup"><span data-stu-id="c4073-538">1</span></span>|  
|<span data-ttu-id="c4073-539">Variable</span><span class="sxs-lookup"><span data-stu-id="c4073-539">Variable</span></span>|<span data-ttu-id="c4073-540">2</span><span class="sxs-lookup"><span data-stu-id="c4073-540">2</span></span>|  
  
### <a name="xml-task"></a><span data-ttu-id="c4073-541">Tarea XML</span><span class="sxs-lookup"><span data-stu-id="c4073-541">XML Task</span></span>  
 <span data-ttu-id="c4073-542">`OperationType`propiedad: se establece mediante el uso de valores de la `DTSXMLOperation` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-542">`OperationType` property-Set by using values from the `DTSXMLOperation` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-543">Nombre descriptivo en DTSXMLOperation</span><span class="sxs-lookup"><span data-stu-id="c4073-543">Friendly name in DTSXMLOperation</span></span>|<span data-ttu-id="c4073-544">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-544">Numeric value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="c4073-545">Validación</span><span class="sxs-lookup"><span data-stu-id="c4073-545">Validate</span></span>|<span data-ttu-id="c4073-546">0</span><span class="sxs-lookup"><span data-stu-id="c4073-546">0</span></span>|  
|<span data-ttu-id="c4073-547">XSLT</span><span class="sxs-lookup"><span data-stu-id="c4073-547">XSLT</span></span>|<span data-ttu-id="c4073-548">1</span><span class="sxs-lookup"><span data-stu-id="c4073-548">1</span></span>|  
|<span data-ttu-id="c4073-549">XPATH</span><span class="sxs-lookup"><span data-stu-id="c4073-549">XPATH</span></span>|<span data-ttu-id="c4073-550">2</span><span class="sxs-lookup"><span data-stu-id="c4073-550">2</span></span>|  
|<span data-ttu-id="c4073-551">Merge</span><span class="sxs-lookup"><span data-stu-id="c4073-551">Merge</span></span>|<span data-ttu-id="c4073-552">3</span><span class="sxs-lookup"><span data-stu-id="c4073-552">3</span></span>|  
|<span data-ttu-id="c4073-553">Diferencias</span><span class="sxs-lookup"><span data-stu-id="c4073-553">Diff</span></span>|<span data-ttu-id="c4073-554">4</span><span class="sxs-lookup"><span data-stu-id="c4073-554">4</span></span>|  
|<span data-ttu-id="c4073-555">Revisión</span><span class="sxs-lookup"><span data-stu-id="c4073-555">Patch</span></span>|<span data-ttu-id="c4073-556">5</span><span class="sxs-lookup"><span data-stu-id="c4073-556">5</span></span>|  
  
 <span data-ttu-id="c4073-557">`SourceType``SecondOperandType`propiedades, y `XPathSourceType` : se establece mediante el uso de valores de la `DTSXMLSourceType` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-557">`SourceType`, `SecondOperandType`, and `XPathSourceType` properties-Set by using values from the `DTSXMLSourceType` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-558">Nombre descriptivo en DTSXMLSourceType</span><span class="sxs-lookup"><span data-stu-id="c4073-558">Friendly name in DTSXMLSourceType</span></span>|<span data-ttu-id="c4073-559">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-559">Numeric value</span></span>|  
|---------------------------------------|-------------------|  
|<span data-ttu-id="c4073-560">FileConnection</span><span class="sxs-lookup"><span data-stu-id="c4073-560">FileConnection</span></span>|<span data-ttu-id="c4073-561">0</span><span class="sxs-lookup"><span data-stu-id="c4073-561">0</span></span>|  
|<span data-ttu-id="c4073-562">Variable</span><span class="sxs-lookup"><span data-stu-id="c4073-562">Variable</span></span>|<span data-ttu-id="c4073-563">1</span><span class="sxs-lookup"><span data-stu-id="c4073-563">1</span></span>|  
|<span data-ttu-id="c4073-564">DirectInput</span><span class="sxs-lookup"><span data-stu-id="c4073-564">DirectInput</span></span>|<span data-ttu-id="c4073-565">2</span><span class="sxs-lookup"><span data-stu-id="c4073-565">2</span></span>|  
  
 <span data-ttu-id="c4073-566">`DestinationType`y propiedades de **DiffGramDestinationType** : se establece mediante el uso de valores de la `DTSXMLSaveResultTo` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-566">`DestinationType` and **DiffGramDestinationType** properties-Set by using values from the `DTSXMLSaveResultTo` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-567">Nombre descriptivo en DTSXMLSaveResultTo</span><span class="sxs-lookup"><span data-stu-id="c4073-567">Friendly name in DTSXMLSaveResultTo</span></span>|<span data-ttu-id="c4073-568">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-568">Numeric value</span></span>|  
|-----------------------------------------|-------------------|  
|<span data-ttu-id="c4073-569">FileConnection</span><span class="sxs-lookup"><span data-stu-id="c4073-569">FileConnection</span></span>|<span data-ttu-id="c4073-570">0</span><span class="sxs-lookup"><span data-stu-id="c4073-570">0</span></span>|  
|<span data-ttu-id="c4073-571">Variable</span><span class="sxs-lookup"><span data-stu-id="c4073-571">Variable</span></span>|<span data-ttu-id="c4073-572">1</span><span class="sxs-lookup"><span data-stu-id="c4073-572">1</span></span>|  
  
 <span data-ttu-id="c4073-573">`ValidationType`propiedad: se establece mediante el uso de valores de la `DTSXMLValidationType` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-573">`ValidationType` property-Set by using values from the `DTSXMLValidationType` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-574">Nombre descriptivo en DTSXMLValidationType</span><span class="sxs-lookup"><span data-stu-id="c4073-574">Friendly name in DTSXMLValidationType</span></span>|<span data-ttu-id="c4073-575">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-575">Numeric value</span></span>|  
|-------------------------------------------|-------------------|  
|<span data-ttu-id="c4073-576">DTD</span><span class="sxs-lookup"><span data-stu-id="c4073-576">DTD</span></span>|<span data-ttu-id="c4073-577">0</span><span class="sxs-lookup"><span data-stu-id="c4073-577">0</span></span>|  
|<span data-ttu-id="c4073-578">XSD</span><span class="sxs-lookup"><span data-stu-id="c4073-578">XSD</span></span>|<span data-ttu-id="c4073-579">1</span><span class="sxs-lookup"><span data-stu-id="c4073-579">1</span></span>|  
  
 <span data-ttu-id="c4073-580">`XPathOperation`propiedad: se establece mediante el uso de valores de la `DTSXMLXPathOperation` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-580">`XPathOperation` property-Set by using values from the `DTSXMLXPathOperation` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-581">Nombre descriptivo en DTSXMLXPathOperation</span><span class="sxs-lookup"><span data-stu-id="c4073-581">Friendly name in DTSXMLXPathOperation</span></span>|<span data-ttu-id="c4073-582">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-582">Numeric Value</span></span>|  
|-------------------------------------------|-------------------|  
|<span data-ttu-id="c4073-583">Evaluación</span><span class="sxs-lookup"><span data-stu-id="c4073-583">Evaluation</span></span>|<span data-ttu-id="c4073-584">0</span><span class="sxs-lookup"><span data-stu-id="c4073-584">0</span></span>|  
|<span data-ttu-id="c4073-585">Valores</span><span class="sxs-lookup"><span data-stu-id="c4073-585">Values</span></span>|<span data-ttu-id="c4073-586">1</span><span class="sxs-lookup"><span data-stu-id="c4073-586">1</span></span>|  
|<span data-ttu-id="c4073-587">NodeList</span><span class="sxs-lookup"><span data-stu-id="c4073-587">NodeList</span></span>|<span data-ttu-id="c4073-588">2</span><span class="sxs-lookup"><span data-stu-id="c4073-588">2</span></span>|  
  
 <span data-ttu-id="c4073-589">`DiffOptions`propiedad: se establece mediante el uso de valores de la `DTSXMLDiffOptions` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-589">`DiffOptions` property-Set by using values from the `DTSXMLDiffOptions` enumeration.</span></span> <span data-ttu-id="c4073-590">Las opciones de este enumerador no se excluyen mutualmente.</span><span class="sxs-lookup"><span data-stu-id="c4073-590">The options in this enumerator are not mutually exclusive.</span></span> <span data-ttu-id="c4073-591">Para utilizar varias opciones, proporcione una lista separada por comas de las opciones que se deben aplicar.</span><span class="sxs-lookup"><span data-stu-id="c4073-591">To use multiple options, provide a comma-separated list of the options to apply.</span></span>  
  
|<span data-ttu-id="c4073-592">Nombre descriptivo en DTSXMLDiffOptions</span><span class="sxs-lookup"><span data-stu-id="c4073-592">Friendly name in DTSXMLDiffOptions</span></span>|<span data-ttu-id="c4073-593">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-593">Numeric Value</span></span>|  
|----------------------------------------|-------------------|  
|<span data-ttu-id="c4073-594">None</span><span class="sxs-lookup"><span data-stu-id="c4073-594">None</span></span>|<span data-ttu-id="c4073-595">0</span><span class="sxs-lookup"><span data-stu-id="c4073-595">0</span></span>|  
|<span data-ttu-id="c4073-596">IgnoreChildOrder</span><span class="sxs-lookup"><span data-stu-id="c4073-596">IgnoreChildOrder</span></span>|<span data-ttu-id="c4073-597">1</span><span class="sxs-lookup"><span data-stu-id="c4073-597">1</span></span>|  
|<span data-ttu-id="c4073-598">IgnoreComments</span><span class="sxs-lookup"><span data-stu-id="c4073-598">IgnoreComments</span></span>|<span data-ttu-id="c4073-599">2</span><span class="sxs-lookup"><span data-stu-id="c4073-599">2</span></span>|  
|<span data-ttu-id="c4073-600">IgnorePI</span><span class="sxs-lookup"><span data-stu-id="c4073-600">IgnorePI</span></span>|<span data-ttu-id="c4073-601">4</span><span class="sxs-lookup"><span data-stu-id="c4073-601">4</span></span>|  
|<span data-ttu-id="c4073-602">IgnoreWhitespace</span><span class="sxs-lookup"><span data-stu-id="c4073-602">IgnoreWhitespace</span></span>|<span data-ttu-id="c4073-603">8</span><span class="sxs-lookup"><span data-stu-id="c4073-603">8</span></span>|  
|<span data-ttu-id="c4073-604">IgnoreNameSpaces</span><span class="sxs-lookup"><span data-stu-id="c4073-604">IgnoreNamespaces</span></span>|<span data-ttu-id="c4073-605">16</span><span class="sxs-lookup"><span data-stu-id="c4073-605">16</span></span>|  
|<span data-ttu-id="c4073-606">IgnorePrefixes</span><span class="sxs-lookup"><span data-stu-id="c4073-606">IgnorePrefixes</span></span>|<span data-ttu-id="c4073-607">32</span><span class="sxs-lookup"><span data-stu-id="c4073-607">32</span></span>|  
|<span data-ttu-id="c4073-608">IgnoreXmlDecl</span><span class="sxs-lookup"><span data-stu-id="c4073-608">IgnoreXmlDecl</span></span>|<span data-ttu-id="c4073-609">64</span><span class="sxs-lookup"><span data-stu-id="c4073-609">64</span></span>|  
|<span data-ttu-id="c4073-610">IgnoreDtd</span><span class="sxs-lookup"><span data-stu-id="c4073-610">IgnoreDtd</span></span>|<span data-ttu-id="c4073-611">128</span><span class="sxs-lookup"><span data-stu-id="c4073-611">128</span></span>|  
  
 <span data-ttu-id="c4073-612">`DiffAlgorithm`propiedad: se establece mediante el uso de valores de la `DTSXMLDiffAlgorithm` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-612">`DiffAlgorithm` property-Set by using values from the `DTSXMLDiffAlgorithm` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-613">Nombre descriptivo en DTSXMLDiffAlgorithm</span><span class="sxs-lookup"><span data-stu-id="c4073-613">Friendly name in DTSXMLDiffAlgorithm</span></span>|<span data-ttu-id="c4073-614">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-614">Numeric value</span></span>|  
|------------------------------------------|-------------------|  
|<span data-ttu-id="c4073-615">Automático</span><span class="sxs-lookup"><span data-stu-id="c4073-615">Auto</span></span>|<span data-ttu-id="c4073-616">0</span><span class="sxs-lookup"><span data-stu-id="c4073-616">0</span></span>|  
|<span data-ttu-id="c4073-617">Fast (rápido)</span><span class="sxs-lookup"><span data-stu-id="c4073-617">Fast</span></span>|<span data-ttu-id="c4073-618">1</span><span class="sxs-lookup"><span data-stu-id="c4073-618">1</span></span>|  
|<span data-ttu-id="c4073-619">Preciso</span><span class="sxs-lookup"><span data-stu-id="c4073-619">Precise</span></span>|<span data-ttu-id="c4073-620">2</span><span class="sxs-lookup"><span data-stu-id="c4073-620">2</span></span>|  
  
##  <a name="maintenance-plan-tasks"></a><a name="MaintenancePlanTasks"></a> <span data-ttu-id="c4073-621">Tareas del plan de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="c4073-621">Maintenance Plan Tasks</span></span>  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="c4073-622">incluye un conjunto de tareas que realiza tareas de SQL Server para utilizar en planes de mantenimiento y paquetes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c4073-622">includes a set of tasks that perform SQL Server tasks for use in maintenance plans and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c4073-623">no admite el trabajo con estas tareas mediante programación y la documentación de referencia de programación no incluye documentación de API de estas tareas y sus enumeradores.</span><span class="sxs-lookup"><span data-stu-id="c4073-623">does not support working with these tasks programmatically and programming reference documentation does not include API documentation of these tasks and their enumerators.</span></span>  
  
### <a name="all-maintenance-tasks"></a><span data-ttu-id="c4073-624">Todas las tareas de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="c4073-624">All Maintenance Tasks</span></span>  
 <span data-ttu-id="c4073-625">Todas las tareas de mantenimiento utilizan las siguientes enumeraciones para establecer las propiedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="c4073-625">All maintenance tasks use the following enumerations to set the specified properties.</span></span>  
  
 <span data-ttu-id="c4073-626">`DatabaseSelectionType`propiedad: se establece mediante el uso de valores de la `DatabaseSelection` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-626">`DatabaseSelectionType` property-Set by using values from the `DatabaseSelection` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-627">Nombre descriptivo en DatabaseSelection</span><span class="sxs-lookup"><span data-stu-id="c4073-627">Friendly name in DatabaseSelection</span></span>|<span data-ttu-id="c4073-628">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-628">Numeric value</span></span>|  
|----------------------------------------|-------------------|  
|<span data-ttu-id="c4073-629">None</span><span class="sxs-lookup"><span data-stu-id="c4073-629">None</span></span>|<span data-ttu-id="c4073-630">0</span><span class="sxs-lookup"><span data-stu-id="c4073-630">0</span></span>|  
|<span data-ttu-id="c4073-631">All</span><span class="sxs-lookup"><span data-stu-id="c4073-631">All</span></span>|<span data-ttu-id="c4073-632">1</span><span class="sxs-lookup"><span data-stu-id="c4073-632">1</span></span>|  
|<span data-ttu-id="c4073-633">Sistema</span><span class="sxs-lookup"><span data-stu-id="c4073-633">System</span></span>|<span data-ttu-id="c4073-634">2</span><span class="sxs-lookup"><span data-stu-id="c4073-634">2</span></span>|  
|<span data-ttu-id="c4073-635">Usuario</span><span class="sxs-lookup"><span data-stu-id="c4073-635">User</span></span>|<span data-ttu-id="c4073-636">3</span><span class="sxs-lookup"><span data-stu-id="c4073-636">3</span></span>|  
|<span data-ttu-id="c4073-637">Específico</span><span class="sxs-lookup"><span data-stu-id="c4073-637">Specific</span></span>|<span data-ttu-id="c4073-638">4</span><span class="sxs-lookup"><span data-stu-id="c4073-638">4</span></span>|  
  
 <span data-ttu-id="c4073-639">`TableSelectionType`propiedad: se establece mediante el uso de valores de la `TableSelection` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-639">`TableSelectionType` property-Set by using values from the `TableSelection` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-640">Nombre descriptivo en TableSelection</span><span class="sxs-lookup"><span data-stu-id="c4073-640">Friendly name in TableSelection</span></span>|<span data-ttu-id="c4073-641">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-641">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="c4073-642">None</span><span class="sxs-lookup"><span data-stu-id="c4073-642">None</span></span>|<span data-ttu-id="c4073-643">0</span><span class="sxs-lookup"><span data-stu-id="c4073-643">0</span></span>|  
|<span data-ttu-id="c4073-644">All</span><span class="sxs-lookup"><span data-stu-id="c4073-644">All</span></span>|<span data-ttu-id="c4073-645">1</span><span class="sxs-lookup"><span data-stu-id="c4073-645">1</span></span>|  
|<span data-ttu-id="c4073-646">Específico</span><span class="sxs-lookup"><span data-stu-id="c4073-646">Specific</span></span>|<span data-ttu-id="c4073-647">2</span><span class="sxs-lookup"><span data-stu-id="c4073-647">2</span></span>|  
  
 <span data-ttu-id="c4073-648">`ObjectTypeSelection`propiedad: se establece mediante el uso de valores de la `ObjectType` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-648">`ObjectTypeSelection` property-Set by using values from the `ObjectType` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-649">Nombre descriptivo en ObjectType</span><span class="sxs-lookup"><span data-stu-id="c4073-649">Friendly name in ObjectType</span></span>|<span data-ttu-id="c4073-650">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-650">Numeric value</span></span>|  
|---------------------------------|-------------------|  
|<span data-ttu-id="c4073-651">Tabla</span><span class="sxs-lookup"><span data-stu-id="c4073-651">Table</span></span>|<span data-ttu-id="c4073-652">0</span><span class="sxs-lookup"><span data-stu-id="c4073-652">0</span></span>|  
|<span data-ttu-id="c4073-653">Ver</span><span class="sxs-lookup"><span data-stu-id="c4073-653">View</span></span>|<span data-ttu-id="c4073-654">1</span><span class="sxs-lookup"><span data-stu-id="c4073-654">1</span></span>|  
|<span data-ttu-id="c4073-655">TableView</span><span class="sxs-lookup"><span data-stu-id="c4073-655">TableView</span></span>|<span data-ttu-id="c4073-656">2</span><span class="sxs-lookup"><span data-stu-id="c4073-656">2</span></span>|  
  
### <a name="back-up-database-task"></a><span data-ttu-id="c4073-657">Tarea Copia de seguridad de la base de datos</span><span class="sxs-lookup"><span data-stu-id="c4073-657">Back Up Database Task</span></span>  
 <span data-ttu-id="c4073-658">`DestinationCreationType`propiedad: se establece mediante el uso de valores de la `DestinationType` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-658">`DestinationCreationType` property-Set by using values from the `DestinationType` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-659">Nombre descriptivo en DestinationType</span><span class="sxs-lookup"><span data-stu-id="c4073-659">Friendly name in DestinationType</span></span>|<span data-ttu-id="c4073-660">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-660">Numeric value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="c4073-661">Automático</span><span class="sxs-lookup"><span data-stu-id="c4073-661">Auto</span></span>|<span data-ttu-id="c4073-662">0</span><span class="sxs-lookup"><span data-stu-id="c4073-662">0</span></span>|  
|<span data-ttu-id="c4073-663">Manual</span><span class="sxs-lookup"><span data-stu-id="c4073-663">Manual</span></span>|<span data-ttu-id="c4073-664">1</span><span class="sxs-lookup"><span data-stu-id="c4073-664">1</span></span>|  
  
 <span data-ttu-id="c4073-665">`ExistingBackupsAction`propiedad: se establece mediante el uso de valores de la `ActionForExistingBackups` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-665">`ExistingBackupsAction` property-Set by using values from the `ActionForExistingBackups` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-666">Nombre descriptivo en ActionForExistingBackups</span><span class="sxs-lookup"><span data-stu-id="c4073-666">Friendly name in ActionForExistingBackups</span></span>|<span data-ttu-id="c4073-667">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-667">Numeric value</span></span>|  
|-----------------------------------------------|-------------------|  
|<span data-ttu-id="c4073-668">Append</span><span class="sxs-lookup"><span data-stu-id="c4073-668">Append</span></span>|<span data-ttu-id="c4073-669">0</span><span class="sxs-lookup"><span data-stu-id="c4073-669">0</span></span>|  
|<span data-ttu-id="c4073-670">Sobrescribir</span><span class="sxs-lookup"><span data-stu-id="c4073-670">Overwrite</span></span>|<span data-ttu-id="c4073-671">1</span><span class="sxs-lookup"><span data-stu-id="c4073-671">1</span></span>|  
  
 <span data-ttu-id="c4073-672">`BackupAction`propiedad: se establece mediante el uso de valores de la `BackupTaskType` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-672">`BackupAction` property-Set by using values from the `BackupTaskType` enumeration.</span></span> <span data-ttu-id="c4073-673">Esta propiedad trabaja con la propiedad `BackupIsIncremental` para definir el tipo de copia de seguridad que realiza la tarea.</span><span class="sxs-lookup"><span data-stu-id="c4073-673">This property works with the `BackupIsIncremental` property to define the type of backup that the task performs.</span></span>  
  
|<span data-ttu-id="c4073-674">Nombre descriptivo en BackupTaskType</span><span class="sxs-lookup"><span data-stu-id="c4073-674">Friendly name in BackupTaskType</span></span>|<span data-ttu-id="c4073-675">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-675">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="c4073-676">Base de datos</span><span class="sxs-lookup"><span data-stu-id="c4073-676">Database</span></span>|<span data-ttu-id="c4073-677">0</span><span class="sxs-lookup"><span data-stu-id="c4073-677">0</span></span>|  
|<span data-ttu-id="c4073-678">Archivos</span><span class="sxs-lookup"><span data-stu-id="c4073-678">Files</span></span>|<span data-ttu-id="c4073-679">1</span><span class="sxs-lookup"><span data-stu-id="c4073-679">1</span></span>|  
|<span data-ttu-id="c4073-680">Log</span><span class="sxs-lookup"><span data-stu-id="c4073-680">Log</span></span>|<span data-ttu-id="c4073-681">2</span><span class="sxs-lookup"><span data-stu-id="c4073-681">2</span></span>|  
  
 <span data-ttu-id="c4073-682">`BackupDevice`Conjunto de propiedades mediante el uso de valores de la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] enumeración de objetos de administración de (SMO) `DeviceType` .</span><span class="sxs-lookup"><span data-stu-id="c4073-682">`BackupDevice` property-Set by using values from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects (SMO) `DeviceType` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-683">Nombre descriptivo en DeviceType</span><span class="sxs-lookup"><span data-stu-id="c4073-683">Friendly name in DeviceType</span></span>|<span data-ttu-id="c4073-684">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-684">Numeric value</span></span>|  
|---------------------------------|-------------------|  
|<span data-ttu-id="c4073-685">LogicalDevice</span><span class="sxs-lookup"><span data-stu-id="c4073-685">LogicalDevice</span></span>|<span data-ttu-id="c4073-686">0</span><span class="sxs-lookup"><span data-stu-id="c4073-686">0</span></span>|  
|<span data-ttu-id="c4073-687">Cinta</span><span class="sxs-lookup"><span data-stu-id="c4073-687">Tape</span></span>|<span data-ttu-id="c4073-688">1</span><span class="sxs-lookup"><span data-stu-id="c4073-688">1</span></span>|  
|<span data-ttu-id="c4073-689">Archivo</span><span class="sxs-lookup"><span data-stu-id="c4073-689">File</span></span>|<span data-ttu-id="c4073-690">2</span><span class="sxs-lookup"><span data-stu-id="c4073-690">2</span></span>|  
|<span data-ttu-id="c4073-691">Pipe</span><span class="sxs-lookup"><span data-stu-id="c4073-691">Pipe</span></span>|<span data-ttu-id="c4073-692">3</span><span class="sxs-lookup"><span data-stu-id="c4073-692">3</span></span>|  
|<span data-ttu-id="c4073-693">VirtualDevice</span><span class="sxs-lookup"><span data-stu-id="c4073-693">VirtualDevice</span></span>|<span data-ttu-id="c4073-694">4</span><span class="sxs-lookup"><span data-stu-id="c4073-694">4</span></span>|  
  
### <a name="maintenance-cleanup-task"></a><span data-ttu-id="c4073-695">tarea, Limpieza de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="c4073-695">Maintenance Cleanup Task</span></span>  
 <span data-ttu-id="c4073-696">`FileTypeSelected`propiedad: se establece mediante el uso de valores de la `FileType` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-696">`FileTypeSelected` property-Set by using values from the `FileType` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-697">Nombre descriptivo en FileType</span><span class="sxs-lookup"><span data-stu-id="c4073-697">Friendly name in FileType</span></span>|<span data-ttu-id="c4073-698">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-698">Numeric value</span></span>|  
|-------------------------------|-------------------|  
|<span data-ttu-id="c4073-699">FileBackup</span><span class="sxs-lookup"><span data-stu-id="c4073-699">FileBackup</span></span>|<span data-ttu-id="c4073-700">0</span><span class="sxs-lookup"><span data-stu-id="c4073-700">0</span></span>|  
|<span data-ttu-id="c4073-701">FileReport</span><span class="sxs-lookup"><span data-stu-id="c4073-701">FileReport</span></span>|<span data-ttu-id="c4073-702">1</span><span class="sxs-lookup"><span data-stu-id="c4073-702">1</span></span>|  
  
 <span data-ttu-id="c4073-703">`OlderThanTimeUnitType`propiedad: se establece mediante el uso de valores de la `TimeUnitType` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-703">`OlderThanTimeUnitType` property-Set by using values from the `TimeUnitType` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-704">Nombre descriptivo en TimeUnitType</span><span class="sxs-lookup"><span data-stu-id="c4073-704">Friendly Name in TimeUnitType</span></span>|<span data-ttu-id="c4073-705">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-705">Numeric Value</span></span>|  
|-----------------------------------|-------------------|  
|<span data-ttu-id="c4073-706">Día</span><span class="sxs-lookup"><span data-stu-id="c4073-706">Day</span></span>|<span data-ttu-id="c4073-707">0</span><span class="sxs-lookup"><span data-stu-id="c4073-707">0</span></span>|  
|<span data-ttu-id="c4073-708">Semana</span><span class="sxs-lookup"><span data-stu-id="c4073-708">Week</span></span>|<span data-ttu-id="c4073-709">1</span><span class="sxs-lookup"><span data-stu-id="c4073-709">1</span></span>|  
|<span data-ttu-id="c4073-710">Month</span><span class="sxs-lookup"><span data-stu-id="c4073-710">Month</span></span>|<span data-ttu-id="c4073-711">2</span><span class="sxs-lookup"><span data-stu-id="c4073-711">2</span></span>|  
|<span data-ttu-id="c4073-712">Year</span><span class="sxs-lookup"><span data-stu-id="c4073-712">Year</span></span>|<span data-ttu-id="c4073-713">3</span><span class="sxs-lookup"><span data-stu-id="c4073-713">3</span></span>|  
  
### <a name="update-statistics-task"></a><span data-ttu-id="c4073-714">Tarea Actualizar estadísticas</span><span class="sxs-lookup"><span data-stu-id="c4073-714">Update Statistics Task</span></span>  
 <span data-ttu-id="c4073-715">`UpdateType`Conjunto de propiedades mediante el uso de valores de la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] enumeración de objetos de administración de (SMO) `StatisticsTarget` .</span><span class="sxs-lookup"><span data-stu-id="c4073-715">`UpdateType` property-Set by using values from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects (SMO) `StatisticsTarget` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-716">Nombre descriptivo en StatisticsTarget</span><span class="sxs-lookup"><span data-stu-id="c4073-716">Friendly name in StatisticsTarget</span></span>|<span data-ttu-id="c4073-717">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-717">Numeric value</span></span>|  
|---------------------------------------|-------------------|  
|<span data-ttu-id="c4073-718">Columna</span><span class="sxs-lookup"><span data-stu-id="c4073-718">Column</span></span>|<span data-ttu-id="c4073-719">1</span><span class="sxs-lookup"><span data-stu-id="c4073-719">1</span></span>|  
|<span data-ttu-id="c4073-720">Índice</span><span class="sxs-lookup"><span data-stu-id="c4073-720">Index</span></span>|<span data-ttu-id="c4073-721">2</span><span class="sxs-lookup"><span data-stu-id="c4073-721">2</span></span>|  
|<span data-ttu-id="c4073-722">All</span><span class="sxs-lookup"><span data-stu-id="c4073-722">All</span></span>|<span data-ttu-id="c4073-723">3</span><span class="sxs-lookup"><span data-stu-id="c4073-723">3</span></span>|  
  
##  <a name="common-properties"></a><a name="CommonProperties"></a> <span data-ttu-id="c4073-724">Propiedades comunes</span><span class="sxs-lookup"><span data-stu-id="c4073-724">Common Properties</span></span>  
 <span data-ttu-id="c4073-725">Los paquetes, tareas, y los contenedores de secuencias, de bucles Foreach y de bucles For pueden utilizar las siguientes enumeraciones para establecer las propiedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="c4073-725">Packages, tasks, and the Foreach Loop, For Loop, and Sequence containers can use the following enumerations to set the specified properties.</span></span>  
  
 <span data-ttu-id="c4073-726">`ForceExecutionResult`propiedad: se establece mediante el uso de valores de la `DTSForcedExecResult` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-726">`ForceExecutionResult` property-Set by using values from the `DTSForcedExecResult` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-727">Nombre descriptivo en DTSForcedExecResult</span><span class="sxs-lookup"><span data-stu-id="c4073-727">Friendly name in DTSForcedExecResult</span></span>|<span data-ttu-id="c4073-728">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-728">Numeric value</span></span>|  
|------------------------------------------|-------------------|  
|<span data-ttu-id="c4073-729">None</span><span class="sxs-lookup"><span data-stu-id="c4073-729">None</span></span>|<span data-ttu-id="c4073-730">-1</span><span class="sxs-lookup"><span data-stu-id="c4073-730">-1</span></span>|  
|<span data-ttu-id="c4073-731">Correcto</span><span class="sxs-lookup"><span data-stu-id="c4073-731">Success</span></span>|<span data-ttu-id="c4073-732">0</span><span class="sxs-lookup"><span data-stu-id="c4073-732">0</span></span>|  
|<span data-ttu-id="c4073-733">Error</span><span class="sxs-lookup"><span data-stu-id="c4073-733">Failure</span></span>|<span data-ttu-id="c4073-734">1</span><span class="sxs-lookup"><span data-stu-id="c4073-734">1</span></span>|  
|<span data-ttu-id="c4073-735">Completion</span><span class="sxs-lookup"><span data-stu-id="c4073-735">Completion</span></span>|<span data-ttu-id="c4073-736">2</span><span class="sxs-lookup"><span data-stu-id="c4073-736">2</span></span>|  
  
 <span data-ttu-id="c4073-737">`IsolationLevel`propiedad: se establece mediante la `IsolationLevel` enumeración .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c4073-737">`IsolationLevel` property-Set by the .NET Framework `IsolationLevel` enumeration.</span></span> <span data-ttu-id="c4073-738">Para obtener más información, vea la biblioteca de clases de .NET Framework. en [MSDN Library](https://go.microsoft.com/fwlink?LinkId=17313).</span><span class="sxs-lookup"><span data-stu-id="c4073-738">For more information, see the .NET Framework Class Library in the [MSDN Library](https://go.microsoft.com/fwlink?LinkId=17313).</span></span>  
  
 <span data-ttu-id="c4073-739">`LoggingMode`propiedad: se establece mediante el uso de valores de la `DTSLoggingMode` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-739">`LoggingMode` property-Set by using values from the `DTSLoggingMode` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-740">Nombre descriptivo en DTSLoggingMode</span><span class="sxs-lookup"><span data-stu-id="c4073-740">Friendly name in DTSLoggingMode</span></span>|<span data-ttu-id="c4073-741">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-741">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="c4073-742">UseParentSetting</span><span class="sxs-lookup"><span data-stu-id="c4073-742">UseParentSetting</span></span>|<span data-ttu-id="c4073-743">0</span><span class="sxs-lookup"><span data-stu-id="c4073-743">0</span></span>|  
|<span data-ttu-id="c4073-744">habilitado</span><span class="sxs-lookup"><span data-stu-id="c4073-744">Enabled</span></span>|<span data-ttu-id="c4073-745">1</span><span class="sxs-lookup"><span data-stu-id="c4073-745">1</span></span>|  
|<span data-ttu-id="c4073-746">Disabled</span><span class="sxs-lookup"><span data-stu-id="c4073-746">Disabled</span></span>|<span data-ttu-id="c4073-747">2</span><span class="sxs-lookup"><span data-stu-id="c4073-747">2</span></span>|  
  
 <span data-ttu-id="c4073-748">`TransactionOption`propiedad: se establece mediante el uso de valores de la `DTSTransactionOption` enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4073-748">`TransactionOption` property-Set by using values from the `DTSTransactionOption` enumeration.</span></span>  
  
|<span data-ttu-id="c4073-749">Nombre descriptivo en DTSTransactionOption</span><span class="sxs-lookup"><span data-stu-id="c4073-749">Friendly name in DTSTransactionOption</span></span>|<span data-ttu-id="c4073-750">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="c4073-750">Numeric value</span></span>|  
|-------------------------------------------|-------------------|  
|<span data-ttu-id="c4073-751">NotSupported</span><span class="sxs-lookup"><span data-stu-id="c4073-751">NotSupported</span></span>|<span data-ttu-id="c4073-752">0</span><span class="sxs-lookup"><span data-stu-id="c4073-752">0</span></span>|  
|<span data-ttu-id="c4073-753">Compatible</span><span class="sxs-lookup"><span data-stu-id="c4073-753">Supported</span></span>|<span data-ttu-id="c4073-754">1</span><span class="sxs-lookup"><span data-stu-id="c4073-754">1</span></span>|  
|<span data-ttu-id="c4073-755">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="c4073-755">Required</span></span>|<span data-ttu-id="c4073-756">2</span><span class="sxs-lookup"><span data-stu-id="c4073-756">2</span></span>|  
  
## <a name="related-tasks"></a><span data-ttu-id="c4073-757">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="c4073-757">Related Tasks</span></span>  
 [<span data-ttu-id="c4073-758">Agregar o cambiar una expresión de propiedad</span><span class="sxs-lookup"><span data-stu-id="c4073-758">Add or Change a Property Expression</span></span>](add-or-change-a-property-expression.md)  
  
## <a name="see-also"></a><span data-ttu-id="c4073-759">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c4073-759">See Also</span></span>  
 <span data-ttu-id="c4073-760">[Usar expresiones de propiedad en paquetes](use-property-expressions-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="c4073-760">[Use Property Expressions in Packages](use-property-expressions-in-packages.md) </span></span>  
 <span data-ttu-id="c4073-761">[Paquetes de Integration Services &#40;SSIS&#41;](../integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="c4073-761">[Integration Services &#40;SSIS&#41; Packages](../integration-services-ssis-packages.md) </span></span>  
 <span data-ttu-id="c4073-762">[Contenedores de Integration Services](../control-flow/integration-services-containers.md) </span><span class="sxs-lookup"><span data-stu-id="c4073-762">[Integration Services Containers](../control-flow/integration-services-containers.md) </span></span>  
 <span data-ttu-id="c4073-763">[Tareas de Integration Services](../control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="c4073-763">[Integration Services Tasks](../control-flow/integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="c4073-764">Restricciones de precedencia</span><span class="sxs-lookup"><span data-stu-id="c4073-764">Precedence Constraints</span></span>](../control-flow/precedence-constraints.md)  
  
  
