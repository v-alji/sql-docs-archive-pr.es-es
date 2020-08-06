---
title: 'Tarea 6: comprobar que el atributo basado en dominio se crea con Master Data Manager | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 6e90517a-910c-4c33-8f11-92ac3cff4fdc
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ea26202ca9e607058b1e385957be3ea3d04038b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662399"
---
# <a name="task-6-verify-that-the-domain-based-attribute-is-created-using-master-data-manager"></a><span data-ttu-id="e231f-102">Tarea 6: Comprobación de que el atributo basado en dominio se crea mediante Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="e231f-102">Task 6: Verify that the Domain-Based Attribute is Created using Master Data Manager</span></span>
  <span data-ttu-id="e231f-103">En esta tarea, comprobará que se crea la entidad **Estado** en **MDS** y que el atributo **State** de la entidad **Proveedor** es un atributo basado en dominio que depende de la entidad **Estado** mediante **Master Data Manager**.</span><span class="sxs-lookup"><span data-stu-id="e231f-103">In this task, you verify that the **State** entity is created in **MDS** and the **State** attribute of the **Supplier** entity is a domain-based attribute that depends on the **State** entity by using **Master Data Manager**.</span></span>

1.  <span data-ttu-id="e231f-104">Cambie a la aplicación web **Master Data Manager**.</span><span class="sxs-lookup"><span data-stu-id="e231f-104">Switch to the **Master Data Manger** web application.</span></span>

2.  <span data-ttu-id="e231f-105">Haga clic en **SQL Server 2012 Master Data Services** en la parte superior para ir a la página principal.</span><span class="sxs-lookup"><span data-stu-id="e231f-105">Click **SQL Server 2012 Master Data Services** at the top to get to the home page.</span></span>

3.  <span data-ttu-id="e231f-106">Asegúrese de que el modelo **Proveedores** está seleccionado y haga clic en **Explorador**.</span><span class="sxs-lookup"><span data-stu-id="e231f-106">Ensure that **Suppliers** model is selected and click **Explorer**.</span></span> <span data-ttu-id="e231f-107">Puede actualizar la página si ya tiene abierto **Explorador**.</span><span class="sxs-lookup"><span data-stu-id="e231f-107">You could refresh the page if you already had **Explorer** open.</span></span>

4.  <span data-ttu-id="e231f-108">Mantenga el mouse sobre **Entidades** en la barra de menús y observe que ahora hay dos entidades: **Proveedor** y **Estado**.</span><span class="sxs-lookup"><span data-stu-id="e231f-108">Hover your mouse over **Entities** on the menu bar and notice that now there are two entities: **Supplier** and **State**.</span></span>

     <span data-ttu-id="e231f-109">![Menú de entidades con estado y proveedor](../../2014/tutorials/media/et-verifythatthedbaiscreatedusingmdm-01.jpg "Menú de entidades con estado y proveedor")</span><span class="sxs-lookup"><span data-stu-id="e231f-109">![Entities Menu with State and Supplier](../../2014/tutorials/media/et-verifythatthedbaiscreatedusingmdm-01.jpg "Entities Menu with State and Supplier")</span></span>

5.  <span data-ttu-id="e231f-110">Haga clic en **Estado** si la entidad no está abierta todavía.</span><span class="sxs-lookup"><span data-stu-id="e231f-110">Click **State** if the entity is not open already.</span></span>

6.  <span data-ttu-id="e231f-111">Seleccione **GA** en la lista.</span><span class="sxs-lookup"><span data-stu-id="e231f-111">Select **GA** from the list.</span></span>

7.  <span data-ttu-id="e231f-112">En el panel **Detalles** de la derecha, cambie el **Nombre** a **Georgia** en el **panel derecho** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e231f-112">In the **Details** pane to the right, change the **Name** to **Georgia** in the **right pane**, and click **OK**.</span></span>

8.  <span data-ttu-id="e231f-113">Repita los pasos anteriores para otros estados.</span><span class="sxs-lookup"><span data-stu-id="e231f-113">Repeat the previous steps for other states.</span></span>

    |<span data-ttu-id="e231f-114">Código</span><span class="sxs-lookup"><span data-stu-id="e231f-114">Code</span></span>|<span data-ttu-id="e231f-115">Nombre</span><span class="sxs-lookup"><span data-stu-id="e231f-115">Name</span></span>|
    |----------|----------|
    |<span data-ttu-id="e231f-116">CA</span><span class="sxs-lookup"><span data-stu-id="e231f-116">CA</span></span>|<span data-ttu-id="e231f-117">California</span><span class="sxs-lookup"><span data-stu-id="e231f-117">California</span></span>|
    |<span data-ttu-id="e231f-118">CO</span><span class="sxs-lookup"><span data-stu-id="e231f-118">CO</span></span>|<span data-ttu-id="e231f-119">Colorado</span><span class="sxs-lookup"><span data-stu-id="e231f-119">Colorado</span></span>|
    |<span data-ttu-id="e231f-120">IL</span><span class="sxs-lookup"><span data-stu-id="e231f-120">IL</span></span>|<span data-ttu-id="e231f-121">Illinois</span><span class="sxs-lookup"><span data-stu-id="e231f-121">Illinois</span></span>|
    |<span data-ttu-id="e231f-122">DC</span><span class="sxs-lookup"><span data-stu-id="e231f-122">DC</span></span>|<span data-ttu-id="e231f-123">Distrito de Columbia</span><span class="sxs-lookup"><span data-stu-id="e231f-123">District of Columbia</span></span>|
    |<span data-ttu-id="e231f-124">FL</span><span class="sxs-lookup"><span data-stu-id="e231f-124">FL</span></span>|<span data-ttu-id="e231f-125">Florida</span><span class="sxs-lookup"><span data-stu-id="e231f-125">Florida</span></span>|
    |<span data-ttu-id="e231f-126">AL</span><span class="sxs-lookup"><span data-stu-id="e231f-126">AL</span></span>|<span data-ttu-id="e231f-127">Alabama</span><span class="sxs-lookup"><span data-stu-id="e231f-127">Alabama</span></span>|
    |<span data-ttu-id="e231f-128">KY</span><span class="sxs-lookup"><span data-stu-id="e231f-128">KY</span></span>|<span data-ttu-id="e231f-129">Kentucky</span><span class="sxs-lookup"><span data-stu-id="e231f-129">Kentucky</span></span>|
    |<span data-ttu-id="e231f-130">MA</span><span class="sxs-lookup"><span data-stu-id="e231f-130">MA</span></span>|<span data-ttu-id="e231f-131">Massachusetts</span><span class="sxs-lookup"><span data-stu-id="e231f-131">Massachusetts</span></span>|
    |<span data-ttu-id="e231f-132">AZ</span><span class="sxs-lookup"><span data-stu-id="e231f-132">AZ</span></span>|<span data-ttu-id="e231f-133">Arizona</span><span class="sxs-lookup"><span data-stu-id="e231f-133">Arizona</span></span>|
    |<span data-ttu-id="e231f-134">MI</span><span class="sxs-lookup"><span data-stu-id="e231f-134">MI</span></span>|<span data-ttu-id="e231f-135">Míchigan</span><span class="sxs-lookup"><span data-stu-id="e231f-135">Michigan</span></span>|
    |<span data-ttu-id="e231f-136">MN</span><span class="sxs-lookup"><span data-stu-id="e231f-136">MN</span></span>|<span data-ttu-id="e231f-137">Minnesota</span><span class="sxs-lookup"><span data-stu-id="e231f-137">Minnesota</span></span>|
    |<span data-ttu-id="e231f-138">NJ</span><span class="sxs-lookup"><span data-stu-id="e231f-138">NJ</span></span>|<span data-ttu-id="e231f-139">Nueva Jersey</span><span class="sxs-lookup"><span data-stu-id="e231f-139">New Jersey</span></span>|
    |<span data-ttu-id="e231f-140">NV</span><span class="sxs-lookup"><span data-stu-id="e231f-140">NV</span></span>|<span data-ttu-id="e231f-141">Nevada</span><span class="sxs-lookup"><span data-stu-id="e231f-141">Nevada</span></span>|
    |<span data-ttu-id="e231f-142">NY</span><span class="sxs-lookup"><span data-stu-id="e231f-142">NY</span></span>|<span data-ttu-id="e231f-143">Nueva York</span><span class="sxs-lookup"><span data-stu-id="e231f-143">New York</span></span>|
    |<span data-ttu-id="e231f-144">OH</span><span class="sxs-lookup"><span data-stu-id="e231f-144">OH</span></span>|<span data-ttu-id="e231f-145">Ohio</span><span class="sxs-lookup"><span data-stu-id="e231f-145">Ohio</span></span>|
    |<span data-ttu-id="e231f-146">Aceptar</span><span class="sxs-lookup"><span data-stu-id="e231f-146">OK</span></span>|<span data-ttu-id="e231f-147">Oklahoma</span><span class="sxs-lookup"><span data-stu-id="e231f-147">Oklahoma</span></span>|
    |<span data-ttu-id="e231f-148">O</span><span class="sxs-lookup"><span data-stu-id="e231f-148">OR</span></span>|<span data-ttu-id="e231f-149">Oregón</span><span class="sxs-lookup"><span data-stu-id="e231f-149">Oregon</span></span>|
    |<span data-ttu-id="e231f-150">PA</span><span class="sxs-lookup"><span data-stu-id="e231f-150">PA</span></span>|<span data-ttu-id="e231f-151">Pensilvania</span><span class="sxs-lookup"><span data-stu-id="e231f-151">Pennsylvania</span></span>|
    |<span data-ttu-id="e231f-152">SC</span><span class="sxs-lookup"><span data-stu-id="e231f-152">SC</span></span>|<span data-ttu-id="e231f-153">Carolina del Sur</span><span class="sxs-lookup"><span data-stu-id="e231f-153">South Carolina</span></span>|
    |<span data-ttu-id="e231f-154">KS</span><span class="sxs-lookup"><span data-stu-id="e231f-154">KS</span></span>|<span data-ttu-id="e231f-155">Kansas</span><span class="sxs-lookup"><span data-stu-id="e231f-155">Kansas</span></span>|
    |<span data-ttu-id="e231f-156">TN</span><span class="sxs-lookup"><span data-stu-id="e231f-156">TN</span></span>|<span data-ttu-id="e231f-157">Tennessee</span><span class="sxs-lookup"><span data-stu-id="e231f-157">Tennessee</span></span>|
    |<span data-ttu-id="e231f-158">TX</span><span class="sxs-lookup"><span data-stu-id="e231f-158">TX</span></span>|<span data-ttu-id="e231f-159">Texas</span><span class="sxs-lookup"><span data-stu-id="e231f-159">Texas</span></span>|
    |<span data-ttu-id="e231f-160">UT</span><span class="sxs-lookup"><span data-stu-id="e231f-160">UT</span></span>|<span data-ttu-id="e231f-161">Utah</span><span class="sxs-lookup"><span data-stu-id="e231f-161">Utah</span></span>|
    |<span data-ttu-id="e231f-162">VA</span><span class="sxs-lookup"><span data-stu-id="e231f-162">VA</span></span>|<span data-ttu-id="e231f-163">Virginia</span><span class="sxs-lookup"><span data-stu-id="e231f-163">Virginia</span></span>|
    |<span data-ttu-id="e231f-164">WA</span><span class="sxs-lookup"><span data-stu-id="e231f-164">WA</span></span>|<span data-ttu-id="e231f-165">Washington</span><span class="sxs-lookup"><span data-stu-id="e231f-165">Washington</span></span>|
    |<span data-ttu-id="e231f-166">WI</span><span class="sxs-lookup"><span data-stu-id="e231f-166">WI</span></span>|<span data-ttu-id="e231f-167">Wisconsin</span><span class="sxs-lookup"><span data-stu-id="e231f-167">Wisconsin</span></span>|
    |<span data-ttu-id="e231f-168">HI</span><span class="sxs-lookup"><span data-stu-id="e231f-168">HI</span></span>|<span data-ttu-id="e231f-169">Hawái</span><span class="sxs-lookup"><span data-stu-id="e231f-169">Hawaii</span></span>|
    |<span data-ttu-id="e231f-170">MD</span><span class="sxs-lookup"><span data-stu-id="e231f-170">MD</span></span>|<span data-ttu-id="e231f-171">Maryland</span><span class="sxs-lookup"><span data-stu-id="e231f-171">Maryland</span></span>|
    |<span data-ttu-id="e231f-172">CT</span><span class="sxs-lookup"><span data-stu-id="e231f-172">CT</span></span>|<span data-ttu-id="e231f-173">Connecticut</span><span class="sxs-lookup"><span data-stu-id="e231f-173">Connecticut</span></span>|

9. <span data-ttu-id="e231f-174">Seleccione cualquiera de las entradas de estado y haga clic en **Ver transacciones** en la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="e231f-174">Select any of the state entries and click **View Transactions** from the Toolbar.</span></span> <span data-ttu-id="e231f-175">Debe ver que la transacción para la actualización que acaba de realizar está en la lista de transacciones.</span><span class="sxs-lookup"><span data-stu-id="e231f-175">You should see the transaction for the update you just made is in the list of transactions.</span></span>

10. <span data-ttu-id="e231f-176">Mantenga el mouse sobre el menú **Entidades** y haga clic en **Proveedor**.</span><span class="sxs-lookup"><span data-stu-id="e231f-176">Hover the mouse over **Entities** menu and click **Supplier**.</span></span>

11. <span data-ttu-id="e231f-177">Ahora, observe que se puede cambiar un valor para el campo **State** en el panel **Detalles** mediante la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="e231f-177">Now, notice that a value for the **State** field can be changed in the **Details** pane by using the drop-down list.</span></span> <span data-ttu-id="e231f-178">También puede ver que en la lista de la izquierda y en la lista desplegable del panel **Detalles**, primero se muestra el código y después el nombre entre llaves.</span><span class="sxs-lookup"><span data-stu-id="e231f-178">You can also see that, in the list to the left and in the drop-down list in the **Details** pane, code is displayed first and then the name in curly braces.</span></span> <span data-ttu-id="e231f-179">Además, puede cambiar cualquier otro valor en el panel **Detalles**.</span><span class="sxs-lookup"><span data-stu-id="e231f-179">You can also change any other value in the **Details** pane.</span></span>

     <span data-ttu-id="e231f-180">![Atributo estado con código y nombres actualizados](../../2014/tutorials/media/et-verifythatthedbaiscreatedusingmdm-02.jpg "Atributo estado con código y nombres actualizados")</span><span class="sxs-lookup"><span data-stu-id="e231f-180">![State Attribute with Updated Code and Names](../../2014/tutorials/media/et-verifythatthedbaiscreatedusingmdm-02.jpg "State Attribute with Updated Code and Names")</span></span>

## <a name="next-step"></a><span data-ttu-id="e231f-181">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="e231f-181">Next Step</span></span>
 [<span data-ttu-id="e231f-182">Tarea 7: Visualización de las actualizaciones realizadas con Master Data Manager en Excel</span><span class="sxs-lookup"><span data-stu-id="e231f-182">Task 7: Viewing Updates Made using Master Data Manager in Excel</span></span>](../../2014/tutorials/task-7-viewing-updates-made-using-master-data-manager-in-excel.md)


