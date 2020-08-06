---
title: Elemento Issue (ssbdiagnose) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- issue element
- XML output file format [ssbdiagnose], issue element
- ssbdiagnose
ms.assetid: 2246a886-686b-44ca-9771-b155cedad8be
author: stevestein
ms.author: sstein
ms.openlocfilehash: a178c1323c1c20f84e67d4d7699fc313090a4c71
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743723"
---
# <a name="issue-element-ssbdiagnose"></a><span data-ttu-id="bde27-102">Elemento Issue (ssbdiagnose)</span><span class="sxs-lookup"><span data-stu-id="bde27-102">Issue Element (ssbdiagnose)</span></span>
  <span data-ttu-id="bde27-103">Informa de un problema encontrado por la utilidad **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="bde27-103">Reports an issue that was found by the **ssbdiagnose** utility.</span></span> <span data-ttu-id="bde27-104">El archivo de salida XML de **ssbdiagnose** tiene un elemento Issue por cada problema notificado.</span><span class="sxs-lookup"><span data-stu-id="bde27-104">The **ssbdiagnose** XML output file has one Issue element per issue reported.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bde27-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bde27-105">Syntax</span></span>  
  
```  
  
<Issue  
    type="..."   
    code="..."   
    server="..."   
    database="..."   
    object="...">   
    ...   
</Issue>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="bde27-106">Atributos del elemento</span><span class="sxs-lookup"><span data-stu-id="bde27-106">Element Attributes</span></span>  
  
|<span data-ttu-id="bde27-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="bde27-107">Attribute</span></span>|<span data-ttu-id="bde27-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="bde27-108">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="bde27-109">Identifica la categoría del problema sobre el que informa el elemento Issue.</span><span class="sxs-lookup"><span data-stu-id="bde27-109">Identifies which category of problem the Issue element is reporting:</span></span><br /><br /> <span data-ttu-id="bde27-110">**"Diagnóstico"** Informa de un problema de configuración encontrado al analizar una configuración de [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bde27-110">**"Diagnosis"** Reports a configuration issue found when you analyze a [!INCLUDE[ssSB](../../includes/sssb-md.md)] configuration.</span></span><br /><br /> <span data-ttu-id="bde27-111">**"Problema"** Informa de un problema que ha impedido que **ssbdiagnose** complete el análisis.</span><span class="sxs-lookup"><span data-stu-id="bde27-111">**"Problem"** Reports an issue that has prevented **ssbdiagnose** from completing its analysis.</span></span> <span data-ttu-id="bde27-112">Corrija el problema y vuelva a ejecutar **ssbdiagnose**.</span><span class="sxs-lookup"><span data-stu-id="bde27-112">Correct the problem and rerun **ssbdiagnose**.</span></span><br /><br /> <span data-ttu-id="bde27-113">**"Evento"** Informa de un evento de [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] encontrado al ejecutar una comprobación de **-RUNTIME** .</span><span class="sxs-lookup"><span data-stu-id="bde27-113">**"Event"** Reports a [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] event found when you run a **-RUNTIME** check.</span></span> <span data-ttu-id="bde27-114">Solo se informa de los eventos si se especifica **-SHOWEVENTS** .</span><span class="sxs-lookup"><span data-stu-id="bde27-114">Events are only reported if **-SHOWEVENTS** is specified.</span></span>|  
|`code`|<span data-ttu-id="bde27-115">Identifica el número de error del mensaje.</span><span class="sxs-lookup"><span data-stu-id="bde27-115">Identifies the error number for the message.</span></span>|  
|`server`|<span data-ttu-id="bde27-116">Identifica la instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)] en la que se encontró el problema.</span><span class="sxs-lookup"><span data-stu-id="bde27-116">Identifies the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] in which the problem was found.</span></span> <span data-ttu-id="bde27-117">Si el problema estaba en una instancia predeterminada, el atributo "server" solo tiene el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="bde27-117">If the problem was in a default instance, the server attribute only has the computer name.</span></span> <span data-ttu-id="bde27-118">Si el problema estaba en una instancia con nombre, el atributo "server" tiene el formato nombreDeEquipo\nombreDeInstancia.</span><span class="sxs-lookup"><span data-stu-id="bde27-118">If the problem was in a named instance, the server attribute is in the form ComputerName\InstanceName.</span></span>|  
|`database`|<span data-ttu-id="bde27-119">Identifica el nombre de la base de datos en la que se encontró el problema.</span><span class="sxs-lookup"><span data-stu-id="bde27-119">Identifies the name of the database in which the problem was found.</span></span>|  
|`object`|<span data-ttu-id="bde27-120">Identifica el nombre del objeto en el que se encontró el problema.</span><span class="sxs-lookup"><span data-stu-id="bde27-120">Identifies the name of the object in which the problem was found.</span></span> <span data-ttu-id="bde27-121">Si el problema era un problema de nivel de instancia o de base de datos, el atributo "object" repite el nombre de la instancia o de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="bde27-121">If the problem was an instance or database level issue, the object attribute repeats the instance or database name.</span></span>|  
  
## <a name="element-characteristics"></a><span data-ttu-id="bde27-122">Características de los elementos</span><span class="sxs-lookup"><span data-stu-id="bde27-122">Element Characteristics</span></span>  
  
|<span data-ttu-id="bde27-123">Característica</span><span class="sxs-lookup"><span data-stu-id="bde27-123">Characteristic</span></span>|<span data-ttu-id="bde27-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="bde27-124">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="bde27-125">**Tipo y longitud de los datos**</span><span class="sxs-lookup"><span data-stu-id="bde27-125">**Data type and length**</span></span>|<span data-ttu-id="bde27-126">`string`, la longitud es ilimitada.</span><span class="sxs-lookup"><span data-stu-id="bde27-126">`string`, length is unlimited.</span></span>|  
|<span data-ttu-id="bde27-127">**Valor**</span><span class="sxs-lookup"><span data-stu-id="bde27-127">**Value**</span></span>|<span data-ttu-id="bde27-128">Devuelve el texto del mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="bde27-128">Returns the text of the error message.</span></span>|  
|<span data-ttu-id="bde27-129">**Repetición**</span><span class="sxs-lookup"><span data-stu-id="bde27-129">**Occurrence**</span></span>|<span data-ttu-id="bde27-130">Una vez por error notificado.</span><span class="sxs-lookup"><span data-stu-id="bde27-130">Once per reported error.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="bde27-131">Relaciones del elemento</span><span class="sxs-lookup"><span data-stu-id="bde27-131">Element Relationships</span></span>  
  
|<span data-ttu-id="bde27-132">Relación</span><span class="sxs-lookup"><span data-stu-id="bde27-132">Relationship</span></span>|<span data-ttu-id="bde27-133">Elementos</span><span class="sxs-lookup"><span data-stu-id="bde27-133">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="bde27-134">**Elemento primario**</span><span class="sxs-lookup"><span data-stu-id="bde27-134">**Parent element**</span></span>|[<span data-ttu-id="bde27-135">Elemento DiagnosticInformation &#40;ssbdiagnose&#41;</span><span class="sxs-lookup"><span data-stu-id="bde27-135">DiagnosticInformation Element &#40;ssbdiagnose&#41;</span></span>](diagnosticinformation-element-ssbdiagnose.md)|  
|<span data-ttu-id="bde27-136">**Elementos secundarios**</span><span class="sxs-lookup"><span data-stu-id="bde27-136">**Child elements**</span></span>|<span data-ttu-id="bde27-137">None</span><span class="sxs-lookup"><span data-stu-id="bde27-137">None</span></span>|  
  
## <a name="example"></a><span data-ttu-id="bde27-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bde27-138">Example</span></span>  
 <span data-ttu-id="bde27-139">Este elemento informa de un error 1102 para una base de datos que no tiene una clave maestra, en la que se encontró el error al analizar una configuración de [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bde27-139">This element reports an 1102 error for a database that does not have a master key, where the error was found when you analyzed a [!INCLUDE[ssSB](../../includes/sssb-md.md)] configuration.</span></span>  
  
```  
<Issue type="Diagnosis" code="1102" server="TestComputer" database="TargetDB" object="TargetDB">The master key was not found</diagnostic>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bde27-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bde27-140">See Also</span></span>  
 [<span data-ttu-id="bde27-141">Utilidad ssbdiagnose &#40;Service Broker&#41;</span><span class="sxs-lookup"><span data-stu-id="bde27-141">ssbdiagnose Utility &#40;Service Broker&#41;</span></span>](ssbdiagnose-utility-service-broker.md)  
  
  
