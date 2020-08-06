---
title: Modificar procedimientos almacenados que utilizan propiedades de búsqueda de texto completo no incluidas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- discontinued properties [Full-Text Search]
- stored procedures [Full-Text Search]
ms.assetid: 8d9392d9-a9ba-4378-84e4-59f516b67ddb
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 12262a588742f0e3be094e32a2a0208a85b6f28a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672466"
---
# <a name="modify-stored-procedures-that-use-discontinued-full-text-search-properties"></a><span data-ttu-id="c8528-102">Modificar los procedimientos almacenados que utilizan propiedades de búsqueda de texto completo no incluidas</span><span class="sxs-lookup"><span data-stu-id="c8528-102">Modify stored procedures that use discontinued Full-Text Search properties</span></span>
  <span data-ttu-id="c8528-103">Para asegurarse de que sus procedimientos almacenados funcionen correctamente, debería modificar los procedimientos existentes y quitar aquellas propiedades y configuraciones relacionadas con la búsqueda de texto completo que se han quitado o han quedado desusadas.</span><span class="sxs-lookup"><span data-stu-id="c8528-103">To ensure that your stored procedures perform correctly, you should edit existing procedures and remove those full-text related properties and settings that have been removed or deprecated.</span></span>  
  
## <a name="component"></a><span data-ttu-id="c8528-104">Componente</span><span class="sxs-lookup"><span data-stu-id="c8528-104">Component</span></span>  
 <span data-ttu-id="c8528-105">Búsqueda de texto completo</span><span class="sxs-lookup"><span data-stu-id="c8528-105">Full-Text Search</span></span>  
  
## <a name="description"></a><span data-ttu-id="c8528-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c8528-106">Description</span></span>  
 <span data-ttu-id="c8528-107">Los siguientes parámetros y propiedades relacionados con la búsqueda de texto completo se han quitado.</span><span class="sxs-lookup"><span data-stu-id="c8528-107">The following Full-Text Search-related properties and settings have been removed.</span></span>  
  
-   <span data-ttu-id="c8528-108">**DataTimeout**</span><span class="sxs-lookup"><span data-stu-id="c8528-108">**DataTimeout**</span></span>  
  
-   <span data-ttu-id="c8528-109">**ConnectTimeout**</span><span class="sxs-lookup"><span data-stu-id="c8528-109">**ConnectTimeout**</span></span>  
  
-   <span data-ttu-id="c8528-110">**Clean_up**</span><span class="sxs-lookup"><span data-stu-id="c8528-110">**Clean_up**</span></span>  
  
-   <span data-ttu-id="c8528-111">**LogSize**</span><span class="sxs-lookup"><span data-stu-id="c8528-111">**LogSize**</span></span>  
  
 <span data-ttu-id="c8528-112">Los siguientes parámetros y propiedades relacionados con la búsqueda de texto completo se han quitado o han quedado desusados:</span><span class="sxs-lookup"><span data-stu-id="c8528-112">The following Full-Text Search-related properties and settings have been removed or deprecated:</span></span>  
  
-   <span data-ttu-id="c8528-113">'Path' del catálogo de texto completo.</span><span class="sxs-lookup"><span data-stu-id="c8528-113">'Path' of the Full-Text Catalog.</span></span> <span data-ttu-id="c8528-114">El Catálogo de texto completo será un objeto lógico sin una ruta de acceso al archivo en el sistema.</span><span class="sxs-lookup"><span data-stu-id="c8528-114">The Full-Text Catalog will be a logic object without a specific file path in the system.</span></span>  
  
-   <span data-ttu-id="c8528-115">La función de habilitar o deshabilitar en SP_FULLTEXT_DATABASE ya no tiene ningún efecto cuando las bases de datos están habilitadas para las búsquedas de texto completo en todo momento y de forma predeterminada en [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8528-115">Enable/disable in SP_FULLTEXT_DATABASE has no effect anymore as databases are enabled for Full-Text Search at all times and by default in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="c8528-116">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="c8528-116">Corrective Action</span></span>  
 <span data-ttu-id="c8528-117">Modifique sus procedimientos almacenados para quitar estas propiedades.</span><span class="sxs-lookup"><span data-stu-id="c8528-117">Modify your stored procedures to remove these properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8528-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c8528-118">See Also</span></span>  
 [<span data-ttu-id="c8528-119">Trabajar con el Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="c8528-119">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
