---
title: File (DTA, elemento) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- File element
ms.assetid: 73dce835-9a80-4aef-8e0f-9dcf07dd5b80
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0eeb2bdcc9513ca6283447daca63c8bbc4fa1726
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747833"
---
# <a name="file-element-dta"></a><span data-ttu-id="c8eab-102">File (DTA, elemento)</span><span class="sxs-lookup"><span data-stu-id="c8eab-102">File Element (DTA)</span></span>
  <span data-ttu-id="c8eab-103">Especifica el archivo de carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c8eab-103">Specifies the workload file.</span></span> <span data-ttu-id="c8eab-104">Una carga de trabajo es un conjunto de instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] que se ejecuta en una o varias bases de datos que se desean optimizar.</span><span class="sxs-lookup"><span data-stu-id="c8eab-104">A workload is a set of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that execute against a database or databases that you want to tune.</span></span> <span data-ttu-id="c8eab-105">Los archivos de carga de trabajo pueden ser scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] (.sql) o archivos de seguimiento (.trc).</span><span class="sxs-lookup"><span data-stu-id="c8eab-105">Workload files can be [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts (.sql) or trace files (.trc).</span></span> <span data-ttu-id="c8eab-106">Para más información, consulte [Iniciar y utilizar el Asistente para la optimización de motor de base de datos](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md).</span><span class="sxs-lookup"><span data-stu-id="c8eab-106">For more information, see [Start and Use the Database Engine Tuning Advisor](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8eab-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c8eab-107">Syntax</span></span>  
  
```  
  
<DTAInput>  
  <Server>...</Server>  
  <Workload>  
    <File>...</File>  
  </Workload>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="c8eab-108">Características de los elementos</span><span class="sxs-lookup"><span data-stu-id="c8eab-108">Element Characteristics</span></span>  
  
|<span data-ttu-id="c8eab-109">Característica</span><span class="sxs-lookup"><span data-stu-id="c8eab-109">Characteristic</span></span>|<span data-ttu-id="c8eab-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="c8eab-110">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="c8eab-111">**Tipo y longitud de los datos**</span><span class="sxs-lookup"><span data-stu-id="c8eab-111">**Data type and length**</span></span>|<span data-ttu-id="c8eab-112">Utilice el tipo de datos `string` para especificar la ruta de acceso del directorio al archivo de carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c8eab-112">Use the `string` data type to specify the directory path to your workload file.</span></span> <span data-ttu-id="c8eab-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c8eab-113">For example:</span></span><br /><br /> `<File>C:\Tuning\tun.sql</File>`<br /><br /> <span data-ttu-id="c8eab-114">El servidor aplica el límite de longitud.</span><span class="sxs-lookup"><span data-stu-id="c8eab-114">Length limit is enforced by the server.</span></span>|  
|<span data-ttu-id="c8eab-115">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="c8eab-115">**Default value**</span></span>|<span data-ttu-id="c8eab-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c8eab-116">None.</span></span>|  
|<span data-ttu-id="c8eab-117">**Repetición**</span><span class="sxs-lookup"><span data-stu-id="c8eab-117">**Occurrence**</span></span>|<span data-ttu-id="c8eab-118">Una obligatoria si no se especifica ningún otro tipo de carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c8eab-118">Required once if no other type of workload is specified.</span></span> <span data-ttu-id="c8eab-119">Es necesario especificar un elemento secundario **EventString**, **File**o **Database** para el elemento primario **Workload** , aunque solo se puede utilizar un tipo.</span><span class="sxs-lookup"><span data-stu-id="c8eab-119">You must specify an **EventString**, a **File**, or a **Database** child element for the **Workload** parent, but only one type can be used.</span></span> <span data-ttu-id="c8eab-120">Por ejemplo, si se especifica una carga de trabajo con el elemento **File** , no se puede especificar una carga de trabajo con el elemento **Database** en el mismo archivo de entrada XML.</span><span class="sxs-lookup"><span data-stu-id="c8eab-120">For example, if you specify a workload with the **File** element, then you cannot also specify a workload with the **Database** element in the same XML input file.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="c8eab-121">Relaciones del elemento</span><span class="sxs-lookup"><span data-stu-id="c8eab-121">Element Relationships</span></span>  
  
|<span data-ttu-id="c8eab-122">Relación</span><span class="sxs-lookup"><span data-stu-id="c8eab-122">Relationship</span></span>|<span data-ttu-id="c8eab-123">Elementos</span><span class="sxs-lookup"><span data-stu-id="c8eab-123">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="c8eab-124">**Elemento primario**</span><span class="sxs-lookup"><span data-stu-id="c8eab-124">**Parent element**</span></span>|[<span data-ttu-id="c8eab-125">Workload &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="c8eab-125">Workload Element &#40;DTA&#41;</span></span>](workload-element-dta.md)|  
|<span data-ttu-id="c8eab-126">**Elementos secundarios**</span><span class="sxs-lookup"><span data-stu-id="c8eab-126">**Child elements**</span></span>|<span data-ttu-id="c8eab-127">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c8eab-127">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c8eab-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c8eab-128">Example</span></span>  
 <span data-ttu-id="c8eab-129">Para obtener un ejemplo de uso de este elemento, vea [Ejemplo de archivo de entrada XML simple &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span><span class="sxs-lookup"><span data-stu-id="c8eab-129">For a usage example of this element, see [Simple XML Input File Sample &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8eab-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c8eab-130">See Also</span></span>  
 [<span data-ttu-id="c8eab-131">Referencia del archivo de entrada XML &#40;Asistente para la optimización de motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="c8eab-131">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
