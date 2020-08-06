---
title: Generar automáticamente valores para el atributo Code (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 19b354ee-2906-4cc7-ba2f-32b4543bddcf
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 6c442f37ffe322985ba55b29b2c4cd539b8a3e05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676042"
---
# <a name="automatically-generate-code-attribute-values-master-data-services"></a><span data-ttu-id="dc61f-102">Generar automáticamente valores para el atributo Code (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="dc61f-102">Automatically Generate Code Attribute Values (Master Data Services)</span></span>
  <span data-ttu-id="dc61f-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], genere automáticamente valores para el atributo Code de una entidad si quiere que se asigne de forma automática un entero al valor Code cada vez que se cree un miembro.</span><span class="sxs-lookup"><span data-stu-id="dc61f-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], automatically generate values for an entity's Code attribute when you want an integer to be automatically assigned to the Code value each time a new member is created.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="dc61f-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="dc61f-104">Prerequisites</span></span>  
 <span data-ttu-id="dc61f-105">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="dc61f-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="dc61f-106">Debe disponer de permiso para tener acceso al área funcional de **Administración del sistema** .</span><span class="sxs-lookup"><span data-stu-id="dc61f-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="dc61f-107">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="dc61f-107">You must be a model administrator.</span></span> <span data-ttu-id="dc61f-108">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="dc61f-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="dc61f-109">La entidad debe existir.</span><span class="sxs-lookup"><span data-stu-id="dc61f-109">The entity must exist.</span></span> <span data-ttu-id="dc61f-110">Para obtener más información, vea [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="dc61f-110">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-automatically-generate-code-values"></a><span data-ttu-id="dc61f-111">Para generar automáticamente valores Code</span><span class="sxs-lookup"><span data-stu-id="dc61f-111">To automatically generate Code values</span></span>  
  
1.  <span data-ttu-id="dc61f-112">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="dc61f-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="dc61f-113">En la página **Explorador de modelos** , en la barra de menús, seleccione **administrar** y haga clic en **entidades**.</span><span class="sxs-lookup"><span data-stu-id="dc61f-113">On the **Model Explorer** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="dc61f-114">En la página **Mantenimiento de entidades** , en la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="dc61f-114">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="dc61f-115">Seleccione la fila para la entidad para la que desea generar códigos.</span><span class="sxs-lookup"><span data-stu-id="dc61f-115">Select the row for the entity that you want to generate codes for.</span></span>  
  
5.  <span data-ttu-id="dc61f-116">Haga clic en **Editar entidad seleccionada**.</span><span class="sxs-lookup"><span data-stu-id="dc61f-116">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="dc61f-117">Active la casilla **Crear automáticamente valores Code** .</span><span class="sxs-lookup"><span data-stu-id="dc61f-117">Select the **Create Code values automatically** check box.</span></span>  
  
7.  <span data-ttu-id="dc61f-118">En el cuadro **Empezar con** , escriba un número para ir incrementándolo.</span><span class="sxs-lookup"><span data-stu-id="dc61f-118">In the **Start with** box, type a number to begin incrementing.</span></span> <span data-ttu-id="dc61f-119">Si ya existen miembros, el valor Code se establece según el mayor valor existente.</span><span class="sxs-lookup"><span data-stu-id="dc61f-119">If members already exist, the Code will be set based on the highest existing value.</span></span> <span data-ttu-id="dc61f-120">Por ejemplo, si el mayor valor Code existente es 299, el valor Code del miembro siguiente se establecerá en 300.</span><span class="sxs-lookup"><span data-stu-id="dc61f-120">For example, if the highest existing Code value is 299, the next member's Code value will be set to 300.</span></span>  
  
8.  <span data-ttu-id="dc61f-121">Haga clic en **Guardar entidad**.</span><span class="sxs-lookup"><span data-stu-id="dc61f-121">Click **Save entity**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc61f-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dc61f-122">See Also</span></span>  
 <span data-ttu-id="dc61f-123">[Creación automática de código &#40;Master Data Services&#41;](../../2014/master-data-services/automatic-code-creation-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="dc61f-123">[Automatic Code Creation &#40;Master Data Services&#41;](../../2014/master-data-services/automatic-code-creation-master-data-services.md) </span></span>  
 [<span data-ttu-id="dc61f-124">Generar automáticamente valores de atributo que no sean Code &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="dc61f-124">Automatically Generate Attribute Values Other Than Code &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/automatically-generate-attribute-values-other-than-code-master-data-services.md)  
  
  
