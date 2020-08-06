---
title: Buscar informes y otros elementos (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6a586659-5c2b-453b-8f40-a3a469277b17
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a964cbdbc674fb3d29e18b5e5075695f0033801e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662613"
---
# <a name="searching-for-reports-and-other-items-report-builder--and-ssrs"></a><span data-ttu-id="2b416-102">Buscar informes y otros elementos (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="2b416-102">Searching for Reports and Other Items (Report Builder  and SSRS)</span></span>
  <span data-ttu-id="2b416-103">Puede usar el Administrador de informes para buscar en un servidor de informes elementos específicos por nombre o descripción.</span><span class="sxs-lookup"><span data-stu-id="2b416-103">You can use Report Manager to search a report server for specific items by name or description.</span></span> <span data-ttu-id="2b416-104">Tiene la posibilidad de buscar informes publicados, modelos de informe, carpetas, orígenes de datos compartidos y recursos.</span><span class="sxs-lookup"><span data-stu-id="2b416-104">You can search for published reports, report models, folders, shared data sources, and resources.</span></span> <span data-ttu-id="2b416-105">En cambio, no pueden realizarse búsquedas de programaciones, propietarios, asignaciones de roles, instantáneas específicas del historial del informe ni suscripciones.</span><span class="sxs-lookup"><span data-stu-id="2b416-105">You cannot search for schedules, owners, role assignments, specific snapshots in report history, or subscriptions.</span></span> <span data-ttu-id="2b416-106">La búsqueda se realiza en la base de datos del servidor de informes en la que se almacenan los elementos.</span><span class="sxs-lookup"><span data-stu-id="2b416-106">The search is performed on the report server database where the items are stored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2b416-107">La búsqueda en el sistema de archivos no devuelve resultados para los elementos administrados por el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="2b416-107">Performing a file system search will not return search results for items managed by a report server.</span></span>  
  
-   <span data-ttu-id="2b416-108">Para buscar elementos en el Administrador de informes, escriba la cadena para buscar en el cuadro de texto **Buscar** que figura en la parte superior de la página.</span><span class="sxs-lookup"><span data-stu-id="2b416-108">To search for items in Report Manager, type a search string in the **Search for** text box at the top of the page.</span></span> <span data-ttu-id="2b416-109">La búsqueda se inicia en el nodo superior de la jerarquía de carpetas y prosigue hacia abajo examinando cada rama.</span><span class="sxs-lookup"><span data-stu-id="2b416-109">Searches begin at the top node in the folder hierarchy and then proceed through every branch.</span></span> <span data-ttu-id="2b416-110">En caso de no tener permiso de acceso a una determinada rama, ésta se omite del proceso.</span><span class="sxs-lookup"><span data-stu-id="2b416-110">If you do not have permission to access a specific branch, that branch is skipped.</span></span> <span data-ttu-id="2b416-111">Este comportamiento también es válido para las carpetas Mis informes que pertenecen a otros usuarios y para otras carpetas que no suelen estar disponibles.</span><span class="sxs-lookup"><span data-stu-id="2b416-111">This applies to My Reports folders that belong to other users, and to other folders that are not generally available.</span></span> <span data-ttu-id="2b416-112">Los resultados de la búsqueda se limitan exclusivamente a los informes y los elementos para los que el usuario tiene permiso de visualización.</span><span class="sxs-lookup"><span data-stu-id="2b416-112">Only reports and items that you have permission to view are included in the search results.</span></span>  
  
-   <span data-ttu-id="2b416-113">Para buscar un elemento por nombre o descripción, especifique una parte del texto que desee que coincida o el texto completo.</span><span class="sxs-lookup"><span data-stu-id="2b416-113">To search for an item by name or description, specify all or part of the text that you want to match.</span></span> <span data-ttu-id="2b416-114">La cadena para buscar no distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="2b416-114">The search string is not case-sensitive.</span></span> <span data-ttu-id="2b416-115">Tenga en cuenta que no se pueden usar operadores de búsqueda como los signos más (+) o menos (-) para exigir o excluir criterios de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="2b416-115">You cannot use search operators such as plus (+) or minus (-) symbols to require or exclude search criteria.</span></span>  
  
-   <span data-ttu-id="2b416-116">Para buscar texto específico dentro de un informe, use la barra de herramientas situada en la parte superior del informe.</span><span class="sxs-lookup"><span data-stu-id="2b416-116">To search for specific text within a report, use the toolbar at the top of the report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2b416-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2b416-117">See Also</span></span>  
 <span data-ttu-id="2b416-118">[Buscar y ver informes en Administrador de informes &#40;Generador de informes y SSRS&#41;](finding-and-viewing-reports-in-the-web-portal-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2b416-118">[Finding and Viewing Reports in Report Manager &#40;Report Builder and SSRS&#41;](finding-and-viewing-reports-in-the-web-portal-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2b416-119">[Usar Mis informes &#40;Generador de informes y SSRS&#41;](using-my-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2b416-119">[Using My Reports &#40;Report Builder and SSRS&#41;](using-my-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2b416-120">[Buscar, ver y administrar informes &#40;Generador de informes y SSRS &#41;](finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2b416-120">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="2b416-121">Abrir y cerrar un informe &#40;Administrador de informes&#41;</span><span class="sxs-lookup"><span data-stu-id="2b416-121">Open and Close a Report &#40;Report Manager&#41;</span></span>](../reports/open-and-close-a-report-report-manager.md)  
  
  
