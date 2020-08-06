---
title: DTAXML (DTA, elemento) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- DTAXML element
ms.assetid: 3d9942ed-8a27-40db-a7c9-808984d914a2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9f428cf996bb819ece74c13226fcd5116a19142b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747359"
---
# <a name="dtaxml-element-dta"></a><span data-ttu-id="bafb6-102">DTAXML (DTA, elemento)</span><span class="sxs-lookup"><span data-stu-id="bafb6-102">DTAXML Element (DTA)</span></span>
  <span data-ttu-id="bafb6-103">El elemento raíz de un archivo de entrada o salida XML del Asistente para la optimización de motor de base de datos, **DTAXML** , contiene todos los elementos que describen la entrada y la salida de optimización que genera el Asistente para la optimización de motor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="bafb6-103">The root element of a Database Engine Tuning Advisor XML input or output file, **DTAXML** contains all elements that describe tuning input and the tuning output that Database Engine Tuning Advisor generates.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bafb6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bafb6-104">Syntax</span></span>  
  
```  
  
<DTAXML   
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"   
    xmlns="https://schemas.microsoft.com/sqlserver/2004/07/dta">  
    ...code removed here...  
</DTAXML>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="bafb6-105">Atributos del elemento</span><span class="sxs-lookup"><span data-stu-id="bafb6-105">Element Attributes</span></span>  
  
|<span data-ttu-id="bafb6-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="bafb6-106">Attribute</span></span>|<span data-ttu-id="bafb6-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="bafb6-107">Description</span></span>|  
|---------------|-----------------|  
|`xmlns:xsi`|<span data-ttu-id="bafb6-108">Necesario.</span><span class="sxs-lookup"><span data-stu-id="bafb6-108">Required.</span></span> <span data-ttu-id="bafb6-109">Identifica el espacio de nombres de la instancia del esquema XML.</span><span class="sxs-lookup"><span data-stu-id="bafb6-109">Identifies the XML Schema Instance namespace.</span></span> <span data-ttu-id="bafb6-110">Los atributos de este espacio de nombres se utilizan para hacer referencia al esquema usado para validar el archivo XML del Asistente para la optimización de motor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="bafb6-110">Attributes from this namespace are used to reference the schema that is used to validate the Database Engine Tuning Advisor XML file.</span></span><br /><br /> <span data-ttu-id="bafb6-111">Valor requerido: [http://www.w3.org/2001/XMLSchema-instance](http://www.w3.org/2001/XMLSchema-instance)</span><span class="sxs-lookup"><span data-stu-id="bafb6-111">Required value: [http://www.w3.org/2001/XMLSchema-instance](http://www.w3.org/2001/XMLSchema-instance)</span></span>|  
|`xmlns`|<span data-ttu-id="bafb6-112">Necesario.</span><span class="sxs-lookup"><span data-stu-id="bafb6-112">Required.</span></span> <span data-ttu-id="bafb6-113">Identifica el espacio de nombres del Asistente para la optimización de motor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="bafb6-113">Identifies the Database Engine Tuning Advisor namespace.</span></span><br /><br /> <span data-ttu-id="bafb6-114">Si se modifica el archivo XML del Asistente para la optimización de motor de base de datos mediante el editor XML de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], este valor es utilizado por F1 Ayuda y la Ayuda dinámica para encontrar posibles temas de referencia en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bafb6-114">If you edit the Database Engine Tuning Advisor XML file using the XML editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], this value is used by F1 Help and Dynamic Help to locate possible reference topics in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span><br /><br /> <span data-ttu-id="bafb6-115">Valor requerido:</span><span class="sxs-lookup"><span data-stu-id="bafb6-115">Required value:</span></span><br /><br /> <span data-ttu-id="bafb6-116">Espacio de nombres del[Esquema XML del Asistente para la optimización de motor de base de datos](https://go.microsoft.com/fwlink/?LinkId=43100)</span><span class="sxs-lookup"><span data-stu-id="bafb6-116">[Database Engine Tuning Advisor XML Schema](https://go.microsoft.com/fwlink/?LinkId=43100) Namespace</span></span>|  
  
## <a name="element-characteristics"></a><span data-ttu-id="bafb6-117">Características de los elementos</span><span class="sxs-lookup"><span data-stu-id="bafb6-117">Element Characteristics</span></span>  
  
|<span data-ttu-id="bafb6-118">Característica</span><span class="sxs-lookup"><span data-stu-id="bafb6-118">Characteristic</span></span>|<span data-ttu-id="bafb6-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="bafb6-119">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="bafb6-120">**Tipo y longitud de los datos**</span><span class="sxs-lookup"><span data-stu-id="bafb6-120">**Data type and length**</span></span>|<span data-ttu-id="bafb6-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="bafb6-121">None.</span></span>|  
|<span data-ttu-id="bafb6-122">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="bafb6-122">**Default value**</span></span>|<span data-ttu-id="bafb6-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="bafb6-123">None.</span></span>|  
|<span data-ttu-id="bafb6-124">**Repetición**</span><span class="sxs-lookup"><span data-stu-id="bafb6-124">**Occurrence**</span></span>|<span data-ttu-id="bafb6-125">Una obligatoria por archivo XML DTA</span><span class="sxs-lookup"><span data-stu-id="bafb6-125">Required once per DTA XML file.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="bafb6-126">Relaciones del elemento</span><span class="sxs-lookup"><span data-stu-id="bafb6-126">Element Relationships</span></span>  
  
|<span data-ttu-id="bafb6-127">Relación</span><span class="sxs-lookup"><span data-stu-id="bafb6-127">Relationship</span></span>|<span data-ttu-id="bafb6-128">Elementos</span><span class="sxs-lookup"><span data-stu-id="bafb6-128">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="bafb6-129">**Elemento primario**</span><span class="sxs-lookup"><span data-stu-id="bafb6-129">**Parent element**</span></span>|<span data-ttu-id="bafb6-130">None</span><span class="sxs-lookup"><span data-stu-id="bafb6-130">None</span></span>|  
|<span data-ttu-id="bafb6-131">**Elementos secundarios**</span><span class="sxs-lookup"><span data-stu-id="bafb6-131">**Child elements**</span></span>|[<span data-ttu-id="bafb6-132">Elemento DTAInput &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="bafb6-132">DTAInput Element &#40;DTA&#41;</span></span>](dtainput-element-dta.md)<br /><br /> <span data-ttu-id="bafb6-133">`DTAOutput`Elemento (vea [Asistente para la optimización de motor de base de datos esquema XML](https://schemas.microsoft.com/sqlserver/) para obtener información)</span><span class="sxs-lookup"><span data-stu-id="bafb6-133">`DTAOutput` Element (see [Database Engine Tuning Advisor XML schema](https://schemas.microsoft.com/sqlserver/) for information)</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bafb6-134">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bafb6-134">Remarks</span></span>  
 <span data-ttu-id="bafb6-135">Para obtener más información acerca de los espacios de nombres XML, vea el artículo sobre [espacios de nombres en un documento XML](https://go.microsoft.com/fwlink/?LinkId=7341) en [!INCLUDE[msCoName](../../includes/msconame-md.md)] MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="bafb6-135">For more information about XML namespaces, see [Namespaces in an XML Document](https://go.microsoft.com/fwlink/?LinkId=7341) in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] MSDN Library.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bafb6-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bafb6-136">Example</span></span>  
 <span data-ttu-id="bafb6-137">Para ver ejemplos de elementos **DTAXML** típicos, consulte [Ejemplos de archivos de entrada XML &#40;DTA&#41;](xml-input-file-samples-dta.md).</span><span class="sxs-lookup"><span data-stu-id="bafb6-137">For examples of typical **DTAXML** elements, see [XML Input File Samples &#40;DTA&#41;](xml-input-file-samples-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bafb6-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bafb6-138">See Also</span></span>  
 <span data-ttu-id="bafb6-139">[Referencia del archivo de entrada XML &#40;Asistente para la optimización de motor de base de datos&#41;](xml-input-file-reference-database-engine-tuning-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="bafb6-139">[XML Input File Reference &#40;Database Engine Tuning Advisor&#41;](xml-input-file-reference-database-engine-tuning-advisor.md) </span></span>  
 [<span data-ttu-id="bafb6-140">Iniciar y utilizar el Asistente para la optimización de motor de base de datos</span><span class="sxs-lookup"><span data-stu-id="bafb6-140">Start and Use the Database Engine Tuning Advisor</span></span>](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md)  
  
  
