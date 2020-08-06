---
title: Anotar una transacción (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- annotations [Master Data Services], for transactions
ms.assetid: f5a6b2ca-56de-4e42-9da8-fba0ac3e8d92
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c384f4241d0ddcd78fd8942fe28da8c0b5b1e77c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747075"
---
# <a name="annotate-a-transaction-master-data-services"></a><span data-ttu-id="dac08-102">Anotar una transacción (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="dac08-102">Annotate a Transaction (Master Data Services)</span></span>
  <span data-ttu-id="dac08-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], agregue una anotación a una transacción si desea proporcionar más información sobre la transacción con fines históricos.</span><span class="sxs-lookup"><span data-stu-id="dac08-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], annotate a transaction when you want to provide supporting details about the transaction for historical purposes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dac08-104">Las anotaciones no se pueden eliminar.</span><span class="sxs-lookup"><span data-stu-id="dac08-104">You cannot delete annotations.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="dac08-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="dac08-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="dac08-106">Para agregar transacciones que creó, debe contar con el permiso para obtener acceso al área funcional de **Explorador** y tener como mínimo el permiso **Actualizar** para el objeto del modelo al que desea agregar anotaciones.</span><span class="sxs-lookup"><span data-stu-id="dac08-106">To annotate transactions that you created, you must have permission to access the **Explorer** functional area, and have a minimum of **Update** permission to the model object you want to annotate.</span></span>  
  
-   <span data-ttu-id="dac08-107">Para agregar anotaciones a las transacciones para todos los usuarios, debe tener permiso de acceso al área funcional **Administración de versiones** y ser administrador de modelos.</span><span class="sxs-lookup"><span data-stu-id="dac08-107">To annotate transactions for all users, you must have permission to access the **Version Management** functional area and be a model administrator.</span></span> <span data-ttu-id="dac08-108">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="dac08-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-annotate-a-transaction-in-explorer"></a><span data-ttu-id="dac08-109">Para agregar anotaciones a una transacción en el Explorador</span><span class="sxs-lookup"><span data-stu-id="dac08-109">To annotate a transaction in Explorer</span></span>  
  
1.  <span data-ttu-id="dac08-110">En la página principal de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , en la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="dac08-110">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="dac08-111">En la lista **Versión** , seleccione una versión.</span><span class="sxs-lookup"><span data-stu-id="dac08-111">From the **Version** list, select a version.</span></span>  
  
3.  <span data-ttu-id="dac08-112">Haga clic en **Explorador**.</span><span class="sxs-lookup"><span data-stu-id="dac08-112">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="dac08-113">En la barra de menús, seleccione **Entidades** y haga clic en la entidad que contiene el miembro que incluye una transacción a la que desee agregar anotaciones.</span><span class="sxs-lookup"><span data-stu-id="dac08-113">From the menu bar, point to **Entities** and click the entity that contains the member with a transaction you want to annotate.</span></span>  
  
5.  <span data-ttu-id="dac08-114">En la cuadrícula, haga clic en la fila del miembro.</span><span class="sxs-lookup"><span data-stu-id="dac08-114">In the grid, click the row of the member.</span></span>  
  
6.  <span data-ttu-id="dac08-115">Haga clic en **Ver transacciones**.</span><span class="sxs-lookup"><span data-stu-id="dac08-115">Click **View Transactions**.</span></span>  
  
7.  <span data-ttu-id="dac08-116">En el cuadro de diálogo **Ver transacciones** , haga clic en la transacción a la que desea agregar anotaciones.</span><span class="sxs-lookup"><span data-stu-id="dac08-116">In the **View Transactions** dialog box, click the transaction you want to annotate.</span></span>  
  
8.  <span data-ttu-id="dac08-117">En el cuadro de la parte inferior del cuadro de diálogo, escriba su anotación.</span><span class="sxs-lookup"><span data-stu-id="dac08-117">In the box at the bottom of the dialog box, type your annotation.</span></span>  
  
9. <span data-ttu-id="dac08-118">Haga clic en **Agregar anotación**.</span><span class="sxs-lookup"><span data-stu-id="dac08-118">Click **Add Annotation**.</span></span> <span data-ttu-id="dac08-119">La anotación se muestra en el panel **Anotaciones** .</span><span class="sxs-lookup"><span data-stu-id="dac08-119">The annotation is displayed in the **Annotations** pane.</span></span>  
  
### <a name="to-annotate-a-transaction-in-version-management-administrators-only"></a><span data-ttu-id="dac08-120">Para agregar anotaciones a una transacción en Administración de versiones (solo administradores)</span><span class="sxs-lookup"><span data-stu-id="dac08-120">To annotate a transaction in Version Management (administrators only)</span></span>  
  
1.  <span data-ttu-id="dac08-121">En la página principal de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , haga clic en **Administración de versiones**.</span><span class="sxs-lookup"><span data-stu-id="dac08-121">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="dac08-122">En la barra de menús, haga clic en **Transacciones**.</span><span class="sxs-lookup"><span data-stu-id="dac08-122">On the menu bar, click **Transactions**.</span></span>  
  
3.  <span data-ttu-id="dac08-123">En el panel **Transacciones** , en la cuadrícula, haga clic en la fila de la transacción a la que desea agregar anotaciones.</span><span class="sxs-lookup"><span data-stu-id="dac08-123">In the **Transactions** pane, click the row in the grid for the transaction you want to annotate.</span></span>  
  
4.  <span data-ttu-id="dac08-124">En el panel **Anotaciones de transacción** , en el cuadro **Anotación** , escriba su anotación.</span><span class="sxs-lookup"><span data-stu-id="dac08-124">In the **Transaction Annotations** pane, in the **Annotation** box, type your annotation.</span></span>  
  
5.  <span data-ttu-id="dac08-125">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="dac08-125">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dac08-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dac08-126">See Also</span></span>  
 <span data-ttu-id="dac08-127">[Anotaciones &#40;Master Data Services&#41;](../../2014/master-data-services/annotations-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="dac08-127">[Annotations &#40;Master Data Services&#41;](../../2014/master-data-services/annotations-master-data-services.md) </span></span>  
 [<span data-ttu-id="dac08-128">Transacciones &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="dac08-128">Transactions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/transactions-master-data-services.md)  
  
  
