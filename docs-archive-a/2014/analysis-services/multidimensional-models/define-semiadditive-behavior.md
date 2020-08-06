---
title: Definir el comportamiento de suma parcial | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- semiadditive
- Business Intelligence enhancements [Analysis Services], semiadditive behavior
- measures [Analysis Services], semiadditive
ms.assetid: b25726bc-728b-4601-ad87-9015c39dc615
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9c2028c350046fdcc9f98bcd0f0612d6a91ccabb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673377"
---
# <a name="define-semiadditive-behavior"></a><span data-ttu-id="917ea-102">Define Semiadditive Behavior</span><span class="sxs-lookup"><span data-stu-id="917ea-102">Define Semiadditive Behavior</span></span>
  <span data-ttu-id="917ea-103">Las medidas semiaditivas, que no agregan uniformemente en todas las dimensiones, son muy comunes en muchas situaciones empresariales.</span><span class="sxs-lookup"><span data-stu-id="917ea-103">Semiadditive measures, which do not uniformly aggregate across all dimensions, are very common in many business scenarios.</span></span> <span data-ttu-id="917ea-104">Todos los cubos que se basan en instantáneas de saldos a lo largo del tiempo presentan este problema.</span><span class="sxs-lookup"><span data-stu-id="917ea-104">Every cube that is based on snapshots of balances over time exhibits this problem.</span></span> <span data-ttu-id="917ea-105">Se pueden encontrar estas instantáneas en las aplicaciones que manejan títulos y valores, saldos de cuentas bancarias, presupuestos, recursos humanos, pólizas y siniestros de seguros y muchos otros ámbitos comerciales.</span><span class="sxs-lookup"><span data-stu-id="917ea-105">You can find these snapshots in applications dealing with securities, account balances, budgeting, human resources, insurance policies and claims, and many other business domains.</span></span>  
  
 <span data-ttu-id="917ea-106">Se agrega comportamiento de suma parcial a un cubo para definir un método de agregación para medidas o miembros individuales del atributo de tipo de cuenta.</span><span class="sxs-lookup"><span data-stu-id="917ea-106">Add semiadditive behavior to a cube to define an aggregation method for individual measures or members of the account type attribute.</span></span> <span data-ttu-id="917ea-107">Si el cubo contiene una dimensión de cuenta, puede establecer automáticamente un comportamiento de suma parcial basado en el tipo de cuenta.</span><span class="sxs-lookup"><span data-stu-id="917ea-107">If the cube contains an account dimension, you can automatically set semiadditive behavior based on the account type.</span></span>  
  
 <span data-ttu-id="917ea-108">Para agregar un comportamiento de suma parcial, abra un cubo en el Diseñador de cubos y elija **Agregar Business Intelligence** en el menú Cubo.</span><span class="sxs-lookup"><span data-stu-id="917ea-108">To add semiadditive behavior, open a cube in Cube Designer and choose **Add Business Intelligence** from the Cube menu.</span></span> <span data-ttu-id="917ea-109">En el Asistente de Business Intelligence, seleccione la opción **Definir el comportamiento de suma parcial** en la página **Elegir mejora** .</span><span class="sxs-lookup"><span data-stu-id="917ea-109">In the Business Intelligence Wizard, select the **Define semiadditive behavior** option on the **Choose Enhancement** page.</span></span> <span data-ttu-id="917ea-110">Este asistente le guía por el proceso de identificar las medidas que tienen un comportamiento de suma parcial.</span><span class="sxs-lookup"><span data-stu-id="917ea-110">This wizard then guides you through the steps of identifying which measures have semiadditive behavior.</span></span>  
  
 <span data-ttu-id="917ea-111">Excepto LastChild, que está disponible en la edición Standard, los comportamientos de suma parcial solo están disponibles en las ediciones Business Intelligence o Enterprise.</span><span class="sxs-lookup"><span data-stu-id="917ea-111">With the exception of LastChild which is available in the standard edition, semi-additive behaviors are only available in the business intelligence or enterprise editions.</span></span>  
  
## <a name="define-semiadditive-behavior"></a><span data-ttu-id="917ea-112">Define Semiadditive Behavior</span><span class="sxs-lookup"><span data-stu-id="917ea-112">Define Semiadditive Behavior</span></span>  
 <span data-ttu-id="917ea-113">En la página **Definir el comportamiento de suma parcial** del asistente, seleccione cómo definir la suma parcial eligiendo una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="917ea-113">On the **Define Semiadditive Behavior** page of the wizard, you select how to define semiadditivity by selecting one of the following options:</span></span>  
  
 <span data-ttu-id="917ea-114">**Desactivar el comportamiento de suma parcial**</span><span class="sxs-lookup"><span data-stu-id="917ea-114">**Turn off semiadditive behavior**</span></span>  
 <span data-ttu-id="917ea-115">Elimina el comportamiento de suma parcial de un cubo en el que se definió anteriormente el comportamiento de suma parcial.</span><span class="sxs-lookup"><span data-stu-id="917ea-115">Removes semiadditive behavior from a cube in which semiadditive behavior was previously defined.</span></span> <span data-ttu-id="917ea-116">Esta selección restablece una medida en `SUM` si se establece en uno de los siguientes tipos de función de agregación:</span><span class="sxs-lookup"><span data-stu-id="917ea-116">This selection resets a measure to `SUM` if it is set to any of the following aggregation function types:</span></span>  
  
-   <span data-ttu-id="917ea-117">By Account</span><span class="sxs-lookup"><span data-stu-id="917ea-117">By Account</span></span>  
  
-   <span data-ttu-id="917ea-118">Average of Children</span><span class="sxs-lookup"><span data-stu-id="917ea-118">Average of Children</span></span>  
  
-   <span data-ttu-id="917ea-119">First Child</span><span class="sxs-lookup"><span data-stu-id="917ea-119">First Child</span></span>  
  
-   <span data-ttu-id="917ea-120">Last Child</span><span class="sxs-lookup"><span data-stu-id="917ea-120">Last Child</span></span>  
  
-   <span data-ttu-id="917ea-121">Last Nonempty Child</span><span class="sxs-lookup"><span data-stu-id="917ea-121">Last Nonempty Child</span></span>  
  
-   <span data-ttu-id="917ea-122">First Nonempty Child</span><span class="sxs-lookup"><span data-stu-id="917ea-122">First Nonempty Child</span></span>  
  
-   <span data-ttu-id="917ea-123">None</span><span class="sxs-lookup"><span data-stu-id="917ea-123">None</span></span>  
  
 <span data-ttu-id="917ea-124">Esta opción no cambia las medidas con una función de agregación normal: `Sum` , `Min` , `Max` , `Count` o `Distinct``Count` .</span><span class="sxs-lookup"><span data-stu-id="917ea-124">This option does not change measures with a regular aggregation function: `Sum`, `Min`, `Max`, `Count`, or `Distinct``Count`.</span></span>  
  
 <span data-ttu-id="917ea-125">**El asistente ha detectado la dimensión de cuenta "cuenta", que contiene miembros de suma parcial. El servidor agregará los miembros de esta dimensión de acuerdo con el comportamiento de suma parcial especificado para cada tipo de cuenta.**</span><span class="sxs-lookup"><span data-stu-id="917ea-125">**The wizard has detected the 'Account" account dimension, which contains semiadditive members. The server will aggregate members of this dimension according to the semiadditive behavior specified for each account type.**</span></span>  
 <span data-ttu-id="917ea-126">Hace que el sistema establezca todas las medidas de un grupo de medida con una dimensión de tipo Cuenta en la función de agregación By Account; el servidor agregará los miembros de dimensión según el comportamiento de suma parcial especificado para cada tipo de cuenta.</span><span class="sxs-lookup"><span data-stu-id="917ea-126">Causes the system to set all measures from a measure group dimensioned by an Account type dimension to the By Account aggregation function and the server will aggregate members of the dimension according to the semiadditive behavior specified for each account type.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="917ea-127">Esta opción se selecciona como opción predeterminada si el asistente detecta una dimensión de tipo Cuenta.</span><span class="sxs-lookup"><span data-stu-id="917ea-127">This option is selected by default if the wizard detects an Account type dimension.</span></span>  
  
 <span data-ttu-id="917ea-128">**Definir el comportamiento de suma parcial para medidas individuales**</span><span class="sxs-lookup"><span data-stu-id="917ea-128">**Define semiadditive behavior for individual measures**</span></span>  
 <span data-ttu-id="917ea-129">Selecciona el comportamiento de suma parcial de cada medida individualmente.</span><span class="sxs-lookup"><span data-stu-id="917ea-129">Selects the semiadditive behavior of each measure individually.</span></span> <span data-ttu-id="917ea-130">El valor predeterminado es `SUM` (suma total).</span><span class="sxs-lookup"><span data-stu-id="917ea-130">The default setting is `SUM` (fully additive).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="917ea-131">Esta opción se selecciona como opción predeterminada si el asistente no detecta una dimensión de tipo Cuenta.</span><span class="sxs-lookup"><span data-stu-id="917ea-131">This option is selected by default if the wizard does not detect an Account type dimension.</span></span>  
  
 <span data-ttu-id="917ea-132">Para cada medida, puede seleccionar entre los tipos de funcionalidad de suma parcial que se describen en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="917ea-132">For each measure, you can select from the types of semiadditive functionality described in the following table.</span></span>  
  
|<span data-ttu-id="917ea-133">Función de suma parcial</span><span class="sxs-lookup"><span data-stu-id="917ea-133">Semiadditive function</span></span>|<span data-ttu-id="917ea-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="917ea-134">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="917ea-135">Average of Children</span><span class="sxs-lookup"><span data-stu-id="917ea-135">Average of Children</span></span>|<span data-ttu-id="917ea-136">La agregación de un miembro es el promedio de sus elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="917ea-136">The aggregation of a member is the average of its children.</span></span>|  
|<span data-ttu-id="917ea-137">ByAccount</span><span class="sxs-lookup"><span data-stu-id="917ea-137">ByAccount</span></span>|<span data-ttu-id="917ea-138">El sistema lee el comportamiento de suma parcial especificado para cada tipo de cuenta.</span><span class="sxs-lookup"><span data-stu-id="917ea-138">The system reads the semiadditive behavior specified for the account type.</span></span>|  
|<span data-ttu-id="917ea-139">Count</span><span class="sxs-lookup"><span data-stu-id="917ea-139">Count</span></span>|<span data-ttu-id="917ea-140">La agregación es un recuento de miembros.</span><span class="sxs-lookup"><span data-stu-id="917ea-140">The aggregation is a count of members.</span></span>|  
|<span data-ttu-id="917ea-141">Distinct Count</span><span class="sxs-lookup"><span data-stu-id="917ea-141">Distinct Count</span></span>|<span data-ttu-id="917ea-142">La agregación es un recuento de miembros únicos.</span><span class="sxs-lookup"><span data-stu-id="917ea-142">The aggregation is a count of unique members.</span></span>|  
|<span data-ttu-id="917ea-143">First Child</span><span class="sxs-lookup"><span data-stu-id="917ea-143">First Child</span></span>|<span data-ttu-id="917ea-144">El valor de miembro se evalúa como el valor de su primer elemento secundario a lo largo de la dimensión de tiempo.</span><span class="sxs-lookup"><span data-stu-id="917ea-144">The member value is evaluated as the value of its first child along the time dimension.</span></span>|  
|<span data-ttu-id="917ea-145">FirstNonEmpty</span><span class="sxs-lookup"><span data-stu-id="917ea-145">FirstNonEmpty</span></span>|<span data-ttu-id="917ea-146">El valor de miembro se evalúa como el valor de su primer elemento secundario a lo largo de la dimensión de tiempo que contiene datos.</span><span class="sxs-lookup"><span data-stu-id="917ea-146">The member value is evaluated as the value of its first child along the time dimension that contains data.</span></span>|  
|<span data-ttu-id="917ea-147">LastChild</span><span class="sxs-lookup"><span data-stu-id="917ea-147">LastChild</span></span>|<span data-ttu-id="917ea-148">El valor de miembro se evalúa como el valor de su último elemento secundario a lo largo de la dimensión de tiempo.</span><span class="sxs-lookup"><span data-stu-id="917ea-148">The member value is evaluated as the value of its last child along the time dimension.</span></span>|  
|<span data-ttu-id="917ea-149">LastNonEmpty</span><span class="sxs-lookup"><span data-stu-id="917ea-149">LastNonEmpty</span></span>|<span data-ttu-id="917ea-150">El valor de miembro se evalúa como el valor de su último elemento secundario a lo largo de la dimensión de tiempo que contiene datos.</span><span class="sxs-lookup"><span data-stu-id="917ea-150">The member value is evaluated as the value of its last child along the time dimension that contains data.</span></span>|  
|<span data-ttu-id="917ea-151">Max</span><span class="sxs-lookup"><span data-stu-id="917ea-151">Max</span></span>|<span data-ttu-id="917ea-152">Se aplica la función de agregación máxima estándar.</span><span class="sxs-lookup"><span data-stu-id="917ea-152">The standard maximum aggregation function is applied.</span></span>|  
|<span data-ttu-id="917ea-153">Min</span><span class="sxs-lookup"><span data-stu-id="917ea-153">Min</span></span>|<span data-ttu-id="917ea-154">Se aplica la función de agregación mínima estándar.</span><span class="sxs-lookup"><span data-stu-id="917ea-154">The standard minimum aggregation function is applied.</span></span>|  
|<span data-ttu-id="917ea-155">None</span><span class="sxs-lookup"><span data-stu-id="917ea-155">None</span></span>|<span data-ttu-id="917ea-156">No se aplican agregaciones.</span><span class="sxs-lookup"><span data-stu-id="917ea-156">No aggregation is applied.</span></span>|  
|<span data-ttu-id="917ea-157">Sum</span><span class="sxs-lookup"><span data-stu-id="917ea-157">Sum</span></span>|<span data-ttu-id="917ea-158">Se aplica la función de suma estándar.</span><span class="sxs-lookup"><span data-stu-id="917ea-158">The standard summation function is applied.</span></span>|  
  
 <span data-ttu-id="917ea-159">Cualquier comportamiento de suma parcial existente se sobrescribe cuando se completa el asistente.</span><span class="sxs-lookup"><span data-stu-id="917ea-159">Any existing semiadditive behavior is overwritten when you complete the wizard.</span></span>  
  
  
