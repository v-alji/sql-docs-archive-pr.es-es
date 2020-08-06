---
title: Suscripción a la directiva Finance Name y comprobación | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 126b4c4c-2a1c-4701-a0ad-8de23fbd7306
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2bfe6f463d03fe8b95f000dc6f34dc0718a7729f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662857"
---
# <a name="subscribe-to-and-check-the-finance-name-policy"></a><span data-ttu-id="ac69d-102">Suscribirse a, y comprobar, la directiva Finance Name</span><span class="sxs-lookup"><span data-stu-id="ac69d-102">Subscribe to and Check the Finance Name Policy</span></span>
  <span data-ttu-id="ac69d-103">En esta tarea, configurará la base de datos Finance para suscribirse a la categoría de directivas Finance.</span><span class="sxs-lookup"><span data-stu-id="ac69d-103">In this task, you will configure the Finance database to subscribe to the Finance policy category.</span></span> <span data-ttu-id="ac69d-104">A continuación, probará la directiva Finance Name.</span><span class="sxs-lookup"><span data-stu-id="ac69d-104">Then, you will test the Finance Name policy.</span></span>  
  
### <a name="to-subscribe-to-the-finance-policy-category"></a><span data-ttu-id="ac69d-105">Para suscribirse a la categoría de directivas Finance</span><span class="sxs-lookup"><span data-stu-id="ac69d-105">To subscribe to the Finance policy category</span></span>  
  
1.  <span data-ttu-id="ac69d-106">En Explorador de objetos, expanda **bases de datos**, haga clic con el botón secundario `Finance` , seleccione **directivas**y, a continuación, haga clic en **categorías**.</span><span class="sxs-lookup"><span data-stu-id="ac69d-106">In Object Explorer, expand **Databases**, right-click `Finance`, point to **Policies**, and then click **Categories**.</span></span>  
  
2.  <span data-ttu-id="ac69d-107">Active la casilla **suscrito** para la `Finance` categoría.</span><span class="sxs-lookup"><span data-stu-id="ac69d-107">Select the **Subscribed** checkbox for the `Finance` category.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-test-the-enforcement-of-the-finance-name-policy"></a><span data-ttu-id="ac69d-108">Para probar la aplicación de la directiva Finance Name</span><span class="sxs-lookup"><span data-stu-id="ac69d-108">To test the enforcement of the Finance Name policy</span></span>  
  
1.  <span data-ttu-id="ac69d-109">En [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], abra una ventana de consulta.</span><span class="sxs-lookup"><span data-stu-id="ac69d-109">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], open a query window.</span></span> <span data-ttu-id="ac69d-110">Ejecute las instrucciones siguientes que intentan crear una tabla que infringe la directiva **Finance Name** .</span><span class="sxs-lookup"><span data-stu-id="ac69d-110">Execute the following statements that try to create a table that violates the **Finance Name** policy.</span></span> <span data-ttu-id="ac69d-111">La tabla infringe la directiva porque el nombre de tabla no comienza con las letras **fintbl**.</span><span class="sxs-lookup"><span data-stu-id="ac69d-111">The table violates the policy because the table name does not begin with the letters **fintbl**.</span></span>  
  
    ```  
    USE Finance ;  
    GO  
    CREATE TABLE NewTable  
    (Col1 int) ;  
    GO  
  
    ```  
  
     <span data-ttu-id="ac69d-112">Observe que la directiva evita que se cree la tabla y devuelve un mensaje informativo que proporciona el nombre de la directiva.</span><span class="sxs-lookup"><span data-stu-id="ac69d-112">Notice that the policy prevents the table from being created and returns an informational message that provides the policy name.</span></span>  
  
2.  <span data-ttu-id="ac69d-113">Para proporcionar un nombre válido, modifique el código como sigue y ejecute la instrucción de nuevo.</span><span class="sxs-lookup"><span data-stu-id="ac69d-113">To provide a valid name, modify the code as follows and run the statement again.</span></span>  
  
    ```  
    USE Finance ;  
    GO  
    CREATE TABLE fintblNewTable  
    (Col1 int) ;  
    GO  
  
    ```  
  
     <span data-ttu-id="ac69d-114">Esta vez, la tabla se crea.</span><span class="sxs-lookup"><span data-stu-id="ac69d-114">This time, the table is created.</span></span>  
  
### <a name="to-apply-the-policy-to-the-whole-server"></a><span data-ttu-id="ac69d-115">Para aplicar la directiva al servidor entero</span><span class="sxs-lookup"><span data-stu-id="ac69d-115">To apply the policy to the whole server</span></span>  
  
1.  <span data-ttu-id="ac69d-116">Actualmente, solo la base de datos Finance se suscribe a la categoría de directiva Finance.</span><span class="sxs-lookup"><span data-stu-id="ac69d-116">Currently, only the Finance database subscribes to the Finance policy category.</span></span> <span data-ttu-id="ac69d-117">En muchos casos, es más fácil aplicar la categoría de directiva a todo el servidor.</span><span class="sxs-lookup"><span data-stu-id="ac69d-117">In many cases, it is easier to apply the policy category to the whole server.</span></span> <span data-ttu-id="ac69d-118">En el Explorador de objetos, expanda **Administración**, haga clic con el botón derecho en **Administración de directivas**y, después, haga clic en **Administrar categorías**.</span><span class="sxs-lookup"><span data-stu-id="ac69d-118">In Object Explorer, expand **Management**, right-click **Policy Management**, and then click **Manage Categories**.</span></span>  
  
2.  <span data-ttu-id="ac69d-119">En el cuadro de diálogo **Administrar categorías de directiva** , busque la categoría Finance y seleccione la casilla **Suscripciones de base de datos de mandatos** para la categoría Finance.</span><span class="sxs-lookup"><span data-stu-id="ac69d-119">In the **Manage Policy Categories** dialog box, locate the Finance category, and select the **Mandate Database Subscriptions** checkbox for the Finance category.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)] <span data-ttu-id="ac69d-120">Ahora la categoría Finance se aplica a todas las bases de datos, pero la condición que ha creado restringe la directiva Finance Name a la base de datos Finance.</span><span class="sxs-lookup"><span data-stu-id="ac69d-120">Now the Finance category applies to all databases, but the condition that you have created restricts the Finance Name policy to the Finance database.</span></span> <span data-ttu-id="ac69d-121">De esta forma, se muestra cómo se pueden utilizar combinaciones complejas de condiciones para destinar las directivas de modo que se apliquen correctamente en muchos servidores.</span><span class="sxs-lookup"><span data-stu-id="ac69d-121">This shows how you can use complex combinations of conditions to target policies in ways that will apply correctly on many servers.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="ac69d-122">Resumen</span><span class="sxs-lookup"><span data-stu-id="ac69d-122">Summary</span></span>  
 <span data-ttu-id="ac69d-123">En este tutorial se ha demostrado cómo crear condiciones de la administración basada en directivas, directivas y grupos de directivas, y cómo aplicar los filtros y comprobar la compatibilidad de los destinos de la administración basada en directivas.</span><span class="sxs-lookup"><span data-stu-id="ac69d-123">This tutorial has shown you how to create Policy-Based Management conditions, policies and policy groups, and how to apply filters and check the compliance of Policy-Based Management targets.</span></span>  
  
## <a name="next"></a><span data-ttu-id="ac69d-124">Siguientes</span><span class="sxs-lookup"><span data-stu-id="ac69d-124">Next</span></span>  
 <span data-ttu-id="ac69d-125">Este tutorial ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="ac69d-125">This tutorial is finished.</span></span> <span data-ttu-id="ac69d-126">Para volver al inicio, haga clic en [Tutorial: Administrar servidores mediante administración basada en directivas](tutorial-administering-servers-by-using-policy-based-management.md).</span><span class="sxs-lookup"><span data-stu-id="ac69d-126">To return to the start, click [Tutorial: Administering Servers by Using Policy-Based Management](tutorial-administering-servers-by-using-policy-based-management.md).</span></span>  
  
 <span data-ttu-id="ac69d-127">Para obtener una lista de tutoriales, consulte los [tutoriales de SQL Server 2014](../../tutorials/tutorials-for-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="ac69d-127">For a list of tutorials, see [Tutorials for SQL Server 2014](../../tutorials/tutorials-for-sql-server-2014.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac69d-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ac69d-128">See Also</span></span>  
 [<span data-ttu-id="ac69d-129">Administrar servidores mediante administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="ac69d-129">Administer Servers by Using Policy-Based Management</span></span>](administer-servers-by-using-policy-based-management.md)  
  
  
