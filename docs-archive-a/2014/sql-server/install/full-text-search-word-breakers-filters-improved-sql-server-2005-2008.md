---
title: Los separadores de palabras y los filtros de búsqueda de texto completo se han mejorado significativamente en SQL Server 2005 y SQL Server 2008 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- filters [Full-Text Search]
- word breakers [Full-Text Search]
ms.assetid: 8d06bda9-0bbf-4baa-b270-07b1c1f640eb
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d2e7d3b8da56b407d3937b05cd980c3f8a4eb0c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676846"
---
# <a name="full-text-search-word-breakers-and-filters-significantly-improved-in-sql-server-2005-and-sql-server-2008"></a><span data-ttu-id="20f9d-102">Los separadores y filtros de palabras de la búsqueda de texto completo se han mejorado considerablemente en SQL Server 2005 y en SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="20f9d-102">Full-Text Search word breakers and filters significantly improved in SQL Server 2005 and SQL Server 2008</span></span>
  <span data-ttu-id="20f9d-103">Los separadores de palabras y los filtros han sufrido cambios significativos.</span><span class="sxs-lookup"><span data-stu-id="20f9d-103">The word breakers and filters were significantly changed.</span></span> <span data-ttu-id="20f9d-104">Se han realizado mejoras adicionales a los separadores de palabras, incluyendo una cobertura mejorada del lenguaje y mayor confiabilidad.</span><span class="sxs-lookup"><span data-stu-id="20f9d-104">Additional improvements have been made to word breakers, including enhanced language coverage and reliability.</span></span>  
  
## <a name="description"></a><span data-ttu-id="20f9d-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="20f9d-105">Description</span></span>  
 <span data-ttu-id="20f9d-106">Los separadores de palabras y los filtros utilizados por la búsqueda de texto completo de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] han sido modificados notablemente para que obtengan mejoras en la funcionalidad y la confiabilidad.</span><span class="sxs-lookup"><span data-stu-id="20f9d-106">Word breakers and filters used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Full-Text Search have been significantly modified to achieve improvements in functionality and reliability.</span></span> <span data-ttu-id="20f9d-107">En algunos casos, los cambios realizados en los separadores de palabras pueden tener algún impacto en la forma en que se crean token a partir de los datos.</span><span class="sxs-lookup"><span data-stu-id="20f9d-107">In some specific cases, changes to the word breakers can impact how some data is tokenized.</span></span> <span data-ttu-id="20f9d-108">Los tokens creados en [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] pueden ser diferentes a los anteriores tokens creados en [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] o en [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="20f9d-108">Tokens created in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] may be different from earlier tokens created in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] or [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
 <span data-ttu-id="20f9d-109">Para obtener información acerca de los separadores de palabras, vea [configurar y administrar separadores de palabras y lematizadores para la búsqueda](../../relational-databases/search/configure-and-manage-word-breakers-and-stemmers-for-search.md).</span><span class="sxs-lookup"><span data-stu-id="20f9d-109">For information about word breakers, see [Configure and Manage Word Breakers and Stemmers for Search](../../relational-databases/search/configure-and-manage-word-breakers-and-stemmers-for-search.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20f9d-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="20f9d-110">See Also</span></span>  
 [<span data-ttu-id="20f9d-111">Trabajar con el Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="20f9d-111">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
