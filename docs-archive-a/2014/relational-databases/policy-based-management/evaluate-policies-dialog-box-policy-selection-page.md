---
title: Cuadro de diálogo Evaluar directivas, página Selección de directiva | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.runnow.f1
ms.assetid: 20075fbe-0b48-42c8-b747-690f1aa23dcf
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f68a1ccc7873b6a05d2641ddaa87e8d5b0e5c6d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744637"
---
# <a name="evaluate-policies-dialog-box-policy-selection-page"></a><span data-ttu-id="f1951-102">Cuadro de diálogo Evaluar directivas, página Selección de directiva</span><span class="sxs-lookup"><span data-stu-id="f1951-102">Evaluate Policies Dialog Box, Policy Selection Page</span></span>
  <span data-ttu-id="f1951-103">Utilice este cuadro de diálogo para evaluar las directivas de administración basada en directivas.</span><span class="sxs-lookup"><span data-stu-id="f1951-103">Use this dialog box to evaluate Policy-Based Management policies.</span></span> <span data-ttu-id="f1951-104">Al seleccionar la página **Resultados de la evaluación** , puede aplicar directivas a los elementos de un conjunto de destinos que no cumplen las directivas.</span><span class="sxs-lookup"><span data-stu-id="f1951-104">By selecting the **Evaluation Results** page, you can apply policies to the items in a target set that do not comply with the policies.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f1951-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="f1951-105">Options</span></span>  
 <span data-ttu-id="f1951-106">**Origen**</span><span class="sxs-lookup"><span data-stu-id="f1951-106">**Source**</span></span>  
 <span data-ttu-id="f1951-107">Especifica el origen de las directivas.</span><span class="sxs-lookup"><span data-stu-id="f1951-107">Specifies the source of the policies.</span></span> <span data-ttu-id="f1951-108">Para cambiar el origen, haga clic en el botón Examinar (**...**) para abrir el cuadro de diálogo **Seleccionar origen** .</span><span class="sxs-lookup"><span data-stu-id="f1951-108">To change the source, click the Browse (**...**) button to open the **Select Source** dialog box.</span></span>  
  
 <span data-ttu-id="f1951-109">**Archivos**</span><span class="sxs-lookup"><span data-stu-id="f1951-109">**Files**</span></span>  
 <span data-ttu-id="f1951-110">Escriba la ruta de acceso de un archivo que contenga una directiva de administración basada en directivas, o use el botón Examinar (**...**) para seleccionar el archivo.</span><span class="sxs-lookup"><span data-stu-id="f1951-110">Type the path of a file that contains a Policy-Based Management policy, or use the Browse (**...**) button to select the file.</span></span>  
  
 <span data-ttu-id="f1951-111">**Server**</span><span class="sxs-lookup"><span data-stu-id="f1951-111">**Server**</span></span>  
 <span data-ttu-id="f1951-112">Seleccione esta opción para conectarse a una instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] que contenga la directiva que desea.</span><span class="sxs-lookup"><span data-stu-id="f1951-112">Select to connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that contains the policy that you want.</span></span>  
  
 <span data-ttu-id="f1951-113">**Directivas: Directiva**</span><span class="sxs-lookup"><span data-stu-id="f1951-113">**Policies: Policy**</span></span>  
 <span data-ttu-id="f1951-114">Haga clic en esta opción para abrir el cuadro de diálogo de directiva correspondiente a la directiva especificada.</span><span class="sxs-lookup"><span data-stu-id="f1951-114">Click to open the policy dialog box for the specified policy.</span></span>  
  
 <span data-ttu-id="f1951-115">**Directivas: Categoría**</span><span class="sxs-lookup"><span data-stu-id="f1951-115">**Policies: Category**</span></span>  
 <span data-ttu-id="f1951-116">Categoría de la directiva.</span><span class="sxs-lookup"><span data-stu-id="f1951-116">The category of the policy.</span></span> <span data-ttu-id="f1951-117">Este cuadro es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="f1951-117">This box is read-only.</span></span>  
  
 <span data-ttu-id="f1951-118">**Directivas: Faceta**</span><span class="sxs-lookup"><span data-stu-id="f1951-118">**Policies: Facet**</span></span>  
 <span data-ttu-id="f1951-119">Faceta implementada por la directiva.</span><span class="sxs-lookup"><span data-stu-id="f1951-119">The facet implemented by the policy.</span></span> <span data-ttu-id="f1951-120">Este cuadro es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="f1951-120">This box is read-only.</span></span>  
  
 <span data-ttu-id="f1951-121">**Evaluate**</span><span class="sxs-lookup"><span data-stu-id="f1951-121">**Evaluate**</span></span>  
 <span data-ttu-id="f1951-122">Ejecuta la directiva en modo de evaluación.</span><span class="sxs-lookup"><span data-stu-id="f1951-122">Runs the policy in evaluation mode.</span></span> <span data-ttu-id="f1951-123">De esta forma se genera un informe de compatibilidad para el conjunto de destino, pero no se vuelve a configurar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ni se exige la compatibilidad en el futuro.</span><span class="sxs-lookup"><span data-stu-id="f1951-123">This generates a compliance report for the target set but does not reconfigure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or enforce future compliance.</span></span>  
  
## <a name="possible-errors"></a><span data-ttu-id="f1951-124">Errores posibles</span><span class="sxs-lookup"><span data-stu-id="f1951-124">Possible Errors</span></span>  
  
-   <span data-ttu-id="f1951-125">**No se encontraron destinos**</span><span class="sxs-lookup"><span data-stu-id="f1951-125">**No targets found**</span></span>  
  
     <span data-ttu-id="f1951-126">El conjunto de destino podría estar vacío debido a alguna de las razones siguientes:</span><span class="sxs-lookup"><span data-stu-id="f1951-126">The target set could be empty due to any of the following reasons:</span></span>  
  
    -   <span data-ttu-id="f1951-127">No hay ningún destino en la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] del tipo especificado por la directiva.</span><span class="sxs-lookup"><span data-stu-id="f1951-127">There are no targets on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] of the type specified by the policy.</span></span>  
  
    -   <span data-ttu-id="f1951-128">La restricción de servidor podría excluir la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que contiene el destino.</span><span class="sxs-lookup"><span data-stu-id="f1951-128">The server restriction might exclude the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that contains the target.</span></span>  
  
    -   <span data-ttu-id="f1951-129">Si la directiva está en un objeto de una base de datos (por ejemplo una tabla, vista o usuario), la base de datos podría no suscribirse a la categoría de la directiva.</span><span class="sxs-lookup"><span data-stu-id="f1951-129">If the policy is on an object in a database (for example a table, view, or user) the database might not subscribe to the category of the policy.</span></span>  
  
    -   <span data-ttu-id="f1951-130">El filtro del conjunto de destino podría excluir todos los destinos de esta instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f1951-130">The target-set filter might exclude all targets on this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
    -   <span data-ttu-id="f1951-131">El tipo de servidor de destino es diferente del tipo de servidor en el que se evalúa la directiva.</span><span class="sxs-lookup"><span data-stu-id="f1951-131">The target server type is different from the server type on which the policy is evaluated.</span></span> <span data-ttu-id="f1951-132">Por ejemplo, en [!INCLUDE[ssDE](../../includes/ssde-md.md)], si intenta evaluar una directiva creada para [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], recibirá un conjunto de destinos vacío.</span><span class="sxs-lookup"><span data-stu-id="f1951-132">For example, in the [!INCLUDE[ssDE](../../includes/ssde-md.md)], if you try to evaluate a policy that has been created for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], you will receive an empty target set</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1951-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f1951-133">See Also</span></span>  
 <span data-ttu-id="f1951-134">[Administrar servidores mediante la administración basada en directivas](administer-servers-by-using-policy-based-management.md) </span><span class="sxs-lookup"><span data-stu-id="f1951-134">[Administer Servers by Using Policy-Based Management](administer-servers-by-using-policy-based-management.md) </span></span>  
 [<span data-ttu-id="f1951-135">Cuadro de diálogo Evaluar directivas, página Resultados de la evaluación</span><span class="sxs-lookup"><span data-stu-id="f1951-135">Evaluate Policies Dialog Box, Evaluation Results Page</span></span>](evaluate-policies-dialog-box-evaluation-results-page.md)  
  
  
