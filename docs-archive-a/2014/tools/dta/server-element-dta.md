---
title: Server (DTA, elemento) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Server element
ms.assetid: 9fe0bfb4-3aa6-4eb2-a83e-c0d0e7d4e9f6
author: stevestein
ms.author: sstein
ms.openlocfilehash: ab67e0303c2b629c3774886441474f5ef5b10a43
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675088"
---
# <a name="server-element-dta"></a><span data-ttu-id="cf63c-102">Server (DTA, elemento)</span><span class="sxs-lookup"><span data-stu-id="cf63c-102">Server Element (DTA)</span></span>
  <span data-ttu-id="cf63c-103">Contiene la información de identificación del servidor en el que residen las bases de datos que se desean optimizar.</span><span class="sxs-lookup"><span data-stu-id="cf63c-103">Contains the identifying information for the server on which the databases reside that you want to tune.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf63c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cf63c-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
    <Server>  
    ...code removed here...  
    </Server>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="cf63c-105">Características de los elementos</span><span class="sxs-lookup"><span data-stu-id="cf63c-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="cf63c-106">Característica</span><span class="sxs-lookup"><span data-stu-id="cf63c-106">Characteristic</span></span>|<span data-ttu-id="cf63c-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="cf63c-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="cf63c-108">**Tipo y longitud de los datos**</span><span class="sxs-lookup"><span data-stu-id="cf63c-108">**Data type and length**</span></span>|<span data-ttu-id="cf63c-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="cf63c-109">None.</span></span>|  
|<span data-ttu-id="cf63c-110">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="cf63c-110">**Default value**</span></span>|<span data-ttu-id="cf63c-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="cf63c-111">None.</span></span>|  
|<span data-ttu-id="cf63c-112">**Repetición**</span><span class="sxs-lookup"><span data-stu-id="cf63c-112">**Occurrence**</span></span>|<span data-ttu-id="cf63c-113">Se requiere una vez por elemento `DTAInput`.</span><span class="sxs-lookup"><span data-stu-id="cf63c-113">Required once per `DTAInput` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="cf63c-114">Relaciones del elemento</span><span class="sxs-lookup"><span data-stu-id="cf63c-114">Element Relationships</span></span>  
  
|<span data-ttu-id="cf63c-115">Relación</span><span class="sxs-lookup"><span data-stu-id="cf63c-115">Relationship</span></span>|<span data-ttu-id="cf63c-116">Elementos</span><span class="sxs-lookup"><span data-stu-id="cf63c-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="cf63c-117">**Elemento primario**</span><span class="sxs-lookup"><span data-stu-id="cf63c-117">**Parent element**</span></span>|[<span data-ttu-id="cf63c-118">Elemento DTAInput &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="cf63c-118">DTAInput Element &#40;DTA&#41;</span></span>](dtainput-element-dta.md)|  
|<span data-ttu-id="cf63c-119">**Elementos secundarios**</span><span class="sxs-lookup"><span data-stu-id="cf63c-119">**Child elements**</span></span>|[<span data-ttu-id="cf63c-120">Name &#40;DTA, elemento de Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cf63c-120">Name Element for Server &#40;DTA&#41;</span></span>](name-element-for-server-dta.md)<br /><br /> [<span data-ttu-id="cf63c-121">Elemento Database para servidor &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="cf63c-121">Database Element for Server &#40;DTA&#41;</span></span>](database-element-for-server-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="cf63c-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cf63c-122">Remarks</span></span>  
 <span data-ttu-id="cf63c-123">Solo puede especificar un `Server` elemento para el `DTAInput` elemento.</span><span class="sxs-lookup"><span data-stu-id="cf63c-123">You can specify only one `Server` element for the `DTAInput` element.</span></span> <span data-ttu-id="cf63c-124">Este elemento tiene el nombre **ServerDetailsTypecomplexType** en el esquema XML DTA.</span><span class="sxs-lookup"><span data-stu-id="cf63c-124">This element is of the **ServerDetailsTypecomplexType** name in the DTA XML schema.</span></span> <span data-ttu-id="cf63c-125">No confunda este elemento `Server` con el elemento secundario de `Configuration`.</span><span class="sxs-lookup"><span data-stu-id="cf63c-125">Do not confuse this `Server` element with the one that is the child of the `Configuration` element.</span></span> <span data-ttu-id="cf63c-126">Para obtener más información, vea [Server &#40;DTA, elemento de Configuration&#41;](server-element-for-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="cf63c-126">For more information, see [Server Element for Configuration &#40;DTA&#41;](server-element-for-configuration-dta.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf63c-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cf63c-127">Example</span></span>  
 <span data-ttu-id="cf63c-128">El ejemplo siguiente muestra cómo especificar la tabla **Sales.SalesPerson** en la base de datos de **AdventureWorks** en SERVER001:</span><span class="sxs-lookup"><span data-stu-id="cf63c-128">The following example shows how to specify the **Sales.SalesPerson** table in the **AdventureWorks** database on SERVER001:</span></span>  
  
```xml  
<Server>  
  <Name>SERVER001</Name>  
  <Database>  
    <Name>AdventureWorks</Name>  
    <Schema>  
      <Name>Sales</Name>  
      <Table>  
        <Name>SalesPerson</Name>  
      </Table>  
    </Schema>  
  </Database>  
</Server  
```  
  
## <a name="see-also"></a><span data-ttu-id="cf63c-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cf63c-129">See Also</span></span>  
 [<span data-ttu-id="cf63c-130">Referencia del archivo de entrada XML &#40;Asistente para la optimización de motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="cf63c-130">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
