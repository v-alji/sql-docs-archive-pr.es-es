---
title: Objetos que admite el asistente Generar scripts
ms.custom: seo-lt-2019
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 071eb2cb-f073-41ca-9f4d-11d3b8803495
author: rothja
ms.author: jroth
ms.openlocfilehash: 5ddc1da0d2f87fc12dfbe034a683802f54b7d34f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676456"
---
# <a name="objects-supported-by-the-generate-scripts-wizard"></a><span data-ttu-id="059be-102">Objetos que admite el asistente Generar scripts</span><span class="sxs-lookup"><span data-stu-id="059be-102">Objects Supported by the Generate Scripts Wizard</span></span>
  <span data-ttu-id="059be-103">El asistente Generar y publicar scripts admite un subconjunto de los objetos admitidos por [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="059be-103">The Generate and Publish Scripts wizard supports a subset of the objects supported by the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
## <a name="supported-objects"></a><span data-ttu-id="059be-104">Objetos admitidos</span><span class="sxs-lookup"><span data-stu-id="059be-104">Supported Objects</span></span>  
 <span data-ttu-id="059be-105">La tabla siguiente enumera los objetos que se pueden publicar y que admite el Asistente para generar y publicar scripts.</span><span class="sxs-lookup"><span data-stu-id="059be-105">The following table lists the objects that can be published supported by the Generate and Publish Scripts Wizard.</span></span>  
  
||||||  
|-|-|-|-|-|  
|<span data-ttu-id="059be-106">Rol de aplicación</span><span class="sxs-lookup"><span data-stu-id="059be-106">Application role</span></span>|<span data-ttu-id="059be-107">Rol de base de datos</span><span class="sxs-lookup"><span data-stu-id="059be-107">Database role</span></span>|<span data-ttu-id="059be-108">Schema</span><span class="sxs-lookup"><span data-stu-id="059be-108">Schema</span></span>|<span data-ttu-id="059be-109">Agregados definidos por el usuario</span><span class="sxs-lookup"><span data-stu-id="059be-109">User-defined aggregate</span></span>|<span data-ttu-id="059be-110">Vista<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="059be-110">View<sup>1</sup></span></span>|  
|<span data-ttu-id="059be-111">Assembly</span><span class="sxs-lookup"><span data-stu-id="059be-111">Assembly</span></span>|<span data-ttu-id="059be-112">Restricción DEFAULT</span><span class="sxs-lookup"><span data-stu-id="059be-112">DEFAULT constraint</span></span>|<span data-ttu-id="059be-113">Procedimiento almacenado<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="059be-113">Stored procedure<sup>1</sup></span></span>|<span data-ttu-id="059be-114">Tipos de datos definidos por el usuario</span><span class="sxs-lookup"><span data-stu-id="059be-114">User-defined data type</span></span>|<span data-ttu-id="059be-115">Colección de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="059be-115">XML schema collection</span></span>|  
|<span data-ttu-id="059be-116">Restricción CHECK</span><span class="sxs-lookup"><span data-stu-id="059be-116">CHECK constraint</span></span>|<span data-ttu-id="059be-117">Catálogo de texto completo</span><span class="sxs-lookup"><span data-stu-id="059be-117">Full-text catalog</span></span>|<span data-ttu-id="059be-118">Synonym (Sinónimo)</span><span class="sxs-lookup"><span data-stu-id="059be-118">Synonym</span></span>|<span data-ttu-id="059be-119">Función definida por el usuario</span><span class="sxs-lookup"><span data-stu-id="059be-119">User-defined function</span></span>||  
|<span data-ttu-id="059be-120">Procedimiento almacenado de CLR (Common Language Runtime)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="059be-120">CLR (common language runtime) stored procedure<sup>1</sup></span></span>|<span data-ttu-id="059be-121">Índice</span><span class="sxs-lookup"><span data-stu-id="059be-121">Index</span></span>|<span data-ttu-id="059be-122">Tabla</span><span class="sxs-lookup"><span data-stu-id="059be-122">Table</span></span>|<span data-ttu-id="059be-123">Tabla definida por el usuario</span><span class="sxs-lookup"><span data-stu-id="059be-123">User-defined table</span></span>||  
|<span data-ttu-id="059be-124">Función CLR definida por el usuario</span><span class="sxs-lookup"><span data-stu-id="059be-124">CLR user-defined function</span></span>|<span data-ttu-id="059be-125">Regla</span><span class="sxs-lookup"><span data-stu-id="059be-125">Rule</span></span>|<span data-ttu-id="059be-126">Usuario<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="059be-126">User<sup>2</sup></span></span>|<span data-ttu-id="059be-127">Tipo definido por el usuario</span><span class="sxs-lookup"><span data-stu-id="059be-127">User-defined type</span></span>||  
  
 <span data-ttu-id="059be-128"><sup>1</sup> publicado sin cifrado.</span><span class="sxs-lookup"><span data-stu-id="059be-128"><sup>1</sup> Published without encryption.</span></span>  
  
 <span data-ttu-id="059be-129"><sup>2</sup> cualquier usuario que no sea del sistema que exista en la base de datos se publicará como rol.</span><span class="sxs-lookup"><span data-stu-id="059be-129"><sup>2</sup> Any non-system users that exist in the database are published as Roles.</span></span>  
  
  
