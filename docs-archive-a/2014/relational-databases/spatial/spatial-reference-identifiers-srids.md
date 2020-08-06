---
title: Identificadores de referencia espacial (SRID) | Microsoft Docs
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Spatial Reference Identifiers (SRIDs)
- geodetic spatial data [SQL Server], identifiers
- SRID
ms.assetid: 0612658a-7d1b-4178-bdc2-42b914ea31a7
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 15db59b43731b9a39ff4bef78e3a6cb6929e9b47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674050"
---
# <a name="spatial-reference-identifiers-srids"></a><span data-ttu-id="f9fc1-102">Identificadores de referencia espacial (SRID)</span><span class="sxs-lookup"><span data-stu-id="f9fc1-102">Spatial Reference Identifiers (SRIDs)</span></span>
  <span data-ttu-id="f9fc1-103">Cada instancia espacial tiene un identificador de referencia espacial (SRID).</span><span class="sxs-lookup"><span data-stu-id="f9fc1-103">Each spatial instance has a spatial reference identifier (SRID).</span></span> <span data-ttu-id="f9fc1-104">El SRID corresponde a un sistema de referencia espacial basado en el elipsoide concreto usado para la creación de mapas de tierra plana o de tierra redonda.</span><span class="sxs-lookup"><span data-stu-id="f9fc1-104">The SRID corresponds to a spatial reference system based on the specific ellipsoid used for either flat-earth mapping or round-earth mapping.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f9fc1-105">Para obtener una descripción detallada y ejemplos de las características espaciales introducidas en [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], incluido un nuevo SRID, descargue las notas del producto sobre las [nuevas características espaciales de SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span><span class="sxs-lookup"><span data-stu-id="f9fc1-105">For a detailed description and examples of spatial features introduced in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], including a new SRID, download the white paper, [New Spatial Features in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span></span>  
  
 <span data-ttu-id="f9fc1-106">Una columna espacial puede contener objetos con SRID diferentes.</span><span class="sxs-lookup"><span data-stu-id="f9fc1-106">A spatial column can contain objects with different SRIDs.</span></span> <span data-ttu-id="f9fc1-107">Sin embargo, solo se pueden usar instancias espaciales con el mismo SRID al realizar operaciones con métodos de datos espaciales de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en sus datos.</span><span class="sxs-lookup"><span data-stu-id="f9fc1-107">However, only spatial instances with the same SRID can be used when performing operations with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] spatial data methods on your data.</span></span> <span data-ttu-id="f9fc1-108">El resultado de cualquier método espacial derivado de dos instancias de datos espaciales solo es válido si dichas instancias tienen el mismo SRID basado en la misma unidad de medida, dato y proyección usados para determinar las coordenadas de las instancias.</span><span class="sxs-lookup"><span data-stu-id="f9fc1-108">The result of any spatial method derived from two spatial data instances is valid only if those instances have the same SRID that is based on the same unit of measurement, datum, and projection used to determine the coordinates of the instances.</span></span> <span data-ttu-id="f9fc1-109">Las unidades de medida más comunes de un SRID son metros o metros cuadrados.</span><span class="sxs-lookup"><span data-stu-id="f9fc1-109">The most common units of measurement of a SRID are meters or square meters.</span></span>  
  
 <span data-ttu-id="f9fc1-110">Si dos instancias espaciales no tienen el mismo SRID, los resultados de un método de tipo de datos `geometry` o `geography` usado en las instancias devolverá NULL.</span><span class="sxs-lookup"><span data-stu-id="f9fc1-110">If two spatial instances do not have the same SRID, the results from a `geometry` or `geography` Data Type method used on the instances will return NULL.</span></span> <span data-ttu-id="f9fc1-111">Por ejemplo, para que el siguiente término de predicado devuelva un resultado distinto de NULL, las dos instancias de `geometry`, `geometry1` y `geometry2`, deben tener el mismo SRID:</span><span class="sxs-lookup"><span data-stu-id="f9fc1-111">For example, for the following predicate term to return a non-NULL result, the two `geometry` instances, `geometry1` and `geometry2`, must have the same SRID:</span></span>  
  
 `geometry1.STIntersects(geometry2) = 1`  
  
> [!NOTE]  
>  <span data-ttu-id="f9fc1-112">El sistema de identificación de referencia espacial está definido por la norma de [Europaan Petroleum Survey Group (EPSG)](https://go.microsoft.com/fwlink/?LinkId=99349) , que consiste en un conjunto de normas desarrolladas para cartografía, sondeos y almacenamiento de datos geodésicos.</span><span class="sxs-lookup"><span data-stu-id="f9fc1-112">The spatial reference identification system is defined by the [European Petroleum Survey Group (EPSG)](https://go.microsoft.com/fwlink/?LinkId=99349) standard, which is a set of standards developed for cartography, surveying, and geodetic data storage.</span></span> <span data-ttu-id="f9fc1-113">Esta norma es propiedad del comité Surveying and Positioning Committee de Oil and Gas Producers (OGP).</span><span class="sxs-lookup"><span data-stu-id="f9fc1-113">This standard is owned by the Oil and Gas Producers (OGP) Surveying and Positioning Committee.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9fc1-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f9fc1-114">See Also</span></span>  
 [<span data-ttu-id="f9fc1-115">Información general de los tipos de datos espaciales</span><span class="sxs-lookup"><span data-stu-id="f9fc1-115">Spatial Data Types Overview</span></span>](spatial-data-types-overview.md)  
  
  
