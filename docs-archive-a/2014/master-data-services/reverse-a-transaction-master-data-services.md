---
title: Invertir una transacción (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- transactions [Master Data Services], reversing
ms.assetid: 6f7c3f07-0f64-4283-8c9c-93facd00a046
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: fb5b1b0932b65b1d6f8fe7b1bc842836e21aaca6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745343"
---
# <a name="reverse-a-transaction-master-data-services"></a><span data-ttu-id="2b75b-102">Invertir una transacción (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="2b75b-102">Reverse a Transaction (Master Data Services)</span></span>
  <span data-ttu-id="2b75b-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], los administradores pueden invertir una transacción cuando sea necesario deshacer una acción.</span><span class="sxs-lookup"><span data-stu-id="2b75b-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], administrators can reverse a transaction when an action needs to be undone.</span></span> <span data-ttu-id="2b75b-104">Los ejemplos de transacciones son cambios del valor de atributo, movimientos de la jerarquía o eliminaciones de miembro.</span><span class="sxs-lookup"><span data-stu-id="2b75b-104">Examples of transactions are attribute value changes, hierarchy moves, or member deletions.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2b75b-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2b75b-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="2b75b-106">Debe disponer del permiso para tener acceso al área funcional de **Administración de versiones** .</span><span class="sxs-lookup"><span data-stu-id="2b75b-106">You must have permission to access the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="2b75b-107">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="2b75b-107">You must be a model administrator.</span></span> <span data-ttu-id="2b75b-108">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2b75b-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-reverse-a-transaction"></a><span data-ttu-id="2b75b-109">Para invertir una transacción</span><span class="sxs-lookup"><span data-stu-id="2b75b-109">To reverse a transaction</span></span>  
  
1.  <span data-ttu-id="2b75b-110">En la página principal de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , haga clic en **Administración de versiones**.</span><span class="sxs-lookup"><span data-stu-id="2b75b-110">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="2b75b-111">En la barra de menús, haga clic en **Transacciones**.</span><span class="sxs-lookup"><span data-stu-id="2b75b-111">On the menu bar, click **Transactions**.</span></span>  
  
3.  <span data-ttu-id="2b75b-112">En la página **Transacciones** , en la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="2b75b-112">On the **Transactions** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="2b75b-113">En la lista **Versión** , seleccione una versión.</span><span class="sxs-lookup"><span data-stu-id="2b75b-113">From the **Version** list, select a version.</span></span>  
  
5.  <span data-ttu-id="2b75b-114">Haga clic en la fila de la cuadrícula correspondiente a la transacción que desea invertir.</span><span class="sxs-lookup"><span data-stu-id="2b75b-114">Click the row in the grid for the transaction you want to reverse.</span></span>  
  
6.  <span data-ttu-id="2b75b-115">Haga clic en **Invertir transacción**.</span><span class="sxs-lookup"><span data-stu-id="2b75b-115">Click **Reverse Transaction**.</span></span>  
  
7.  <span data-ttu-id="2b75b-116">En el cuadro de diálogo de confirmación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2b75b-116">In the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="2b75b-117">Se agrega otra transacción a la cuadrícula para registrar la transacción invertida.</span><span class="sxs-lookup"><span data-stu-id="2b75b-117">Another transaction is added to the grid to record the reversed transaction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b75b-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2b75b-118">See Also</span></span>  
 <span data-ttu-id="2b75b-119">[Transacciones &#40;Master Data Services&#41;](../../2014/master-data-services/transactions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="2b75b-119">[Transactions &#40;Master Data Services&#41;](../../2014/master-data-services/transactions-master-data-services.md) </span></span>  
 [<span data-ttu-id="2b75b-120">Reactivar un miembro o una colección &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="2b75b-120">Reactivate a Member or Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/reactivate-a-member-or-collection-master-data-services.md)  
  
  
