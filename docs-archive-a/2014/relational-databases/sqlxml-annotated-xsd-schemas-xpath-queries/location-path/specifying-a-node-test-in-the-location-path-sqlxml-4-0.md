---
title: Especificar una prueba de nodo en la ruta de acceso de ubicación (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], location paths
- principal node types [SQLXML]
- node tests [SQLXML]
- location path for XPath query
ms.assetid: f46c30bf-1e24-4435-9ac2-f8ba43a8ff94
author: rothja
ms.author: jroth
ms.openlocfilehash: 9d8535154f4b481c8a47bfdb8b801e3136a1ef0f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673581"
---
# <a name="specifying-a-node-test-in-the-location-path-sqlxml-40"></a><span data-ttu-id="944d5-102">Especificar una prueba de nodo en la ruta de acceso de ubicación (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="944d5-102">Specifying a Node Test in the Location Path (SQLXML 4.0)</span></span>
  <span data-ttu-id="944d5-103">Una prueba de nodo especifica el tipo de nodo seleccionado por el paso de ubicación.</span><span class="sxs-lookup"><span data-stu-id="944d5-103">A node test specifies the node type selected by the location step.</span></span> <span data-ttu-id="944d5-104">Cada eje (`child`, `parent`, `attribute` o `self`) tiene un tipo de nodo principal.</span><span class="sxs-lookup"><span data-stu-id="944d5-104">Every axis (`child`, `parent`, `attribute`, or `self`) has a principal node type.</span></span> <span data-ttu-id="944d5-105">Para el `attribute` eje, el tipo de nodo principal es **\<attribute>** .</span><span class="sxs-lookup"><span data-stu-id="944d5-105">For the `attribute` axis, the principal node type is **\<attribute>**.</span></span> <span data-ttu-id="944d5-106">En el caso de los `parent` `child` ejes, y `self` , el tipo de nodo principal es **\<element>** .</span><span class="sxs-lookup"><span data-stu-id="944d5-106">For the `parent`, `child`, and `self` axes, the principal node type is **\<element>**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="944d5-107">La prueba de nodo de carácter comodín \* (por ejemplo, `child::*`) no se admite.</span><span class="sxs-lookup"><span data-stu-id="944d5-107">The wildcard node test \* (for example, `child::*`) is not supported.</span></span>  
  
## <a name="node-test-example-1"></a><span data-ttu-id="944d5-108">Prueba de nodo: ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="944d5-108">Node Test: Example 1</span></span>  
 <span data-ttu-id="944d5-109">La ruta de acceso `child::Customer` de ubicación selecciona elementos **\<Customer>** secundarios del nodo de contexto.</span><span class="sxs-lookup"><span data-stu-id="944d5-109">The location path `child::Customer` selects **\<Customer>** element children of the context node.</span></span>  
  
 <span data-ttu-id="944d5-110">En este ejemplo, `child` es el eje y `Customer` es la prueba de nodo.</span><span class="sxs-lookup"><span data-stu-id="944d5-110">In this example, `child` is the axis and `Customer` is the node test.</span></span> <span data-ttu-id="944d5-111">El tipo de nodo principal para el `child` eje es **\<element>** .</span><span class="sxs-lookup"><span data-stu-id="944d5-111">The principal node type for the `child` axis is **\<element>**.</span></span> <span data-ttu-id="944d5-112">Por lo tanto, la prueba de nodo es TRUE si el **\<Customer>** nodo es un **\<element>** nodo.</span><span class="sxs-lookup"><span data-stu-id="944d5-112">Therefore, the node test is TRUE if the **\<Customer>** node is an **\<element>** node.</span></span> <span data-ttu-id="944d5-113">Si el nodo de contexto no tiene ningún **\<Customer>** elemento secundario, se devuelve un conjunto de nodos vacío.</span><span class="sxs-lookup"><span data-stu-id="944d5-113">If the context node has no **\<Customer>** children, an empty set of nodes is returned.</span></span>  
  
## <a name="node-test-example-2"></a><span data-ttu-id="944d5-114">Prueba de nodo: Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="944d5-114">Node Test: Example 2</span></span>  
 <span data-ttu-id="944d5-115">La ruta `attribute::CustomerID` de acceso de ubicación selecciona el atributo **CustomerID** del nodo de contexto.</span><span class="sxs-lookup"><span data-stu-id="944d5-115">The location path `attribute::CustomerID` selects the **CustomerID** attribute of the context node.</span></span>  
  
 <span data-ttu-id="944d5-116">En el ejemplo, `attribute` es el eje y `CustomerID` es la prueba de nodo.</span><span class="sxs-lookup"><span data-stu-id="944d5-116">In the example, `attribute` is the axis and `CustomerID` is the node test.</span></span> <span data-ttu-id="944d5-117">El tipo de nodo principal del `attribute` eje es **\<attribute>** .</span><span class="sxs-lookup"><span data-stu-id="944d5-117">The principal node type of the `attribute` axis is **\<attribute>**.</span></span> <span data-ttu-id="944d5-118">Por lo tanto, la prueba de nodo es TRUE si **CustomerID** es un **\<attribute>** nodo.</span><span class="sxs-lookup"><span data-stu-id="944d5-118">Therefore, the node test is TRUE if **CustomerID** is an **\<attribute>** node.</span></span> <span data-ttu-id="944d5-119">Si el nodo de contexto no tiene **CustomerID**, se devuelve un conjunto vacío de nodos.</span><span class="sxs-lookup"><span data-stu-id="944d5-119">If the context node has no **CustomerID**, an empty set of nodes is returned.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="944d5-120">En esta implementación de XPath, si un paso de ubicación hace referencia a un **\<element>** **\<attribute>** tipo o que no está declarado en el esquema, se genera un error.</span><span class="sxs-lookup"><span data-stu-id="944d5-120">In this implementation of XPath, if a location step refers to an **\<element>** or an **\<attribute>** type that is not declared in the schema, an error is generated.</span></span> <span data-ttu-id="944d5-121">Este comportamiento es diferente al de la implementación de XPath en MSXML, que devuelve un conjunto de nodos vacío.</span><span class="sxs-lookup"><span data-stu-id="944d5-121">This is different from the implementation of XPath in MSXML, which returns an empty node set.</span></span>  
  
## <a name="abbreviated-syntax-for-the-axes"></a><span data-ttu-id="944d5-122">Sintaxis abreviada para los ejes</span><span class="sxs-lookup"><span data-stu-id="944d5-122">Abbreviated Syntax for the Axes</span></span>  
 <span data-ttu-id="944d5-123">Se admite la sintaxis abreviada siguiente para la ruta de acceso de ubicación:</span><span class="sxs-lookup"><span data-stu-id="944d5-123">The following abbreviated syntax for the location path is supported:</span></span>  
  
-   <span data-ttu-id="944d5-124">`attribute::` se puede abreviar como `@`.</span><span class="sxs-lookup"><span data-stu-id="944d5-124">`attribute::` can be abbreviated to `@`.</span></span>  
  
     <span data-ttu-id="944d5-125">La ruta de acceso de ubicación `Customer[@CustomerID="ALFKI"]` es la misma que `child::Customer[attribute::CustomerID="ALFKI"]`.</span><span class="sxs-lookup"><span data-stu-id="944d5-125">The location path `Customer[@CustomerID="ALFKI"]` is the same as `child::Customer[attribute::CustomerID="ALFKI"]`.</span></span>  
  
-   <span data-ttu-id="944d5-126">`child::` se puede omitir en un paso de ubicación.</span><span class="sxs-lookup"><span data-stu-id="944d5-126">`child::` can be omitted from a location step.</span></span>  
  
     <span data-ttu-id="944d5-127">Por tanto, `child` es el eje predeterminado.</span><span class="sxs-lookup"><span data-stu-id="944d5-127">Thus, `child` is the default axis.</span></span> <span data-ttu-id="944d5-128">La ruta de acceso de ubicación `Customer/Order` es la misma que `child::Customer/child::Order`.</span><span class="sxs-lookup"><span data-stu-id="944d5-128">The location path `Customer/Order` is the same as `child::Customer/child::Order`.</span></span>  
  
-   <span data-ttu-id="944d5-129">`self::node()` se puede abreviar en un punto (.) y `parent::node()` se puede abreviar en dos puntos (..).</span><span class="sxs-lookup"><span data-stu-id="944d5-129">`self::node()` can be abbreviated to one period (.), and `parent::node()` can be abbreviated to two periods (..).</span></span>  
  
  
