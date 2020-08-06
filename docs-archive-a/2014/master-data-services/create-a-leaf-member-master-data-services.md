---
title: Crear un miembro hoja (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- leaf members [Master Data Services], creating
- creating leaf members [Master Data Services]
- members [Master Data Services], creating leaf members
ms.assetid: 0499d3b3-d508-4d43-a740-19cf53ade9f1
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: fe0245dd30019e1cb9112754bd8b8eeafed93aa5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662144"
---
# <a name="create-a-leaf-member-master-data-services"></a><span data-ttu-id="d7c12-102">Crear un miembro hoja (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="d7c12-102">Create a Leaf Member (Master Data Services)</span></span>
  <span data-ttu-id="d7c12-103">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , cree un miembro hoja si desea agregar datos maestros al sistema y no utiliza tablas de almacenamiento provisional o [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)] para importar datos.</span><span class="sxs-lookup"><span data-stu-id="d7c12-103">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], create a leaf member when you want to add master data to your system and are not using staging tables or the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)] to import data.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d7c12-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d7c12-104">Prerequisites</span></span>  
 <span data-ttu-id="d7c12-105">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="d7c12-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="d7c12-106">Debe disponer de permiso de acceso al área funcional **Explorador** .</span><span class="sxs-lookup"><span data-stu-id="d7c12-106">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="d7c12-107">Debe tener como mínimo el permiso **Actualizar** para el objeto de modelo hoja para la entidad a la que va a agregar un miembro.</span><span class="sxs-lookup"><span data-stu-id="d7c12-107">You must have a minimum of **Update** permission to the leaf model object for the entity you are adding a member to.</span></span>  
  
### <a name="to-create-a-leaf-member"></a><span data-ttu-id="d7c12-108">Crear un miembro hoja</span><span class="sxs-lookup"><span data-stu-id="d7c12-108">To create a leaf member</span></span>  
  
1.  <span data-ttu-id="d7c12-109">En la página principal de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , en la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="d7c12-109">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="d7c12-110">Si es un usuario, seleccione una versión abierta de la lista **Versión** .</span><span class="sxs-lookup"><span data-stu-id="d7c12-110">If you are a user, select an open version from the **Version** list.</span></span> <span data-ttu-id="d7c12-111">Si es administrador, seleccione una versión que tenga el estado abierto o bloqueado de la lista **Versión** .</span><span class="sxs-lookup"><span data-stu-id="d7c12-111">If you are an administrator, select a version with open or locked status from the **Version** list.</span></span>  
  
3.  <span data-ttu-id="d7c12-112">Haga clic en **Explorador**.</span><span class="sxs-lookup"><span data-stu-id="d7c12-112">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="d7c12-113">En la barra de menús, seleccione **Entidades** y haga clic en el nombre de la entidad a la que desee agregar un miembro.</span><span class="sxs-lookup"><span data-stu-id="d7c12-113">From the menu bar, point to **Entities** and click the name of the entity you want to add a member to.</span></span>  
  
5.  <span data-ttu-id="d7c12-114">Haga clic en **Agregar miembro**.</span><span class="sxs-lookup"><span data-stu-id="d7c12-114">Click **Add member**.</span></span>  
  
6.  <span data-ttu-id="d7c12-115">En el panel **Detalles** , cumplimente los campos.</span><span class="sxs-lookup"><span data-stu-id="d7c12-115">In the **Details** pane, complete the fields.</span></span>  
  
7.  <span data-ttu-id="d7c12-116">Opcional.</span><span class="sxs-lookup"><span data-stu-id="d7c12-116">Optional.</span></span> <span data-ttu-id="d7c12-117">En el cuadro **Anotaciones** , escriba un comentario sobre los motivos por los que se agregó el miembro.</span><span class="sxs-lookup"><span data-stu-id="d7c12-117">In the **Annotations** box, type a comment about why the member was added.</span></span> <span data-ttu-id="d7c12-118">Todos los usuarios que tienen acceso al miembro pueden ver la anotación.</span><span class="sxs-lookup"><span data-stu-id="d7c12-118">All users who have access to the member can view the annotation.</span></span>  
  
8.  <span data-ttu-id="d7c12-119">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="d7c12-119">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7c12-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d7c12-120">See Also</span></span>  
 <span data-ttu-id="d7c12-121">[Cargar o actualizar miembros en Master Data Services mediante el proceso de almacenamiento provisional](add-update-and-delete-data-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="d7c12-121">[Load or Update Members in Master Data Services by Using the Staging Process](add-update-and-delete-data-master-data-services.md) </span></span>  
 <span data-ttu-id="d7c12-122">[Cree un miembro consolidado &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-consolidated-member-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="d7c12-122">[Create a Consolidated Member &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-consolidated-member-master-data-services.md) </span></span>  
 [<span data-ttu-id="d7c12-123">Miembros &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d7c12-123">Members &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/members-master-data-services.md)  
  
  
