---
title: Utilizar la ventana Propiedades en Management Studio
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- viewing properties
- Properties window [SQL Server Management Studio]
- complex properties [SQL Server Management Studio]
ms.assetid: 903d4aca-f57c-43d9-a893-702eceaa7004
author: rothja
ms.author: jroth
ms.openlocfilehash: 5030bf85fc87482b11e91967ff8fb1baf77a213e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676993"
---
# <a name="use-the-properties-window-in-management-studio"></a><span data-ttu-id="cf17b-102">Utilizar la ventana Propiedades en Management Studio</span><span class="sxs-lookup"><span data-stu-id="cf17b-102">Use the Properties Window in Management Studio</span></span>
  <span data-ttu-id="cf17b-103">La ventana Propiedades describe el estado de un elemento de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], como una conexión o un operador de plan de presentación, además de proporcionar información acerca de objetos de la base de datos, como tablas, vistas y diseñadores.</span><span class="sxs-lookup"><span data-stu-id="cf17b-103">The Properties window describes the state of an item in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], such as a connection or a Showplan operator, and information about database objects such as tables, views, and designers.</span></span>  
  
 <span data-ttu-id="cf17b-104">La ventana Propiedades se puede utilizar para ver las propiedades de la conexión actual.</span><span class="sxs-lookup"><span data-stu-id="cf17b-104">You can use the Properties window to view the properties of the current connection.</span></span> <span data-ttu-id="cf17b-105">Muchas propiedades son de solo lectura en la ventana Propiedades, aunque se pueden cambiar en otras ubicaciones de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf17b-105">Many properties are read-only in the Properties window but can be changed elsewhere in the [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="cf17b-106">Por ejemplo, la propiedad Database de una consulta es de solo lectura en la ventana Propiedades, aunque se puede cambiar en la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="cf17b-106">For example, the Database property of a query is read-only in the Properties window, but can be changed on the tool bar.</span></span>  
  
### <a name="to-view-properties-using-the-properties-window"></a><span data-ttu-id="cf17b-107">Para ver propiedades mediante la ventana Propiedades</span><span class="sxs-lookup"><span data-stu-id="cf17b-107">To view properties using the Properties window</span></span>  
  
1.  <span data-ttu-id="cf17b-108">Si la ventana Propiedades no está visible, haga clic en **Ventana Propiedades** en el menú **Ver** o presione F4.</span><span class="sxs-lookup"><span data-stu-id="cf17b-108">If the Properties window is not visible, click **Properties Window** on the **View** menu, or press F4.</span></span>  
  
2.  <span data-ttu-id="cf17b-109">Establezca el foco en el objeto que desea ver.</span><span class="sxs-lookup"><span data-stu-id="cf17b-109">Set the focus on the object that you want to view.</span></span>  
  
3.  <span data-ttu-id="cf17b-110">Busque una propiedad específica en la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="cf17b-110">Look for a specific property in the Properties window.</span></span>  
  
### <a name="to-view-connection-properties-of-a-query-window"></a><span data-ttu-id="cf17b-111">Para ver las propiedades de conexión de una ventana de consulta</span><span class="sxs-lookup"><span data-stu-id="cf17b-111">To view connection properties of a query window</span></span>  
  
1.  <span data-ttu-id="cf17b-112">Si la ventana Propiedades no está visible, haga clic en **Ventana Propiedades** en el menú **Ver** o presione F4.</span><span class="sxs-lookup"><span data-stu-id="cf17b-112">If the Properties window is not visible, click **Properties Window** on the **View** menu, or press F4.</span></span>  
  
2.  <span data-ttu-id="cf17b-113">En la ventana Propiedades podrá ver todas las propiedades de conexión.</span><span class="sxs-lookup"><span data-stu-id="cf17b-113">In the Properties window, you can see all the connection properties.</span></span>  
  
### <a name="to-view-the-properties-of-a-showplan-operator"></a><span data-ttu-id="cf17b-114">Para ver las propiedades de un operador de plan de presentación</span><span class="sxs-lookup"><span data-stu-id="cf17b-114">To view the properties of a Showplan operator</span></span>  
  
1.  <span data-ttu-id="cf17b-115">En el menú **Consulta** , haga clic en **Incluir plan de ejecución real**.</span><span class="sxs-lookup"><span data-stu-id="cf17b-115">On the **Query** menu, click **Include Actual Execution Plan**.</span></span>  
  
2.  <span data-ttu-id="cf17b-116">En el Editor de consultas de SQL, escriba y ejecute una consulta.</span><span class="sxs-lookup"><span data-stu-id="cf17b-116">In the SQL Query Editor, type and execute a query.</span></span>  
  
3.  <span data-ttu-id="cf17b-117">Si la ventana Propiedades no está visible, haga clic en **Ventana Propiedades** en el menú **Ver** o presione F4.</span><span class="sxs-lookup"><span data-stu-id="cf17b-117">If the Properties window is not visible, click **Properties Window** on the **View** menu, or press F4.</span></span>  
  
4.  <span data-ttu-id="cf17b-118">En la pestaña **Plan de ejecución** del Editor de consultas de SQL, haga clic en los iconos de los operadores para ver información sobre éstos en la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="cf17b-118">On the **Execution plan** tab of the SQL Query Editor click the icons of the operators to view information about the operators in the Properties window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf17b-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cf17b-119">See Also</span></span>  
 [<span data-ttu-id="cf17b-120">Ventana Propiedades &#40;Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="cf17b-120">Properties Window &#40;Management Studio&#41;</span></span>](../../ssms/properties-window-management-studio.md)  
  
  
