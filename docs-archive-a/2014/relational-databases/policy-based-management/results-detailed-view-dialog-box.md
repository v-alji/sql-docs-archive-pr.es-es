---
title: Cuadro de diálogo Vista detallada de resultados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.results.f1
- sql12.swb.dmf.policy.resultdetails.f1
ms.assetid: 366f0ff8-722a-40a9-934f-854147e4933d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1c4d669fb1546d27eb8b6ae78e0de8dea5975f24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749761"
---
# <a name="results-detailed-view-dialog-box"></a><span data-ttu-id="37009-102">Cuadro de diálogo Vista detallada de resultados</span><span class="sxs-lookup"><span data-stu-id="37009-102">Results Detailed View Dialog Box</span></span>
  <span data-ttu-id="37009-103">Este cuadro de diálogo muestra los resultados de la evaluación de una directiva cuando se ejecuta una mediante el cuadro de diálogo **Evaluar directivas** y se hace hacer clic en **Ver**.</span><span class="sxs-lookup"><span data-stu-id="37009-103">This dialog box shows the results of policy evaluation after you have run a policy by using the **Evaluate Policies** dialog box and clicked **Evaluate**.</span></span> <span data-ttu-id="37009-104">Este cuadro de diálogo es de solo lectura y le ayuda a entender qué parte de una expresión de propiedad podría no ser correcta.</span><span class="sxs-lookup"><span data-stu-id="37009-104">This dialog box is read-only, and helps you understand which part of a property expression might be failing.</span></span>  
  
## <a name="options"></a><span data-ttu-id="37009-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="37009-105">Options</span></span>  
 <span data-ttu-id="37009-106">**Y/O**</span><span class="sxs-lookup"><span data-stu-id="37009-106">**AndOr**</span></span>  
 <span data-ttu-id="37009-107">Cuando hay más de una expresión de propiedad, indica si las expresiones de propiedad son acumulativas o alternativas.</span><span class="sxs-lookup"><span data-stu-id="37009-107">When more than one property expression is present, indicates whether the property expressions are cumulative or alternative.</span></span>  
  
 <span data-ttu-id="37009-108">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="37009-108">**Result**</span></span>  
 <span data-ttu-id="37009-109">Icono que representa la corrección o el error de la expresión de propiedad.</span><span class="sxs-lookup"><span data-stu-id="37009-109">Icon that represents the success or failure of the property expression.</span></span>  
  
 <span data-ttu-id="37009-110">**Campo**</span><span class="sxs-lookup"><span data-stu-id="37009-110">**Field**</span></span>  
 <span data-ttu-id="37009-111">Propiedad de la faceta que se modela.</span><span class="sxs-lookup"><span data-stu-id="37009-111">The property of the facet that is being modeled.</span></span>  
  
 <span data-ttu-id="37009-112">**Operador**</span><span class="sxs-lookup"><span data-stu-id="37009-112">**Operator**</span></span>  
 <span data-ttu-id="37009-113">Operador de la expresión, por ejemplo **=** o **Like**.</span><span class="sxs-lookup"><span data-stu-id="37009-113">The operator for the expression, for example **=** or **Like**.</span></span>  
  
 <span data-ttu-id="37009-114">**Valor esperado**</span><span class="sxs-lookup"><span data-stu-id="37009-114">**Expected Value**</span></span>  
 <span data-ttu-id="37009-115">Valor del campo que hará que la expresión de propiedad sea correcta.</span><span class="sxs-lookup"><span data-stu-id="37009-115">The value for the field that will cause the property expression to be successful.</span></span>  
  
 <span data-ttu-id="37009-116">**Valor real**</span><span class="sxs-lookup"><span data-stu-id="37009-116">**Actual Value**</span></span>  
 <span data-ttu-id="37009-117">Valor del campo que la directiva detectó.</span><span class="sxs-lookup"><span data-stu-id="37009-117">The value for the field that was detected by the policy.</span></span>  
  
 <span data-ttu-id="37009-118">**Descripción de directiva**</span><span class="sxs-lookup"><span data-stu-id="37009-118">**Policy description**</span></span>  
 <span data-ttu-id="37009-119">Descripción de la directiva.</span><span class="sxs-lookup"><span data-stu-id="37009-119">The description of the policy.</span></span>  
  
 <span data-ttu-id="37009-120">**Ayuda adicional**</span><span class="sxs-lookup"><span data-stu-id="37009-120">**Additional help**</span></span>  
 <span data-ttu-id="37009-121">Haga clic en el hipervínculo para abrir una página web que esté relacionada con esta directiva.</span><span class="sxs-lookup"><span data-stu-id="37009-121">Click the hyperlink to open a Web page that is related to this policy.</span></span> <span data-ttu-id="37009-122">Al crear la directiva, se configura un hipervínculo de ayuda adicional que podría estar en blanco o no disponible.</span><span class="sxs-lookup"><span data-stu-id="37009-122">The Additional Help hyperlink is configured when the policy is created and might be blank or unavailable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37009-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="37009-123">See Also</span></span>  
 <span data-ttu-id="37009-124">[Nodo Administración de directivas &#40;Explorador de objetos&#41;](../../ssms/object/object-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="37009-124">[Policy Management Node &#40;Object Explorer&#41;](../../ssms/object/object-explorer.md) </span></span>  
 [<span data-ttu-id="37009-125">Administrar servidores mediante administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="37009-125">Administer Servers by Using Policy-Based Management</span></span>](administer-servers-by-using-policy-based-management.md)  
  
  
