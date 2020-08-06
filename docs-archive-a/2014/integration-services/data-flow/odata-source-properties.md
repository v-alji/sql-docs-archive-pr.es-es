---
title: Propiedades de orígenes OData | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 4fde5bb0-6d78-4ec4-8f0b-67f91c53fe99
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8139f79ed595ca3e6204f96823f6bc95e6fb40df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750038"
---
# <a name="odata-source-properties"></a><span data-ttu-id="a9303-102">Propiedades de orígenes OData</span><span class="sxs-lookup"><span data-stu-id="a9303-102">OData Source Properties</span></span>
  <span data-ttu-id="a9303-103">Al hacer clic con el botón derecho en **Origen OData** en el flujo de datos y hacer clic en **Propiedades**, verá las propiedades del componente de **Origen OData** en la ventana **Propiedades** .</span><span class="sxs-lookup"><span data-stu-id="a9303-103">When you right-click **OData Source** in the data flow and click **Properties**, you will see properties for the **OData Source** component in the **Properties** window.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a9303-104">Propiedad</span><span class="sxs-lookup"><span data-stu-id="a9303-104">Property</span></span>|<span data-ttu-id="a9303-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="a9303-105">Description</span></span>|  
|<span data-ttu-id="a9303-106">CollectionName</span><span class="sxs-lookup"><span data-stu-id="a9303-106">CollectionName</span></span>|<span data-ttu-id="a9303-107">Nombre de la colección que desea recuperar del servicio OData.</span><span class="sxs-lookup"><span data-stu-id="a9303-107">Name of the collection you wish to retrieve from the OData service.</span></span> <span data-ttu-id="a9303-108">La propiedad **CollectionName** se usa cuando **UseResourcePath** es False.</span><span class="sxs-lookup"><span data-stu-id="a9303-108">The **CollectionName** property is used when **UseResourcePath** is False.</span></span><br /><br /> <span data-ttu-id="a9303-109">Esta propiedad se puede incluir en expresiones, lo que permite establecer el valor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a9303-109">This property is expression-able, allowing the value to be set at runtime.</span></span> <span data-ttu-id="a9303-110">Sin embargo, si los metadatos de la colección no coinciden con los metadatos que se usaron en tiempo de diseño, se producirá un error de validación, lo que producirá un error en la ejecución del flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="a9303-110">However, if the metadata of the collection does not match the metadata that was used at design time, a validation error will occur, causing the data flow execution to fail.</span></span>|  
|<span data-ttu-id="a9303-111">DefaultStringLength</span><span class="sxs-lookup"><span data-stu-id="a9303-111">DefaultStringLength</span></span>|<span data-ttu-id="a9303-112">Este valor especifica la longitud predeterminada de las columnas de cadena que no tienen ninguna longitud máxima.</span><span class="sxs-lookup"><span data-stu-id="a9303-112">This value specifies default length for string columns that have no max length.</span></span><br /><br /> <span data-ttu-id="a9303-113">**Valor predeterminado:** 4000</span><span class="sxs-lookup"><span data-stu-id="a9303-113">**Default:** 4000</span></span>|  
|<span data-ttu-id="a9303-114">Consultar</span><span class="sxs-lookup"><span data-stu-id="a9303-114">Query</span></span>|<span data-ttu-id="a9303-115">Parámetros de consulta OData.</span><span class="sxs-lookup"><span data-stu-id="a9303-115">The OData query parameters.</span></span> <span data-ttu-id="a9303-116">Esta propiedad se puede incluir en expresiones y establecer en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a9303-116">This property is expression-able and can be set at runtime.</span></span>|  
|<span data-ttu-id="a9303-117">ResourcePath</span><span class="sxs-lookup"><span data-stu-id="a9303-117">ResourcePath</span></span>|<span data-ttu-id="a9303-118">Use esta propiedad cuando necesite especificar una ruta de acceso completa a recursos, en lugar de seleccionar simplemente el nombre de una colección.</span><span class="sxs-lookup"><span data-stu-id="a9303-118">Use this property when you need to specify a full resource path, rather than just selecting a collection name.</span></span> <span data-ttu-id="a9303-119">Esta propiedad se usa cuando **UseResourcePath** es True.</span><span class="sxs-lookup"><span data-stu-id="a9303-119">This property is used when **UseResourcePath** is True.</span></span>|  
|<span data-ttu-id="a9303-120">UseResourcePath</span><span class="sxs-lookup"><span data-stu-id="a9303-120">UseResourcePath</span></span>|<span data-ttu-id="a9303-121">Cuando se establece en True, el valor **ResourcePath** se anexa a la dirección URL base para determinar la ubicación de la fuente OData.</span><span class="sxs-lookup"><span data-stu-id="a9303-121">When set to True, the **ResourcePath** value is appended to the base URL to determine the OData feed location.</span></span> <span data-ttu-id="a9303-122">Cuando se establece en False, se usa el valor **CollectionName** .</span><span class="sxs-lookup"><span data-stu-id="a9303-122">When set to False, the **CollectionName** value is used.</span></span><br /><br /> <span data-ttu-id="a9303-123">**Valor predeterminado:** Es</span><span class="sxs-lookup"><span data-stu-id="a9303-123">**Default:** False</span></span>|  
  
  
