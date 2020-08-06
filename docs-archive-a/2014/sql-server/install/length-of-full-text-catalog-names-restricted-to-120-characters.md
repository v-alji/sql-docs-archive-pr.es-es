---
title: La longitud de los nombres de catálogo de texto completo está restringida a 120 caracteres | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- full-text catalogs names
ms.assetid: 50633373-83f6-4ed9-99b9-71f92479a14f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: fa9b06fa6fe4acd79782c19a8814357721e59c24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678026"
---
# <a name="length-of-full-text-catalog-names-restricted-to-120-characters"></a><span data-ttu-id="90310-102">La longitud de los nombres del catálogo de texto completo está restringida a 120 caracteres</span><span class="sxs-lookup"><span data-stu-id="90310-102">Length of full-text catalog names restricted to 120 characters</span></span>
  <span data-ttu-id="90310-103">La longitud de los nombres de catálogos de texto completo se limita a 120 caracteres, lo que representa una reducción con respecto a la limitación de 128 caracteres de versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90310-103">The length of full-text catalog names is restricted to 120 characters, reduced from the 128 character restriction in previous releases of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="description"></a><span data-ttu-id="90310-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="90310-104">Description</span></span>  
 <span data-ttu-id="90310-105">Este cambio no afecta a los nombres del catálogo existentes; sin embargo, los scripts que crean catálogos de texto completo con nombres con más de 120 caracteres producirán un error.</span><span class="sxs-lookup"><span data-stu-id="90310-105">This change does not affect existing catalog names; however, scripts that create full-text catalogs with names longer than 120 characters result in an error.</span></span> <span data-ttu-id="90310-106">Los nombres de catálogo se utilizan para generar nombres de archivo lógicos que se corresponden con los catálogos.</span><span class="sxs-lookup"><span data-stu-id="90310-106">The catalog names are used to generate logical file names that correspond to catalogs.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="90310-107">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="90310-107">Corrective Action</span></span>  
 <span data-ttu-id="90310-108">Modifique todos aquellos scripts que creen catálogos de texto completo para asegurarse de que restringen los nombres a 120 caracteres.</span><span class="sxs-lookup"><span data-stu-id="90310-108">Modify all scripts that create full-text catalogs to ensure that they restrict catalog names to 120 characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90310-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="90310-109">See Also</span></span>  
 [<span data-ttu-id="90310-110">Trabajar con el Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="90310-110">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
