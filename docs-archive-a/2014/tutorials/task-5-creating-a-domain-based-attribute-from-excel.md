---
title: 'Tarea 5: crear un atributo basado en dominio desde Excel | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 07cbc624-2c6b-4568-96e4-f18663a05d80
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: b866478150fb4c06a3c4ea1ee6c227527f963219
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746059"
---
# <a name="task-5-creating-a-domain-based-attribute-from-excel"></a><span data-ttu-id="39392-102">Tarea 5: Creación de un atributo basado en dominio desde Excel</span><span class="sxs-lookup"><span data-stu-id="39392-102">Task 5: Creating a Domain-Based Attribute from Excel</span></span>
  <span data-ttu-id="39392-103">En esta tarea, convierta el atributo **Estado** de la entidad **proveedor** como un **atributo basado en dominio**.</span><span class="sxs-lookup"><span data-stu-id="39392-103">In this task, you convert the **State** attribute of the **Supplier** entity as a **domain-based attribute**.</span></span> <span data-ttu-id="39392-104">Después de configurar el atributo State para que sea uno basado en dominio y publicarlo en MDS, se creará una nueva entidad denominada **State** en el servidor MDS con todos los valores de la columna y el atributo **State** de la entidad **proveedor** se rellenará con los valores de la entidad **Estado** .</span><span class="sxs-lookup"><span data-stu-id="39392-104">After you configure the State attribute to be a domain-based one and publish it to MDS, a new entity named **State** will be created on MDS server with all the values in the column and the **State** attribute of the **Supplier** entity will be populated with values from the **State** entity.</span></span> <span data-ttu-id="39392-105">Ahora, el modelo **proveedores** debe tener dos entidades: **proveedor** y **Estado** , donde el atributo **Estado** de la entidad **proveedor** es un atributo basado en dominio que depende de la entidad **Estado** .</span><span class="sxs-lookup"><span data-stu-id="39392-105">Now, the **Suppliers** model should have two entities: **Supplier** and **State** where the **State** attribute of the **Supplier** entity is a domain-based attribute that depends on **State** entity.</span></span>  
  
1.  <span data-ttu-id="39392-106">Cambie a la ventana de **Excel** que tiene la **limpieza y coincidencia Suppliers.xlsx** abrir.</span><span class="sxs-lookup"><span data-stu-id="39392-106">Switch to **Excel** window that has **Cleansed and Matched Suppliers.xlsx** open.</span></span>  
  
2.  <span data-ttu-id="39392-107">Haga clic en el botón **Actualizar** de la cinta de opciones para obtener las actualizaciones más recientes de MDS.</span><span class="sxs-lookup"><span data-stu-id="39392-107">Click **Refresh** button on the ribbon to get the latest updates from MDS.</span></span> <span data-ttu-id="39392-108">Debería ver los dos registros más si ha realizado la **tarea 4**opcional.</span><span class="sxs-lookup"><span data-stu-id="39392-108">You should see the two more records if you have performed the optional **Task 4**.</span></span>  
  
3.  <span data-ttu-id="39392-109">Haga clic en el nombre de columna **State** (celda **I1**) en la **fila de encabezado**.</span><span class="sxs-lookup"><span data-stu-id="39392-109">Click column name **State** (cell **I1**) in the **header row**.</span></span>  
  
     <span data-ttu-id="39392-110">![Excel - Botón Propiedades de los atributos](../../2014/tutorials/media/et-creatingadomainbasedattributefromexcel-01.jpg "Excel - Botón Propiedades de los atributos")</span><span class="sxs-lookup"><span data-stu-id="39392-110">![Excel - Attribute Properties Button](../../2014/tutorials/media/et-creatingadomainbasedattributefromexcel-01.jpg "Excel - Attribute Properties Button")</span></span>  
  
4.  <span data-ttu-id="39392-111">Haga clic en **propiedades de atributo** en la cinta de opciones.</span><span class="sxs-lookup"><span data-stu-id="39392-111">Click **Attribute Properties** on the ribbon.</span></span>  
  
5.  <span data-ttu-id="39392-112">En el cuadro de diálogo **propiedades de atributo** , seleccione **lista restringida (basada en dominio)** para el **tipo de atributo**.</span><span class="sxs-lookup"><span data-stu-id="39392-112">In the **Attribute Properties** dialog box, select **Constrained list (Domain-based)** for the **Attribute type**.</span></span>  
  
6.  <span data-ttu-id="39392-113">Escriba **Estado** para el **nuevo nombre de entidad** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="39392-113">Type **State** for the **New entity name** and click **OK**.</span></span>  
  
     <span data-ttu-id="39392-114">![Excel - Cuadro de diálogo Propiedades de los atributos](../../2014/tutorials/media/et-creatingadomainbasedattributefromexcel-02.jpg "Excel - Cuadro de diálogo Propiedades de los atributos")</span><span class="sxs-lookup"><span data-stu-id="39392-114">![Excel - Attribute Properties Dialog Box](../../2014/tutorials/media/et-creatingadomainbasedattributefromexcel-02.jpg "Excel - Attribute Properties Dialog Box")</span></span>  
  
7.  <span data-ttu-id="39392-115">Ahora, en Excel, debería ver la **flecha abajo** al hacer clic en cualquier valor de la columna **Estado** .</span><span class="sxs-lookup"><span data-stu-id="39392-115">Now, in Excel, you should see **down arrow** when you click any value in the **State** column.</span></span> <span data-ttu-id="39392-116">Puede cambiar el valor mediante la lista desplegable si es necesario.</span><span class="sxs-lookup"><span data-stu-id="39392-116">You can change the value by using the drop-down list if you need.</span></span>  
  
     <span data-ttu-id="39392-117">![Excel - Lista desplegable con los estados](../../2014/tutorials/media/et-creatingadomainbasedattributefromexcel-03.jpg "Excel - Lista desplegable con los estados")</span><span class="sxs-lookup"><span data-stu-id="39392-117">![Excel - Drop Down List with States](../../2014/tutorials/media/et-creatingadomainbasedattributefromexcel-03.jpg "Excel - Drop Down List with States")</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="39392-118">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="39392-118">Next Step</span></span>  
 [<span data-ttu-id="39392-119">Tarea 6: Comprobación de que el atributo basado en dominio se crea mediante Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="39392-119">Task 6: Verify that the Domain-Based Attribute is Created using Master Data Manager</span></span>](../../2014/tutorials/task-6-verify-domain-based-attribute-master-data-manager.md)  
  
  
