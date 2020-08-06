---
title: Workload (DTA, elemento) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Workload element
ms.assetid: 68ffd473-6546-4015-98d0-3763165de65c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 20184760c3fcb5eed6c02b8f8fd9b63f5586c9af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671879"
---
# <a name="workload-element-dta"></a><span data-ttu-id="554c9-102">Workload (DTA, elemento)</span><span class="sxs-lookup"><span data-stu-id="554c9-102">Workload Element (DTA)</span></span>
  <span data-ttu-id="554c9-103">Especifica la carga de trabajo que se va a utilizar durante una sesión de optimización.</span><span class="sxs-lookup"><span data-stu-id="554c9-103">Specifies the workload to be used for a tuning session.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="554c9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="554c9-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
    <Server>  
...code removed...  
    <Workload>...</Workload>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="554c9-105">Características de los elementos</span><span class="sxs-lookup"><span data-stu-id="554c9-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="554c9-106">Característica</span><span class="sxs-lookup"><span data-stu-id="554c9-106">Characteristic</span></span>|<span data-ttu-id="554c9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="554c9-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="554c9-108">**Tipo y longitud de los datos**</span><span class="sxs-lookup"><span data-stu-id="554c9-108">**Data type and length**</span></span>|<span data-ttu-id="554c9-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="554c9-109">None.</span></span>|  
|<span data-ttu-id="554c9-110">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="554c9-110">**Default value**</span></span>|<span data-ttu-id="554c9-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="554c9-111">None.</span></span>|  
|<span data-ttu-id="554c9-112">**Repetición**</span><span class="sxs-lookup"><span data-stu-id="554c9-112">**Occurrence**</span></span>|<span data-ttu-id="554c9-113">Una obligatoria por cada elemento `DTAInput`.</span><span class="sxs-lookup"><span data-stu-id="554c9-113">Required once for each `DTAInput` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="554c9-114">Relaciones del elemento</span><span class="sxs-lookup"><span data-stu-id="554c9-114">Element Relationships</span></span>  
  
|<span data-ttu-id="554c9-115">Relación</span><span class="sxs-lookup"><span data-stu-id="554c9-115">Relationship</span></span>|<span data-ttu-id="554c9-116">Elementos</span><span class="sxs-lookup"><span data-stu-id="554c9-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="554c9-117">**Elemento primario**</span><span class="sxs-lookup"><span data-stu-id="554c9-117">**Parent element**</span></span>|[<span data-ttu-id="554c9-118">Iniciar y utilizar el Asistente para la optimización de motor de base de datos</span><span class="sxs-lookup"><span data-stu-id="554c9-118">Start and Use the Database Engine Tuning Advisor</span></span>](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md)|  
|<span data-ttu-id="554c9-119">**Elementos secundarios**</span><span class="sxs-lookup"><span data-stu-id="554c9-119">**Child elements**</span></span>|[<span data-ttu-id="554c9-120">File &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="554c9-120">File Element &#40;DTA&#41;</span></span>](file-element-dta.md)<br /><br /> [<span data-ttu-id="554c9-121">Database &#40;DTA, elemento de Workload&#41;</span><span class="sxs-lookup"><span data-stu-id="554c9-121">Database Element for Workload &#40;DTA&#41;</span></span>](database-element-for-workload-dta.md)<br /><br /> [<span data-ttu-id="554c9-122">EventString &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="554c9-122">EventString Element &#40;DTA&#41;</span></span>](eventstring-element-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="554c9-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="554c9-123">Remarks</span></span>  
 <span data-ttu-id="554c9-124">Una carga de trabajo es un conjunto de instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] que se ejecuta en una o varias bases de datos que se desean optimizar.</span><span class="sxs-lookup"><span data-stu-id="554c9-124">A workload is a set of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that execute against a database or databases that you want to tune.</span></span> <span data-ttu-id="554c9-125">El Asistente para la optimización de motor de base de datos puede utilizar scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] , archivos de seguimiento y tablas de seguimiento como cargas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="554c9-125">The Database Engine Tuning Advisor can use [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts, trace files, and trace tables as workloads.</span></span>  
  
 <span data-ttu-id="554c9-126">Si se especifica una carga de trabajo en un archivo de entrada XML y una carga de trabajo en la línea de comandos mediante la herramienta **dta** , la carga de trabajo especificada en la línea de comandos se utilizará para la optimización.</span><span class="sxs-lookup"><span data-stu-id="554c9-126">If you specify a workload in an XML input file and a workload on the command line with the **dta** tool, the workload specified on the command line will be used for tuning.</span></span> <span data-ttu-id="554c9-127">Todas las opciones de optimización especificadas en la línea de comandos tienen preferencia sobre las especificadas en un archivo de entrada XML.</span><span class="sxs-lookup"><span data-stu-id="554c9-127">All tuning options specified on the command line override those that are specified in an XML input file.</span></span> <span data-ttu-id="554c9-128">La única excepción se produce cuando se usa una configuración especificada por el usuario en el modo de evaluación del archivo de entrada XML.</span><span class="sxs-lookup"><span data-stu-id="554c9-128">The only exception is if a user-specified configuration is entered in the evaluate mode in the XML input file.</span></span> <span data-ttu-id="554c9-129">Por ejemplo, si se especifica una configuración en el elemento `Configuration` del archivo de entrada XML y el elemento `EvaluateConfiguration` también se ha especificado como una de las opciones de optimización, las opciones de optimización especificadas en el archivo de entrada XML tendrán preferencia sobre aquellas especificadas en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="554c9-129">For example, if a configuration is entered in the `Configuration` element of the XML input file and the `EvaluateConfiguration` element is also specified as one of the tuning options, the tuning options specified in the XML input file will override any tuning options entered at the command line.</span></span>  
  
 <span data-ttu-id="554c9-130">Es necesario especificar una carga de trabajo para cada sesión de optimización.</span><span class="sxs-lookup"><span data-stu-id="554c9-130">One workload must be specified for each tuning session.</span></span>  
  
## <a name="example"></a><span data-ttu-id="554c9-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="554c9-131">Example</span></span>  
 <span data-ttu-id="554c9-132">En el ejemplo de código siguiente se especifica la tabla de seguimiento de My **Database. MyDBOwner. TuningTable001** para el `Workload` elemento.</span><span class="sxs-lookup"><span data-stu-id="554c9-132">The following code example specifies the **MyDatabase.MyDBOwner.TuningTable001** trace table for the `Workload` element.</span></span> <span data-ttu-id="554c9-133">**TuningTable001** se creó utilizando la plantilla Optimización con SQL Server Profiler y guardando el seguimiento generada como una tabla.</span><span class="sxs-lookup"><span data-stu-id="554c9-133">The **TuningTable001** was created by using the Tuning template with SQL Server Profiler and saving the trace output as a table.</span></span>  
  
```  
<DTAXML ...>  
  <DTAInput>  
    <Server>  
...code removed here...  
    </Server>  
    <Workload>  
      <Database>  
        <Name>MyDatabase</Name>  
        <Schema>  
          <Name>MyDBOwner</Name>  
            <Table>  
              <Name>TuningTable001</Name>  
            </Table>  
        </Schema>  
      </Database>  
    </Workload>  
...code removed here...  
  </DTAInput>  
</DTAXML>  
```  
  
## <a name="see-also"></a><span data-ttu-id="554c9-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="554c9-134">See Also</span></span>  
 [<span data-ttu-id="554c9-135">Referencia del archivo de entrada XML &#40;Asistente para la optimización de motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="554c9-135">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
