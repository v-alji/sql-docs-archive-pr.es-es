---
title: Creación de la directiva Finance Name | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 56b2c852-fd69-4cd2-9b5d-977467b94fd9
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 44ffff45f126d2ad9b73c5b8410b8f89ad2b0604
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663427"
---
# <a name="create-the-finance-name-policy"></a><span data-ttu-id="35fde-102">Crear la directiva Finance Name</span><span class="sxs-lookup"><span data-stu-id="35fde-102">Create the Finance Name Policy</span></span>
  <span data-ttu-id="35fde-103"> En esta tarea, creará una base de datos denominada Finance y, después, una condición que requiera que los nombres de todas las tablas comiencen con las letras **fintbl**.</span><span class="sxs-lookup"><span data-stu-id="35fde-103">In this task, you will create a database named Finance, and then create a condition that requires all tables to start with the letters **fintbl**.</span></span> <span data-ttu-id="35fde-104">A continuación, creará una directiva y una categoría de directivas para exigir una denominación estándar para las tablas de la base de datos Finance.</span><span class="sxs-lookup"><span data-stu-id="35fde-104">Then, you will create a policy and policy category to enforce a naming standard for tables in the Finance database.</span></span>  
  
### <a name="to-create-the-finance-database"></a><span data-ttu-id="35fde-105">Para crear la base de datos Finance</span><span class="sxs-lookup"><span data-stu-id="35fde-105">To create the Finance database</span></span>  
  
1.  <span data-ttu-id="35fde-106">En [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], abra una ventana de consulta y ejecute la instrucción siguiente:</span><span class="sxs-lookup"><span data-stu-id="35fde-106">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], open a query window and execute the following statement:</span></span>  
  
    ```  
    CREATE DATABASE Finance ;  
    GO  
    ```  
  
2.  <span data-ttu-id="35fde-107">En el Explorador de objetos, haga clic en **Bases de datos**y, a continuación, presione F5 para actualizar la lista de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="35fde-107">In Object Explorer, click **Databases**, and then press F5 to refresh the list of databases.</span></span>  
  
### <a name="to-create-the-finance-tables-condition"></a><span data-ttu-id="35fde-108">Para crear la condición Finance Tables</span><span class="sxs-lookup"><span data-stu-id="35fde-108">To create the Finance Tables condition</span></span>  
  
1.  <span data-ttu-id="35fde-109">En el Explorador de objetos, expanda **Administración**, expanda **Administración de directivas**, haga clic con el botón derecho en **Condiciones**y, después, haga clic en **Nueva condición**.</span><span class="sxs-lookup"><span data-stu-id="35fde-109">In Object Explorer, expand **Management**, expand **Policy Management**, right-click **Conditions**, and then click **New Condition**.</span></span>  
  
2.  <span data-ttu-id="35fde-110">En el cuadro de diálogo **Crear nueva condición** , en el cuadro **Nombre** , escriba **Finance Tables**.</span><span class="sxs-lookup"><span data-stu-id="35fde-110">In the **Create New Condition** dialog box, in the **Name** box, type **Finance Tables**.</span></span>  
  
3.  <span data-ttu-id="35fde-111">En la lista **Faceta** , seleccione **Nombre de varias partes**.</span><span class="sxs-lookup"><span data-stu-id="35fde-111">In the **Facet** list, select **Multipart Name**.</span></span>  
  
4.  <span data-ttu-id="35fde-112">En el área **expresión** , en el **cuadro campo** , seleccione \*\* \@ nombre\*\*; en el cuadro **operador** , seleccione **like**; y en el cuadro **valor** , escriba **' fintbl% '** para forzar que todos los nombres de tabla comiencen con las letras **fintbl**.</span><span class="sxs-lookup"><span data-stu-id="35fde-112">In the **Expression** area, in the **Field** box, select **\@Name**; in the **Operator** box, select **Like**; and in the **Value** box, type **'fintbl%'** to force all table names to start with the letters **fintbl**.</span></span>  
  
5.  <span data-ttu-id="35fde-113">En la página **Descripción** , escriba **Los nombres de tablas de finanzas deben comenzar con fintbl**y, a continuación, haga clic en **Aceptar** para crear la condición.</span><span class="sxs-lookup"><span data-stu-id="35fde-113">On the **Description** page, type **Finance table names must begin with fintbl**, and then click **OK** to create the condition.</span></span>  
  
### <a name="to-create-the-finance-name-policy"></a><span data-ttu-id="35fde-114">Para crear la directiva Finance Name</span><span class="sxs-lookup"><span data-stu-id="35fde-114">To create the Finance Name policy</span></span>  
  
1.  <span data-ttu-id="35fde-115">En el Explorador de objetos, haga clic con el botón derecho en **Directivas**y, después, haga clic en **Nueva directiva**.</span><span class="sxs-lookup"><span data-stu-id="35fde-115">In Object Explorer, right-click **Policies**, and then click **New Policy**.</span></span>  
  
2.  <span data-ttu-id="35fde-116">En el cuadro de diálogo **Crear nueva directiva** , en el cuadro **Nombre** , escriba **Finance Name**.</span><span class="sxs-lookup"><span data-stu-id="35fde-116">In the **Create New Policy** dialog box, in the **Name** box, type **Finance Name**.</span></span>  
  
3.  <span data-ttu-id="35fde-117">En la lista **Condición de comprobación** , seleccione **Finance Tables**.</span><span class="sxs-lookup"><span data-stu-id="35fde-117">In the **Check condition** list, select **Finance Tables**.</span></span> <span data-ttu-id="35fde-118">Está en el área **Nombre de varias partes** .</span><span class="sxs-lookup"><span data-stu-id="35fde-118">This is in the **Multipart Name** area.</span></span>  
  
4.  <span data-ttu-id="35fde-119">En el área **Contra** verá una lista de los objetos de base de datos que podrían aplicar esta directiva.</span><span class="sxs-lookup"><span data-stu-id="35fde-119">In the **Against** area you will see a list of the database objects that could apply this policy.</span></span> <span data-ttu-id="35fde-120">Active la casilla de **Cada tabla**.</span><span class="sxs-lookup"><span data-stu-id="35fde-120">Select the check box for **Every Table**.</span></span>  
  
5.  <span data-ttu-id="35fde-121">En el área **Cada base de datos** , expanda **Cada**y, a continuación, haga clic en **Nueva condición**.</span><span class="sxs-lookup"><span data-stu-id="35fde-121">In the **Every Database** area, expand **Every**, and then click **New condition**.</span></span>  
  
6.  <span data-ttu-id="35fde-122">En el cuadro de diálogo **Crear nueva condición** , en el cuadro **Nombre** , escriba **Finance Database**.</span><span class="sxs-lookup"><span data-stu-id="35fde-122">In the **Create New Condition** dialog box, in the **Name** box, type **Finance Database**.</span></span>  
  
7.  <span data-ttu-id="35fde-123">En el cuadro **expresión** , complete la expresión para incluir \*\* \@ name = ' Finance '\*\* y, a continuación, haga clic en **Aceptar** para cerrar la página condición.</span><span class="sxs-lookup"><span data-stu-id="35fde-123">In the **Expression** box, complete the expression to include **\@Name = 'Finance'**, and then click **OK** to close the condition page.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="35fde-124">Es posible que tenga que salir del cuadro **Valor** para habilitar el botón **Aceptar** .</span><span class="sxs-lookup"><span data-stu-id="35fde-124">You might have to tab out of the **Value** box to enable the **OK** button.</span></span>  
  
8.  <span data-ttu-id="35fde-125">En la lista **Modo de evaluación** , seleccione **Al cambiar: impedir**.</span><span class="sxs-lookup"><span data-stu-id="35fde-125">In the **Evaluation Mode** list, select **On change: prevent**.</span></span> <span data-ttu-id="35fde-126">Esto exigirá la directiva creando un desencadenador de base de datos en la base de datos Finance.</span><span class="sxs-lookup"><span data-stu-id="35fde-126">This will enforce the policy by creating a database trigger on the Finance database.</span></span>  
  
9. <span data-ttu-id="35fde-127">Seleccione la lista **Habilitado** .</span><span class="sxs-lookup"><span data-stu-id="35fde-127">Select the **Enabled** list.</span></span> <span data-ttu-id="35fde-128">(El cuadro **Habilitado** no se aplica a las directivas **A petición** ).</span><span class="sxs-lookup"><span data-stu-id="35fde-128">(The **Enabled** box does not apply to **On demand** policies.)</span></span>  
  
10. <span data-ttu-id="35fde-129">En la lista **Restricción de servidor** , seleccione **Ninguna**.</span><span class="sxs-lookup"><span data-stu-id="35fde-129">In the **Server restriction** list, select **None**.</span></span>  
  
11. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-create-the-finance-policy-category"></a><span data-ttu-id="35fde-130">Para crear la categoría de directivas Finance</span><span class="sxs-lookup"><span data-stu-id="35fde-130">To create the Finance policy category</span></span>  
  
1.  <span data-ttu-id="35fde-131">En el Explorador de objetos, expanda **Administración**, haga clic con el botón derecho en **Administración de directivas**y, después, haga clic en **Administrar categorías**.</span><span class="sxs-lookup"><span data-stu-id="35fde-131">In Object Explorer, expand **Management**, right-click **Policy Management**, and then click **Manage Categories**.</span></span>  
  
2.  <span data-ttu-id="35fde-132">En el cuadro de diálogo **administrar categorías de directiva** , en **nombre**, escriba `Finance` en el cuadro en blanco y, a continuación, desactive las **suscripciones de base de datos de autorización**.</span><span class="sxs-lookup"><span data-stu-id="35fde-132">In the **Manage Policy Categories** dialog box, under **Name**, type `Finance` in the blank box, and then clear **Mandate Database Subscriptions**.</span></span> <span data-ttu-id="35fde-133">**Suscripciones de base de datos de mandatos** exigirá que cada base de datos en la instancia se suscriba a las directivas que pertenecen a esta categoría de directiva.</span><span class="sxs-lookup"><span data-stu-id="35fde-133">**Mandate Database Subscriptions** will force every database in the instance to subscribe to the policies that belong to this policy category.</span></span> <span data-ttu-id="35fde-134">Para esta lección, solo la base de datos Finance debería suscribirse a la directiva Finance Name.</span><span class="sxs-lookup"><span data-stu-id="35fde-134">For this lesson, only the Finance database should subscribe to the Finance Name policy.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="35fde-135">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="35fde-135">Next Task in Lesson</span></span>  
 [<span data-ttu-id="35fde-136">Suscribirse a, y comprobar, la directiva Finance Name</span><span class="sxs-lookup"><span data-stu-id="35fde-136">Subscribe to and Check the Finance Name Policy</span></span>](lesson-2-2-subscribe-to-and-check-the-finance-name-policy.md)  
  
  
