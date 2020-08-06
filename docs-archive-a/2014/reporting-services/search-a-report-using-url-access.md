---
title: Buscar un informe mediante un acceso URL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- searching reports
- text searches [Reporting Services]
- URL access [Reporting Services], report searches
ms.assetid: 6f3410c4-7944-448f-bae8-bab3e8152d46
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b45f3fabf58a0980d41ee7b4b89a771655477d02
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749060"
---
# <a name="search-a-report-using-url-access"></a><span data-ttu-id="7d977-102">Buscar un informe mediante un acceso URL</span><span class="sxs-lookup"><span data-stu-id="7d977-102">Search a Report Using URL Access</span></span>
  <span data-ttu-id="7d977-103">Puede buscar un conjunto concreto de texto en un informe utilizando el acceso URL.</span><span class="sxs-lookup"><span data-stu-id="7d977-103">You can search a report for a specific set of text using URL access.</span></span> <span data-ttu-id="7d977-104">Para buscar en un informe, establezca el valor del parámetro *rc:FindString* en la URL igual al texto que desea buscar.</span><span class="sxs-lookup"><span data-stu-id="7d977-104">To search a report, set the value of the *rc:FindString* parameter on the URL equal to the text for which you want to search.</span></span> <span data-ttu-id="7d977-105">Además, utilice los parámetros *rc:StartFind* y *rc:EndFind* para restringir su búsqueda a las páginas determinadas dentro del informe.</span><span class="sxs-lookup"><span data-stu-id="7d977-105">Additionally, use the *rc:StartFind* and *rc:EndFind* parameters to narrow your search to specific pages within the report.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d977-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7d977-106">Example</span></span>  
 <span data-ttu-id="7d977-107">El siguiente ejemplo de acceso URL busca la primera aparición del texto "Mountain-400" en el informe de ejemplo Catálogo de productos desde la página uno hasta la página cinco:</span><span class="sxs-lookup"><span data-stu-id="7d977-107">The following URL access example searches for the first occurrence of the text "Mountain-400" in the Product Catalog sample report starting with page one and ending with page five:</span></span>  
  
```  
http://server/Reportserver?/SampleReports/Product Catalog&rs:Command=Render&rc:StartFind=1&rc:EndFind=5&rc:FindString=Mountain-400  
```  
  
## <a name="see-also"></a><span data-ttu-id="7d977-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7d977-108">See Also</span></span>  
 <span data-ttu-id="7d977-109">[Acceso URL &#40;SSRS&#41;](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7d977-109">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="7d977-110">Referencia de parámetros de acceso URL</span><span class="sxs-lookup"><span data-stu-id="7d977-110">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
